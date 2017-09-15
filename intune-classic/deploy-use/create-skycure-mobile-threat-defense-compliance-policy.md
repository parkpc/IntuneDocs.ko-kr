---
title: "Skycure Mobile Threat Defense 준수 정책 만들기"
description: "Intune 클래식 포털에서 Skycure Mobile Threat Defense 준수 정책을 만듭니다."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 56ff1728-1119-4e8a-aae6-ed5c7fafa052
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: e8f7b6c5c1e8497ca698b83215525ba9b4056f59
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/09/2017
---
# <a name="create-skycure-mobile-threat-defense-compliance-policy"></a>Skycure Mobile Threat Defense 준수 정책 만들기

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Skycure Mobile Threat Defense와 Intune을 사용하면 모바일 장치에 대한 위험을 감지하고 해당 장치에 대한 위험을 평가할 수 있습니다. 위험을 평가하는 Intune 준수 정책 규칙을 만들어 장치가 정책을 준수하는지 확인할 수 있습니다. 그런 다음 조건부 액세스 정책을 사용하여 장치 준수 여부에 따라 액세스를 차단할 수 있습니다.

## <a name="before-you-begin"></a>시작하기 전에

Skycure 장치 위협 방지와 준수 정책에 대한 필수 구성 요소:

-   [Intune과 Skycure 통합 설정](/intune-classic/deploy-use/setup-the-skycure-integration-with-Intune)

-   [Intune에서 Skycure 연결 사용](/intune-classic/deploy-use/enable-skycure-mobile-threat-defense-in-intune)

Skycure Mobile Threat Defense 설정의 일부로, Skycure 콘솔에서 다양한 위협 수준을 높음, 보통, 낮음으로 분류하는 정책을 만들었습니다. Intune 준수 정책에서 허용된 최대 위협 수준을 설정할 수 있습니다.

## <a name="to-create-skycure-compliance-policy"></a>Skycure 준수 정책을 만들려면

1.  [Intune 클래식 포털](https://manage.microsoft.com/)로 이동한 다음 자격 증명을 입력합니다.

2.  **정책** &gt; **준수 정책**을 선택합니다. 기존 준수 정책을 사용하거나 새로 만들 수 있습니다.

3.  **추가** &gt; **장치 상태**를 선택한 다음 **장치 위협 방지**를 사용하도록 설정합니다.

4.  **허용된 최대 위협 수준**을 선택합니다.

    a.  **없음(보안됨)**: 가장 안전한 수준입니다. 장치가 어떠한 위협에도 노출되지 않았으며 회사 리소스에 계속 액세스할 수 있습니다. 어떠한 위협이든 확인되는 장치는 비규격으로 평가됩니다.

    b.  **낮음**: 낮은 수준의 위협만 있는 장치는 규격 장치입니다. 더 높은 수준의 위협이 발생하면 장치는 규정 비준수 상태가 됩니다.

    c.  **보통**: 낮음 또는 보통 수준의 위협이 발견되는 장치는 규격 장치입니다. 높은 수준의 위협이 검색되는 장치는 비규격으로 간주됩니다.

    d.  **높음**: 안전성이 가장 낮은 수준입니다. 이 수준은 모든 위협 수준을 허용하며 보고용으로만 Skycure Mobile Threat Defense를 사용합니다.

> [!IMPORTANT]
> Office 365 또는 기타 서비스용으로 조건부 액세스 정책을 만드는 경우 준수 평가가 수행되며, 위협이 해결될 때까지 회사 리소스에 대한 비규격 장치의 액세스가 차단됩니다.

## <a name="span-idmonitor-device-threats-classanchorspan-idnext-steps-classanchorspan-idtoc477360344-classanchorspanspanspannext-steps"></a><span id="monitor-device-threats" class="anchor"><span id="next-steps" class="anchor"><span id="_Toc477360344" class="anchor"></span></span></span>다음 단계

-   다음에 대한 조건부 액세스 정책 만들기

    -   [Exchange Online](/intune-classic/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)
    -   [Exchange 온-프레미스](/intune-classic/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)
    -   [SharePoint Online](/intune-classic/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune)
    -   [비즈니스용 Skype Online](/intune-classic/deploy-use/restrict-access-to-skype-for-business-online-with-microsoft-intune)
    -   [Dynamics CRM](/intune-classic/deploy-use/restrict-access-to-dynamics-crm-online-with-microsoft-intune)
