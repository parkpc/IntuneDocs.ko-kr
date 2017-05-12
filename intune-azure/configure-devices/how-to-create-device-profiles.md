---
title: "Intune 장치 구성 프로필 만들기 | Intune Azure 미리 보기"
titleSuffix: Intune Azure preview
description: "Intune Azure 미리 보기: Intune 장치 구성 프로필을 만드는 방법을 알아봅니다."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 3758df744311392528be01c826527c2a9d879975
ms.openlocfilehash: 74a905ed2ba9ec04ae14df96fcd3f6b6caf1241c
ms.contentlocale: ko-kr
ms.lasthandoff: 05/10/2017


---

# <a name="how-to-create-device-configuration-profiles-in-microsoft-intune"></a>Microsoft Intune에서 장치 구성 프로필을 만드는 방법

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


1. Azure 포털에 로그인합니다.
2. **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
3. **Intune** 블레이드에서 **장치 구성**을 선택합니다.
2. **장치 구성** 블레이드에서 **관리** > **프로필**을 선택합니다.
2. 프로필 목록이 표시된 블레이드에서 **프로필 만들기**를 선택합니다.
3. **프로필 만들기** 블레이드에서 다음을 지정합니다.
    - **이름** - 새 프로필에 대한 설명이 포함된 이름을 입력합니다.
    - **설명** - 프로필에 대한 설명을 입력합니다(선택 사항).
    - **플랫폼** - 만들려는 프로필에 대한 플랫폼 유형을 선택합니다.
    - **프로필 유형** - 만들려는 프로필의 유형을 선택합니다. 사용 가능한 유형 목록은 선택한 플랫폼에 따라 다릅니다.
    - **설정** - 각 프로필 유형의 설정에 대한 자세한 내용은 다음 항목을 참조하세요.
        -  [장치 기능 설정](how-to-configure-device-features.md)
        -  [장치 제한 설정](how-to-configure-device-restrictions.md)
        -  [메일 설정](how-to-configure-email-settings.md)
        -  [VPN 설정](how-to-configure-vpn-settings.md)
        -  [Wi-Fi 설정](how-to-configure-wi-fi-settings.md)
        -  [Windows 10 버전 업그레이드 설정](how-to-configure-windows-10-edition-upgrade.md)
        -  [인증서 설정](how-to-configure-certificates.md)
        -  [Windows Information Protection 설정](how-to-configure-windows-information-protection.md)
        -  [교육 설정](how-to-configure-education-settings.md)
        -  [사용자 지정 설정](how-to-configure-custom-settings.md)

    ![장치 프로필 만들기](./media/create-device-profile.png)
4. 설정 구성을 완료한 후 **프로필 만들기** 블레이드에서 **만들기**를 선택합니다.

프로필이 만들어지고 프로필 목록 블레이드에 표시됩니다.
계속해서 이 프로필을 그룹에 할당하려면 [장치 프로필을 할당하는 방법](how-to-assign-device-profiles.md)을 참조하세요.


### <a name="next-steps"></a>다음 단계
장치 프로필을 할당하는 방법에 대한 자세한 내용은 [Microsoft Intune을 사용하여 장치 프로필을 할당하는 방법](how-to-assign-device-profiles.md)을 참조하세요.

