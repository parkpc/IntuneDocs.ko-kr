---
title: "Intune 출시 통신 계획 개발 | Microsoft 문서"
description: "이 문서의 정보를 활용하여 Microsoft Intune 클라우드 전용 설계 및 구현을 위한 출시 통신 계획을 개발할 수 있습니다."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 393ebe75-d001-485a-b81c-6361c8b5e6ee
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: f807d6e4b20b98ecf622d1ebdd9db33b132a2e6a
ms.openlocfilehash: 96127663a794a0c433cedbe7ef5269d65724c3fe


---

# <a name="develop-an-intune-rollout-communication-plan"></a>Intune 출시 통신 계획 개발

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

이전 섹션에서 Intune 관리 대상으로 지정될 조직 그룹의 확인, Intune 출시에 대한 타임라인, 등록 접근 방식, Intune 출시 계획 개발 등을 검토했습니다. 이제 Intune 출시에 대한 통신 계획을 개발해야 합니다. Intune 출시 통신 계획에는 다음과 같은 네 영역이 포함되어야 합니다.

-   전달할 정보

-   통신에 사용되는 배달 방법

-   통신 수신 대상

-   통신 타임라인

각 영역을 더 자세히 살펴보겠습니다.

## <a name="what-needs-to-be-communicated"></a>통신을 통해 전달해야 하는 내용

전달할 정보는 통신 중인 Intune 출시 프로세스의 시기에 따라 결정됩니다. 일부 조직에서는 웨이브(출시 프로세스 단계)에 따라 해당 조직 그룹 및 사용자와 통신할 수 있습니다. 먼저 Intune 출시 킥오프부터 시작하여 차례로 등록 전, 등록 후 통신을 수행합니다. 각 웨이브에서 전달될 수 있는 정보의 유형에 대해 살펴보겠습니다.

**킥오프 웨이브:** Intune 프로젝트 자체를 소개하는 광범위한 통신으로, Intune이 무엇인지와 Intune을 채택하는 이유(예: 조직 및 사용자에 대한 이점) 그리고 배포 및 출시 활동에 대한 개략적 계획과 같은 영역을 다룹니다.

**등록 전 웨이브**: Intune에 대한 추가 정보, 보완 제공 사항(예: Office, Outlook, OneDrive), 사용자 리소스, 조직 그룹/사용자가 Intune을 받기로 예약된 시기에 대한 구체적인 타임라인이 포함된 광범위 통신입니다.

**등록 웨이브:** Intune을 받기로 예약된 조직 그룹/사용자를 대상으로 하는 통신으로, 사용자에게 Intune을 받을 준비가 되었음을 알려 주고, 도움을 요청하거나 질문할 수 있는 연락처 정보와 함께 등록 지침을 제공합니다.

**등록 후 웨이브:** Intune에서 등록한 조직 그룹/사용자를 대상으로 하는 통신으로, 사용자에게 유용한 추가 리소스를 제공하고 등록하는 동안과 이후의 환경에 대한 피드백을 수집합니다.

## <a name="communication-delivery-methods"></a>통신 배달 방법

대상 조직 그룹 및 사용자에게 Intune 출시 정보를 전달하는 데 활용할 수 있는 몇 가지 배달 방법이 있습니다. 통신 배달 방법 및 함께 사용할 수 있는 웨이브의 몇 가지 예가 아래에 나와 있습니다.

-   킥오프 웨이브에 사용되는 조직 전체의 오프라인 및/또는 Skype 회의

-   등록 전, 등록 및 등록 후 웨이브에 사용되는 메일

-   모든 웨이브에 사용되는 조직 웹 사이트

-   킥오프 및 등록 전 웨이브에 사용되는 Yammer 및 포스터/전단

## <a name="communications-timeline"></a>통신 타임라인

전달할 내용 및 통신에 사용되는 방법을 결정한 후에는 다음 단계로 통신을 수신할 시기 및 대상이 포함된 통신 타임라인을 결정합니다. 예를 들어 초기 Intune 프로젝트 킥오프 통신은 전체 조직 또는 하위 집합을 대상으로 할 수 있으며, Intune 출시가 시작되기 전에 몇 주에 걸쳐 수행될 수 있습니다. 그런 다음, 해당 Intune 출시 일정에 맞춰 조직 그룹 및 사용자에게 웨이브에 따라 정보를 전달할 수 있습니다. 개략적인 Intune 출시 통신 계획의 한 예가 아래에 나와 있습니다.

  | **통신 계획** | **7월** | **8월** | **9월** | **10월** |
|:---:|:---:|:---:|:---:|:---:|
| 웨이브 1  | 모두 |  |  |  |                                                         
| 킥오프 회의 | 첫째 주 |  |  |  |                                                         
| 웨이브 2 | IT | 영업 및 마케팅 | 소매 | HR, 재무 및 임원 |
| 출시 전 메일 1 | 첫째 주 | 첫째 주 | 첫째 주 | 첫째 주 |
| 웨이브 3 | IT | 영업 및 마케팅 | 소매 | HR, 재무 및 임원 |
| 출시 전 메일 2 | 둘째 주 | 둘째 주 | 둘째 주 | 둘째 주 |
| 웨이브 4 | IT | 영업 및 마케팅 | 소매 | HR, 재무 및 임원 |
| 등록 메일 | 셋째 주 | 셋째 주 | 셋째 주 | 셋째 주 |
| 웨이브 5 | IT | 영업 및 마케팅 | 소매 | HR, 재무 및 임원 |
| 등록 후 메일 | 넷째 주 | 넷째 주 | 넷째 주 | 넷째 주 |

## <a name="next-section"></a>다음 섹션

다음 섹션에서는 [지원 계획 개발](section-6-develop-a-support-plan.md)에 대한 지침을 제공합니다.



<!--HONumber=Dec16_HO5-->


