---
title: "초기 버전"
description: 
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 11/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f4fd810529732d2b24b948eb0ae741d37e0fb59e
ms.sourcegitcommit: d64b03bff0566f08d88ecb488dd48f19af74cab3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="the-early-edition-for-microsoft-intune---december-2017"></a>Microsoft Intune 초기 버전 - 2017년 12월

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

### <a name="app-protection-policies-----679615---"></a>앱 보호 정책 <!-- 679615 -->
Intune 앱 보호 정책은 전체 테넌트의 모든 사용자에 대해 보호를 빠르게 사용할 수 있도록 전역 기본 정책을 만드는 기능을 제공합니다.

### <a name="revoking-ios-volume-purchase-program-apps-----820863---"></a>iOS Volume-Purchase Program 앱 철회 <!-- 820863 -->
하나 이상의 iOS VPP(Volume-Purchase Program) 앱이 설치된 지정된 장치의 경우 장치의 관련 장치 기반 앱 라이선스를 철회할 수 있습니다. 앱 라이선스를 철회해도 장치에서 관련 VPP 앱이 제거되지 않습니다. VPP 앱을 제거하려면 할당 작업을 **제거**로 변경해야 합니다. 자세한 내용은 [Microsoft Intune을 사용하여 대량 구매 프로그램을 통해 구매한 iOS 앱을 관리하는 방법](vpp-apps-ios.md)을 참조하세요.

### <a name="revoke-licenses-for-an-ios-volume-purchasing-program-token----820870---"></a>iOS Volume Purchasing Program 토큰에 대한 라이선스 철회 <!-- 820870 -->
지정된 VPP 토큰에 대한 모든 iOS VPP(Volume-Purchase Program) 앱의 라이선스를 철회할 수 있습니다.

### <a name="delete-an-ios--volume-purchasing-program-token----820879---"></a>iOS Volume Purchasing Program 토큰 삭제 <!-- 820879 -->
콘솔을 사용하여 iOS VPP(Volume-Purchase Program) 토큰을 삭제할 수 있습니다. VPP 토큰의 중복 인스턴스가 있는 경우 이 기능이 필요할 수 있습니다.

### <a name="network-access-control-nac-device-check-in-reporting-----1232250---"></a>NAC(네트워크 액세스 제어) 장치 체크 인 보고 <!-- 1232250 -->
이 변경을 수행하기 전에 IT 관리자는 Intune 쪽에서 NAC 관리 장치가 NAC 솔루션과 통신하는지 여부를 확인할 수 없습니다. NAC 관리 장치가 NAC 솔루션과 통신하지 않는 경우 장치는 NAC 솔루션에서 비준수로 간주하므로 NAC 솔루션 자체에서 차단되고 나중에 장치 준수 상태에 기반을 둔 조건부 액세스 정책에 의해 차단됩니다.

이 변경을 수행하면 IT 관리자는 어떤 NAC 장치가 NAC 솔루션과 성공적으로 통신하는지 확인할 수 있습니다. 이 새로운 기능은 Intune 내의 장치 준수 워크로드에 있는 두 개의 새 모니터링 기능으로 구성되며 통계는 아래와 같이 표시됩니다.
- **지난 1시간의 평균 NAC 호출**
- **마지막 NAC 들어오는 요청(날짜/시간)**

### <a name="new-ios-device-action------1244701---"></a>새로운 iOS 장치 작업 <!-- 1244701 -->
iOS 10.3 감독된 장치를 종료할 수 있습니다. 이 작업을 수행하면 최종 사용자에게 경고하지 않고 장치가 즉시 종료됩니다. **장치** 워크로드에서 장치를 선택하면 장치 속성에서 **시스템 종료(감독 모드인 경우에만)** 작업을 찾을 수 있습니다.

### <a name="palo-alto-vpn-now-supported----1333680-eeready---"></a>이제 Palo Alto VPN이 지원됨 <!-- 1333680 eeready -->
기본 VPN을 구성하면 **연결 형식** 목록에 Palo Alto VPN이 포함됩니다.

### <a name="multiple-connector-support-for-scep-and-pfx-certificate-handling----1361755-eeready---"></a>SCEP 및 PFX 인증서 처리에 대한 여러 커넥터 지원 <!-- 1361755 eeready -->
온-프레미스 NDES Connector를 사용하여 인증서를 장치에 전달하는 고객은 단일 테넌트에서 여러 커넥터를 구성할 수 있습니다.

이 새로운 기능은 다음 시나리오를 지원합니다.

- **고가용성**

    각 NDES Connector는 Intune에서 인증서 요청을 풀합니다.  하나의 NDES Connector가 오프라인으로 전환될 경우 다른 커넥터는 계속 요청을 처리할 수 있습니다.

### <a name="new-automatic-redeployment-setting----1469168---"></a>새 자동 재배포 설정 <!-- 1469168 -->
이 설정을 통해 사용자는 장치 잠금 화면에서 **Ctrl + Win + R**을 사용하여 모든 사용자 데이터 및 설정을 삭제할 수 있습니다. 장치가 자동으로 재구성되고 관리에 다시 등록됩니다.

이 설정은 Windows 10 -> [장치 제한] -> [일반] -> [자동 재배포]에서 찾을 수 있습니다.

### <a name="install-office-apps-on-macos-devices----1494311---"></a>macOS 장치에 Office 앱 설치 <!-- 1494311 -->
macOS 장치에 Office 앱을 설치할 수 있습니다. 새 앱 유형을 사용하여 Word, Excel, PowerPoint, Outlook 및 OneNote를 설치할 수 있습니다. 또한 이들 앱은 MAU(Microsoft 자동 업데이트)와 함께 제공되므로 앱을 안전하게 최신 상태로 유지할 수 있습니다.

### <a name="surface-hub-resource-account-supported----1566442-eeready---"></a>Surface Hub 리소스 계정 지원됨 <!-- 1566442 eeready -->
관리자가 Surface Hub와 연결된 리소스 계정을 정의하고 업데이트할 수 있도록 새 장치 작업이 추가될 예정입니다.

리소스 계정은 Surface Hub에서 Skype/Exchange로 인증하는 데 사용되므로 모임에 참여할 수 있습니다. Surface Hub는 모임에서 회의실로 표시되도록 고유한 리소스 계정을 만들 수 있습니다. 예를 들어, 리소스 계정은 *회의실 B41/6233*으로 표시될 수 있습니다. Surface Hub의 리소스 계정(장치 계정이라고 함)은 일반적으로 회의실 위치에 대해 구성되고 다른 리소스 계정 매개 변수를 변경해야 할 경우 구성되어야 합니다.

관리자가 장치에서 리소스 계정을 업데이트하려는 경우 장치와 연결된 현재 Active Directory/Azure Active Directory 자격 증명을 제공해야 합니다. 장치에 대한 암호 순환이 켜져 있는 경우 관리자는 Azure Active Directory로 이동하여 암호를 찾아야 합니다.

> [!NOTE]
> 모든 필드는 번들로 전송되며 이전에 구성된 모든 필드를 덮어씁니다. 빈 필드도 기존 필드를 덮어씁니다.

설정 관리자가 다음을 구성할 수 있습니다.

- **리소스 계정**  

   - **Active Directory 사용자**   
   Domainname\username 또는 UPN(사용자 계정 이름): user@domainname.com
   - **암호**


- **선택적 리소스 계정 매개 변수**(지정된 리소스 계정을 사용하여 설정해야 함)
   - **암호 순환 기간**   
     보안상의 이유로 Surface Hub에서 자동으로 계정 암호를 업데이트하도록 합니다. 이 옵션을 사용하도록 설정한 후에 매개 변수를 구성하려면 먼저 Azure Active Directory의 계정에서 암호를 재설정해야 합니다.

   - **SIP(Session Initiation Protocol) 주소**    
     자동 검색이 실패할 경우에만 사용됩니다.

   - **메일**    
     장치/리소스 계정의 메일 주소입니다.

   - **Exchange Server**    
     자동 검색이 실패할 경우에만 필요합니다.

   - **일정 동기화**    
     일정 동기화 및 기타 Exchange Server 서비스를 사용할지 여부를 지정합니다. 예: 모임 동기화.

### <a name="intune-now-provides-the-account-move-operation-----1573558-1579830---"></a>이제 Intune이 계정 이동 작업을 제공함 <!-- 1573558, 1579830 -->
**계정 이동**은 ASU(Azure Scale Unit) 간에 테넌트를 마이그레이션합니다. **계정 이동**의 경우 이를 요청하기 위해 Intune 지원 팀에 전화를 거는 경우와 같이 고객이 시작하는 시나리오와 Microsoft가 백 엔드에서 서비스를 조정해야 하는 경우와 같이 Microsoft가 주도하는 시나리오에 둘 다 사용될 수 있습니다. **계정 이동** 중에 테넌트는 ROM(읽기 전용 모드)로 전환됩니다. ROM 기간에는 등록, 장치 이름 바꾸기, 준수 상태 업데이트와 같은 서비스 작업이 실패합니다.

### <a name="new-windows-defender-security-center-wdsc-device-configuration-profile-settings----1335507---"></a>새 WDSC(Windows Defender 보안 센터) 장치 구성 프로필 설정 <!-- 1335507 -->
Intune은 **Windows Defender 보안 센터**라는 끝점 보호가 적용되는 장치 구성 프로필 설정의 새 섹션을 추가합니다. IT 관리자는 최종 사용자가 액세스할 수 있는 Windows Defender 보안 센터 앱 영역을 구성할 수 있습니다. IT 관리자가 Windows Defender 보안 센터 앱 영역을 숨기면 숨겨진 영역에 관련된 모든 알림이 사용자 장치에 표시되지 않습니다.

관리자는 Windows Defender 보안 센터 장치 구성 프로필 설정에서 이러한 영역을 숨길 수 있습니다.
- 바이러스 및 위협 방지
- 장치 성능 및 상태
- 방화벽 및 네트워크 보호
- 앱 및 브라우저 제어
- 패밀리 옵션

IT 관리자는 사용자가 받는 알림을 사용자 지정할 수도 있습니다. 예를 들어, 사용자가 WDSC의 표시되는 영역에서 생성되는 모든 알림을 수신할지, 아니면 중요 알림만 수신할지 구성할 수 있습니다. 중요하지 않은 알림에는 스캔이 완료되었을 경우 생성되는 Windows Defender 바이러스 백신 작업 및 알림에 대한 주기적 요약이 포함됩니다. 다른 모든 알림은 중요 알림으로 간주합니다. 또한 알림 콘텐츠 자체를 사용자 지정할 수 있습니다. 예를 들어, 사용자의 장치에 표시되는 알림에 포함할 IT 담당자 정보를 제공할 수 있습니다.




<!-- the following are present prior to 1712 -->
### <a name="assign-office-365-mobile-apps-to-ios-and-android-devices-using-built-in-app-type----1332318---"></a>기본 제공 앱 유형을 사용하여 iOS 및 Android 장치에 Office 365 모바일 앱 할당<!-- 1332318 -->
**기본 제공** 앱 유형을 사용하면 사용자가 관리하는 iOS 및 Android 장치에 Office 365 앱을 손쉽게 만들고 할당할 수 있습니다. 이러한 앱에는 Word, Excel, PowerPoint 및 OneDrive와 같은 0365 앱이 포함됩니다. 특정 앱을 앱 유형에 할당하고, 앱 정보 구성을 편집할 수 있습니다.

### <a name="single-sign-on-support-for-ios----1333645---"></a>iOS을 위한 Single Sign-On 지원 <!-- 1333645 -->  
iOS 사용자를 위한 Single Sign-On을 사용할 수 있습니다. Single Sign On 페이로드에서 사용자 자격 증명을 검색하도록 코딩되는 iOS 앱은 이 페이로드 구성 업데이트로 작동합니다. 또한 UPN 및 Intune 장치 ID를 사용하여 사용자 이름 및 영역을 구성할 수 있습니다.

### <a name="ios-11-app-inventory-api-for-mobile-threat-detection----1391759---"></a>모바일 위협 요소 탐지를 위한 iOS 11 앱 인벤토리 API<!-- 1391759 -->
Intune은 개인 및 회사 소유 장치 모두에서 앱 인벤토리 정보를 수집하며 Lookout for Work와 같은 페치할 MTD(모바일 스레드 검색) 공급자에서 사용할 수 있도록 합니다. iOS 11+ 장치의 사용자로부터 앱 인벤토리를 수집할 수 있게 됩니다.

**앱 인벤토리**  
회사 소유의 iOS 11+ 및 개인적으로 소유한 장치 모두의 인벤토리가 사용자의 MTD 서비스 공급자에게 전송됩니다. 앱 인벤토리의 데이터에는 다음이 포함됩니다.

 - 앱 ID
 - 앱 버전
 - 앱 짧은 버전
 - 앱 이름
 - 앱 번들 크기
 - 앱 동적 크기
 - 앱의 유효성 검사 여부
 - 앱의 관리 여부

### <a name="audit-updates----1412961---"></a>감사 업데이트 <!-- 1412961 -->  
Intune 감사는 Intune과 관련된 변경 작업에 대한 레코드를 제공합니다.  모든 만들기, 업데이트, 삭제 및 원격 작업 조작은 캡처되고 1년 동안 보존됩니다.  Azure Portal은 각 워크로드에서 최근 30일 동안의 감사 데이터에 대한 뷰를 제공하며 필터링할 수 있습니다.  해당 Graph API를 사용하면 마지막 연도에 저장된 감사 데이터를 검색할 수 있습니다. 

감사는 **모니터** 그룹에서 찾을 수 있습니다. 각 워크로드에 **감사 로그** 메뉴 항목이 있습니다.   

### <a name="text-protocol-allowed-from-managed-apps----1414050----"></a>관리되는 앱에서 허용하는 텍스트 프로토콜 <!-- 1414050  -->
Intune 앱 SDK에 의해 관리되는 앱은 SMS 메시지를 보낼 수 있습니다.

### <a name="remotely-restart-ios-device-supervised-only----1424595---"></a>iOS 장치를 원격으로 다시 시작(감독 모드만 해당) <!-- 1424595 -->
장치 동작을 사용하여 다시 시작하도록 감독되는 iOS 10.3+ 장치를 트리거할 수 있습니다. 장치 다시 시작 동작 사용에 대한 자세한 내용은 [Intune으로 장치를 원격으로 다시 시작](device-restart.md)을 참조하세요.

> [!Note]  
> 이 명령은 감독되는 장치 및 **장치 잠금** 액세스 권한에 필요합니다. 장치를 즉시 다시 시작합니다. 암호로 잠긴 iOS 장치는 다시 시작한 후 Wi-Fi 네트워크에 다시 가입되지 않습니다. 다시 시작한 후 서버와 통신하지 못할 수도 있습니다.

### <a name="remotely-lock-managed-macos-device-with-intune----1437691---"></a>Intune을 사용하여 관리되는 macOS 장치 원격 잠금 <!-- 1437691 -->
손실된 macOS 장치를 잠그고 6자리 복구 PIN을 설정할 수 있습니다. 잠기면 **장치 개요** 블레이드에 다른 장치 작업이 전송될 때까지 PIN이 표시됩니다.

자세한 내용은 [Intune을 사용하여 관리되는 장치 원격 잠금](device-remote-lock.md)을 참조하세요.

### <a name="windows-defender-advanced-threat-protection-reporting-frequency-settings------1455974-----"></a>Windows Defender Advanced Threat Protection 보고 주기 설정 <!--- 1455974  --->
WDATP(Windows Defender Advanced Threat Protection) 서비스를 사용하면 관리자가 관리되는 장치에 대한 보고 주기를 관리할 수 있습니다. 새 **원격 보고 빈도 가속화** 옵션을 사용하면 WDATP는 더 자주 데이터를 수집하고 위험을 평가합니다. 보고에 대한 기본값은 속도 및 성능을 최적화합니다. 보고 빈도를 늘리는 것은 위험 수준이 높은 장치에 유용할 수 있습니다. 이 설정은 **장치 구성**의 **Windows Defender ATP** 프로필에서 확인할 수 있습니다.

### <a name="assignment-conflict-resolution-has-changed-for-ios-store-apps----1480316---"></a>iOS 스토어 앱에서 할당 충돌 해결책이 변경됨 <!-- 1480316 -->
최종 사용자는 iOS 스토어 앱의 가용성에 변경 사항이 있을 수 있습니다. 현재 **필수 및 사용 가능**과 **해당 없음**으로 충돌되는 두 그룹에 할당된 앱은 **필수 및 사용 가능**으로 확인됩니다. 변경되면 이러한 충돌이 발생하는 앱은 **해당 없음**으로 확인됩니다.

변경 내용은 한 앱이 서로 다른 앱 의도로 여러 그룹에 할당된 경우의 혼란을 해결합니다.

11월 서비스 릴리스 전에 정보 근로자 포털 및 회사 포털에서 사용할 수 있는 앱을 갖길 원하는 경우 다음과 같은 두 가지 옵션이 있습니다.

1. 그룹에 대한 **해당 없음** 할당을 제거합니다.
2. **필수 및 사용 가능** 의도가 할당된 멤버가 포함되지 않은 새 그룹을 만들고 해당 그룹을 **해당 없음**으로 할당합니다.

자세한 내용은 [Microsoft Intune을 사용하여 그룹에 앱을 할당하는 방법](apps-deploy.md)을 참조하세요.

> [!Note]
> 릴리스 후에는 Intune 클래식 콘솔에서 MDM(모바일 장치 관리) 앱 할당을 보거나 수정할 수 없습니다. 단, Azure 콘솔 또는 Intune Graph API를 사용하여 앱 할당을 만들 수 있습니다.

### <a name="manage-android-for-work-devices-independently-from-android-devices----1490731---"></a>Android 장치와는 독립적으로 Android for Work 장치 관리 <!-- 1490731 -->
Intune은 Android 플랫폼과는 독립적으로 Android for Work 장치의 등록 관리를 지원합니다. 이러한 설정은 **장치 등록** > **등록 제한** > **장치 유형 제한**에서 관리됩니다. (이전에는 **장치 등록** > **Android for Work 등록** > **Android for Work 등록 설정**에 있었음)

기본적으로 Android for Work 장치 설정은 Android 장치에 대한 설정과 동일합니다. 그러나 Android for Work 설정을 변경하면 달라집니다.
 
개인적인 Android for Work 등록을 차단하는 경우 회사 Android 장치만 Android for Work로 등록할 수 있습니다.

새 설정으로 작업할 때는 다음 사항을 고려합니다.

#### <a name="if-you-have-never-previously-onboarded-android-for-work-enrollment"></a>이전에 등록된 Android for Work 등록이 없는 경우
새 Android for Work 플랫폼이 기본 장치 유형 제한에서 차단됩니다. 기능을 등록한 후에 Android for Work로 등록하도록 장치를 허용할 수 있습니다. 이렇게 하려면 기본값을 변경하거나 기본 장치 유형 제한을 대체할 새 장치 유형 제한을 만듭니다.

#### <a name="if-you-have-onboarded-android-for-work-enrollment"></a>등록된 Android for Work 등록이 있는 경우
이전에 등록한 경우 상황은 사용자가 선택한 설정에 따라 다릅니다.

| 설정 | 기본 장치 유형 제한에서의 Android for Work 상태 | 참고 |
| --- | --- | --- |
| **모든 장치를 Android로 관리** | 차단됨 | 모든 Android 장치는 Android for Work 없이 등록해야 합니다. |
| **지원되는 장치를 Android for Work로 관리** | 허용됨 | Android for Work를 지원하는 모든 Android 장치는 Android for Work로 등록해야 합니다. |
| **이러한 그룹의 사용자만을 위해 지원되는 장치를 Android for Work로 관리** | 차단됨 | 기본값을 재정의하기 위해 별도 장치 유형 제한 정책이 만들어졌습니다. 이 정책은 Android for Work 등록을 허용하도록 이전에 선택한 그룹을 정의합니다. 선택된 그룹 내 사용자는 Android for Work 장치를 등록할 수 있도록 계속 허용됩니다. 다른 모든 사용자는 Android for Work 등록에 제한을 받습니다. |

모든 경우에 사용자의 의도한 규정이 유지됩니다. 사용자 환경에서 Android for Work의 전역 또는 그룹별 허용 한도를 유지하기 위한 별도의 작업은 필요하지 않습니다.

이러한 변경 내용은 11월 업데이트와 함께 출시되지만, 계정에서 실행하기까지는 시간이 걸릴 수 있습니다. 이러한 변경 내용이 사용자 계정에 적용될 때 Office 365 포털에서 확인 알림이 사용자에게 표시됩니다.

### <a name="support-for-multiple-network-device-enrollment-service-ndes-connectors----1528104---"></a>여러 NDES(네트워크 장치 등록 서비스) 커넥터에 대한 지원 <!-- 1528104 -->
NDES를 사용하면 도메인 자격 증명 없이 실행되는 모바일 장치에서 SCEP(단순 인증서 등록 프로토콜)를 기반으로 인증서를 가져올 수 있습니다. 이 업데이트를 통해 여러 NDES 커넥터가 지원됩니다.

### <a name="new-scep-profile-details-supported----1559808---"></a>지원되는 새 SCEP 프로필 세부 정보 <!-- 1559808 -->
관리자는 Windows, iOS, macOS 및 Android 플랫폼에서 SCEP 프로필을 만들 때 추가 설정을 지정할 수 있습니다.  관리자는 IMEI, 일련 번호 또는 주체 이름 형식의 전자 메일을 포함한 일반 이름을 설정할 수 있습니다.

### <a name="configure-an-ios-app-pin----1586774---"></a>iOS 앱 PIN 구성 <!-- 1586774 -->
곧 사용자는 대상 iOS 앱에 대한 PIN이 필요하게 됩니다. Azure Portal을 통해 며칠 내에 PIN 요구 사항 및 만료 날짜를 구성할 수 있습니다. 필요한 경우 사용자는 iOS 앱에 대한 액세스를 얻기 전에 새 PIN을 설정 및 사용해야 합니다. Intune 앱 SDK와 함께 앱 보호가 설정된 iOS 앱만 이 기능을 지원합니다.

### <a name="retain-data-during-a-factory-reset-----1588489---"></a>출하 시 설정으로 리셋하는 동안 데이터 유지 <!-- 1588489 -->
Windows 출하 시 설정으로 리셋에 대한 새로운 기능 지원을 추가하였습니다. 이제 관리자는 출하 시 설정으로 리셋하는 동안 장치에서 장치 등록 및 프로비전된 기타 데이터가 유지되는지 여부를 지정할 수 있습니다. 
 
다음 데이터는 출하 시 설정으로 리셋되는 동안 유지됩니다.
- 장치와 연결된 사용자 계정
- 컴퓨터 상태(도메인 가입, AADJ)
- MDM 등록
- OEM이 설치한 앱(저장소 및 Win32 앱)
- 사용자 프로필
- 사용자 프로필 외부의 사용자 데이터
- 사용자 자동 로그온
 
다음 데이터는 보존되지 않습니다.
- 사용자 파일
- 사용자가 설치한 앱(저장소 및 Win32 앱)
- 기본 설정 이외의 장치 설정 

### <a name="app-install-status-report-now-a-bar-chart----1249446---"></a>이제 앱 설치 상태를 가로 막대형 차트로 보고 <!-- 1249446 -->  
**모바일 앱** 워크로드의 **앱** 목록을 통해 각 앱에서 액세스할 수 있는 **앱 설치 상태** 보고서가 곧 가로 막대형 차트로 렌더링될 예정입니다.

### <a name="add-find-my-iphone-for-personal-devices---1427287--"></a>개인 장치를 위한 “내 iPhone 찾기” 추가 <!--1427287-->
iOS 장치가 활성화 잠금이 설정되어 있는지 여부를 확인할 수 있게 됩니다. 이전에 이 기능은 클래식 포털의 Intune에서 찾을 수 있었습니다.

### <a name="group-assigned-enrollment-restrictions----747598---"></a>그룹 할당 등록 제한 <!-- 747598 -->
Intune 관리자는 사용자 그룹에 대한 사용자 지정 장치 유형 및 장치 제한 등록 제한을 만들 수 있게 됩니다.
 
Intune Azure Portal에서 각 제한 유형의 인스턴스를 25개까지 만들 수 있으며 나중에 사용자 그룹에 할당할 수 있습니다. 그룹 할당 제한은 기본 제한을 재정의합니다.
 
제한 유형의 모든 인스턴스는 엄격하게 정렬된 목록으로 유지됩니다. 이 순서는 충돌 해결을 위한 우선 순위 값을 정의합니다. 둘 이상의 제한 인스턴스의 영향을 받는 사용자는 우선 순위가 가장 높은 값의 인스턴스에 의해서만 제한됩니다. 지정된 인스턴스의 우선 순위를 목록에서 다른 위치로 끌어서 변경할 수 있습니다. 
 
이 기능은 Android for Work 설정이 Android for Work 등록 메뉴에서 등록 제한 메뉴로 마이그레이션되면서 릴리스될 예정입니다. 이 마이그레이션은 며칠이 걸릴 수 있으므로 계정이 11월 릴리스의 다른 일부로 업그레이드된 후에 등록 제한에서 그룹 할당을 사용할 수 있습니다.

### <a name="windows-10-update-ring-assignments-are-displayed----1621837---"></a>Windows 10 업데이트 링 할당 표시됨 <!-- 1621837 -->
확인 중인 사용자에 대해 **문제 해결** 중인 경우 모든 Windows 10 업데이트 링 할당을 확인할 수 있게 됩니다.  



<!-- the following are present prior to 1711 -->

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Azure Active Directory 웹 사이트에는 Intune Managed Browser 앱이 필요하고 Managed Browser(공개 미리 보기)에 Single Sign-On을 지원할 수 있습니다.<!-- 710595 -->   
Azure AD(Azure Active Directory)를 사용하면 모바일 장치에서 웹 사이트에 대한 액세스를 Intune Managed Browser 앱으로 제한할 수 있습니다. Managed Browser에서 웹 사이트 데이터는 최종 사용자 개인 데이터와 별도로 안전하게 유지됩니다. 또한 Managed Browser는 Azure AD에서 보호하는 사이트에 Single Sign-On 기능을 지원합니다. Managed Browser에 로그인하거나 Intune에서 관리하는 다른 앱과 함께 장치에서 Managed Browser를 사용하면 사용자에게 자격 증명을 입력하지 않고도 Azure AD에서 보호되는 회사 사이트에 액세스할 수 있습니다. 이 기능은 OWA(Outlook Web Access) 및 SharePoint Online과 같은 사이트뿐만 아니라 Azure 앱 프록시를 통해 액세스되는 인트라넷 리소스와 같은 다른 회사 사이트에도 적용됩니다.

### <a name="troubleshoot-enrollment-issues------746324----"></a>등록 문제 해결<!--- 746324 --->  
문제 해결 작업 영역에서는 사용자 등록 문제를 표시합니다. 문제 및 제안된 수정 단계에 대한 세부 정보를 통해 관리자 및 도움말 지원 센터 운영자가 문제를 해결할 수 있습니다. 특정 등록 문제는 캡처되지 않고 일부 오류에는 수정 제안이 없을 수 있습니다.


















<!-- the following are present prior to 1710 -->



### <a name="support-for-windows-10-edition-upgrade-policy------903672archived-1119689---"></a>Windows 10 버전 업그레이드 정책에 대한 지원  <!-- 903672(archived), 1119689 -->  
Windows 10 장치를 Windows 10 Education, Windows 10 Education N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional Education 및 Windows 10 Professional Education N으로 업그레이드하는 Windows 10 버전 업그레이드 정책을 만들 수 있습니다. Windows 10 버전 업그레이드에 대한 자세한 내용은 [Windows 10 버전 업그레이드 구성 방법](edition-upgrade-configure-windows-10.md)을 참조하세요.




<!-- the following are present prior to 1709 -->



### <a name="android-for-work-support-for-lookout----1087312---"></a>Android for Work의 Lookout 지원 <!-- 1087312 -->   
Lookout for Work 앱 사용 시 Lookout이 설치된 Intune 커넥터가Android for Work 장치를 지원할 예정입니다. 그러면 컨테이너 내부 또는 외부에서 Lookout 앱을 배포할 수 있습니다.

### <a name="intune-app-protection-and-citrix-mdx-development-tools----709185---"></a>Intune 앱 보호 및 Citrix MDX 개발 도구<!-- 709185 -->
Citrix XenMobile MDX와 Microsoft Intune의 조합으로 장치와 앱을 관리할 수 있습니다. 이 옵션을 사용하면 Citrix의 mVPN 기술을 사용하면서 Intune 앱 보호 정책으로 앱을 관리할 수 있습니다.

Intune 앱 래핑 도구와 iOS 및 Android용 Intune 앱 SDK를 포함하는 코드 리포지토리를 찾아 Citrix MDX mVPN 기술과 통합할 수 있습니다.


### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>온-프레미스 Exchange Connector 고가용성 지원 <!-- 676614 -->   
온-프레미스 Exchange Connector에 대해 여러 CAS(클라이언트 액세스 서버) 역할을 사용할 수 있습니다. 예를 들어 주 CA에서 오류가 발생할 경우 Exchange Connector는 다른 CAS로 대체하기 위한 쿼리를 수신합니다. 이 기능은 서비스가 중단되지 않도록 합니다.

### <a name="system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>Exchange Connector용 System Center Operations Manager 관리 팩 <!-- 885457 -->   
Exchange Connector 로그를 구문 분석하는 데 도움이 되도록 Exchange Connector용 System Center Operations Manager 관리 팩이 제공될 예정입니다. 이 관리 팩을 사용하면 문제를 해결해야 할 때 Intune을 다른 방식으로 모니터링할 수 있습니다.





## <a name="intune-apps"></a>Intune 앱

### <a name="helping-your-users-help-themselves-with-the-company-portal-app-for-android----1573324-1573150-1558616-1564878---"></a>Android용 회사 포털 앱을 사용하는 사용자가 스스로 해결책을 찾도록 도움 <!---1573324, 1573150, 1558616, 1564878--->
사용자의 이해를 돕고 가능한 경우 새로운 사용 사례에서 자체적으로 해결할 수 있도록 최종 사용자를 위한 지침이 Android용 회사 포털 앱에 추가되었습니다. 

- [Google의 권장 지침]에 따라 암호화에 대한 준수 정책이 배포되었으나, [장치 제조업체는 장치를 암호화하지 않는다](/intune-user-help/your-device-appears-encrypted-but-cp-says-otherwise-android)는 내용을 설명하는 새 메시지가 표시됩니다.(https://developer.android.com/reference/android/app/admin/DevicePolicyManager.html#setStorageEncryption(android.content.ComponentName, boolean).
- 최종 사용자는 추가가 허용된 최대 장치 수에 도달한 경우 장치를 제거하도록 (Azure Active Directory 포털)[https://account.activedirectory.windowsazure.com/r/#/profile]로 안내됩니다. 
- 최종 사용자에게는 [Samsung KNOX 장치에서 활성화 오류를 수정](https://go.microsoft.com/fwlink/?linkid=859718)하는 데 유용한 단계 또는 [절전 모드 끄기](/intune-user-help/power-saving-mode-android)에 대한 단계가 제공됩니다. 그러한 해결책이 문제를 해결하지 못하는 경우 [Microsoft에 로그를 제출](/intune-user-help/send-logs-to-microsoft-ios)하는 방법에 대한 설명이 제공됩니다. 


### <a name="new-resolve-action-available-for-android-devices----1583480---"></a>Android 장치에서 사용할 수 있는 새로운 ‘해결’ 작업 <!---1583480--->
Android용 회사 포털 앱은 _장치 설정 업데이트_ 페이지에서 ‘해결’ 작업을 소개하고 있습니다. 이 옵션을 선택하면 최종 사용자는 장치의 비호환 상태를 유발하는 설정으로 바로 이동할 수 있습니다. Android용 회사 포털 앱은 현재 이 작업을 [장치 암호](/intune-user-help/set-your-pin-or-password-android), [장치 암호화](/intune-user-help/encrypt-your-device-android), [USB 디버깅](/intune-user-help/you-need-to-turn-off-usb-debugging-android) 및 [알 수 없는 소스](/intune-user-help/you-need-to-turn-off-unknown-sources-android) 설정에 지원합니다. 




<!-- the following are present prior to 1711 -->


### <a name="redirecting-macos-users-to-our-new-company-portal-app---1380728--"></a>새 회사 포털 앱에 macOS 사용자 리디렉션<!--1380728-->   
최종 사용자가 macOS 장치를 등록하기 위해 회사 포털 웹 사이트에 로그인하는 경우 프로세스를 완료하기 위해 macOS용 새 회사 포털 앱을 다운로드하도록 리디렉션됩니다. 이는 macOS 장치에서 OS X El Capitan 10.11 이상을 사용하는 경우에 발생합니다. 


<!-- the following are present prior to 1710 -->



### <a name="apps-that-are-available-with-or-without-enrollment-can-now-be-installed-without-being-prompted-for-enrollment----1334712---"></a>등록을 하거나 등록을 하지 않고 사용할 수 있는 앱이 이제 등록을 묻는 메시지가 표시되지 않고 설치될 수 있습니다. <!-- 1334712 -->
Android 회사 포털 앱에서 등록을 하거나 등록을 하지 않고 사용할 수 있는 회사 앱이 등록을 묻는 메시지가 표시되지 않고 설치될 수 있습니다.


<!-- the following are present prior to 1709 -->

### <a name="intune-managed-browser-support-for-ios-and-android----1374196---"></a>iOS 및 Android를 위한 Intune Managed Browser 지원 <!-- 1374196 -->
2017년 10월을 기준으로 Android 앱에서 Intune Managed Browser 앱은 Android 4.4 이상을 실행하는 장치만 지원합니다. iOS의 Intune Managed Browser 앱은 iOS 9.0 이상을 실행하는 장치만 지원합니다. Android 및 iOS 이전 버전에서도 계속 Managed Browser를 사용할 수는 있지만 새로운 버전의 앱을 설치할 수 없고 모든 기능을 액세스하지 못할 수 있습니다. 이러한 장치를 지원되는 운영 체제 버전으로 업데이트하는 것이 좋습니다.


### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>사용자가 등록이 허용된 최대 장치 수에 도달하면 표시되는 향상된 오류 메시지 <!-- 1270370 -->
일반 오류 메시지 대신 최종 사용자에게 “IT 관리자가 허용한 최대 장치 수를 등록했습니다. 등록된 장치를 제거하거나 IT 관리자에게 도움을 요청하십시오.”라는 친숙하고 조치를 수행할 수 있는 오류 메시지가 표시됩니다.




## <a name="notices"></a>알림

이번에는 활성 알림이 없습니다.




### <a name="see-also"></a>참고 항목
최근 개발 작업에 대한 자세한 내용은 [Microsoft Intune의 새로운 기능](whats-new.md)을 참조하세요.
