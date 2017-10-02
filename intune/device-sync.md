---
title: "Intune으로 장치 동기화"
titlesuffix: Azure portal
description: "Intune으로 장치를 동기화하여 최신 정책과 작업을 가져오는 방법을 알아봅니다.”"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 02ad249e-f098-421f-861f-6b2ff733ac7c
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ab24b147b32c94ba51728c0c223de3e6c92dd215
ms.sourcegitcommit: cf7f7e7c9e9cde5b030cf5fae26a5e8f4d269b0d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2017
---
# <a name="sync-devices-with-intune-to-get-the-latest-policies-and-actions"></a>Intune으로 장치를 동기화하여 최신 정책과 작업을 가져오기


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

장치 **동기화** 작업은 선택한 장치가 Intune을 사용하여 즉시 체크 인하도록 강제합니다. 장치가 체크 인하면 장치에 할당된 보류 중인 작업 또는 정책을 즉시 받게 됩니다.  이 작업을 사용하면 예약된 다음 체크 인을 기다리지 않고 즉시 할당한 정책의 유효성을 검사하고 문제를 해결할 수 있습니다.

## <a name="supported-platforms"></a>지원되는 플랫폼

- Windows - 지원됨
- Windows Phone - 지원됨
- iOS - 지원됨
- macOS - 지원됨
- Android - 지원됨

## <a name="how-to-sync-a-device"></a>장치를 동기화하는 방법

1. Azure 포털에 로그인합니다.
2. **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
3. **Intune** 블레이드에서 **장치**를 선택합니다.
4. **장치 및 그룹** 블레이드에서 **모든 장치**를 선택합니다.
5. 관리하는 장치 목록에서 장치를 선택한 다음 **동기화** 원격 작업을 선택합니다.
7. **예**를 선택하여 작업을 확인합니다.

## <a name="next-steps"></a>다음 단계

**장치 작업**을 선택하여 동기화 작업의 상태를 확인합니다. 
