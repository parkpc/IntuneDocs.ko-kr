---
title: "Azure Portal 미리 보기의 Intune 소개 | Intune Azure 미리 보기 | Microsoft Docs"
description: "Intune Azure 미리 보기: Azure Portal 미리 보기의 Intune에 대한 기본 사항 및 이를 통해 장치를 관리하는 방법을 알아봅니다."
keywords: 
author: robstackmsft
ms.author: robstack
nmanager: angrobe
ms.date: 01/08/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a085264-232a-4af0-97f1-747496c44517
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 1024d2a33d843c628ffbb68f7b01a5d511191e7e
ms.openlocfilehash: f7f6dd79531d8d69eda3ed80bbb1cddf2692ab81


---


# <a name="introduction-to-microsoft-intune-in-the-azure-portal-preview"></a>Azure Portal 미리 보기의 Microsoft Intune 소개


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Microsoft Intune이 Azure Portal로 전환되는 중입니다. 따라서 사용되는 워크플로 및 기능이 변경됩니다.
새 포털에서는 조직의 모바일 장치, PC 및 앱을 관리할 수 있는 Azure Portal의 새롭고 업데이트된 기능에 대한 미리 보기를 제공합니다.
모든 Intune 기능이 결국 Azure로 전환될 예정이지만 특정 Intune 작업은 지금 Azure Portal에서 수행할 수 있습니다. 이 새로운 환경은 미리 보기로 제공되기 때문에 일부 기능은 포털에 아직 없을 수 있습니다. 자세한 내용은 [미리 보기의 새로운 기능](#what's-new-in-the-preview) 섹션을 참조하세요.

> [!IMPORTANT]
> **새 포털이 아직 보이지 않으세요?**<br>
> 테넌트를 선택하도록 미리 보기를 이미 롤아웃하기 시작했습니다. 기존 테넌트는 2017년 초부터 새 환경으로 마이그레이션됩니다. 테넌트 마이그레이션 전에 Office 메시지 센터에서 알림을 받게 됩니다. 테넌트 마이그레이션 일정에 대한 질문이 있으면 [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com)으로 마이그레이션 팀에 문의하세요.


이 라이브러리에서 새 제품 설명서를 찾을 수 있으며, 미리 보기 중에 지속적으로 업데이트될 예정입니다. 제안 사항이 있는 경우 항목 설명에 의견을 남겨 주세요. 여러분의 의견을 듣고 싶습니다.

<!--- You can view the new Intune technical preview console in Azure at [portal.azure.com]. --->

새 환경에 대한 요약 정보는 다음과 같습니다.

- 모든 EMS(Enterprise Mobility + Security) 구성 요소에 대한 통합 콘솔
- 웹 표준을 기반으로 하는 HTML 기반 콘솔
- 많은 작업을 자동화하는 Microsoft Graph API 지원
- 모든 Azure 응용 프로그램에서 호환성을 제공하는 Azure AD 그룹
- 대부분의 최신 웹 브라우저 지원

클래식 Intune 콘솔에 대한 설명서를 보려면 [Intune 설명서 라이브러리](https://docs.microsoft.com/en-us/intune/)를 참조하세요.

## <a name="before-you-start"></a>시작하기 전에

Azure Portal에서 Intune을 사용하려면 Intune 관리 및 테넌트 계정이 있어야 합니다. [여기](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20)에서 계정에 등록할 수 있습니다.

## <a name="supported-web-browsers-for-the-azure-portal"></a>Azure Portal에 대해 지원되는 웹 브라우저

Azure Portal은 대부분의 최신 PC, Mac 및 태블릿에서 실행됩니다. 휴대폰은 지원되지 않습니다.
현재 지원되는 브라우저는 다음과 같습니다.

- Microsoft Edge(최신 버전)
- Microsoft Internet Explorer 11
- Safari(최신 버전, Mac만)
- Chrome(최신 버전)
- Firefox(최신 버전)

지원되는 브라우저에 대한 최신 정보는 [여기](https://docs.microsoft.com/azure/azure-preview-portal-supported-browsers-devices)를 참조하세요.

## <a name="whats-in-this-library"></a>이 라이브러리의 내용

설명서에는 필요한 정보를 보다 쉽게 찾을 수 있도록 Intune 포털의 레이아웃이 반영됩니다.

![Azure Portal 워크로드](./media/azure-portal-workloads.png)

<!--- ### Plan and design
Information to help you plan and design your Intune environment.
[Read more](/intune-azure/plan-and-design/get-started) --->
### <a name="enroll-devices"></a>장치 등록
Intune에서 장치를 관리하는 방법
[자세히 알아보기](/intune-azure/enroll-devices/what-is)
### <a name="devices--groups"></a>장치 및 그룹
인벤토리 및 보고서를 사용하여 관리하는 장치에 대해 알아봅니다.
[자세히 알아보기](/intune-azure/manage-devices/what-is)
### <a name="manage-users"></a>사용자 관리
관리하는 장치의 사용자에 대해 알아봅니다.
[자세히 알아보기](/intune-azure/manage-users/what-is)
### <a name="manage-apps"></a>앱 관리
앱을 게시, 관리, 구성 및 보호하는 방법에 대한 정보를 포함합니다.
[자세히 알아보기](/intune-azure/manage-apps/what-is-app-management)
### <a name="configure-devices"></a>장치 구성
관리하는 장치에서 설정 및 기능을 구성하는 데 사용할 수 있는 프로필에 대한 정보를 포함합니다.
[자세히 알아보기](/intune-azure/configure-devices/what-are-device-profiles)
### <a name="set-device-compliance"></a>장치 준수 설정
장치에 대한 준수 수준을 정의한 다음 호환되지 않는 장치에 대해 보고합니다. [자세히 알아보기](/intune-azure/set-device-compliance/what-is-device-compliance)
### <a name="conditional-access"></a>조건부 액세스
지정한 조건에 따라 Exchange 서비스에 대한 액세스를 제한합니다.
[자세히 알아보기](/intune-azure/conditional-access/what-is-conditional-access)
### <a name="access-control"></a>액세스 제어
다양한 Intune 작업을 수행할 수 있는 사람 및 해당 작업이 적용되는 사람을 제어합니다. 몇 가지 일반적인 Intune 시나리오에 적용되는 기본 제공 역할을 사용하거나, 사용자 고유의 역할을 만들 수 있습니다.
[자세히 알아보기](/intune-azure/access-control/role-based-access-control)


## <a name="whats-new"></a>새로운 기능

[미리 보기 릴리스의 새로운 기능을 알아봅니다](/intune-azure/introduction/whats-new).


<!--HONumber=Feb17_HO1-->


