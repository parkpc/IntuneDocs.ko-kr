---
title: "Intune을 사용하는 조건부 액세스"
titleSuffix: Intune on Azure
description: "사용자 및 장치가 Microsoft Intune에서 회사 리소스에 액세스하기 위해 충족해야 하는 조건을 정의하는 방법을 알아봅니다.\""
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 05/23/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1973f38-ea55-43eb-a151-505fb34a8afb
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d3e6b720eeed65c81e5f3a4dbf06890ea8fd09ce
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2017
---
# <a name="whats-conditional-access"></a>조건부 액세스란?

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

이 항목에서는 Enterprise Mobility + Security(EMS)에 적용되는 조건부 액세스 및 Intune 사용 시의 일반적인 조건부 액세스 시나리오에 대해 설명합니다.

Enterprise Mobility + Security(EMS) 조건부 액세스는 독립 실행형 제품이 아니며 EMS의 일부분인 모든 서비스와 제품에 포함되는 솔루션입니다. EMS 조건부 액세스는 회사 데이터의 보안을 유지할 수 있는 세분화된 액세스 제어 기능을 제공하는 동시에, 사용자에게는 모든 위치와 장치에서 업무를 가장 효율적으로 수행할 수 있도록 하는 환경을 제공합니다.

위치, 장치, 사용자 상태 및 응용 프로그램 민감도 등을 기반으로 회사 데이터에 대한 액세스를 제한하는 조건을 정의할 수 있습니다.

> [!NOTE] 
> 조건부 액세스의 기능은 [Office 365 서비스](https://blogs.technet.microsoft.com/wbaer/2017/02/17/conditional-access-policies-with-sharepoint-online-and-onedrive-for-business/)로도 확장 적용됩니다.

![조건부 액세스 아키텍처 다이어그램](./media/ca-diagram-1.png)

## <a name="conditional-access-with-intune"></a>Intune을 사용하는 조건부 액세스

Intune은 EMS 조건부 액세스 솔루션을 지원하기 위해 모바일 장치 준수 및 모바일 응용 프로그램 관리 기능을 추가적으로 제공합니다.

![EMS 사용 시의 Intune 및 조건부 액세스](./media/intune-with-ca-1.png)

Intune에서 조건부 액세스를 사용하는 방법은 다음과 같습니다.

-   **장치 기반 조건부 액세스**

    -   Exchange 온-프레미스에 대한 조건부 액세스

    -   네트워크 액세스 제어 기준 조건부 액세스

    -   장치 위험 기준 조건부 액세스

    -   Windows PC에 대한 조건부 액세스

        -   회사 소유

        -   BYOD(Bring Your Own Device)

-   **앱 기반 조건부 액세스**

## <a name="next-steps"></a>다음 단계

[Intune에서 조건부 액세스를 사용하는 일반적인 방법](conditional-access-intune-common-ways-use.md)