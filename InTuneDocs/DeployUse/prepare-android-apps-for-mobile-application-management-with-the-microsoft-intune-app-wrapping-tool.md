---
title: "앱 줄 바꿈 도구를 사용하여 Android 앱 줄 바꿈 | Microsoft Intune"
description: "이 항목의 정보를 사용하여 앱 자체의 코드를 수정하지 않고 Android 앱을 줄 바꿈하는 방법에 대해 알아봅니다. 모바일 앱 관리 정책을 적용할 수 있도록 앱을 준비합니다."
keywords: 
author: karthikaraman
manager: arob98
ms.date: 07/06/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e9c349c8-51ae-4d73-b74a-6173728a520b
ms.reviewer: matgates
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2038ed6219a94dc4285891d71ce00fd51310f3e3
ms.openlocfilehash: 15d0877f799c89e2a8af65c416c0e914f898641f


---

# Intune 앱 래핑 도구를 사용하여 모바일 응용 프로그램 관리용 Android 앱 준비
**Android용 Microsoft Intune 앱 래핑 도구**를 사용하여 사내 Android 앱의 동작을 수정하면 해당 앱 코드를 수정하지 않고도 앱 기능을 구성할 수 있습니다.

이 도구는 PowerShell에서 실행되고 앱 주위에 ‘래퍼'를 생성하는 Windows 명령줄 응용 프로그램입니다. 앱을 처리한 후에는 구성하는 [모바일 응용 프로그램 관리 정책](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md)을 사용하여 앱의 기능을 변경할 수 있습니다.

앱에서 Azure ADAL(Active Directory 인증 라이브러리)을 사용하는 경우 앱을 래핑하기 전에 [Azure Active Directory 라이브러리를 사용하는 앱의 래핑 방법](#how-to-wrap-apps-that-use-the-azure-active-directory-library)의 단계를 완료해야 합니다. 앱이 해당 라이브러리를 사용하는지 확실치 않으면 앱의 개발자에게 문의하세요.

도구를 실행하기 전에 [앱 래핑 도구를 실행하기 위한 보안 고려 사항](#security-considerations-for-running-the-app-wrapping-tool)을 검토하세요. 이 도구를 다운로드하려면 [Android용 Microsoft Intune 앱 줄 바꿈 도구](https://www.microsoft.com/download/details.aspx?id=47267)를 참조하세요.

## 1단계 앱 래핑 도구 사용을 위한 필수 구성 요소 준비

-   앱 래핑 도구는 Windows 7 이상을 실행하는 Windows 컴퓨터에서 실행해야 합니다.

-   입력하는 앱은 확장명이 **.apk** 인 유효한 Android 응용 프로그램 패키지 파일이어야 합니다. 그리고:

    -   암호화할 수 없음

    -   앱 래핑 도구로 이미 래핑되지 않아야 함

    -   Android 4.0 이상에서 작성해야 함

-   앱이 회사에 의해 또는 회사를 위해 개발되어야 합니다. 이 도구를 사용하여 Google Play 스토어에서 다운로드한 앱을 처리할 수 없습니다.

-   앱 래핑 도구를 실행하려면 최신 버전의 [Java 런타임 환경](http://java.com/download/)을 설치한 다음 Windows 환경 변수에 Java path 변수를 **C:\ProgramData\Oracle\Java\javapath**로 설정해야 합니다. 도움이 더 필요하면 [Java 설명서](http://java.com/download/help/)를 참조하세요.

    > [!NOTE]
    > 일부 경우에 32비트 버전의 Java에서 메모리 문제가 발생할 수 있습니다. 64비트 버전을 대신 설치하는 것이 좋습니다.

## 2단계 앱 래핑 도구 설치

1.  Microsoft 다운로드 센터에서 앱 래핑 도구의 설치 파일을 Windows 컴퓨터에 다운로드하고 엽니다.

2.  사용권 계약에 동의한 다음 설치를 완료합니다.

이 도구를 설치한 폴더를 메모해 둡니다. 기본 위치는 **C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool**입니다.

## 3단계 앱 래핑 도구 실행

1.  앱 줄 바꿈 도구를 설치한 Windows 컴퓨터의 관리자 모드에서 PowerShell 창을 엽니다.

2.  도구를 설치한 폴더에서 앱 래핑 도구 PowerShell 모듈을 가져옵니다.

    ```
    Import-Module .\IntuneAppWrappingTool.psm1
    ```

3.  **invoke-AppWrappingTool** 명령과 다음 매개 변수를 사용하여 도구를 실행합니다. "선택 사항"으로 표시된 매개 변수는 Azure ADAL(Active Directory 인증 라이브러리)를 사용하는 앱을 위한 것입니다. 자세한 내용은 [Azure Active Directory 라이브러리를 사용하는 앱의 줄 바꿈 방법](#how-to-wrap-apps-that-use-the-azure-active-directory-library)항목을 참조하세요.

|매개 변수|추가 정보|예|
|-------------|--------------------|---------|
|**-InputPath**&lt;String&gt;|원본 Android 앱(.apk)의 경로입니다.| |
|**-OutputPath**&lt;String&gt;|"출력" Android 앱의 경로입니다. InputPath와 동일한 디렉터리 경로일 경우 패키징이 실패합니다.| |
|**-KeyStorePath**&lt;String&gt;|서명을 위한 공개/개인 키 쌍이 포함된 키 저장소 파일의 경로입니다.| |
|**-KeyStorePassword**&lt;SecureString&gt;|키 저장소를 해독하는 데 사용되는 암호입니다. Android에서는 모든 응용 프로그램 패키지(.apk)가 서명되어야 합니다. 예제에 표시된 대로 Java Key Tool을 사용하여 KeyStorePassword를 생성합니다. [keystore](https://docs.oracle.com/javase/7/docs/api/java/security/KeyStore.html)에 대해 자세히 알아보세요.|keytool.exe -genkey -v -keystore keystorefile -alias ks -keyalg RSA -keysize 2048 -validity 50000 |
|**-KeyAlias**&lt;String&gt;|서명에 사용할 키의 이름입니다.| |
|**-KeyPassword**&lt;SecureString&gt;|서명에 사용될 개인 키의 암호를 해독하는 데 사용되는 암호입니다.| |
|**-SigAlg**&lt;SecureString&gt;|서명에 사용할 서명 알고리즘의 이름입니다. 이 알고리즘은 개인 키와 호환해야 합니다.|예: SHA256withRSA, SHA1withRSA, MD5withRSA|
|**-ClientID**&lt;GUID&gt;|입력 앱의 Azure Active Directory 클라이언트 ID입니다(선택 사항).| |
|**-AuthorityURI**&lt;Uri&gt;|입력 앱의 Azure Active Directory 기관 URI입니다(선택 사항).| |
|**-SkipBroker**&lt;Boolean&gt;|입력 응용 프로그램이 장치 범위의 조정된 Single Sign-On을 지원하는지 나타냅니다(선택 사항). |**True** - 입력 응용 프로그램이 장치 범위의 조정된 Single Sign-On을 지원하지 않습니다. NonBrokerRedirectURI 매개 변수를 사용하십시오. **False** - 입력 응용 프로그램이 장치 범위의 조정된 Single Sign-On을 지원합니다.|
|**-NonBrokerRedirectURI**&lt;URI&gt;|SkipBroker가 true일 경우 사용할 Azure Active Directory 리디렉션 URI입니다(선택 사항).|  |


**&lt;CommonParameters&gt;**
    (선택 사항 - verbose, debug와 같은 일반적인 PowerShell 매개 변수 지원)

- 일반적인 매개 변수의 목록은 [Microsoft Script Center](https://technet.microsoft.com/library/hh847884.aspx)를 참조하세요.

- 도구에 대한 도움말을 보려면 다음 명령을 입력합니다.

    ```
    Help Invoke-AppWrappingTool
    ```
- AAD(Azure Active Directory) 통합에 대해 알아보려면 [Azure Active Directory 라이브러리를 사용하는 앱을 줄 바꿈하는 방법](#how-to-wrap-apps-that-use-the-azure-active-directory-library)을 참조하세요.

**예:**


    Import-Module "C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool\IntuneAppWrappingTool.psm1"
    invoke-AppWrappingTool -InputPath .\app\HelloWorld.apk -OutputPath .\app.wrapped\HelloWorld_wrapped2.apk -KeyStorePath "C:\Program Files (x86)\Java\jre1.8.0_91\bin\keystorefile" -keyAlias ks -SigAlg SHA1withRSA -Verbose

**KeyStorePassword** 및 **KeyPassword**에 대한 메시지가 표시됩니다.

지정한 출력 경로에 래핑된 앱이 생성되고 로그 파일과 함께 저장됩니다.

## 앱 래핑 도구를 실행하기 위한 보안 고려 사항
잠재적인 스푸핑, 정보 공개 및 권한 상승 공격을 방지하려면:

-   입력 업무용 응용 프로그램, 출력 응용 프로그램 및 Java KeyStore가 앱 래핑 도구를 실행한 것과 같은 컴퓨터에 있는지 확인합니다.

-   출력 응용 프로그램을 도구가 실행 중인 것과 같은 컴퓨터의 Intune 콘솔에 가져옵니다. Java keytool에 대한 자세한 내용은 [keytool](https://docs.oracle.com/javase/8/docs/technotes/tools/unix/keytool.html)을 참조하세요.

-   출력 응용 프로그램 및 도구가 UNC(Universal Naming Convention) 경로에 있는데 도구와 입력 파일을 동일한 컴퓨터에서 실행하지 않는 경우, [IPsec(Internet Protocol Security)](http://en.wikipedia.org/wiki/IPsec) 또는 [SMB(Server Message Block) 서명](https://support.microsoft.com/en-us/kb/887429)을 사용하여 환경을 안전하게 구성합니다.

-   응용 프로그램이 신뢰할 수 있는 소스에서 온 것인지, 특히 AAD(Azure Active Directory)를 사용하는 경우 런타임 중에 응용 프로그램이 AAD 토큰에 액세스할 수 있는지 확인하십시오.

-   래핑된 앱을 포함하고 있는 출력 디렉터리를 보호합니다. 출력에 대한 사용자 수준 디렉터리를 사용하는 것이 좋습니다.

## Azure Active Directory 라이브러리를 사용하는 앱을 래핑하는 방법
앱에서 Azure ADAL(Active Directory 인증 라이브러리)을 사용하는 경우 앱을 래핑하기 전에 이러한 단계를 완료해야 합니다.

### 1단계 ADAL에 대한 요구 사항을 충족하는지 확인
ADAL을 사용하는 앱은 다음 조건을 충족해야 합니다.

-   버전 1.0.2 이상의 ADAL이 통합되어 있어야 합니다.

-   개발자는 [3단계 AAD에서 모바일 응용 프로그램 관리에 대한 액세스 구성](#step-3-configure-access-to-mobile-app-management-in-aad)에 설명된 대로 Intune 모바일 응용 프로그램 관리 리소스에 대한 액세스 권한을 앱에 부여해야 합니다.

### 2단계 앱을 등록할 때 받아야 하는 ID 검토
다음 단계에서는 Azure 관리 포털을 사용하여 앱(AAD(Azure Active Directory)와 함께 ADAL을 사용)을 등록하여 다음 표에 나열된 고유 식별자를 받습니다. 그런 다음 앱을 ADAL과 통합할 때 식별자를 개발자에게 전달합니다.

|식별자|추가 정보|기본값|
|--------------|--------------------|-----------------|
|**클라이언트 ID**|앱을 AAD에 등록한 후 앱에 대해 생성된 고유한 GUID 식별자입니다.<br /><br />앱의 클라이언트 ID를 알 경우, 이 값을 지정합니다. 그렇지 않을 경우 기본값을 사용합니다.|6c7e8096-f593-4d72-807f-a5f86dcc9c77|
|**기관 URI**|AAD 개체(예: 사용자 및 그룹)에 대한 기관 식별자 URI(Uniform Resource Identifier)입니다.<br /><br />AuthorityURI 매개 변수는 앱 래핑 도구의 경우 선택 사항입니다. 매개 변수를 사용하지 않으면 기본 URI가 사용됩니다.||
|**SkipBroker**|회사 포털을 브로커로 사용할지 나타내는 값입니다.<br /><br />**True** – 회사 포털이 ADAL 인증에 사용되지 않습니다.<br /><br />**False** – 회사 포털이 ADAL 인증에 사용됩니다. 회사 포털은 등록된 사용자의 Single Sign-On을 위해 사용됩니다.||
|**비 브로커 리디렉션 URI**|ADAL이 브로커 앱(Intune 회사 포털)을 사용하지 않을 경우 사용되는 로그인 URI입니다.|urn:ietf:wg:oauth:2.0:oob|
|**리소스 ID**|앱의 AAD 리소스에 대한 포인터입니다.||

### 3단계 AAD의 모바일 앱 관리에 대한 액세스 구성
앱 래핑 도구에서 앱의 AAD 등록 값을 사용하려면 먼저 앱 개발자가 다음 단계에 따라 Intune 모바일 응용 프로그램 관리 리소스에 대한 액세스 권한을 해당 앱에 부여해야 합니다.

1.  Azure 관리 포털에서 기존 AAD 계정에 로그인합니다.

2.  **기존 LOB 응용 프로그램 등록**을 선택합니다.

3.  **구성** 섹션에서 **다른 응용 프로그램의 웹 API에 대한 액세스 구성**을 선택합니다.

4.  **다른 응용 프로그램에 대한 사용 권한** 드롭다운 목록에서 **Intune 모바일 응용 프로그램 관리**를 선택합니다.

이제 앱 래핑 도구에서 앱의 클라이언트 ID를 사용할 수 있습니다. 클라이언트 ID는 [2단계 앱을 등록할 때 받아야 하는 ID 검토](#step-2-review-the-identifiers-you-need-to-get-when-you-register-the-app)의 테이블에 설명된 대로 Azure Active Directory 관리 포털에서 찾을 수 있습니다.

### 4단계 앱 래핑 도구에서 AAD ID 값 사용
등록 과정에서 받은 식별자 값을 사용하여 앱 래핑 도구에 명령줄 속성으로 값을 입력합니다. 최종 사용자가 앱을 성공적으로 인증하려면 표의 모든 값을 지정해야 합니다. 값을 지정하지 않으면 기본값이 사용됩니다.

|식별자|매개 변수|
|--------------|-------------|
|클라이언트 ID|ClientID|
|기관 URI|기관 URI|
|SkipBroker|SkipBroker|
|비 브로커 리디렉션 URI|NonBrokerRedirectURI|
|리소스 ID|ResourceID|
앱을 래핑할 때 다음 사항에 유의하십시오.

-   인증이 성공했는지 확인하기 위해 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]에서 MAM 리소스 ID와 연결된 AAD 토큰을 가져옵니다. 그러나 이 토큰은 토큰의 유효성을 검사하는 어떤 호출에도 사용되지 않습니다. [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] 앱 액세스 확인을 위해 로그인한 사용자의 사용자 계정 이름(UPN)만 읽습니다. 다른 서비스 호출에서도 AAD 토큰은 사용되지 않습니다.

-   클라이언트 응용 프로그램의 클라이언트 ID 및 기관 URI를 입력하면 이중 로그인 시도가 차단됩니다. 클라이언트 ID로 AAD 대시보드에 게시된 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] MAM 리소스 ID에 액세스하려면 이 클라이언트 ID를 등록해야 합니다. 클라이언트 ID를 등록하지 않으면 사용자가 앱을 실행할 때 로그인에 실패합니다.


### 참고 항목
- [Microsoft Intune으로 모바일 응용 프로그램 관리용 앱을 준비하는 방법 결정](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md)

- [SDK를 사용하여 모바일 응용 프로그램 관리에 앱을 사용하도록 설정](use-the-sdk-to-enable-apps-for-mobile-application-management.md)



<!--HONumber=Jul16_HO4-->


