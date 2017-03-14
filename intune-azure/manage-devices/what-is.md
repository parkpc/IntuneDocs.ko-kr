---
title: "Intune으로 장치 관리"
titleSuffix: Intune Azure preview
description: "Intune Azure 미리 보기: Intune을 사용하여 관리하는 장치를 보고 여러 작업을 수행하는 방법을 알아봅니다."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: d5d7b87f58604b93ba3b65d5d264a0a5e3743d45
ms.lasthandoff: 02/18/2017


---

# <a name="what-is-microsoft-intune-device-management"></a>Microsoft Intune 장치 관리란? 


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

**장치 및 그룹** 워크로드는 관리하는 장치에 대한 정보를 제공하고, 이러한 장치에 대해 원격 작업을 수행할 수 있도록 합니다. 이 워크로드에 액세스하려면 다음을 수행합니다.

1. Azure 포털에 로그인합니다.
2. **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
3. **Intune** 블레이드에서 **장치 및 그룹**을 선택합니다.

    ![장치 및 그룹 워크로드](./media/devices-and-groups-workload.png)

이제 다음 중 하나를 선택합니다.

- **개요** - 등록한 장치 및 각 장치에서 실행하는 운영 체제에 대한 정보를 가져옵니다.
- **관리** - **모든 장치**를 선택하면 관리하는 모든 장치 목록이 표시됩니다.
    목록에서 이러한 장치 중 하나를 선택하면 <*장치 이름*> **개요** 블레이드가 열립니다. 여기서 다음 중 하나를 선택할 수 있습니다.
    - **개요** - 이름, 소유자, BYOD 장치인지 여부, 마지막으로 체크 인한 시간 등 장치에 대한 일반 정보를 표시합니다. 또한 장치에서 다음과 같은 원격 작업을 수행할 수 있습니다(일부 작업은 일부 장치 플랫폼에서 지원되지 않음).
        - **회사 데이터 제거** - Intune에서 관리하는 회사 데이터만 제거합니다. 장치에서 개인 데이터를 제거하지 않습니다. 장치가 더 이상 Intune에서 관리되지 않으며 더 이상 회사 리소스에 액세스할 수 없습니다(Azure Active Directory에 가입된 Windows 장치에 대해 지원되지 않음).
        - **초기화** - 기본 설정으로 돌아갑니다. 장치가 더 이상 Intune에서 관리되지 않으며 회사 및 개인 데이터가 모두 제거됩니다. 이 작업은 취소할 수 없습니다.
        - **원격 잠금** - 장치를 잠급니다. 장치 소유자가 암호를 사용하여 잠금을 해제해야 합니다. PIN 또는 암호가 설정된 장치만 원격으로 잠글 수 있습니다.
        - **암호 재설정** - <*장치 이름*> **개요** 블레이드에 표시되는 장치의 새 암호를 생성합니다.
        - **활성화 잠금 무시** - 사용자의 Apple ID와 암호 없이 iOS 장치에서 활성화 잠금을 제거합니다. 활성화 잠금을 무시한 후 내 iPhone 앱 찾기가 시작되면 장치에서 활성화 잠금이 다시 켜집니다. 장치에 실제로 액세스할 수 있는 경우에만 활성화 잠금을 무시합니다.
        - **손실된 모드** - 장치가 도난된 경우 손실된 모드를 설정할 수 있습니다. 이를 통해 장치의 잠금 화면에 표시되는 메시지 및 전화 번호를 지정할 수 있습니다.
        - **다시 시작** - 장치가 다시 시작되도록 합니다. 장치 소유자에게 다시 시작 알림이 자동으로 제공되지 않으므로 작업이 손실될 수 있습니다.
        ![장치 개요](http://i.imgur.com/4Rx4VXm.png)
        
    - **하드웨어** - 사용 가능한 저장 공간, 모델, 제조업체 등 장치에 대한 자세한 정보를 표시합니다.
    ![관리되는 장치 하드웨어 인벤토리](./media/hardware-inventory.png)
    - **검색된 응용 프로그램** - Intune에서 찾아서 장치에 설치한 모든 앱 목록을 표시합니다.
    ![검색된 응용 프로그램 노드](./media/detected-applications.png)
- **모니터** **장치 작업**을 선택하면 관리하는 장치에서 수행된 장치 작업 목록 및 해당 작업의 현재 상태가 표시됩니다.
![모니터 장치 작업](./media/monitor-device-actions.png)

