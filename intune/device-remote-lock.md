---
title: "Intune을 사용하여 관리 장치 원격 잠금"
titlesuffix: Azure portal
description: "Intune을 사용하여 관리하는 장치를 원격으로 잠그는 방법을 알아봅니다.\""
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 01/22/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b67f285-229d-4a0f-ae34-0402a20b4518
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ecd7fa03b35e91b5a77906858fb251348796704d
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2018
---
# <a name="remotely-lock-managed-devices-with-intune"></a>Intune을 사용하여 관리 장치 원격 잠금


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

**원격 잠금** 장치 작업을 수행하면 선택한 장치가 잠깁니다. 장치 소유자가 암호를 사용하여 잠금을 해제해야 합니다. PIN 또는 암호가 설정된 장치만 원격으로 잠글 수 있습니다.

## <a name="supported-platforms"></a>지원되는 플랫폼

원격 잠금은 다음 플랫폼에서 지원됩니다.

|플랫폼|지원 상태|
|---|---|
|Android|예|
|iOS|예|
|macOS|예|
|Windows 10|예|
|Windows 10 Mobile|예|
|Windows Phone|Windows Phone 8.1 이상 지원|

> [!NOTE]  
> macOS 장치의 경우 6자리 복구 PIN을 설정합니다. 잠기면 **장치 개요** 블레이드에 다른 장치 작업이 전송될 때까지 PIN이 표시됩니다.

## <a name="how-to-remote-lock-a-device"></a>장치를 원격으로 잠그는 방법

1. Azure 포털에 로그인합니다.
2. **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
3. **Intune** 블레이드에서 **장치**를 선택합니다.
4. **장치 및 그룹** 블레이드에서 **모든 장치**를 선택합니다.
5. 관리하는 장치 목록에서 장치를 선택한 다음 **원격 잠금** 장치 원격 작업을 선택합니다.

## <a name="next-steps"></a>다음 단계

방금 수행한 작업의 상태를 확인하려면 **장치 및 그룹** 블레이드에서 **장치 작업**을 선택합니다.
