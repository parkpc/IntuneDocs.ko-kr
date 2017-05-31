---
title: "앱 래핑 도구를 사용하여 Android 앱 래핑 | Microsoft 문서"
description: "이 문서의 정보를 사용하여 앱 자체의 코드를 변경하지 않고 Android 앱을 줄 바꿈하는 방법에 대해 알아봅니다. 모바일 앱 관리 정책을 적용할 수 있도록 앱을 준비합니다."
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e9c349c8-51ae-4d73-b74a-6173728a520b
ms.reviewer: oldang
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: a89c2b26daf2b3b4da57e0c190f772e078681bee
ms.contentlocale: ko-kr
ms.lasthandoff: 05/23/2017


---

# <a name="prepare-android-apps-for-mobile-application-management-with-the-intune-app-wrapping-tool"></a>Intune 앱 래핑 도구를 사용하여 모바일 응용 프로그램 관리용 Android 앱 준비

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Android용 Microsoft Intune 앱 래핑 도구를 사용하여 해당 앱 코드를 변경하지 않고도 앱 기능을 제한하여 사내 Android 앱의 동작을 변경합니다.

이 도구는 PowerShell에서 실행되고 Android 앱 주위에 래퍼를 생성하는 Windows 명령줄 응용 프로그램입니다. 앱을 래핑한 후에는 Intune에서 [모바일 응용 프로그램 관리 정책](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md)을 구성하여 앱의 기능을 변경할 수 있습니다.


도구를 실행하기 전에 [앱 래핑 도구를 실행하기 위한 보안 고려 사항](#security-considerations-for-running-the-app-wrapping-tool)을 검토하세요. 이 도구를 다운로드하려면 GitHub의 [Microsoft Intune App Wrapping Tool for Android](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android)(Android용 Microsoft Intune 앱 래핑 도구)로 이동하세요.



## <a name="fulfill-the-prerequisites-for-using-the-app-wrapping-tool"></a>앱 래핑 도구의 필수 구성 요소 준비

-   앱 래핑 도구는 Windows 7 이상을 실행하는 Windows 컴퓨터에서 실행해야 합니다.

-   입력하는 앱은 파일 확장명이 .apk인 유효한 Android 응용 프로그램 패키지여야 합니다. 그리고

    -   암호화할 수 없습니다.
    -   Intune 앱 래핑 도구로 이미 래핑되지 않아야 합니다.
    -   Android 4.0 이상에서 작성해야 합니다.

-   앱이 회사에 의해 또는 회사를 위해 개발되어야 합니다. Google Play 스토어에서 다운로드한 앱에서 이 도구를 사용할 수 없습니다.

-   앱 래핑 도구를 실행하려면 최신 버전의 [Java 런타임 환경](http://java.com/download/)을 설치한 다음 Windows 환경 변수에 Java path 변수를 C:\ProgramData\Oracle\Java\javapath로 설정해야 합니다. 도움이 더 필요하면 [Java 설명서](http://java.com/download/help/)를 참조하세요.

    > [!NOTE]
    > 일부 경우에 32비트 버전의 Java에서 메모리 문제가 발생할 수 있습니다. 64비트 버전을 설치하는 것이 좋습니다.

- Android는 모든 앱 패키지(.apk)를 서명해야 합니다. Java keytool을 사용하여 래핑된 출력 앱에 서명하기 위해 필요한 자격 증명을 생성합니다. 예를 들어 다음 명령은 Java 실행 파일 keytool.exe를 사용하여 래핑된 출력 앱에 서명하기 위해 앱 래핑 도구에서 사용할 수 있는 키를 생성합니다.

    ```
    keytool.exe -genkeypair -v -keystore mykeystorefile -alias mykeyalias -keyalg RSA -keysize 2048 -validity 50000
    ```
    이 예제에서는 RSA 알고리즘을 사용하여 키 쌍(2,048비트 크기의 공개 키 및 개인 키)을 생성합니다. 그런 다음 공개 키를 X.509 v3 자체 서명된 인증서로 래핑하고, 이 공개 키는 단일 요소 인증서 체인으로 저장됩니다. 이 인증서 체인 및 개인 키는 "mykeystorefile"이라는 새 키 저장소 항목에 저장되고 "mykeyalias" 별칭으로 식별됩니다. 키 저장소 항목은 50,000일 동안 유효합니다.

    명령을 실행하면 키 저장소 및 키에 대한 암호를 제공하라는 메시지가 나타납니다. 안전한 암호를 사용하고, 나중에 앱 래핑 도구를 실행하는 데 필요하므로 암호를 적어 두세요.

    자세한 설명서는 Oracle 설명서 웹 사이트에서 Java [keytool](http://docs.oracle.com/javase/6/docs/technotes/tools/windows/keytool.html) 및 Java [KeyStore](https://docs.oracle.com/javase/7/docs/api/java/security/KeyStore.html)에 대해 읽으세요.

## <a name="install-the-app-wrapping-tool"></a>앱 래핑 도구 설치

1.  [GitHub 리포지토리](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android)에서 Android용 Intune 앱 래핑 도구에 대한 InstallAWT.exe 설치 파일을 Windows 컴퓨터에 다운로드합니다. 설치 파일을 엽니다.

2.  사용권 계약에 동의한 다음 설치를 완료합니다.

이 도구를 설치한 폴더를 메모해 둡니다. 기본 위치는 C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool입니다.

## <a name="run-the-app-wrapping-tool"></a>앱 래핑 도구 실행

1.  앱 줄 바꿈 도구를 설치한 Windows 컴퓨터의 관리자 모드에서 PowerShell 창을 엽니다.

2.  도구를 설치한 폴더에서 앱 래핑 도구 PowerShell 모듈을 가져옵니다.

    ```
    Import-Module .\IntuneAppWrappingTool.psm1
    ```

3.  **invoke-AppWrappingTool** 명령을 사용하여 도구를 실행합니다. 사용 구문은 다음과 같습니다.
    ```
    Invoke-AppWrappingTool [-InputPath] <String> [-OutputPath] <String> -KeyStorePath <String> -KeyStorePassword <SecureString>
    -KeyAlias <String> -KeyPassword <SecureString> [-SigAlg <String>] [<CommonParameters>]
    ```

 다음 표에 **invoke-AppWrappingTool** 명령의 속성이 자세히 나와 있습니다.

|속성|정보 산업|예|
|-------------|--------------------|---------|
|**-InputPath**&lt;String&gt;|원본 Android 앱(.apk)의 경로입니다.| |
|**-OutputPath**&lt;String&gt;|출력 Android 앱의 경로입니다. InputPath와 동일한 디렉터리 경로일 경우 패키징이 실패합니다.| |
|**-KeyStorePath**&lt;String&gt;|서명을 위한 공개/개인 키 쌍이 포함된 키 저장소 파일의 경로입니다.|기본적으로 키 저장소 파일은 "C:\Program Files (x86)\Java\jreX.X.X_XX\bin"에 저장됩니다. |
|**-KeyStorePassword**&lt;SecureString&gt;|키 저장소를 해독하는 데 사용되는 암호입니다. Android에서는 모든 응용 프로그램 패키지(.apk)가 서명되어야 합니다. Java keytool을 사용하여 KeyStorePassword를 생성합니다. 여기에서 Java [KeyStore](https://docs.oracle.com/javase/7/docs/api/java/security/KeyStore.html)(키 저장소)에 대해 자세히 읽으세요.| |
|**-KeyAlias**&lt;String&gt;|서명에 사용할 키의 이름입니다.| |
|**-KeyPassword**&lt;SecureString&gt;|서명에 사용될 개인 키의 암호를 해독하는 데 사용되는 암호입니다.| |
|**-SigAlg**&lt;SecureString&gt;| (선택 사항) 서명에 사용할 서명 알고리즘의 이름입니다. 이 알고리즘은 개인 키와 호환해야 합니다.|예: SHA256withRSA, SHA1withRSA, MD5withRSA|
| **&lt;CommonParameters&gt;** | (선택 사항) 명령은 verbose, debug와 같은 일반적인 PowerShell 매개 변수를 지원합니다. |


- 일반적인 매개 변수의 목록은 [Microsoft Script Center](https://technet.microsoft.com/library/hh847884.aspx)를 참조하세요.

- 도구에 대한 자세한 사용 정보를 보려면 명령을 입력합니다.

    ```
    Help Invoke-AppWrappingTool
    ```

**예:**

PowerShell 모듈을 가져옵니다.
```
Import-Module "C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool\IntuneAppWrappingTool.psm1"
```
네이티브 앱 HelloWorld.apk에서 앱 래핑 도구를 실행합니다.
```
invoke-AppWrappingTool -InputPath .\app\HelloWorld.apk -OutputPath .\app_wrapped\HelloWorld_wrapped.apk -KeyStorePath "C:\Program Files (x86)\Java\jre1.8.0_91\bin\mykeystorefile" -keyAlias mykeyalias -SigAlg SHA1withRSA -Verbose
```

**KeyStorePassword** 및 **KeyPassword**에 대한 메시지가 표시됩니다. 키 저장소 파일을 만드는 데 사용한 자격 증명을 입력합니다.

래핑된 앱과 로그 파일이 생성되고 지정한 출력 경로에 저장됩니다.

## <a name="security-considerations-for-running-the-app-wrapping-tool"></a>앱 래핑 도구를 실행하기 위한 보안 고려 사항
잠재적인 스푸핑, 정보 공개 및 권한 상승 공격을 방지하려면:

-   입력 LOB(기간 업무) 응용 프로그램, 출력 응용 프로그램 및 Java KeyStore가 앱 래핑 도구를 실행한 것과 같은 Windows 컴퓨터에 있는지 확인합니다.

-   출력 응용 프로그램을 도구가 실행 중인 것과 같은 컴퓨터의 Intune 콘솔에 가져옵니다. Java keytool에 대한 자세한 내용은 [keytool](https://docs.oracle.com/javase/8/docs/technotes/tools/unix/keytool.html)을 참조하세요.

-   출력 응용 프로그램 및 도구가 UNC(Universal Naming Convention) 경로에 있는데 도구와 입력 파일을 동일한 컴퓨터에서 실행하지 않는 경우, [IPsec(Internet Protocol Security)](http://wikipedia.org/wiki/IPsec) 또는 [SMB(Server Message Block) 서명](https://support.microsoft.com/kb/887429)을 사용하여 환경을 안전하게 설정합니다.

-   응용 프로그램이 신뢰할 수 있는 소스에서 오는지 확인합니다.

-   래핑된 앱을 포함하고 있는 출력 디렉터리를 보호합니다. 출력에 대한 사용자 수준 디렉터리를 사용하는 것이 좋습니다.

### <a name="see-also"></a>참고 항목
- [Microsoft Intune으로 모바일 응용 프로그램 관리용 앱을 준비하는 방법 결정](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md)

- [SDK를 사용하여 모바일 응용 프로그램 관리에 앱을 사용하도록 설정](use-the-sdk-to-enable-apps-for-mobile-application-management.md)

