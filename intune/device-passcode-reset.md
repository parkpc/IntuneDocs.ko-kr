---
title: "Intune을 사용하여 장치 암호 초기화"
titleSuffix: Intune on Azure
description: "Intune으로 관리하는 장치에서 암호를 초기화하는 방법을 알아봅니다.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47181d19-4049-4c7a-a8de-422206c4027e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 30fac990d8b4a0a088180598e7787e23b1f708b7
ms.sourcegitcommit: ee7f69efe9f32a1d6bdeb1fab73d03dbfe1ae58c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2017
---
# <a name="reset-the-passcode-on-intune-managed-devices"></a>Intune 관리 장치에서 암호 초기화


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

**암호 초기화** 작업을 수행하면 <*장치 이름*> **개요** 블레이드에 표시되는 장치의 새 암호가 생성됩니다.

## <a name="supported-platforms"></a>지원되는 플랫폼

- Windows - 지원되지 않음
- Windows Phone - Azure AD에 연결되지 않은 Windows Phone 8.1-Windows 10 크리에이터스 업데이트, Windows 10 크리에이터스 업데이트 이상에서 지원됨
- iOS - 지원됨
- macOS - 지원되지 않음
- Android - Android 7 이전 버전의 Android에서 지원됩니다. Android for Work는 지원되지 않습니다.

## <a name="how-to-reset-a-passcode"></a>암호를 재설정하는 방법

1. Azure 포털에 로그인합니다.
2. **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
3. **Intune** 블레이드에서 **장치**를 선택합니다.
4. **장치 및 그룹** 블레이드에서 **모든 장치**를 선택합니다.
5. 관리하는 장치 목록에서 장치를 선택한 다음 **암호 초기화** 장치 원격 작업을 선택합니다.

## <a name="next-steps"></a>다음 단계

방금 수행한 작업의 상태를 확인하려면 **장치 및 그룹** 블레이드에서 **장치 작업**을 선택합니다.
