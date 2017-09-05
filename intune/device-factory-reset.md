---
title: "Intune을 사용하여 장치를 출하 시 설정으로 재설정"
titleSuffix: Intune on Azure
description: "관리하는 장치를 Intune에서 출하 시 설정으로 재설정하는 방법을 알아봅니다.\""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8eff9b53-eef2-4c50-8aee-556bc49d69f2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: fd7273d6c5f75a675d7b01df4225a96fd3a5f821
ms.sourcegitcommit: 10e3ab2aeb79a1fb2243bef2748ccc003fdd4cc7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/02/2017
---
# <a name="reset-intune-managed-devices-to-factory-settings"></a>Intune 관리 장치를 출하 시 설정으로 재설정


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

**초기화**를 수행하면 장치가 기본 설정으로 돌아갑니다. 장치가 더 이상 Intune에서 관리되지 않으며 회사 및 개인 데이터가 모두 제거됩니다. 이 작업은 취소할 수 없습니다.

## <a name="supported-platforms"></a>지원되는 플랫폼

- Windows - Windows 8.1 이상(EAS 관리 장치 아님)에서 지원됨
- Windows Phone - 지원됨
- iOS - 지원됨
- macOS - 지원되지 않음
- Android - 지원됨(Android for Work는 지원되지 않음)

## <a name="how-to-reset-a-device-to-factory-settings"></a>장치를 공장 설정으로 재설정하는 방법

1. Azure 포털에 로그인합니다.
2. **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
3. **Intune** 블레이드에서 **장치**를 선택합니다.
4. **장치 및 그룹** 블레이드에서 **모든 장치**를 선택합니다.
5. 관리하는 장치 목록에서 장치를 선택한 다음 **초기화** 장치 원격 작업을 선택합니다.

## <a name="next-steps"></a>다음 단계

방금 수행한 작업의 상태를 확인하려면 **장치 및 그룹** 블레이드에서 **장치 작업**을 선택합니다.
