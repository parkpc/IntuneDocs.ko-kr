---
title: "규정 준수 정책에서 장치 보호 규칙 활성화 | Microsoft Intune"
description: "장치 규정 준수 정책에서 모바일 위협 방지 규칙을 활성화합니다."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c951692d-6538-46c0-a9f0-d607ded189ae
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 686321a1c19acb9a3a7e262822b11304d07adb40
ms.openlocfilehash: 3e6aef013ae8764d9b031e880c333e184191feb4


---

# <a name="enable-device-threat-protection-rule-in-the-compliance-policy"></a>규정 준수 정책에서 장치 위협 방지 규칙 활성화
Lookout Mobile Threat Protection과 함께 Intune을 사용하면 모바일 위협을 탐지하고 장치에 대한 위험을 평가할 수 있습니다. 위험 평가를 포함하는 규정 준수 정책 규칙을 만들어 장치가 정책을 준수하는지 확인할 수 있습니다. 그런 다음 장치 규정 준수에 따라 조건부 액세스 정책으로 Exchange, SharePoint 및 기타 서비스에 대한 액세스를 허용하거나 차단할 수 있습니다.

장치에 대한 규정 준수 정책이 Lookout의 위협 감지의 영향을 받으려면

* 규정 준수 정책에서 **장치 위협 방지** 규칙을 활성화해야 합니다.

* **Intune 관리 콘솔**의 **Lookout 상태** 페이지가 **활성** 상태로 나타나야 합니다. Lookout 통합 활성화 방법에 대한 지침 등 자세한 내용은 [Intune에서 Lookout MTP 연결](enable-lookout-mtp-connection-in-intune.md) 항목을 참조하세요.


규정 준수 정책에서 장치 위협 방지 규칙을 만들기 전에, [Lookout 장치 위협 방지 구독을 설정](set-up-your-subscription-with-lookout-mtp.md)하고 [Intune에서 Lookout을 연결](enable-lookout-mtp-connection-in-intune.md)하며 [Lookout for work 앱을 구성](configure-and-deploy-lookout-for-work-apps.md)하는 것이 좋습니다. 규정 준수 규칙은 설치가 완료된 후에만 적용됩니다.

장치 위협 방지 규칙을 활성화하려면 기존 규정 준수 정책을 사용하거나 새 규정 준수 정책을 만들면 됩니다.

[Lookout 콘솔](https://aad.lookout.com)에서 Lookout 장치 위협 장지를 설정하는 중에 다양한 위협을 높음, 보통, 낮음 수준으로 분류하는 정책을 만들었습니다. 위협 수준은 Intune 규정 준수 정책에서 허용되는 최대 위협 수준을 설정하는 데 사용됩니다.

**Intune 관리자 콘솔**의 **규정 준수 정책** 페이지에서 **장치 상태**로 이동한 후 토글 옵션을 사용하여 **장치 위협 방지** 규칙을 사용하도록 설정합니다. 그런 다음 허용되는 최대 위협 수준을 다음 중에서 선택합니다.
* **없음(보안됨)**: 가장 안전합니다.  장치에 어떤 위협도 있어서는 안 된다는 의미입니다.  위협 수준이 발견되면 장치가 규정을 준수하지 않는 것으로 평가됩니다.  
* **낮음**: 낮은 수준의 위협만 있는 경우 장치가 규정 준수로 평가됩니다. 더 높은 수준의 위협이 발생하면 장치는 규정 비준수 상태가 됩니다.
* **보통**: 장치에 있는 위협이 낮음 또는 중간 수준인 경우 장치가 규정 준수로 평가됩니다. 높은 수준의 위협이 감지되면 장치가 규정 비준수로 결정됩니다.
* **높음**: 가장 보안이 낮습니다. 기본적으로 이 옵션은 모든 위협 수준을 허용하기 때문에 이 솔루션을 보고 목적으로 사용할 경우에만 유용합니다.

![장치 위협 방지 규칙을 설정한 모습을 보여 주는 스크린샷 ](../media/mtp/mtp-compliance-policy-rule.png)

![장치 위협 방지 규칙에서 위협 수준 옵션을 설정한 모습을 보여 주는 스크린샷](../media/mtp/mtp-compliance-policy-setting.png)

Office 365 및 기타 서비스에 대한 조건부 액세스 정책을 만들 경우 위의 규정 준수 평가 사항을 고려하여 위협을 해결할 때까지 규정 비준수 장치는 회사 리소스 액세스가 차단됩니다.

**Intune 관리자 콘솔**의 **모든 장치** 페이지에서 장치의 규정 준수 상태를 볼 수 있습니다.

![장치의 규정 준수 상태를 보여 주는 Intune 관리 콘솔의 장치 페이지 스크린샷](../media/mtp/mtp-device-status-intune-console.png)

## <a name="next-steps"></a>다음 단계
* 조건부 액세스 정책 만들기
  * [Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md)
  * [Exchange 온-프레미스](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  * [SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)
  * [비즈니스용 Skype Online](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)
  * [Dynamics CRM](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md)



<!--HONumber=Nov16_HO5-->


