---
title: "Azure Portal 미리 보기의 Intune 소개"
titleSuffix: Intune Azure preview
description: "Intune Azure 미리 보기: Azure Portal 미리 보기의 Intune에 대한 기본 사항 및 이를 통해 장치를 관리하는 방법을 알아봅니다."
keywords: 
author: robstackmsft
ms.author: robstack
nmanager: angrobe
ms.date: 04/24/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a085264-232a-4af0-97f1-747496c44517
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: b6026197a7a57ce29378b7ef9d064837faa75c6f
ms.openlocfilehash: a046e8a9b6c1c8c81bfeb4420418c0de22e6a6a3
ms.contentlocale: ko-kr
ms.lasthandoff: 05/12/2017


---


# <a name="introduction-to-microsoft-intune-in-the-azure-portal-preview"></a>Azure Portal 미리 보기의 Microsoft Intune 소개


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Microsoft Intune이 Azure Portal로 전환되는 중입니다. 따라서 사용되는 워크플로 및 기능이 변경됩니다.
새 포털에서는 조직의 모바일 장치, PC 및 앱을 관리할 수 있는 Azure Portal의 새롭고 업데이트된 기능에 대한 미리 보기를 제공합니다.
모든 Intune 기능이 결국 Azure로 전환될 예정이지만 다수의 Intune 작업은 지금 Azure Portal에서 수행할 수 있습니다. 이 새로운 환경은 미리 보기로 제공되기 때문에 일부 기능은 포털에 아직 없을 수 있습니다. 자세한 내용은 [새로운 기능](#what's-new) 섹션을 참조하세요.

> [!IMPORTANT]
> **새 포털이 아직 보이지 않으세요?**<br>
> 테넌트를 선택하도록 미리 보기를 이미 롤아웃하기 시작했습니다. 기존 테넌트는 2017년 초부터 새 환경으로 마이그레이션됩니다. 테넌트 마이그레이션 전에 Office 메시지 센터에서 알림을 받게 됩니다.
>
> 2017년 1월 이전에 만든 Intune 계정은 일회성 마이그레이션을 수행해야 Azure에서 Apple 등록 워크플로를 사용할 수 있습니다. 마이그레이션 일정은 아직 공지되지 않았지만 가능한 한 빠른 시일 내에 세부 정보가 제공될 예정입니다. 기존 계정에서 미리 보기에 액세스할 수 없는 경우 평가판 계정을 만들어 새로운 경험을 테스트해 보는 것이 좋습니다.


이 라이브러리에서 새 제품 설명서를 찾을 수 있으며, 미리 보기 중에 지속적으로 업데이트될 예정입니다. 제안 사항이 있는 경우 항목 설명에 의견을 남겨 주세요. 여러분의 의견을 듣고 싶습니다.

<!--- You can view the new Intune technical preview console in Azure at [portal.azure.com]. --->

새 환경에 대한 요약 정보는 다음과 같습니다.

- 모든 EMS(Enterprise Mobility + Security) 구성 요소에 대한 통합 콘솔
- 웹 표준을 기반으로 하는 HTML 기반 콘솔
- 많은 작업을 자동화하는 Microsoft Graph API 지원
- 모든 Azure 응용 프로그램에서 호환성을 제공하는 Azure AD(Active Directory) 그룹
- 대부분의 최신 웹 브라우저 지원

클래식 Intune 콘솔에 대한 설명서를 보려면 [Intune 설명서 라이브러리](https://docs.microsoft.com/intune/)를 참조하세요.

## <a name="before-you-start"></a>시작하기 전에

Azure Portal에서 Intune을 사용하려면 Intune 관리 및 테넌트 계정이 있어야 합니다. 계정이 아직 없는 경우 [계정에 등록](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20)하세요.

## <a name="supported-web-browsers-for-the-azure-portal"></a>Azure Portal에 대해 지원되는 웹 브라우저

Azure Portal은 대부분의 최신 PC, Mac 및 태블릿에서 실행됩니다. 휴대폰은 지원되지 않습니다.
현재 지원되는 브라우저는 다음과 같습니다.

- Microsoft Edge(최신 버전)
- Microsoft Internet Explorer 11
- Safari(최신 버전, Mac만)
- Chrome(최신 버전)
- Firefox(최신 버전)

지원되는 브라우저에 대한 최신 정보는 [Azure Portal](https://docs.microsoft.com/azure/azure-preview-portal-supported-browsers-devices)을 참조하세요.

## <a name="whats-in-this-library"></a>이 라이브러리의 내용

설명서에는 필요한 정보를 보다 쉽게 찾을 수 있도록 Intune 포털의 레이아웃이 반영됩니다.

![Azure Portal 워크로드](./media/azure-portal-workloads.png)

### <a name="introduction-and-get-started"></a>소개 및 시작
이 섹션에는 Intune의 [새로운 기능](whats-new.md), [알려진 문제](known-issues-in-the-intune-preview.md), [지원을 받는 방법](how-to-get-support-for-microsoft-intune.md) 및 [무료 평가판 시작](sign-up-free-trial-microsoft-intune.md) 방법에 대한 정보가 포함되어 있습니다.
### <a name="plan-and-design"></a>계획 및 디자인
Intune 환경의 [계획 및 디자인](/intune/plan-and-design/introduction)에 도움을 주는 정보입니다.
### <a name="device-enrollment"></a>장치 등록
[Intune에서 장치를 관리하는 방법](../enroll-devices/what-is.md)
### <a name="device-compliance"></a>장치 정책 준수
[장치에 대한 준수 수준을 정의한 다음 호환되지 않는 장치에 대해 보고합니다](../set-device-compliance/what-is-device-compliance.md).
### <a name="device-configuration"></a>장치 구성
[관리하는 장치에서 설정 및 기능을 구성하는 데 사용할 수 있는 프로필을 이해합니다](../configure-devices/what-are-device-profiles.md).
### <a name="devices"></a>장치
[인벤토리 및 보고서를 사용하여 관리하는 장치에 대해 알아봅니다](../manage-devices/what-is.md).
### <a name="mobile-apps"></a>모바일 앱
[앱을 게시하고 관리하고 구성하고 보호하는 방법](../manage-apps/what-is-app-management.md)
### <a name="conditional-access"></a>조건부 액세스
[지정한 조건에 따라 Exchange 서비스에 대한 액세스를 제한합니다](../conditional-access/what-is-conditional-access.md).
### <a name="on-premises-access"></a>온-프레미스 액세스
[Exchange ActiveSync 및 Exchange 온-프레미스에 대한 액세스를 구성하는 방법에 대해 알아봅니다](/intune/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune).
### <a name="users"></a>Users
[관리하는 장치의 사용자에 대해 알아보고 리소스를 그룹으로 정렬합니다](../manage-users/what-is.md).
### <a name="groups"></a>Groups
[Intune에서 Azure Active Directory 그룹을 사용할 수 있는 방법에 대해 알아봅니다](../manage-users/get-started-with-groups.md).
### <a name="intune-roles"></a>Intune 역할
[다양한 Intune 작업을 수행할 수 있는 사람 및 해당 작업이 적용되는 사람을 제어합니다](../access-control/role-based-access-control.md). 몇 가지 일반적인 Intune 시나리오에 적용되는 기본 제공 역할을 사용하거나, 사용자 고유의 역할을 만들 수 있습니다.
### <a name="software-updates"></a>소프트웨어 업데이트
[Windows 10 장치용 소프트웨어 업데이트를 구성하는 방법에 대해 알아봅니다](../configure-devices/how-to-configure-windows-update-for-business.md).



## <a name="whats-new"></a>새로운 기능은 무엇입니까?

[미리 보기 릴리스의 새로운 기능을 알아봅니다](whats-new.md).

