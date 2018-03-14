---
title: "Microsoft Intune을 사용하여 iOS 장치에서 사용자 제거"
titlesuffix: 
description: "Intune을 사용하여 공유 iOS 장치에서 사용자를 제거하는 방법을 알아봅니다."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2ea5941c-a69b-4e1c-b42c-a1fc0c3a7de7
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ce1b6b439c287b67a7c9e776edf136e78e5ecf5b
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/08/2018
---
# <a name="remove-a-user-from-a-shared-ios-device"></a>공유 iOS 장치에서 사용자 제거


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

**사용자 제거** 작업은 [iOS 교육 프로필](education-settings-configure-ios.md)을 사용하여 iOS 교실 앱을 관리하도록 구성된 공유 iPad 장치의 로컬 캐시에서 선택한 사용자를 삭제합니다. 

## <a name="supported-platforms"></a>지원되는 플랫폼

- Windows - 지원되지 않음
- Windows Phone - 지원되지 않음
- iOS - iOS 9.3 및 이상에서 지원됨(공유 iPad 장치만 해당)
- macOS - 지원되지 않음
- Android - 지원되지 않음

## <a name="how-to-remove-a-user"></a>사용자 제거 방법

1. 로그인은 [Azure 포털](https://portal.azure.com)합니다.
2. **모든 서비스** > **Intune**을 선택합니다. Intune은 **모니터링 + 관리** 섹션에 있습니다.
3. **Intune** 블레이드에서 **장치**를 선택합니다.
4. **장치** 블레이드에서 **모든 장치**를 선택합니다.
5. 관리하는 장치 목록에서 iOS 장치를 선택합니다.
6. 해당 장치에 대한 블레이드에서 **사용자**를 선택합니다.
7. 목록에서 제거할 사용자를 마우스 오른쪽 단추로 클릭하고 **사용자 제거**를 선택합니다.

## <a name="next-steps"></a>다음 단계

방금 수행한 작업의 상태를 확인하려면 **장치** 블레이드에서 **장치 작업**을 선택합니다.
