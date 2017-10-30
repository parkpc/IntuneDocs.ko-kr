---
title: "초기 버전"
description: 
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 10/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: a2e6fd2381286aa652a04b5ed34ab21c57ed85f6
ms.sourcegitcommit: bb2c181fd6de929cf1e5d3856e048d617eb72063
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/20/2017
---
# <a name="the-early-edition-for-microsoft-intune---october-2017"></a>Microsoft Intune 초기 버전 - 2017년 10월

**초기 버전**에서는 Microsoft Intune의 향후 릴리스에서 도입될 기능의 목록을 제공합니다. 이 정보는 제한적으로 제공되며 변경될 수 있습니다. 회사 외부에서 이 정보를 공유하지 마세요. 여기 나열된 일부 기능은 마감일을 맞추지 못할 위험이 있으며 다음 릴리스까지 지연될 수 있습니다. 다른 기능은 고객용 준비 상태를 확인하기 위해, 파일럿(플라이팅) 테스트 중 입니다. 질문이나 궁금한 내용이 있으면 Microsoft 제품 그룹 담당자에게 연락하세요.

이 페이지는 정기적으로 업데이트됩니다. 추가 업데이트가 있는지 다시 확인하세요.

> [!Note]
>Intune에 대해 다음 변경 사항을 개발 중입니다. 새로운 하이브리드 기능에 대한 자세한 내용은 [hybrid What’s New page](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management)(하이브리드 새로운 기능 페이지)를 참조하세요.

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->



## <a name="intune-in-the-azure-portal"></a>Azure Portal의 Intune

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Azure Active Directory 웹 사이트에는 Intune Managed Browser 앱이 필요하고 Managed Browser(공개 미리 보기)에 Single Sign-On을 지원할 수 있습니다.<!-- 710595 -->   
Azure AD(Azure Active Directory)를 사용하면 모바일 장치에서 웹 사이트에 대한 액세스를 Intune Managed Browser 앱으로 제한할 수 있습니다. Managed Browser에서 웹 사이트 데이터는 최종 사용자 개인 데이터와 별도로 안전하게 유지됩니다. 또한 Managed Browser는 Azure AD에서 보호하는 사이트에 Single Sign-On 기능을 지원합니다. Managed Browser에 로그인하거나 Intune에서 관리하는 다른 앱과 함께 장치에서 Managed Browser를 사용하면 사용자에게 자격 증명을 입력하지 않고도 Azure AD에서 보호되는 회사 사이트에 액세스할 수 있습니다. 이 기능은 OWA(Outlook Web Access) 및 SharePoint Online과 같은 사이트뿐만 아니라 Azure 앱 프록시를 통해 액세스되는 인트라넷 리소스와 같은 다른 회사 사이트에도 적용됩니다.

### <a name="troubleshoot-enrollment-issues------746324----"></a>등록 문제 해결<!--- 746324 --->  
문제 해결 작업 영역에서는 사용자 등록 문제를 표시합니다. 문제 및 제안된 수정 단계에 대한 세부 정보를 통해 관리자 및 도움말 지원 센터 운영자가 문제를 해결할 수 있습니다. 특정 등록 문제는 캡처되지 않고 일부 오류에는 수정 제안이 없을 수 있습니다.

### <a name="admins-can-now-configure-the-firewall-settings-on-a-device-using-a-device-configuration-profile----951708---"></a>관리자는 장치 구성 프로필을 사용하여 장치에서 방화벽 설정을 구성할 수 있습니다.<!-- 951708 -->   
관리자는 장치에 방화벽을 설정하고, 도메인, 개인 및 공용 네트워크에 다양한 프로토콜을 구성할 수도 있습니다.  이러한 방화벽 설정은 "Endpoint Protection" 프로필에서 찾을 수 있습니다.

### <a name="windows-defender-application-guard-helps-protect-devices-from-untrusted-websites-as-defined-by-your-organization----958257---"></a>Windows Defender Application Guard를 통해 조직에서 정의한 대로 신뢰할 수 없는 웹 사이트로부터 장치를 보호할 수 있습니다.<!-- 958257 -->   
관리자는 Windows Information Protection 워크플로 또는 장치 구성에서 새 "네트워크 경계" 프로필을 사용하여 사이트를 "신뢰할 수 있음" 또는 "협력"으로 정의할 수 있습니다. 64비트 Windows 10 장치의 신뢰할 수 있는 네트워크 경계에 나열되지 않은 사이트가 Microsoft Edge에 표시되는 경우 Hyper-V 가상 컴퓨터 내에서 브라우저를 대신 엽니다.

"Endpoint Protection" 프로필의 장치 구성 프로필에서 Application Guard를 찾을 수 있습니다. 여기에서부터 관리자는 가상화된 브라우저와 호스트 컴퓨터, 트러스트되지 않은 사이트와 신뢰할 수 있는 사이트 간에 상호 작용을 구성하고 가상화된 브라우저에서 생성된 데이터를 저장할 수 있습니다. 장치에서 Application Guard를 사용하려면 네트워크 경계를 먼저 구성해야 합니다. 장치에 네트워크 경계를 하나만 정의해야 합니다.  

### <a name="windows-defender-application-guard-on-windows-10-enterprise-provides-mode-to-trust-only-authorized-apps----1031096---"></a>Windows 10 Enterprise에서 Windows Defender Application Guard는 인증된 앱만을 신뢰하는 모드를 제공합니다.<!-- 1031096 -->    
수천 개의 새로운 악성 파일이 매일 생성되기 때문에 바이러스 백신 서명 기반 감지를 사용하여 맬웨어에 대항하는 방법은 더 이상 새로운 공격에 대한 적절한 방어를 제공할 수 없습니다. Windows 10 Enterprise에서 Windows Defender Application Guard를 사용하면 장치 구성을 변경할 수 있습니다(변경 전: 앱을 바이러스 백신 또는 기타 보안 솔루션으로 차단하지 않으면 신뢰할 수 있는 모드, 변경 후: 운영 체제가 기업에서 권한을 부여한 앱만을 신뢰하는 모드). Windows Defender Application Guard에서 응용 프로그램에 트러스트를 할당합니다.

Intune을 사용하면 "감사 전용" 모드 또는 적용 모드에서 응용 프로그램 제어 정책을 구성할 수 있습니다. 앱을 "감사 전용" 모드로 실행하면 차단되지 않습니다. "감사 전용" 모드는 로컬 클라이언트 로그에 있는 모든 이벤트를 기록합니다. Windows 구성 요소 및 Windows 스토어 앱만 실행할 수 있는지 아니면 Intelligent Security Graph에서 정의한 대로 평판이 좋은 추가 앱도 실행할 수 있는지 구성할 수 있습니다.

### <a name="new-enrollment-status-page-for-windows-10-enrollments---1063201--"></a>Windows 10 등록의 새 등록 상태 페이지<!--1063201-->    
이제 사용자가 Windows 10 장치를 등록할 때 표시되는 인사말을 구성할 수 있습니다. **등록 상태 화면**을 사용하여 해당 Windows 10 장치를 등록할 때 최종 사용자에게 표시될 사용자 지정 메시지 및 하이퍼링크를 구성합니다.  또한 **등록 상태 화면**에서는 최종 사용자에게 해당 장치에 적용되는 정책 설정의 진행률에 대한 보기를 제공합니다.  

### <a name="window-defender-exploit-guard-is-a-new-set-of-intrusion-prevention-capabilities-for-windows-10----1063615---"></a>Window Defender Exploit Guard는 Windows 10의 새로운 침입 방지 기능 집합입니다.<!-- 1063615 -->   
dow Defender Exploit Guard는 응용 프로그램의 악용 가능성을 줄이는 사용자 지정 규칙을 포함하고, 매크로 및 스크립트 위협을 방지하고, 평판이 좋지 않은 IP 주소에 대한 네트워크 연결을 자동으로 차단하고, 랜섬웨어 및 알 수 없는 위협으로부터 데이터를 보호할 수 있습니다. Windows Defender Exploit Guard는 다음과 같은 구성 요소로 구성됩니다.

- **ASR(Attack Surface Reduction)**은 매크로, 스크립트 및 전자 메일 위협을 방지할 수 있도록 하는 규칙을 제공합니다.
- **제어된 폴더 액세스**는 보호된 폴더의 콘텐츠에 대한 액세스를 자동으로 차단합니다.
- **네트워크 필터**는 앱에서 평판이 낮은 IP/도메인으로의 아웃바운드 연결을 차단합니다.
- **악용 보호**는 악용으로부터 응용 프로그램을 보호하는 데 사용할 수 있는 메모리, 제어 흐름 및 정책 제한을 제공합니다.

### <a name="app-conditional-launch-support----1193313---"></a>앱 조건부 시작 지원<!-- 1193313 -->
이제 IT 관리자는 Azure 관리 포털을 통해 요구 사항을 설정하여 응용 프로그램을 시작하는 경우 MAM(모바일 앱 관리)를 통해 숫자 PIN이 아닌 암호를 적용할 수 있습니다. 항목이 구성되면 사용자는 MAM 지원 응용 프로그램에 대한 액세스 권한을 가져오기 전에 메시지가 표시될 때 암호를 설정하고 사용합니다. 암호는 하나 이상의 특수 문자 또는 대/소문자 알파벳을 포함한 숫자 PIN으로 정의됩니다. Intune의 이번 릴리스에서는 **iOS에서만** 이 기능을 활성화합니다. Intune은 숫자 PIN과 유사한 방식으로 암호를 지원합니다. 즉, 최소 길이를 설정하며 반복 문자 및 시퀀스를 허용합니다. 이 기능을 사용하려면 응용 프로그램(즉, WXP, Outlook, Managed Browser, Yammer)에 참여하여 나중에 대상 응용 프로그램에 적용할 암호 설정을 준비하기 위해 코드와 Intune APP SDK를 통합합니다.

### <a name="app-version-number-for-line-of-business-in-device-install-status-report----1233999---"></a>장치 설치 상태 보고서의 기간 업무 앱에 대한 버전 번호 <!-- 1233999 -->  
장치 설치 상태 보고서는 iOS 및 Android용 기간 업무 앱의 앱 버전 번호를 표시합니다. 이 정보를 사용하여 앱 문제를 해결하거나 오래된 앱 버전을 실행하는 장치를 찾을 수 있습니다.

### <a name="co-management-for-windows-10-devices-----124445---"></a>Windows 10 장치의 공동 관리<!-- 124445 -->
공동 관리는 기존 관리에서 최신 관리에 대한 연결을 제공하고 단계별 접근 방법을 사용하여 전환할 수 있는 경로를 제공하는 솔루션입니다. 기본적으로 공동 관리는 Windows 10 장치를 Configuration Manager와 Microsoft Intune에서 동시에 관리할 수 있는 솔루션입니다. 뿐만 아니라 AD(Active Directory) 및 Azure AD(Azure Active Directory)에 조인되됩니다.  이 구성을 통해 한 번에 경로로 이동할 수 없는 경우 조직에 적합한 속도로 시간이 지남에 따라 현대화하는 경로를 제공합니다.  

### <a name="set-access-for-apps-by-minimum-android-security-patch-on-the-device---1278463---"></a>장치에 대한 최소 Android 보안 패치를 기준으로 앱에 대한 액세스 권한 설정<!-- 1278463 -->   
관리자는 관리되는 계정 아래에서 관리되는 응용 프로그램에 대한 액세스 권한을 얻기 위해 장치에 설치해야 하는 최소 Android 보안 패치를 정의할 수 있습니다.

> [!Note]  
> 이 기능은 Android 6.0 이상 장치에서 Google에 의해 릴리스된 보안 패치만을 제한합니다.

### <a name="new-device-restriction-settings-for-windows-10---------1308850---"></a>Windows 10의 새 장치 제한 설정<!-- 1308850 -->
-    메시지(모바일 전용) - 테스트 또는 MMS 메시지 사용 안 함
-    암호 - FIPS 사용하기 위한 설정 및 인증에 Windows Hello 보조 장치 사용 
-    표시 - 레거시 앱에 GDI Scaling 켜기 또는 끄기 설정


### <a name="windows-10-kiosk-mode-device-restrictions----1308872---"></a>Windows 10 키오스크 모드 장치 제한<!-- 1308872 -->   
Windows 10 장치 사용자를 키오스크 모드로 제한할 수 있습니다. 그러면 미리 정의된 앱의 집합으로 사용자를 제한합니다.  이렇게 하려면 Windows 10 장치 제한 프로필을 만들고 키오스크 설정을 설정합니다.

키오스크 모드는 **단일 앱**(사용자가 하나의 앱을 실행하도록 허용) 또는 **다중 앱**(앱 집합에 대한 액세스 권한 허용)이라는 두 가지 모드를 지원합니다.  사용자 계정 및 장치 이름을 정의합니다. 여기서는 지원되는 앱을 결정합니다.  사용자는 정의된 앱에만 로그인할 수 있습니다.  자세한 내용은 [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp)를 참조하세요. 

키오스크 모드에는 다음 항목이 필요합니다.

- Intune는 MDM 기관이어야 합니다.
- 앱은 이미 대상 장치에 설치되어 있어야 합니다.
- 장치는 [제대로 프로비전](https://docs.microsoft.com/windows/configuration/set-up-a-kiosk-for-windows-10-for-desktop-editions)되어야 합니다.

### <a name="new-device-configuration-profile-for-creating-network-boundaries----1311967---"></a>네트워크 경계를 만들기 위한 새 장치 구성 프로필<!-- 1311967 -->   
**네트워크 경계**라는 장치 구성 프로필을 만들었습니다. 이 기능은 다른 장치 구성 프로필을 통해 찾을 수 있습니다. 이 프로필을 사용하여 협력 및 신뢰할 수 있도록 하려는 온라인 리소스를 정의합니다. Windows Defender Application Guard 및 Windows Information Protection과 같은 기능을 장치에서 사용하기 *전에* 장치의 네트워크 경계를 정의해야 합니다. 각 장치에 네트워크 경계를 하나만 정의해야 합니다.

엔터프라이즈 클라우드 리소스, IP 주소 범위 및 내부 프록시 서버를 신뢰할 수 있다고 정의할 수 있습니다. 네트워크 경계를 정의하면 Windows Defender Application Guard 및 Windows Information Protection과 같은 다른 기능에서 사용할 수 있습니다.

###  <a name="two-additional-settings-for-windows-defender-antivirus----1338409---"></a>Windows Defender Antivirus의 두 가지 추가 설정<!-- 1338409 -->  
**파일 차단 수준**

| | |
|---|---|
| 구성되지 않음 | **구성되지 않음**에서는 기본 Windows Defender Antivirus 차단 수준을 사용하고 올바른 파일을 감지하는 위험을 늘리지 않고도 강력한 감지 기능을 제공합니다. |
| 높음 | **높음**은 강력한 검색 수준에 적용됩니다.
| 높음 +  | **높음 +**은 클라이언트 성능에 영향을 줄 수 있는 추가 보호 수단으로 높음 수준을 제공합니다.
| 허용 오차 제로  | **허용 오차 제로**는 알 수 없는 실행 파일을 모두 차단합니다. |

가능성은 낮지만 **높음**으로 설정하면 올바른 파일 일부를 감지할 수도 있습니다.
파일 차단 수준을 기본인 **구성되지 않음**으로 설정하는 것이 좋습니다.

**클라우드에 의한 파일 검사의 제한 시간 확장**  

| | |
|--|--|
| 시간(초, 0~50) | Windows Defender Antivirus가 클라우드의 결과를 기다리는 동안 파일을 차단해야 하는 최대 시간을 지정합니다. 기본 시간은 10초입니다. 여기에서 지정된 추가 시간(최대 50초)은 해당 10초에 추가됩니다. 대부분의 경우에 검사는 최대값보다 훨씬 적은 시간이 걸립니다. 시간을 확장하면 클라우드가 의심스러운 파일을 철저하게 조사할 수 있습니다. 이 설정을 사용하고 추가로 적어도 20초를 지정하는 것이 좋습니다. |


### <a name="support-for-symantec-cloud-certification-authority-ca-----1333638---"></a>Symantec 클라우드 CA(인증 기관)에 대한 지원<!-- 1333638 -->    
이제 Intune은 지원 Symantec 클라우드 CA 클라우드를 지원합니다. 이 기능을 사용하면 Intune 인증서 커넥터가 Symantec 클라우드 CA에서 Intune 관리 장치에 PKCS 인증서를 발급할 수 있습니다. Microsoft CA(인증 기관)에서 이미 Intune 인증서 커넥터를 사용하는 경우 기존 Intune 인증서 커넥터 설정을 활용하여 Symantec CA 지원을 추가할 수 있습니다.



### <a name="citrix-vpn-added-for-windows-10-devices----1512457---"></a>Windows 10 장치에 추가된 Citrix VPN<!-- 1512457 -->  
고객이 Windows 10 장치에 Citrix VPN을 구성할 수 있습니다. Windows 10 이상에 VPN을 구성하는 경우 **기본 VPN** 블레이드의 *연결 형식 선택* 목록에서 Citrix VPN을 선택할 수 있습니다.

> [!Note]
> iOS 및 Android용 Citrix 구성이 있습니다.





<!-- the following are present prior to 1710 -->

### <a name="google-play-protect-support-on-android----908720----"></a>Android에서 Google Play 보호 지원 <!-- 908720  -->  
Android Oreo가 출시되면서 Google은 사용자와 조직이 보안 앱과 보안 Android 이미지를 실행할 수 있는 Google Play 보호라는 보안 기능 제품군을 소개합니다. Intune은 SafetyNet 원격 증명을 비롯하여 Google Play 보호 기능을 지원합니다.  관리자는 Google Play 보호를 구성하고 정상 상태를 유지하는 데 필요한 준수 정책 요구 사항을 설정할 수 있습니다. **SafetyNet 장치 증명** 설정은 장치가 정상 상태이고 손상되지 않았음을 확인하기 위해 장치를 Google 서비스에 연결하도록 합니다. 또한 관리자는 Google Play 서비스에서 설치된 앱을 확인하도록 하기 위해 Android for Work에 대한 구성 프로필 설정을 설정할 수 있습니다.  장치가 Google Play 보호 요구 사항을 준수하지 않는 경우 조건부 액세스는 사용자가 회사 리소스에 액세스하는 것을 차단합니다. 


### <a name="support-for-windows-10-edition-upgrade-policy------903672archived-1119689---"></a>Windows 10 버전 업그레이드 정책에 대한 지원  <!-- 903672(archived), 1119689 -->  
Windows 10 장치를 Windows 10 Education, Windows 10 Education N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional Education 및 Windows 10 Professional Education N으로 업그레이드하는 Windows 10 버전 업그레이드 정책을 만들 수 있습니다. Windows 10 버전 업그레이드에 대한 자세한 내용은 [Windows 10 버전 업그레이드 구성 방법](edition-upgrade-configure-windows-10.md)을 참조하세요.


### <a name="intune-mam-and-outlook-for-android-add-ins-----1450688---"></a>Android용 Intune MAM 및 Outlook 추가 기능 <!-- 1450688 -->
몇 주 후에 Office 팀은 Android의 Outlook용 추가 기능을 발표할 것입니다. 이 추가 기능 집합은 Windows, iOS, 웹 및 Mac의 Outlook에 이미 존재합니다. 추가 기능은 Exchange를 통해 관리되기 때문에 사용자는 Outlook 및 관리되지 않는 추가 기능 응용 프로그램에서 데이터와 메시지를 복사하고 공유할 수 있습니다(Exchange 관리자가 추가 기능에 대한 액세스를 해제하지 않은 경우). 

추가 기능에 대한 사용자 액세스 권한을 관리하려면 Exchange 관리자와 함께 작업하여 MAM 데이터 보호 정책이 추가 기능에 적용되도록 합니다.

#### <a name="how-does-this-affect-me"></a>이 변경 사항은 어떤 영향을 미치나요?
Exchange 정책이 이미 추가 기능을 사이드로드하거나 설치하지 않도록 설정된 경우 더 읽지 마세요. MAM 정책은 예상대로 적용됩니다. 그러나 Android의 Outlook 내에서 잘라내기, 복사 및 붙여넣기 작업을 제한하도록 MAM의 정책을 설정하고 Exchange의 추가 기능 정책을 설정하지 않은 경우, 기본적으로 사용자가 Outlook에 추가 기능을 설치할 수 있습니다. 이러한 추가 기능은 메시지 본문, 제목 및 기타 메시지 속성에 액세스할 수 있습니다. Exchange 관리자가 "내 마켓플레이스 앱" 및 "내 사용자 지정 앱" 역할을 제거하도록 하여 사용자가 추가 기능을 설치하는 기능을 해제할 수 있습니다.

Exchange에서 설정 변경은 Windows, iOS, 웹, Mac 및 모바일의 Outlook에 적용됩니다. 

#### <a name="what-do-i-need-to-do"></a>어떤 작업을 수행해야 하나요?
지금 Exchange 정책을 검토합니다. IT 및 지원 센터 직원에게 알립니다. 궁금한 사항이 있으면 지원 팀에 문의하세요. 




<!-- the following are present prior to 1709 -->

### <a name="actions-for-non-compliance----730266--846515---"></a>비준수에 대한 작업 <!--730266  846515 -->     
*비준수에 대한 작업*은 정책을 준수하지 않는 장치에 조치를 취할 수 있는 준수 정책의 새로운 기능입니다. 단일 또는 여러 작업을 지정할 수 있으며, 이러한 작업이 수행되어야 하는 기간을 지정할 수 있습니다. 예를 들어 장치가 메일을 통해 비준수 상태가 된 직후에 사용자에게 비준수 장치를 알리거나 조건부 액세스를 통해 3일 유예 기간이 지난 후 비준수 장치가 회사 리소스에 액세스하는 것을 못하도록 차단할 수 있습니다.

### <a name="android-for-work-support-for-lookout----1087312---"></a>Android for Work의 Lookout 지원 <!-- 1087312 -->   
Lookout for Work 앱 사용 시 Lookout이 설치된 Intune 커넥터가Android for Work 장치를 지원할 예정입니다. 그러면 컨테이너 내부 또는 외부에서 Lookout 앱을 배포할 수 있습니다.

### <a name="intune-app-protection-and-citrix-mdx-development-tools----709185---"></a>Intune 앱 보호 및 Citrix MDX 개발 도구<!-- 709185 -->
Citrix XenMobile MDX와 Microsoft Intune의 조합으로 장치와 앱을 관리할 수 있습니다. 이 옵션을 사용하면 Citrix의 mVPN 기술을 사용하면서 Intune 앱 보호 정책으로 앱을 관리할 수 있습니다.

Intune 앱 래핑 도구와 iOS 및 Android용 Intune 앱 SDK를 포함하는 코드 리포지토리를 찾아 Citrix MDX mVPN 기술과 통합할 수 있습니다.

#### <a name="how-integration-with-intune-works"></a>Intune과 통합하는 방법
위험은 Zimperium을 실행하는 장치에서 수집된 원격 분석에 따라 평가됩니다. Intune 장치 준수 정책을 통해 사용하도록 설정된 Zimperium 위험 평가에 따라 EMS 조건부 액세스 정책을 구성할 수 있습니다. 이 정책을 사용하여 회사 리소스에 액세스하는 미준수 장치를 감지된 위협에 따라 허용하거나 차단할 수 있습니다.

### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>온-프레미스 Exchange Connector 고가용성 지원 <!-- 676614 -->   
온-프레미스 Exchange Connector에 대해 여러 CAS(클라이언트 액세스 서버) 역할을 사용할 수 있습니다. 예를 들어 주 CA에서 오류가 발생할 경우 Exchange Connector는 다른 CAS로 대체하기 위한 쿼리를 수신합니다. 이 기능은 서비스가 중단되지 않도록 합니다.

### <a name="system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>Exchange Connector용 System Center Operations Manager 관리 팩 <!-- 885457 -->   
Exchange Connector 로그를 구문 분석하는 데 도움이 되도록 Exchange Connector용 System Center Operations Manager 관리 팩이 제공될 예정입니다. 이 관리 팩을 사용하면 문제를 해결해야 할 때 Intune을 다른 방식으로 모니터링할 수 있습니다.


## <a name="intune-apps"></a>Intune 앱


### <a name="redirecting-macos-users-to-our-new-company-portal-app---1380728--"></a>새 회사 포털 앱에 macOS 사용자 리디렉션<!--1380728-->   
최종 사용자가 macOS 장치를 등록하기 위해 회사 포털 웹 사이트에 로그인하는 경우 프로세스를 완료하기 위해 macOS용 새 회사 포털 앱을 다운로드하도록 리디렉션됩니다. 이는 macOS 장치에서 OS X El Capitan 10.11 이상을 사용하는 경우에 발생합니다. 

### <a name="certificate-based-authentication-support-on-the-company-portal-for-ios---1029830--"></a>iOS용 회사 포털에서 인증서 기반 인증 지원<!--1029830-->
iOS용 회사 포털 앱에서 CBA(인증서 기반 인증)에 대한 지원을 추가했습니다. CBA를 사용하는 사용자는 사용자 이름을 입력한 후 "인증서를 사용하여 로그인" 링크를 누릅니다. CBA는 이미 Android 및 Windows용 회사 포털 앱에서 지원되고 있습니다. [회사 포털 앱에 로그인](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal) 페이지에서 자세히 알아볼 수 있습니다.

<!-- the following are present prior to 1710 -->



### <a name="apps-that-are-available-with-or-without-enrollment-can-now-be-installed-without-being-prompted-for-enrollment----1334712---"></a>등록을 하거나 등록을 하지 않고 사용할 수 있는 앱이 이제 등록을 묻는 메시지가 표시되지 않고 설치될 수 있습니다. <!-- 1334712 -->
Android 회사 포털 앱에서 등록을 하거나 등록을 하지 않고 사용할 수 있는 회사 앱이 등록을 묻는 메시지가 표시되지 않고 설치될 수 있습니다.


<!-- the following are present prior to 1709 -->

### <a name="intune-managed-browser-support-for-ios-and-android----1374196---"></a>iOS 및 Android를 위한 Intune Managed Browser 지원 <!-- 1374196 -->
2017년 10월을 기준으로 Android 앱에서 Intune Managed Browser 앱은 Android 4.4 이상을 실행하는 장치만 지원합니다. iOS의 Intune Managed Browser 앱은 iOS 9.0 이상을 실행하는 장치만 지원합니다. Android 및 iOS 이전 버전에서도 계속 Managed Browser를 사용할 수는 있지만 새로운 버전의 앱을 설치할 수 없고 모든 기능을 액세스하지 못할 수 있습니다. 이러한 장치를 지원되는 운영 체제 버전으로 업데이트하는 것이 좋습니다.


### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>사용자가 등록이 허용된 최대 장치 수에 도달하면 표시되는 향상된 오류 메시지 <!-- 1270370 -->
일반 오류 메시지 대신 최종 사용자에게 “IT 관리자가 허용한 최대 장치 수를 등록했습니다. 등록된 장치를 제거하거나 IT 관리자에게 도움을 요청하십시오.”라는 친숙하고 조치를 수행할 수 있는 오류 메시지가 표시됩니다.




## <a name="notices"></a>알림

### <a name="device-and-app-management-integration----677972---"></a>장치 및 앱 관리 통합<!-- 677972 -->   
이제 Azure Portal에서 Intune의 MDM(모바일 장치 관리) 및 MAM(모바일 응용 프로그램 관리)에 모두 액세스할 수 있습니다. Intune은 응용 프로그램 및 장치 관리와 관련된 IT 관리자 환경을 통합하기 시작했습니다. 이러한 변경 내용을 통해 장치 및 앱 관리 환경을 단순화할 수 있습니다.

[Intune 지원팀 블로그](https://blogs.technet.microsoft.com/intunesupport/2017/09/19/support-tip-setting-up-communication-between-mam-managed-and-mdm-managed-apps/)에서 발표된 MAM 및 MDM 변경 내용에 대해 자세히 알아봅니다.




### <a name="see-also"></a>참고 항목
최근 개발 작업에 대한 자세한 내용은 [Microsoft Intune의 새로운 기능](whats-new.md)을 참조하세요.
