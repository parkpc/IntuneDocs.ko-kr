---
title: "Android 장치에 대한 Intune 사용자 지정 설정"
titleSuffix: Azure portal
description: "Android 사용자 지정 프로필에서 사용할 수 있는 설정을 알아봅니다.\""
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 09/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 494b3892-916e-4b40-9b67-61adec889bdf
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 293137705fc8d5a37ac0dd7101a7ce80c9f7e917
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2018
---
# <a name="custom-settings-for-android-devices-in-microsoft-intune"></a>Microsoft Intune의 Android 장치에 대한 사용자 지정 설정

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Microsoft Intune Android **사용자 지정** 프로필을 사용하여 Android 장치에서 기능을 제어하는 데 사용할 수 있는 OMA-URI 설정을 할당합니다. 이는 많은 모바일 장치 제조업체가 장치 기능을 제어하는 데 사용하는 표준 설정입니다.

이 기능은 Intune 정책을 사용하여 구성할 수 없는 다음 Android 설정을 할당할 수 있도록 하기 위한 것입니다.

- [Microsoft Intune 사용자 지정 장치 프로필을 사용하여 미리 공유한 키로 Wi-Fi 프로필 만들기](/intune/wi-fi-profile-shared-key)
- [Microsoft Intune 사용자 지정 프로필을 사용하여 Android 장치에 대한 앱별 VPN 프로필 만들기](/intune/android-pulse-secure-per-app-vpn)
- [Microsoft Intune에서 사용자 지정 정책을 사용하여 Samsung Knox Standard 장치에 대해 앱 허용 및 차단](/intune/samsung-knox-apps-allow-block)

>[!IMPORTANT]
>현재 위에 나열된 설정만이 이 프로필 형식에 의해 구성될 수 있습니다. Android 장치는 구성할 수 있는 OMA-URI 설정의 전체 목록을 노출하지 않습니다. 추가 설정이 추가되었는지 확인하려는 경우 [Intune Uservoice 사이트](https://microsoftintune.uservoice.com/forums/291681-ideas)에서 요청하세요.

## <a name="custom-profile-settings-for-android-devices"></a>Android 장치에 대한 사용자 지정 프로필 설정

1. [Microsoft Intune에서 사용자 지정 장치 설정을 구성하는 방법](custom-settings-configure.md)의 지침을 사용하여 시작합니다.
2. **프로필 만들기** 블레이드에서 **설정**을 선택하여 하나 이상의 OMA-URI 설정을 추가합니다.
3. **행 편집** 블레이드에서 각 설정에 대해 다음 값을 구성합니다.
    - **이름** - 설정 목록에서 쉽게 식별할 수 있도록 OMA-URI 설정에 대한 고유한 이름을 입력합니다.
    - **설명** - 설정의 개요에 대한 설명과 찾을 때 도움이 되는 기타 관련 정보를 제공합니다.
    - **데이터 형식** - 이 OMA-URI 설정을 지정할 데이터 형식을 선택합니다. **문자열**, **문자열(XML)**, **날짜 및 시간**, **정수**, **부동 소수점** 또는 **부울** 중에서 선택합니다.
    - **OMA-URI** - 설정을 제공하려는 OMA-URI를 지정합니다.
    - **값** - 입력한 OMA-URI와 연결할 값을 입력합니다.
4. 완료되면 **확인**을 클릭한 다음 필요에 따라 설정을 계속 추가합니다.

## <a name="next-steps"></a>다음 단계

설정을 완료하면 프로필이 생성되어 프로필 목록 블레이드에 표시됩니다. 계속해서 이 프로필을 그룹에 할당하려면 [장치 프로필을 할당하는 방법](device-profile-assign.md)을 참조하세요.




