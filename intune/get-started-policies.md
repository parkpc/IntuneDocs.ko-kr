---
title: "정책 시작"
titlesuffix: Azure portal
description: "사용자가 장치에서 권한이 없는 작업을 수행하지 않도록 하는 정책을 만듭니다."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1ac74ba5-7441-44ac-98b5-9d8bb8899747
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7d100eeb177e2b47065f0688d9f94b2f4e5c06bc
ms.sourcegitcommit: fa6aaf12611c3e03e38e467806fc30b1d0255e88
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2017
---
# <a name="get-started-with-policies"></a>정책 시작

Intune을 시작하는 주요 목표 중 하나는 회사 정책을 준수하도록 장치를 등록하는 것입니다. 준수 정책은 회사 소유 키오스크와 같은 특수 장치 유형뿐 아니라 개인(Bring Your Own) 장치, 태블릿 및 사용자가 지정되지 않은 장치를 관리하는 데 도움이 됩니다.

![데이터가 매우 적은 규정 준수 대시보드](/intune/media/generic-compliance-dashboard.png)

준수 정책은 모바일 장치에 대해 다음과 같은 관리 기능을 제공합니다.

* 각 사용자가 등록하는 장치 수 규정
* 장치 설정(예: 장치 수준 암호화, 암호 길이, 카메라 사용) 관리
* 앱, 메일 프로필, VPN 프로필 등을 제공합니다.
* 보안 준수 정책에 대한 장치 수준 기준 평가

각 플랫폼에 대한 준수 정책을 개별적으로 만듭니다. 이 연습에서는 iOS에 집중하겠습니다. iOS 장치에 사용할 수 있는 정책은 다음과 같습니다.

* PIN 또는 암호 구성
* 장치 암호화
* 탈옥 장치
* 전자 메일 프로필
* 최소 OS 버전
* 최대 OS 버전

__정책을 만들려면 어떻게 하나요?__

1. [Azure 포털](https://portal.azure.com)에 로그인합니다.
2. **리소스 검색**을 사용하여 **Intune**을 검색합니다.
3. **장치 준수**를 선택합니다.
4. **장치 준수** 블레이드에서 **정책**을 선택합니다.
5. **정책 만들기**를 선택한 다음 **이름** 및 **설명**과 같은 세부 정보를 입력합니다. **iOS**를 **플랫폼**으로 선택합니다.
6. **설정**에서 **시스템 보안**을 선택한 다음 **모바일 장치의 잠금을 해제하는 데 암호 필요**를 **필요**로 전환합니다. **최소 암호 길이**, **필수 암호 유형**, **암호에 포함해야 하는 영숫자가 아닌 문자 수** 등의 다른 규칙을 설정할 수도 있습니다. 정책 설정을 마쳤으면 **확인**을 선택합니다.
7. **정책 만들기** 블레이드로 돌아간 다음 **만들기**를 선택합니다.
8. 정책을 만든 후 **할당**을 선택하여 테스트 그룹에 할당합니다. 테스트 사용자가 포함된 테스트 그룹을 선택한 다음 **저장**을 클릭하여 해당 그룹에 정책을 할당합니다.
9. 몇 분 정도 기다리면 등록된 장치에서 회사 정책 준수를 유지하기 위해 업데이트된 암호가 필요하다는 메시지를 표시합니다. 이 동작은 **iOS용 회사 포털 앱**에서 장치 이름, **동기화** 단추를 차례로 탭하여 수동으로 확인할 수도 있습니다.

## <a name="next-steps"></a>다음 단계

[장치 등록 시작](get-started-enroll.md) - iOS 장치의 전체 등록 과정을 안내하여 등록 과정을 알아봅니다.

## <a name="learn-more"></a>자세한 정보

* [Intune 장치 준수 정책 모니터링](compliance-policy-monitor.md)
* [Intune에서 조건부 액세스 정책을 사용하는 일반적인 방법](conditional-access-intune-common-ways-use.md)
