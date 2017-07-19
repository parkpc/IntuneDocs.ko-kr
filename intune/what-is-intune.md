---
title: "Azure Portal의 Intune 소개"
titleSuffix: Intune on Azure
description: "Azure Portal의 Intune에 대한 기본 사항 및 Intune을 통해 장치를 관리하는 방법을 알아봅니다.\""
keywords: 
author: robstackmsft
ms.author: robstack
nmanager: angrobe
ms.date: 06/13/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a085264-232a-4af0-97f1-747496c44517
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7549f3277c23c3951090502f2babfe7c47b0a201
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2017
---
# <a name="introduction-to-microsoft-intune-in-the-azure-portal"></a>Azure Portal의 Microsoft Intune 소개


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Microsoft Intune은 이제 Azure Portal에 포함되었습니다. 따라서 이전에 사용했던 워크플로와 기능이 달라졌습니다.
새 포털에서는 조직의 모바일 장치, PC 및 앱을 관리할 수 있는 Azure Portal의 새롭고 업데이트된 기능을 제공합니다.

> [!IMPORTANT]
> **새 포털이 아직 보이지 않으세요?**<br>
> 현재 기존 테넌트를 새로운 환경으로 마이그레이션하는 중입니다. 테넌트가 마이그레이션되기 전에 Office 메시지 센터에 알림이 표시됩니다.
>
> 2017년 1월 이전에 만든 Intune 계정은 일회성 마이그레이션을 수행해야 Azure에서 Apple 등록 워크플로를 사용할 수 있습니다. 마이그레이션 일정은 아직 공지되지 않았습니다. 기존 계정으로 Azure Portal에 액세스할 수 없는 경우 평가판 계정을 만드는 것이 좋습니다.
>
> 잠재적 차단 목록을 검토합니다. https://blogs.technet.microsoft.com/intunesupport/2017/05/17/intune-migration-blockers-for-grouping-targeting/


새 포털에 대한 정보는 이 라이브러리에서 확인할 수 있으며 지속적으로 업데이트됩니다. 제안 사항이 있는 경우 항목 설명에 의견을 남겨 주세요. 여러분의 의견을 듣고 싶습니다.

새 환경에 대한 요약 정보는 다음과 같습니다.

- 모든 EMS(Enterprise Mobility + Security) 구성 요소에 대한 통합 콘솔
- 웹 표준을 기반으로 하는 HTML 기반 콘솔
- 많은 작업을 자동화하는 Microsoft Graph API 지원
- 모든 Azure 응용 프로그램에서 호환성을 제공하는 Azure AD(Active Directory) 그룹
- 대부분의 최신 웹 브라우저 지원

클래식 Intune 콘솔에 대한 설명서를 보려면 [Intune 설명서 라이브러리](https://docs.microsoft.com/intune-classic/)를 참조하세요.

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
이 섹션에서는 Intune 사용을 시작하는 데 도움이 되는 [소개 정보](introduction-intune.md)를 제공합니다.
### <a name="plan-and-design"></a>계획 및 디자인
Intune 환경의 [계획 및 디자인](/intune-classic/plan-design/introduction)에 도움을 주는 정보입니다.
### <a name="device-enrollment"></a>장치 등록
[Intune에서 장치를 관리하는 방법](device-enrollment.md)
### <a name="device-compliance"></a>장치 정책 준수
[장치에 대한 준수 수준을 정의한 다음 호환되지 않는 장치에 대해 보고합니다](device-compliance.md).
### <a name="device-configuration"></a>장치 구성
[관리하는 장치에서 설정 및 기능을 구성하는 데 사용할 수 있는 프로필을 이해합니다](device-profiles.md).
### <a name="devices"></a>장치
[인벤토리 및 보고서를 사용하여 관리하는 장치에 대해 알아봅니다](device-management.md).
### <a name="mobile-apps"></a>모바일 앱
[앱을 게시하고 관리하고 구성하고 보호하는 방법](app-management.md)
### <a name="conditional-access"></a>조건부 액세스
[지정한 조건에 따라 Exchange 서비스에 대한 액세스를 제한합니다](conditional-access.md).
### <a name="on-premises-access"></a>온-프레미스 액세스
[Exchange ActiveSync 및 Exchange 온-프레미스에 대한 액세스를 구성하는 방법에 대해 알아봅니다](/intune-classic/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune).
### <a name="users"></a>Users
[관리하는 장치의 사용자에 대해 알아보고 리소스를 그룹으로 정렬합니다](user-management.md).
### <a name="groups"></a>Groups
[Intune에서 Azure Active Directory 그룹을 사용할 수 있는 방법에 대해 알아봅니다](groups-get-started.md).
### <a name="intune-roles"></a>Intune 역할
[다양한 Intune 작업을 수행할 수 있는 사람 및 해당 작업이 적용되는 사람을 제어합니다](role-based-access-control.md). 몇 가지 일반적인 Intune 시나리오에 적용되는 기본 제공 역할을 사용하거나, 사용자 고유의 역할을 만들 수 있습니다.
### <a name="software-updates"></a>소프트웨어 업데이트
[Windows 10 장치용 소프트웨어 업데이트를 구성하는 방법에 대해 알아봅니다](windows-update-for-business-configure.md).



## <a name="whats-new"></a>새로운 기능은 무엇입니까?

[Intune의 새로운 기능에 대해 알아봅니다](whats-new.md).
