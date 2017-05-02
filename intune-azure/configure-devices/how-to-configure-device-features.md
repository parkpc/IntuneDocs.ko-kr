---
title: "Intune 장치 기능 설정 구성"
titleSuffix: Intune Azure preview
description: "Intune Azure 미리 보기: Intune을 사용하여 관리하는 장치에서 기능을 구성하는 방법을 알아봅니다."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: e5dd7cb5b320df7f443b52a1b502027fa3c4acaf
ms.openlocfilehash: e1bc6388ec1927693bac676a20a18935cdbf894e
ms.lasthandoff: 04/19/2017


---

# <a name="how-to-configure-device-feature-settings-in-microsoft-intune"></a>Microsoft Intune에서 장치 기능 설정을 구성하는 방법

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

장치 제한을 통해 IOS 및 macOS 장치에서 AirPrint, 알림 및 공유 장치 구성과 같은 기능을 제어할 수 있습니다.

이 항목의 정보를 사용하여 장치 기능 프로필 구성에 대한 기본 사항을 알아본 다음, 각 플랫폼에 대한 추가 항목을 통해 장치에 특정한 정보를 확인할 수 있습니다.

## <a name="create-a-device-profile-containing-device-restriction-settings"></a>장치 제한 설정을 포함하는 장치 프로필 만들기

1. Azure 포털에 로그인합니다.
2. **추가 서비스** > **기타** > **Intune**을 선택합니다.
3. **Intune** 블레이드에서 **장치 구성**을 선택합니다.
2. **장치 구성** 블레이드에서 **관리** > **프로필**을 선택합니다.
3. 프로필 블레이드에서 **프로필 만들기**를 선택합니다.
4. **프로필 만들기** 블레이드에서 장치 기능 프로필에 대한 **이름** 및 **설명**을 입력합니다.
5. **플랫폼** 드롭다운 목록에서 설정을 적용할 장치 플랫폼을 선택합니다. 현재 장치 기능에 대해 다음 플랫폼 중 하나를 선택할 수 있습니다.
    - **iOS**
    - **macOS**
6. **프로필 유형** 드롭다운 목록에서 **장치 기능**을 선택합니다. 
7. 선택한 플랫폼에 따라 구성할 수 있는 설정이 다릅니다. 각 플랫폼에 대한 자세한 설정을 보려면 다음 항목 중 하나로 이동하세요.
    - [iOS 및 MacOS용 AirPrint 설정](air-print-settings-for-ios-and-macos.md)
     - [iOS용 AirPlay 설정](airplay-settings-for-ios-devices.md)
    - [iOS용 홈 화면 레이아웃 설정](home-screen-settings-for-ios.md)
    - [iOS용 앱 알림 설정](app-notification-settings-for-ios.md)
    - [iOS용 공유 장치 구성 설정](shared-device-settings-for-ios.md)
    - [iOS 장치용 웹 콘텐츠 필터 설정](web-content-filter-settings-for-ios.md)

8. 완료되면 **프로필 만들기** 블레이드로 돌아가서 **만들기**를 누릅니다.

프로필이 만들어지고 프로필 목록 블레이드에 표시됩니다.
계속해서 이 프로필을 그룹에 할당하려면 [장치 프로필을 할당하는 방법](how-to-assign-device-profiles.md)을 참조하세요.




