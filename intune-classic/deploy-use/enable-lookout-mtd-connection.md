---
title: "Intune에서 Lookout MTP 사용"
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
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f34697140a287d41203d1bad5df59250f07d08ce
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/10/2017
---
# <a name="enable-lookout-mtd-connection-in-the-intune-classic-portal"></a>Intune 클래식 포털에서 Lookout MTD 연결 사용

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune에서 Lookout MTD(Mobile Threat Defense) 연결을 사용하려면 Lookout 콘솔에서 Intune Connector를 미리 구성해야 합니다.  아직 구성하지 않은 경우 [Lookout MTD(Mobile Threat Defense) 구독을 설정](setup-your-lookout-mtd-subscription.md)해야 합니다.

Intune에서 Lookout MTP를 연결하려면 [Microsoft Intune 관리자 콘솔](https://manage.microsoft.com)의 **관리** 페이지에서 **타사 서비스 통합**을 선택합니다. **Lookout 상태**를 선택하고 토글 단추를 사용하여 **MTP와 동기화**를 사용하도록 설정합니다.

![토글 단추를 사용하도록 선택한 Lookout 동기화 페이지의 스크린샷](../media/mtp/lookout-intune-synchronization.png)

>[!IMPORTANT]
> 규정 준수 정책 규칙을 만들고 조건부 액세스를 구성하기 전에 Lookout for Work 앱을 구성**해야 합니다**. 이렇게 하면 앱이 최종 사용자가 설치할 수 있는 상태로 준비되어 최종 사용자가 메일과 기타 회사 리소스에 액세스할 수 있게 됩니다.

Intune 관리자 콘솔에서 Lookout 및 Intune 통합 설정이 완료되었습니다.  이 솔루션을 구현하는 다음 몇 단계에는 [Lookout for Work 앱](/intune-classic/deploy-use/device-threat-protection-policy) 정책 배포가 포함됩니다.


## <a name="next-steps"></a>다음 단계
[Lookout for Work 앱 구성](/intune-classic/deploy-use/device-threat-protection-apps)
