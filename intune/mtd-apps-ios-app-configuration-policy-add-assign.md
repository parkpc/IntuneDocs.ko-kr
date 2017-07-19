---
title: "Intune에 MTD 앱 추가 및 할당"
titleSuffix: Intune on Azure
description: "Azure의 Intune에 MTD 앱, Microsoft Authenticator 앱 및 iOS 구성 정책 추가"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00356258-76a8-4a84-9cf5-64ceedb58e72
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7b3fb86648a86b161eadfc071bdacbfd4ea0222f
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2017
---
# <a name="add-and-assign-mobile-threat-defense-mtd-apps-with-intune"></a>Intune을 사용하여 MTD(Mobile Threat Defense) 앱 추가 및 할당

Intune을 사용하면 최종 사용자가 모바일 장치에서 위협이 식별될 때 알림을 받을 수 있도록 MTD 앱을 추가 및 배포하고 위협을 해결하기 위한 지침을 받을 수 있습니다.

iOS 장치의 경우 사용자의 ID가 Azure AD에서 확인될 수 있도록 [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to)가 필요합니다. 또한 Intune에서 사용할 MTD iOS 앱에 신호를 보내는 iOS 앱 구성 정책이 필요합니다.

> [!TIP]
> Intune 회사 포털은 사용자의 ID가 Azure AD에서 확인될 수 있도록 Android 장치에서 브로커로 작동합니다.

## <a name="before-you-begin"></a>시작하기 전에

-   [Azure Portal](https://portal.azure.com/)에서 아래 단계를 완료해야 합니다.

-   다음 프로세스에 대해 잘 알고 있어야 합니다.

    -   [Intune에 앱 추가](apps-add.md)

    -   [Intune에 iOS 앱 구성 정책 추가](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)

    -   [Intune을 사용하여 앱 할당](https://docs.microsoft.com/intune/deploy-use/deploy-apps-in-microsoft-intune)

    -   [iOS 앱 구성 정책 추가](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)

## <a name="to-add-apps"></a>앱을 추가하려면

### <a name="skycure-app-for-android"></a>Android용 Skycure 앱

- [Microsoft Intune에 Android 스토어 앱 추가](store-apps-android.md) 지침을 참조하세요. **7단계**에서 이 [Skycure 앱 스토어 URL](https://play.google.com/store/apps/details?id=com.skycure.skycure)을 사용합니다.

### <a name="skycure-app-for-ios"></a>IOS용 Skycure 앱

- [Microsoft Intune에 iOS 스토어 앱 추가](store-apps-ios.md) 지침을 참조하세요. **앱 정보 구성** 섹션의 **5단계**에서 이 [Skycure 앱 스토어 URL](https://itunes.apple.com/us/app/skycure/id695620821?mt=8)을 사용합니다.

### <a name="microsoft-authenticator-app-for-ios"></a>iOS용 Microsoft Authenticator 앱

- [Microsoft Intune에 iOS 스토어 앱 추가](store-apps-ios.md) 지침을 참조하세요. **앱 정보 구성** 섹션의 **5단계**에서 이 [Microsoft Authenticator 앱 스토어 URL](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8)을 사용합니다.

### <a name="lookout-for-work-android-app"></a>Lookout for work Android 앱

- [Microsoft Intune에 Android 스토어 앱 추가](store-apps-android.md) 지침을 참조하세요. **7단계**에서 이 [Lookout for work Google 앱 스토어 URL](https://play.google.com/store/apps/details?id=com.lookout.enterprise)을 사용합니다.

### <a name="lookout-for-work-ios-app"></a>Lookout for Work iOS 앱

- [Microsoft Intune에 iOS 스토어 앱 추가](store-apps-ios.md) 지침을 참조하세요. **앱 정보 구성** 섹션의 **5단계**에서 이 [Lookout for Work iOS 앱 스토어 URL](https://itunes.apple.com/us/app/lookout-for-work/id997193468?mt=8)을 사용합니다.

### <a name="lookout-for-work-app-outside-the-apple-store"></a>Apple Store 외부의 Lookout for Work 앱

Lookout for Work iOS 앱에 다시 서명해야 합니다. Lookout에서는 iOS App Store 외부에 Lookout for Work iOS 앱을 배포합니다. 앱을 배포하기 전에 iOS 엔터프라이즈 개발자 인증서를 사용하여 앱에 다시 서명해야 합니다.

Lookout for Work iOS 앱에 다시 서명하는 방법에 대한 자세한 내용은 Lookout 웹 사이트에서 [Lookout for Work iOS 앱 다시 서명 프로세스](https://personal.support.lookout.com/hc/articles/114094038714)를 참조하세요.

#### <a name="enable-azure-ad-authentication-for-lookout-for-work-ios-app"></a>Lookout for Work iOS 앱에 대해 Azure AD 인증 사용

다음을 수행하여 iOS 사용자에게 Azure Active Directory 인증을 사용하도록 설정합니다.

1. [Azure Portal](https://portal.sazure.com)로 이동해서 자격 증명으로 로그인한 다음 응용 프로그램 페이지를 탐색합니다.
  
2. **Lookout for Work iOS 앱**을 **네이티브 클라이언트 응용 프로그램**으로 추가합니다.

3. **com.lookout.enterprise.yourcompanyname**을 IPA에 서명할 때 선택한 고객 번들 ID로 바꿉니다.

4.  원래 리디렉션 URI의 URL 인코드된 버전을 뒤에 추가하여 다른 리디렉션 URI(**&lt;companyportal://code/>**)를 추가합니다.

5.  **위임된 권한**을 앱에 추가합니다.

    > [!NOTE] 
    > 자세한 내용은 [Azure AD를 사용하여 네이티브 클라이언트 응용 프로그램 구성](https://azure.microsoft.com/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application)을 참조하세요.

#### <a name="add-the-lookout-for-work-ipa-file"></a>Lookout for Work ipa 파일 추가

- [Intune을 사용하여 iOS LOB 앱 추가](lob-apps-ios.md) 항목에 설명된 대로 다시 서명된 .ipa 파일을 업로드합니다. 또한 최소 OS 버전을 iOS 8.0 이상으로 설정해야 합니다.

## <a name="to-associate-the-mtd-app-with-an-ios-app-configuration-policy"></a>iOS 앱 구성 정책에 MTD 앱을 연결하려면

### <a name="for-skycure"></a>Skycure의 경우

-   Skycure 관리 콘솔에서 이전에 구성된 Azure AD 계정, 즉 Intune 클래식 콘솔에 로그인할 때 사용한 계정과 동일한 계정을 사용해야 합니다.

-   사용할 수 있는 Skycure 통합 파일이 있어야 합니다. 이 파일은 Skycure 관리 콘솔에서 이전에 다운로드한 .zip 파일로, iOS 앱 구성 정책 매개 변수가 있는 **skycure\_configuration.plist** 파일이 포함되어 있습니다.

- Skycure iOS 앱 구성 정책을 추가하려면 [iOS에 대해 Microsoft Intune 앱 구성 정책 사용](app-configuration-policies-use-ios.md) 지침을 참조하세요.
    - 8단계에서 **XML 데이터 입력** 옵션을 사용하고, **skycure_configuration.plist** 파일에서 콘텐츠를 복사한 다음 구성 정책 본문에 붙여넣습니다.

다음 위치에서 **skycure_configuration.plist** 콘텐츠를 복사할 수도 있습니다.

```
<dict>
    <key>MdmType</key>
    <string>Intune</string>
    <key>UserEmail</key>
    <string>{{userprincipalname}}</string>
</dict>

```
### <a name="for-lookout"></a>Lookout의 경우

- [iOS 앱 구성 정책 사용](app-configuration-policies-use-ios.md) 항목에 설명된 대로 iOS 앱 구성 정책을 만듭니다.

## <a name="to-assign-mtd-apps"></a>MTD 앱을 할당하려면

- [intune을 사용하여 그룹에 앱 할당](apps-deploy.md) 지침을 참조하세요.

## <a name="next-steps"></a>다음 단계

[Intune과 Skycure 통합 설정](skycure-mtd-connector-integration.md)
[Intune과 Lookout 통합 설정](lookout-mtd-connector-integration.md)
