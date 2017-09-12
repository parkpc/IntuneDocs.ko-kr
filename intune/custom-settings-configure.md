---
title: "Intune 사용자 지정 장치 설정을 구성하는 방법"
titleSuffix: Azure portal
description: "관리하는 장치에서 Intune을 사용하여 사용자 지정 설정을 구성하는 방법을 알아봅니다.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 14c85b04c18edb2dfa9bdf3b73457448ad8ef8c8
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/09/2017
---
# <a name="how-to-configure-custom-device-settings-in-microsoft-intune"></a>Microsoft Intune에서 사용자 지정 장치 설정을 구성하는 방법

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="when-to-use-custom-settings"></a>사용자 지정 설정을 사용하는 경우

Intune에 다른 장치 프로필에서 기본 제공되고 사용 가능한 구성하려는 설정이 없는 경우 사용자 지정 장치 설정이 유용할 수 있습니다.
사용자 지정 설정은 플랫폼마다 다르게 구성됩니다. 예를 들어 Android 및 Windows 장치에서는 장치의 기능을 제어하기 위해 OMA-URI(Open Mobile Alliance Uniform Resource Identifier) 값을 지정할 수 있습니다. Apple 장치의 경우 [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)를 사용하여 만든 파일을 가져올 수 있습니다.

이 항목의 정보를 사용하여 사용자 지정 설정을 사용한 프로필 구성에 대한 기본 사항을 알아본 다음 각 플랫폼에 대한 추가 항목을 통해 장치에 특정한 정보를 확인할 수 있습니다.

## <a name="create-a-device-profile-containing-custom-settings"></a>사용자 지정 설정을 포함하는 장치 프로필 만들기

1. Azure 포털에 로그인합니다.
2. **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
3. **Intune** 블레이드에서 **장치 구성**을 선택합니다.
2. **장치 구성** 블레이드에서 **관리** > **프로필**을 선택합니다.
3. 프로필 블레이드에서 **프로필 만들기**를 선택합니다.
4. **프로필 만들기** 블레이드에서 사용자 지정 프로필에 대한 **이름** 및 **설명**을 입력합니다.
5. **플랫폼** 드롭다운 목록에서 사용자 지정 설정을 적용할 장치 플랫폼을 선택합니다. 현재 사용자 지정 장치 설정에 대해 다음 플랫폼 중 하나를 선택할 수 있습니다.
    - **OWA(Outlook Web Access)**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 10 이상**
6. **프로필** 유형 드롭다운 목록에서 선택 **사용자 지정**을 선택합니다.
7. 선택한 플랫폼에 따라 구성할 수 있는 설정이 다릅니다. 각 플랫폼에 대한 자세한 설정을 보려면 다음 항목 중 하나로 이동하세요.
    - [Android 설정](custom-settings-android.md)
    - [iOS 설정](custom-settings-ios.md)
    - [macOS 설정](custom-settings-macos.md)
    - [Windows Phone 8.1 설정](custom-settings-windows-phone-8-1.md)
    - [Windows 10 설정](custom-settings-windows-10.md)
    - [Android for Work 설정](custom-settings-android-for-work.md)
8. 완료되면 **프로필 만들기** 블레이드로 돌아가서 **만들기**를 누릅니다.

프로필이 만들어지고 프로필 목록 블레이드에 표시됩니다.
계속해서 이 프로필을 그룹에 할당하려면 [장치 프로필을 할당하는 방법](device-profile-assign.md)을 참조하세요.
