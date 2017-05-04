---
title: "Intune 온보딩 프로세스 | Microsoft 문서"
description: "이 문서에는 Intune 클라우드 전용 솔루션을 환경에 온보딩할 때 고려해야 하는 유용한 모든 세부 정보가 포함되어 있습니다."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ac7bd764-5365-4920-8fd0-ea57d5ebe039
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: e10453155343bb7fd91a4fd3874d393ef78d0b1a
ms.openlocfilehash: 307a4aec1d9b86a92bde9114fdfd45846a82a2f3
ms.lasthandoff: 04/25/2017


---

# <a name="intune-implementation"></a>Intune 구현

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

온보딩 단계에서, 프로덕션 환경에 Intune을 구현합니다. 구현 프로세스는 이 가이드의 이전 섹션에서 검토한 [사용 사례 요구 사항](section-3-determine-use-case-requirements.md)에 따라 Intune 및 외부 종속성(필요한 경우)을 설정하고 구성하는 과정으로 구성됩니다.

다음 섹션에서는 요구 사항 및 대략적인 작업이 포함된 Intune 구현 프로세스의 개요를 제공합니다.

>[!TIP]
> Intune 구현 프로세스에 대한 자세한 내용은 [추가 리소스](additional-resources.md)에서 확인하세요.

## <a name="intune-requirements"></a>Intune 요구 사항

주요 Intune 독립 실행형 요구 사항이 아래에 나와 있습니다.

-   EMS/Intune 구독

-   Office 365 구독(Office 앱 및 MAM 정책 관리 앱용)

-   Apple APNs 인증서(iOS 장치 플랫폼 관리를 사용하도록 설정하기 위해)

-   Azure AD Connect(디렉터리 동기화용)

-   Intune 온-프레미스 Exchange Connector(필요한 경우 Exchange 온-프레미스용 CA에 사용하기 위해)

-   Intune Certificate Connector(필요한 경우 SCEP 인증서 배포용)

>[!TIP]
> Intune 독립 실행형 요구 사항에 대한 자세한 내용은 [여기](https://docs.microsoft.com/intune/get-started/what-to-know-before-you-start-microsoft-intune)에서 찾아볼 수 있습니다.

## <a name="intune-implementation-process"></a>Intune 구현 프로세스

### <a name="overview-of-implementation-tasks"></a>구현 작업 개요

다음에서 Intune 구현 시의 각 작업을 간략하게 보여 줍니다.

#### <a name="task-1-add-intune-subscription"></a>작업 1: Intune 구독 추가

앞의 요구 사항 섹션에서 확인했듯이 EMS 또는 Intune 구독이 필요합니다. 조직에 EMS(Enterprise Mobility + Security) 또는 Intune 구독이 없는 경우 EMS 또는 Intune 구매에 관심이 있으면 관련 Microsoft 계정 팀 또는 Microsoft에 문의하세요.

-   [Microsoft Intune을 구매하는 방법](https://www.microsoft.com/cloud-platform/microsoft-intune-pricing)에 대해 자세히 알아보세요.

#### <a name="task-2-add-office-365-subscription"></a>작업 2: Office 365 구독 추가

이 단계는 선택 사항입니다. 앞의 요구 사항 섹션에서 확인했듯이 Exchange Online을 사용하고 MAM 정책으로 Office 모바일 앱을 관리할 계획이 있는 경우 Office 365 구독이 필요합니다. 조직에 Office 365 구독이 없는 경우 Office 365 구매에 관심이 있으면 관련 Microsoft 계정 팀 또는 Microsoft에 문의하세요.

-   [Office 365 구매 방법](https://products.office.com/business/compare-office-365-for-business-plans)에 대해 자세히 알아보세요.

#### <a name="task-3-add-users-groups-in-azure-ad"></a>작업 3: Azure AD에서 사용자 그룹 추가

Intune 배포 사용 사례 시나리오 및 요구 사항에 따라 AD 또는 AAD에서 사용자 또는 보안 그룹을 추가해야 할 수 있습니다. Active Directory 또는 Azure Active Directory의 현재 사용자 및 보안 그룹을 검토하고, 해당 사용자 및 보안 그룹이 요구를 완벽하게 충족하는지 확인해야 합니다. 새 사용자 및 보안 그룹은 일반적으로 Active Directory에 추가되며 Azure AD Directory Connect를 통해 Azure Active Directory로 동기화됩니다.

-   [Intune에 사용자/그룹을 추가하는 방법](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3)에 대해 자세히 알아보세요.

#### <a name="task-4-assign-intune-and-office-365-user-licenses"></a>작업 4: Intune 및 Office 365 사용자 라이선스 할당

EMS/Intune 및 Office 365 출시 대상으로 지정될 모든 사용자에게는 할당받은 라이선스가 있어야 합니다. Office 365 관리 센터 포털에서 EMS/Intune 및 Office 365 라이선스 할당을 수행할 수 있습니다.

-   [Intune 라이선스를 할당하는 방법](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-4)에 대해 자세히 알아보세요.

#### <a name="task-5-set-mobile-device-management-authority-to-intune"></a>작업 5: Intune으로 모바일 장치 관리 기관 설정

Intune을 사용하여 장치를 설치/구성/관리/등록하려면 먼저 장치 관리 기관을 Intune으로 설정해야 합니다. 장치 관리 기관 설정 작업은 Intune 관리 포털, 관리 작업 영역에서 완료할 수 있습니다.

-   [장치 관리 기관을 설정하는 방법](https://docs.microsoft.com/intune/deploy-use/prerequisites-for-enrollment#step-2-set-mdm-authority)에 대해 자세히 알아보세요.

#### <a name="task-6-enable-device-platforms"></a>작업 6: 장치 플랫폼을 사용하도록 설정

기본적으로 Apple 장치(iOS 및 Mac)를 제외한 대부분의 장치 플랫폼을 Intune 관리 콘솔에서 사용하도록 설정할 수 있습니다. Intune에서 iOS 장치를 등록하고 관리하려면 먼저, 장치 플랫폼을 사용하도록 설정해야 합니다. iOS 장치 플랫폼을 사용하도록 설정하는 프로세스는 3단계 즉, APNs 인증서를 만들어 다운로드한 후 Intune에 APNs 인증서를 업로드하는 과정으로 구성됩니다.

-   [iOS 및 Mac 장치 관리 설정의 작동 방법](https://docs.microsoft.com/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune)에 대해 자세히 알아보세요.

#### <a name="task-7-add-and-deploy-terms-and-conditions-policies"></a>작업 7: 사용 약관 정책 추가 및 배포

Microsoft Intune은 사용 약관 정책의 추가 및 배포를 지원합니다. 사용 약관 정책의 추가 및 배포는 Intune 관리 포털, 정책 작업 영역에서 완료할 수 있습니다. 사용 약관 정책을 적절히 추가하고, Intune 배포 사용 사례 및 요구 사항에 따라 대상 그룹에 배포합니다.

-   [사용 약관 정책을 추가하고 배포하는 방법](https://docs.microsoft.com/intune/deploy-use/terms-and-condition-policy-settings-in-microsoft-intune)에 대해 자세히 알아보세요.

#### <a name="task-8-add-and-deploy-configuration-policies"></a>작업 8: 구성 정책 추가 및 배포

Microsoft Intune은 두 가지 유형의 구성 정책 즉, 일반 및 사용자 지정 구성 정책의 추가 및 배포를 지원합니다. 구성 정책의 추가 및 배포는 Intune 관리 포털, 정책 작업 영역에서 완료할 수 있습니다. 구성 정책을 적절히 추가하고, Intune 배포 사용 사례 및 요구 사항에 따라 대상 그룹에 배포합니다.

-   [구성 정책을 추가하고 배포하는 방법](https://docs.microsoft.com/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies)에 대해 자세히 알아보세요.

#### <a name="task-9-add-and-deploy-resource-profiles"></a>작업 9: 리소스 프로필 추가 및 배포

Microsoft Intune은 메일, Wi-Fi 및 VPN 프로필을 지원합니다. 프로필의 추가 및 배포는 Intune 관리 포털, 정책 작업 영역에서 완료할 수 있습니다. 메일/Wi-Fi/VPN 프로필을 적절히 추가하고, Intune 배포 사용 사례 및 요구 사항에 따라 대상 그룹에 배포합니다.

-   [Intune을 사용하여 회사 리소스에 대한 액세스 허용](https://docs.microsoft.com/intune/deploy-use/enable-access-to-company-resources-with-microsoft-intune)에 대해 자세히 알아보세요.

#### <a name="task-10-add-and-deploy-apps"></a>작업 10: 앱 추가 및 배포

Microsoft Intune은 웹, LOB 및 공용 저장소 앱의 배포를 지원합니다. 또한 MAM 정책과 연결함으로써 Intune SDK를 통합한 앱을 관리할 수 있습니다. 앱의 추가 및 배포는 Intune 관리 포털, 앱 작업 영역에서 완료할 수 있습니다. MAM 정책의 추가는 Intune 관리 포털, 정책 작업 영역에서 완료할 수 있습니다. 앱을 적절히 추가하고, Intune 배포 사용 사례 및 요구 사항에 따라 대상 그룹에 배포합니다.

-   [응용 프로그램 추가 및 배포](https://docs.microsoft.com/intune/deploy-use/deploy-apps)에 대해 자세히 알아보세요.

#### <a name="task-11-add-and-deploy-compliance-policies"></a>작업 11: 준수 정책 추가 및 배포

Microsoft Intune은 준수 정책을 지원합니다. 준수 정책의 추가 및 배포는 Intune 관리 포털, 정책 작업 영역에서 완료할 수 있습니다. 준수 정책을 적절히 추가하고, Intune 배포 사용 사례 및 요구 사항에 따라 대상 그룹에 배포합니다.

-   [준수 정책](https://docs.microsoft.com/intune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune)에 대해 자세히 알아보세요.

#### <a name="task-12-enable-conditional-access-policies"></a>작업 12: 조건부 액세스 정책을 사용하도록 설정

Microsoft Intune은 Exchange Online 및 온-프레미스, SharePoint Online, 비즈니스용 Skype Online 및 Dynamics CRM Online에 대한 조건부 액세스를 지원합니다. Intune 관리 포털, 정책 작업 영역에서 조건부 액세스 정책을 사용하도록 설정할 수 있습니다. [Intune 배포 사용 사례 및 요구 사항](section-3-determine-use-case-requirements.md)에 따라 적절히 조건부 액세스를 사용하도록 설정하고 구성합니다.

-   [조건부 액세스](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)에 대해 자세히 알아보세요.

#### <a name="task-13-enroll-devices"></a>작업 13: 장치 등록

Intune은 iOS, Mac OS, Android, Windows 데스크톱 및 Windows 모바일 장치 플랫폼을 지원합니다. Intune 배포 사용 사례 및 요구 사항에 따라 적절히 모바일 장치 플랫폼을 등록합니다.

-   [장치를 등록하는 방법](https://docs.microsoft.com/intune/deploy-use/enroll-devices-in-microsoft-intune)에 대해 자세히 알아보세요.

>[!TIP]
> Intune 구현 프로세스에 대한 자세한 내용은 이 [Microsoft Virtual Academy Intune 세션 모듈](https://mva.microsoft.com/training-courses/deploying-microsoft-enterprise-mobility-suite-16408?l=PPWNoZxvD_1404778676)에서 확인해 보세요.

## <a name="next-section"></a>다음 섹션

다음 섹션에서는 [Intune 배포 테스트 및 유효성 검사](section-9-test-and-validation.md)에 대한 지침을 제공합니다.

