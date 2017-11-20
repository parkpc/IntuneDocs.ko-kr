---
title: "Intune에서 등록 제한 설정"
titlesuffix: Azure portal
description: "Intune에서 플랫폼별로 등록을 제한하고 장치 등록 제한을 설정합니다. \""
keywords: 
author: ErikjeMS
ms.author: erikje
manager: angrobe
ms.date: 11/6/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 463278e4dc9ad677f654754d4710b110b376cc2d
ms.sourcegitcommit: 5279a0bb8c5aef79aa57aa247ad95888ffe5a12b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2017
---
# <a name="set-enrollment-restrictions"></a>등록 제한 설정

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune 관리자의 경우 Intune을 사용한 관리에 등록할 수 있는 장치를 결정할 수 있습니다. Azure Portal을 사용하여 장치 등록에 대해 다음과 같은 제한을 설정합니다.

- 등록된 장치의 최대 수
- 등록할 수 있는 장치 플랫폼:
  - Android
  - iOS
  - macOS
  - Windows
- iOS, Android 및 Windows용 플랫폼 운영 체제 버전(Windows 10 버전만 사용 가능, Windows 8.1이 허용되는 경우 공백으로 비워 둠)
  - 최소 버전
  - 최대 버전
- 개인 소유 장치 제한(iOS, Android 및 macOS만 해당)

>[!NOTE]
>등록 제한은 보안 기능이 아닙니다. 손상된 장치는 해당 문자를 잘못 표시할 수 있습니다. 이러한 제한은 무해한 사용자를 위한 최선의 장벽입니다.

## <a name="set-device-type-restrictions"></a>장치 유형 제한 설정
기본 등록 제한은 모든 사용자 등록과 사용자가 없는 등록에 적용됩니다.
1. Azure 포털에 로그인합니다.
2. **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
3. **장치 등록** > **등록 제한**을 선택합니다.
4. **등록 제한** > **장치 유형 제한**에서 **기본값**을 선택합니다.
5. **모든 사용자**에서 **플랫폼**을 선택합니다. 각 플랫폼에 대해 **허용** 또는 **차단**을 선택합니다.
  - **Android**
  - **iOS**
  - **macOS**
  - **Windows**

  **Save**을 클릭합니다.
6. **모든 사용자**에서 **플랫폼 구성**을 선택하고 다음 구성을 선택합니다. 허용되는 각 플랫폼에 대해 다음 옵션을 구성할 수 있습니다.
  - **버전** - Android, iOS 또는 Windows 장치의 **최소** 및 **최대** 플랫폼 운영 체제 버전을 지정합니다. Android는 major.minor.rev.build를 지원합니다. iOS는 major.minor.rev를 지원합니다. Windows는 Windows 10용 major.minor.rev.build만 지원합니다. 운영 체제 버전은 장비 등록 프로그램, Apple School Manager 또는 Apple Configurator 앱에 등록되는 Apple 장치에 적용되지 않습니다. 
  - **개인적으로 소유함** - Android, iOS 및 macOS 장치에 대해 **허용**할지 아니면 **차단**할지 지정합니다.
  ![개인적으로 소유함 설정이 구성된 기본 장치 플랫폼 구성이 있는 장치 제한 작업 영역 스크린샷](media/device-restrictions-platform-configurations.png)
  **Save**을 클릭합니다.

>[!NOTE]
>개인적으로 소유한 Android 장치의 등록을 차단하는 경우에도 개인적으로 소유한 Android for Work 장치는 계속 등록할 수 있습니다.

## <a name="set-device-limit-restrictions"></a>장치 개수 제한
기본 등록 제한은 모든 사용자 등록에 적용됩니다.
1. Azure 포털에 로그인합니다.
2. **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
3. **장치 등록** > **등록 제한**을 선택합니다.
4. Azure Portal에서 **장치 등록**을 선택한 다음 **등록 제한**을 선택합니다.
5. **등록 제한** > **장치 개수 제한**을 선택합니다.
6. **모든 사용자**에서 **장치 제한**을 선택합니다. 사용자당 등록된 장치의 최대 수를 지정합니다.  
![장치 개수 제한이 있는 장치 개수 제한 블레이드 스크린샷](./media/device-restrictions-limit.png)

  **저장**을 클릭합니다.
