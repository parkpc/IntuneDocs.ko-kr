---
title: "Intune Wi-Fi 설정을 구성하는 방법"
titleSuffix: Azure portal
description: "관리하는 장치에서 Intune을 사용하여 Wi-Fi 연결을 구성하는 방법을 알아봅니다.\""
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1fadb488-9c6c-43c1-ba23-8c69db633b96
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e3333a5addfd0c4ab757121e22e19ac66c0b3e1d
ms.sourcegitcommit: ec8561b8c63515e0b5f21a858984108dc5dbd5d3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2017
---
# <a name="how-to-configure-wi-fi-settings-in-microsoft-intune"></a>Microsoft Intune에서 Wi-Fi 설정을 구성하는 방법

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Microsoft Intune Wi-Fi 프로필을 사용하여 무선 네트워크 설정을 조직의 사용자와 장치에 할당합니다. Wi-Fi 프로필을 할당하면 사용자가 Wi-Fi를 직접 구성하지 않고도 회사 Wi-Fi 네트워크에 액세스할 수 있습니다.

예를 들어, Contoso Wi-Fi라는 이름의 새 Wi-Fi 네트워크를 설치하고 모든 iOS 장치를 이 네트워크에 연결하도록 설정하려고 합니다. 프로세스는 다음과 같습니다.

1. Contoso Wi-Fi 무선 네트워크에 연결하는 데 필요한 설정이 포함된 Wi-Fi 프로필을 만듭니다.
2. iOS 장치의 모든 사용자를 포함하는 그룹에 프로필을 할당합니다.
3. 사용자는 장치의 무선 네트워크 목록에서 새 Contoso Wi-Fi 네트워크를 찾아서 쉽게 연결할 수 있습니다.

Wi-Fi 프로필은 다음 장치 플랫폼을 지원합니다.

- Android 4 이상
- Android for Work
- iOS 8.0 이상
- macOS(Mac OS X 10.9 이상)

Windows 8.1, Windows 10 및 Windows 10 Mobile을 실행하는 장치의 경우 이전에 다른 장치에서 내보낸 Wi-Fi 구성을 가져올 수 있습니다.

이 항목의 정보를 사용하여 Wi-Fi 프로필 구성에 대한 기본 사항을 알아본 다음 각 플랫폼에 대한 추가 항목을 통해 장치에 특정한 정보를 확인할 수 있습니다.

## <a name="create-a-device-profile-containing-wi-fi-settings"></a>Wi-Fi 설정을 포함하는 장치 프로필 만들기

1. Azure 포털에 로그인합니다.
2. **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
3. **Intune** 블레이드에서 **장치 구성**을 선택합니다.
2. **장치 구성** 블레이드에서 **관리** > **프로필**을 선택합니다.
3. 프로필 블레이드에서 **프로필 만들기**를 선택합니다.
4. **프로필 만들기** 블레이드에서 Wi-Fi 프로필에 대한 **이름** 및 **설명**을 입력합니다.
5. **플랫폼** 드롭다운 목록에서 Wi-Fi 설정을 적용할 장치 플랫폼을 선택합니다. 현재 Wi-Fi 설정에 대해 다음 플랫폼 중 하나를 선택할 수 있습니다.
    - **OWA(Outlook Web Access)**
    - **Android for Work**
    - **Android**
    - **macOS**
    - **Windows 8.1 이상(프로필 가져오기)**
6. **프로필** 유형 드롭다운 목록에서 **Wi-Fi 기본** 또는 **Wi-Fi 엔터프라이즈**를 선택합니다.
    >[!TIP]
    >**Wi-Fi 기본**을 사용하여 네트워크 이름 및 SSID와 같은 기본 기능을 제공합니다. **Wi-Fi 엔터프라이즈**를 사용하여 EAP(확장 인증 프로토콜)와 같은 보다 고급 정보를 제공할 수 있습니다(Wi-Fi 네트워크에서 이를 사용하는 경우). **Wi-Fi 가져오기**(Windows 8.1 및 Windows 10의 경우)를 사용하여 이전에 다른 장치에서 내보낸 XML 파일로 Wi-Fi 설정을 가져올 수 있습니다.
7. 선택한 플랫폼에 따라 구성할 수 있는 설정이 다릅니다. 각 플랫폼에 대한 자세한 설정을 보려면 다음 항목 중 하나로 이동하세요.
    - [Android and Android for Work 설정](wi-fi-settings-android.md)
    - [iOS 설정](wi-fi-settings-ios.md)
    - [macOS 설정](wi-fi-settings-macos.md)
    - [Windows Phone 8.1 설정](wi-fi-settings-import-windows-8-1.md)
8. 완료되면 **프로필 만들기** 블레이드로 돌아가서 **만들기**를 누릅니다.

프로필이 만들어지고 프로필 목록 블레이드에 표시됩니다.
계속해서 이 프로필을 그룹에 할당하려면 [장치 프로필을 할당하는 방법](device-profile-assign.md)을 참조하세요.
