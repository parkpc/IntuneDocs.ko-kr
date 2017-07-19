---
title: "Intune으로 장치 관리"
titleSuffix: Intune on Azure
description: "Intune을 사용하여 관리하는 장치를 보고 해당 장치에 대해 여러 작업을 수행하는 방법을 알아봅니다.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/05/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d2412418-d91a-4767-a3d6-bc88bb29caa2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8f066e62e323fffb7c6954d83b2b55ee63f4be46
ms.sourcegitcommit: fd5b7aa26446d2fa92c21638cb29371e43fe169f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/06/2017
---
# <a name="what-is-microsoft-intune-device-management"></a>Microsoft Intune 장치 관리란?


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

**장치** 워크로드는 관리하는 장치에 대한 정보를 제공하고, 이러한 장치에 대해 원격 작업을 수행할 수 있도록 합니다. 이 워크로드에 액세스하려면 다음을 수행합니다.

1. Azure 포털에 로그인합니다.
2. **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
3. **Intune** 블레이드에서 **장치**를 선택합니다.

이제 다음과 같은 작업을 수행할 수 있습니다.

- [장치 인벤토리 보기](device-inventory.md)
- 다음의 원격 장치 작업 수행:
    - [회사 데이터 제거](device-company-data-remove.md) 
    - [초기화](device-factory-reset.md)
    - [원격 잠금](device-remote-lock.md)
    - [암호 초기화](device-passcode-reset.md)
    - [활성화 잠금 무시](device-activation-lock-bypass.md)
    - [새로 시작](device-fresh-start.md)
    - [분실 모드](device-lost-mode.md)
    - [장치 찾기](device-locate.md)
    - [다시 시작](device-restart.md)
    - [Windows 10 PIN 재설정](device-windows-pin-reset.md)
    - [Android 원격 제어](device-profile-android-teamviewer.md)


## <a name="support-for-each-device-action"></a>각 장치 작업에 대한 지원

다음 표를 사용하여 각 작업에서 지원하는 장치 플랫폼을 이해할 수 있습니다.

|||||||
|-|-|-|-|-|-|
|장치 작업|Windows|Windows Phone|iOS|macOS|Android|
|**회사 데이터 제거**|예|예|예|예|예|
|**초기화**|Windows 8.1 이상(EAS 관리 장치 아님)|예|예|아니요|Android for Work는 지원되지 않음|
|**삭제**|예|예|예|예|예|
|**원격 잠금**|아니요|Windows Phone 8.1 이상|예|아니요|예|
|**암호 초기화**|아니요|Azure AD에 연결되지 않은 Windows Phone 8.1-Windows 10 크리에이터스 업데이트, Windows 10 크리에이터스 업데이트 이상 - 모두|예|아니요|Android 7 이전, Android for Work는 지원되지 않음|
|**새로운 암호**(Windows 10 장치용)|아니요|Windows 10 크리에이터스 업데이트 이상(Azure AD 연결)|아니요|아니요|Android for Work는 지원되지 않음|
|**활성화 잠금 무시**|아니요|아니요|회사 소유 장치만|아니요|아니요|
|**분실 모드**|아니요|아니요|iOS 9.3 이상, 감독됨, 회사 소유|아니요|아니요|
|**장치 찾기**|아니요|아니요|분실 모드 iOS 9.3 이상, 감독됨, 회사 소유|아니요|아니요|
|**현재 사용자 로그아웃**|아니요|아니요|iOS 9.3 및 이상(공유 iPad 장치만 해당)|아니요|아니요|
|**다시 시작**|Windows 8.1 이상|Windows Phone 8.1 이상|아니요|아니요|아니요|
|**새로 시작**|Windows 10 크리에이터스 업데이트 이상|아니요|아니요|아니요|아니요|
|**새 원격 지원 세션**|아니요|아니요|아니요|아니요|예|
|**사용자 제거**|아니요|아니요|iOS 9.3 및 이상(공유 iPad 장치만 해당)|아니요|아니요|

## <a name="next-steps"></a>다음 단계

- **장치 작업**을 선택하여 관리하는 장치에서 수행된 작업의 상태를 확인합니다. 
![모니터 장치 작업](./media/monitor-device-actions.png)