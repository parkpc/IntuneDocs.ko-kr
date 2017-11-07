---
title: "Intune VPN 설정을 구성하는 방법"
titleSuffix: Azure portal
description: "관리하는 장치에서 Intune을 사용하여 VPN 연결을 구성하는 방법을 알아봅니다.\""
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 699fa64bc0f720b18c1376e39b85eccd9018bbaf
ms.sourcegitcommit: e9f9fccccef691333143b7523d1b325ee7d1915a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2017
---
# <a name="how-to-configure-vpn-settings-in-microsoft-intune"></a>Microsoft Intune에서 VPN 설정을 구성하는 방법

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

VPN(가상 사설망)을 사용하면 사용자가 회사 네트워크에 안전하게 원격으로 액세스할 수 있습니다. 장치는 VPN 연결 프로필을 사용하여 VPN 서버와의 연결을 시작합니다. Microsoft Intune의 **VPN 프로필**을 사용하여 조직의 사용자 및 장치에 VPN 설정을 할당하면 네트워크에 쉽고 안전하게 연결할 수 있습니다.

예를 들어 기업 네트워크에서 파일 공유에 연결하는 데 필요한 설정을 사용하여 모든 iOS 장치를 프로비전하려고 할 수 있습니다. 회사 네트워크에 연결하는 데 필요한 설정이 포함된 VPN 프로필을 만들어 iOS 장치를 이용하는 모든 사용자에게 할당합니다. 사용자에게 이용 가능한 네트워크 목록에 대한 VPN 연결이 표시되어 최소한의 노력으로 연결할 수 있습니다.

## <a name="vpn-connection-types"></a>VPN 연결 형식

다음의 연결 유형을 사용하여 VPN 프로필을 만들 수 있습니다.

|연결 유형|Android<br>Android for Work|iOS|macOS|Windows Phone 8.1|Windows 8.1|Windows 10|
|-|-|-|-|-|-|-|
|Pulse Secure|예|예|예|예|예|예|
|Cisco(IPsec)|아니요|예|아니요|아니요|아니요|아니요|
|Citrix|예|예|아니요|아니요|아니요|예|
|F5 Edge Client|예|예|예|예|예|예|
|Dell SonicWALL Mobile Connect|예|예|예|예|예|예|
|검사점 캡슐 VPN|예|예|예|예|예|예|
|Cisco AnyConnect|예|예|예|아니요|아니요|아니요|
|자동|아니요|아니요|아니요|아니요|아니요|예|
|IKEv2|아니요|아니요|아니요|아니요|아니요|예|
|L2TP|아니요|아니요|아니요|아니요|아니요|예|
|PPTP|아니요|아니요|아니요|아니요|아니요|예|
|사용자 지정|아니요|예|예|아니요|아니요|아니요|


> [!IMPORTANT]
> 장치에 할당된 VPN 프로필을 사용하려면 프로필에 적용 가능한 VPN 앱을 설치해야 합니다. [Microsoft Intune의 앱 관리란?](app-management.md) 항목의 정보를 참조하여 Intune을 사용해 앱을 할당할 수 있습니다.  

[사용자 지정 VPN 프로필 만들기](custom-vpn-profiles-create.md)의 URI 설정을 사용하여 사용자 지정 VPN 프로필을 만드는 방법을 알아봅니다.     

## <a name="create-a-device-profile-containing-vpn-settings"></a>VPN 설정을 포함하는 장치 프로필 만들기

1. Azure 포털에 로그인합니다.
2. **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
3. **Intune** 블레이드에서 **장치 구성**을 선택합니다.
2. **장치 구성** 블레이드에서 **관리** > **프로필**을 선택합니다.
3. 프로필 블레이드에서 **프로필 만들기**를 선택합니다.
4. **프로필 만들기** 블레이드에서 VPN 프로필에 대한 **이름** 및 **설명**을 입력합니다.
5. **플랫폼** 드롭다운 목록에서 VPN 설정을 적용할 장치 플랫폼을 선택합니다. 현재 VPN 장치 설정에 대해 다음 플랫폼 중 하나를 선택할 수 있습니다.
    - **OWA(Outlook Web Access)**
    - **Android for Work**
    - **Android**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 이상**
    - **Windows 10 이상**
6. **프로필** 유형 드롭다운 목록에서 선택 **VPN**을 선택합니다.
7. 선택한 플랫폼에 따라 구성할 수 있는 설정이 다릅니다. 각 플랫폼에 대한 자세한 설정을 보려면 다음 항목 중 하나로 이동하세요.
    - [Android and Android for Work 설정](vpn-settings-android.md)
    - [iOS 설정](vpn-settings-ios.md)
    - [macOS 설정](vpn-settings-macos.md)
    - [Windows Phone 8.1 설정](vpn-settings-windows-phone-8-1.md)
    - [Windows 8.1 설정](vpn-settings-windows-8-1.md)
    - [Windows 10 설정](vpn-settings-windows-10.md)
8. 완료되면 **프로필 만들기** 블레이드로 돌아가서 **만들기**를 누릅니다.

프로필이 만들어지고 프로필 목록 블레이드에 표시됩니다.
계속해서 이 프로필을 그룹에 할당하려면 [장치 프로필을 할당하는 방법](device-profile-assign.md)을 참조하세요.


## <a name="methods-of-securing-vpn-profiles"></a>VPN 프로필을 보호하는 방법

VPN 프로필에서는 다른 제조업체의 다양한 연결 형식과 프로토콜을 사용할 수 있습니다. 이러한 연결은 일반적으로 다음의 두 가지 방법 중 하나를 사용하여 보안이 유지됩니다.

### <a name="certificates"></a>인증서

VPN 프로필을 만들 때 이전에 Intune에서 만든 SCEP 또는 PKCS 인증서 프로필을 선택합니다. ID 인증서라고 합니다. 사용자 장치의 연결 허용을 설정하기 위해 만든 신뢰할 수 있는 인증서 프로필(또는 *루트 인증서*)에 대해 인증하는 데 사용됩니다. 신뢰할 수 있는 인증서는 VPN 연결을 인증하는 컴퓨터(대개 VPN 서버)에 할당됩니다.

Intune에서 인증서 프로필을 만들고 사용하는 방법에 대한 자세한 내용은 [Microsoft Intune을 사용하여 인증서를 구성하는 방법](certificates-configure.md)을 참조하세요.

### <a name="user-name-and-password"></a>사용자 이름 및 암호

사용자는 사용자 이름과 암호를 제공하여 VPN 서버에 인증합니다.
