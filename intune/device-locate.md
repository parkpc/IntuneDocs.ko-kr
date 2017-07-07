---
title: "Intune을 사용하여 분실한 iOS 장치 찾기"
titleSuffix: Intune on Azure
description: "Intune을 사용하여 분실했거나 도난당한 iOS 장치를 찾는 방법을 알아봅니다.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/27/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3e544286-12ad-4a3a-86f8-d2cf16940b1f
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 80aa0e5afd1f8862b181d455ff6b545e462f90c9
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2017
---
# <a name="locate-lost-or-stolen-ios-devices-with-intune"></a>Intune을 사용하여 분실했거나 도난당한 iOS 장치 찾기


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

**장치 찾기** 장치 작업에서는 분실했거나 도난당한 iOS 장치의 위치를 지도에 표시합니다. 장치는 DEP를 통해 등록되고 감독 모드 상태인 회사 소유의 iOS 장치여야 합니다. 이 작업을 사용하려면 장치가 [분실 모드](/intune-azure/manage-devices/lost-mode.md)로 설정된 상태여야 합니다.

1. Azure 포털에 로그인합니다.
2. **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
3. **Intune** 블레이드에서 **장치**를 선택합니다.
4. **장치 및 그룹** 블레이드에서 **모든 장치**를 선택합니다.
5. 관리하는 장치 목록에서 iOS 장치를 선택한 다음 **장치 찾기** 원격 작업을 선택합니다.
6. 장치의 위치를 찾으면 **장치 찾기** 블레이드에 위치가 표시됩니다.
    ![장치 찾기 블레이드](./media/locate-device.png)

>[!NOTE]
>개인 정보 보호 차원에서 지도를 확대할 수 있는 거리가 제한됩니다.

## <a name="security-and-privacy-information-for-the-lost-mode-and-locate-device-actions"></a>분실 모드의 보안 및 개인 정보와 장치 찾기 작업
- 이 작업을 켤 때까지 장치 위치 정보는 Intune에 전송되지 않습니다.
- 찾기 장치 작업을 사용하면 장치의 위도/경도 좌표가 Intune으로 전송되고 Azure Portal에 표시됩니다.
- 데이터는 24시간 동안 저장되었다가 제거됩니다. 위치 데이터를 수동으로 제거할 수 없습니다.
- 위치 데이터는 저장된 동안 및 전송되는 동안 모두 암호화됩니다.
- 분실 모드를 구성할 때는 잠금 화면에 표시되도록 입력하는 메시지에 장치를 습득한 사람으로부터 돌려 받는 데 도움이 되는 정보를 포함하는 것이 좋습니다.
