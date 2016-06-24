---
# required metadata

title: iOS용 Microsoft Intune 앱 SDK 개발자 가이드 | Microsoft Intune
description:
keywords:
author: Msmbaldwin
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8e280d23-2a25-4a84-9bcb-210b30c63c0b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# iOS용 Microsoft Intune 앱 SDK 개발자 가이드

> [!NOTE] 먼저 지원되는 각 플랫폼에서 통합을 준비하는 방법을 설명하는 [Intune 앱 SDK 시작 가이드](intune-app-sdk-get-started.md)를 읽어보는 것이 좋습니다.* 

iOS용 Microsoft Intune 앱 SDK를 사용하면 iOS 앱에 Intune MAM(모바일 앱 관리)을 통합할 수 있습니다. MAM 사용이 가능한 응용 프로그램은 Intune 앱 SDK와 통합된 응용 프로그램으로, IT 관리자가 앱을 적극적으로 관리할 때 모바일 앱에 정책을 배포할 수 있게 해줍니다.

# SDK에 포함된 내용

iOS용 Intune 앱 SDK에는 정적 라이브러리, 리소스 파일, API 헤더, 디버그 설정 plist 및 구성기 도구가 포함되어 있습니다. 모바일 앱은 단순히 리소스 파일을 포함하고 대부분 정책 적용을 위해 라이브러리에 정적으로 연결할 수 있습니다. 고급 Intune MAM 기능은 API를 통해 적용됩니다.
이 가이드에서는 iOS용 Intune 앱 SDK를 통합할 때 다음을 사용하는 방법을 설명합니다.

* **`libIntuneMAM.a`**: Intune 앱 SDK 라이브러리입니다. 모바일 앱을 MAM 사용이 가능하도록 만들려면 이 라이브러리를 프로젝트에 연결합니다. 지침은 이 문서의 "Intune 앱 SDK를 사용하여 앱 빌드" 섹션에 있습니다.

* **`IntuneMAMResources.Bundle`**: SDK에서 사용하는 리소스를 포함하는 리소스 번들입니다. 

* **헤더**: Intune 앱 SDK API를 표시합니다. API를 사용하는 경우 API가 포함된 헤더 파일을 포함해야 합니다. 

# Intune 앱 SDK의 작동 방식

iOS용 Intune 앱 SDK의 목적은 최소한의 코드 변경으로 iOS 응용 프로그램에 관리 기능을 추가하는 것입니다. 코드 변경량을 줄이면 모바일 응용 프로그램의 일관성 및 안정성이 증가하는 동시에 시장 출시 시간이 단축됩니다. 

응용 프로그램이 정적 라이브러리에 연결되고 리소스 번들을 포함해야 합니다. MAMDebugSettings.plist 파일은 선택 사항이며, Microsoft Intune을 통해 응용 프로그램을 배포하지 않고도 응용 프로그램에 적용되는 MAM 정책을 시뮬레이트하기 위해 패키지에 포함될 수 있습니다. 또한 디버그 빌드에서는 iTunes 파일 공유를 통해 응용 프로그램의 문서 디렉터리에 MAMDebugSettings.plist 파일을 전송하여 MAMDebugSettings.plist 파일의 정책을 적용할 수 있습니다.

# Intune 앱 SDK를 사용하여 앱 빌드 

Intune 앱 SDK를 사용하도록 설정하려면 아래 단계를 완료합니다.

1. 다음을 수행하여 `libIntuneMAM.a` 라이브러리에 연결합니다.

    프로젝트 대상의 "연결된 프레임워크 및 라이브러리" 목록에 libIntuneMAM.a 라이브러리를 끌어 놓습니다.  

    ![Intune 앱 SDK iOS - 연결된 프레임워크 및 라이브러리](../media/intune-app-sdk-ios-linked-frameworks-and-libraries.png)
 
    **참고**: 앱 스토어에 릴리스하는 경우 디버그 버전이 아니라 릴리스용으로 빌드된 libIntuneMAM.a 버전을 사용하세요. 릴리스 버전은 "릴리스" 폴더에 포함됩니다. 디버그 버전에는 Intune 앱 SDK를 사용하여 문제를 디버그하는 데 유용한 자세한 정보 출력이 있습니다.

2. 프로젝트에 다음 iOS 프레임워크를 추가합니다(없는 경우).
    * `MessageUI.framework`
    * `Security.framework`
    * `MobileCoreServices.framework`
    * `SystemConfiguration.framework`
    * `libsqlite3.dylib`
    * `libc++.dylib`
    * `ImageIO.framework`
    * `LocalAuthentication.Framework`
    * `AudioToolbox.framework`<br>

    **참고**: 응용 프로그램이 iOS7을 대상으로 하는 경우 `LocalAuthentication.Framework` 의 'Status' 특성을 "Optional"로 설정합니다. 

    'Status'를 설정하지 않으면 iOS7에서 응용 프로그램이 시작되지 않습니다.

    **참고**: Xcode 7에서는 `.dylib` 확장이 `.tbd`.

3. "빌드 단계" 내의 "번들 리소스 복사" 아래로 리소스 번들을 끌어 프로젝트에 `IntuneMAMResources.bundle` 리소스 번들을 추가합니다. 

    ![Intune 앱 SDK iOS - 번들 리소스 복사](../media/intune-app-sdk-ios-copy-bundle-resources.png)

4. 프로젝트의 OTHER_LDFLAGS 빌드 구성 설정이나 UI의 "기타 링커 플래그"에 `-force_load {PATH_TO_LIB}/libIntuneMAM.a` 를 Intune 앱 SDK 위치로 대체하여 `{PATH_TO_LIB}` 를 다음 중 하나에 추가합니다.
    * 프로젝트의 OTHER_LDFLAGS 빌드 구성 설정 
    * UI의 "기타 링커 플래그"<br>

    **참고**: `PATH_TO_LIB`를 찾으려면 `libIntuneMAM.a` 파일을 선택하고 '파일' 메뉴에서 '정보 가져오기'를 선택합니다. '정보' 창의 '일반' 섹션에서 '위치' 정보(경로)를 복사하여 붙여넣습니다.

5. 모바일 앱이 해당 `info.plist`에서 주 Nib 또는 스토리보드를 정의하는 경우 주 스토리보드 또는 주 Nib 파일 필드를 제거합니다. `IntuneMAMSettings`라는 새 사전에 이전에 제거한 스토리보드 또는 Nib 값을 다음과 같은 키 이름으로 추가합니다(해당하는 경우).
    * `MainStoryboardFile`
    * `MainStoryboardFile~ipad`
    * `MainNibFile`
    * `MainNibFile~ipad `
    
    모바일 앱이 해당 `info.plist`에서 주 Nib 또는 스토리보드를 정의하지 않는 경우에는 이러한 설정이 **필요하지 않습니다**. 

    **참고**: 문서 본문의 아무 곳이나 마우스 오른쪽 단추로 클릭하고 보기 형식을 "원시 키/값 표시"로 변경하여 `info.plist` 를 원시 형식으로 표시할 수도 있습니다(키 이름을 확인하기 위해).

6. 각 프로젝트 대상에서 '기능'을 클릭하고 키 집합 공유 스위치를 사용하도록 설정하여 키 집합 공유를 사용하도록 설정합니다(아직 설정되지 않은 경우). 다음 단계를 진행하려면 키 집합 공유가 필요합니다.

    **참고**: 프로비저닝 프로필이 새로운 키 집합 공유 값을 지원해야 합니다. 키 집합 액세스 그룹이 와일드카드 문자를 지원해야 합니다. 이를 확인하려면 텍스트 편집기에서 `.mobileprovision` 파일을 열고 'keychain-access-groups'를 검색한 다음 와일드카드가 있는지 확인합니다. 예를 들면 다음과 같습니다. 

       <key>keychain-access-groups</key>
       <array>
       <string>YOURBUNDLESEEDID.*</string>
       </array>

7. 키 집합 공유를 사용하도록 설정한 후 다음 단계에 따라 Intune 앱 SDK 데이터를 저장할 별도의 액세스 그룹을 만듭니다. UI를 사용하거나 자격 파일을 사용하여 키 집합 액세스 그룹을 만들 수 있습니다.

    UI를 사용하여 키 집합 액세스 그룹 만들기: 
    
    * 모바일 앱에 키 집합 액세스 그룹이 정의되어 있지 않으면 앱의 번들 ID를 첫 번째 그룹으로 추가합니다.
    * 공유 키 집합 그룹 com.microsoft.intune.mam을 추가합니다. 이 액세스 그룹은 Intune 앱 SDK에서 데이터를 저장하는 데 사용됩니다.  
    * "빌드 단계" 내의 "번들 리소스 복사" 아래로 리소스 번들을 끌어 프로젝트에 `com.microsoft.adalcache` 를 추가합니다. 
 
    ![Intune 앱 SDK iOS - 키 집합 공유](../media/intune-app-sdk-ios-keychain-sharing.png)

    일반 UI보다 자격 파일을 사용하여 키 집합 액세스 그룹을 만드는 경우 자격 파일에서 키 집합 액세스 그룹 앞에 `$(AppIdentifierPrefix)` 를 추가해야 합니다. 예를 들면 `$(AppIdentifierPrefix)com.microsoft.intune.mam` 및 `$(AppIdentifierPrefix)com.microsoft.adalcache`.

    **참고**: 자격 파일은 iOS 앱 내에서 특별한 사용 권한 및 기능을 지정하는 데 사용되는 해당 모바일 응용 프로그램에 고유한 XML 파일입니다.

8. iOS 9+용으로 개발되는 모바일 앱의 경우 모바일 앱이 `UIApplication canOpenURL` 에 전달하는 각 프로토콜을 모바일 앱 `LSApplicationQueriesSchemes` 파일의 `info.plist` 배열에 포함해야 합니다. 또한 나열된 각 프로토콜에 대해 새 프로토콜을 추가하고 앞에 `-intunemam`. 또한 `http-intunemam`, `https-intunemam`및 `ms-outlook-intunemam` 을 배열에 포함해야 합니다. 

9. 앱이 해당 `info.plist file`에서 URL 체계를 정의하는 경우 `-intunemam` 접미사를 사용하여 각 URL 체계에 대해 다른 체계를 추가합니다.

10. 앱의 자격에 앱 그룹이 정의되어 있으면 해당 그룹을 `IntuneMAMSettings` 키 아래의 `AppGroupIdentitifiers` 사전에 문자열 배열로 추가합니다.

11. ADAL 라이브러리에 모바일 응용 프로그램을 연결합니다. Objective C용 ADAL 라이브러리는 [Github에서 사용할 수 있습니다](https://github.com/AzureAD/azure-activedirectory-library-for-objc).

    **참고**: Intune 앱 SDK는 2015년 6월 19일의 ADAL 브로커 분기 코드에 대해 테스트되었습니다. ADAL 라이브러리의 최신/작업 버전에 연결하고 있는지 확인하세요.

12. "빌드 단계" 내의 "번들 리소스 복사" 아래로 리소스 번들을 끌어 프로젝트에 `ADALiOSBundle.bundle resource` 리소스 번들을 포함합니다.

13. 라이브러리에 연결하는 경우 `-force_load PATH_TO_ADAL_LIBRARY` 링커 옵션을 사용합니다.

    프로젝트의 OTHER_LDFLAGS 빌드 구성 설정이나 UI의 "기타 링커 플래그"에 `-force_load {PATH_TO_LIB}/libADALiOS.a` 를 추가합니다. “PATH_TO_LIB”를 ADAL 이진 파일 위치로 대체해야 합니다. 

모바일 응용 프로그램이 해당 인증에 ADAL를 사용하는 경우 이 문서의 "Azure Directory 인증 라이브러리 설정 구성" 섹션을 검토하세요.

## 원격 분석 

iOS용 Intune 앱 SDK는 기본적으로 Microsoft Intune에 전송된 사용 이벤트에 대한 원격 분석 데이터를 기록합니다.

다음과 같은 사용 이벤트에 대한 데이터가 기록됩니다. 

1. 앱 시작 - Microsoft Intune이 관리 유형별로 MAM 사용이 가능한 앱 사용을 확인하는 데 도움이 됩니다.

2. EnrollApplication API 호출 - Microsoft Intune이 클라이언트 쪽에서 enrollApplication 호출의 성공률 및 다른 다양한 성능 메트릭을 확인하는 데 도움이 됩니다.

**참고**: 모바일 응용 프로그램에서 Microsoft Intune에 Intune 앱 SDK 원격 분석 데이터를 보내지 않도록 선택하는 경우 **IntuneMAMSettings** 에서 `MAMTelemetryDisabled` 속성을 'YES'로 설정하여 Intune 앱 SDK 원격 분석 캡처를 `IntuneMAMSettings`.

## ADAL(Azure Directory 인증 라이브러리) 설정 구성(옵션)

Intune 앱 SDK는 해당 인증 및 조건부 시작 시나리오에 ADAL을 사용합니다. 일반적으로 ADAL에서는 앱이 `ClientID`라는 고유 ID 및 앱에 부여된 토큰의 보안을 보장하기 위한 기타 식별자를 등록하고 얻어야 합니다. Intune 앱 SDK는 Azure Active Directory에 연결할 때 기본 등록 값을 사용합니다.  앱 자체에서 해당 인증 시나리오에 ADAL을 사용하는 경우 앱은 기존 등록 값을 사용하고 Intune 앱 SDK 기본값을 재정의하여 최종 사용자에게 인증 확인 메시지가 두 번(Intune 앱 SDK에 의해 한 번, 앱에 의해 한 번) 표시되지 않도록 해야 합니다. 

아래 단계는 앱 자체에서 인증에 ADAL을 사용하는 경우에 필요합니다. 모바일 앱이 ADAL를 사용하지 않는 경우에는 추가 작업이 필요하지 않습니다. 

1. 프로젝트 `Info.plist`의 `IntuneMAMSettings` 사전 아래에서 ADAL 호출에 사용할 `ADALClientId`를 키 이름 `ClientID` 로 지정합니다. 

2. 프로젝트 `Info.plist`의 `IntuneMAMSettings` 사전 아래에서 ADAL 호출에 사용할 `ADALRedirectUri`로 지정합니다. 앱의 리디렉션 URI 형식에 따라 `ADALRedirectScheme` 을 지정해야 할 수도 있습니다.

## 사용자 확장 빌드(옵션) 

확장을 빌드하는 경우 이 문서의 "Intune 앱 SDK를 사용하여 앱 빌드" 섹션에 설명된 것과 동일한 지침에 따라 모바일 앱을 빌드합니다. 또한 각 확장의 info.plist 파일을 업데이트하여 IntuneMAMSettings 사전에 ContainingAppBundleId 키를 포함 응용 프로그램의 번들 ID 값으로 추가합니다.

## 사용자 프레임워크 빌드(옵션)

Intune 앱 SDK의 최신 변경 내용에서는 모바일 앱에 포함된 응용 프로그램 프레임워크가 있는 경우 특정 링커 플래그를 사용하여 모바일 앱을 컴파일할 필요가 없습니다. 

## 시작 시 이미지 파일(옵션)

MAM 사용이 가능한 앱이 Microsoft Intune에서 적극적으로 관리되는 경우 Intune 앱 SDK는 앱 시작 시 시작 화면을 표시하여 앱이 관리되고 있음을 사용자에게 나타냅니다. 필요에 따라 "회사에서 관리" 시작 페이지에 표시할 이미지 파일을 추가할 수도 있습니다. 이미지에 대한 다음 지침을 따르세요.

* 앱 info.plist의 `IntuneMAMSettings` 사전에 키 이름 `SplashIconFile` 및 `SplashIconFile~ipad`. 

* 이미지 크기 및 요구 사항:

    * iPhone 6s Plus 및 iPhone 6 Plus의 경우 180x180, 다른 iPhone 모델의 경우 120x120, iPad의 경우 152x152. 
    
    * 파일 이름에서 `.png` 확장명을 제거합니다. 
    
    * 라이브러리에 연결하는 경우 `@2x` 접미사를 사용하고, 3x 배율 버전에는 `@3x` 접미사를 사용합니다. 이미지가 올바른 크기가 아니면 크기가 적절하게 조정됩니다. SplashIconFile 값이 지정되지 않은 경우 Intune 앱 SDK는 앱의 아이콘 중 하나를 선택합니다(모든 iPhone의 경우 60x60, iPad의 경우 76x76).

**참고**: 이 화면은 시작 시 트리거되지만 사용자가 영구적으로 해제할 수 있습니다.

# Intune 앱 SDK 설정 구성

응용 프로그램의 `IntuneMAMSettings` 에 포함된 `info.plist` 사전을 사용하여 Intune 앱 SDK를 구성합니다. 다음은 지원되는 모든 설정 목록입니다. 

이러한 설정 중 일부는 이전 섹션에서 설명되었을 수도 있으며 일부 응용 프로그램에 적용되지 않는 설정도 있습니다. 

설정  | 유형  | 정의 | 필수 여부
--|--|--|--
ADALClientId  | 문자열  | 응용 프로그램의 AAD 클라이언트 식별자입니다. | 응용 프로그램이 ADAL을 사용한 경우에 필요합니다.
ADALRedirectUri  | 문자열  | 응용 프로그램의 AAD 리디렉션 URI입니다. | 응용 프로그램이 ADAL을 사용한 경우에 필요합니다. 
AppGroupIdentifier | 문자열 배열  | 앱 자격 com.apple.security.application-groups 섹션의 앱 그룹 배열입니다. | 앱이 응용 프로그램 그룹을 사용하는 경우에 필요합니다.
ContainingAppBundleId  | 문자열 | 확장의 포함 응용 프로그램 번들 ID를 지정합니다. | iOS 확장에 필요합니다.
MainNibFile<br>MainNibFile~ipad  | 문자열  | 이 설정은 응용 프로그램의 주 nib 파일 이름을 포함해야 합니다.  | 응용 프로그램이 해당 info.plist에서 MainNibFile을 정의하는 경우에 필요합니다.
MainStoryboardFile<br>MainStoryboardFile~ipad  | 문자열  | 이 설정은 응용 프로그램의 주 스토리보드 파일 이름을 포함해야 합니다. | 응용 프로그램이 해당 info.plist에서 UIMainStoryboardFile을 정의하는 경우에 필요합니다.
SplashIconFile <br>SplashIconFile~ipad  | 문자열  | Intune 시작 아이콘 파일을 지정합니다. 자세한 내용은 이 문서의 "시작 시 이미지 파일" 섹션을 참조하세요. | 선택 사항입니다.
SplashDuration | 숫자 | 응용 프로그램 시작 시 Intune 시작 화면이 표시되는 최소 시간(초)입니다. 기본값은 1.5입니다. | 선택 사항입니다.
ADALLogOverrideDisabled | 부울  | SDK에서 모든 ADAL 로그(있는 경우 앱에서의 ADAL 호출 포함)를 해당 로그 파일로 라우팅할지 여부를 지정합니다. 기본값은 NO입니다. 앱이 해당 ADAL 로그 콜백을 설정하려는 경우 YES로 설정합니다. | 선택 사항입니다.

# Intune 앱 SDK에 대한 헤더 

다음 헤더에는 Intune 앱 SDK의 기능을 사용하도록 설정하는 데 필요한 API 함수 호출이 포함됩니다. 

    IntuneMAMAsyncResult.h
    IntuneMAMDataProtectionInfo.h
    IntuneMAMDataProtectionManager.h
    IntuneMAMFileProtectionInfo.h
    IntuneMAMFileProtectionManager.h
    IntuneMAMPolicyDelegate.h
    IntuneMAMLogger.h

# Xcode에서 Intune 앱 SDK 디버그

Microsoft Intune을 사용하여 MAM 사용이 가능한 앱을 테스트하기 전에 Xcode에서 `Settings.bundle` 을 사용할 수 있습니다. 그러면 Intune에 연결하지 않고도 테스트 정책을 설정할 수 있습니다. 사용하도록 설정하려면

* 프로젝트에서 최상위 폴더를 마우스 오른쪽 단추로 클릭하여 `Settings.bundle` 을 추가합니다. 메뉴에서 "추가 -> 새 파일"을 선택합니다. "리소스" 아래에서 추가할 "설정 번들" 템플릿을 선택합니다.

* 디버그 빌드에서만 `MAMDebugSettings.plist` 를 `Settings.bundle`.

* `Root.plist`(Settings.bundle)에서 "Type" 자식 창, "FileName" `MAMDebugSettings`의 기본 설정을 추가합니다.

* "설정 -> Your-App-Name"에서 "테스트 정책 사용"을 설정/해제합니다.

* (Xcode 내부 또는 외부에서) 앱을 시작합니다. 

* "설정 -> Your-App-Name > 테스트 정책 사용"에서 정책(예: 'PIN')을 설정/해제합니다.

* (Xcode 내부 또는 외부에서) 앱을 시작합니다. PIN이 예상대로 작동하는지 확인합니다.

> [!NOTE] 이제 "설정 -> Your-App-Name > 테스트 정책 사용"을 통해 설정을 사용하도록 설정하고 전환할 수 있습니다.

# 권장되는 iOS 모범 사례

다음은 iOS용으로 개발할 때 권장되는 몇 가지 모범 사례입니다.

iOS 파일 시스템은 대/소문자를 구분합니다. `libIntuneMAM.a` 및 `IntuneMAMResources.bundle`과 같은 파일 이름에 대/소문자가 올바른지 확인합니다.

Xcode에서 `libIntuneMAM.a`를 찾는 데 문제가 있는 경우 링커 검색 경로에 이 라이브러리 경로를 추가하면 문제를 해결할 수 있습니다.



<!--HONumber=May16_HO2-->


