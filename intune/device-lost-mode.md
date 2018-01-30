---
title: "Intune을 사용하여 iOS 분실 모드 활성화"
titlesuffix: Azure portal
description: "Intune을 사용하여 분실했거나 도난당한 iOS 장치에서 분실 모드를 활성화하는 방법을 알아봅니다.\""
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 08/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 126a7489-fe3e-43fd-a681-defb2fe0bb66
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7884682b765fe0df0ecb8b55b18f7a85ac4b2ec9
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2018
---
# <a name="activate-lost-mode-on-ios-devices"></a>iOS 장치에서 분실 모드 활성화


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

**분실 모드** 장치 작업을 수행하면 분실했거나 도난당한 iOS 장치에 대해 분실 모드를 사용하도록 설정할 수 있습니다. 이 모드를 통해 장치의 잠금 화면에 표시되는 메시지 및 전화 번호를 지정할 수 있습니다.

## <a name="supported-platforms"></a>지원되는 플랫폼

- Windows - 지원되지 않음
- Windows Phone - 지원되지 않음
- iOS - iOS 9.3 이상에서 지원되고 감독되며 회사에서 소유함
- macOS - 지원되지 않음
- Android - 지원되지 않음

## <a name="how-to-activate-lost-mode"></a>분실된 모드를 활성화하는 방법

1. Azure 포털에 로그인합니다.
2. **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
3. **Intune** 블레이드에서 **장치**를 선택합니다.
4. **장치 및 그룹** 블레이드에서 **모든 장치**를 선택합니다.
5. 관리하는 장치 목록에서 iOS 장치를 선택한 다음 **분실 모드** 원격 작업을 선택합니다.
6. **분실 모드** 블레이드에서 분실 모드를 사용하도록 설정합니다. 그런 다음 표시할 메시지와 선택적으로 연락처 전화 번호를 입력합니다.
7. **확인**을 클릭합니다.

분실 모드를 사용하도록 설정하면 장치에 대한 모든 사용이 차단됩니다. 분실 모드를 사용하지 않도록 설정할 때까지 최종 사용자는 장치에 액세스할 수 없습니다. 분실 모드가 사용하도록 설정된 동안 **장치 찾기** 작업을 사용하여 장치 위치를 찾을 수 있습니다.
장치에서 분실 모드를 사용하려면 감독 모드인 회사 소유 iOS 장치여야 합니다.

## <a name="security-and-privacy-information-for-the-lost-mode-and-locate-device-actions"></a>분실 모드의 보안 및 개인 정보와 장치 찾기 작업
- 이 작업을 켤 때까지 장치 위치 정보는 Intune에 전송되지 않습니다.
- 찾기 장치 작업을 사용하면 장치의 위도/경도 좌표가 Intune으로 전송되고 Azure Portal에 표시됩니다.
- 데이터는 24시간 동안 저장되었다가 제거됩니다. 위치 데이터를 수동으로 제거할 수 없습니다.
- 위치 데이터는 저장된 동안 및 전송되는 동안 모두 암호화됩니다.
- 잠금 화면에 표시되도록 입력하는 메시지에 장치를 습득한 사람으로부터 돌려받는 데 도움이 되는 정보를 포함하는 것이 좋습니다.

## <a name="next-steps"></a>다음 단계

방금 수행한 작업의 상태를 확인하려면 **장치 및 그룹** 블레이드에서 **장치 작업**을 선택합니다.

