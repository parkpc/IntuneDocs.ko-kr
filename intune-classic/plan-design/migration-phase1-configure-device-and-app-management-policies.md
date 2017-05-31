---
title: "Intune 마이그레이션 중 장치 준수 및 앱 관리 정책 구성 | Microsoft 문서"
description: "이 문서의 목적은 Intune 마이그레이션 중 장치 준수 및 앱 관리 정책을 구성하는 데 필요한 단계를 제공하는 것입니다."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0062d08e-e5b3-4f73-8b64-5ad95adbe945
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 50a8929ef31e0a322e9460f82af3ed821ade69cf
ms.contentlocale: ko-kr
ms.lasthandoff: 05/23/2017


---

# <a name="phase-1-configure-device-compliance-and-app-management-policies"></a>1단계: 장치 준수 및 앱 관리 정책 구성

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Intune으로 마이그레이션할 때 주요 목표는 모든 장치를 등록하고 해당 정책을 준수하도록 하는 것입니다. 장치 정책을 통해 회사 소유의 단일 사용자 장치를 관리할 수 있을 뿐만 아니라 키오스크, POS(Point of Sale) 컴퓨터, 강의실에서 여러 학생이 공유하는 태블릿, 사용자가 지정되지 않은 장치(iOS에만 해당) 등 공유 장치 및 개인 장치(BYOD)를 관리할 수 있습니다.

각 장치 플랫폼이 다양한 설정을 제공할 수 있지만, 다음 모바일 장치 관리 기능을 제공하여 Intune 장치 정책을 각 장치 플랫폼에 적용할 수 있습니다.

-   각 사용자가 등록하는 장치의 수를 규정합니다.

-   장치 설정(예: 장치 수준 암호화, 암호 길이, 카메라 사용)을 관리합니다.

-   앱, 메일 프로필, VPN 프로필 등을 제공합니다.

-   보안 준수 정책에 대한 장치 수준 기준을 평가합니다.

> [!IMPORTANT]
> 장치 관리 정책은 개별 장치 또는 사용자에게 직접 할당되지 않으며, 대신 사용자 그룹에 할당됩니다. 정책을 사용자 그룹에 직접 적용함으로써 사용자 장치에 적용하거나, 정책을 장치 그룹에 적용함으로써 그룹 구성원에게 적용할 수 있습니다.

## <a name="task-list-for-device-compliance-policies"></a>장치 준수 정책에 대한 작업 목록

### <a name="task-1-add-device-groups-optional"></a>작업 1: 장치 그룹 추가(선택 사항)

[Intune 클래식 포털](https://manage.microsoft.com/)에서는 사용자 ID 대신 장치 ID에 따라 다양한 관리 작업을 수행해야 할 때 장치 그룹을 만드는 기능을 제공합니다.

장치 그룹은 키오스크 장치와 같이 전용 사용자가 없는 장치 또는 교대 근무자에 의해 공유되거나 특정 위치에 할당된 장치를 관리하는 데 유용합니다.

장치 등록 전에 미리 장치 그룹을 구성하면 등록 시 장치 범주를 활용하여 장치를 자동으로 그룹화함으로써 해당 그룹의 장치 정책을 자동으로 받을 수 있습니다.

-   [장치 그룹을 추가하는 방법](/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)에 대해 알아보세요.

-   [장치 범주를 구성하는 방법](/intune-classic/deploy-use/categorize-devices-with-device-group-mapping-in-microsoft-intune)에 대해 알아보세요.

### <a name="task-2-use-resource-access-profiles-wi-fi-vpn-and-email-certificates"></a>작업 2: 리소스 액세스 프로필(Wi-Fi, VPN 및 메일 인증서) 사용

리소스 액세스 프로필은 인증서 및 등록된 장치에 대한 액세스 구성을 프로비전합니다.

앞서 MDM 요구 사항 평가 섹션에서 설명한 대로 인증서 기반 인증을 사용할 경우 VPN, Wi-Fi 및 메일 인증서를 배포하려면 [PKI 인프라를 구축](/intune-classic/deploy-use/secure-resource-access-with-certificate-profiles)해야 합니다.

#### <a name="direct-import-of-resource-access-profiles-optional"></a>리소스 액세스 프로필 직접 가져오기(선택 사항)

기존 MDM 솔루션에서 XML 형식으로 메일, Wi-Fi 및 VPN 프로필을 내보낼 수 있는 메커니즘을 제공하는 경우 iOS, Android 및 Windows 장치에 대한 사용자 지정 프로필을 만드는 데 OMA-URI를 사용함으로써 XML 파일을 활용하여 Intune으로 가져올 수 있습니다.

-   [iOS](/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune) 장치에 대한 사용자 지정 정책을 추가하는 방법을 알아보세요.

### <a name="task-3-create-and-deploy-device-configuration-profiles"></a>작업 3: 장치 구성 프로필 만들기 및 배포

장치 수준 설정을 적용할 장치 구성 프로필(예: 카메라 사용 안 함, 앱 스토어, 단일 앱 모드 구성, 홈 화면 등)을 만들어야 합니다.

- [장치 구성 프로필](https://docs.microsoft.com/intune/device-profile-create)에 대해 알아보세요.

####  <a name="direct-import-of-ios-configuration-profiles-optional"></a>iOS 구성 프로필 직접 가져오기(선택 사항)

-   **Apple Configurator iOS 프로필(iOS 7.1 이상):** 기존 MDM 솔루션에서 Apple Configurator 프로필(.mobileconfig 파일)을 사용하는 경우 Intune에서 해당 프로필을 사용자 지정 구성 정책으로 직접 가져올 수 있습니다.

-   **iOS 모바일 응용 프로그램 구성 정책:** 기존 MDM 솔루션에서 iOS 모바일 응용 프로그램 구성 정책을 사용하는 경우 해당 정책이 Apple에서 속성 목록에 대해 지정한 XML 형식을 충족하는 한 Intune에서 이 정책을 직접 가져올 수 있습니다.

- [iOS](/intune-classic/deploy-use/ios-policy-settings-in-microsoft-intune#custom-policy-settings) 사용자 지정 정책을 추가하는 방법에 대해 알아보세요.

### <a name="task-4-create-and-deploy-device-compliance-policies-optional"></a>작업 4: 장치 준수 정책 만들기 및 배포(선택 사항)

장치 준수 정책은 보안 지향 설정을 평가하고 장치가 회사 표준을 준수하는지 여부를 보여 주는 보고를 제공합니다. 장치 준수 정책은 다음과 같은 보안 지향 요인을 평가합니다.

-   PIN 길이

-   탈옥 상태

-   OS 버전

장치 준수 설정에 대한 추가 리소스를 참조하세요.

-   [장치 준수 정책](/intune-classic/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune)에 대해 알아보세요.

-   [장치 준수 정책을 만드는 방법](/intune-classic/deploy-use/create-a-device-compliance-policy-in-microsoft-intune)에 대해 알아보세요.

### <a name="task-5-publish-and-deploy-apps"></a>작업 5: 앱 게시 및 배포

Intune MDM을 사용하는 경우 앱 자동 설치를 요구하거나 회사 포털에서 앱을 사용할 수 있도록 하여 앱을 프로비전할 수 있습니다.

-   [앱을 추가하는 방법](/intune-classic/deploy-use/add-apps)에 대해 알아보세요.

-   [앱을 배포하는 방법](/intune-classic/deploy-use/deploy-apps)에 대해 알아보세요.

### <a name="task-6-enable-device-enrollment"></a>작업 6: 장치 등록 사용

등록은 장치에서 컨트롤을 프로비전하여 관리를 설정합니다.

-   [회사 소유 장치 및 사용자의 개인 장치를 등록하는 방법](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)에 대해 알아보세요.

-   [회사 소유 장치를 등록하는 방법](/intune-classic/deploy-use/manage-corporate-owned-devices)에 대해 알아보세요.

공유 또는 사용자가 없는 장치를 등록해야 하는 경우 [장치 등록 관리자 /intune-classic/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)를 사용할 수 있습니다.

## <a name="next-steps"></a>다음 단계 

[1단계: 앱 보호 정책 구성 /intune-classic/plan-design/migration-phase1-configure-app-protection-policies)

