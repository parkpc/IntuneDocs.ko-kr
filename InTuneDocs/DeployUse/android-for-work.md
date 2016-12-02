---
title: "Android for Work 정보 | Microsoft Intune"
description: "Intune에서는 사용자가 업무용 Android 장치를 사용할 때 추가 관리 기능과 개인 정보를 제공하기 위해 Android for Work을 관리합니다."
keywords: 
author: nathbarn
manager: angrobe
ms.date: 11/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: aa0002d9-f5a0-466e-98ac-3970cb77e3a2
translationtype: Human Translation
ms.sourcegitcommit: 83914246bde673b188ca3f7d9cf50b4d0de2edd4
ms.openlocfilehash: 127db326fc96625c719b8136964bae014a904b3d


---

# <a name="manage-android-for-work-devices-with-intune"></a>Intune에서 Android for Work 장치 관리

Android for Work은 일련의 Android 장치 기능 및 서비스입니다. 이러한 기능과 서비스는 사용자가 업무용 Android 장치를 사용할 때 추가 관리 기능과 개인 정보를 제공합니다. Intune을 통해 앱과 회사 리소스를 Android for Work 장치에 배포하여 회사 및 개인 정보가 구분되도록 할 수 있습니다. 성공적으로 배포된 경우 앱과 앱이 액세스하는 데이터는 장치의 Android for Work 환경 내에서만 유지됩니다.

[!INCLUDE[wit_nextref](../includes/afw_rollout_disclaimer.md)]

## <a name="supported-devices"></a>지원되는 장치

대부분 관리 기능은 최신 Android 운영 체제에 포함된 기능에 의존하기 때문에 Android for Work에는 최신 Android 하드웨어가 필요합니다. Android for Work은 현재 Android 5.0 Lollipop 이상을 실행하고 작업 프로필을 지원하는 장치에서 지원됩니다. Android for Work을 기본적으로 지원하지 않는 장치의 경우 기존 Android 관리를 계속 사용할 수 있습니다. [Android for Work 요구 사항](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012)에 대해 자세히 알아보세요.

## <a name="onboarding"></a>온보딩

Android for Work 장치를 등록하기 전에 일부 온보딩 단계를 완료해야 합니다. 이러한 단계는 Android for Work 앱 배포 및 관리 프로세스의 필수적인 부분인 Google의 Play for Work 서비스와 Intune 테넌트 간에 연결을 설정합니다. [Android for Work 등록 사용](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-android-for-work)에 대해 자세히 알아보세요.

## <a name="work-profile-management"></a>회사 프로필 관리

Intune에서 Android for Work 장치를 관리할 경우 전체 장치를 관리하는 것이 아닙니다. 관리 기능은 등록하는 동안 만들어진 회사 프로필에만 영향을 줍니다. Intune을 통해 장치에 배포되는 앱은 회사 프로필에 포함됩니다. 회사 프로필의 앱 아이콘에는 주황색 서류 가방이 표시됩니다. 이 표시로 장치에서 회사 앱과 개인 앱을 구별합니다. 장치의 Android for Work 부분에 포함되지 않은 모든 Android 앱과 데이터는 개인용으로 유지되고 최종 사용자가 관리합니다. 사용자는 선택한 앱을 장치에 개인용으로 설치할 수 있지만, 관리자는 회사 프로필로 범위가 지정된 작업을 관리하고 모니터링할 수 있습니다.

## <a name="app-publishing-and-distribution"></a>앱 게시 및 배포

Google Play for Work 서비스는 앱 배포 및 관리의 필수적인 부분입니다. 회사 프로필로 Android for Work 장치에 배포된 모든 앱은 Play for Work에서 제공됩니다. Play 스토어에서 앱을 관리하고 배포하려면 Intune 관리자로 Play for Work 웹 사이트에 로그인하고 Intune 테넌트용 앱을 승인합니다. 이러한 앱은 Intune 콘솔에 동기화되고, 나중에 이 콘솔에서 Intune을 통해 앱을 배포하고 관리할 수 있습니다. 조직에서 개발한 LOB(기간 업무) 앱은 Google의 Android 앱 게시 콘솔을 사용하여 Play for Work에 게시해야 합니다. 조직에 대한 액세스를 제한하려면 Android 앱 게시 콘솔에서 기간 업무 앱을 구성해야 합니다.

앱은 사용자 조작 없이, 사용자가 **알 수 없는 소스에서의 설치**를 허용할 필요 없이 설치됩니다. 선택적 앱이나 사용 가능한 앱을 찾아보고 설치하기 위해 사용자는 장치에서 Play 스토어 앱에 회사 배지를 달았습니다. [Android for Work용 앱 배포](https://docs.microsoft.com/en-us/intune/deploy-use/android-for-work-apps)에 대해 자세히 알아보세요.

## <a name="app-configuration"></a>앱 구성

Android for Work은 앱 구성 값을 지원되는 앱에 배포하기 위한 인프라를 제공합니다. 업무용 앱의 구성 값을 지정하면 사용자가 앱을 처음 시작할 때 구성 값이 제대로 설정됩니다. 앱 구성을 지원하려면 앱 개발자가 특별히 관리되는 구성 값을 지원하도록 Android 앱을 만들어야 합니다. 이렇게 되면 Intune을 사용하여 이러한 구성 설정을 지정하고 적용할 수 있습니다. [Android for Work 앱 구성 설정](afw-app-configuration-policy.md)에 대해 자세히 알아보세요.

## <a name="email-configuration"></a>메일 구성

Android for Work는 iOS에서 제공되는 것과 같은 네이티브 메일 앱이나 기본 메일 프로필을 제공하지 않습니다. 대신, 앱 구성 설정을 지원하는 앱에 해당 설정을 적용하여 메일 구성을 설정할 수 있습니다. Gmail 및 Nine Work은 Android for Work 앱 구성이 포함된 구성을 지원하는 Play 스토어의 두 가지 EAS(Exchange ActiveSync) 클라이언트 앱입니다.

Intune은 Gmail 및 Nine Work 앱에 대한 구성 템플릿을 제공합니다. 앱 구성 프로필을 지원하는 기타 메일 앱은 모바일 앱 구성 정책을 통해 구성할 수 있습니다.

Android for Work 장치에 EAS 조건부 액세스를 사용 중이면 Gmail 또는 Nine Work 메일 앱을 사용해야 합니다. Android용 Microsoft Outlook 앱이나 ADAL을 통해 최신 인증을 사용하는 기타 메일 앱도 지원됩니다. [회사 메일에 대한 메일 프로필](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md)에 대해 자세히 알아보세요.

## <a name="mobile-app-management-policies"></a>모바일 앱 관리 정책

MAM(모바일 응용 프로그램 관리)이 사용되는 앱에 적용되는 제한 정책은 회사 프로필 및 개인 프로필에서 완벽하게 지원됩니다. Android 앱 게시 콘솔(https://play.google.com/apps/publish)에 기간 업무 앱을 게시할 수 있습니다. 이 콘솔에는 앱을 조직에 비공개로 설정하는 옵션이 포함됩니다. [준수 정책 설정](afw-compliance-policy-settings-in-microsoft-intune.md)에 대해 자세히 알아보세요. 자세한 내용은 [Microsoft Intune에서 모바일 앱 관리 정책을 사용하여 앱 데이터 보호](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)를 참조하세요.

## <a name="vpn-profiles"></a>VPN 프로필

VPN 지원은 Android VPN 프로필과 비슷합니다. 동일한 VPN 공급자와 기본 구성 옵션을 사용할 수 있습니다. 그러나 두 가지 주요 차이점도 있습니다.

1.  **회사 프로필 범위 VPN** – VPN 연결은 회사 프로필에 배포된 앱으로만 범위가 지정됩니다. Android for Work 관리되는 앱만 VPN 연결을 사용할 수 있습니다. 장치의 개인 앱은 관리되는 VPN 연결을 사용할 수 없습니다.

2.  **앱별 VPN** – VPN 공급자가 앱별 VPN에 대한 구성을 지원하고 Android for Work 앱 구성 프로필을 통해 앱별 VPN을 구성하는 기능을 제공할 경우 Intune에서 앱별 VPN을 구성할 수 있습니다. VPN 공급자에게 문의하여 이 기능을 지원하는지 확인하세요. [VPN 연결 프로필](vpn-connections-in-microsoft-intune.md)에 대해 자세히 알아보세요.

## <a name="certificate-profiles"></a>인증서 프로필

기존 Android 관리에 사용할 수 있는 것과 같은 인증서 프로필 구성 옵션을 Android for Work 장치에서 사용할 수 있습니다. Android for Work에서는 고급 인증서 관리 API를 제공합니다. 고급 인증서 관리는 다음 기능을 제공합니다.

1.  인증서 배포가 자동으로 매끄럽게 수행되도록 합니다.

2.  Intune에서 장치가 사용 중지되고 회사 프로필이 제거될 경우 배포된 인증서가 완전히 제거되도록 합니다.

3.  관리 서비스를 통해 IT 부서에서 인증서를 배포 및 구성했음을 사용자에게 알리는 향상된 메시지를 제공합니다.

[인증서 프로필](secure-resource-access-with-certificate-profiles.md)에 대해 자세히 알아보세요.

## <a name="wi-fi-profiles"></a>Wi-Fi 프로필

Intune에서 장치가 사용 중지되고 회사 프로필이 삭제될 경우 Android for Work에서 관리되는 Wi-Fi 프로필도 제거됩니다. [Wi-Fi 프로필](wi-fi-connections-in-microsoft-intune.md)에 대해 자세히 알아보세요.

## <a name="next-steps"></a>다음 단계
[Android for Work 등록 사용](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-android-for-work)
[Android for Work용 앱 배포](https://docs.microsoft.com/en-us/intune/deploy-use/android-for-work-apps)



<!--HONumber=Nov16_HO5-->


