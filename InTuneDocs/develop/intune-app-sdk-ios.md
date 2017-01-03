---
title: "iOS용 Microsoft Intune 앱 SDK 개발자 가이드 | Microsoft 문서"
description: "iOS용 Microsoft Intune 앱 SDK를 사용하면 iOS 앱에 MAM(모바일 앱 관리) 형태의 회사 Intune 앱 보호 정책을 통합할 수 있습니다."
keywords: 
author: mtillman
manager: angrobe
ms.author: mtillman
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8e280d23-2a25-4a84-9bcb-210b30c63c0b
ms.reviewer: oydang
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b068da7685792757825a4bc0d555e28ee0168cb1
ms.openlocfilehash: cb80d531a28eaccbd26bc53df3e13ad233522dcf


---

# <a name="microsoft-intune-app-sdk-for-ios-developer-guide"></a>iOS용 Microsoft Intune 앱 SDK 개발자 가이드

> [!NOTE]
> 먼저 지원되는 각 플랫폼에서 통합을 준비하는 방법을 설명하는 [Intune 앱 SDK 시작 가이드](intune-app-sdk-get-started.md) 문서를 읽어보는 것이 좋습니다.

iOS용 Microsoft Intune 앱 SDK를 사용하면 iOS 앱에 MAM(모바일 앱 관리) 형태의 회사 Intune 앱 보호 정책을 통합할 수 있습니다. MAM 지원 응용 프로그램은 Intune 앱 SDK와 통합된 응용 프로그램입니다. 이를 통해 IT 관리자는 Intune에서 앱을 적극적으로 관리할 때 모바일 앱에 정책을 배포할 수 있습니다.

## <a name="prerequisites"></a>필수 구성 요소

* Xcode 도구 집합 버전 5 이상이 설치된 OS X 10.8.5 이상의 Mac OS 컴퓨터에서 실행해야 합니다.

* [iOS용 Intune 앱 SDK 사용 조건](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios/blob/master/Microsoft%20License%20Terms%20Intune%20App%20SDK%20for%20iOS%20.pdf)을 확인하세요. 기록을 위해 사용 조건의 사본을 인쇄하여 보관. IOS용 Intune 앱 SDK를 다운로드하여 이러한 사용 조건에 동의합니다.  동의하지 않는 경우 소프트웨어를 사용하지 마세요.

* [GitHub](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios)에서 iOS용 Intune 앱 SDK 파일을 다운로드합니다.

## <a name="whats-in-the-sdk"></a>SDK에 포함된 내용

iOS용 Intune 앱 SDK에는 정적 라이브러리, 리소스 파일, API 헤더, 디버그 설정 plist 파일 및 구성기 도구가 포함되어 있습니다. 모바일 앱은 단순히 리소스 파일을 포함하고 대부분 정책 적용을 위해 라이브러리에 정적으로 연결할 수 있습니다. 고급 Intune MAM 기능은 API를 통해 적용됩니다.

이 가이드에서는 iOS용 Intune 앱 SDK의 다음 구성 요소 사용을 설명합니다.

* **libIntuneMAM.a**: Intune 앱 SDK 정적 라이브러리입니다. 앱에서 확장을 사용하지 않는 경우 이 라이브러리를 프로젝트에 연결하여 Intune 모바일 응용 프로그램 관리에 대해 앱을 사용하도록 설정합니다.

* **IntuneMAM.framework**: Intune 앱 SDK 프레임워크입니다. 이 프레임워크를 프로젝트에 연결하여 Intune 모바일 응용 프로그램 관리에 대해 앱을 사용하도록 설정합니다. 앱에서 확장을 사용하는 경우, 프로젝트에서 정적 라이브러리의 복사본을 여러 개 만들지 않도록 정적 라이브러리 대신 프레임워크를 사용합니다.

* **IntuneMAMResources.bundle**: SDK에서 사용하는 리소스가 있는 리소스 번들입니다.

* **헤더**: Intune 앱 SDK API를 표시합니다. API를 사용하는 경우 API가 포함된 헤더 파일을 포함해야 합니다. 다음 헤더 파일에는 Intune 앱 SDK의 기능을 사용하도록 설정하는 데 필요한 API 함수 호출이 포함되어 있습니다.

    * IntuneMAMAsyncResult.h
    * IntuneMAMDataProtectionInfo.h
    * IntuneMAMDataProtectionManager.h
    * IntuneMAMFileProtectionInfo.h
    * IntuneMAMFileProtectionManager.h
    * IntuneMAMPolicyDelegate.h
    * IntuneMAMLogger.h


## <a name="how-the-intune-app-sdk-works"></a>Intune 앱 SDK의 작동 방식

iOS용 Intune 앱 SDK의 목적은 최소한의 코드 변경으로 iOS 응용 프로그램에 관리 기능을 추가하는 것입니다. 모바일 응용 프로그램의 일관성과 안정성에 영향을 주지 않으면서 코드 변경을 적게 하고, 출시에 필요한 시간을 단축할 수 있습니다.

응용 프로그램이 정적 라이브러리에 연결되어야 하고 리소스 번들을 포함해야 합니다. MAMDebugSettings.plist 파일은 선택 사항입니다. Microsoft Intune을 통해 응용 프로그램을 배포하지 않고도 응용 프로그램에 적용되는 MAM 정책을 시뮬레이트하기 위해 패키지에 포함될 수 있습니다. 또한 디버그 빌드에서는 iTunes 파일 공유를 통해 앱의 문서 디렉터리에 파일을 전송하여 MAMDebugSettings.plist 파일의 정책을 적용할 수 있습니다.

## <a name="build-the-sdk-into-your-mobile-app"></a>모바일 앱으로 SDK 빌드

Intune 앱 SDK를 사용하려면 다음이 단계를 따르세요.

1. **옵션 1**: `libIntuneMAM.a` 라이브러리에 연결합니다. 프로젝트 대상의 **연결된 프레임워크 및 라이브러리** 목록으로 `libIntuneMAM.a` 라이브러리를 끌어옵니다.
    ![Intune 앱 SDK iOS - 연결된 프레임워크 및 라이브러리](../media/intune-app-sdk-ios-linked-frameworks-and-libraries.png)

    > [!NOTE]
    > 앱을 앱 스토어에 릴리스하려는 경우 디버그 버전이 아니라 릴리스용으로 빌드된 `libIntuneMAM.a` 버전을 사용하세요. 릴리스 버전은 **릴리스** 폴더에 포함됩니다. 디버그 버전에는 Intune 앱 SDK를 사용하여 문제를 해결하는 데 유용한 자세한 정보 출력이 있습니다.

    **옵션 2**: `IntuneMAM.framework`를 프로젝트에 연결합니다. 프로젝트 대상의 **연결된 프레임워크 및 라이브러리** 목록으로 `IntuneMAM.framework`를 끌어옵니다.

    > [!NOTE]
    > 프레임워크를 사용하는 경우 앱을 앱 스토어에 제출하기 전에 수동으로 범용 프레임워크에서 시뮬레이터 아키텍처를 제거해야 합니다. "앱 스토어에 앱 제출" 섹션을 참조하세요.

2. 프로젝트에 다음 iOS 프레임워크를 추가합니다.
    * MessageUI.framework
    * Security.framework
    * MobileCoreServices.framework
    * SystemConfiguration.framework
    * libsqlite3.dylib
    * libc++.dylib
    * ImageIO.framework
    * LocalAuthentication.framework
    * AudioToolbox.framework

    > [!NOTE]
    > 응용 프로그램이 iOS 7을 대상으로 하는 경우 `LocalAuthentication.framework`의 `Status` 특성을 "Optional"로 설정합니다. `Status`를 설정하지 않으면 iOS 7에서 응용 프로그램이 시작되지 않습니다.
    >
    > 또한 Xcode 7에서는 `.dylib` 확장이 `.tbd`로 전환되었습니다.

3. **빌드 단계** 내의 **번들 리소스 복사** 아래로 리소스 번들을 끌어 프로젝트에 `IntuneMAMResources.bundle` 리소스 번들을 추가합니다.
![Intune 앱 SDK iOS: 번들 리소스 복사](../media/intune-app-sdk-ios-copy-bundle-resources.png)

4. 프로젝트의 OTHER_LDFLAGS 빌드 구성 설정이나 UI의 "기타 링커 플래그"에 `-force_load {PATH_TO_LIB}/libIntuneMAM.a` 를 Intune 앱 SDK 위치로 대체하여 `{PATH_TO_LIB}` 를 다음 중 하나에 추가합니다.
    * 프로젝트의 `OTHER_LDFLAGS` 빌드 구성 설정
    * UI의 **기타 링커 플래그**<br>

    > [!NOTE]
    > `PATH_TO_LIB`를 찾으려면 `libIntuneMAM.a` 파일을 선택하고 **파일** 메뉴에서 **정보 가져오기**를 선택합니다. **정보** 창의 **일반** 섹션에서 **위치** 정보(경로)를 복사하여 붙여넣습니다.

5. 모바일 앱이 해당 Info.plist 파일에서 주 nib 또는 스토리보드를 정의하는 경우 **주 스토리보드** 또는 **주 Nib** 파일 필드를 제거합니다. IntuneMAMSettings라는 새 사전에 이전에 제거한 스토리보드 또는 nib 값을 다음과 같은 키 이름으로 추가합니다(해당하는 경우).
    * MainStoryboardFile
    * MainStoryboardFile~ipad
    * MainNibFile
    * MainNibFile~ipad

    > [!NOTE]
    > 모바일 앱이 해당 Info.plist 파일에서 주 nib 또는 스토리보드 파일을 정의하지 않는 경우에는 이러한 설정이 필요하지 않습니다.

    문서 본문의 아무 곳이나 마우스 오른쪽 단추로 클릭하고 보기 형식을 **원시 키/값 표시**로 변경하여 Info.plist를 원시 형식으로 표시할 수 있습니다(키 이름을 확인하기 위해).

6. 각 프로젝트 대상에서 **기능**을 클릭하고 **키 집합 공유** 스위치를 사용하도록 설정하여 키 집합 공유를 사용하도록 설정합니다(아직 설정되지 않은 경우). 다음 단계를 진행하려면 키 집합 공유가 필요합니다.

    > [!NOTE]
    > 프로비저닝 프로필이 새로운 키 집합 공유 값을 지원해야 합니다. 키 집합 액세스 그룹이 와일드카드 문자를 지원해야 합니다. 이를 확인하려면 텍스트 편집기에서 .mobileprovision 파일을 열고 **keychain-access-groups**를 검색한 다음 와일드카드가 있는지 확인합니다. 예를 들어     ```xml
    <key>keychain-access-groups</key>
    <array>
    <string>YOURBUNDLESEEDID.*</string>
    </array>
    ```를 구성할 수 있습니다.

7. 키 집합 공유를 사용하도록 설정한 후 다음 단계에 따라 Intune 앱 SDK 데이터를 저장할 별도의 액세스 그룹을 만듭니다. UI를 사용하거나 자격 파일을 사용하여 키 집합 액세스 그룹을 만들 수 있습니다.

    UI를 사용하여 키 집합 액세스 그룹을 만드는 경우

    a. 모바일 앱에 키 집합 액세스 그룹이 정의되어 있지 않으면 앱의 번들 ID를 첫 번째 그룹으로 추가합니다.

    b. 공유 키 집합 그룹 `com.microsoft.intune.mam`을 추가합니다. Intune 앱 SDK에서 이 액세스 그룹을 사용하여 데이터를 저장합니다.

    c. 기존 액세스 그룹에 `com.microsoft.adalcache`를 추가합니다.

    ![Intune 앱 SDK iOS: 키 집합 공유](../media/intune-app-sdk-ios-keychain-sharing.png)

    자격 파일을 사용하여 키 집합 액세스 그룹을 만드는 경우 자격 파일에서 키 집합 액세스 그룹 앞에 `$(AppIdentifierPrefix)`를 추가합니다. 예를 들면 다음과 같습니다.  

    * `$(AppIdentifierPrefix)com.microsoft.intune.mam`
    * `$(AppIdentifierPrefix)com.microsoft.adalcache`

    > [!NOTE]
    > 자격 파일은 모바일 응용 프로그램에 고유한 XML 파일입니다. IOS 앱에서 특수한 권한 및 기능을 지정하는 데 사용됩니다.

8. 앱이 해당 Info.plist 파일에서 URL 체계를 정의하는 경우 `-intunemam` 접미사를 사용하여 각 URL 체계에 대해 다른 체계를 추가합니다.

9. iOS 9 이상용으로 개발되는 모바일 앱의 경우 앱이 `UIApplication canOpenURL`에 전달하는 각 프로토콜을 앱 Info.plist 파일의 `LSApplicationQueriesSchemes` 배열에 포함합니다. 또한 나열된 각 프로토콜에 대해 새 프로토콜을 추가하고 앞에 `-intunemam`을 추가합니다. 또한 `http-intunemam`, `https-intunemam`및 `ms-outlook-intunemam` 을 배열에 포함해야 합니다.

10. 앱의 자격에 앱 그룹이 정의되어 있으면 이러한 그룹을 `AppGroupIdentitifiers` 키 아래의 IntuneMAMSettings 사전에 문자열 배열로 추가합니다.

11. 모바일 응용 프로그램을 ADAL(Azure Directory 인증 라이브러리)에 연결합니다. Objective C용 ADAL 라이브러리는 [GitHub에서 사용할 수 있습니다](https://github.com/AzureAD/azure-activedirectory-library-for-objc).

    > [!NOTE]
    > Intune 앱 SDK는 2015년 6월 19일의 ADAL 브로커 분기 코드에 대해 테스트되었습니다. ADAL 라이브러리의 최신/작업 버전에 연결하고 있는지 확인하세요.

12. **빌드 단계** 내의 **번들 리소스 복사** 아래로 리소스 번들을 끌어 프로젝트에 `ADALiOSBundle.bundle` 리소스 번들을 포함합니다.

13. 라이브러리에 연결하는 경우 `-force_load PATH_TO_ADAL_LIBRARY` 링커 옵션을 사용합니다.

    프로젝트의 `OTHER_LDFLAGS` 빌드 구성 설정이나 UI의 **기타 링커 플래그**에 `-force_load {PATH_TO_LIB}/libADALiOS.a`를 추가합니다. `PATH_TO_LIB`를 ADAL 이진 파일의 위치로 바꿔야 합니다.

## <a name="set-up-azure-directory-authentication-library"></a>Active Directory Authentication Library 설정

Intune 앱 SDK는 해당 인증 및 조건부 시작 시나리오에 ADAL을 사용합니다. 또한 ADAL을 사용하여 장치 등록 시나리오가 없는 관리를 위해 MAM 서비스에 사용자 ID를 등록합니다.

일반적으로 ADAL에서는 앱이 Azure AD(Azure Active Directory)에 등록하고 클라이언트 ID라는 고유 ID 및 기타 ID을 받아야 앱에 부여된 토큰의 보안이 보장됩니다. Intune 앱 SDK는 Azure AD에 연결할 때 기본 등록 값을 사용합니다.  

앱 자체에서 인증 시나리오에 ADAL을 사용하는 경우 기존 등록 값을 사용하고 Intune 앱 SDK 기본값을 재정의해야 합니다. 이렇게 하면 사용자에게 인증 메시지가 두 번(Intune 앱 SDK를 통해 한 번, 앱에서 한 번) 나타나지 않습니다.

### <a name="adal-faqs"></a>ADAL FAQ

**어떤 ADAL 이진 파일을 사용해야 하나요?**

현재 Intune 앱 SDK에서는 조건부 액세스가 필요한 앱을 지원하기 위해 [GitHub의 ADAL](https://github.com/AzureAD/azure-activedirectory-library-for-objc) 브로커 분기를 사용합니다. 따라서 이러한 앱은 Microsoft Authenticator 앱에 종속됩니다. 그러나 SDK는 ADAL의 마스터 분기와 계속 호환됩니다. 앱에 적합한 분기를 사용합니다.

**ADAL 이진 파일에 연결하려면 어떻게 하나요?**

프로젝트의 `OTHER_LDFLAGS` 빌드 구성 설정이나 UI의 **기타 링커 플래그**에 `-force_load {PATH_TO_LIB}/libADALiOS.a`를 추가합니다. `PATH_TO_LIB`를 ADAL 이진 파일의 위치로 바꿔야 합니다. 또한 앱에 ADAL 번들을 복사해야 합니다.  

자세한 내용은 [GitHub의 ADAL](https://github.com/AzureAD/azure-activedirectory-library-for-objc)에 설명된 지침을 참조하세요.

**같은 프로비전 프로필로 서명된 다른 앱과 ADAL 캐시를 공유하려면 어떻게 하나요?**

앱에 키 집합 액세스 그룹이 정의되어 있지 않으면 앱의 번들 ID를 첫 번째 그룹으로 추가합니다.

키 집합 자격에 `com.microsoft.adalcache` 및 `com.microsoft.workplacejoin` 액세스 그룹을 추가하여 ADAL SSO(Single Sign-On)를 사용하도록 설정합니다.

ADAL 공유 캐시 키 집합 그룹을 명시적으로 설정하는 경우 이를 `<app_id_prefix>.com.microsoft.adalcache`로 설정해야 합니다. 이를 재정의하지 않으면 ADAL에서 자동으로 설정합니다. 사용자 지정 키 집합 그룹을 지정하여 `com.microsoft.adalcache`를 바꾸려면 IntuneMAMSettings 아래의 Info.plist 파일에 `ADALCacheKeychainGroupOverride` 키를 사용하여 지정하세요.

**강제로 Intune 앱 SDK가 앱에서 이미 사용되고 있는 ADAL 설정을 사용하도록 하려면 어떻게 하나요?**

앱에서 이미 ADAL를 사용하고 있는 경우 아래 설정을 채우는 방법에 대한 자세한 내용은 IntuneMAMSettings에 대한 섹션을 참조하세요.  

* ADALClientId
* ADALRedirectUri
* ADALRedirectScheme
* ADALCacheKeychainGroupOverride

**Azure AD 프로덕션 환경과 내부 테스트 환경 간에 전환하려면 어떻게 하나요?**

MAMPolicies.plist에서 `AadAuthorityURI` 설정을 사용하여 ADAL 호출에 사용되는 Azure AD 환경을 지정할 수 있습니다. 재정의하지 않는 한, 현재 이 설정은 기본적으로 Azure AD PPE(사전 프로덕션 환경)로 설정됩니다.

PPE에 대해 테스트하려면 컴파일 시간 또는 런타임 스위치를 사용할 수 있습니다.

MAM 서비스 URL 및 Azure AD의 컴파일 시간 환경 스위치의 경우 MAMEnvironment.plist에서 `UsePPE` 부울 플래그를 true로 설정합니다. Info.plist를 통해 이렇게 할 수는 없습니다.

런타임 환경 스위치의 경우 표준 사용자 기본값에서 `com.microsoft.intune.mam.useppe`를 "1"로 설정하여 PPE를 사용하도록 합니다. 이 설정은 기존 `com.microsoft.intune.mam.AADAuthorityEnvironment` 설정을 대체합니다.

**Azure AD 기관 URL을 런타임에 제공된 테넌트 특정 URL로 재정의하려면 어떻게 하나요?**

IntuneMAMPolicyManager 인스턴스에 대해 `aadAuthorityUriOverride` 속성을 설정합니다.

> [!NOTE]
> 장치 등록이 없는 MAM 시나리오에서 SDK가 앱이 가져온 ADAL 새로 고침 토큰을 다시 사용할 수 있도록 하려면 이렇게 해야 합니다.

SDK는 값이 지워지거나 변경되지 않는 한 정책 새로 고침 및 후속 등록 요청에 이 기관 URL을 계속 사용합니다.  회사 사용자가 앱에서 로그아웃하면 값을 지우고 새로운 회사 사용자가 로그인하면 값을 재설정해야 합니다.

**앱 자체에서 인증에 ADAL을 사용하는 경우 어떻게 해야 하나요?**

앱에서 이미 인증에 ADAL을 사용하는 경우 다음 작업이 필요합니다.

* 프로젝트 Info.plist 파일의 IntuneMAMSettings 사전 아래에서 ADAL 호출에 사용할 ClientID를 키 이름 `ADALClientId`로 지정합니다.

* 프로젝트 Info.plist 파일의 IntuneMAMSettings 사전 아래에서 ADAL 호출에 사용할 리디렉션 URI를 키 이름 `ADALRedirectUri`로 지정합니다. 앱의 리디렉션 URI 형식에 따라 `ADALRedirectScheme`을 지정해야 할 수도 있습니다.

**앱에서 인증에 ADAL을 아직 사용하지 않는 경우에는 어떻게 되나요?**

앱에서 ADAL을 사용하지 않는 경우 Intune 앱 SDK는 ADAL 매개 변수에 대한 기본값을 제공하며, Azure AD에 대한 인증을 처리합니다.

## <a name="register-your-app-with-the-intune-mam-service"></a>Intune MAM 서비스에 앱 등록

### <a name="use-the-apis"></a>API 사용
이제 Intune 앱 SDK는 iOS 앱에 MAM(모바일 장치 관리)을 통해 Intune에 등록할 필요 없이 Intune에서 MAM 정책을 수신하는 기능을 제공합니다. 이 새로운 기능을 지원하기 위해 SDK는 앱이 MAM 정책을 수신할 수 있게 해주는 새로운 API를 제공합니다. 새 API를 사용하려면 다음 단계를 따르세요.

1. 장치 등록 여부와 관계없이 앱 관리를 지원하는 Intune 앱 SDK의 최신 릴리스를 사용합니다. 앱에 이 기능이 없는 이전 버전의 SDK가 사용된 경우 Headers 폴더를 최신 SDK의 헤더를 사용하여 업데이트해야 할 뿐만 아니라 Intune MAM 라이브러리도 업데이트해야 합니다.

2. API를 호출하는 모든 파일에 IntuneMAMEnrollment.h를 추가합니다.

3. PPE에 대해 테스트하려면 컴파일 시간 또는 런타임 스위치를 사용할 수 있습니다.

    MAM 서비스 URL 및 Azure AD의 컴파일 시간 환경 스위치의 경우 MAMEnvironment.plist에서 `UsePPE` 부울 플래그를 true로 설정합니다. Info.plist를 통해 이렇게 할 수는 없습니다.

    런타임 환경 스위치의 경우 표준 사용자 기본값에서 `com.microsoft.intune.mam.useppe`를 "1"로 설정하여 PPE를 사용하도록 합니다. 이 설정은 기존 `com.microsoft.intune.mam.AADAuthorityEnvironment` 설정을 대체합니다.


### <a name="register-accounts"></a>계정 등록

앱이 지정된 사용자 계정을 대신하여 등록된 경우 앱은 Intune 서비스로부터 MAM 정책을 수신할 수 있습니다. Intune 앱 SDK를 사용하여 새로 로그인한 사용자를 등록하는 것은 앱의 책임입니다. 새 사용자 계정이 인증된 후 앱은 다음과 같이 Headers/IntuneMAMEnrollment.h의 `registerAndEnrollAccount` 메서드를 호출해야 합니다.

```objc
/**


 *  This method will add the account to the list of registered accounts.
 *  An enrollment request will immediately be started.
 *  @param identity The UPN of the account to be registered with the SDK
 */

(void)registerAndEnrollAccount:(NSString *)identity;

```
`registerAndEnrollAccount` 메서드를 호출하여 SDK는 사용자 계정을 등록하고 이 계정을 대신하여 앱을 등록하려고 시도합니다. 어떤 이유로든 등록에 실패하면 SDK는 자동으로 24시간 후에 등록을 다시 시도합니다. 디버깅 목적으로 앱은 대리자를 통해 모든 등록 요청의 결과에 대한 알림을 수신할 수 있습니다.

이 API가 호출되고 나면 응용 프로그램이 정상적으로 계속 작동할 수 있습니다. 등록에 성공하면 SDK가 사용자에게 앱을 다시 시작해야 한다고 알립니다. 이때 사용자는 앱을 즉시 다시 시작할 수 있습니다.

### <a name="deregister-accounts"></a>계정 등록 취소

사용자가 앱에서 로그아웃하기 전에 앱이 SDK에서 사용자를 등록 취소해야 합니다. 그러면 다음 사항이 보장됩니다.

1. 사용자 계정에 대해 더 이상 등록이 다시 시도되지 않습니다.

2. 사용자가 응용 프로그램을 등록하면 사용자 및 앱이 Intune MAM 서비스에서 등록 취소되고 MAM 정책이 제거됩니다.

3. 필요에 따라 앱에서 선택적 초기화를 시작한 경우 모든 회사 또는 학교 관련 데이터가 삭제됩니다.

사용자가 로그아웃하기 전에 앱은 Headers/IntuneMAMEnrollment.h에서 다음 API를 호출해야 합니다.

```objc
/*
 *  This method will remove the provided account from the list of
 *  registered accounts.  Once removed, if the account has enrolled
 *  the application, the account will be un-enrolled.
 *  @note In the case where an un-enroll is required, this method will block
 *  until the Intune MAM AAD token is acquired, then return.  This method must be called before  
 *  the user is removed from the application (so that required AAD tokens are not purged
 *  before this method is called).
 *  @param identity The UPN of the account to be removed.
 *  @param doWipe   If YES, a selective wipe if the account is un-enrolled
 */

(void)deRegisterAndUnenrollAccount:(NSString *)identity withWipe:(BOOL)doWipe;
```

이 메서드는 사용자 계정의 Azure AD 토큰이 삭제되기 전에 호출해야 합니다. SDK에서는 사용자의 앱 토큰이 사용자를 대신하여 Intune MAM 서비스에 대해 특정 요청을 해야 합니다.

앱이 자체적으로 사용자의 회사 또는 학교 관련 데이터를 삭제하는 경우 `doWipe` 플래그를 false로 설정할 수 있습니다. 그렇지 않으면 앱은 SDK에서 선택적 초기화를 시작하도록 할 수 있습니다. 그러면 앱의 선택적 초기화 대리자가 호출됩니다.

```objc
[[IntuneMAMEnrollmentManager instance] deRegisterAndUnenrollAccount:@”user@foo.com” withWipe:YES];
```

## <a name="enroll-without-prior-sign-in"></a>이전 로그인 없이 등록

Azure Active Directory를 통해 사용자를 로그인하지 않는 앱은 API를 호출하여 SDK에서 해당 인증을 처리하도록 하여 Intune 서비스에서 MAM 정책을 계속 수신할 수 있습니다. 앱에 Azure AD로 인증된 사용자가 없지만 데이터를 보호하기 위해 MAM 정책을 수신해야 하는 경우 이 기술을 사용해야 합니다. 예를 들어 다른 인증 서비스가 앱 로그인에 사용되거나 앱에서 서명을 지원하지 않는 경우가 여기에 해당됩니다. 이렇게 하려면 응용 프로그램이 Headers/IntuneMAMEnrollment.h의 `loginAndEnrollAccount` 메서드를 호출해야 합니다.

```objc
/**
 *  Creates an enrollment request which is started immediately.
 *  If no token can be retrieved for the identity, the user will be prompted
 *  to enter their credentials, after which enrollment will be retried.
 *  @param identity The UPN of the account to be logged in and enrolled.
 */
 (void)loginAndEnrollAccount: (NSString *)identity;

```

이 메서드를 호출하면 기존 토큰을 찾을 수 없는 경우 SDK에서 사용자에게 자격 증명을 묻는 메시지를 표시합니다. 그런 다음 SDK는 이 계정을 대신해 응용 프로그램을 등록하려고 합니다. "nil"을 ID로 사용하여 메서드를 호출할 수 있습니다. 이 경우 SDK는 장치에서 기존 MAM 사용자로 등록하거나, 기존 사용자가 없는 경우 사용자 이름을 입력하라는 메시지를 표시합니다.

등록에 실패하는 경우 앱은 실패의 세부 정보에 따라 나중에 다시 이 API 호출을 고려해야 합니다. 앱은 대리자를 통해 모든 등록 요청의 결과에 대한 알림을 수신할 수 있습니다.

이 API가 호출되고 나면 앱이 정상적으로 계속 작동할 수 있습니다. 등록에 성공하면 SDK가 사용자에게 앱을 다시 시작해야 한다고 알립니다.

## <a name="status-result-and-debug-notifications"></a>상태, 결과 및 디버그 알림

앱은 Intune MAM 서비스에 대한 다음 요청과 관련한 상태, 결과 및 디버그 알림을 수신할 수 있습니다.

 - 등록 요청
 - 정책 업데이트 요청
 - 등록 취소 요청

알림은 다음과 같이 Headers/IntuneMAMEnrollmentDelegate.h의 대리자 메서드를 통해 제공됩니다.

```objc
/**
 *  Called when an enrollment request operation is completed.
 * @param status status object containing debug information
 */

(void)enrollmentRequestWithStatus:(IntuneMAMEnrollmentStatus *)status;

/**
 *  Called when a MAM policy request operation is completed.
 *  @param status status object containing debug information
 */
(void)policyRequestWithStatus:(IntuneMAMEnrollmentStatus *)status;

/**
 *  Called when a un-enroll request operation is completed.
 *  @Note: when a user is un-enrolled, the user is also de-registered with the SDK
 *  @param status status object containing debug information
 */

(void)unenrollRequestWithStatus:(IntuneMAMEnrollmentStatus *)status;

```

이러한 대리자 메서드는 다음 정보가 있는 `IntuneMAMEnrollmentStatus` 개체를 반환합니다.

- 요청과 연결된 계정의 ID
- 요청의 결과를 나타내는 상태 코드
- 상태 코드에 대한 설명이 포함된 오류 문자열
- `NSError` 개체입니다.

이 개체는 반환될 수 있는 특정 상태 코드와 함께 Headers/IntuneMAMEnrollmentStatus.h에 정의됩니다.




## <a name="sample-code"></a>예제 코드

다음은 대리자 메서드의 예제 구현입니다.

```objc
- (void)enrollmentRequestWithStatus:(IntuneMAMEnrollmentStatus *)status


{


    NSLog(@"enrollment result for identity %@ with status code %ld", status.identity, (unsigned long)status.statusCode);


    NSLog(@"Debug Message: %@", status.errorString);


}


- (void)policyRequestWithStatus:(IntuneMAMEnrollmentStatus *)status


{


    NSLog(@"policy check-in result for identity %@ with status code %ld", status.identity, (unsigned long)status.statusCode);


    NSLog(@"Debug Message: %@", status.errorString);


}


- (void)unenrollRequestWithStatus:(IntuneMAMEnrollmentStatus *)status


{


    NSLog(@"un-enroll result for identity %@ with status code %ld", status.identity, (unsigned long)status.statusCode);



    NSLog(@"Debug Message: %@", status.errorString);


}

```

## <a name="app-restart"></a>앱 다시 시작

앱이 처음으로 MAM 정책을 수신하면 필요한 후크를 적용하기 위해 다시 시작되어야 합니다. 다시 시작되어야 한다는 사실을 앱에 알리기 위해 SDK는 Headers/IntuneMAMPolicyDelegate.h의 대리자 메서드를 제공합니다.

```objc
 - (BOOL) restartApplication
```
이 메서드의 반환 값은 SDK에 응용 프로그램에서 필요한 다시 시작을 처리하는지를 알립니다.   

 - true가 반환되는 경우 응용 프로그램이 다시 시작을 처리합니다.   
 - false가 반환되는 경우 SDK는 이 메서드가 반환된 후 응용 프로그램을 다시 시작합니다. SDK는 사용자에게 응용 프로그램을 다시 시작하도록 알리는 대화 상자를 즉시 표시합니다.

## <a name="implement-save-as-controls"></a>다른 이름으로 저장 컨트롤 구현

Intune을 사용하여 IT 관리자는 관리되는 앱이 데이터를 저장할 수 있는 저장소 위치를 선택할 수 있습니다. 앱은 **isSaveToAllowedForLocation** API를 사용하여 Intune 앱 SDK에서 허용된 저장소 위치를 쿼리할 수 있습니다.

클라우드 저장소 또는 로컬 위치에 관리되는 데이터를 저장하려면 먼저 앱에서 **isSaveToAllowedForLocation** API를 사용하여 IT 관리자가 해당 위치로의 데이터 저장을 허용했는지 확인해야 합니다.

**isSaveToAllowedForLocation** API를 사용하는 경우 앱은 저장소 위치에 UPN(사용 가능한 경우)을 전달해야 합니다.

### <a name="supported-save-locations"></a>지원되는 저장 위치

**isSaveToAllowedForLocation** API는 IT 관리자가 다음 위치에 데이터를 저장하는 것을 허용하는지 여부를 확인하기 위한 상수를 제공합니다.

* IntuneMAMSaveLocationOther
* IntuneMAMSaveLocationOneDriveForBusiness
* IntuneMAMSaveLocationSharePoint
* IntuneMAMSaveLocationBox
* IntuneMAMSaveLocationDropbox
* IntuneMAMSaveLocationGoogleDrive
* IntuneMAMSaveLocationLocalDrive

앱은 **isSaveToAllowedForLocation** API의 상수를 사용하여 데이터를 "관리되는" 위치(예: 비즈니스용 OneDrive 또는 "개인")로 저장할 수 있는지 확인해야 합니다. 또한 앱에서 위치가 "관리되는" 위치인지 “개인” 위치인지 확인할 수 없을 때 이 API를 사용해야 합니다.

위치가 "개인" 위치로 알려진 경우 앱은 **IntuneMAMSaveLocationOther** 값을 사용해야 합니다.

앱이 로컬 장치의 위치로 데이터를 저장할 때는 **IntuneMAMSaveLocationLocalDrive** 상수를 사용해야 합니다.

## <a name="set-up-the-intune-app-sdk"></a>Intune 앱 SDK 설정

응용 프로그램의 Info.plist 파일에 포함된 IntuneMAMSettings 사전을 사용하여 Intune 앱 SDK를 설정할 수 있습니다. 다음은 지원되는 모든 설정 목록입니다.

이러한 설정 중 일부는 이전 섹션에서 설명되었을 수도 있으며 일부 앱에 적용되지 않는 설정도 있습니다.

설정  | 유형  | 정의 | 필수 여부
--       |  --   |   --       |  --
ADALClientId  | 문자열  | 앱의 Azure AD 클라이언트 식별자입니다. | 앱에서 ADAL을 사용하는 경우 필수입니다.
ADALRedirectUri  | 문자열  | 앱의 Azure AD 리디렉션 URI입니다. | 앱에서 ADAL을 사용하는 경우 ADALRedirectUri 또는 ADALRedirectScheme은 필수입니다.
ADALRedirectScheme  | 문자열  | 앱의 Azure AD 리디렉션 스키마입니다. 응용 프로그램의 리디렉션 URI가 `scheme://bundle_id` 형식인 경우 ADALRedirectUri 대신 이 설정을 사용할 수 있습니다. | 앱에서 ADAL을 사용하는 경우 ADALRedirectUri 또는 ADALRedirectScheme은 필수입니다.
ADALLogOverrideDisabled | 부울  | SDK에서 모든 ADAL 로그(있는 경우 앱에서의 ADAL 호출 포함)를 해당 로그 파일로 라우팅할지 여부를 지정합니다. 기본값은 NO입니다. 앱이 해당 ADAL 로그 콜백을 설정하려는 경우 YES로 설정합니다. | 선택 사항입니다.
ADALCacheKeychainGroupOverride | 문자열  | "com.microsoft.adalcache" 대신 ADAL 캐시에 사용할 키 집합 그룹을 지정합니다. 이 설정에는 app-id 접두사가 없습니다. 이 접두사는 런타임에 제공된 문자열에 추가됩니다. | 선택 사항입니다.
AppGroupIdentifiers | 문자열 배열  | 앱 자격 com.apple.security.application-groups 섹션의 앱 그룹 배열입니다. | 앱이 응용 프로그램 그룹을 사용하는 경우에 필요합니다.
ContainingAppBundleId | 문자열 | 확장의 포함 응용 프로그램 번들 ID를 지정합니다. | iOS 확장에 필요합니다.
DebugSettingsEnabled| 부울 | YES로 설정할 경우 설정 번들 내의 테스트 정책을 적용할 수 있습니다. 응용 프로그램은 이 설정이 사용하도록 설정된 상태로 제공되어서는 *안 됩니다*. | 선택 사항입니다.
MainNibFile<br>MainNibFile~ipad  | 문자열  | 이 설정에는 응용 프로그램의 주 nib 파일 이름이 있어야 합니다.  | 응용 프로그램이 해당 Info.plist에서 MainNibFile을 정의하는 경우에 필수입니다.
MainStoryboardFile<br>MainStoryboardFile~ipad  | 문자열  | 이 설정에는 응용 프로그램의 주 스토리보드 파일 이름이 있어야 합니다. | 응용 프로그램이 해당 Info.plist에서 UIMainStoryboardFile을 정의하는 경우에 필수입니다.
MAMPolicyRequired| 부울| 앱에 Intune MAM 정책이 없는 경우 앱이 시작되지 않도록 할지를 지정합니다. 기본값은 NO입니다. | 선택 사항입니다.
MAMPolicyWarnAbsent | 부울| 앱에 Intune MAM 정책이 없는 경우 앱이 시작 시 사용자에게 경고할지를 지정합니다. 이 설정이 YES로 설정된 스토어에는 앱을 제출할 수 없습니다. | 선택 사항입니다.
MultiIdentity | 부울| 앱이 다중 ID를 인식하는지를 지정합니다. | 선택 사항입니다.
SplashIconFile <br>SplashIconFile~ipad | 문자열  | Intune 시작 아이콘 파일을 지정합니다. | 선택 사항입니다.
SplashDuration | 숫자 | 응용 프로그램 시작 시 Intune 시작 화면이 표시되는 최소 시간(초)입니다. 기본값은 1.5입니다. | 선택 사항입니다.
BackgroundColor| 문자열| 시작 및 PIN 화면의 배경색을 지정합니다. '#XXXXXX' 형식의 16진수 RGB 문자열을 허용합니다. 여기서 X는 0-9 또는 A-F 범위의 값일 수 있습니다. 파운드 기호는 생략할 수 있습니다.   | 선택 사항입니다. 기본값은 연한 회색입니다.
ForegroundColor| 문자열| 시작 및 PIN 화면의 전경색(텍스트 색 등)을 지정합니다. '#XXXXXX' 형식의 16진수 RGB 문자열을 허용합니다. 여기서 X는 0-9 또는 A-F 범위의 값일 수 있습니다. 파운드 기호는 생략할 수 있습니다.  | 선택 사항입니다. 기본값은 검정입니다.
AccentColor | 문자열| PIN 화면의 테마 컬러(예: 단추 텍스트 색 및 상자 강조 색)를 지정합니다. '#XXXXXX' 형식의 16진수 RGB 문자열을 허용합니다. 여기서 X는 0-9 또는 A-F 범위의 값일 수 있습니다. 파운드 기호는 생략할 수 있습니다.| 선택 사항입니다. 기본값은 시스템 파란색입니다.
MAMTelemetryDisabled| 부울| SDK가 원격 분석 데이터를 해당 백 엔드로 보내는지를 지정합니다.| 선택 사항입니다.
MAMTelemetryUsePPE | 부울 | SDK에서 PPE 백 엔드에 데이터를 보낼지를 지정합니다. 테스트 원격 분석 데이터가 고객 데이터와 혼합되지 않도록 Intune 정책을 사용하여 앱을 테스트하는 경우 이 설정을 사용합니다. | 선택 사항입니다.

## <a name="telemetry"></a>원격 분석

기본적으로 iOS용 Intune 앱 SDK는 다음 사용 이벤트에 대한 원격 분석 데이터를 기록합니다. 이 데이터는 Microsoft Intune로 전송됩니다.

* **앱 시작**: Microsoft Intune이 관리 유형별로 MAM 지원 앱 사용에 대해 알아보는 데 도움이 됩니다(MDM이 있는 MAM, MDM 등록이 없는 MAM 등).
* **EnrollApplication API 호출**: Microsoft Intune이 클라이언트 쪽에서 `enrollApplication` 호출의 성공률 및 다른 성능 메트릭에 대해 알아보는 데 도움이 됩니다.

> [!NOTE]
> 모바일 응용 프로그램에서 Microsoft Intune에 Intune 앱 SDK 원격 분석 데이터를 보내지 않도록 선택하는 경우 Intune 앱 SDK 원격 분석 캡처를 사용하지 않도록 설정해야 합니다. IntuneMAMSettings 사전에서 `MAMTelemetryDisabled` 속성을 YES로 설정합니다.

## <a name="enable-multi-identity-optional"></a>(선택 사항) 다중 ID 사용 설정

기본적으로 SDK는 앱에 전체적으로 정책을 적용합니다. 다중 ID는 ID 단위 수준에서 정책을 적용하기 위해 사용할 수 있는 MAM 기능입니다. 이 기능을 사용하려면 다른 MAM 기능보다 더 많은 앱 참여가 필요합니다.

앱은 활성 ID를 변경하려는 경우 앱 SDK에 알려야 합니다. SDK는 ID 변경이 필요한 경우 앱에도 알립니다. 현재 관리 ID는 하나만 지원됩니다. 사용자가 장치 또는 앱을 등록하고 나면 SDK에서 이 ID를 사용하고 이를 기본 관리 ID로 간주합니다. 앱의 다른 사용자는 무제한 정책 설정이 적용되는 관리되지 않는 항목으로 처리됩니다.

ID는 단순히 문자열로 정의됩니다. ID는 대/소문자를 구분하지 않습니다. ID와 관련한 SDK에 대한 요청은 ID를 설정할 때 원래 사용된 것과 같은 대/소문자를 반환하지 않을 수도 있습니다.

### <a name="identity-overview"></a>ID 개요

ID는 계정의 사용자 이름일 뿐입니다. 예를 들어 user@contoso.com). 개발자는 다음 수준에서 앱의 ID를 설정할 수 있습니다.

* **프로세스 ID**: 프로세스 전반 ID를 설정하고 주로 단일 ID 응용 프로그램에 사용됩니다. 이 ID는 모든 작업, 파일 및 UI에 영향을 줍니다.
* **UI ID**: 잘라내기/복사/붙여넣기, PIN, 인증, 데이터 공유 등 주 스레드에서 UI 작업에 적용되는 정책을 결정합니다. UI ID는 파일 작업(암호화, 백업 등)에 영향을 주지 않습니다.
* **스레드 ID**: 현재 스레드에 적용되는 정책에 영향을 줍니다. 이 ID는 모든 작업, 파일 및 UI에 영향을 줍니다.

사용자가 관리되는지와 관계없이 ID를 적절하게 설정하는 것은 앱의 책임입니다.

어느 시점에서든 모든 스레드에는 UI 작업 및 파일 작업에 대한 유효한 ID가 있습니다. 이 ID는 적용되어야 하는 정책(있는 경우)을 확인하는 데 사용됩니다. ID가 'ID 없음'이거나 사용자가 관리되지 않는 경우 정책이 적용되지 않습니다.

### <a name="thread-queues"></a>스레드 큐

앱은 흔히 비동기 및 동기 작업을 스레드 큐로 디스패치합니다. SDK는 GCD(Grand Central Dispatch) 호출을 가로채고 현재 스레드 ID를 디스패치된 작업과 연결합니다. 작업이 종료되면 SDK는 일시적으로 스레드 ID를 작업과 연결된 ID로 변경하고 작업을 종료한 다음 원래 스레드 ID를 복원합니다.


`NSOperationQueue`는 GCD를 기반으로 구축되므로 `NSOperations`는 `NSOperationQueue`에 작업이 추가될 때 스레드의 ID에서 실행됩니다. GCD를 통해 직접 디스패치된 `NSOperations` 또는 함수는 실행되고 있을 때 현재 스레드 ID를 변경할 수도 있습니다. 이 ID는 디스패치하는 스레드에서 상속된 ID를 재정의합니다.

### <a name="file-owner"></a>파일 소유자

SDK는 로컬 파일 소유자 ID를 추적하여 적절하게 정책을 적용합니다. 파일이 만들어지거나 파일이 잘라내기 모드에서 열리면 파일 소유자가 설정됩니다. 소유자는 작업을 수행하는 스레드의 유효 파일 작업 ID로 설정됩니다.

또는 앱은 `IntuneMAMFilePolicyManager`를 사용하여 명시적으로 파일 소유자 ID를 설정할 수 있습니다. 앱은 파일 내용을 표시하기 전에 `IntuneMAMFilePolicyManager`를 사용하여 파일 소유자를 검색하고 UI ID를 설정합니다.

### <a name="shared-data"></a>공유 데이터

앱이 관리되는 사용자와 관리되지 않는 사용자 둘 다의 데이터를 포함하는 파일을 만드는 경우 관리되는 사용자의 데이터를 암호화하는 것은 앱의 책임입니다. `IntuneMAMDataProtectionManager`에서 `protect` 및 `unprotect` API를 사용하여 데이터를 암호화할 수 있습니다.

`protect` 메서드는 관리되는 사용자 또는 관리되지 않는 사용자일 수 있는 ID를 허용합니다. 사용자가 관리되는 경우 데이터가 암호화됩니다. 사용자가 관리되지 않는 경우 ID를 인코딩하는 데이터에 헤더가 추가되지만 데이터는 암호화되지 않습니다. `protectionInfo` 메서드를 사용하여 데이터의 소유자를 검색할 수 있습니다.

### <a name="share-extensions"></a>공유 확장

앱에 공유 확장이 있는 경우 `IntuneMAMDataProtectionManager`의 `protectionInfoForItemProvider` 메서드를 통해 공유되는 항목의 소유자를 검색할 수 있습니다. 공유 항목이 파일인 경우 SDK에서 파일 소유자 설정을 처리합니다. 공유 항목이 데이터인 경우 파일 소유자를 설정하고(이 데이터가 파일에 유지되는 경우) 이 데이터를 UI에 표시하기 전에 `setUIPolicyIdentity` API를 호출하는 것은 앱의 책임입니다.

### <a name="turning-on-multi-identity"></a>다중 ID 설정

기본적으로 앱은 단일 ID로 간주됩니다. SDK는 등록된 사용자의 프로세스 ID를 설정합니다. 다중 ID 지원을 사용하려면 앱의 Info.plis 파일에 있는 IntuneMAMSettings 사전에 이름이 `MultiIdentity`이고 값이 YES인 부울 설정을 추가합니다.

> [!NOTE]
> 다중 ID를 사용하도록 설정한 경우 프로세스 ID, UI ID 및 스레드 ID는 nil로 설정됩니다. 이를 적절하게 설정하는 것은 앱은 책임입니다.

### <a name="switching-identities"></a>ID 전환

* **앱에서 시작된 ID 전환**:

    다중 ID 앱은 시작될 때 알 수 없는, 관리되지 않는 계정으로 실행된다고 간주됩니다. 조건부 시작 UI는 실행되지 않으며 앱에서 정책이 적용되지 않습니다. ID를 변경해야 할 때마다 SDK에 알리는 것은 앱의 책임입니다. 일반적으로 이러한 상황은 앱이 특정 사용자 계정에 대한 데이터를 표시하려고 할 때마다 발생합니다.

    사용자가 문서, 사서함 또는 전자 필기장의 탭을 열려고 하는 경우를 예로 들 수 있습니다. 앱은 파일, 사서함 또는 탭이 실제로 열리기 전에 SDK에 알려야 합니다. 이 작업은 `IntuneMAMPolicyManager`의 `setUIPolicyIdentity` API를 통해 수행됩니다. 이 API는 사용자가 관리되는지와 관계없이 호출되어야 합니다. 사용자가 관리되는 경우 SDK는 조건부 시작 검사(탈옥 검색, PIN, 인증 등)를 수행합니다.

    ID 전환 결과는 완료 처리기를 통해 비동기적으로 앱에 반환됩니다. 성공 결과 코드가 반환될 때까지 앱은 문서, 사서함 또는 탭을 여는 작업을 연기해야 합니다. ID 전환에 실패하는 경우 앱은 작업을 취소해야 합니다.

* **SDK에서 시작된 ID 전환**:

    SDK가 앱에 특정 ID로의 전환을 요청해야 하는 경우가 있습니다. 다중 ID 앱은 `IntuneMAMPolicyDelegate`에 이 요청을 처리하기 위한 `identitySwitchRequired` 메서드를 구현해야 합니다.

    이 메서드가 호출되면 앱은 지정된 ID로의 전환 요청을 처리할 수 있는 경우 `IntuneMAMAddIdentityResultSuccess`를 완료 처리기에 전달해야 합니다. 앱이 ID 전환을 처리할 수 없는 경우 `IntuneMAMAddIdentityResultFailed`를 완료 처리기에 전달해야 합니다.

    앱은 이 호출에 대한 응답으로 `setUIPolicyIdentity`를 호출할 필요는 없습니다. SDK가 앱이 관리되지 않는 사용자 계정으로 전환하도록 요구하는 경우 빈 문자열이 `identitySwitchRequired` 호출에 전달됩니다.

* **선택적 초기화**:

    앱이 선택적으로 초기화된 경우 SDK는 `IntuneMAMPolicyDelegate`의 `wipeDataForAccount` 메서드를 호출합니다. 지정된 사용자의 계정 및 해당 계정과 연결된 모든 데이터를 제거하는 것은 앱의 책임입니다. SDK는 사용자가 소유한 모든 파일을 제거할 수 있으며, 앱이 `wipeDataForAccount` 호출에서 FALSE를 반환하는 경우 이렇게 합니다.

    이 메서드는 백그라운드 스레드에서 호출됩니다. 사용자에 대한 모든 데이터(앱에서 FALSE를 반환하는 경우에는 파일 제외)가 제거될 때까지 앱에서 값을 반환해서는 안 됩니다.

## <a name="debug-the-intune-app-sdk-in-xcode"></a>Xcode에서 Intune 앱 SDK 디버그

Microsoft Intune을 사용하여 MAM 지원 앱을 수동으로 테스트하기 전에 Xcode에서 Settings.bundle 파일을 사용할 수 있습니다. 그러면 Intune에 연결하지 않고도 테스트 정책을 설정할 수 있습니다. 사용하도록 설정하려면

1. 프로젝트에서 최상위 폴더를 마우스 오른쪽 단추로 클릭하여 Settings.bundle 파일을 추가합니다. 메뉴에서 **추가** > **새 파일**을 선택합니다. **리소스** 아래에서 추가할 **설정 번들** 템플릿을 선택합니다.

2. 디버그 빌드에서만 MAMDebugSettings.plist를 Settings.bundle에 복사합니다.

3. Settings.bundle에 있는 Root.plist에서 `Type` = `Child Pane` 및 `FileName` = `MAMDebugSettings`인 기본 설정을 추가합니다.

4. **설정** > **Your-App-Name**에서 **테스트 정책 사용**을 설정합니다.

5. Xcode 내부 또는 외부에서 앱을 시작합니다.

6. **설정** > **Your-App-Name** > **테스트 정책 사용**에서 정책(예: **PIN**)을 설정합니다.

7. Xcode 내부 또는 외부에서 앱을 시작합니다. PIN이 예상대로 작동하는지 확인합니다.

> [!NOTE]
> **설정** > **Your-App-Name** > **테스트 정책 사용**을 통해 설정을 사용하도록 설정하고 전환할 수 있습니다.

## <a name="ios-best-practices"></a>iOS 모범 사례

다음은 iOS용으로 개발할 때 권장되는 모범 사례입니다.

* iOS 파일 시스템은 대/소문자를 구분합니다. `libIntuneMAM.a` 및 `IntuneMAMResources.bundle`과 같이 파일 이름의 대/소문자가 올바른지 확인합니다.

* Xcode에서 `libIntuneMAM.a`를 찾는 데 문제가 있는 경우 링커 검색 경로에 이 라이브러리 경로를 추가하면 문제를 해결할 수 있습니다.

## <a name="faq"></a>FAQ

**내 앱의 모든 사용자를 MAM 서비스에 등록해야 하나요?**

아니요. 실제로 회사 또는 학교 계정만 Intune 앱 SDK에 등록하면 됩니다. 계정이 회사 또는 학교 컨텍스트에서 사용되는지를 결정하는 것은 앱의 책임입니다.   

**앱에 이미 로그인한 사용자의 경우는 어떤가요? 등록해야 하나요?**

성공적으로 인증된 후 사용자를 등록하는 것은 응용 프로그램의 책임입니다. 또한 응용 프로그램이 MDM 없는 MAM 기능을 가지기 전에 존재했을 수 있는 기존 계정을 등록하는 것도 응용 프로그램의 책임입니다.   

이렇게 하려면 응용 프로그램이 `registeredAccounts:` 메서드를 사용해야 합니다. 이 메서드는 등록된 모든 계정이 있는 NSDictionary를 Intune MAM 서비스에 반환합니다. 응용 프로그램의 모든 기존 계정이 목록에 없는 경우 응용 프로그램은 `registerAndEnrollAccount:`을 통해 해당 계정을 등록해야 합니다.

**SDK가 등록을 다시 시도하는 빈도는 어느 정도인가요?**

SDK는 이전에 실패한 모든 등록을 24시간 간격으로 자동으로 다시 시도합니다. SDK는 사용자의 조직에서 사용자가 응용 프로그램에 로그인한 후 MAM을 사용하도록 설정한 경우 사용자가 등록되고 정책을 수신하도록 하기 위해 이렇게 합니다.

SDK는 사용자가 응용 프로그램을 등록했음을 감지하면 다시 시도를 중지합니다. 특정 시점에 1명의 사용자만 응용 프로그램을 등록할 수 있기 때문입니다. 사용자가 등록 취소된 경우 다시 시도는 같은 24시간 간격으로 다시 시작됩니다.

**사용자를 등록 취소해야 하는 이유는 무엇인가요?**

SDK는 백그라운드에서 주기적으로 다음 작업을 수행합니다.

 - 응용 프로그램이 아직 등록되지 않은 경우 SDK는 24시간마다 모든 등록된 계정을 등록하려고 시도합니다.
 - 응용 프로그램이 등록된 경우 SDK는 8시간마다 MAM 정책 업데이트를 확인합니다.

사용자를 등록 취소하면 사용자가 더 이상 응용 프로그램을 사용하지 않으며 해당 사용자 계정에 대한 주기적 이벤트를 중지할 수 있음이 SDK에 통지됩니다. 또한 등록 취소하고 필요한 경우 선택적 초기화를 수행하라고 앱을 트리거합니다.

**등록 취소 메서드에서 doWipe 플래그를 true로 설정해야 하나요?**

사용자가 응용 프로그램에서 로그아웃하기 전에 이 메서드를 호출해야 합니다.  로그아웃 진행 과정의 일부로 사용자의 데이터가 응용 프로그램에서 삭제되면 `doWipe`를 false로 설정할 수 있습니다. 그러나 응용 프로그램이 사용자의 데이터를 제거하지 않는 경우 SDK가 데이터를 삭제할 수 있도록 `doWipe`를 true로 설정해야 합니다.

**앱을 등록 취소할 수 있는 다른 방법이 있나요?**

예, IT 관리자는 응용 프로그램에는 선택적 초기화 명령을 보낼 수 있습니다. 그러면 사용자가 등록 취소되고 사용자의 데이터가 초기화됩니다. SDK는 이 시나리오를 자동으로 처리하고 등록 취소 대리자 메서드를 통해 알림을 보냅니다.

## <a name="submit-your-app-to-the-app-store"></a>앱 스토어에 앱 제출

Intune 앱 SDK의 정적 라이브러리 빌드와 프레임워크 빌드는 둘 다 범용 이진 파일입니다. 따라서 모든 장치와 시뮬레이터 아키텍처에 대한 코드가 있습니다. Apple은 앱에 시뮬레이터 코드가 있는 경우 앱 스토어에 제출된 앱을 거부합니다. 장치 전용 빌드의 정적 라이브러리에 대해 컴파일할 때 링커에서 시뮬레이터 코드를 자동으로 제거합니다. 앱 스토어에 앱을 업로드하기 전에 모든 시뮬레이터 코드를 제거하려면 다음 단계를 수행합니다.

1. 데스크톱에 `IntuneMAM.framework`가 있는지 확인합니다.

2. 다음 명령을 실행하세요.

    ```bash
    lipo ~/Desktop/IntuneMAM.framework/IntuneMAM -remove i386 -remove x86_64 -output ~/Desktop/IntuneMAM.device_only
    ```

    ```bash
    cp ~/Desktop/IntuneMAM.device_only ~/Desktop/IntuneMAM.framework/IntuneMAM
    ```
    첫 번째 명령은 프레임워크의 DYLIB 파일에서 시뮬레이터 아키텍처를 제거합니다. 두 번째 명령은 장치 전용 DYLIB 파일을 프레임워크 디렉터리에 다시 복사합니다.



<!--HONumber=Dec16_HO3-->


