---
title: Intune에서 Skycure Mobile Threat Defense를 사용하도록 설정
description: Intune 클래식 포털에서 Skycure Mobile Threat Defense를 사용하도록 설정합니다.
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 03/16/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 0cc4e59d-819a-47a2-a26f-4f8d0f8df7bf
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: da4197a41798f4e47ff35d2dfab36c5317f92e21
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="enable-skycure-mobile-threat-defense-in-intune"></a>Intune에서 Skycure Mobile Threat Defense를 사용하도록 설정

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Skycure MTD(Mobile Threat Defense)을 사용하도록 설정하려면 [Skycure 콘솔에서 Intune 커넥터](/intune-classic/deploy-use/setup-the-skycure-integration-with-Intune)를 미리 구성해야 합니다.

## <a name="to-enable-the-skycure-mtd-connection-in-intune"></a>Intune에서 Skycure MTD 연결을 사용하도록 설정하려면

1.  [Intune 클래식 포털](https://manage.microsoft.com/)로 이동한 다음 자격 증명을 입력합니다.

2.  **관리자** &gt; **타사 서비스 통합**을 선택한 다음 **Skycure 상태**를 선택하고 토글 단추를 사용하여 **MTD와 동기화**를 사용하도록 설정합니다.

    ![Intune 클래식 포털에서 Skycure 토글을 사용하도록 설정](../media/mtp/enable-skycure-1.png)

> [!IMPORTANT] 
> 준수 정책 규칙을 만들고 조건부 액세스를 구성하기 전에 Skycure 앱을 구성해야 합니다. 이렇게 하면 앱이 최종 사용자가 설치할 수 있는 상태로 준비되어 최종 사용자가 메일과 기타 회사 리소스에 액세스할 수 있게 됩니다.

그러면 Intune 관리자 콘솔에서 Skycure 및 Intune 통합 설정이 완료됩니다. 다음으로는, 이 솔루션을 구현하기 위해 Skycure for Work 앱을 배포하고 준수 정책을 설정하기 위한 몇 가지 단계를 진행하게 됩니다.

## <a name="next-steps"></a>다음 단계

[Skycure Mobile Threat Defense 준수 정책 만들기](/intune-classic/deploy-use/create-skycure-mobile-threat-defense-compliance-policy)
