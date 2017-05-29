---
title: "조건부 액세스로 최종 사용자 도입 촉진 | Microsoft 문서"
description: "이 문서의 목적은 조건부 액세스를 활용하여 Intune 등록을 촉진하는 방법에 대한 유용한 정보를 제공하는 것입니다."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c2d7ce3f-fe97-4044-ad9e-25ac8fa301c9
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 55e437fa33af9d27223798cbac9f541b0bc1be2d
ms.contentlocale: ko-kr
ms.lasthandoff: 05/23/2017


---

# <a name="phase-2-drive-end-user-adoption-with-conditional-access"></a>2단계: 조건부 액세스로 최종 사용자 도입 촉진

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

등록 취소된 장치에 대한 메일 차단과 같은 조건부 액세스 기능을 Intune에서 사용하도록 설정하면 등록 및 준수를 촉진하는 데 도움이 될 수 있지만, 마이그레이션 성공에 필요한 과정은 아닙니다. 마이그레이션 도입 목표 및 보안 요구 사항에서 성공 여부를 결정해야 합니다.

## <a name="migration-campaign-with-conditional-access"></a>조건부 액세스로 마이그레이션 캠페인

다음은 조건부 액세스로 마이그레이션 캠페인을 강화하는 일반적인 방법입니다.

1.  모든 사용자에 적용할 조건부 액세스 규칙을 설정하지만, 특별히 이전 MDM 공급자에서 마이그레이션해야 하는 사용자는 제외합니다. 모든 조건부 액세스 제외 사용자가 포함된 Azure AD 사용자 그룹을 만들 수 있습니다.

2.  사용자 마이그레이션 시 조건부 액세스 제외 그룹에서 해당 사용자를 제거합니다.

3.  마이그레이션이 완료되면 Intune에서 액세스를 허용하지 않는 한 기본적으로 차단하도록 모든 조건부 액세스 정책을 구성합니다.

### <a name="advantages"></a>장점

-   새 사용자 계정 또는 이전 솔루션으로 관리되지 않는 사용자 계정에 대한 액세스 제어를 제공합니다.

-   이전 솔루션의 사용자가 마이그레이션할 수 있도록 유예 기간을 제공합니다.

-   생산성 저하를 최소화합니다.

### <a name="disadvantages"></a>단점

-   이전 솔루션의 사용자가 조건부 액세스를 사용할 수 있게 될 때까지 해당 사용자는 관리되지 않는 장치를 사용하여 리소스에 액세스할 수 있습니다.

> [!TIP]
> 이는 여러 방법 중 하나입니다. 모든 단계에서 등록 지시를 받은 이후까지 모든 조건부 액세스를 지연하는 간단한 프로세스를 선택하거나 처음부터 조건부 액세스를 적용하고 모든 액세스에 대한 완전한 준수를 요구하는 엄격한 프로세스를 선택할 수 있습니다.

-   [조건부 액세스](https://docs.microsoft.com/intune/conditional-access)에 대해 자세히 알아보세요.

## <a name="task-list-for-conditional-access"></a>조건부 액세스에 대한 작업 목록

### <a name="task-1-get-ready-for-intune-conditional-access"></a>작업 1: Intune 조건부 액세스 준비

-   [조건부 액세스를 구성하는 방법](/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)에 대해 알아보세요.

### <a name="task-2-set-up-intune-conditional-access"></a>작업 2: Intune 조건부 액세스 설정

더 자세히 알아보려면 다음 조건부 액세스 정책 유형 중 하나를 선택합니다.

-   [Exchange Online 및 새 Exchange Online Dedicated](/intune-classic/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)

-   [Exchange 온-프레미스 및 레거시 Exchange Online Dedicated](/intune-classic/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)

-   [SharePoint Online](/intune-classic/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune)

-   [비즈니스용 Skype Online](/intune-classic/deploy-use/restrict-access-to-skype-for-business-online-with-microsoft-intune)

-   [Dynamics CRM Online](/intune-classic/deploy-use/restrict-access-to-dynamics-crm-online-with-microsoft-intune)

-   [예제 메일 액세스 시나리오](/intune-classic/deploy-use/restrict-email-access-example-scenarios)

## <a name="next-steps"></a>다음 단계

[2단계: 일반적인 마이그레이션 주기](/intune-classic/plan-design/migration-phase2-typical-migration-cycle)

