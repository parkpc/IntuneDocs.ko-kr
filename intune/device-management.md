---
title: "Microsoft Intune에서 장치 관리"
titleSuffix: 
description: "Intune을 사용하여 관리하는 장치를 검토하고 해당 장치에 대해 여러 작업을 수행합니다."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/21/2018
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d2412418-d91a-4767-a3d6-bc88bb29caa2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2e69f47e841cb44ab646431d5bd81b9c1d874c64
ms.sourcegitcommit: aafed032492c1b5861d7097a335f9bbb29ce3221
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2018
---
# <a name="what-is-microsoft-intune-device-management"></a>Microsoft Intune 장치 관리란?


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

IT 관리자의 경우 관리되는 장치가 위험으로부터 해당 데이터를 보호하는 동안 최종 사용자가 해당 작업을 수행해야 하는 리소스를 제공하도록 해야 합니다.

**장치** 워크로드는 관리하는 장치에 대한 정보를 제공하고, 이러한 장치에 대해 원격 작업을 수행할 수 있도록 합니다. 이 워크로드에 액세스하려면 다음을 수행합니다.

1. 로그인은 [Azure 포털](https://portal.azure.com)합니다.
2. **모든 서비스** > **Intune**을 선택합니다. Intune은 **모니터링 + 관리** 섹션에 있습니다.
3. **Intune**에서 **장치**를 선택합니다.
4. 장치에 대한 정보를 보고 다음과 같이 원격 장치 작업을 수행할 수 있습니다.
    - **개요** - 관리할 수 있는 등록된 장치의 스냅숏입니다.
    - **모든 장치** - 관리하는 등록된 장치의 목록입니다. **필터** 또는 **열**을 선택하여 표시되는 정보를 구체화합니다. [장치 인벤토리를 확인](device-inventory.md)하려는 장치를 선택합니다.
    - **Azure AD 장치** - Azure AD(Active Directory)로 등록되거나 조인된 장치 목록입니다. [Azure AD 장치 관리](https://docs.microsoft.com/azure/active-directory/device-management-introduction)에 대해 자세히 알아봅니다.
    - **장치 작업** - 작업, 해당 상태, 작업을 시작한 사용자 및 시간을 비롯한 원격 작업의 기록은 장치에서 수행됩니다.

        ![장치 작업 모니터링 스크린샷](./media/monitor-device-actions.png)

    - **감사 로그** - 감사 로그는 Microsoft Intune에서 변경을 생성하는 활동 레코드를 제공합니다. [감사 로그](monitor-audit-logs.md)에 대해 자세히 알아봅니다.
    - **TeamViewer 커넥터** - TeamViewer 서비스를 사용하면 Intune에서 관리되는 Android 장치의 사용자가 IT 관리자의 원격 지원을 받을 수 있습니다. [TeamViewer](device-profile-android-teamviewer.md)에 대해 자세히 알아봅니다.
    - **도움말 및 지원** - 문제를 해결하거나, 지원을 요청하거나, Intune 상태를 볼 수 있습니다.  
    
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
