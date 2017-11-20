---
title: "Intune으로 장치 암호 재설정 및 제거"
titlesuffix: Azure portal
description: "Intune으로 관리하는 장치에서 암호를 재설정하고 제거하는 방법을 알아봅니다."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 11/06/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47181d19-4049-4c7a-a8de-422206c4027e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dfa94d11f978bbe4d23b6672423c849e1f061986
ms.sourcegitcommit: 474a24ba67f6bf4f00268bf9e4eba52331a6b82d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2017
---
# <a name="reset-and-remove-the-passcode-on-intune-managed-devices"></a>Intune 관리 장치에서 암호 재설정 및 제거


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

이 문서에서 *제거* 및 *재설정*이라는 용어는 같은 의미로 사용됩니다.

**암호 제거** 작업을 수행하면 <*장치 이름*> **개요** 블레이드에 표시되는 장치의 새 암호가 생성됩니다.

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
5. 관리하는 장치 목록에서 장치를 선택한 다음 **암호 제거** 장치 원격 작업을 선택합니다.

## <a name="next-steps"></a>다음 단계

방금 수행한 작업의 상태를 확인하려면 **장치 및 그룹** 블레이드에서 **장치 작업**을 선택합니다.
