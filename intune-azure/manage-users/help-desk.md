---
title: "기술 지원팀의 문제 해결 포털 | Microsoft Docs"
titleSuffix: Intune Azure preview
description: "기술 지원팀 직원은 문제 해결 포털을 사용하여 사용자의 기술 문제를 해결합니다."
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 03/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1f39c02a-8d8a-4911-b4e1-e8d014dbce95
ms.reviewer: sumitp
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: c8715f96f532ee6bacda231e1147d03226ecbb48
ms.openlocfilehash: 4916b66e1f2eeabb42401645dbece28dad28eb19
ms.contentlocale: ko-kr
ms.lasthandoff: 04/26/2017

---
# <a name="help-users-with-the-troubleshooting-portal-in-microsoft-intune"></a>Microsoft Intune의 문제 해결 포털을 통해 사용자 지원

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

문제 해결 포털을 사용하면 도움말 센터 운영자 및 Intune 관리자가 사용자와 장치를 확인하고 Intune 기술 문제를 해결하는 작업을 수행할 수 있습니다.

## <a name="add-help-desk-operators"></a>지원 센터 운영자 추가
Intune 관리자는 사용자에게 지원 센터 운영자 권한을 할당할 수 있습니다. 지원 센터 사용자는 Intune 포털을 확인할 수는 있지만 문제 해결 워크로드를 벗어나면 관리 작업을 보거나 수행할 수 없습니다.

1. [Azure Portal](https:portal.azure.com)에 Intune 관리자 권한으로 로그인하고 **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
2. 왼쪽 탐색 블레이드에서 **Intune 역할**을 선택합니다.
3. **Intune 역할** 워크로드에서 **지원 센터 연산자**를 선택한 다음 **할당**을 선택합니다.
4. **할당 이름**(필수), **할당 설명**(선택 사항)을 입력한 다음 **구성원(그룹)** 및 **범위(그룹)**을 할당합니다.
5. 이제 지원 데스크 운영자 역할이 있는 구성원이 문제 해결 포털을 사용할 수 있습니다.

Intune 역할에 대한 자세한 내용은 [Intune 역할](https://docs.microsoft.com/intune-azure/access-control/role-based-access-control)을 참조하세요.

## <a name="access-the-troubleshooting-portal"></a>문제 해결 포털 액세스

지원 센터 직원 및 Intune 관리자는 다음 두 가지 방법으로 문제 해결 포털에 액세스할 수 있습니다.
- [Azure Portal](https://portal.azure.com)에서 **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택한 다음 왼쪽 탐색 블레이드에서 **문제 해결**을 선택합니다. 왼쪽 탐색 블레이드에 다른 작업들도 표시되지만 사용할 수는 없습니다.

![사용자 선택 링크가 포함된 Intune 문제 해결 워크로드 스크린샷](media/help-desk-user.png)
- 웹 브라우저에서 [http://aka.ms/intunetroubleshooting](http://aka.ms/intunetroubleshooting)을 엽니다. 문제 해결 포털만 표시됩니다.

## <a name="use-the-troubleshooting-portal"></a>문제 해결 포털 사용

문제 해결 포털에서 **사용자 선택**을 선택하여 사용자의 정보를 볼 수 있습니다. 사용자 정보는 사용자와 장치의 현재 상태를 이해하는 데 유용합니다. 문제 해결 포털에서는 다음 Intune 사용자 및 장치 세부 정보를 보여 줍니다.
- 사용자 계정 정보
- 사용자 그룹 구성원 자격
- 장치 세부 정보

지원 센터 사용자는 장치에서 **원격 잠금**과 같은 원격 작업을 수행할 수도 있습니다.

