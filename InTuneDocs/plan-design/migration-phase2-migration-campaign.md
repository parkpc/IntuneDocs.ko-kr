---
title: "Intune 마이그레이션 캠페인 시작 | Microsoft 문서"
description: "이 문서의 목적은 마이그레이션 캠페인을 시작하는 방법에 대한 지침을 제공하는 것입니다."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f781b029-50f2-46ee-8ff7-03b4a6719e80
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab5aa4e12d951d818c5afb4e1ac5e866b05733fb
ms.openlocfilehash: 506b0360fb7b1f28c4c9ad3265e24c0ffa0b065d
ms.lasthandoff: 03/27/2017


---

# <a name="phase-2-migration-campaign"></a>2단계: 마이그레이션 캠페인

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

조직은 고유한 요구에 가장 적합한 마이그레이션 방법을 사용하고 특정 요구 사항에 따라 구현 전략을 조정해야 합니다. 이 가이드의 나머지 부분에서는 사용자의 장치를 Intune에 등록한다는 목표를 달성하는 데 필요한 도구를 준비할 수 있도록 합니다.

## <a name="keys-to-a-successful-migration"></a>마이그레이션 성공의 열쇠

다음은 타사 MDM 공급자에서 Intune으로 마이그레이션할 때의 핵심적인 교훈입니다.

-   통신이 최종 사용자 가동 중지 시간을 최소화하는 열쇠이며 만족도에도 매우 중요합니다.

-   명확하고 구체적인 마이그레이션 지침이 있어야 합니다.

-   Intune에 등록하기 전에 먼저 관리되는 장치를 모두 기존 MDM 공급자에서 등록 취소해야 합니다.

-   장치를 등록 취소하는 방법에 대한 기존 MDM 공급자의 지침을 최종 사용자에게 제공합니다.

-   단계별 방법을 사용합니다. 소규모 파일럿 사용자 그룹부터 시작하여 전체 규모의 배포에 도달할 때까지 사용자의 그룹을 증분 방식으로 추가합니다.

-   각 주기의 지원 센터 로드 및 등록 성공 여부를 모니터링합니다. 다음 마이그레이션을 수행하기 전에 각 그룹에 대해 성공 기준을 평가할 수 있도록 일정에 시간 여유를 둡니다. 파일럿 배포에서는 다음을 확인해야 합니다.

    -   등록 성공 및 실패 비율이 예상 범위 내에 있습니다.

    -   사용자 생산성:

        -   VPN, Wi-Fi, 메일, 인증 등의 회사 리소스가 작동되고 있습니다.

        -   프로비전된 앱을 액세스할 수 있습니다.

    -   데이터 보안:

        -   준수 보고

        -   모바일 앱 보호 적용

-   마이그레이션의 첫 번째 단계에 만족하는 경우 다음 단계에 대해 마이그레이션 주기(아래의 일반적인 마이그레이션 주기의 설명 참조)를 반복합니다.

-   모든 사용자가 Intune에 마이그레이션될 때까지 단계적 주기를 반복합니다.

-   지원 센터 팀이 마이그레이션 캠페인 전반에 걸쳐 최종 사용자를 지원할 준비가 되었는지 확인합니다. 지원 호출 작업을 예측할 수 있을 때까지 자발적인 마이그레이션을 실행합니다.

-   지원 센터에서 나머지 모집단을 처리할 수 있을 때까지 등록 마감일을 설정하지 않아야 합니다.

> [!IMPORTANT] 
> Exchange 또는 SharePoint Online과 같은 리소스에 액세스 제어를 적용하도록 Intune 및 기존 타사 MDM 솔루션을 구성하지 않아야 합니다. 또한 한 번에 하나의 솔루션에만 장치를 등록해야 합니다.

## <a name="next-steps"></a>다음 단계

[2단계: 통신 계획](https://docs.microsoft.com/intune/plan-design/migration-phase2-communication-plan)

