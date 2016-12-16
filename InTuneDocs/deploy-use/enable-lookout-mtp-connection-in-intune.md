---
title: "Intune에서 Lookout MTP를 사용하도록 설정 | Microsoft Intune"
description: "Intune 관리 콘솔에서 Lookout Mobile Threat Protection을 사용하도록 설정합니다."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 2f835fd0-4e62-42f3-b7ca-ce8b7ddd40e4
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 87e37cd8334ddb9331c0662b691545cd0ab0553a
ms.openlocfilehash: 1bef6c15387309e1b36bc85758ca699acd54fdd0


---

# <a name="enable-lookout-mtp-connection-in-the-intune-admin-console"></a>Intune 관리 콘솔에서 Lookout MTP 연결
이 항목에서는 Intune에서 Lookout MTP를 연결하는 방법을 보여 줍니다. 이 단계를 수행하려면 이미 Lookout 콘솔에서 Intune Connector를 구성한 상태여야 합니다.  아직 구성하지 않은 경우 [Lookout Mobile Threat Protection 구독 설정](set-up-your-subscription-with-lookout-mtp.md)에 설명된 단계를 진행합니다.

Intune에서 Lookout MTP를 연결하려면 [Microsoft Intune 관리자 콘솔](https://manage.microsoft.com)의 **관리** 페이지에서 **타사 서비스 통합**을 선택합니다. **Lookout 상태**를 선택하고 토글 단추를 사용하여 **MTP와 동기화**를 설정합니다.

![토글 단추를 사용하도록 선택한 Lookout 동기화 페이지의 스크린샷](../media/mtp/lookout-intune-synchronization.png)

이렇게 하면 Intune 관리자 콘솔에서 Lookout 및 Intune 통합 설정이 완료됩니다.  그다음으로는, 이 솔루션을 구현하기 위해 [Lookout for Work 앱](configure-and-deploy-lookout-for-work-apps.md)을 배포하고 [규정 준수](enable-device-threat-protection-rule-in-compliance-policy.md) 정책을 설정하기 위한 몇 가지 단계를 진행하게 됩니다.

>[!IMPORTANT]
> 규정 준수 정책 규칙을 만들고 조건부 액세스를 구성하기 전에 Lookout for Work 앱을 구성**해야 합니다**. 이렇게 하면 앱이 최종 사용자가 설치할 수 있는 상태로 준비되어 최종 사용자가 메일과 기타 회사 리소스에 액세스할 수 있게 됩니다.
## <a name="next-steps"></a>다음 단계
[Lookout for Work 앱 구성 ](configure-and-deploy-lookout-for-work-apps.md)



<!--HONumber=Dec16_HO2-->


