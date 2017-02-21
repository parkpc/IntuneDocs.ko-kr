---
title: "Intune 장치 제한 설정 구성 | Intune Azure 미리 보기 | Microsoft Docs"
description: "Intune Azure 미리 보기: Intune을 사용하는 관리하는 iOS 장치에서 설정 및 기능을 구성하는 방법을 알아봅니다."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 67e3481f9cf01bd1b298cfb26f25d1a3205e0f29
ms.openlocfilehash: 0c22d8a85d90139b3ac17c54668890d5b4c0afe6


---

# <a name="how-to-configure-device-restriction-settings-in-intune-azure-preview"></a>Intune Azure 미리 보기에서 장치 제한 설정을 구성하는 방법

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

장치 제한 사항을 통해 보안, 브라우저, 하드웨어 및 데이터 공유 설정 등 다양한 범주에 걸쳐 관리하는 광범위한 설정 및 기능을 제어할 수 있습니다. 예를 들어 iOS 장치의 사용자가 장치 카메라에 액세스하지 못하도록 하는 장치 제한 프로필을 만들 수 있습니다.

이 항목의 정보를 사용하여 장치 제한 프로필 구성에 대한 기본 사항을 알아본 다음 각 플랫폼에 대한 추가 항목을 통해 장치에 특정한 정보를 확인할 수 있습니다.

## <a name="create-a-device-profile-containing-device-restriction-settings"></a>장치 제한 설정을 포함하는 장치 프로필 만들기

1. Azure 포털에 로그인합니다.
2. **추가 서비스** > **기타** > **Intune**을 선택합니다.
3. **Intune** 블레이드에서 **장치 구성**을 선택합니다.
2. **장치 구성** 블레이드에서 **관리** > **프로필**을 선택합니다.
3. 프로필 블레이드에서 **프로필 만들기**를 선택합니다.
4. **프로필 만들기** 블레이드에서 장치 제한 프로필에 대한 **이름** 및 **설명**을 입력합니다.
5. **플랫폼** 드롭다운 목록에서 사용자 지정 설정을 적용할 장치 플랫폼을 선택합니다. 현재 장치 제한 설정에 대해 다음 플랫폼 중 하나를 선택할 수 있습니다.
    - **OWA(Outlook Web Access)**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 이상**
    - **Windows 10 이상**
6. **프로필** 유형 드롭다운 목록에서 **장치 제한**을 선택합니다. Surface Hub와 같은 Windows 10 Team 장치에 대한 장치 제한 프로필을 만들려면 **장치 제한(Windows 10 Team)**을 선택합니다.
7. 선택한 플랫폼에 따라 구성할 수 있는 설정이 다릅니다. 각 플랫폼에 대한 자세한 설정을 보려면 다음 항목 중 하나로 이동하세요.
    - [Android 설정](device-restrictions-for-android.md)
    - [iOS 설정](device-restrictions-for-ios.md)
    - [macOS 설정](device-restrictions-for-macos.md)
    - [Windows Phone 8.1 설정](device-restrictions-for-windows-phone-8-1.md)
    - [Windows 8.1](device-restrictions-for-windows-8-1.md)
    - [Windows 10 설정](device-restrictions-for-windows-10.md)
    - [Windows 10 Team 설정](device-restrictions-for-windows-10-team.md)
8. 완료되면 **프로필 만들기** 블레이드로 돌아가서 **만들기**를 누릅니다.

프로필이 만들어지고 프로필 목록 블레이드에 표시됩니다.
계속해서 이 프로필을 그룹에 할당하려면 [장치 프로필을 할당하는 방법](how-to-assign-device-profiles.md)을 참조하세요.

## <a name="example-of-device-restriction-settings"></a>장치 제한 설정의 예

이 개략적인 예에서는 Android 장치에서 기본 제공 카메라 앱의 사용을 차단하는 장치 제한 정책을 만듭니다.

![Android 장치에서 카메라를 사용하지 않도록 설정하는 방법](./media/disable-android-camera.png)




<!--HONumber=Feb17_HO1-->


