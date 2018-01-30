---
title: "Intune으로 장치 프로필을 할당하는 방법"
titlesuffix: Azure portal
description: "Intune 장치 프로필을 만든 후 이 항목의 내용을 참조하여 장치에 프로필을 할당하는 방법을 알아봅니다.\""
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 07/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f6f5414d-0e41-42fc-b6cf-e7ad76e1e06d
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ef03eeab32050559d34d3d7d580c06c21f5ffb05
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2018
---
# <a name="how-to-assign-microsoft-intune-device-profiles"></a>Microsoft Intune 장치 프로필을 할당하는 방법

## <a name="assign-a-device-profile"></a>장치 프로필 할당

1. Azure 포털에 로그인합니다.
2. **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
3. **Intune** 블레이드에서 **장치 구성**을 선택합니다.
1. **장치 구성** 블레이드에서 **관리** > **프로필**을 선택합니다.
2. 프로필 목록 블레이드에서 관리할 프로필을 선택한 다음 <*프로필 이름*> **보고서** 블레이드에서 **관리** > **할당**을 선택합니다.
3. 다음 블레이드에서 **포함**(그룹 포함) 또는 **제외**(그룹 제외)를 선택한 다음 **그룹 선택**을 선택합니다.
![프로필 할당에서 그룹을 제외하고 포함합니다.](./media/group-include-exclude.png)
4. **그룹 선택** 블레이드에서 할당에 포함하거나 제외할 Azure AD 그룹을 선택합니다. **Ctrl** 키를 누른 상태로 여러 그룹을 선택할 수 있습니다.
4. 완료했으면 **그룹 선택** 블레이드에서 **선택**을 선택합니다.



## <a name="how-to-exclude-groups-from-a-device-profile-assignment"></a>장치 프로필 할당에서 그룹을 제외하는 방법

Intune 장치 구성 프로필을 통해 정책 할당에서 그룹을 제외할 수 있습니다. 예를 들어 **모든 회사 사용자** 그룹에 장치 프로필을 할당하되 **Senior Management Staff** 그룹의 구성원을 모두 제외할 수 있습니다.

할당에서 그룹을 제외하는 경우 사용자 또는 장치 그룹 중 하나만 제외하고 그룹을 섞어서 제외하지 마세요. Intune은 그룹을 제외할 때 사용자와 장치 간의 연결을 고려하지 않습니다. 장치 그룹을 제외하고 사용자 그룹을 포함하면 필요한 결과를 얻을 가능성이 적습니다. 그룹을 섞어서 사용하거나 다른 충돌이 있는 경우 포함이 제외보다 우선 적용됩니다.

예를 들어 키오스크 장치를 제외한 조직의 모든 장치에 장치 프로필을 할당하려고 합니다. **모든 사용자** 그룹을 포함하되 **모든 장치** 그룹을 제외합니다.

이 경우 사용자 장치가 **모든 장치** 그룹에 속하는 경우에도 모든 사용자와 해당 장치에 정책이 적용됩니다. 

제외는 그룹의 직접 구성원만 평가하고 사용자와 연결된 장치는 포함하지 않습니다. 그러나 사용자가 없는 장치는 **모든 사용자** 그룹에 대한 연결이 없기 때문에 정책이 적용되지 않습니다. 

**모든 장치**를 포함하되 **모든 사용자**를 제외하면 모든 장치에 정책이 적용됩니다. 이 경우 연결된 사용자가 있는 장치를 이 정책에서 제외하기 위한 것입니다. 하지만 제외 기능은 직접적인 그룹 구성원만 비교하기 때문이 효과가 없습니다. 

>[!Tip]
>현재 준수 정책 또는 앱 할당에는 제외를 사용할 수 없습니다. 할당에서 구성원을 제외하려면 사용 가능 및 적용할 수 없음 할당 의도를 사용할 수 있습니다. 예를 들어 **사용 가능** 의도로 **모든 회사 사용자**에게, 그리고 **적용할 수 없음** 의도로 **Senior Management Staff**에게 앱을 할당합니다. **Senior Management Staff** 그룹의 사용자를 *제외한* 모든 사용자에게 앱이 할당됩니다. **필요** 의도로 **모든 회사 사용자**에게 앱을 할당하면 **Senior Management Staff** 그룹의 사용자가 제외되지 않습니다.
 
    
## <a name="next-steps"></a>다음 단계
장치 프로필 할당을 모니터링하는 데 유용한 정보는 [장치 프로필을 모니터링하는 방법](device-profile-monitor.md)을 참조하세요.
