---
title: "Intune으로 장치 관리"
titleSuffix: Intune on Azure
description: "Intune을 사용하여 관리하는 장치를 보고 해당 장치에 대해 여러 작업을 수행하는 방법을 알아봅니다.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d2412418-d91a-4767-a3d6-bc88bb29caa2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e0fc5337b92ac604a448038f685b27623b6153f9
ms.sourcegitcommit: ee7f69efe9f32a1d6bdeb1fab73d03dbfe1ae58c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2017
---
# <a name="what-is-microsoft-intune-device-management"></a>Microsoft Intune 장치 관리란?


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

**장치** 워크로드는 관리하는 장치에 대한 정보를 제공하고, 이러한 장치에 대해 원격 작업을 수행할 수 있도록 합니다. 이 워크로드에 액세스하려면 다음을 수행합니다.

1. Azure 포털에 로그인합니다.
2. **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
3. **Intune** 블레이드에서 **장치**를 선택합니다.
4. 이제 나열된 원격 장치 작업을 수행할 수 있습니다. 사용 가능한 작업은 장치 플랫폼 및 장치 구성에 따라 다릅니다.

## <a name="available-device-actions"></a>사용 가능한 장치 작업

- [장치 인벤토리 보기](device-inventory.md)
- 다음의 원격 장치 작업 수행:
    - [회사 데이터 제거](device-company-data-remove.md) 
    - [초기화](device-factory-reset.md)
    - [원격 잠금](device-remote-lock.md)
    - [암호 초기화](device-passcode-reset.md)
    - [활성화 잠금 무시](device-activation-lock-bypass.md)
    - [새로 시작](device-fresh-start.md)
    - [분실 모드](device-lost-mode.md)
    - [장치 찾기](device-locate.md)
    - [다시 시작](device-restart.md)
    - [Windows 10 PIN 재설정](device-windows-pin-reset.md)
    - [Android 원격 제어](device-profile-android-teamviewer.md)
    - [장치 동기화](device-sync.md)


## <a name="next-steps"></a>다음 단계

- **장치 작업**을 선택하여 관리하는 장치에서 수행된 작업의 상태를 확인합니다. 
![모니터 장치 작업](./media/monitor-device-actions.png)
