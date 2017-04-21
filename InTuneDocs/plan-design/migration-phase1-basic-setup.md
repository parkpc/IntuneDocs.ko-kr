---
title: "Intune 기본 설정 | Microsoft 문서"
description: "이 문서의 목적은 Microsoft Intune을 설정하는 데 필요한 단계를 제공하는 것입니다."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 60cfa440-0723-4ea0-bacf-3c5d26f9a1d3
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab6d9b6b296fb4e1fb0aaa9496fede28976728dc
ms.openlocfilehash: 0fce3edb43a147491465d8a58d1a9a4f009fba55
ms.lasthandoff: 04/14/2017


---

# <a name="phase-1-basic-setup"></a>1단계: 기본 설정

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

환경을 평가했으면 Intune을 설정할 차례입니다.

## <a name="external-dependencies-for-an-intune-deployment"></a>Intune 배포에 대한 외부 종속성

### <a name="identity"></a>ID

Intune은 ID 및 사용자 그룹화 공급자로 AAD(Azure Active Directory)가 필요합니다.

-   [ID 요구 사항](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview)에 대해 자세히 알아보세요.

-   [디렉터리 동기화 요구 사항](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements)에 대해 자세히 알아보세요.

-   [다단계 인증 요구 사항](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements)에 대해 자세히 알아보세요.

-   [사용자 및 장치 그룹 계획](https://docs.microsoft.com/intune/deploy-use/plan-your-user-and-device-groups)에 대해 자세히 알아보세요.

-   [사용자 및 장치 그룹을 만드는 방법](https://docs.microsoft.com/intune/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune)에 대해 알아보세요.

조직이 이미 Office 365를 사용하고 있는 경우 Intune에서 동일한 Azure Active Directory 환경을 사용하는 것이 중요합니다.

### <a name="pki-optional"></a>PKI(선택 사항)

Intune에서 VPN, Wi-Fi 또는 메일 프로필에 인증서 기반 인증을 사용할 계획인 경우 지원되는 [PKI 인프라를 구축](https://docs.microsoft.com/intune/deploy-use/secure-resource-access-with-certificate-profiles)하고, 인증서 프로필을 만들어 배포할 준비가 되었는지 확인해야 합니다.

Intune에서 인증서를 구성하는 방법에 대한 자세한 내용은 다음을 참조하세요.

-   [How to configure the certificate infrastructure for SCEP](https://docs.microsoft.com/intune/deploy-use/configure-certificate-infrastructure-for-scep)(SCEP 인증서 인프라 구성 방법)

-   [PFX 인증서 인프라 구성](https://docs.microsoft.com/intune/deploy-use/configure-certificate-infrastructure-for-pfx)

-   [Intune 인증서 프로필 구성 방법](file:///C:/intune/deploy-use/https://docs.microsoft.com/intune/deploy-use/configure-intune-certificate-profiles).

-   [Microsoft Intune을 사용하여 회사 리소스에 대한 액세스 허용](https://docs.microsoft.com/intune/deploy-use/enable-access-to-company-resources-with-microsoft-intune)

## <a name="task-list-for-an-intune-setup"></a>Intune 설정에 대한 작업 목록

### <a name="task-1-intune-subscription"></a>작업 1: Intune 구독

Intune으로 마이그레이션하려면 먼저, Intune 구독이 필요합니다.

-   [이 페이지](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0)를 방문하면 다음을 수행하는 방법에 대한 지침을 확인할 수 있습니다.

    -   새 AAD 테넌트에 연결된 새 Intune 구독을 만듭니다.

    -   기존 AAD 테넌트에 로그인하여 Intune 구독을 연결합니다.

### <a name="task-2-assign-intune-user-licenses"></a>작업 2: Intune 사용자 라이선스 할당

-   [Intune 사용자 라이선스를 할당하는 방법](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-4)에 대해 알아보세요.

-   새 Azure Active Directory 테넌트를 만든 경우 [새 사용자를 생성하거나 온-프레미스 AD(Active Directory)에서 사용자를 동기화하는 방법](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)에 대해 알아보세요.

### <a name="task-3-set-your-mdm-authority-to-intune"></a>작업 3: MDM 기관을 Intune으로 설정

Intune은 Azure Portal 또는 Configuration Manager 현재 분기 콘솔을 통해 관리할 수 있습니다. Intune을 Configuration Manager 현재 분기 배포와 통합해야 하는 경우가 아니라면 [Azure Portal](https://portal.azure.com)에서 Intune을 관리하는 것이 좋습니다.

Intune Azure Portal을 사용하도록 설정하려면 MDM 기관을 **Intune**으로 설정합니다. 다른 MDM 기관을 사용하면 Intune에서 MDM 관리를 대체 Microsoft 관리 콘솔로 전송할 수 있습니다. 이러한 경우는 일반적이지 않습니다.

> [!IMPORTANT]
> 모바일 장치 관리를 Intune에 처음으로 전송할 경우 MDM 기관을 Intune으로 설정해야 합니다.

-   [모바일 관리 기관을 설정하는 방법](https://docs.microsoft.com/intune/deploy-use/prerequisites-for-enrollment#step-2-set-mdm-authority)에 대해 알아보세요.

## <a name="next-step"></a>다음 단계

[1단계: 장치 및 앱 관리 정책 구성](https://docs.microsoft.com/intune/plan-design/migration-phase1-configure-device-and-app-management-policies)

