---
title: "Intune으로 장치 관리"
titleSuffix: Intune on Azure
description: "Intune을 사용하여 관리하는 장치를 보고 해당 장치에 대해 여러 작업을 수행하는 방법을 알아봅니다.\""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: dougeby
ms.date: 08/31/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d2412418-d91a-4767-a3d6-bc88bb29caa2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1b034e144aa43d239874b484acb2a40be12aff7c
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2018
---
# <a name="what-is-microsoft-intune-device-management"></a>Microsoft Intune 장치 관리란?


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

IT 관리자의 경우 관리되는 장치가 위험으로부터 해당 데이터를 보호하는 동안 최종 사용자가 해당 작업을 수행해야 하는 리소스를 제공하도록 해야 합니다.

**장치** 워크로드는 관리하는 장치에 대한 정보를 제공하고, 이러한 장치에 대해 원격 작업을 수행할 수 있도록 합니다. 이 워크로드에 액세스하려면 다음을 수행합니다.

1. Azure 포털에 로그인합니다.
2. **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
3. **Intune**에서 **장치**를 선택합니다.
4. 장치에 대한 정보를 보고 다음과 같이 원격 장치 작업을 수행할 수 있습니다.
    - **개요** - 관리할 수 있는 등록된 장치의 스냅숏입니다.
    - **모든 장치** - 관리하는 등록된 장치의 목록입니다. **필터** 또는 **열**을 선택하여 표시되는 정보를 구체화합니다. [장치 인벤토리를 확인](device-inventory.md)하려는 장치를 선택합니다.
    - **Azure AD 장치** - Azure AD(Active Directory)로 등록되거나 조인된 장치 목록입니다. [Azure AD 장치 관리](https://docs.microsoft.com/azure/active-directory/device-management-introduction)에 대해 자세히 알아봅니다.
    - **장치 작업** - 작업, 해당 상태, 작업을 시작한 사용자 및 시간을 비롯한 원격 작업의 기록은 장치에서 수행됩니다.

    ![장치 작업 모니터링](./media/monitor-device-actions.png)

    - **TeamViewer** - TeamViewer 서비스를 사용하면 Intune에서 관리되는 Android 장치의 사용자가 IT 관리자의 원격 지원을 받을 수 있습니다. [TeamViewer](device-profile-android-teamviewer.md)에 대해 자세히 알아봅니다.

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
