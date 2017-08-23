---
title: "Intune을 사용하여 iOS 장치의 사용자 로그아웃"
titleSuffix: Intune on Azure
description: "Intune을 사용하여 iOS 장치의 현재 사용자를 로그아웃하는 방법을 알아봅니다.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/13/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 702bc46c-1a6f-4689-bd53-3b778a447baa
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1de2069b7b25ee5e5c21a8e4caa7512f13d4ca0e
ms.sourcegitcommit: ee7f69efe9f32a1d6bdeb1fab73d03dbfe1ae58c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2017
---
# <a name="logout-the-current-user-on-intune-managed-ios-devices"></a>Intune 관리 iOS 장치에서 현재 사용자 로그아웃


[!INCLUDE[azure_portal](./includes/azure_portal.md)]


**현재 사용자 로그아웃** 작업은 [iOS 교육 프로필](education-settings-configure-ios.md)을 사용하여 iOS 교실 앱을 관리하도록 구성된 공유 iPad 장치에서 현재 사용자를 로그아웃합니다. 

## <a name="supported-platforms"></a>지원되는 플랫폼

- Windows - 지원되지 않음
- Windows Phone - 지원되지 않음
- iOS - iOS 9.3 및 이상에서 지원됨(공유 iPad 장치만 해당)
- macOS - 지원되지 않음
- Android - 지원되지 않음

## <a name="how-to-logout-the-current-user"></a>현재 사용자를 로그아웃하는 방법

1.  Azure 포털에 로그인합니다.
2.  **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
3.  **Intune** 블레이드에서 **장치**를 선택합니다.
4.  **장치 및 그룹** 블레이드에서 **모든 장치**를 선택합니다.
5.  관리하는 장치 목록에서 iOS 장치를 선택한 다음 **현재 사용자 로그아웃** 장치 원격 작업을 선택합니다.

## <a name="next-steps"></a>다음 단계

방금 수행한 작업의 상태를 확인하려면 **장치 및 그룹** 블레이드에서 **장치 작업**을 선택합니다.
