---
title: "Intune으로 장치 관리"
titlesuffix: Azure portal
description: "Intune을 사용하여 관리하는 장치를 보고 해당 장치에 대해 여러 작업을 수행하는 방법을 알아봅니다.\""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/31/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d2412418-d91a-4767-a3d6-bc88bb29caa2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ca40eee8a53fa3e8b2610ce414f0037180d4beaf
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/09/2017
---
# <a name="what-is-microsoft-intune-device-management"></a>Microsoft Intune 장치 관리란?


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

**장치** 워크로드는 관리하는 장치에 대한 정보를 제공하고, 이러한 장치에 대해 원격 작업을 수행할 수 있도록 합니다. 이 워크로드에 액세스하려면 다음을 수행합니다.

1. Azure 포털에 로그인합니다.
2. **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
3. **Intune** 블레이드에서 **장치**를 선택합니다.
4. 장치에 대한 정보를 보고 나열된 원격 장치 작업을 수행할 수 있습니다.

## <a name="available-device-actions"></a>사용 가능한 장치 작업
사용 가능한 작업은 장치 플랫폼 및 장치 구성에 따라 다릅니다.

- [장치 인벤토리 보기](device-inventory.md)
- 다음의 원격 장치 작업 수행:
    - [회사 데이터 제거](devices-wipe.md#remove-company-data)
    - [초기화](devices-wipe.md#factory-reset)
    - [원격 잠금](device-remote-lock.md)
    - [암호 초기화](device-passcode-reset.md)
    - [활성화 잠금 무시](device-activation-lock-bypass.md)(iOS만 해당)
    - [새로 시작](device-fresh-start.md)(Windows만 해당)
    - [분실 모드](device-lost-mode.md)(iOS만 해당)
    - [장치 찾기](device-locate.md)(iOS만 해당)
    - [다시 시작](device-restart.md)(Windows만 해당)
    - [Windows 10 PIN 재설정](device-windows-pin-reset.md)
    - [Android 원격 제어](device-profile-android-teamviewer.md)
    - [장치 동기화](device-sync.md)


## <a name="next-steps"></a>다음 단계

- **장치 작업**을 선택하여 관리하는 장치에서 수행된 작업의 상태를 확인합니다.
![모니터 장치 작업](./media/monitor-device-actions.png)
