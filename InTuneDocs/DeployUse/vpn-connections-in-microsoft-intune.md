---
title: "VPN 연결 | Microsoft Intune"
description: "VPN 프로필을 사용하여 조직의 사용자 및 장치에 VPN 설정을 배포합니다."
keywords: 
author: Nbigman
manager: angrobe
ms.date: 07/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: abc57093-7351-408f-9f41-a30877f96f73
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 300df17fd5844589a1e81552d2d590aee5615897
ms.openlocfilehash: 475c68f8812627cd58f86bb74d8c48988f53f7ed


---

# Microsoft Intune에서 VPN 연결
 VPN(가상 사설망)을 사용하면 사용자가 회사 네트워크에 안전하게 원격으로 액세스할 수 있습니다. 원격 사용자는 자신의 장치가 네트워크에 실제로 연결된 것처럼 작업할 수 있습니다. 장치는 VPN 연결 프로필을 사용하여 VPN 서버와의 연결을 시작합니다. Microsoft Intune의 *VPN 프로필*을 사용하여 조직의 사용자 및 장치에 VPN 설정을 배포합니다. 이러한 설정을 배포하여 최종 사용자가 회사 네트워크에 있는 리소스에 연결하는 데 필요한 노력을 최소화할 수 있습니다.

예를 들어 기업 네트워크에서 파일 공유에 연결하는 데 필요한 설정을 사용하여 모든 iOS 장치를 프로비전하려고 할 수 있습니다. 회사 네트워크에 연결하는 데 필요한 설정이 포함된 VPN 프로필을 만들어 iOS 장치를 이용하는 모든 사용자에게 배포합니다. 사용자에게 이용 가능한 네트워크 목록에 대한 VPN 연결이 표시되어 최소한의 노력으로 연결할 수 있습니다.

VPN 프로필을 사용하여 다음의 장치 유형을 구성할 수 있습니다.

* Android 4 이상을 실행하는 장치
* iOS 7.1 이상을 실행하는 장치
* Mac OS X 10.9 이상을 실행하는 장치
* Windows 8.1 이상을 실행하는 등록된 장치
* Windows Phone 8.1 이상을 실행하는 장치
* Windows 10 Desktop 및 Mobile을 실행하는 장치

VPN 프로필 구성 옵션은 선택하는 장치 유형에 따라 다릅니다.

## VPN 연결 형식

Intune에서는 다음의 연결 유형을 사용하는 VPN 프로필 만들기를 지원합니다.




연결 형식 |iOS 및 Mac OS X  |Android|Windows 8.1|Windows RT|Windows RT 8.1|Windows Phone 8.1|Windows 10 Desktop 및 Mobile |
----------------|------------------|-------|-----------|----------|--------------|-----------------|----------------------|
Cisco AnyConnect|예 |예   |아니요    |     아니요    |아니요  |아니요    | 예(OMA-URI, Mobile만)|     
Pulse Secure|예  |예 |예   |아니요  |예  |예| 예|        
F5 Edge Client|예 |예 |예 |아니요  |예  |   예 |  예|   
Dell SonicWALL Mobile Connect|예 |예 |예 |아니요  |예 |예 |예|         
CheckPoint Mobile VPN|예 |예 |예 |예 |예|예|예|
Microsoft SSL(SSTP)|아니요 |아니요 |아니요 |아니요 |아니요|아니요|VPNv1 OMA-URI*|
Microsoft 자동|아니요 |아니요 |아니요 |아니요 |아니요|예(OMA-URI)|예|
IKEv2|iOS 사용자 지정 프로필|아니요 |아니요 |아니요 |아니요|예(OMA-URI)|예|
PPTP|iOS 사용자 지정 프로필|아니요 |아니요 |아니요 |아니요|아니요|예|
L2TP|iOS 사용자 지정 프로필|아니요 |아니요 |아니요 |아니요|예(OMA-URI)|예|

\* Windows 10에 사용할 수 있는 추가 설정이 없습니다.

> [!IMPORTANT]
> 장치에 배포된 VPN 프로필을 사용하려면 프로필에 적용 가능한 VPN 앱을 설치해야 합니다. [Microsoft Intune에서 앱 배포](deploy-apps-in-microsoft-intune.md) 항목의 정보를 참조하여 Intune을 사용해 해당 앱을 배포할 수 있습니다.  

 URI 설정을 사용하여 사용자 지정 VPN 프로필을 만드는 방법에 대해 알아보려면 [VPN 프로필에 대한 사용자 지정 구성](custom-configurations-for-vpn-profiles.md)을 참조하세요.     

## VPN 프로필을 보호하는 방법

VPN 프로필에서는 다른 제조업체의 다양한 연결 형식과 프로토콜을 사용할 수 있습니다. 이러한 연결은 일반적으로 다음의 두 가지 방법 중 하나를 사용하여 보안이 유지됩니다.

### 인증서

VPN 프로필을 만들 때 이전에 Intune에서 만든 SCEP 또는 .PFX 인증서 프로필을 선택합니다.

ID 인증서라고 합니다. 사용자 장치의 연결 허용을 설정하기 위해 만든 신뢰할 수 있는 인증서 프로필(또는 루트 인증서)에 대해 인증하는 데 사용됩니다. 신뢰할 수 있는 인증서는 VPN 연결을 인증하는 컴퓨터(대개 VPN 서버)에 배포됩니다.

Intune에서 인증서 프로필을 만들고 사용하는 방법에 대한 자세한 내용은 [인증서 프로필을 통해 리소스 액세스 보안](secure-resource-access-with-certificate-profiles.md)을 참조하세요.

### 사용자 이름 및 암호

사용자는 사용자 이름과 암호를 제공하여 VPN 서버에 인증합니다.

## VPN 프로필 만들기

1. [Microsoft Intune 관리 콘솔](https://manage.microsoft.com)에서 **정책** > **정책 추가**를 선택합니다.
2. 관련 장치 종류를 확장하여 새 정책에 대한 템플릿을 선택한 다음 해당 장치에 대한 VPN 프로필을 선택합니다.
    * **VPN 프로필(Android 4 이상)**
    * **VPN 프로필(iOS 7.1 이상)**
    * **VPN 프로필(Mac OS X 10.9 이상)**
    * **VPN 프로필(Windows 8.1 이상)**
    * **VPN 프로필(Windows Phone 8.1 이상)**
    * **VPN 프로필(Windows 10 Desktop 및 Mobile 이상)**

 사용자 지정 VPN 프로필 정책만 만들고 배포할 수 있습니다. 권장 설정은 사용할 수 없습니다.

3. 다음 테이블을 사용하여 VPN 프로필 설정을 쉽게 구성할 수 있습니다.

설정 이름  |추가 정보  
---------|---------
**Name**     |Intune 콘솔에서 쉽게 식별할 수 있도록 VPN 프로필에 대한 고유한 이름을 입력합니다.         
**설명**     |VPN 프로필의 개요에 대한 설명과 찾을 때 도움이 되는 기타 관련 정보를 제공합니다.         
**VPN 연결 이름(사용자에게 표시)**     |VPN 프로필의 이름을 지정합니다. 사용자는 장치의 사용 가능한 VPN 연결 목록에서 이 이름을 볼 수 있습니다.         
**연결 형식**     |  VPN 프로필에서 사용할 연결 형식으로 다음 중 하나를 선택합니다. **Cisco AnyConnect**(Windows 8.1 또는 Windows Phone 8.1에 대해 사용할 수 없음), **Pulse Secure**, **F5 Edge Client**, **Dell SonicWALL Mobile Connect**, **CheckPoint Mobile VPN**.
**VPN 서버 설명**     | 장치가 연결될 VPN 서버에 대한 설명을 지정합니다. 예: **Contoso VPN 서버**. 연결 형식이 **F5 Edge Client**인 경우 **서버 목록** 필드를 사용하여 서버 설명 및 IP 주소 목록을 지정합니다.
**서버 IP 주소 또는 FQDN**    |장치를 연결할 VPN 서버의 정규화된 도메인 이름 또는 IP 주소를 입력합니다. 예: **192.168.1.1**, **vpn.contoso.com**.  연결 형식이 **F5 Edge Client**인 경우 **서버 목록** 필드를 사용하여 서버 설명 및 IP 주소 목록을 지정합니다.         |         
**서버 목록**     |**추가**를 선택하여 VPN 연결에 사용할 새 VPN 서버를 추가합니다. 또한 연결에 대한 기본 서버를 지정할 수도 있습니다. 연결 형식이 **F5 Edge Client**인 경우에만 이 옵션이 표시됩니다.         
**VPN 연결을 통해 모든 네트워크 트래픽 보내기**     |이 옵션을 선택하는 경우 모든 네트워크 트래픽이 VPN 연결을 통해 보내집니다. 이 옵션을 선택하지 않으면 클라이언트에서 타사 VPN 서버에 연결할 때 분할 터널링용 라우트를 동적으로 협상합니다. 회사 네트워크에 대한 연결만 VPN 터널을 통해 보내집니다. VPN 터널링은 인터넷에 있는 리소스에 연결할 경우에는 사용되지 않습니다.
**인증 방법**| VPN 연결에서 사용되는 인증 방법(**인증서** 또는 **사용자 이름 및 암호**)을 선택합니다. (연결 형식이 Cisco AnyConnect인 경우에는 **사용자 이름 및 암호**를 사용할 수 없습니다.) Windows 8.1의 경우 **인증 방법** 옵션을 사용할 수 없습니다.
**로그온 할 때마다 사용자 자격 증명 기억**|연결을 설정할 때마다 사용자가 자격 증명을 입력하지 않아도 되도록 사용자 자격 증명을 저장하려면 이 옵션을 선택합니다.
**클라이언트 인증을 위해 클라이언트 인증서 선택(ID 인증서)**|이전에 만든 클라이언트 SCEP 인증서를 선택합니다. VPN 연결을 인증하는 데 사용됩니다. Intune에서 인증서 프로필을 사용하는 방법에 대한 자세한 내용은 [인증서 프로필을 통해 리소스 액세스 보안](secure-resource-access-with-certificate-profiles.md)을 참조하세요. 인증 방법이 **인증서**인 경우에만 이 옵션이 표시됩니다.
**역할**| 이 연결에 대한 액세스 권한이 있는 사용자 역할의 이름을 지정합니다. 사용자 역할은 개인 설정과 옵션을 정의하고, 특정 액세스 기능을 사용 또는 사용하지 않도록 설정합니다. 연결 형식이 **Pulse Secure**인 경우에만 이 옵션이 표시됩니다.
**영역**|사용하려는 인증 영역의 이름을 지정합니다. 인증 영역은 Pulse Secure 연결 형식에서 사용하는 인증 리소스 그룹입니다. 연결 형식이 **Pulse Secure**인 경우에만 이 옵션이 표시됩니다.
**로그인 그룹 또는 도메인**|연결하려는 로그인 그룹 또는 도메인의 이름을 지정합니다. 연결 형식이 **Dell SonicWALL Mobile Connect**인 경우에만 이 옵션이 표시됩니다.
**지문**|신뢰할 수 있는 VPN 서버를 확인하는 데 사용할 문자열(예: 'Contoso 지문 코드')을 지정합니다. 연결 시 동일한 지문을 제시하는 서버가 신뢰할 수 있는지 알 수 있도록 클라이언트에 지문을 보낼 수 있습니다. 장치에 지문이 아직 없으면, 사용자에게 지문을 보여주면서 연결하려는 VPN 서버를 신뢰할 것인지 묻는 메시지가 표시됩니다. 사용자는 지문을 수동으로 확인한 후 연결할 **신뢰**를 선택합니다. 연결 형식이 **CheckPoint Mobile VPN**인 경우에만 이 옵션이 표시됩니다.
**앱 당 VPN**|앱이 실행될 때 연결이 열리도록 이 VPN 연결을 iOS 또는 Mac OS X 앱과 연결하려면 이 옵션을 선택합니다. 소프트웨어를 배포할 때 VPN 프로필을 앱과 연결할 수 있습니다. 자세한 내용은 [Microsoft Intune에서 앱 배포](deploy-apps-in-microsoft-intune.md) 항목을 참조하세요.
**프록시 설정 자동 검색**(iOS, Mac OS X, Windows 8.1 및 Windows Phone 8.1에만 해당)|VPN 서버에 연결을 위한 프록시 서버가 필요한 경우 장치가 연결 설정을 자동으로 검색할지 여부를 지정합니다. 자세한 내용은 Windows Server 설명서를 참조하세요.
**자동 구성 스크립트 사용**(iOS, Mac OS X, Windows 8.1 및 Windows Phone 8.1에만 해당)|VPN 서버에 연결을 위한 프록시 서버가 필요한 경우 설정을 정의하기 위해 자동 구성 스크립트를 사용할지 여부를 지정한 다음 설정이 포함된 파일에 대한 URL을 지정합니다. 자세한 내용은 Windows Server 설명서를 참조하세요.
**프록시 서버 사용**(iOS, Mac OS X, Windows 8.1 및 Windows Phone 8.1에만 해당)|VPN 서버에 연결을 위한 프록시 서버가 필요한 경우 이 옵션을 선택한 다음 프록시 서버의 주소 및 포트 번호를 지정합니다. 자세한 내용은 Windows Server 설명서를 참조하세요.
**로컬 주소에 대해 프록시 설정 사용 안 함**(iOS, Mac OS X, Windows 8.1 및 Windows Phone 8.1에만 해당)|VPN 서버에 연결을 위한 프록시 서버가 필요한 경우 지정하는 로컬 주소에 대해 프록시 서버를 사용하지 않으려면 이 옵션을 선택합니다. 자세한 내용은 Windows Server 설명서를 참조하세요.
**사용자 지정 XML**(Windows 8.1 이상 및 Windows Phone 8.1 이상에만 해당)|VPN 연결을 구성하는 사용자 지정 XML 명령을 지정합니다. **Pulse Secure**의 예: &lt;pulse-schema&gt;&lt;isSingleSignOnCredential&gt;true&lt;/isSingleSignOnCredential&gt;&lt;/pulse-schema&gt;. **CheckPoint Mobile VPN**의 예: &lt;CheckPointVPN port="443" name="CheckPointSelfhost" sso="true"  debug="3" /&gt;. **Dell SonicWALL Mobile Connect**의 예: &lt;MobileConnect&gt;&lt;Compression&gt;false&lt;/Compression&gt;&lt;debugLogging&gt;True&lt;/debugLogging&gt;&lt;packetCapture&gt;False&lt;/packetCapture&gt;&lt;/MobileConnect&gt;. **F5 Edge Client**의 예: &lt;f5-vpn-conf&gt;&lt;single-sign-on-credential /&gt;&lt;/f5-vpn-conf&gt;. 사용자 지정 XML 명령을 작성하는 방법에 대한 자세한 내용은 각 제조업체의 VPN 설명서를 참조하세요.
**DNS 접미사 검색 목록**(Windows Phone 8.1에만 해당)|각 줄에 하나의 DNS 접미사를 지정합니다. 지정하는 각 DNS 접미사는 짧은 이름을 사용하여 웹 사이트에 연결할 때 검색됩니다. 예를 들어 DNS 접미사 **domain1. contoso.com** 및 **domain2. contoso.com**을 지정하고 URL **http://mywebsite**를 방문하면 URL **http://mywebsite.domain1.contoso.com** 및 **http://mywebsite.domain2.contoso.com**이 검색됩니다.
**회사 Wi-Fi 네트워크에 연결된 경우 VPN 사용 안 함**(Windows Phone 8.1에만 해당)|장치가 회사 Wi-Fi 네트워크에 연결된 경우 VPN 연결을 사용하지 않도록 지정하려면 이 옵션을 선택합니다.
**가정용 Wi-Fi 네트워크에 연결된 경우 VPN 사용 안 함**(Windows Phone 8.1에만 해당)|장치가 가정용 Wi-Fi 네트워크에 연결된 경우 VPN 연결을 사용하지 않도록 지정하려면 이 옵션을 선택합니다.

Windows 10 Desktop 및 Mobile 장치에는 다음과 같은 추가 설정을 사용할 수 있습니다.

설정 이름  |추가 정보  
---------|---------
**네트워크 트래픽 규칙**|VPN 연결을 위해 사용할 프로토콜, 로컬/원격 포트와 주소 범위를 선택합니다. 네트워크 트래픽 규칙을 만들지 않으면 모든 프로토콜, 포트 및 주소 범위를 사용할 수 있습니다. 규칙을 만들고 나면 해당 규칙에 지정하는 프로토콜, 포트 및 주소 범위만 VPN 연결에 사용됩니다.
**경로**|VPN 연결을 사용할 경로를 선택합니다.
**DNS 서버**| 연결이 설정된 후 VPN 연결에 사용할 DNS 서버를 선택합니다.         
**연결된 앱**|자동으로 VPN 연결을 사용하는 앱 목록을 제공합니다. 앱 유형에 따라 앱 식별자가 결정됩니다. 유니버설 앱의 경우 패키지 패밀리 이름을 제공합니다. 데스크톱 앱의 경우에는 앱의 파일 경로를 제공합니다.          


> [!IMPORTANT]
> 앱별 VPN의 구성에서 사용하기 위해 컴파일하는 앱의 모든 목록을 보호하는 것이 좋습니다. 권한이 없는 사용자가 목록을 수정한 경우 해당 목록을 앱별 VPN 앱 목록으로 가져오는 경우 액세스 권한이 부여되면 안 되는 앱에 VPN 액세스 권한을 잠재적으로 부여하게 됩니다. 앱 목록을 보호하는 한 가지 방법은 ACL(액세스 제어 목록)을 사용하는 것입니다.

회사 경계 설정을 사용할 수 있는 경우의 예로, 원격 데스크톱에 대해서만 VPN을 사용하려는 경우를 들 수 있습니다. 이렇게 하려면 외부 포트 3996에서 프로토콜 27에 대한 트래픽을 허용하는 네트워크 트래픽 규칙을 만듭니다. 그러면 다른 트래픽은 VPN을 사용하지 않습니다.

분할 터널링의 트래픽을 처리하는 방법을 정의할 수 없는 VPN 연결 형식을 사용할 때 회사 경계에서 경로를 정의하면 유용합니다. 이 경우에는 **경로**를 사용하여 VPN을 사용할 경로를 나열합니다.

사용자 지정 OMA-URI 설정을 만들어 Windows 10 장치의 VPN 사용을 특정 앱으로 제한할 수 있습니다.

새 정책이 **정책** 작업 영역의 **구성 정책** 노드에 표시됩니다.

## 정책 배포

1.  **정책** 작업 영역에서 배포할 정책을 선택한 다음 **배포 관리**를 선택합니다.

2.   **배포 관리** 대화 상자에서

    -   정책을 배포하려면 정책을 배포하려는 그룹을 하나 이상 선택하고 **추가** &gt; **확인**을 선택합니다.

    -   정책을 배포하지 않고 대화 상자를 닫으려면 **취소**를 선택합니다.


배포 후 사용자는 장치의 VPN 연결 목록에서 지정된 VPN 연결 이름을 볼 수 있습니다.

**정책** 작업 영역의 **개요** 페이지에 있는 상태 요약 및 경고는 주의가 필요한 정책 문제를 식별합니다. 또한 상태 요약은 대시보드 작업 영역에 표시됩니다.

### 참고 항목
[VPN 프로필에 대한 사용자 지정 구성](Custom-configurations-for-VPN-profiles.md)

[Android Pulse Secure용 앱별 VPN](per-app-vpn-for-android-pulse-secure.md)



<!--HONumber=Jul16_HO4-->


