---
title: "Android 장치에 대한 Intune VPN 설정 | Intune Azure 미리 보기 | Microsoft Docs"
description: "Intune Azure 미리 보기: Android 장치에서 VPN 연결을 구성하는 데 사용할 수 있는 Intune 설정을 알아봅니다."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 16c056ca-320e-4107-ad03-a0cf96c28885
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6cd3069a63bd657d1c9f5e33b96db39a3b3f98d2
ms.openlocfilehash: f93ab44889837fe8acc5dd5287b63f3b30678159


---

# <a name="vpn-settings-for-android-devices-in-intune-azure-preview"></a>Intune Azure 미리 보기의 Android 장치에 대한 VPN 설정

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

선택한 설정에 따라 아래 목록의 일부 값을 구성할 수 없습니다.

**연결 이름** - 이 연결에 대한 이름을 입력합니다. 최종 사용자가 장치에서 사용 가능한 VPN 연결 목록을 찾아볼 때 이 이름이 표시됩니다.
- **IP 주소 또는 FQDN** - 장치를 연결할 VPN 서버의 정규화된 도메인 이름 또는 IP 주소를 입력합니다. 예: **192.168.1.1**, **vpn.contoso.com**.
- **인증 방법** - 장치에서 VPN 서버에 인증할 방법을 선택합니다.
    - **인증서** - 이전에 연결을 인증하기 위해 만든 SCEP 또는 PKCS 인증서 프로필을 선택합니다. 인증서 프로필에 대한 자세한 내용은 [인증서를 구성하는 방법](how-to-configure-certificates.md)을 참조하세요.
    - **사용자 이름 및 암호** - 최종 사용자는 VPN 서버에 로그인하기 위해 사용자 이름 및 암호를 제공해야 합니다.
- **연결 형식** - 다음 공급업체 목록에서 VPN 연결 형식을 선택합니다.
    - **검사점 캡슐 VPN**
    - **Cisco AnyConnect**
    - **Dell SonicWALL Mobile Connect**
    - **F5 Edge Client**
    - **Pulse Secure**
    - **Citrix**

- **지문**(검사점 캡슐 VPN에만 해당) - 신뢰할 수 있는 VPN 서버를 확인하는 데 사용할 문자열(예: 'Contoso 지문 코드')을 지정합니다. 연결 시 동일한 지문을 제시하는 서버가 신뢰할 수 있는지 알 수 있도록 클라이언트에 지문을 보낼 수 있습니다. 장치에 지문이 아직 없으면 사용자에게 지문을 보여주면서 연결하려는 VPN 서버를 신뢰할 것인지 묻는 메시지가 표시됩니다. 사용자는 지문을 수동으로 확인한 후 연결 신뢰를 선택합니다.
- **Citrix VPN 특성에 대한 키 및 값 쌍을 입력합니다**(Citrix에만 해당) - Citrix에서 제공한 키 및 값 쌍을 입력하여 VPN 연결의 속성을 구성합니다.



<!--HONumber=Feb17_HO2-->


