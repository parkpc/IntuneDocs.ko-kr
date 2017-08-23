---
title: "Intune을 사용하여 원격으로 장치 다시 시작"
titleSuffix: Intune on Azure
description: "다시 시작 장치 작업을 사용하여 장치를 원격으로 다시 시작하는 방법을 알아봅니다.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/27/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c707e0c4-391a-4bad-9dfd-9a7799c48dd5
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5278179f22d174de6e97aa990bbe8761d8c8f8f8
ms.sourcegitcommit: ee7f69efe9f32a1d6bdeb1fab73d03dbfe1ae58c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2017
---
# <a name="remotely-restart-devices-with-intune"></a>Intune을 사용하여 원격으로 장치 다시 시작


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

**다시 시작** 장치 작업을 수행하면 선택한 장치가 다시 시작됩니다. 장치 소유자에게 다시 시작 알림이 자동으로 제공되지 않으므로 작업이 손실될 수 있습니다.

## <a name="supported-platforms"></a>지원되는 플랫폼

- Windows - Windows 8.1 이상에서 지원됨
- Windows Phone - Windows Phone 8.1 이상에서 지원됨
- iOS - 지원되지 않음
- macOS - 지원되지 않음
- Android - 지원되지 않음

## <a name="how-to-restart-a-device"></a>장치를 다시 시작하는 방법

1. Azure 포털에 로그인합니다.
2. **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
3. **Intune** 블레이드에서 **장치**를 선택합니다.
4. **장치 및 그룹** 블레이드에서 **모든 장치**를 선택합니다.
5. 관리하는 장치 목록에서 장치를 선택한 다음 **다시 시작** 장치 원격 작업을 선택합니다.

## <a name="next-steps"></a>다음 단계

방금 수행한 작업의 상태를 확인하려면 **장치 및 그룹** 블레이드에서 **장치 작업**을 선택합니다.
