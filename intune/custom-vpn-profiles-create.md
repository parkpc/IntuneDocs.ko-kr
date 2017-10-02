---
title: "Microsoft Intune을 사용하여 사용자 지정 VPN 프로필을 만드는 방법"
titleSuffix: Azure portal
description: "사용자 지정 구성을 사용하여 Intune에서 VPN 프로필을 만듭니다."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4c0bd439-3b58-420b-9a9a-282886986786
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7a3ab162ee950527c8d78123b4fd0a44c8bd7f29
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2017
---
# <a name="how-to-create-custom-vpn-profiles-in-microsoft-intune"></a>Microsoft Intune에서 사용자 지정 VPN 프로필을 만드는 방법

## <a name="create-a-custom-configuration"></a>사용자 지정 구성 만들기
사용자 지정 구성 정책을 사용하여 다음에 대한 VPN 프로필을 만들 수 있습니다.

* Android 4 이상을 실행하는 장치
* Windows 8.1 이상을 실행하는 등록된 장치
* Windows Phone 8.1 이상을 실행하는 장치
* Windows 10 데스크톱 이상을 실행하는 등록된 장치 
* Windows 10 Mobile을 실행하는 장치

표준 Intune VPN 정책에 사용하려는 설정이 없는 경우 이 유형의 정책이 유용할 수 있습니다.

## <a name="to-create-a-custom-configuration-policy"></a>사용자 지정 구성 정책을 만들려면

1. Azure 포털에 로그인합니다.
2. **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
3. **Intune** 블레이드에서 **장치 구성**을 선택합니다.
4. **장치 구성** 블레이드에서 **관리** > **프로필**을 선택합니다.
5. 프로필 블레이드에서 **프로필 만들기**를 선택합니다.
6. **프로필 만들기** 블레이드에서 VPN 프로필에 대한 **이름** 및 **설명**을 입력합니다.
7. **플랫폼** 드롭다운 목록에서 VPN 설정을 적용할 장치 플랫폼을 선택합니다. 현재 사용자 지정 장치 설정에 대해 다음 플랫폼 중 하나를 선택할 수 있습니다.
    - **OWA(Outlook Web Access)**
    - **iOS**(Apple Configurator에서 내보낸 파일을 사용하여 구성).
    - **macOS**(Apple Configurator에서 내보낸 파일을 사용하여 구성).
    - **Windows Phone 8.1**
    - **Windows 10 이상**
6. **프로필** 유형 드롭다운 목록에서 선택 **사용자 지정**을 선택합니다.
7. **사용자 지정 OMA-URI 설정** 블레이드에서 지정할 각 URI 설정에 대해 **추가**를 선택하고 요청된 정보를 제공한 다음 **확인**을 선택합니다. 아래 예를 살펴보세요.

   ![VPN 프로필 사용자 지정 구성 대화 상자](./media/Intune_Add_VPN_URI.png)

4.  필요한 URI 설정을 모두 입력한 후 **확인**을 선택하고 **프로필 만들기** 블레이드에서 **만들기**를 선택합니다.

프로필이 만들어지고 프로필 목록 블레이드에 표시됩니다.
계속해서 이 프로필을 그룹에 할당하려면 [장치 프로필을 할당하는 방법](device-profile-assign.md)을 참조하세요.




