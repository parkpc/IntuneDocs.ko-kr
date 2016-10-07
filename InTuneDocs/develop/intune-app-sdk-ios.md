---
title: "iOS용 Microsoft Intune 앱 SDK 개발자 가이드 | Microsoft Intune"
description: 
keywords: 
author: Msmbaldwin
manager: jeffgilb
ms.date: 09/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8e280d23-2a25-4a84-9bcb-210b30c63c0b
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 975708b5204ab83108a9174083bb87dfeb04a063
ms.openlocfilehash: 52ad28686fa279a7ec251d073283c3554d1c81fc


---

# iOS용 Microsoft Intune 앱 SDK 개발자 가이드

> [!NOTE]
> 먼저 지원되는 각 플랫폼에서 통합을 준비하는 방법을 설명하는 [Intune 앱 SDK 시작 가이드](intune-app-sdk-get-started.md)를 읽어보는 것이 좋습니다.* 

iOS용 Microsoft Intune 앱 SDK를 사용하면 iOS 앱에 Intune MAM(모바일 앱 관리)을 통합할 수 있습니다. MAM 지원 응용 프로그램은 Intune 앱 SDK와 통합된 응용 프로그램으로, 앱이 Intune에 의해 적극적으로 관리되는 경우 IT 관리자가 모바일 앱에 정책을 배포할 수 있게 해줍니다.


# SDK에 포함된 내용 

iOS용 Intune 앱 SDK에는 정적 라이브러리, 리소스 파일, API 헤더, 디버그 설정 plist 및 구성기 도구가 포함되어 있습니다. 모바일 앱은 단순히 리소스 파일을 포함하고 대부분 정책 적용을 위해 라이브러리에 정적으로 연결할 수 있습니다. 고급 Intune MAM 기능은 API를 통해 적용됩니다.

이 가이드에서는 iOS용 Intune 앱 SDK의 다음 구성 요소 사용을 설명합니다.

* **libIntuneMAM.a**: Intune 앱 SDK 정적 라이브러리입니다. 앱에서 확장을 사용하지 않는 경우 이 라이브러리를 프로젝트에 연결하여 Intune 모바일 응용 프로그램 관리에 대해 앱을 사용하도록 설정합니다. 지침은 "Intune 앱 SDK를 사용하여 앱 빌드" 섹션에 있습니다.

* **IntuneMAM.framework**: Intune 앱 SDK 프레임워크입니다. 이 프레임워크를 프로젝트에 연결하여 Intune 모바일 응용 프로그램 관리에 대해 앱을 사용하도록 설정합니다. 앱에서 확장을 사용하는 경우, 프로젝트에서 정적 라이브러리의 복사본을 여러 개 만들지 않도록 정적 라이브러리 대신 프레임워크를 사용합니다.

* **IntuneMAMResources.bundle**: SDK에서 사용하는 리소스가 포함된 리소스 번들입니다. 

* **헤더**: Intune 앱 SDK API를 표시합니다. API를 사용하는 경우 API가 포함된 헤더 파일을 포함해야 합니다. 다음 헤더 파일에는 Intune 앱 SDK의 기능을 사용하도록 설정하는 데 필요한 API 함수 호출이 포함되어 있습니다. 
    
    * IntuneMAMAsyncResult.h
    * IntuneMAMDataProtectionInfo.h
    * IntuneMAMDataProtectionManager.h
    * IntuneMAMFileProtectionInfo.h
    * IntuneMAMFileProtectionManager.h
    * IntuneMAMPolicyDelegate.h
    * IntuneMAMLogger.h 


# Intune 앱 SDK의 작동 방식

iOS용 Intune 앱 SDK의 목적은 최소한의 코드 변경으로 iOS 응용 프로그램에 관리 기능을 추가하는 것입니다. 코드 변경을 적게 하고, 출시에 필요한 시간을 줄이면서도 모바일 응용 프로그램의 일관성과 안정성은 계속 보장할 수 있습니다. 

응용 프로그램이 정적 라이브러리에 연결되어야 하고 리소스 번들을 포함해야 합니다. MAMDebugSettings.plist 파일은 선택 사항이며, Microsoft Intune을 통해 응용 프로그램을 배포하지 않고도 응용 프로그램에 적용되는 MAM 정책을 시뮬레이트하기 위해 패키지에 포함될 수 있습니다. 또한 디버그 빌드에서는 iTunes 파일 공유를 통해 앱의 문서 디렉터리에 파일을 전송하여 MAMDebugSettings.plist 파일의 정책을 적용할 수 있습니다.

# 모바일 앱으로 SDK 빌드 

Intune 앱 SDK를 사용하도록 설정하려면 아래 단계를 완료합니다.

1. **옵션 1**: 다음을 수행하여 `libIntuneMAM.a` 라이브러리에 연결합니다.

    프로젝트 대상의 "연결된 프레임워크 및 라이브러리" 목록에 `libIntuneMAM.a` 라이브러리를 끌어서 놓습니다.
    ![Intune 앱 SDK iOS - 연결된 프레임워크 및 라이브러리](../media/intune-app-sdk-ios-linked-frameworks-and-libraries.png) 

    **참고**: 앱을 앱 스토어에 릴리스하려는 경우 디버그 버전이 아니라 릴리스용으로 빌드된 `libIntuneMAM.a` 버전을 사용하세요. 릴리스 버전은 "릴리스" 폴더에 포함됩니다. 디버그 버전은 Intune 앱 SDK를 사용하여 문제를 해결하는 데 유용한 자세한 정보 출력을 포함합니다.
    
    **옵션 2**: `IntuneMAM.framework`를 프로젝트에 연결합니다. 프로젝트 대상의 "연결된 프레임워크 및 라이브러리" 목록에 `IntuneMAM.framework`를 끌어서 놓습니다.
    
    **참고**: 프레임워크를 사용하는 경우 앱을 앱 스토어에 제출하기 전에 수동으로 범용 프레임워크에서 시뮬레이터 아키텍처를 제거해야 합니다. "앱 스토어에 앱 제출" 섹션을 참조하세요.

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

    **참고**: 응용 프로그램이 iOS 7을 대상으로 하는 경우 `LocalAuthentication.framework`의 "Status" 특성을 "Optional"로 설정합니다. "Status"를 설정하지 않으면 iOS 7에서 응용 프로그램이 시작되지 않습니다.

    **참고**: Xcode 7에서는 `.dylib` 확장이 `.tbd`.

3. "빌드 단계" 내의 "번들 리소스 복사" 아래로 리소스 번들을 끌어 프로젝트에 `IntuneMAMResources.bundle` 리소스 번들을 추가합니다.
![Intune 앱 SDK iOS - 번들 리소스 복사](../media/intune-app-sdk-ios-copy-bundle-resources.png)
 
4. 프로젝트의 OTHER_LDFLAGS 빌드 구성 설정이나 UI의 "기타 링커 플래그"에 `-force_load {PATH_TO_LIB}/libIntuneMAM.a` 를 Intune 앱 SDK 위치로 대체하여 `{PATH_TO_LIB}` 를 다음 중 하나에 추가합니다.
    * 프로젝트의 `OTHER_LDFLAGS` 빌드 구성 설정 
    * UI의 "기타 링커 플래그"<br>

    **참고**: `PATH_TO_LIB`를 찾으려면 `libIntuneMAM.a` 파일을 선택하고 "파일" 메뉴에서 "정보 가져오기"를 선택합니다. "정보" 창의 "일반" 섹션에서 "위치" 정보(경로)를 복사하여 붙여넣습니다.

5. 모바일 앱이 해당 Info.plist에서 주 Nib 또는 스토리보드를 정의하는 경우 주 스토리보드 또는 주 Nib 파일 필드를 제거합니다. IntuneMAMSettings라는 새 사전에 이전에 제거한 스토리보드 또는 Nib 값을 다음과 같은 키 이름으로 추가합니다(해당하는 경우).
    * MainStoryboardFile
    * MainStoryboardFile~ipad
    * MainNibFile
    * MainNibFile~ipad
    
   **참고**: 모바일 앱이 해당 Info.plist에서 주 Nib 또는 스토리보드를 정의하지 않는 경우에는 이러한 설정이 **필요하지 않습니다**. 

    **참고**: 문서 본문의 아무 곳이나 마우스 오른쪽 단추로 클릭하고 보기 형식을 "원시 키/값 표시"로 변경하여 Info.plist를 원시 형식으로 표시할 수 있습니다(키 이름을 확인하기 위해).

6. 각 프로젝트 대상에서 "기능"을 클릭하고 "키 집합 공유" 스위치를 사용하도록 설정하여 키 집합 공유를 사용하도록 설정합니다(아직 설정되지 않은 경우). 다음 단계를 진행하려면 키 집합 공유가 필요합니다.

    **참고**: 프로비저닝 프로필이 새로운 키 집합 공유 값을 지원해야 합니다. 키 집합 액세스 그룹이 와일드카드 문자를 지원해야 합니다. 이를 확인하려면 텍스트 편집기에서 .mobileprovision 파일을 열고 'keychain-access-groups'를 검색한 다음 와일드카드가 있는지 확인합니다. 예를 들면 다음과 같습니다. 
    ```
    <key>keychain-access-groups</key>
    <array>
    <string>YOURBUNDLESEEDID.*</string>
    </array>
    ```
7. 키 집합 공유를 사용하도록 설정한 후 다음 단계에 따라 Intune 앱 SDK 데이터를 저장할 별도의 액세스 그룹을 만듭니다. UI를 사용하거나 자격 파일을 사용하여 키 집합 액세스 그룹을 만들 수 있습니다.

    UI를 사용하여 키 집합 액세스 그룹 만들기: 
    
    * 모바일 앱에 키 집합 액세스 그룹이 정의되어 있지 않으면 앱의 번들 ID를 첫 번째 그룹으로 추가합니다.
    * 공유 키 집합 그룹 `com.microsoft.intune.mam`을 추가합니다. 이 액세스 그룹은 Intune 앱 SDK에서 데이터를 저장하는 데 사용됩니다.  
    * 기존 액세스 그룹에 `com.microsoft.adalcache`를 추가합니다. 

    ![Intune 앱 SDK iOS - 키 집합 공유](../media/intune-app-sdk-ios-keychain-sharing.png) 

    일반 UI보다 자격 파일을 사용하여 키 집합 액세스 그룹을 만드는 경우 자격 파일에서 키 집합 액세스 그룹 앞에 `$(AppIdentifierPrefix)` 를 추가해야 합니다. 예를 들면 다음과 같습니다.  
    * `$(AppIdentifierPrefix)com.microsoft.intune.mam` 
    * `$(AppIdentifierPrefix)com.microsoft.adalcache`

    **참고**: 자격 파일은 iOS 앱 내에서 특별한 사용 권한 및 기능을 지정하는 데 사용되는 해당 모바일 응용 프로그램에 고유한 XML 파일입니다.

8. 앱이 해당 Info.plist 파일에서 URL 체계를 정의하는 경우 `-intunemam` 접미사를 사용하여 각 URL 체계에 대해 다른 체계를 추가합니다.

9. iOS 9 이상용으로 개발되는 모바일 앱의 경우 앱이 `UIApplication canOpenURL`에 전달하는 각 프로토콜을 앱 Info.plist 파일의 `LSApplicationQueriesSchemes` 배열에 포함해야 합니다. 또한 나열된 각 프로토콜에 대해 새 프로토콜을 추가하고 앞에 `-intunemam`. 또한 `http-intunemam`, `https-intunemam`및 `ms-outlook-intunemam` 을 배열에 포함해야 합니다. 

10. 앱의 자격에 앱 그룹이 정의되어 있으면 이러한 그룹을 `AppGroupIdentitifiers` 키 아래의 IntuneMAMSettings 사전에 문자열 배열로 추가합니다.

11. 모바일 응용 프로그램을 ADAL(Azure Directory 인증 라이브러리)에 연결합니다. Objective C용 ADAL 라이브러리는 [Github에서 사용할 수 있습니다](https://github.com/AzureAD/azure-activedirectory-library-for-objc).

    **참고**: Intune 앱 SDK는 2015년 6월 19일의 ADAL 브로커 분기 코드에 대해 테스트되었습니다. ADAL 라이브러리의 최신/작업 버전에 연결하고 있는지 확인하세요.

12. "빌드 단계" 내의 "번들 리소스 복사" 아래로 리소스 번들을 끌어 프로젝트에 `ADALiOSBundle.bundle` 리소스 번들을 포함합니다.

13. 라이브러리에 연결하는 경우 `-force_load PATH_TO_ADAL_LIBRARY` 링커 옵션을 사용합니다.

    프로젝트의 `OTHER_LDFLAGS` 빌드 구성 설정이나 UI의 "기타 링커 플래그"에 `-force_load {PATH_TO_LIB}/libADALiOS.a`를 추가합니다. `PATH_TO_LIB` 를 ADAL 이진 파일 위치로 바꿔야 합니다. 

# 앱에서 ADAL(Azure Directory 인증 라이브러리) 설정 구성 

Intune 앱 SDK는 해당 인증 및 조건부 시작 시나리오에 ADAL을 사용합니다. 또한 ADAL을 사용하여 장치 등록 시나리오가 없는 관리를 위해 MAM 서비스에 사용자 ID를 등록합니다. 

일반적으로 ADAL에서는 앱이 ClientID라는 고유 ID 및 앱에 부여된 토큰의 보안을 보장하기 위한 기타 식별자를 등록하고 얻어야 합니다. Intune 앱 SDK는 Azure Active Directory에 연결할 때 기본 등록 값을 사용합니다.  

앱 자체에서 해당 인증 시나리오에 ADAL을 사용하는 경우 앱은 기존 등록 값을 사용하고 Intune 앱 SDK 기본값을 재정의하여 최종 사용자에게 인증 확인 메시지가 두 번(Intune 앱 SDK에 의해 한 번, 앱에 의해 한 번) 표시되지 않도록 해야 합니다. 

##ADAL FAQ

**어떤 ADAL 이진 파일을 사용해야 하나요?** 

현재 Intune 앱 SDK에서는 조건부 액세스가 필요한 앱(따라서 Microsoft Authenticator 앱에 의존하는 앱)을 지원하기 위해 [ADAL on GitHub](https://github.com/AzureAD/azure-activedirectory-library-for-objc)(GitHub의 ADAL)의 브로커 분기를 사용합니다. 그러나 SDK는 ADAL의 마스터 분기와 계속 호환됩니다. 앱에 적합한 분기를 사용하세요.

**ADAL 이진 파일에 연결하려면 어떻게 하나요?**

프로젝트의 `OTHER_LDFLAGS` 빌드 구성 설정이나 UI의 "기타 링커 플래그"에 `-force_load {PATH_TO_LIB}/libADALiOS.a`를 추가합니다. `PATH_TO_LIB` 를 ADAL 이진 파일 위치로 바꿔야 합니다. 또한 앱에 ADAL 번들을 복사해야 합니다.  

자세한 내용은 [ADAL on Github](https://github.com/AzureAD/azure-activedirectory-library-for-objc)(GitHub의 ADAL)의 지침을 참조하세요.


**같은 프로비전 프로필로 서명된 다른 앱과 ADAL 캐시를 공유하려면 어떻게 하나요?**

앱에 키 집합 액세스 그룹이 정의되어 있지 않으면 앱의 번들 ID를 첫 번째 그룹으로 추가합니다.
키 집합 자격에 `com.microsoft.adalcache` 및 `com.microsoft.workplacejoin` 액세스 그룹을 추가하여 ADAL SSO를 사용하도록 설정합니다. 

ADAL 공유 캐시 키 집합 그룹을 명시적으로 설정하는 경우 이를 `<app_id_prefix>.com.microsoft.adalcache`로 설정해야 합니다. 이를 재정의하지 않으면 ADAL에서 자동으로 설정합니다. 사용자 지정 키 집합 그룹을 지정하여 `com.microsoft.adalcache`를 바꾸려면 "IntuneMAMSettings" 아래의 Info.plist에 `ADALCacheKeychainGroupOverride` 키를 사용하여 지정하세요.

**강제로 Intune 앱 SDK가 앱에서 이미 사용되고 있는 ADAL 설정을 사용하도록 하려면 어떻게 하나요?** 

앱에서 이미 ADAL를 사용하고 있는 경우 아래 설정을 채우는 방법에 대한 자세한 내용은 아래의 IntuneMAMSettings에 대한 섹션을 참조하세요.  

* ADALClientId
* ADALRedirectUri
* ADALRedirectScheme
* ADALCacheKeychainGroupOverride

**AAD 프로덕션 환경과 내부 테스트 환경 간에 전환하려면 어떻게 하나요?**

`MAMPolicies.plist`의 `AadAuthorityURI` 설정을 사용하여 ADAL 호출에 사용되는 AAD 환경을 지정할 수 있습니다. 재정의하지 않는 한, 현재 이 설정은 기본적으로 AAD PPE(사전 프로덕션 환경)로 설정됩니다.
    
PPE에 대해 테스트하려면 컴파일 시간 또는 런타임 스위치를 사용할 수 있습니다. 

MAM 서비스 URL 및 AAD의 컴파일 시간 환경 스위치의 경우 MAMEnvironment.plist에서 설정된 `UsePPE` 부울 플래그를 true로 설정합니다(**참고**: Info.plist를 통해 이렇게 할 수는 없음). 

런타임 환경 스위치의 경우 표준 사용자 기본값에서 `com.microsoft.intune.mam.useppe`를 "1"로 설정하여 PPE를 사용하도록 합니다. 이 설정은 기존 `com.microsoft.intune.mam.AADAuthorityEnvironment` 설정을 대체합니다. 

**AAD 기관 URL을 런타임에 제공된 테넌트 특정 URL로 재정의하려면 어떻게 하나요?** 

IntuneMAMPolicyManager 인스턴스에 대해 `aadAuthorityUriOverride` 속성을 설정합니다.

**참고**: 장치 등록 시나리오가 없는 MAM에서 SDK가 앱이 가져온 ADAL 새로 고침 토큰을 다시 사용할 수 있도록 하려면 이렇게 해야 합니다.

**참고:** SDK는 값이 지워지거나 변경되지 않는 한 정책 새로 고침 및 후속 등록 요청에 이 기관 URL을 계속 사용합니다.  따라서 회사 사용자가 앱에서 로그아웃하면 값을 지우고 새로운 회사 사용자가 다시 로그인하면 값을 재설정해야 합니다.


**앱 자체에서 인증에 ADAL을 사용하는 경우 어떻게 해야 하나요?**

앱에서 이미 인증에 ADAL을 사용하는 경우 아래 단계가 필요합니다. 앱에서 ADAL을 사용하지 않는 경우 Intune 서비스에 등록하는 방법에 대한 섹션을 검토해야 합니다.

* 프로젝트 Info.plist의 IntuneMAMSettings 사전 아래에서 ADAL 호출에 사용할 ClientID를 키 이름 `ADALClientId`로 지정합니다. 

* 프로젝트 Info.plist의 IntuneMAMSettings 사전 아래에서 ADAL 호출에 사용할 리디렉션 URI를 키 이름 `ADALRedirectUri`로 지정합니다. 앱의 리디렉션 URI 형식에 따라 `ADALRedirectScheme` 을 지정해야 할 수도 있습니다.



#MAM 서비스에 앱 등록 

## API 사용
이제 Intune 앱 SDK는 iOS 앱에 Intune에서 MDM에 등록할 필요 없이 Intune에서 MAM 정책을 수신하는 기능을 제공합니다. 이 새로운 기능을 지원하기 위해 SDK는 앱이 MAM 정책을 수신할 수 있게 해주는 새로운 API를 제공합니다. 새로운 API를 사용하려면 다음 단계를 완료하세요.

1. 장치 등록 여부와 관계없이 앱 관리를 지원하는 Intune 앱 SDK의 최신 릴리스를 사용합니다. 앱에 이 기능이 없는 이전 버전의 SDK가 사용된 경우 Headers 폴더를 최신 SDK의 헤더를 사용하여 업데이트해야 할 뿐만 아니라 Intune MAM 라이브러리도 업데이트해야 합니다.

2. API를 호출하는 모든 파일에 IntuneMAMEnrollment.h를 추가합니다. 

3. PPE에 대해 테스트하려면 컴파일 시간 또는 런타임 스위치를 사용할 수 있습니다. 

    MAM 서비스 URL 및 AAD의 컴파일 시간 환경 스위치의 경우 MAMEnvironment.plist에서 설정된 `UsePPE` 부울 플래그를 true로 설정합니다(**참고**: Info.plist를 통해 이렇게 할 수는 없음). 

    런타임 환경 스위치의 경우 표준 사용자 기본값에서 `com.microsoft.intune.mam.useppe`를 "1"로 설정하여 PPE를 사용하도록 합니다. 이 설정은 기존 `com.microsoft.intune.mam.AADAuthorityEnvironment` 설정을 대체합니다. 


##계정 등록 

앱이 지정된 사용자 계정을 대신하여 등록된 경우 앱은 Intune 서비스로부터 MAM 정책을 수신할 수 있습니다.  Intune 앱 SDK를 사용하여 새로 로그인한 사용자를 등록하는 것은 앱의 책임입니다.  새 사용자 계정이 인증된 후 앱은 다음과 같이 Headers/IntuneMAMEnrollment.h에 있는 `registerAndEnrollAccount` 메서드를 호출해야 합니다. 

```
/** 


 *  This method will add the account to the list of registered accounts. 
 *  An enrollment request will immediately be started.
 *  @param identity The UPN of the account to be registered with the SDK 
 */ 

(void)registerAndEnrollAccount:(NSString *)identity; 

```
위의 메서드를 호출하여 SDK는 사용자 계정을 등록하고 이 계정을 대신하여 앱을 등록하려고 시도합니다.  어떤 이유로든 등록에 실패하면 SDK는 자동으로 24시간 후에 등록을 다시 시도합니다.  디버깅 목적으로 앱은 대리자를 통해 모든 등록 요청의 결과에 대한 알림을 수신할 수 있습니다(아래 세부 정보 참조).

이 API가 호출되고 나면 응용 프로그램이 정상적으로 계속 작동할 수 있습니다.  등록에 성공하면 SDK가 사용자에게 앱을 다시 시작해야 한다고 알립니다.  이때 사용자는 앱을 즉시 다시 시작할 수 있습니다.


##계정 등록 취소 


사용자가 앱에서 로그아웃하기 전에 앱이 SDK에서 사용자를 등록 취소해야 합니다.  그러면 다음 사항이 보장됩니다. 

1. 사용자 계정에 대해 더 이상 등록이 다시 시도되지 않습니다. 
2. 사용자가 응용 프로그램을 등록하면 사용자 및 앱이 Intune MAM 서비스에서 등록 취소되고 MAM 정책이 제거됩니다.
3. 필요에 따라 선택적 초기화를 시작하여 모든 회사 또는 학교 관련 데이터가 삭제되도록 할 수 있습니다. 

사용자가 로그아웃하기 전에 앱은 Headers/IntuneMAMEnrollment.h에 있는 다음 API를 호출해야 합니다. 

```
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

이 메서드는 사용자 계정의 AAD 토큰이 삭제되기 전에 호출해야 합니다.  SDK에서는 사용자의 앱 토큰이 사용자를 대신하여 Intune MAM 서비스에 대해 특정 요청을 해야 합니다. 

앱이 자체적으로 사용자의 회사 또는 학교 관련 데이터를 삭제하는 경우 `doWipe` 플래그를 false로 설정할 수 있습니다.  그러지 않으면 앱은 SDK가 선택적 초기화를 시작하도록 할 수 있으며, 이에 따라 앱의 선택적 초기화 대리자에 대한 호출이 생성됩니다. 

```
[[IntuneMAMEnrollmentManager instance] deRegisterAndUnenrollAccount:@”user@foo.com” withWipe:YES]; 
```


##이전 로그인 없이 등록 

Azure Active Directory를 통해 사용자를 로그인하지 않는 앱은 아래 API를 호출하여 SDK에서 해당 인증을 처리하도록 하여 Intune 서비스에서 MAM 정책을 계속 수신할 수 있습니다. 앱은 AAD로 사용자를 인증하지 않았지만 해당 앱의 데이터를 보호하기 위해 계속 MAM 정책을 검색해야 하는 경우(예: 앱 로그인에 다른 인증 서비스가 사용되거나 앱이 로그인을 전혀 지원하지 않는 경우) 이를 사용해야 합니다. 이렇게 하려면 응용 프로그램이 Headers/IntuneMAMEnrollment.h에 있는 `loginAndEnrollAccount` 메서드를 호출해야 합니다.

```
/** 
 *  Creates an enrollment request which is started immediately. 
 *  If no token can be retrieved for the identity, the user will be prompted 
 *  to enter their credentials, after which enrollment will be retried. 
 *  @param identity The UPN of the account to be logged in and enrolled. 
 */ 
 (void)loginAndEnrollAccount: (NSString *)identity; 

```
SDK는 이 메서드를 호출하여 기존 토큰이 없는 경우 자격 증명을 입력하라는 메시지를 표시한 다음 이 계정을 대신하여 응용 프로그램 등록을 시도합니다. "nil"을 ID로 사용하여 메서드를 호출할 수 있으며, 이 경우 SDK는 장치에서 기존 MAM 사용자로 등록하거나, 기존 사용자가 없는 경우 사용자 이름을 입력하라는 메시지를 표시합니다. 

등록에 실패하는 경우 앱은 실패의 세부 정보에 따라 나중에 다시 이 API 호출을 고려해야 합니다. 앱은 대리자를 통해 모든 등록 요청의 결과에 대한 알림을 수신할 수 있습니다(세부 정보 참조). 

이 API가 호출되고 나면 앱이 정상적으로 계속 작동할 수 있습니다.  등록에 성공하면 계정 등록에 대한 위 섹션에 표시된 것처럼 SDK가 사용자에게 앱을 다시 시작해야 한다고 알립니다. 

##디버그 정보 

앱은 Intune MAM 서비스에 대한 다음 요청과 관련한 디버그 알림을 수신할 수 있습니다. 

 - 등록 요청 
 - 정책 업데이트 요청 
 - 등록 취소 요청 

알림은 다음과 같이 Headers/IntuneMAMEnrollmentDelegate.h에서 찾을 수 있는 대리자 메서드를 통해 제공됩니다. 

```
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

이러한 대리자 메서드는 다음 정보를 포함하는 ```IntuneMAMEnrollmentStatus``` 개체를 반환합니다. 

- 요청과 연결된 계정의 ID 
- 요청의 결과를 나타내는 상태 코드 
- 상태 코드에 대한 설명이 포함된 오류 문자열 
- NSError 개체 

이 개체는 반환될 수 있는 특정 상태 코드와 함께 Headers/IntuneMAMEnrollmentStatus.h에 정의됩니다. 

이 정보는 디버그 목적으로 제공되며, 어떠한 앱의 비즈니스 논리도 이러한 알림을 기반으로 해서는 안 됩니다.  요점은 앱이 디버깅 또는 모니터링 목적으로 이 정보를 원격 분석 서비스로 보낼 수 있다는 것입니다. 


##샘플 코드 

다음은 대리자 메서드의 예제 구현입니다. 

```
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


##앱 다시 시작 

앱이 처음으로 MAM 정책을 수신하면 필요한 후크를 적용하기 위해 다시 시작되어야 합니다.  다시 시작되어야 한다는 사실을 앱에 알리기 위해 SDK는 Headers/IntuneMAMPolicyDelegate.h의 대리자 메서드를 제공합니다. 
```
 - (BOOL) restartApplication 
```
이 메서드의 반환 값은 SDK에 응용 프로그램에서 필요한 다시 시작을 처리하는지를 알립니다.   

 - true가 반환되는 경우 응용 프로그램이 다시 시작 처리를 담당합니다.   
 - false가 반환되는 경우 SDK는 이 메서드가 반환된 후 응용 프로그램을 다시 시작합니다.  SDK는 사용자에게 응용 프로그램을 다시 시작해야 한다는 사실을 알리는 대화 상자를 즉시 표시합니다. 



# Intune 앱 SDK 설정 구성

응용 프로그램의 Info.plist에 포함된 IntuneMAMSettings 사전은 Intune 앱 SDK를 구성하는 데 사용됩니다. 다음은 지원되는 모든 설정 목록입니다. 

이러한 설정 중 일부는 이전 섹션에서 설명되었을 수도 있으며 일부 앱에 적용되지 않는 설정도 있습니다. 

설정  | 유형  | 정의 | 필수 여부
--       |  --   |   --       |  --
ADALClientId  | 문자열  | 앱의 AAD 클라이언트 식별자입니다. | 앱에서 ADAL을 사용하는 경우 필수입니다.
ADALRedirectUri  | 문자열  | 앱의 AAD 리디렉션 URI입니다. | 앱에서 ADAL을 사용하는 경우 ADALRedirectUri 또는 ADALRedirectScheme은 필수입니다. 
ADALRedirectScheme  | 문자열  | 앱의 AAD 리디렉션 구성표입니다. 응용 프로그램의 리디렉션 URI가 `scheme://bundle_id` 형식인 경우 ADALRedirectUri 대신 이 설정을 사용할 수 있습니다. | 앱에서 ADAL을 사용하는 경우 ADALRedirectUri 또는 ADALRedirectScheme은 필수입니다. 
ADALLogOverrideDisabled | 부울  | SDK에서 모든 ADAL 로그(있는 경우 앱에서의 ADAL 호출 포함)를 해당 로그 파일로 라우팅할지 여부를 지정합니다. 기본값은 NO입니다. 앱이 해당 ADAL 로그 콜백을 설정하려는 경우 YES로 설정합니다. | 선택 사항입니다.
ADALCacheKeychainGroupOverride | 문자열  | "com.microsoft.adalcache" 대신 ADAL 캐시에 사용할 키 집합 그룹을 지정합니다. 이 설정은 app-id 접두사를 포함하지 않습니다. 이 접두사는 런타임에 제공된 문자열에 추가됩니다. | 선택 사항입니다.
AppGroupIdentifiers | 문자열 배열  | 앱 자격 com.apple.security.application-groups 섹션의 앱 그룹 배열입니다. | 앱이 응용 프로그램 그룹을 사용하는 경우에 필요합니다.
ContainingAppBundleId | 문자열 | 확장의 포함 응용 프로그램 번들 ID를 지정합니다. | iOS 확장에 필요합니다.
DebugSettingsEnabled| 부울 | YES로 설정할 경우 설정 번들 내의 테스트 정책을 적용할 수 있습니다. 응용 프로그램은 이 설정이 사용하도록 설정된 상태로 제공되어서는 **안 됩니다**. | 선택 사항입니다.
MainNibFile<br>MainNibFile~ipad  | 문자열  | 이 설정은 응용 프로그램의 주 nib 파일 이름을 포함해야 합니다.  | 응용 프로그램이 해당 Info.plist에서 MainNibFile을 정의하는 경우에 필수입니다.
MainStoryboardFile<br>MainStoryboardFile~ipad  | 문자열  | 이 설정은 응용 프로그램의 주 스토리보드 파일 이름을 포함해야 합니다. | 응용 프로그램이 해당 Info.plist에서 UIMainStoryboardFile을 정의하는 경우에 필수입니다.
MAMPolicyRequired| 부울| 앱에 Intune MAM 정책이 없는 경우 앱이 시작되지 않도록 할지를 지정합니다. 기본값은 "no"입니다. 
MAMPolicyWarnAbsent | 부울| 앱에 Intune MAM 정책이 없는 경우 앱이 시작 시 사용자에게 경고할지를 지정합니다. 참고: 이 설정이 YES로 설정된 스토어에는 앱을 제출할 수 없습니다. | 선택 사항입니다.
MultiIdentity | 부울| 앱이 다중 ID를 인식하는지를 지정합니다. | 선택 사항입니다.
SplashIconFile <br>SplashIconFile~ipad | 문자열  | Intune 시작 아이콘 파일을 지정합니다. 자세한 내용은 이 문서의 "시작 시 이미지 파일" 섹션을 참조하세요. | 선택 사항입니다.
SplashDuration | 숫자 | 응용 프로그램 시작 시 Intune 시작 화면이 표시되는 최소 시간(초)입니다. 기본값은 1.5입니다. | 선택 사항입니다.
BackgroundColor| 문자열| 시작 화면 및 PIN 화면의 배경색을 지정합니다. '#XXXXXX' 형식의 16진수 RGB 문자열을 허용합니다. 여기서 'X'는 0-9 또는 A-F 범위의 값일 수 있습니다. 파운드 기호는 생략할 수 있습니다.   | 선택 사항이며, 기본값은 연한 회색입니다.
ForegroundColor| 문자열| 시작 화면 및 PIN 화면의 전경색(예: 텍스트 색)을 지정합니다. '#XXXXXX' 형식의 16진수 RGB 문자열을 허용합니다. 여기서 'X'는 0-9 또는 A-F 범위의 값일 수 있습니다. 파운드 기호는 생략할 수 있습니다.  | 선택 사항이며, 기본값은 검정색입니다.
AccentColor | 문자열| PIN 화면의 테마 컬러(예: 단추 텍스트 색 및 상자 강조 색)를 지정합니다.  '#XXXXXX' 형식의 16진수 RGB 문자열을 허용합니다. 여기서 'X'는 0-9 또는 A-F 범위의 값일 수 있습니다. 파운드 기호는 생략할 수 있습니다.| 선택 사항이며, 기본값은 시스템 파란색입니다.
MAMTelemetryDisabled| 부울| SDK가 원격 분석 데이터를 해당 백 엔드로 다시 보내는지를 지정합니다.| 선택 사항입니다.
MAMTelemetryUsePPE | 부울 | SDK가 PPE(사전 프로덕션 환경) 백 엔드에 데이터를 보내는지를 지정합니다. 테스트 원격 분석 데이터가 고객 데이터와 혼합되지 않도록 Intune 정책을 사용하여 앱을 테스트하는 경우 이 설정을 사용합니다. | 선택 사항입니다.

## 원격 분석 

기본적으로 iOS용 Intune 앱 SDK는 Microsoft Intune에 전송된 사용 이벤트에 대한 원격 분석 데이터를 기록합니다. 다음과 같은 사용 이벤트에 대한 데이터가 기록됩니다. 

1. **앱 시작**: Microsoft Intune이 관리 유형별로 MAM 지원 앱 사용에 대해 알아보는 데 도움이 됩니다(MDM이 있는 MAM, MDM 등록이 없는 MAM 등).

2. **EnrollApplication API 호출**: Microsoft Intune이 클라이언트 쪽에서 `enrollApplication` 호출의 성공률 및 다른 다양한 성능 메트릭에 대해 알아보는 데 도움이 됩니다.

**참고**: 모바일 응용 프로그램에서 Microsoft Intune으로 Intune 앱 SDK 원격 분석 데이터를 보내지 않도록 하는 경우 IntuneMAMSettings 사전에서 `MAMTelemetryDisabled` 속성을 "YES"로 설정하여 Intune 앱 SDK 원격 분석 캡처를 사용하지 않도록 설정해야 합니다.


## 확장으로 SDK 빌드(선택 사항) 

확장을 빌드하는 경우 "모바일 앱으로 SDK 빌드" 섹션에 설명된 것과 동일한 지침에 따라 모바일 앱을 빌드합니다. 또한 IntuneMAMSettings 사전 아래에 응용 프로그램의 번들 ID를 포함하는 값을 사용해 `ContainingAppBundleId` 키를 추가하여 각 확장의 Info.plist 파일을 업데이트합니다.

## 프레임워크로 SDK 빌드(선택 사항)

Intune 앱 SDK의 최신 업데이트에서는 모바일 앱에 포함된 응용 프로그램 프레임워크가 있는 경우 특정 링커 플래그를 사용하여 모바일 앱을 컴파일할 필요가 없습니다. 

## 시작 시 이미지 파일(옵션)

MAM 사용이 가능한 앱이 Microsoft Intune에서 적극적으로 관리되는 경우 Intune 앱 SDK는 앱 시작 시 시작 화면을 표시하여 앱이 관리되고 있음을 사용자에게 나타냅니다. 필요에 따라 "회사에서 관리" 시작 페이지에 표시할 이미지 파일을 추가할 수도 있습니다. 이미지에 대한 다음 지침을 따르세요.

* 앱 Info.plist의 IntuneMAMSettings 사전 아래에 키 이름 `SplashIconFile` 및 `SplashIconFile~ipad`를 사용해 파일 이름을 추가합니다. 

* 이미지 크기 및 요구 사항:

    * iPhone 6s Plus 및 iPhone 6 Plus의 경우 180x180, 다른 iPhone 모델의 경우 120x120, iPad의 경우 152x152. 
    
    * 파일 이름에서 .png 확장명을 제거합니다. 
    
    * 라이브러리에 연결하는 경우 `@2x` 접미사를 사용하고, 3x 배율 버전에는 `@3x` 접미사를 사용합니다. 이미지가 올바른 크기가 아니면 크기가 적절하게 조정됩니다. SplashIconFile 값이 지정되지 않은 경우 Intune 앱 SDK는 앱의 아이콘 중 하나를 선택합니다(모든 iPhone의 경우 60x60, iPad의 경우 76x76).

**참고**: 이 화면은 시작 시 트리거되지만 사용자가 영구적으로 해제할 수 있습니다.



#다중 ID 사용(선택 사항)

기본적으로 SDK는 앱에 전체적으로 정책을 적용합니다. 다중 ID는 정책을 ID 수준별로 적용하기 위해 설정할 수 있는 MAM 기능입니다.  이 기능을 사용하려면 다른 MAM 기능보다 더 많은 앱 참여가 필요합니다. 

앱은 활성 ID를 변경하려는 경우 앱 SDK에 알려야 합니다. SDK는 ID 변경이 필요한 경우 앱에도 알립니다. 현재 관리 ID는 하나만 지원됩니다. 사용자가 장치 또는 앱을 등록하고 나면 SDK에서 이 ID를 사용하고 이를 기본 관리 ID로 간주합니다. 앱의 다른 사용자는 무제한 정책 설정이 적용되는 관리되지 않는 항목으로 처리됩니다. 

ID는 단순히 문자열로 정의됩니다. ID는 대/소문자를 구분하지 않으며 ID와 관련한 SDK에 대한 요청은 ID를 설정할 때 원래 사용된 것과 같은 대/소문자를 반환하지 않을 수도 있습니다.


##ID 이해 
  
ID는 단순히 계정(예: user@contoso.com)의 사용자 이름입니다. 개발자는 다음과 같은 다양한 수준에서 앱의 ID를 설정할 수 있습니다. 

* **프로세스 ID**: 프로세스 ID는 프로세스 전반 ID를 설정하고 주로 단일 ID 응용 프로그램에 사용됩니다. 이 ID는 모든 작업, 파일 및 UI에 영향을 줍니다.
* **UI ID**: 잘라내기/복사/붙여넣기, PIN, 인증, 데이터 공유 등 주 스레드에서 UI 작업에 적용되는 정책을 결정합니다. UI ID는 파일 작업(암호화, 백업 등)에 영향을 주지 않습니다. 
* **스레드 ID**: 스레드 ID는 현재 스레드에 적용되는 정책에 영향을 줍니다. 이 ID는 모든 작업, 파일 및 UI에 영향을 줍니다.

사용자가 관리되는지와 관계없이 ID를 적절하게 설정하는 것은 앱의 책임입니다.

어느 시점에서든 모든 스레드는 UI 작업 및 파일 작업에 대한 유효 ID를 가집니다. 이 ID는 적용되어야 하는 정책(있는 경우)을 결정하는 데 사용됩니다. ID가 'ID 없음'이거나 사용자가 관리되지 않는 경우 정책이 적용되지 않습니다. 
 
 

##스레드 큐
 
앱은 흔히 비동기 및 동기 작업을 스레드 큐로 디스패치합니다. SDK는 GCD(Grand Central Dispatch) 호출을 가로채고 현재 스레드 ID를 디스패치된 작업과 연결합니다. 작업이 실행되면 SDK는 일시적으로 스레드 ID를 작업과 연결된 ID로 변경하고 작업을 실행한 다음 원래 스레드 ID를 복원합니다. `NSOperationQueue`는 GCD를 기반으로 구축되므로 `NSOperations`는 `NSOperationQueue`에 추가될 때 스레드의 ID에서 실행됩니다. GCD를 사용하여 디스패치된 `NSOperations` 또는 함수는 실행되고 있을 때 현재 스레드 ID를 직접 변경하는 기능도 가집니다. 이 ID는 디스패치하는 스레드에서 상속된 ID를 재정의합니다. 

##파일 소유자
 
SDK는 로컬 파일 소유자 ID를 추적하여 적절하게 정책을 적용합니다. 파일이 만들어지거나 파일이 잘라내기 모드에서 열리면 파일 소유자가 설정됩니다. 소유자는 작업을 수행하는 스레드의 유효 파일 작업 ID로 설정됩니다. 또는 앱은 `IntuneMAMFilePolicyManager`를 사용하여 명시적으로 파일 소유자 ID를 설정할 수 있습니다. 앱은 파일 내용을 표시하기 전에 `IntuneMAMFilePolicyManager`를 사용하여 파일 소유자를 검색하고 UI ID를 설정합니다.


##공유 데이터 파일
 
앱이 관리되는 사용자와 관리되지 않는 사용자 둘 다의 데이터를 포함하는 파일을 만드는 경우 관리되는 사용자의 데이터를 암호화하는 것은 앱의 책임입니다. `IntuneMAMDataProtectionManager`의 `protect` 및 `unprotect` API를 사용하여 데이터를 암호화할 수 있습니다. `protect` 메서드는 관리되는 사용자 또는 관리되지 않는 사용자일 수 있는 ID를 허용합니다. 사용자가 관리되는 경우 데이터가 암호화됩니다. 사용자가 관리되지 않는 경우 ID를 인코딩하는 데이터에 헤더가 추가되지만 데이터는 암호화되지 않습니다.  `protectionInfo` 메서드를 사용하여 데이터의 소유자를 검색할 수 있습니다.

##공유 확장
 
앱이 공유 확장을 포함하는 경우 `IntuneMAMDataProtectionManager`의 `protectionInfoForItemProvider` 메서드를 사용하여 공유되는 항목의 소유자를 검색할 수 있습니다. 공유 항목이 파일인 경우 SDK에서 파일 소유자 설정을 처리합니다. 공유 항목이 데이터인 경우, 이 데이터가 파일에 유지되면 파일 소유자를 설정하고 이 데이터를 UI에 표시하기 전에 `setUIPolicyIdentity` API(아래에 설명됨)를 호출하는 것은 앱의 책임입니다.
 
#다중 ID 사용
 
기본적으로 앱은 단일 ID로 간주되며 프로세스 ID는 SDK에 의해 등록된 사용자로 설정됩니다. 다중 ID 지원을 사용하려면 앱의 Info.plis 파일 내에 있는 IntuneMAMSettings 사전에 이름이 'MultiIdentity'이고 값이 'YES'인 부울 설정을 추가해야 합니다. 다중 ID가 사용하도록 설정된 경우 프로세스 ID, UI ID 및 스레드 ID는 nil로 설정되며, 이러한 ID를 적절하게 설정하는 것은 앱의 책임입니다.

 
##ID 전환
 
###앱에서 시작된 ID 전환
다중 ID 앱은 시작될 때 알 수 없는, 관리되지 않는 계정으로 실행된다고 간주됩니다. 조건부 시작 UI는 실행되지 않으며 앱에서 정책이 적용되지 않습니다. ID를 변경해야 할 때마다 SDK에 알리는 것은 앱의 책임입니다. 일반적으로 이러한 상황은 앱이 특정 사용자 계정에 대한 데이터를 표시하려고 할 때마다 발생합니다.

사용자가 문서, 사서함 또는 전자 필기장의 탭을 열려고 하는 경우를 예로 들 수 있습니다. 앱은 파일, 사서함 또는 탭이 실제로 열리기 전에 SDK에 알려야 합니다. 이 작업은 `IntuneMAMPolicyManager`의 `setUIPolicyIdentity` API를 통해 수행됩니다. 이 API는 사용자가 관리되는지와 관계없이 호출되어야 합니다. 사용자가 관리되는 경우 SDK는 조건부 시작 검사(탈옥 검색, PIN, 인증 등)를 수행합니다. ID 전환 결과는 완료 처리기를 통해 비동기적으로 앱에 반환됩니다. 앱은 성공 결과 코드가 반환될 때까지 문서, 사서함, 탭 등을 여는 작업을 연기해야 합니다. ID 전환에 실패하는 경우 앱은 작업을 취소해야 합니다. 

###SDK에서 시작된 ID 전환
SDK가 앱에 특정 ID로의 전환을 요청해야 하는 경우가 있습니다. 다중 ID 앱은 `IntuneMAMPolicyDelegate`에 이 요청을 처리하기 위한 `identitySwitchRequired` 메서드를 구현해야 합니다. 이 메서드가 호출되면 앱은 지정된 ID로의 전환 요청을 처리할 수 있는 경우 `IntuneMAMAddIdentityResultSuccess`를 완료 처리기에 전달해야 합니다. 앱이 ID 전환을 처리할 수 없는 경우 `IntuneMAMAddIdentityResultFailed`를 완료 처리기에 전달해야 합니다. 앱은 이 호출에 대한 응답으로 `setUIPolicyIdentity`를 호출할 필요는 없습니다. SDK가 앱이 관리되지 않는 사용자 계정으로 전환하도록 요구하는 경우 빈 문자열이 `identitySwitchRequired` 호출에 전달됩니다. 
 
###선택적 초기화
앱이 선택적으로 초기화된 경우 SDK는 `IntuneMAMPolicyDelegate`의 `wipeDataForAccount` 메서드를 호출합니다. 지정된 사용자의 계정 및 해당 계정과 연결된 모든 데이터를 제거하는 것은 앱의 책임입니다. SDK는 사용자가 소유한 모든 파일을 제거할 수 있으며, 앱이 `wipeDataForAccount` 호출에서 "FALSE"를 반환하는 경우 이렇게 합니다. 이 메서드는 백그라운드 스레드에서 호출되며 앱은 사용자에 대한 모든 데이터가 제거될 때까지 반환되지 않습니다(앱이 "FALSE"를 반환하는 경우의 파일 제외).

# Xcode에서 Intune 앱 SDK 디버그

Microsoft Intune을 사용하여 MAM 지원 앱을 수동으로 테스트하기 전에 Xcode에서 **Settings.bundle** 파일을 사용할 수 있습니다. 그러면 Intune에 연결하지 않고도 테스트 정책을 설정할 수 있습니다. 사용하도록 설정하려면

* 프로젝트에서 최상위 폴더를 마우스 오른쪽 단추로 클릭하여 Settings.bundle 파일을 추가합니다. 메뉴에서 "추가 -> 새 파일"을 선택합니다. "리소스" 아래에서 추가할 "설정 번들" 템플릿을 선택합니다.

* 디버그 빌드에서만 MAMDebugSettings.plist를 Settings.bundle에 복사합니다.

* Root.plist(Settings.bundle에 있음)에서 "Type" = Child Pane 및 "FileName" = MAMDebugSettings의 기본 설정을 추가합니다.

* **설정 -> Your-App-Name**에서 "테스트 정책 사용"을 설정합니다.

* (Xcode 내부 또는 외부에서) 앱을 시작합니다. 

* **설정 -> Your-App-Name -> 테스트 정책 사용**에서 정책(예: "PIN")을 설정합니다.

* (Xcode 내부 또는 외부에서) 앱을 시작합니다. PIN이 예상대로 작동하는지 확인합니다.

> [!NOTE]
> 이제 **설정 -> Your-App-Name -> 테스트 정책 사용**을 통해 설정을 사용하도록 설정하고 전환할 수 있습니다.

# 권장되는 iOS 모범 사례

다음은 iOS용으로 개발할 때 권장되는 몇 가지 모범 사례입니다.

iOS 파일 시스템은 대/소문자를 구분합니다. `libIntuneMAM.a` 및 `IntuneMAMResources.bundle`과 같은 파일 이름에 대/소문자가 올바른지 확인합니다.

Xcode에서 `libIntuneMAM.a`를 찾는 데 문제가 있는 경우 링커 검색 경로에 이 라이브러리 경로를 추가하면 문제를 해결할 수 있습니다.



##FAQ 

 **내 응용 프로그램의 모든 사용자를 MAM 서비스에 등록해야 하나요?**

아니요.  실제로 회사 또는 학교 계정만 Intune 앱 SDK에 등록하면 됩니다.  계정이 회사 또는 학교 컨텍스트에서 사용되는지를 결정하는 것은 앱의 책임입니다.   
 
**응용 프로그램에 이미 로그인한 사용자의 경우는 어떤가요?  등록해야 하나요?** 

사용자가 인증된 후 사용자를 등록하는 것은 응용 프로그램의 책임이지만, 응용 프로그램에 MDM이 없는 MAM 기능이 있기 전에 제공되었을 수 있는 모든 기존 계정을 등록하는 것도 응용 프로그램의 책임입니다.   


이렇게 하려면 응용 프로그램이 `registeredAccounts:` 메서드를 사용해야 합니다.  이 메서드는 등록된 모든 계정을 포함하는 NSDictionary를 Intune MAM 서비스에 반환합니다.  응용 프로그램의 모든 기존 계정이 목록에 없는 경우 응용 프로그램은 `registerAndEnrollAccount:`을 통해 해당 계정을 등록해야 합니다. 


 

**SDK가 등록을 다시 시도하는 빈도는 어느 정도인가요?** 

SDK는 이전에 실패한 모든 등록을 24시간 간격으로 자동으로 다시 시도합니다.  SDK는 사용자의 조직에서 사용자가 응용 프로그램에 로그인한 후 MAM을 사용하도록 설정한 경우 사용자가 등록되고 정책을 수신하도록 하기 위해 이렇게 합니다. 

SDK는 사용자가 응용 프로그램을 등록했음을 감지하면 다시 시도를 중지합니다.  어느 시점에서든 1명의 사용자만 하나의 응용 프로그램을 등록할 수 있기 때문입니다. 사용자가 등록 취소된 경우 다시 시도는 같은 24시간 간격으로 다시 시작됩니다. 


 
**사용자를 등록 취소해야 하는 이유는 무엇인가요?** 

SDK는 백그라운드에서 주기적으로 다음 작업을 수행합니다.

 - 응용 프로그램이 아직 등록되지 않은 경우 SDK는 24시간마다 모든 등록된 계정을 등록하려고 시도합니다. 
 - 응용 프로그램이 등록된 경우 SDK는 8시간마다 MAM 정책 업데이트를 확인합니다. 

사용자를 등록 취소하면 사용자가 더 이상 응용 프로그램을 사용하지 않으며 해당 사용자 계정에 대한 위의 주기적 이벤트를 중지할 수 있음이 SDK에 통지됩니다.  또한 등록 취소하고 필요한 경우 선택적 초기화를 수행하라고 앱을 트리거합니다. 

**등록 취소 메서드에서 doWipe 플래그를 true로 설정해야 하나요?** 사용자가 응용 프로그램에서 로그아웃하기 전에 이 메서드를 호출해야 합니다.  로그아웃 진행 과정의 일부로 사용자의 데이터가 응용 프로그램에서 삭제되면 `doWipe`를 false로 설정할 수 있습니다.  그러나 응용 프로그램이 실제로 사용자의 데이터를 제거하지 않는 경우 SDK가 수동으로 데이터 자체를 삭제할 수 있도록 이 플래그를 true로 설정해야 합니다. 

**응용 프로그램을 등록 취소할 수 있는 다른 방법이 있나요?** 예, IT 관리자는 응용 프로그램에 선택적 초기화 명령을 보내 사용자가 등록 취소되고 사용자의 데이터가 초기화되도록 할 수 있습니다.  SDK는 이 시나리오를 자동으로 처리하고 등록 취소 대리자 메서드를 통해 알림을 보냅니다. 

#앱 스토어에 앱 제출
Intune 앱 SDK의 정적 라이브러리 및 프레임워크 빌드는 모두 범용 이진 파일입니다. 즉, 모든 장치 및 시뮬레이터 아키텍처에 대한 코드를 포함합니다. Apple은 앱이 시뮬레이터 코드를 포함한 경우 앱 스토어에 제출된 앱을 거부합니다. 장치 전용 빌드의 정적 라이브러리에 대해 컴파일할 때 링커에서 시뮬레이터 코드를 자동으로 제거합니다.

앱에서 Intune 앱 SDK의 **프레임워크 빌드**를 사용하는 경우 앱을 앱 스토어에 제출하기 전에 수동으로 범용 프레임워크에서 시뮬레이터 아키텍처를 제거해야 합니다. 아래 지침은 이렇게 하는 데 도움이 됩니다.

1. 데스크톱에 `IntuneMAM.framework`가 있는지 확인합니다.
2. 다음 명령을 실행합니다.
    
    ```
    lipo ~/Desktop/IntuneMAM.framework/IntuneMAM -remove i386 -remove x86_64 -output ~/Desktop/IntuneMAM.device_only
    ```
    첫 번째 명령은 프레임워크의 dylib에서 시뮬레이터 아키텍처를 제거합니다.
    ```
    cp ~/Desktop/IntuneMAM.device_only ~/Desktop/IntuneMAM.framework/IntuneMAM 
    ```
    두 번째 명령은 장치 전용 dylib를 프레임워크 디렉터리에 다시 복사합니다.



<!--HONumber=Sep16_HO4-->


