---
title: Microsoft Intune-Azure에서 장치 암호 다시 설정 | Micrososft Docs
description: Intune에서 관리하거나 모니터링하는 장치에서 암호 제거 작업을 사용하여 암호를 제거하거나 다시 설정합니다.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 47181d19-4049-4c7a-a8de-422206c4027e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4cca5922f036711093469e71489e267af53f05a9
ms.sourcegitcommit: e6319ff186d969da34bd19c9730ba003d6cce353
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2018
---
# <a name="reset-or-remove-a-device-passcode-in-intune"></a>Intune에서 장치 암호 다시 설정 또는 제거

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

장치에 새 암호를 만들려면 **암호 제거** 작업을 사용합니다.

## <a name="supported-platforms"></a>지원되는 플랫폼

- Windows Phone 8.1(Azure Active Directory에 가입되지 않음), Windows 10 크리에이터 업데이트 릴리스 포함
- Windows 10 크리에이터스 업데이트 이상
- iOS
- Android 7 이전 Android 버전

다음 시스템에서는 이 기능이 지원되지 않습니다.

- Windows
- macOS
- Android for Work

## <a name="reset-a-passcode"></a>암호 재설정

1. [Azure 포털](https://portal.azure.com)에 로그인합니다.
2. **모든 서비스**를 선택하고 **Intune**에서 필터링한 다음, **Microsoft Intune**을 선택합니다.
3. **장치**를 선택한 다음, **모든 장치**를 선택합니다.
4. 관리하는 장치 목록에서 장치를 선택하고 **자세히...**를 선택합니다. 그런 다음, **암호 제거** 장치 원격 작업을 선택합니다.

## <a name="next-steps"></a>다음 단계

방금 수행한 작업의 상태를 확인하려면 **장치**에서 **장치 작업**을 선택합니다.
