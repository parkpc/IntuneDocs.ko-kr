---
title: "장치 보호 규칙 사용"
description: "장치 준수 정책에서 모바일 위협 검색 규칙을 사용하도록 설정하는 방법을 설명합니다."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c951692d-6538-46c0-a9f0-d607ded189ae
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 5ee11809349999a795aca0a373724ce18eedbe65
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/10/2017
---
# <a name="create-lookout-device-compliance-policy-in-intune"></a>Intune에서 Lookout 장치 준수 정책 만들기

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Lookout Mobile Threat Defense와 Intune을 사용하면 모바일 장치에 대한 위협을 감지하고 해당 장치에 대한 위협을 평가할 수 있습니다. 위험을 평가하는 준수 정책 규칙을 만들어 장치가 정책을 준수하는지 확인할 수 있습니다. 그런 다음 조건부 액세스 정책을 사용하여 장치 준수 여부에 따라 액세스를 차단할 수 있습니다.

Lookout Mobile Threat Defense와 준수 정책에 대한 필수 구성 요소:

- [Lookout Mobile Threat Defense 구독 설정](setup-your-lookout-mtd-subscription.md)
- [Intune에서 Lookout 연결 사용](enable-lookout-mtd-connection.md)
- [Lookout for Work 앱 구성 및 배포](configure-deploy-lookout-for-work-app.md)

Lookout Mobile Threat Defense 설정의 일부로, [Lookout 콘솔](https://aad.lookout.com)에서 다양한 위협 수준을 높음, 보통, 낮음으로 분류하는 정책을 만들었습니다. Intune 준수 정책에서 허용된 최대 위협 수준을 설정할 수 있습니다.

1. [Intune 관리자 콘솔](https://manage.microsoft.com)에서 **준수 정책** 페이지로 이동합니다. 기존 준수 정책을 사용하거나 새로 만들 수 있습니다. **장치 상태**로 이동하고 **장치 위협 방지**를 사용하도록 설정합니다.
  ![장치 위협 방지 규칙을 설정한 모습을 보여 주는 스크린샷](../media/mtp/mtp-compliance-policy-rule.png)

2. **허용된 최대 위협 수준**을 선택합니다.
  * **없음(보안됨)**: 가장 안전한 수준입니다.  장치가 어떠한 위협에도 노출되지 않았으며 회사 리소스에 계속 액세스할 수 있습니다.  어떠한 위협이든 확인되는 장치는 비규격으로 평가됩니다.  
  * **낮음**: 낮은 수준의 위협만 있는 장치는 규격 장치입니다. 더 높은 수준의 위협이 확인되는 장치는 비규격 상태로 설정됩니다.
  * **보통**: 낮음 또는 보통 수준의 위협이 발견되는 장치는 규격 장치입니다. 높은 수준의 위협이 검색되는 장치는 비규격으로 간주됩니다.
  * **높음**: 안전성이 가장 낮은 수준입니다. 이 수준은 모든 위협 수준을 허용하며 방지 보고용으로만 Lookout 모바일 위협 방지를 사용합니다.

![장치 위협 방지 규칙에서 위협 수준 옵션을 설정한 모습을 보여 주는 스크린샷](../media/mtp/mtp-compliance-policy-setting.png)

Office 365 또는 기타 서비스용으로 조건부 액세스 정책을 만드는 경우 준수 평가가 수행되며, 위협이 해결될 때까지 회사 리소스에 대한 비규격 장치의 액세스가 차단됩니다.

## <a name="monitor-device-threats"></a>모니터 장치 위협
장치의 준수 상태를 보려면 [Intune 관리자 콘솔](https://manage.microsoft.com)로 이동하고 **모든 장치**를 봅니다.

![장치의 규정 준수 상태를 보여 주는 Intune 관리 콘솔의 장치 페이지 스크린샷](../media/mtp/mtp-device-status-intune-console.png)

## <a name="next-steps"></a>다음 단계
* 조건부 액세스 정책 만들기
  * [Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md)
  * [Exchange 온-프레미스](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  * [SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)
  * [비즈니스용 Skype Online](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)
  * [Dynamics CRM](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md)
