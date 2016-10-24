---
title: "앱 줄 바꿈 도구를 사용하여 iOS 앱 줄 바꿈 | Microsoft Intune"
description: "이 항목의 정보를 사용하여 앱 자체의 코드를 수정하지 않고 iOS 앱을 줄 바꿈하는 방법에 대해 알아봅니다. 모바일 앱 관리 정책을 적용할 수 있도록 앱을 준비합니다."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 09/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 99ab0369-5115-4dc8-83ea-db7239b0de97
ms.reviewer: oldang
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c67a5042fd177a4c5bd897092e84281db0977f5e
ms.openlocfilehash: 2c187b61b8fe25b2870d0cbc62f8352494583fc2


---

# Intune 앱 래핑 도구를 사용하여 모바일 응용 프로그램 관리를 위해 iOS 앱 준비
**iOS용 Microsoft Intune 앱 래핑 도구**를 사용하여 사내 iOS 앱의 동작을 수정하면 해당 앱 코드를 변경하지 않고도 앱 기능을 제한할 수 있습니다.

이 도구는 앱 주위에 '래퍼'를 만드는 Mac OS 명령줄 응용 프로그램입니다. 앱을 처리한 후에는 구성하는 Intune [모바일 응용 프로그램 관리 정책](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md)을 사용하여 앱의 기능을 변경할 수 있습니다.

이 도구를 다운로드하려면 [Microsoft Intune App Wrapping Tool for iOS](https://github.com/msintuneappsdk/intune-app-wrapping-tool-ios)(iOS용 Microsoft Intune 앱 래핑 도구)를 참조하세요.



## 1단계. 앱 래핑 도구의 필수 구성 요소 준비
필수 조건 및 설정 방법에 대한 자세한 내용은 [이 블로그 게시물](http://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)을 참조하세요.

|요구 사항|추가 정보|
|---------------|--------------------------------|
|지원되는 운영 체제 및 도구 집합|앱 래핑 도구는 Xcode 도구 집합 버전 5 이상이 설치된 OS X 10.8.5 이상의 MacOS 컴퓨터에서 실행해야 합니다.|
|인증서 및 프로비저닝 프로필 서명|Apple 서명 인증서 및 프로비저닝 프로필이 있어야 합니다. [Apple 개발자 설명서](https://developer.apple.com/)를 참조하세요.|
|앱 래핑 도구를 사용하여 앱 처리|사용자의 회사나 ISV(Independent Software Vendor)에서 개발 및 서명한 앱이어야 합니다. 이 도구를 사용하여 Apple 스토어의 앱을 처리할 수는 없습니다. iOS 8.0 이상용으로 작성된 앱이어야 합니다. 또한 PIE(Position Independent Executable) 형식의 앱이어야 합니다. PIE 형식에 대한 자세한 내용은 Apple 개발자 설명서를 참조하세요. 마지막으로, 앱의 확장명이 **.app**, 또는 **.ipa** 형식이어야 합니다.|
|래핑 도구에서 처리할 수 없는 앱|암호화된 앱, 서명되지 않은 앱 및 확장된 파일 특성을 가진 앱입니다.|
|앱에 대한 자격 설정|앱을 래핑하려면 먼저 일반적으로 부여되는 권한 및 기능 이외에 앱에 추가적인 사용 권한 및 기능을 제공하는 자격을 설정해야 합니다. 지침은 [앱 자격 설정](#setting-app-entitlements)을 참조하세요.|

## 2단계. 앱 래핑 도구 설치

1.  [GitHub](https://github.com/msintuneappsdk/intune-app-wrapping-tool-ios)에 호스트된 **Microsoft Intune App Wrapping Tool for iOS**(iOS용 Microsoft Intune 앱 래핑 도구) 리포지토리에서 앱 래핑 도구에 대한 파일을 Mac OS 컴퓨터에 다운로드합니다.

2.  설치 파일 **Microsoft Intune App Wrapping Tool for iOS.dmg**를 두 번 클릭합니다. EULA(최종 사용자 사용권 계약) 창이 나타납니다. 문서를 주의하여 읽습니다.

3. **동의**를 선택하여 EULA에 동의하면 패키지가 컴퓨터에 탑재됩니다.

4.  **IntuneMAMPackager** 패키지를 열고 MacOS 컴퓨터의 로컬 폴더에 파일을 저장합니다. 이제 앱 래핑 도구를 실행할 수 있습니다.

## 3단계. 앱 래핑 도구 실행
* MacOS 컴퓨터에서 터미널 창을 열고 앱 래핑 도구 파일을 저장한 폴더로 이동합니다. 실행 가능한 도구의 이름은 **IntuneMAMPackager**이고 **IntuneMAMPackager/Contents/MacOS**에 위치합니다. 다음과 같이 명령을 실행해야 합니다.

    ```
./IntuneMAMPackager/Contents/MacOS/IntuneMAMPackager -i /<path of input app>/<app filename> -o /<path to output folder>/<app filename> -p /<path to provisioning profile> -c <SHA1 hash of the certificate> [-b [<output app build string>]] [-v] [-e] [-x /<array of extension provisioning profile paths>]

    ```

    > [!NOTE]
    > 아래 표에 나와 있는 것처럼 일부 매개 변수는 선택 사항입니다.

    **예:** 다음 예제 명령은 **MyApp.ipa**앱에 대해 앱 래핑 도구를 실행합니다. 프로비저닝 프로필 및 SHA-1 해시가 지정됩니다. **MyApp_Wrapped.ipa**라는 이름의 처리된 앱이 만들어지고 사용자의 데스크톱 폴더에 저장됩니다.

    ```
    ./IntuneMAMPackager/Contents/MacOS/IntuneMAMPackager -i ~/Desktop/MyApp.ipa -o ~/Desktop/MyApp_Wrapped.ipa -p ~/Desktop/My_Provisioning_Profile_.mobileprovision -c 12A3BC45D67EF8901A2B3CDEF4ABC5D6E7890FAB  -v true
    ```
    앱 래핑 도구에는 다음 명령줄 속성을 사용할 수 있습니다.

    |속성|사용 방법|
  |------------|--------------------|
  |**-i**|`<Path of the input native iOS application file>`. 파일은 .app 또는 .ipa로 끝나야 합니다. |
  |**-o**|`<Path of the wrapped output application>` |
  |**-p**|`<Path of your provisioning profile for iOS apps>`|
  |**-c**|`<SHA1 hash of the signing certificate>`|
    |-h|앱 래핑 도구에 대해 사용 가능한 명령줄 속성에 대한 자세한 사용 정보를 표시합니다.|
  |-v|(유용한 선택 사항) 자세한 정보 메시지를 콘솔에 출력합니다.|
  |-e | (선택 사항) 이 플래그를 사용하여 앱 래핑 도구에서 앱을 처리할 때 누락된 자격을 제거하도록 합니다. 자세한 내용은 "앱 자격 설정" 단원을 참조하세요.|
  |-xe| (선택 사항) 앱의 iOS 확장 및 iOS 확장을 사용하기 위해 필요한 자격에 대한 정보를 인쇄합니다. 자세한 내용은 "앱 자격 설정" 단원을 참조하세요. |
  |-x| (선택 사항) `<An array of paths to extension provisioning profiles>`. 앱에서 확장 프로비저닝 프로필이 필요한 경우 사용합니다.|
  |-f |(선택 사항) `<Path to a plist file specifying arguments.>`plist 템플릿을 사용하여 -i, -o, -p 등 나머지 IntuneMAMPackager 속성을 지정하도록 선택하는 경우 [plist](https://developer.apple.com/library/mac/documentation/Cocoa/Conceptual/PropertyLists/Introduction/Introduction.html) 앞에 이 플래그를 사용합니다. 자세한 내용은 "plist를 사용하여 인수 입력" 단원을 참조하세요. |
  |-b|(선택 사항) 래핑된 출력 앱에서 입력 앱과 같은 번들 버전을 사용하려는 경우 인수 없이 -b를 사용합니다(권장하지 않음). <br/><br/> 래핑된 앱에서 사용자 지정 CFBundleVersion을 사용하도록 하려면 `-b <custom bundle version>`을 사용합니다. 사용자 지정 CFBundleVersion을 지정하도록 선택하는 경우 가장 덜 중요한 구성 요소 단위로 네이티브 앱의 CFBundleVersion을 증가하는 것이 좋습니다. 예: 1.0.0 -> 1.0.1 |


###plist를 사용하여 인수 입력
앱 래핑 도구를 실행하는 간단한 방법은 모든 명령 인수를 [plist](https://developer.apple.com/library/mac/documentation/Cocoa/Conceptual/PropertyLists/Introduction/Introduction.html) 파일에 두는 것입니다. Plist는 형식 인터페이스를 사용하여 명령줄 인수를 입력하기 위해 사용할 수 있는 XML과 비슷한 파일 형식입니다.

**IntuneMAMPackager/Contents/MacOS** 폴더에서 텍스트 편집기 또는 Xcode를 사용하여 빈 plist 템플릿인 `Parameters.plist`를 엽니다. 다음 키에 대한 인수를 입력합니다.

| Plist 키 |  기본값| 참고 |
|------------------|--------------|-----|
| 입력 응용 프로그램 패키지 경로  |비어 있음| -i와 동일합니다. |
| 출력 응용 프로그램 패키지 경로 |비어 있음| -o와 동일합니다.|
| 프로비저닝 프로필 경로 |비어 있음| -p와 동일합니다. |
| SHA-1 인증서 해시 |비어 있음| -c와 동일합니다. |
| 자세한 정보 사용 |false| -v와 동일합니다. |
| 누락된 자격 제거 | false| -c와 동일합니다.|
| 기본 빌드 방지 |false | 인수 없이 -b를 사용하는 것과 동일합니다. |
|문자열 재정의 빌드 | 비어 있음| 래핑된 출력 앱의 사용자 지정 CFBundleVersion |
|확장 프로비전 프로필 경로 | 비어 있음| 앱에 대한 확장 프로비전 프로필의 배열입니다.
  

마지막으로 유일한 인수로써 plist와 함께 IntuneMAMPackager를 실행합니다.

```
./IntuneMAMPackager –f Parameters.plist
```

* 처리가 완료되면 “**응용 프로그램이 래핑되었습니다.**” 메시지가 표시됩니다.

    오류가 발생한 경우 도움이 필요하면 [오류 메시지](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md#error-messages)를 참조하세요.

*   래핑된 앱은 이전에 지정한 출력 폴더에 저장됩니다. 이제 앱을 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]에 업로드하고 모바일 응용 프로그램 관리 정책에 연결할 수 있습니다.

    > [!IMPORTANT]
    > 래핑된 앱을 업로드할 때 이전(래핑된 또는 네이티브) 버전이 이미 Intune에 배포된 경우 이전 버전의 앱을 업데이트할 수 있습니다. 오류가 발생하면 앱을 새 앱으로 업로드하고 이전 버전을 삭제합니다.

    이제 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] 그룹에 앱을 배포할 수 있으며, 지정한 앱 제한을 사용하여 장치에서 앱이 실행됩니다.

## 오류 메시지 및 로그 파일
앱 래핑 도구 관련 문제를 해결하려면 다음 정보를 사용하세요.

### 오류 메시지
앱 래핑 도구가 정상적으로 완료되지 않으면 다음 오류 메시지 중 하나가 콘솔에 표시됩니다.

|오류 메시지|추가 정보|
|-----------------|--------------------|
|올바른 iOS 프로비저닝 프로필을 지정해야 합니다.|프로비저닝 프로필이 유효하지 않을 수 있습니다. 장치에 대한 올바른 권한이 있으며 프로필이 올바른 대상(개발 또는 배포)을 지정하는지 확인하세요. 프로비저닝 프로필이 만료되었을 수도 있습니다.|
|올바른 입력 응용 프로그램 이름을 지정하세요.|지정한 입력 응용 프로그램 이름이 올바른지 확인합니다.|
|출력 응용 프로그램의 올바른 경로를 지정하세요.|지정한 출력 응용 프로그램의 경로가 있으며 올바른지 확인합니다.|
|올바른 입력 프로비저닝 프로필을 지정하세요.|올바른 프로비저닝 프로필 이름 및 확장명을 입력했는지 확인합니다. 프로비저닝 프로필에서 권한 부여가 누락되었거나 **–p** 명령줄 옵션을 포함하지 않았을 수 있습니다.|
|지정한 입력 응용 프로그램을 찾을 수 없습니다. 올바른 입력 응용 프로그램 이름 및 경로를 지정하세요.|입력 앱 경로가 유효하며 있는지 확인합니다. 입력 앱이 해당 위치에 있는지 확인합니다.|
|지정한 입력 프로비저닝 프로필 파일을 찾을 수 없습니다. 올바른 입력 프로비저닝 프로필 파일을 지정하세요.|입력 프로비저닝 파일의 경로가 올바르며 지정한 파일이 있는지 확인합니다.|
|지정한 출력 응용 프로그램 폴더를 찾을 수 없습니다. 출력 응용 프로그램의 올바른 경로를 지정하세요.|지정한 출력 경로가 유효하며 있는지 확인합니다.|
|출력 앱의 확장명이 .ipa가 아닙니다.|앱 래핑 도구에서는 확장명이 **.app** 및 **.ipa** 인 앱만 사용할 수 있습니다. 출력 파일의 확장명이 올바른지 확인합니다.|
|잘못된 서명 인증서가 지정되어 있습니다. 올바른 Apple 서명 인증서를 지정하세요.|Apple 개발자 포털에서 올바른 서명 인증서를 다운로드했는지 확인합니다. 인증서가 만료되었거나 공개 키 또는 개인 키가 누락되었을 수 있습니다. Apple 인증서 및 프로비저닝 프로필을 사용하여 Xcode 내에서 앱에 올바르게 서명할 수 있으면 해당 인증서와 프로필을 앱 래핑 도구에서 사용할 수 있습니다.|
|지정한 입력 응용 프로그램이 잘못되었습니다. 올바른 응용 프로그램을 지정하세요.|.app 또는 .ipa 파일로 컴파일된 올바른 iOS 응용 프로그램이 있는지 확인합니다.|
|지정한 입력 응용 프로그램이 암호화되어 있습니다. 암호화되지 않은 올바른 응용 프로그램을 지정하세요.|앱 래핑 도구에서는 암호화된 앱을 지원하지 않으므로 암호화되지 않은 앱을 제공합니다.|
|지정한 입력 응용 프로그램이 PIE(Position Independent Executable) 형식이 아닙니다. PIE 형식의 올바른 응용 프로그램을 지정하세요.|PIE(Position Independent Executable) 앱은 실행 시 임의 메모리 주소에서 로드할 수 있으므로 보안상 유리합니다. 자세한 내용은 Apple 개발자 설명서를 참조하세요.|
|지정한 입력 앱은 이미 래핑되었습니다. 래핑되지 않은 올바른 응용 프로그램을 지정하세요.|도구에서 이미 처리된 앱은 처리할 수 없습니다. 앱을 다시 처리하려면 원래 앱 버전을 사용하여 도구를 다시 실행합니다.|
|지정한 입력 응용 프로그램이 서명되지 않았습니다. 서명된 올바른 응용 프로그램을 지정하세요.|앱 래핑 도구에서 처리할 앱은 서명되어져야 합니다. 래핑된 앱에 서명을 하는 방법은 개발자 설명서를 참조하세요.|
|지정한 입력 응용 프로그램은 .ipa 또는 .app 형식이어야 합니다.|확장명이 .ipa인 앱만 앱 래핑 도구에서 처리할 수 있습니다. 입력 파일의 확장명이 올바르고 .app 또는 .ipa 파일로 컴파일되었는지 확인합니다.|
|지정한 입력 앱은 이미 래핑되었으며 최신 정책 템플릿 버전을 사용합니다.|앱 래핑 도구는 기존에 래핑된 앱을 최신 정책 템플릿 버전을 사용하여 다시 래핑하지 않습니다.|
|경고: SHA1 인증서 해시를 지정하지 않았습니다. 배포 전에 래핑된 응용 프로그램이 서명되어 있는지 확인하세요.|**–c** 명령줄 플래그 다음에 유효한 SHA1 해시를 지정했는지 확인합니다. |

### 앱 래핑 도구의 로그 파일
앱 래핑 도구를 사용하여 앱을 래핑하면 iOS 클라이언트 장치 콘솔에 작성되는 로그가 생성됩니다. 응용 프로그램에서 문제가 발생하여 앱 래핑 도구 관련 문제인지를 진단해야 하는 경우 이 정보가 유용합니다. 이 정보를 검색하려면 다음 단계를 수행합니다.

1.  앱을 실행하여 문제를 재현합니다.

2.  [배포된 iOS 앱 디버깅](https://developer.apple.com/library/ios/qa/qa1747/_index.html)과 관련한 Apple의 지침에 따라 콘솔 출력을 수집합니다.

3.  콘솔에 다음 스크립트를 입력하여 앱 제한 출력에 대해 저장된 로그를 필터링합니다.

    ```
    grep “IntuneAppRestrictions” <text file containing console output> > <required filtered log file name>
    ```
    필터링된 로그를 Microsoft에 제출할 수 있습니다.

    > [!NOTE]
    > 로그 파일에서 항목 '빌드 버전'은 Xcode의 빌드 버전을 나타냅니다.

    래핑된 앱은 앱 작동이 중단된 후 전자 메일을 통해 장치에서 로그를 직접 보내는 옵션도 제공합니다. 사용자는 개발자가 점검하여 필요한 경우 Microsoft로 전달할 수 있는 로그를 보낼 수 있습니다.


### 인증서, 프로비저닝 프로필 및 인증 요구 사항

앱 래핑 도구에는 전체 기능을 보장하기 위해 충족해야 하는 몇 가지 요구 사항이 있습니다.

|요구 사항|세부 정보|
|---------------|-----------|
|프로비저닝 프로필|**프로비저닝 프로필을 포함하기 전에 프로필이 올바른지 확인합니다**. 앱 래핑 도구에서는 iOS 앱을 처리할 때 프로비저닝 프로필이 만료되었는지 확인하지 않습니다. 만료된 프로비저닝 프로필을 지정하면 앱 래핑 도구는 만료된 프로비저닝 프로필을 그대로 포함하며, iOS 장치에서 앱 설치가 실패할 때까지 문제가 있음을 알 수 없습니다.|
|인증서|**인증서를 지정하기 전에 인증서가 유효한지 확인합니다**. 도구에서는 iOS 앱을 처리할 때 인증서가 만료되었는지 확인하지 않습니다. 따라서 만료된 인증서의 해시를 제공하면 도구에서 앱을 처리하고 서명을 하기는 하지만 장치에 앱을 설치하지는 못합니다.<br /><br />**패키지 응용 프로그램에 서명하기 위해 제공된 인증서가 프로비저닝 프로필에 일치하는 항목이 있는지 확인합니다**. 도구에서는 래핑된 응용 프로그램에 서명하기 위해 제공된 인증서에 대해 프로비저닝 프로필에 일치하는 항목이 있는지 확인하지 않습니다.|
|인증|암호화가 작동하려면 장치에 PIN이 있어야 합니다. 사용자는 래핑된 앱을 배포한 장치의 상태 표시줄을 터치할 때 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]에 다시 인증해야 합니다. 래핑된 앱의 기본 정책은 *다시 시작할 때 인증*입니다. iOS에서 앱을 종료했다가 다시 시작하여 외부 알림(예: 전화 통화)을 처리합니다.


## 앱 자격 설정
앱을 래핑하기 전에 **자격**을 부여하여 앱이 일반적으로 수행할 수 있는 작업을 초과하는 추가적인 권한 및 기능을 제공할 수 있습니다.  **자격 파일**은 앱 내에서 특정 권한(예: 공유 키 집합에 대한 액세스 권한)을 지정하는 코드 서명 동안 사용됩니다. **기능**이라는 특정 앱 서비스는 앱 개발 동안 Xcode 내에서 설정됩니다. 이렇게 사용하도록 설정되면 기능이 자격 파일에 반영됩니다. 자격 및 기능에 대한 자세한 내용은 iOS 개발자 라이브러리의 [기능 추가](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html)를 참조하세요. 지원되는 전체 기능 목록이 필요하면 [지원되는 기능](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/SupportedCapabilities/SupportedCapabilities.html)을 참조하세요.

### IOS용 앱 래핑 도구에 지원되는 기능

|기능|설명|권장 지침|
|--------------|---------------|------------------------|
|앱 그룹|앱 그룹을 사용하여 여러 앱에서 공유 컨테이너에 액세스하도록 허용하고 앱들 간의 추가적인 프로세스 간 통신을 허용합니다.<br /><br />앱 그룹을 설정하려면 **기능** 창을 열고, **앱 그룹** 섹션에서 **ON** 스위치를 클릭합니다. 앱 그룹을 추가하거나 기존 앱 그룹을 선택할 수 있습니다.|앱 그룹을 사용할 때에는 역방향 DNS 표기법을 사용합니다.<br /><br />*group.com.companyName.AppGroup*|
|Background Modes(백그라운드 모드)|백그라운드 모드를 사용하면 iOS이 백그라운드에서 계속 실행될 수 있습니다.||
|데이터 보호|데이터 보호 기능을 사용하면 iOS 앱에 의해 디스크에 저장된 파일에 보안 수준이 추가됩니다. 데이터 보호 기능에서는 특정 장치에 있는 기본 제공 암호화 하드웨어를 사용하여 디스크에서 파일을 암호화된 형식으로 저장합니다. 데이터 보호를 사용하도록 앱을 프로비저닝해야 합니다.||
|앱에서 바로 구매|앱에서 바로 구매 기능에서는 스토어에 연결하여 사용자의 지불을 안전하게 처리할 수 있도록 하여 스토어를 앱에 바로 포함합니다. 앱에서 바로 구매 기능을 사용하여 향상된 기능이나 앱에서 사용할 수 있는 추가적인 콘텐츠에 대한 지불을 회수할 수 있습니다.||
|키 집합 공유|키 집합 공유 기능을 사용하면 자신의 앱이 팀에서 개발한 다른 앱과 키 집합에 있는 암호를 공유할 수 있습니다.|키 집합 공유 기능을 사용할 때에는 역방향 DNS 표기법을 사용합니다.<br /><br />*com.companyName.KeychainGroup*|
|Personal VPN(개인 VPN)|앱이 네트워크 확장 프레임워크를 사용하여 사용자 지정 시스템 VPN 구성을 만들고 제어할 수 있도록 하려면 개인 VPN을 사용합니다.||
|푸시 알림|APNs(Apple 푸시 알림 서비스)를 사용하면 포그라운드에서 실행되지 않고 있는 앱이 사용자에 대한 정보를 보유하고 있다고 사용자에게 알릴 수 있습니다.|푸시 알림이 작동하도록 하려면 앱별 프로비저닝 프로필을 사용해야 합니다.<br /><br />[Apple 개발자 설명서](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html)의 절차를 따릅니다.|
|Wireless Accessory Configuration(무선 액세서리 구성)|무선 액세서리 구성 기능을 사용하면 프로젝트에 외부 액세서리 프레임워크가 추가되고 앱이 MFi Wi-Fi 액세서리를 구성할 수 있게 됩니다.||

### 자격을 사용하도록 설정하는 절차

1.  앱에서 기능을 사용하도록 설정합니다.

    1.  Xcode에서 앱의 대상으로 이동하고 **기능** 창을 클릭합니다.

    2.  적절한 기능을 켭니다. 각 기능 및 올바른 값을 결정하는 방법에 대한 자세한 내용은 iOS 개발자 라이브러리의 [기능 추가](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html)를 참조하세요.

    3.  프로세스 중에 만든 ID를 확인합니다.

    4.  래핑할 앱을 빌드하고 서명합니다.

2.  프로비저닝 프로필에서 자격을 사용하도록 설정합니다.

    1.  Apple Developer Member Center에 로그인합니다.

    2.  앱용 프로비저닝 프로필을 만듭니다. 자세한 지침은 [iOS용 Intune 앱 줄 바꿈 도구에 대한 필수 구성 요소를 가져오는 방법](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios/)을 참조하세요.

    3.  프로비저닝 프로필에서 앱에 있는 것과 동일한 자격을 설정합니다. 앱을 개발하는 동안 지정한 것과 동일한 ID를 제공해야 합니다.

    4.  프로비저닝 프로필 마법사를 완료하고 파일을 다운로드합니다.

3.  모든 필수 구성 요소가 충족되었는지 확인한 다음 앱을 래핑합니다.

### 자격과 관련한 일반적인 오류 문제 해결
iOS용 앱 래핑 도구에 자격 오류가 표시되는 경우 다음의 문제 해결 절차를 수행해 보세요.

|문제|원인|해결 방법|
|---------|---------|--------------|
|입력 응용 프로그램에서 생성된 자격을 구문 분석하지 못했습니다.|앱 래핑 도구가 앱에서 추출된 자격 파일을 읽을 수 없습니다. 자격 파일의 형식이 잘못되었을 수 있습니다.|앱용 자격 파일을 검사합니다. 이를 수행하려면 아래 설명된 지침을 따르세요. 자격 파일을 검사할 때에는 잘못된 구문이 있는지 확인합니다. 파일이 XML 형식으로 되어있어야 합니다.|
|프로비저닝 프로필에 자격이 누락되었습니다(누락된 자격이 나열됨). 이러한 자격이 있는 프로비저닝 프로필로 앱을 다시 패키징합니다.|프로비저닝 프로필에서 사용할 수 있는 자격과 앱에서 사용할 수 있는 기능 간에 일치하지 않는 사항이 있습니다. 이 불일치는 특정 기능(즉, 앱 그룹, 키 집합 액세스 등)과 연결된 ID에도 적용됩니다.|일반적으로 앱과 동일한 기능을 사용하는 새 프로비저닝 프로필을 만들 수 있습니다. 프로필과 앱 간 ID가 일치하지 않으면 가능할 경우 앱 래핑 도구가 ID 대체하게 됩니다. 새 프로비저닝 프로필을 만든 후에도 이 오류가 여전히 발생하면 **-e** 매개 변수를 사용하여 앱에서 자격의 제거를 시도할 수 있습니다(아래 섹션 "-e 매개 변수를 사용하여 앱에서 자격 제거" 참조).|

### 서명된 앱의 기존 자격 찾기
서명된 앱 및 프로비저닝 프로필의 기존 자격을 확인하려면

1.  .ipa 파일을 찾고 확장명을 .zip으로 변경합니다.

2.  .zip 파일을 확장합니다. .app 번들에 포함된 페이로드 폴더가 생성됩니다.

3.  코드 서명 도구를 사용하여 다음과 같이 .app 번들에 대한 자격을 확인합니다.

    ```
    $ codesign -d --entitlements :- "Payload/YourApp.app"
    ```
    여기서 `YourApp.app`는 .app 번들의 실제 이름입니다.

4.  보안 도구를 사용하여 앱의 포함된 프로비저닝 프로필 자격을 확인합니다.

    ```
    $ security -D -i "Payload/YourApp.app/embedded.mobileprovision"
    ```
    여기서 `YourApp.app`는 .app 번들의 실제 이름입니다.

### –e 매개 변수를 사용하여 앱에서 자격 제거
이 명령은 자격 파일에 없는 앱에서 사용할 수 있는 기능을 모두 제거합니다. 앱에서 사용 중인 기능을 제거하면 앱이 중단될 수 있습니다. 누락된 기능을 제거할 수 있는 위치의 예로 기본적으로 모든 기능을 갖춘 공급업체에서 만든 앱이 있는 경우입니다.

```
./IntuneMAMPackager/Contents/MacOS/IntuneMAMPackager –i /<path of input app>/<app filename> -o /<path to output folder>/<app filename> –p /<path to provisioning profile> –c <SHA1 hash of the certificate> -e
```

## 앱 래핑 도구의 보안 및 개인 정보
앱 래핑 도구를 사용할 때는 다음의 보안 및 개인 정보 관련 모범 사례를 사용합니다.

-   지정하는 서명 인증서, 프로비저닝 프로필, LOB(기간 업무) 앱은 앱 래핑 도구를 실행하는 데 사용하는 것과 같은 MacOS 컴퓨터에 있어야 합니다. 파일이 UNC 경로에 있으면 MacOS 컴퓨터에서 해당 파일에 액세스할 수 있는지 확인합니다. IPsec 또는 SMB 서명을 통해 경로를 보호해야 합니다.

    [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] 콘솔로 가져온 래핑된 응용 프로그램은 도구를 실행하는 동일한 컴퓨터에 있어야 합니다. 파일이 UNC 경로에 있으면 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] 콘솔을 실행하는 컴퓨터에서 해당 파일에 액세스할 수 있는지 확인합니다. IPsec 또는 SMB 서명을 통해 경로를 보호해야 합니다.

-   GitHub 리포지토리에서 앱 래핑 도구를 다운로드하는 환경은 IPsec 또는 SMB 서명을 통해 보호해야 합니다.

-   공격을 차단하려면 신뢰할 수 있는 출처의 앱만 처리해야 합니다.

-   앱 래핑 도구에 지정된 출력 폴더(특히 원격 폴더)를 보호해야 합니다.

-   파일 업로드 대화 상자를 포함하는 iOS 앱에서는 사용자가 앱에 적용된 잘라내기, 복사, 붙여넣기 제한을 우회할 수 있습니다. 예를 들어 사용자가 파일 업로드 대화 상자를 사용하여 앱 데이터의 스크린샷을 업로드할 수 있습니다.

-   사용자가 래핑된 앱 내에서 장치의 문서 폴더를 모니터링할 때는 **.msftintuneapplauncher**라는 폴더가 표시될 수 있습니다. 이 폴더를 변경하거나 삭제하면 제한된 앱이 정상적으로 작동하지 않을 수 있습니다.

### 참고 항목
- [Microsoft Intune으로 모바일 응용 프로그램 관리용 앱을 준비하는 방법 결정](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md)</br>
- [Microsoft Intune 정책을 사용하여 장치의 설정 및 기능 관리](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)</br>
- [SDK를 사용하여 모바일 응용 프로그램 관리에 앱을 사용하도록 설정](use-the-sdk-to-enable-apps-for-mobile-application-management.md)



<!--HONumber=Oct16_HO2-->


