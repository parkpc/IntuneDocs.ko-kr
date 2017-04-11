---
title: "Intune에서 Lookout MTP 사용 | Microsoft 문서"
description: "Intune 관리 콘솔에서 Lookout Mobile Threat Protection을 사용하도록 설정합니다."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2f835fd0-4e62-42f3-b7ca-ce8b7ddd40e4
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: d42fa20a3bc6b6f4a74dd0872aae25cfb33067b9
ms.openlocfilehash: d2a10a0e14d9b0b4d2e3f8e2715b47d984e5aa66
ms.lasthandoff: 03/21/2017


---

# <a name="enable-lookout-mtd-connection-in-the-intune-classic-console"></a>Intune 클래식 콘솔에서 Lookout MTD 연결 사용

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune에서 Lookout MTD(Mobile Threat Defense) 연결을 사용하려면 Lookout 콘솔에서 Intune Connector를 미리 구성해야 합니다.  아직 구성하지 않은 경우 [Lookout MTD(Mobile Threat Defense) 구독을 설정](set-up-your-subscription-with-lookout-mtp.md)해야 합니다.

Intune에서 Lookout MTP를 연결하려면 [Microsoft Intune 관리자 콘솔](https://manage.microsoft.com)의 **관리** 페이지에서 **타사 서비스 통합**을 선택합니다. **Lookout 상태**를 선택하고 토글 단추를 사용하여 **MTP와 동기화**를 사용하도록 설정합니다.

![토글 단추를 사용하도록 선택한 Lookout 동기화 페이지의 스크린샷](../media/mtp/lookout-intune-synchronization.png)

>[!IMPORTANT]
> 규정 준수 정책 규칙을 만들고 조건부 액세스를 구성하기 전에 Lookout for Work 앱을 구성**해야 합니다**. 이렇게 하면 앱이 최종 사용자가 설치할 수 있는 상태로 준비되어 최종 사용자가 메일과 기타 회사 리소스에 액세스할 수 있게 됩니다.

이렇게 하면 Intune 관리자 콘솔에서 Lookout 및 Intune 통합 설정이 완료됩니다.  그다음으로는, 이 솔루션을 구현하기 위해 [Lookout for Work 앱](https://docs.microsoft.com/intune/deploy-use/device-threat-protection-apps)을 배포하고 [규정 준수](https://docs.microsoft.com/intune/deploy-use/device-threat-protection-policy) 정책을 설정하기 위한 몇 가지 단계를 진행하게 됩니다.


## <a name="next-steps"></a>다음 단계
[Lookout for Work 앱 구성](https://docs.microsoft.com/intune/deploy-use/device-threat-protection-apps)

