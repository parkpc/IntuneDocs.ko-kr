---
title: "Microsoft Intune - Azure에서 장치 프로필 만들기 | Microsoft Docs"
description: "플랫폼 형식 선택과 Azure Portal 내에서 설정 구성을 포함한 Microsoft Intune에서 장치 프로필 추가나 구성"
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/01/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c40fd13a46a61ec0ee05efba7ece7653f5de90ca
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2018
---
# <a name="create-a-device-profile-in-microsoft-intune"></a>Microsoft Intune에서 장치 프로필 만들기

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="create-the-profile"></a>프로필 만들기
1. [Azure Portal](https://portal.azure.com)에서 **모든 서비스**를 선택하고 **Microsoft Intune**을 검색합니다.

2. **Microsoft Intune**에서 **장치 구성**를 선택하고 **프로필**을 선택한 다음, **프로필 만들기**를 선택합니다.

3. 다음 속성을 입력합니다. 

    - **이름** - 새 프로필에 대한 설명이 포함된 이름 입력
    - **설명**: 선택 사항이지만 사용하는 것이 좋습니다. 프로필에 대한 설명을 입력합니다.
    - **플랫폼**: 플랫폼 형식을 선택 합니다.  

        - **OWA(Outlook Web Access)**
        - **Android for Work**
        - **Android**
        - **macOS**
        - **Windows Phone 8.1**
        - **Windows 8.1 이상**
        - **Windows 10 이상**

    - **프로필 유형** - 만들려는 유형을 선택합니다. 목록은 선택한 플랫폼에 따라 달라집니다.
    - **설정** - 다음 항목에서는 각 프로필 유형의 설정에 대해 설명합니다.

        -  [장치 기능 설정](device-features-configure.md)
        -  [장치 제한 설정](device-restrictions-configure.md)
        -  [메일 설정](email-settings-configure.md)
        -  [VPN 설정](vpn-settings-configure.md)
        -  [Wi-Fi 설정](wi-fi-settings-configure.md)
        -  [Windows 10 버전 업그레이드 설정](edition-upgrade-configure-windows-10.md)
        -  [인증서 설정](certificates-configure.md)
        -  [Windows Information Protection 설정](windows-information-protection-configure.md)
        -  [교육 설정](education-settings-configure.md)
        -  [사용자 지정 설정](custom-settings-configure.md)

    ![장치 프로필을 만들려면 설정 입력](./media/create-device-profile.png)

4. 완료된 경우 **만들기**를 선택합니다. 

프로필이 만들어지고 목록에 표시됩니다. 이 프로필을 그룹에 할당하려면 [장치 프로필을 할당하는 방법](device-profile-assign.md)을 참조하세요.


## <a name="next-steps"></a>다음 단계
장치 프로필을 할당하려면 [Microsoft Intune을 사용하여 장치 프로필을 할당하는 방법](device-profile-assign.md)을 참조하세요.