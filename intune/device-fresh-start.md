---
title: "Intune을 사용하여 Windows 10 장치 다시 설정"
titlesuffix: Azure portal
description: "새로 시작 기능을 사용하여 Intune을 실행하는 Windows 10 PC를 다시 설정하는 방법을 알아봅니다.\""
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 08/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5aa5cfa3-c483-4099-b40f-578ff8dca425
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dce888c1985ff4761100d15d898b654d77318b65
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2018
---
# <a name="use-fresh-start-to-reset-windows-10-devices-with-intune"></a>Intune을 통해 새로 시작 기능을 사용하여 Windows 10 장치 다시 설정


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

**새로 시작** 장치 작업을 수행하면 크리에이터스 업데이트를 실행 중인 Windows 10 PC에 설치된 앱이 제거되고 PC가 자동으Apple MDM Push certificate로 최신 버전의 Windows로 업데이트됩니다.
이 작업은 종종 새 PC와 함께 제공되는 미리 설치된 OEM 앱을 제거하는 데 사용할 수 있습니다. 이 장치 작업을 실행할 때 사용자 데이터를 유지할지 여부를 구성할 수 있습니다. 이 경우 앱과 설정은 제거되지만 사용자 홈 폴더의 내용은 그대로 유지됩니다.

## <a name="how-to-use-fresh-start"></a>새로 시작을 사용하는 방법

1. Azure 포털에 로그인합니다.
2. **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
3. **Intune** 블레이드에서 **장치**를 선택합니다.
4. **장치 및 그룹** 블레이드에서 **모든 장치**를 선택합니다.
5. 관리하는 장치 목록에서 Windows 10 데스크톱 장치를 선택한 다음 **새로 시작** 장치 원격 작업을 선택합니다.

## <a name="next-steps"></a>다음 단계

방금 수행한 작업의 상태를 확인하려면 **장치 및 그룹** 블레이드에서 **장치 작업**을 선택합니다.

