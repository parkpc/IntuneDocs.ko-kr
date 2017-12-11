---
title: "Intune을 사용하여 관리 장치 원격 잠금"
titlesuffix: Azure portal
description: "Intune을 사용하여 관리하는 장치를 원격으로 잠그는 방법을 알아봅니다.\""
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 11/21/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b67f285-229d-4a0f-ae34-0402a20b4518
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8905b97a5912010a2516788a8da66441fc6f89ae
ms.sourcegitcommit: 520eb7712625e129b781e2f2b9fe16f9b9f3d08a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/01/2017
---
# <a name="remotely-lock-managed-devices-with-intune"></a>Intune을 사용하여 관리 장치 원격 잠금


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

**원격 잠금** 장치 작업을 수행하면 선택한 장치가 잠깁니다. 장치 소유자가 암호를 사용하여 잠금을 해제해야 합니다. PIN 또는 암호가 설정된 장치만 원격으로 잠글 수 있습니다.

## <a name="supported-platforms"></a>지원되는 플랫폼

- Windows - 지원되지 않음
- Windows Phone - Windows Phone 8.1 이상에서 지원됨
- iOS - 지원됨
- macOS - 지원됨

    > [!Note]  
    > 6자리 복구 PIN을 설정합니다. 잠기면 **장치 개요** 블레이드에 다른 장치 작업이 전송될 때까지 PIN이 표시됩니다.
- Android - 지원됨

## <a name="how-to-remote-lock-a-device"></a>장치를 원격으로 잠그는 방법

1. Azure 포털에 로그인합니다.
2. **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
3. **Intune** 블레이드에서 **장치**를 선택합니다.
4. **장치 및 그룹** 블레이드에서 **모든 장치**를 선택합니다.
5. 관리하는 장치 목록에서 장치를 선택한 다음 **원격 잠금** 장치 원격 작업을 선택합니다.

## <a name="next-steps"></a>다음 단계

방금 수행한 작업의 상태를 확인하려면 **장치 및 그룹** 블레이드에서 **장치 작업**을 선택합니다.
