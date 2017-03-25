---
title: "Intune 지원 계획 개발 | Microsoft 문서"
description: "이 문서의 정보를 활용하여 Microsoft Intune 클라우드 전용 설계 및 구현을 위한 Intune 지원 계획을 개발할 수 있습니다."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b9428769-4333-4778-b677-f23dea1f74da
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 6df87e20011f20b99b91d88e669c67bb97ad2277
ms.openlocfilehash: e21b088dbb7fdcef9996e2b970bb406cab5ee0aa
ms.lasthandoff: 03/13/2017


---

# <a name="develop-an-intune-support-plan"></a>Intune 지원 계획 개발

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Intune 지원 계획이 있으면 Intune 관련 문제를 더 효과적으로 파악하고 해결하며, 최종 사용자의 전반적인 Intune 환경을 개선할 수 있습니다. 다음은 Intune 지원 계획을 개발할 때 고려할 몇 가지 질문입니다.

-   어떤 팀이 Intune 지원의 제공을 담당하나요?

-   지원 조직에 여러 계층(예: 계층 1-3)이 있는 경우 각 계층에 대한 Intune 지원 책임은 무엇인가요?

-   어떤 프로세스가 Intune 지원을 제공하는 데 사용되나요?

-   Intune 지원 교육을 어떻게 제공할 계획인가요?

-   Intune 배포 프로세스의 초기에 지원 팀을 참여시킬 기회는 무엇인가요?

각 영역을 더 자세히 살펴보겠습니다.

## <a name="which-teams-are-responsible-for-providing-support"></a>어떤 팀이 지원의 제공을 담당하나요?

조직에 다양한 지원 계층/수준(1-3)이 있을 수 있습니다. 예를 들어 계층 1과 2는 지원 팀의 일부일 수 있으며, 계층 3에 Intune 배포를 담당하는 MDM 팀의 멤버가 포함될 수 있습니다.

## <a name="what-is-the-support-process"></a>지원 프로세스는 어떻게 되나요?

계층 1은 통상적으로 첫 번째 지원 수준이며, 일반적으로 사용자가 지원 요청을 위해 연락할 첫 번째 계층입니다. 계층 1이 최종 사용자의 문제를 해결할 수 없는 경우 문제를 계층 2로 에스컬레이션하며, 필요한 경우 계층 2는 문제를 계층 3으로 에스컬레이션할 수 있습니다. 또한 Microsoft 지원은 계층 4로 간주될 수 있습니다.

-   [Intune 지원](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune)에 대해 자세히 알아보세요.

초기 프로덕션 출시 단계의 경우 조직에 브리지 또는 Skype 통화에 참여하는&3;계층이 모두 있을 수 있습니다. 다음은 조직이 IT 지원/기술 지원팀 워크플로를 어떻게 구현할 수 있는지를 보여 주는 한 가지 예입니다.

1.  최종 사용자가 등록 문제에 대해 IT 지원/기술 지원팀 계층 1에 연락합니다.

2.  IT 지원/기술 지원팀 계층 1이 근본 원인을 확인할 수 없어 계층 2로 에스컬레이션합니다.

3.  IT 지원/기술 지원팀 계층 2가 조사하지만, 문제를 해결할 수 없어 계층 3으로 에스컬레이션하고 조사를 지원하기 위해 추가 정보를 제공합니다.

4.  IT 지원/기술 지원팀 계층 3이 추가로 조사하여 근본 원인을 알아내고 해결 방법을 계층 2 및 1로 전달합니다.

5.  그러면 IT 지원/기술 지원팀 계층 1이 고객에게 연락하여 해당 문제를 해결합니다.

특히 Intune 출시의 초기 단계에 이러한 유형의 접근 방식을 사용하면 다음과 같은 여러 이점이 부가됩니다.

-   기술 학습 및 확장 지원

-   문제 및 해결 방법의 신속한 파악

-   전반적인 사용자 환경 개선

## <a name="how-you-plan-to-provide-intune-support-training"></a>Intune 지원 교육을 어떻게 제공할 계획인가요?

IT 지원/기술 지원팀 직원에게 Intune 기술 교육을 제공하는 것이 중요합니다. 교육은 적절한 수준으로 제공되고 구체적인 지원 계층 및 책임에 적용되어야 합니다. 조직에서는 Intune MDM 팀이 지원 리더에게 이 교육을 수행하도록 한(트레이너 교육) 후 교육받은 리더가 해당 지원 팀원에게 이 교육을 제공하도록 할 수 있습니다. 이 교육은 일반적으로 2-3시간 동안 제공될 수 있으며, 강의 및 실습을 포함합니다.

Intune 지원 교육 어젠더의 예가 아래에 제공되어 있습니다.

-   Intune 지원 계획 검토

-   Intune 개요

-   일반적인 문제 해결

-   도구 및 리소스

-   Q&A

>[!TIP]
> [추가 리소스](additional-resources.md)에서는 지원 팀이 Microsoft Intune을 확장하는 동안 검토하고 활용하는 데 유용할 수 있는 기술 리소스를 제공합니다.

## <a name="what-opportunities-are-there-to-involve-the-support-team-earlier"></a>초기에 지원 팀을 참여시킬 어떤 기회가 있나요?

Intune 배포 계획 및 파일럿 활동의 초기 단계에 IT 지원/기술 지원팀 직원을 참여시키는 것은 조직에 매우 유익할 수 있습니다. 지원 담당자에게 솔루션을 접하고 귀중한 경험을 쌓을 기회를 제공합니다. 이를 통해 IT 지원/기술 지원팀 직원이 조직 전체 프로덕션 출시를 지원할 준비를 할 수 있습니다.

## <a name="next-section"></a>다음 섹션

다음 섹션에서는 [Intune 설계](section-7-create-an-intune-design.md)에 대한 지침을 제공합니다.

