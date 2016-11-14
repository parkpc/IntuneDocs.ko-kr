---
title: "새로운 기능 | Microsoft Intune"
description: "이번 달의 새로운 소식과 Microsoft Intune의 이전 릴리스 확인"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 503719953031bf5079b2bf5bc84a0497d708f79a
ms.openlocfilehash: 730809e0841a248b90f5fe157f2c6338bfd32b2d


---
# Microsoft Intune의 새로운 기능 -- 2016 10월
이번 Microsoft Intune 릴리스의 새로운 기능에 대해 알아봅니다. 이전 릴리스에 대한 정보뿐만 아니라 계획을 수립해야 하는 예정된 변경에 대해서도 알아볼 수 있습니다.

최종적으로는 이 모든 기능이 하이브리드 고객 배포(Intune과 Configuration Manager )용으로 지원될 예정입니다. 새로운 하이브리드 기능에 대한 자세한 내용은 [hybrid What’s New page](https://technet.microsoft.com/library/mt718155.aspx)(하이브리드 새로운 기능 페이지)를 참조하세요.
<!---@Barry, the above blurb stays in each version, but make sure Tyler signs off each time. Also, remember to set the ms.date in the metadata to the sprint release. --->

## 새로운 기능

### 모바일 응용 프로그램 관리용 조건부 액세스
Exchange Online에 대한 액세스를 제한하여 Outlook과 같이 Intune 모바일 응용 프로그램 정책을 지원하는 앱에서만 액세스하도록 할 수 있습니다. [이 새로운 기능](/intune/deploy-use/allow-policy-managed-apps-access-to-o365)은 Intune MAM(모바일 앱 관리) 정책과 완벽히 쌍을 이루어 기본 제공 메일 클라이언트나 Intune MAM 정책을 사용하여 구성되지 않은 기타 앱에 대한 액세스를 차단할 수 있습니다. 따라서 사용자는 Intune MAM을 사용하여 보호할 수 있는 앱에서 조직 데이터를 액세스하게 됩니다. Intune 모바일 앱 관리는 Azure portal을 통해 시작할 수 있습니다. "설정" 블레이드에서 새 조건부 액세스 섹션을 찾아보세요.

### Windows PC에 대한 조건부 액세스
이제 Intune 관리 콘솔을 통해 Windows PC가 [Exchange Online](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune) 및 [SharePoint Online](/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune)에 액세스하지 못하도록 하는 조건부 액세스 정책을 만들 수 있습니다. 또한 Office 데스크톱 및 유니버설 응용 프로그램에 대한 액세스를 차단하기 위한 조건부 액세스 정책을 만들 수 있습니다.

### Android for Work 지원
Intune은 이제 Android for Work 프로그램의 일부입니다. Microsoft는 이번 달부터 intune에서 Android for Work 기능을 지원한다고 발표할 것입니다.
[Intune의 Android for Work 지원에 대한 Microsoft 공지 사항 읽기](https://blogs.technet.microsoft.com/enterprisemobility/2016/09/12/microsoft-intune-support-for-android-for-work/)를 참조하세요.

다음 Intune 항목은 새롭거나 업데이트된 Android for Work 정보입니다.

IT 전문가용:
- [Android for Work 설정](/intune/deploy-use/set-up-android-for-work)
<!--- [Nathan Bigman's resource access topics]()-->
- [Intune을 사용하여 Exchange Online 및 새 Exchange Online Dedicated에 대한 메일 액세스 제한](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)
- [Intune을 사용하여 Exchange 온-프레미스 및 레거시 Exchange Online Dedicated에 대한 메일 액세스 제한](/intune/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)
- [Android for Work 규정 준수 정책 설정](/intune/deploy-use/afw-compliance-policy-settings-in-microsoft-intune)
- [Android for Work 앱을 배포하는 방법](/intune/deploy-use/android-for-work-apps)
- [모바일 앱 구성 정책을 사용하여 Android for Work 앱 구성](/intune/deploy-use/afw-app-configuration-policy)
- [Android for Work 정책 설정](/intune/deploy-use/android-for-work-policy-settings-in-microsoft-intune)

최종 사용자:
- [업무용 프로필을 만들면 어떻게 되나요?](/intune/enduser/what-happens-when-you-create-a-work-profile-android)
- [업무용 프로필을 만들고 Intune에서 장치 등록](/intune/enduser/create-a-work-profile-and-enroll-your-device-in-intune-android)

### iOS 장치를 보호하기 위한 Lookout 통합
10월에 Microsoft는 맬웨어, 위험한 앱 등을 감지한 iOS 모바일 장치를 보호하기 위해 Lookout의 모바일 위협 방지 솔루션과 통합합니다. Lookout의 솔루션을 통해 위협 수준을 결정할 수 있고, 이 수준은 구성이 가능합니다. Lookout의 위협 평가를 기준으로 장치 준수를 결정하는 준수 정책 규칙을 Intune에서 만들 수 있습니다. 조건부 액세스 정책을 사용하여 장치 준수 상태에 따라 회사 리소스에 대한 액세스를 허용하거나 차단할 수 있습니다.

비준수 iOS 장치의 최종 사용자는 표시되는 등록 요청 메시지에서 회사 데이터에 대한 액세스 권한을 얻기 위해 Lookout for Work 앱을 장치에 설치하여 활성화하고 이 앱에 보고된 위협을 해결하도록 요청받습니다. [Lookout for Work 앱 구성 및 배포](/intune/deploy-use/configure-and-deploy-lookout-for-work-apps) 방법을 알아 봅니다.
<!--TFS 1319493-->

<!--### New Microsoft Intune Company Portal available for Windows 10 devices
Microsoft is releasing a new [Microsoft Intune Company Portal for Windows 10 devices](https://go.microsoft.com/fwlink/?linkid=830663). This app, which leverages the new Windows 10 Universal format, will provide the user with an updated user experience within the app and identical experiences across all Windows 10 devices, PC and Mobile alike, while still enabling all the same functionality that they are using today.

The new app will also allow users to leverage additional platform features like single sign-on (SSO) and certificate-based authentication on Windows 10 devices. The app will be made available as an upgrade to the existing Windows 8.1 Company Portal and Windows Phone 8.1 Company Portal installs from the Windows Store.-->

### Android용 Intune 앱 래핑 도구
Intune 앱 래핑 도구를 사용하여 Intune 모바일 앱에서 MAM(모바일 응용 프로그램 관리) 정책을 사용할 수 있게 할 수 있습니다. 이제 장치 등록을 요구하지 않는 Intune MAM 정책이 지원됩니다.

### MAM 정책으로 관리되는 앱에서 인쇄 관리
이제는 MAM 정책을 포함한 앱에서 회사 데이터를 인쇄할 없습니다. 이 설정은 [Azure 포털](/Intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune)에서 사용할 수 있으며 [iOS](/Intune/deploy-use/ios-mam-policy-settings) 및 [Android](/Intune/deploy-use/android-mam-policy-settings) 장치에서 모두 지원됩니다.
<!--TFS 1014328-->

## 알림

### Intune과 Android Samsung KNOX의 호환성
Intune에서는 특정 모델의 삼성 Galaxy Ace 전화를 Samsung KNOX 장치로 관리할 수 없습니다. 대신 Intune에서 이러한 장치를 등록하면 해당 장치가 표준 Android 장치로 관리됩니다.

영향 받는 모델 번호는 다음과 같습니다.

* SM-G313HU
* SM-G313HY
* SM-G313M
* SM-G313MY
* SM-G313U

관리자와 최종 사용자는 더 이상 조치를 취할 필요가 없습니다. 자세한 내용은 [Samsung KNOX](https://www.samsungknox.com) 웹 사이트를 참조하세요.

### Windows 8용 회사 포털 앱은 사용되지 않으며, Windows Phone 8 및 Windows RT 플랫폼도 사용되지 않을 것입니다.
2016년 10월부터 Microsoft Intune에서는 Windows 8 회사 포털을 더 이상 지원하지 않습니다. 또한 Windows Phone 8 및 Windows RT 플랫폼도 지원되지 않을 것입니다. 따라서 Windows Phone 8 또는 Windows RT 장치를 등록하거나 업데이트할 수 없게 됩니다.

이미 등록된 Windows Phone 8, Windows RT 및 Windows 8 장치는 계속 관리할 수 있습니다. 서비스 중단 없이 이러한 장치에 앱을 계속 배포하려면 Windows Phone 8 및 Windows 8 장치를 Windows 8.1 및 Windows Phone 8.1로 업데이트하고 해당하는 Windows 8.1 및 Windows Phone 8.1 회사 포털 앱을 사용하세요.

2016년 11월부터 Windows Phone 8 회사 포털을 더 이상 지원하지 않습니다.
<!--TFS 1255391-->

## 향후 예정 사항

### Windows 10 장치에 사용할 수 있는 새로운 Microsoft Intune 회사 포털
Microsoft는 새로운 Windows 10 장치용 Microsoft Intune 회사 포털을 출시하고 있습니다. 이 앱은 새로운 Windows 10 유니버셜 형식을 활용하고 있으며, 현재 사용 중인 모든 기능을 계속 사용할 수 있게 하면서 사용자에게 앱의 업데이트된 사용자 환경과 모든 Windows 10 장치, PC 및 모바일 유사 장치에 걸쳐 동일한 환경을 제공합니다.

새 앱을 사용하면 사용자가 Windows 10 장치에서 SSO(Single Sign-On) 및 인증서 기반 인증과 같은 추가적인 플랫폼 기능도 활용할 수 있습니다. 이 앱은 기존 Windows 8.1 회사 포털과 Windows Phone 8.1 회사 포털에 대한 업그레이드로서 Windows 스토어에서 설치해 사용할 수 있습니다. 자세한 내용은 [aka.ms/intunecp_universalapp](http://aka.ms/intunecp_universalapp)를 참조하세요.
<!--TFS 1016502-->

### 참고 항목
* [Microsoft Intune 블로그](http://go.microsoft.com/fwlink/?LinkID=273882)
* [클라우드 플랫폼 로드맵](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [이전 Intune 릴리스](previous-intune-releases.md)



<!--HONumber=Oct16_HO3-->


