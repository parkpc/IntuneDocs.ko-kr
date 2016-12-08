---
title: "새로운 기능 | Microsoft Intune"
description: "이번 달의 새로운 소식과 Microsoft Intune의 이전 릴리스 확인"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 8ef3b7e4eec5a520c93fb3f70c8e5b6ee7d2c3aa
ms.openlocfilehash: e0b0c7eb3ddc07f05fc0c2e4caa6726ed052c9d8


---
# <a name="whats-new-in-microsoft-intune---november-2016"></a>Microsoft Intune의 새로운 기능 - 2016년 11월
이번 Microsoft Intune 릴리스의 새로운 기능에 대해 알아봅니다. 이전 릴리스에 대한 정보뿐만 아니라 계획을 수립해야 하는 예정된 변경에 대해서도 알아볼 수 있습니다.

> [!Note]
> 최종적으로는 이 모든 기능이 하이브리드 고객 배포(Intune과 Configuration Manager )용으로 지원될 예정입니다. 새로운 하이브리드 기능에 대한 자세한 내용은 [hybrid What’s New page](https://docs.microsoft.com/en-us/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management)(하이브리드 새로운 기능 페이지)를 참조하세요.

## <a name="new-capabilities"></a>새로운 기능

<!--### View App States for All Platforms in Real Time
App installation status is now shown in real-time in the console. When you previously deployed an app, you had to wait for a targeted device to report back before the app install status was displayed in the Intune console.

### Streamline iOS App Management for your End Users
Intune can now automatically take over management of the previously installed app and no end user action is required.

Previously, if the end user of an enrolled iOS device installed an app from the App Store before you deployed that same app with a deployment action of __Available__, then the end user had to:

1. Open the __Company Portal__.
2. Select the app.
3. Tap __Install__ to enable Intune to take over management of the app.-->

__Windows 10 장치에 사용할 수 있는 새로운 Microsoft Intune 회사 포털__ Microsoft는 새로운 [Windows 10 장치용 Microsoft Intune 회사 포털 앱](https://www.microsoft.com/store/apps/9wzdncrfj3pz)을 출시했습니다. 이 앱은 새로운 Windows 10 유니버셜 형식을 활용하고 있으며, 현재 사용 중인 모든 기능을 계속 사용할 수 있게 하면서 사용자에게 앱의 업데이트된 사용자 환경과 모든 Windows 10 장치, PC 및 모바일 유사 장치에 걸쳐 동일한 환경을 제공합니다.

새 앱을 사용하면 사용자가 Windows 10 장치에서 SSO(Single Sign-On) 및 인증서 기반 인증과 같은 추가적인 플랫폼 기능도 활용할 수 있습니다. 이 앱은 기존 Windows 8.1 회사 포털과 Windows Phone 8.1 회사 포털에 대한 업그레이드로서 Windows 스토어에서 설치해 사용할 수 있습니다. 자세한 내용은 [aka.ms/intunecp_universalapp](http://aka.ms/intunecp_universalapp)를 참조하세요.

<!--### Support for Windows Store for Business Apps Being Deployed as Available
You can now deploy apps you synchronized from the Windows Store for Business (WSfB) with a deployment action of __Available__ or __Required__. After syncing WSfB apps into Intune, administrators will be able to target those apps as available installs to groups of users. End users will see the deployed WSfB apps as available for install in the Universal Company Portal, where they can choose whether they would like to acquire the apps.

### Conditional Access for MAM with SharePoint Online

You can block apps that are not supported by Intune mobile app management (MAM) policies from accessing SharePoint online.  You can get started in Intune mobile app management via the Azure portal. Look for the  Conditional Access section in the “Settings” blade which now includes the option for SharePoint online.-->

> [!IMPORTANT]

> __Intune 및 Android for Work에 대한 업데이트__

> __필수__ 작업을 통해 Android for Work 앱을 배포할 수 있는 반면, Intune 그룹이 새 Azure AD 그룹 환경으로 마이그레이션된 경우에는 앱을 __사용 가능__으로 배포할 수 있습니다.

### <a name="intune-app-sdk-for-cordova-plugin-now-supports-mam-without-enrollment"></a>Intune 앱 SDK Cordova 플러그 인을 통해 별도의 등록 없이 MAM 사용
앱 개발자는 Cordova용 Intune 앱 SDK 플러그 인을 사용하여 Cordova 기반 Android 및 iOS용 앱에 장치를 등록하지 않고도 MAM 기능을 설정할 수 있습니다. Cordova용 Intune 앱 SDK 플러그 인은 [여기](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam)에서 제공됩니다.

### <a name="intune-app-sdk-xamarin-component-now-supports-mam-without-enrollment"></a>Intune 앱 SDK Xamarin 구성 요소를 통해 별도의 등록 없이 MAM 사용
앱 개발자는 Intune 앱 SDK Xamarin 구성 요소를 사용하여 Xamarin 기반 Android 및 iOS용 앱에 장치를 등록하지 않고도 MAM 기능을 설정할 수 있습니다. Intune 앱 SDK Xamarin 구성 요소는 [여기](https://github.com/msintuneappsdk/intune-app-sdk-xamarin)에서 제공됩니다.

## <a name="notices"></a>알림

### <a name="symantec-signing-certificate-no-longer-requires-signed-windows-phone-8-company-portal-for-upload"></a>이제 Symantec 서명 인증서를 로드할 때 Windows Phone 8 회사 포털이 필요하지 않음
Symantec 서명 인증서를 업로드할 때 서명된 Windows Phone 8 회사 포털 앱이 필요하지 않습니다. 인증서는 개별적으로 업로드할 수 있습니다.

## <a name="deprecations"></a>지원 중단

### <a name="support-for-the-windows-phone-8-company-portal"></a>Windows Phone 8 회사 포털에 대한 지원
이제 Windows Phone 8 회사 포털을 지원하지 않습니다. Windows Phone 8 및 WinRT 플랫폼 지원이 2016년 10월에 중단되었습니다. Windows 8 회사 포털 지원도 2016년 10월에 중단되었습니다.


### <a name="see-also"></a>참고 항목
* [Microsoft Intune 블로그](http://go.microsoft.com/fwlink/?LinkID=273882)
* [클라우드 플랫폼 로드맵](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [이전 Intune 릴리스](whats-new-archive.md)



<!--HONumber=Dec16_HO1-->


