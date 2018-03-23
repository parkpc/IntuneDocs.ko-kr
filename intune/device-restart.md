---
title: Intune을 사용하여 원격으로 장치 다시 시작
titlesuffix: Microsoft Intune
description: Microsoft Intune에서 다시 시작 장치 작업을 사용하여 장치를 원격으로 다시 시작하는 방법을 알아봅니다.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: c707e0c4-391a-4bad-9dfd-9a7799c48dd5
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1bd5a01b8aac91c3bd6ea033d62d41e19aab65f8
ms.sourcegitcommit: e30fb2375fb79f67e5c1e4ed7b2c21fb9ca80c59
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2018
---
# <a name="remotely-restart-devices-with-intune"></a>Intune을 사용하여 원격으로 장치 다시 시작


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

**다시 시작** 장치 작업을 수행하면 선택한 장치가 다시 시작됩니다. 장치 소유자에게 다시 시작 알림이 자동으로 제공되지 않으므로 작업이 손실될 수 있습니다.

## <a name="supported-platforms"></a>지원되는 플랫폼

- Windows - Windows 8.1 이상에서 지원됨
- Windows Phone - Windows Phone 8.1 이상에서 지원됨
- iOS - 지원됨

    > [!Note]  
    > 이 명령은 감독되는 장치 및 **장치 잠금** 액세스 권한에 필요합니다. 장치를 즉시 다시 시작합니다. 암호로 잠긴 iOS 장치는 다시 시작한 후 Wi-Fi 네트워크에 다시 가입되지 않습니다. 다시 시작한 후 서버와 통신하지 못할 수도 있습니다.
- macOS - 지원되지 않음
- Android - 지원되지 않음

## <a name="how-to-restart-a-device"></a>장치를 다시 시작하는 방법

1. 로그인은 [Azure 포털](https://portal.azure.com)합니다.
2. **모든 서비스** > **Intune**을 선택합니다. Intune은 **모니터링 + 관리** 섹션에 있습니다.
3. **Intune** 블레이드에서 **장치**를 선택합니다.
4. **장치** 블레이드에서 **모든 장치**를 선택합니다.
5. 관리하는 장치 목록에서 iOS 장치를 선택하고 **자세히...**를 선택한 다음, **다시 시작** 장치 원격 작업을 선택합니다.

## <a name="next-steps"></a>다음 단계

방금 수행한 작업의 상태를 확인하려면 **장치** 블레이드에서 **장치 작업**을 선택합니다.
