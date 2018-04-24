---
title: Microsoft Intune을 사용하여 사용자 지정 VPN 프로필을 만드는 방법
titleSuffix: ''
description: 사용자 지정 구성을 사용하여 Intune에서 VPN 프로필을 만듭니다.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ec9b959d086051985287a62f7d10fe8d4cbad7e9
ms.sourcegitcommit: 28ed8902a11500b195fff839d59b90c16af6e743
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/29/2018
---
# <a name="how-to-create-custom-vpn-profiles-in-microsoft-intune"></a>Microsoft Intune에서 사용자 지정 VPN 프로필을 만드는 방법

사용자 지정 구성 정책을 사용하여 다음 플랫폼에 대한 VPN 프로필을 만들 수 있습니다.

* Android 4 이상
* Windows 8.1 이상을 실행하는 등록된 장치
* Windows Phone 8.1 이상
* Windows 10 데스크톱 이상을 실행하는 등록된 장치 
* Windows 10 Mobile

표준 Intune VPN 정책에 사용하려는 설정이 없는 경우 이 유형의 정책이 유용할 수 있습니다.

## <a name="to-create-a-custom-configuration-policy"></a>사용자 지정 구성 정책을 만들려면

1. 로그인은 [Azure 포털](https://portal.azure.com)합니다.
2. **모든 서비스** > **Intune**을 선택합니다. Intune은 **모니터링 + 관리** 섹션에 있습니다.
3. **Intune** 창에서 **장치 구성**을 선택합니다.
2. **관리** 섹션 아래의 **장치 구성** 창에서 **프로필**을 선택합니다.
5. 프로필 창에서 **프로필 만들기**를 선택합니다.
6. **프로필 만들기** 창에서 VPN 프로필에 대한 **이름** 및 **설명**을 입력합니다.
7. **플랫폼** 드롭다운 목록에서 VPN 설정을 적용할 장치 플랫폼을 선택합니다. 현재 사용자 지정 장치 설정에 대해 다음 플랫폼 중 하나를 선택할 수 있습니다.
    - **OWA(Outlook Web Access)**
    - **Android for Work**
    - **iOS**(Apple Configurator에서 내보낸 파일을 사용하여 구성).
    - **macOS**(Apple Configurator에서 내보낸 파일을 사용하여 구성).
    - **Windows Phone 8.1**
    - **Windows 8.1 이상**
    - **Windows 10 이상**
6. **프로필** 유형 드롭다운 목록에서 선택 **사용자 지정**을 선택합니다.
7. **사용자 지정 OMA-URI 설정** 창에서 지정할 각 URI 설정에 대해 **추가**를 선택하고 요청된 정보를 제공한 다음, **확인**을 선택합니다. 아래 예를 살펴보세요.

   ![VPN 프로필 사용자 지정 구성 대화 상자](./media/Intune_Add_VPN_URI.png)

4.  필요한 URI 설정을 모두 입력한 후 **확인**을 선택하고 **프로필 만들기** 창에서 **만들기**를 선택합니다.

프로필이 만들어지고 프로필 목록 창에 표시됩니다.
계속해서 이 프로필을 그룹에 할당하려면 [장치 프로필을 할당하는 방법](device-profile-assign.md)을 참조하세요.




