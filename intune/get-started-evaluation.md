---
title: "Intune 시작"
titleSuffix: Intune on Azure
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 06/27/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6bfab644-c1e2-4154-a254-e95b9a1d75f2
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ef58e46118a0a44609abba5de4986b5a1526a151
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2017
---
# <a name="what-is-microsoft-intune"></a>Microsoft Intune이란?

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

![Azure Portal의 Microsoft Intune](./media/generic-intune-azure.png)

Microsoft Intune은 Azure의 최신 서비스 중 하나입니다. 조직의 모바일 장치, PC 및 앱을 관리하는 데 사용되며 [정기적으로 업데이트](whats-new.md)되는 도구를 제공합니다. 최신 Azure 콘솔뿐 아니라 Intune을 통해 클래식 콘솔도 사용할 수 있습니다. 클래식 콘솔은 Intune의 첫 번째 버전으로, 여기서도 [Intune 소프트웨어 클라이언트를 사용한 Windows PC 관리](/intune-classic/deploy-use/pc-management-comparison.md)로 이동합니다. Silverlight에서 빌드된 클래식 포털은 적은 수의 작업에만 사용됩니다. 모바일 장치 및 앱 관리를 포함한 나머지 작업은 모두 Azure Portal에서 수행됩니다. 시작 가이드에서는 Azure Portal에서 Intune을 사용하여 필요한 기본 작업을 성공적으로 수행하는 과정을 안내합니다.

![Intune 왼쪽 사이드바의 작업 목록 맨 아래에 있는 도움말 및 지원 블레이드](./media/intune-azure-help-support-closeup.png)

## <a name="what-does-intune-in-the-azure-portal-provide"></a>Azure Portal의 Intune은 어떤 기능을 제공하나요?

Azure Portal의 Intune에서 제공하는 기능은 다음과 같습니다.

* 모든 [EMS(Enterprise Mobility + Security) 구성 요소](https://docs.microsoft.com/enterprise-mobility-security)에 대한 통합 콘솔
* [최신 웹 브라우저](supported-devices-browsers.md)를 지원하는, 웹 표준을 토대로 빌드된 HTML 기반 콘솔
* 모든 Azure 응용 프로그램에서 호환성을 제공하는 [Azure Active Directory 그룹](groups-get-started.md)
* [Microsoft Graph API](intune-graph-apis.md)를 통한 자동화

## <a name="prerequisites"></a>필수 구성 요소

시작하기 전에 Intune 관리자 및 테넌트 계정이 활성화되어 있어야 합니다. [여기](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20)서 이러한 계정에 등록할 수 있습니다. 현재 구독자는 라이브 테넌트에서 이러한 작업을 완료할 수도 있습니다. 테스트 장치에서만 작업해야 합니다.

또한 가이드에 있는 모든 작업을 완료하려면 조직의 전역 관리자여야 합니다.
