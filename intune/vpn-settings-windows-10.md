---
title: "Windows 10 장치에 대한 Intune VPN 설정"
titlesuffix: Azure portal
description: "Windows 10 장치에서 VPN 연결을 구성하는 데 사용할 수 있는 Intune 설정을 알아봅니다.\""
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 1/26/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d126853051bb4a6c2f1ea6fbd54195ae06254b51
ms.sourcegitcommit: 2c7794848777e73d6a9502b4e1000f0b07ac96bc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2018
---
# <a name="vpn-settings-for-windows-10-devices-in-microsoft-intune"></a>Microsoft Intune의 Windows 10 장치에 대한 VPN 설정

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

선택한 설정에 따라 다음 목록의 일부 값을 구성할 수 없습니다.

> [!NOTE]
> 이 설정은 Windows Holographic for Business를 실행하는 장치에도 적용됩니다.


## <a name="base-vpn-settings"></a>기본 VPN 설정


- **연결 이름** - 이 연결에 대한 이름을 입력합니다. 최종 사용자가 장치에서 사용 가능한 VPN 연결 목록을 찾아볼 때 이 이름이 표시됩니다.
- **서버** - 장치를 연결할 한 대 이상의 VPN 서버를 추가합니다.
    - **추가** - 다음 정보를 지정할 수 있는 **행 추가** 블레이드를 엽니다.
        - **설명** - 서버의 설명이 포함된 이름(예: **Contoso VPN 서버**)을 지정합니다.
        - **IP 주소 또는 FQDN** - 장치가 연결되는 VPN 서버의 IP 주소 또는 정규화된 도메인 이름을 입력합니다. 예: **192.168.1.1**, **vpn.contoso.com**.
        - **기본 서버** - 이 서버를 장치에서 연결을 설정하는 데 사용할 기본 서버로 사용합니다. 기본적으로 하나의 서버만 설정해야 합니다.
    - **가져오기** - 설명, IP 주소 또는 FQDN, 기본 서버 형식의 쉼표로 구분된 서버 목록을 포함하는 파일로 이동합니다. **확인**을 선택하여 이를 **서버** 목록으로 가져옵니다.
    - **내보내기** - 서버 목록을 쉼표로 구분된 값(csv) 파일로 내보냅니다.

**연결 형식** - 다음 공급업체 목록에서 VPN 연결 형식을 선택합니다.
- **자동**
- **검사점 캡슐 VPN**
- **Citrix VPN**
- **Dell SonicWALL Mobile Connect**
- **F5 Edge Client**
- **IKEv2**
- **L2TP**
- **PPTP**
- **Pulse Secure**


**로그인 그룹 또는 도메인**(Dell SonicWALL 모바일 연결만) - 연결하려는 로그인 그룹 또는 도메인의 이름을 지정합니다.

**사용자 지정 XML**/**EAP XML** - VPN 연결을 구성하는 사용자 지정 XML 명령을 지정합니다.

**Pulse Secure의 예:**

```
    <pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>
```

**CheckPoint 모바일 VPN의 예:**

```
    <CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" />
```

**Dell SonicWALL 모바일 연결의 예:**

```
    <MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>
```

**F5 Edge Client의 예:**

```
    <f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>
```

사용자 지정 XML 명령을 작성하는 방법에 대한 자세한 내용은 각 제조업체의 VPN 설명서를 참조하세요.

사용자 지정 EAP XML을 만드는 방법에 대한 자세한 내용은 [EAP 구성](https://docs.microsoft.com/windows/client-management/mdm/eap-configuration)을 참조하세요.

**분할 터널링** - 장치에서 트래픽에 따라 사용할 연결을 결정할 수 있도록 하는 이 옵션을 **사용**하거나 **사용하지 않도록** 설정합니다. 예를 들어 호텔에 있는 사용자는 VPN 연결을 사용하여 작업 파일에 액세스하지만 일반적인 웹 검색에는 호텔의 표준 네트워크를 사용합니다.
- **이 VPN 연결에 대한 분할 터널링 경로** - 타사 VPN 공급자에 대한 선택적 경로를 추가합니다. 대상 접두사 및 각각의 접두사 크기를 지정합니다.

## <a name="apps-and-traffic-rules"></a>앱 및 트래픽 규칙

**이러한 앱만 VPN 연결을 사용하도록 제한** - 지정한 앱만 VPN 연결을 사용하도록 하려면 이 옵션을 선택합니다.
**연결된 앱** - 자동으로 VPN 연결을 사용하는 앱 목록을 제공합니다. 앱의 유형에 따라 앱 식별자가 결정됩니다. 유니버설 앱의 경우 패키지 패밀리 이름을 제공합니다. 데스크톱 앱의 경우에는 앱의 파일 경로를 제공합니다.

>[!IMPORTANT]
>앱별 VPN의 구성에서 사용하기 위해 컴파일하는 앱의 모든 목록을 보호하는 것이 좋습니다. 권한이 없는 사용자가 목록을 수정한 경우 해당 목록을 앱별 VPN 앱 목록으로 가져오는 경우 액세스 권한이 부여되면 안 되는 앱에 VPN 액세스 권한을 잠재적으로 부여하게 됩니다. 앱 목록을 보호할 수 있는 한 가지 방법은 ACL(액세스 제어 목록)을 사용하는 것입니다.

**이 VPN 연결에 대한 네트워크 트래픽 규칙** - VPN 연결을 위해 사용할 프로토콜, 로컬/원격 포트와 주소 범위를 선택합니다. 네트워크 트래픽 규칙을 만들지 않으면 모든 프로토콜, 포트 및 주소 범위를 사용할 수 있습니다. 규칙을 만들고 나면 해당 규칙에 지정하는 프로토콜, 포트 및 주소 범위만 VPN 연결에 사용됩니다.


## <a name="conditional-access"></a>조건부 액세스

**이 VPN 연결에 대한 조건부 액세스** - 클라이언트에서 장치 준수 흐름이 가능하게 합니다. 사용하도록 설정하면, VPN 클라이언트가 인증에 사용할 인증서를 가져오기 위해 Azure Active Directory와 통신하려고 합니다. 인증서 인증을 사용하려면 VPN을 설정해야 하고, VPN 서버가 Azure Active Directory에서 반환된 서버를 신뢰해야 합니다.

**대체 인증서를 사용한 SSO(Single Sign-On)** - 장치 준수에 대해 Kerberos 인증을 위한 VPN 인증 인증서와 다른 인증서를 사용합니다. 다음 설정으로 인증서를 지정합니다. 

- **확장 키 사용** - EKU(확장 키 사용)의 이름입니다.
- **개체 식별자** - EKU의 개체 식별자입니다.
- **발급자 해시** - SSO 인증서의 지문입니다.

## <a name="dns-settings"></a>DNS 설정

**이 VPN 연결의 DNS 이름 및 서버** - 연결이 설정된 후 VPN 연결에 사용할 DNS 서버를 선택합니다.
각 서버에 대해 다음을 지정합니다.
- **DNS 이름**
- **DNS 서버**
- **프록시**

## <a name="proxy-settings"></a>프록시 설정

- **자동으로 프록시 설정 검색** - VPN 서버에 연결을 위한 프록시 서버가 필요한 경우 장치가 연결 설정을 자동으로 검색할지 여부를 지정합니다. 자세한 내용은 Windows Server 설명서를 참조하세요.
- **자동 구성 스크립트** - 파일을 사용하여 프록시 서버를 구성합니다. 구성 파일이 포함된 **프록시 서버 URL**(예: **http://proxy.contoso.com)을 입력합니다.
- **프록시 서버 사용** - 프록시 서버 설정을 수동으로 입력하려는 경우 이 옵션을 선택합니다.
    - **주소** - 프록시 서버 주소를 IP 주소로 입력합니다.
    - **포트 번호** - 프록시 서버와 연결된 포트 번호를 입력합니다.
- **로컬 주소에 프록시 사용 안 함** - VPN 서버에 연결을 위한 프록시 서버가 필요한 경우 지정하는 로컬 주소에 대해 프록시 서버를 사용하지 않으려면 이 옵션을 선택합니다. 자세한 내용은 Windows Server 설명서를 참조하세요.
