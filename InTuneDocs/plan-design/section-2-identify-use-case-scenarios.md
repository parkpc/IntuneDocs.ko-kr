---
title: "Intune 사용 사례 시나리오 확인 | Microsoft 문서"
description: "이 문서의 정보를 활용하여 Microsoft Intune 클라우드 전용 구현을 위한 Intune 사용 사례 및 하위 사용 사례 시나리오를 확인할 수 있습니다."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4b3c9af9-78da-44d2-8bd2-3f0f8885952d
ms.reviewer: jeffbu, cgerth
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: f807d6e4b20b98ecf622d1ebdd9db33b132a2e6a
ms.openlocfilehash: c834b0282b8f9b47566ab1da2125d993ba8febdf


---

# <a name="identify-intune-use-case-scenarios"></a>Intune 사용 사례 시나리오 확인

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

모바일 장치 관리 사용 사례 시나리오에서는 사용자 유형 또는 역할 및 장치의 소유권(예: 회사 또는 개인)을 설명합니다. 사용자 사례 시나리오를 통해 사용자를 관리 가능한 그룹으로 분할할 수 있으므로 이 시나리오는 유용합니다. 사용 사례 시나리오의 확인은 Intune 배포에 대한 계획 프로세스의 중요한 부분입니다.

조직이 Intune 사용 사례 시나리오뿐만 아니라 조직 그룹 및 각 사용 사례와 관련된 모바일 장치 플랫폼을 확인하는 데에도 도움이 되는 몇 가지 예를 살펴보겠습니다.

## <a name="use-case-scenarios"></a>사용 사례 시나리오

배포에 대한 주요 사용 사례 시나리오를 확인할 수 있도록 먼저 조직의 Intune 배포 목적과 목표를 참조할 수 있습니다. Intune 배포 계획의 범위 내에서 다음 질문에 대답해야 합니다.

-   회사 소유 장치를 지원할 계획인가요?

-   개인 소유 장치(BYOD)를 지원할 계획인가요?

### <a name="sub-use-case-scenarios"></a>하위 사용 사례 시나리오

주요 사용 사례 시나리오를 확인한 후 각 사용 사례 시나리오에 하위 사용 사례가 포함되어 있는지도 확인해야 합니다. 예를 들어 조직은 다음과 같은 추가 하위 사용 사례를 포함하는 회사 사용 사례 시나리오를 지원하기 위한 요구 사항을 확인할 수 있습니다.

-   정보 근로자

-   임원

-   키오스크

다음은 사용 사례 및 하위 사용 사례 시나리오의 몇 가지 예입니다. 아래 표를 활용하여 조직의 사용 사례 및 하위 사용 사례 시나리오를 입력할 수 있습니다.

| **사용 사례** | **하위 사용 사례** |
|:---:|:---:|
| 회사 | 정보 근로자 |              
| 회사 | 임원 |           
| 회사 | 키오스크 |
| BYOD | 정보 근로자 |           
| BYOD | 임원 |

## <a name="identify-organizational-groups-associated-with-use-case-scenarios"></a>사용 사례 시나리오와 관련된 조직 그룹 확인

이제 각 사용 사례 및 하위 사용 사례 시나리오와 관련된 조직 그룹을 확인해야 합니다. 다음은 조직의 정보를 입력하는 데 템플릿으로 사용할 수 있는 사용 사례 및 하위 사용 사례 시나리오와 관련된 조직 그룹의 몇 가지 예입니다.

| **사용 사례** | **하위 사용 사례** | **조직 그룹** |
|:---:|:---:|:---:|
| 회사 | 정보 근로자 | HR, 재무 |               
| 회사 | 임원 | HR, 재무 |            
| 회사 | 키오스크 | 소매 |
| BYOD | 정보 근로자 | 마케팅, 영업 |            
| BYOD | 임원 | 마케팅, 영업 |

## <a name="identify-mobile-device-platforms-for-use-case-scenarios"></a>사용 사례 시나리오에 대한 모바일 장치 플랫폼 확인

여기에서 각 사용 사례 시나리오와 관련된 모바일 장치 플랫폼을 확인합니다. 예를 들어 회사 사용 사례 시나리오에서 iOS 및 Android Samsung KNOX 장치 플랫폼을 지원할 수 있으며, BYOD 정책에 Android(비 삼성 KNOX) 및 Windows 10 Mobile과 같은 추가 모바일 장치 플랫폼에 대한 지원을 포함할 수 있습니다. 다음은 각 사용 사례 시나리오와 관련된 모바일 장치 플랫폼의 예입니다. 아래 표를 사용하여 해당 사용 사례 시나리오와 관련된 조직의 장치 플랫폼을 입력할 수 있습니다.

| **사용 사례** | **하위 사용 사례** | **그룹** | **장치 플랫폼** |   
|:---:|:---:|:---:|:---:|
| 회사 | 정보 근로자 | HR, 재무 | iOS |                                                           
| 회사 | 임원 | HR, 재무 | iOS |                                                           
| 회사 | 키오스크 | 소매 | Android |
| BYOD | 정보 근로자 | 마케팅, 영업 | iOS |                                                           
| BYOD | 임원 | 마케팅, 영업 | iOS |

## <a name="next-section"></a>다음 섹션

다음 섹션에서는 [각 사용 사례 시나리오에 대한 Intune 요구 사항을 확인하는 방법](section-3-determine-use-case-requirements.md)에 대한 지침을 제공합니다.



<!--HONumber=Dec16_HO5-->


