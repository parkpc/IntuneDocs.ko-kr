---
title: "초기 버전"
description: 
keywords: 
author: ErikjeMS
ms.author: erikje
manager: angrobe
ms.date: 01/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ac9cb0ad7d1b5e2c29e80f16c172f41c08d3a15d
ms.sourcegitcommit: 5fd17a57989c6da3d325ed2e0018ce16fe20bb79
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/04/2018
---
# <a name="the-early-edition-for-microsoft-intune---january-2018"></a>Microsoft Intune 초기 버전 - 2018년 1월

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

### <a name="easier-resolution-of-compliance-issues-for-the-company-portal-app-for-windows-10---676546---"></a>Windows 10용 회사 포털 앱의 준수 문제 해결 용이 <!--676546 -->

Windows 장치를 사용하는 최종 사용자는 회사 포털 앱에서 비준수 이유를 탭할 수 있습니다. 가능하면 문제를 해결하기 위해 설정 앱의 올바른 위치로 직접 이동시킵니다. 

### <a name="new-option-for-user-authentication-for-apple-bulk-enrollment----747625---"></a>Apple 대량 등록을 위한 새로운 사용자 인증 옵션 <!-- 747625 -->
Intune은 다음 등록 방법에 대해 회사 포털 앱을 사용하여 장치를 인증하는 옵션을 제공합니다.

- Apple 장비 등록 프로그램
- Apple School Manager
- Apple Configurator 등록

회사 포털 옵션을 사용하면 이러한 등록 방법을 차단하지 않고 Azure Active Directory 다단계 인증을 적용할 수 있습니다.

회사 포털 옵션을 사용할 경우 Intune은 사용자 선호도 등록을 위한 iOS 설정 도우미의 사용자 인증을 건너뜁니다. 따라서 처음에는 장치가 사용자 없는 장치로 등록되므로 사용자 그룹의 구성 또는 정책을 받지 않습니다. 장치 그룹의 구성과 정책만 받습니다. 그러나 Intune이 장치에 회사 포털 앱을 자동으로 설치합니다. 회사 포털 앱을 시작하고 로그인하는 첫 번째 사용자가 Intune에서 해당 장치와 연결됩니다. 사용자는 이때 사용자 그룹의 구성과 정책을 받습니다. 사용자 연결을 변경하려면 다시 등록해야 합니다.

### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685---"></a>여러 Apple DEP/Apple School Manager 계정에 대한 Intune 지원 <!-- 747685 -->
Intune은 최대 100개의 다른 Apple DEP(장비 등록 프로그램) 또는 Apple School Manager 계정의 장치 등록을 지원합니다. 업로드된 각 토큰을 등록 프로필과 장치에 대해 별도로 관리할 수 있습니다. 업로드된 DEP/School Manager 토큰마다 다른 등록 프로필을 자동으로 할당할 수 있습니다. School Manager 토큰이 여러 개 업로드된 경우 한 번에 하나의 토큰만 Microsoft School Data Sync와 공유할 수 있습니다.

Graph를 통해 Apple DEP 또는 ASM을 관리하기 위한 베타 Graph API 및 게시된 스크립트는 마이그레이션 후 더 이상 작동하지 않습니다. 새 베타 Graph API가 개발 중이며 마이그레이션 후 릴리스될 예정입니다.

### <a name="select-device-categories-by-using-the-access-work-or-school-settings----1058963-eeready---"></a>회사 또는 학교 액세스 설정을 사용하여 장치 범주 선택 <!-- 1058963 eeready --> 
[장치 그룹 매핑](https://docs.microsoft.com/en-us/intune/device-group-mapping)을 사용하도록 설정한 경우, Windows 10의 사용자에게 **설정** > **계정** > **회사 또는 학교 액세스**의 **연결** 단추를 통해 등록한 후 또는 첫 실행 경험 중에 장치 범주를 선택하라는 메시지가 표시됩니다.

### <a name="targeting-compliance-policies-to-devices-in-device-groups---1307012---"></a>장치 그룹의 장치를 준수 정책의 대상으로 지정 <!--1307012 -->

사용자 그룹의 사용자를 준수 정책의 대상으로 지정할 수 있습니다. 장치 그룹의 장치를 준수 정책의 대상으로 지정할 수 있습니다. 

### <a name="including-and-excluding-app-assignment-based-on-groups----1406920---"></a>그룹에 따라 앱 할당 포함 및 제외 <!-- 1406920 -->

앱 할당 중이나 할당 유형을 선택한 후 포함할 그룹과 제외할 그룹을 선택할 수 있습니다. 미리 생성된 그룹(모든 사용자, 모든 장치, 모든 사용자+장치)을 포함된 그룹으로 사용할 수도 있습니다.

### <a name="remote-erase-command-support----1438084---"></a>원격 "지우기" 명령 지원 <!-- 1438084 -->

관리자는 지우기 명령을 원격으로 실행할 수 있습니다.

> [!IMPORTANT]
> 지우기 명령은 취소할 수 없으며 주의해서 사용해야 합니다.

지우기 명령은 장치에서 운영 체제를 비롯한 모든 데이터를 제거합니다. 또한 Intune 관리에서 장치를 제거합니다. 사용자에게 경고가 표시되지 않으며, 명령을 실행하는 즉시 지우기가 수행됩니다.

6자리 복구 PIN을 구성할 수 있습니다. 이 PIN을 사용하여 지워진 장치의 잠금을 해제할 수 있으며, 이때 운영 체제의 재설치가 시작됩니다. 지우기가 시작된 후에는 Intune의 장치 개요 블레이드에 있는 상태 표시줄에 PIN이 표시됩니다. 지우기가 진행되는 동안 PIN이 계속 유지됩니다. 지우기가 완료되면 장치가 Intune 관리에서 완전히 사라집니다. 장치를 복원하는 누구든지 사용할 수 있도록 복구 PIN을 기록해야 합니다.

### <a name="windows-information-protection-wip-encrypted-data-in-windows-search-results----1469193---"></a>Windows 검색 결과의 WIP(Windows Information Protection) 암호화된 데이터 <!-- 1469193 -->

WIP(Windows Information Protection) 정책의 새 설정을 사용하면 WIP 암호화된 데이터를 Windows 검색 결과에 포함할지 여부를 제어할 수 있습니다.

### <a name="website-learning-mode----1631908---"></a>웹 사이트 학습 모드 <!-- 1631908 -->

Intune에서 WIP(Windows Information Protection) 학습 모드 확장을 도입할 예정입니다. WIP 지원 앱에 대한 정보뿐 아니라 웹 사이트와 작업 데이터를 공유한 장치 요약도 볼 수 있습니다. 이 정보를 사용하여 그룹 및 사용자 WIP 정책에 추가할 웹 사이트를 확인할 수 있습니다.

### <a name="updates-to-compliance-emails---1637547---"></a>준수 메일 업데이트 <!--1637547 -->

비준수 장치를 보고하기 위해 메일을 보낼 때 비준수 장치에 대한 세부 정보가 포함됩니다. [비준수에 대한 작업 자동화](#actions-for-noncompliance) 문서가 이 사실을 표시하기 위해 업데이트될 예정입니다.

### <a name="conditional-access-policies-for-intune-is-only-available-from-the-azure-portal-----1737088-1634311---"></a>Intune에 대한 조건부 액세스 정책은 Azure Portal에서만 사용할 수 있음 <!-- 1737088 1634311 --> 
조건부 액세스를 구성하고 관리하는 위치를 간소화할 예정입니다. [Azure Portal](https://portal.azure.com)의 **Azure Active Directory** > **조건부 액세스**에서 정책을 구성하고 관리합니다. 편의상, **Intune** > **조건부 액세스**를 통해 Azure Portal의 Intune에서 이 블레이드에 액세스할 수도 있습니다.

###  <a name="alerts-for-expired-tokens-and-tokens-that-will-soon-expire----1639263---"></a>만료된 토큰 및 곧 만료되는 토큰에 대한 경고 <!-- 1639263 -->
개요 페이지에는 만료된 토큰과 곧 만료되는 토큰에 대한 경고가 표시됩니다. 단일 토큰에 대한 경고를 클릭하면 토큰의 세부 정보 페이지로 이동합니다.  여러 토큰이 포함된 경고를 클릭하면 해당 상태의 모든 토큰 목록으로 이동합니다. 관리자는 만료 날짜 전에 해당 토큰을 갱신해야 합니다.

### <a name="remote-printing-over-a-secure-network----1709994----"></a>보안 네트워크를 통한 원격 인쇄 <!-- 1709994  -->
PrinterOn의 무선 모바일 인쇄 솔루션을 사용하면 사용자가 보안 네트워크를 통해 언제 어디서나 원격으로 인쇄할 수 있습니다. PrinterOn은 iOS 및 Android용 Intune 앱 SDK와 둘 다 통합됩니다. 관리 콘솔의 Intune **앱 보호 정책** 블레이드를 통해 이 앱을 앱 보호 정책의 대상으로 지정할 수 있습니다. 최종 사용자는 Intune 에코시스템에서 사용하기 위해 Play 스토어 또는 iTunes를 통해 'PrinterOn for Microsoft' 앱을 다운로드할 수 있습니다.

### <a name="approve-the-company-portal-app-for-android-for-work---1797090---"></a>Android for Work용 회사 포털 앱 승인 <!--1797090 -->
조직에서 Android for Work를 사용하는 경우 관리되는 Google Play 스토어에서 자동 업데이트를 계속 받으려면 Android용 회사 포털 앱을 수동으로 승인해야 합니다.

### <a name="microsoft-graph-api-for-intune---general-availability-----1833289---"></a>Intune용 Microsoft Graph API - 일반 공급 <!-- 1833289 -->
Microsoft Graph의 Intune API를 사용하면 Intune 서비스의 관리 작업을 자동화하기 위한 데이터와 메서드를 프로그래밍 방식으로 액세스할 수 있습니다.  이러한 API가 **일반 공급**되므로 고객, 파트너 및 개발자는 이 API를 활용하여 Intune 또는 Microsoft Graph를 통해 사용할 수 있는 기타 Microsoft 서비스가 필요하거나 관련이 있는 사내 또는 상용 솔루션과 통합할 수 있습니다. 

<!-- the following are present prior to 1801 -->

### <a name="app-protection-policies-----679615---"></a>앱 보호 정책 <!-- 679615 -->
Intune 앱 보호 정책은 전체 테넌트의 모든 사용자에 대해 보호를 빠르게 사용할 수 있도록 전역 기본 정책을 만드는 기능을 제공합니다.

### <a name="revoking-ios-volume-purchase-program-apps-----820863---"></a>iOS Volume-Purchase Program 앱 철회 <!-- 820863 -->
하나 이상의 iOS VPP(Volume-Purchase Program) 앱이 설치된 지정된 장치의 경우 장치의 관련 장치 기반 앱 라이선스를 철회할 수 있습니다. 앱 라이선스를 철회해도 장치에서 관련 VPP 앱이 제거되지 않습니다. VPP 앱을 제거하려면 할당 작업을 **제거**로 변경해야 합니다. 자세한 내용은 [Microsoft Intune을 사용하여 대량 구매 프로그램을 통해 구매한 iOS 앱을 관리하는 방법](vpp-apps-ios.md)을 참조하세요.

### <a name="revoke-licenses-for-an-ios-volume-purchasing-program-token----820870---"></a>iOS Volume Purchasing Program 토큰에 대한 라이선스 철회 <!-- 820870 -->
지정된 VPP 토큰에 대한 모든 iOS VPP(Volume-Purchase Program) 앱의 라이선스를 철회할 수 있습니다.

### <a name="network-access-control-nac-device-check-in-reporting-----1232250---"></a>NAC(네트워크 액세스 제어) 장치 체크 인 보고 <!-- 1232250 -->
이 변경을 수행하기 전에 IT 관리자는 Intune 쪽에서 NAC 관리 장치가 NAC 솔루션과 통신하는지 여부를 확인할 수 없습니다. NAC 관리 장치가 NAC 솔루션과 통신하지 않는 경우 장치는 NAC 솔루션에서 비준수로 간주하므로 NAC 솔루션 자체에서 차단되고 나중에 장치 준수 상태에 기반을 둔 조건부 액세스 정책에 의해 차단됩니다.

이 변경을 수행하면 IT 관리자는 어떤 NAC 장치가 NAC 솔루션과 성공적으로 통신하는지 확인할 수 있습니다. 이 새로운 기능은 Intune 내의 장치 준수 워크로드에 있는 두 개의 새 모니터링 기능으로 구성되며 통계는 아래와 같이 표시됩니다.
- **지난 1시간의 평균 NAC 호출**
- **마지막 NAC 들어오는 요청(날짜/시간)**

### <a name="new-ios-device-action------1244701---"></a>새로운 iOS 장치 작업 <!-- 1244701 -->
iOS 10.3 감독된 장치를 종료할 수 있습니다. 이 작업을 수행하면 최종 사용자에게 경고하지 않고 장치가 즉시 종료됩니다. **장치** 워크로드에서 장치를 선택하면 장치 속성에서 **시스템 종료(감독 모드인 경우에만)** 작업을 찾을 수 있습니다.


### <a name="intune-now-provides-the-account-move-operation-----1573558-1579830---"></a>이제 Intune이 계정 이동 작업을 제공함 <!-- 1573558, 1579830 -->
**계정 이동**은 ASU(Azure Scale Unit) 간에 테넌트를 마이그레이션합니다. **계정 이동**의 경우 이를 요청하기 위해 Intune 지원 팀에 전화를 거는 경우와 같이 고객이 시작하는 시나리오와 Microsoft가 백 엔드에서 서비스를 조정해야 하는 경우와 같이 Microsoft가 주도하는 시나리오에 둘 다 사용될 수 있습니다. **계정 이동** 중에 테넌트는 ROM(읽기 전용 모드)로 전환됩니다. ROM 기간에는 등록, 장치 이름 바꾸기, 준수 상태 업데이트와 같은 서비스 작업이 실패합니다.




<!-- the following are present prior to 1712 -->
### <a name="assign-office-365-mobile-apps-to-ios-and-android-devices-using-built-in-app-type----1332318---"></a>기본 제공 앱 유형을 사용하여 iOS 및 Android 장치에 Office 365 모바일 앱 할당<!-- 1332318 -->
**기본 제공** 앱 유형을 사용하면 사용자가 관리하는 iOS 및 Android 장치에 Office 365 앱을 손쉽게 만들고 할당할 수 있습니다. 이러한 앱에는 Word, Excel, PowerPoint 및 OneDrive와 같은 0365 앱이 포함됩니다. 특정 앱을 앱 유형에 할당하고, 앱 정보 구성을 편집할 수 있습니다.


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

| Setting | 기본 장치 유형 제한에서의 Android for Work 상태 | 참고 |
| --- | --- | --- |
| **모든 장치를 Android로 관리** | 차단됨 | 모든 Android 장치는 Android for Work 없이 등록해야 합니다. |
| **지원되는 장치를 Android for Work로 관리** | 허용됨 | Android for Work를 지원하는 모든 Android 장치는 Android for Work로 등록해야 합니다. |
| **이러한 그룹의 사용자만을 위해 지원되는 장치를 Android for Work로 관리** | 차단됨 | 기본값을 재정의하기 위해 별도 장치 유형 제한 정책이 만들어졌습니다. 이 정책은 Android for Work 등록을 허용하도록 이전에 선택한 그룹을 정의합니다. 선택된 그룹 내 사용자는 Android for Work 장치를 등록할 수 있도록 계속 허용됩니다. 다른 모든 사용자는 Android for Work 등록에 제한을 받습니다. |

모든 경우에 사용자의 의도한 규정이 유지됩니다. 사용자 환경에서 Android for Work의 전역 또는 그룹별 허용 한도를 유지하기 위한 별도의 작업은 필요하지 않습니다.

이러한 변경 내용은 11월 업데이트와 함께 출시되지만, 계정에서 실행하기까지는 시간이 걸릴 수 있습니다. 이러한 변경 내용이 사용자 계정에 적용될 때 Office 365 포털에서 확인 알림이 사용자에게 표시됩니다.


### <a name="configure-an-ios-app-pin----1586774---"></a>iOS 앱 PIN 구성 <!-- 1586774 -->
곧 사용자는 대상 iOS 앱에 대한 PIN이 필요하게 됩니다. Azure Portal을 통해 며칠 내에 PIN 요구 사항 및 만료 날짜를 구성할 수 있습니다. 필요한 경우 사용자는 iOS 앱에 대한 액세스를 얻기 전에 새 PIN을 설정 및 사용해야 합니다. Intune 앱 SDK와 함께 앱 보호가 설정된 iOS 앱만 이 기능을 지원합니다.


<!-- the following are present prior to 1711 -->

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Azure Active Directory 웹 사이트에는 Intune Managed Browser 앱이 필요하고 Managed Browser(공개 미리 보기)에 Single Sign-On을 지원할 수 있습니다.<!-- 710595 -->   
Azure AD(Azure Active Directory)를 사용하면 모바일 장치에서 웹 사이트에 대한 액세스를 Intune Managed Browser 앱으로 제한할 수 있습니다. Managed Browser에서 웹 사이트 데이터는 최종 사용자 개인 데이터와 별도로 안전하게 유지됩니다. 또한 Managed Browser는 Azure AD에서 보호하는 사이트에 Single Sign-On 기능을 지원합니다. Managed Browser에 로그인하거나 Intune에서 관리하는 다른 앱과 함께 장치에서 Managed Browser를 사용하면 사용자에게 자격 증명을 입력하지 않고도 Azure AD에서 보호되는 회사 사이트에 액세스할 수 있습니다. 이 기능은 OWA(Outlook Web Access) 및 SharePoint Online과 같은 사이트뿐만 아니라 Azure 앱 프록시를 통해 액세스되는 인트라넷 리소스와 같은 다른 회사 사이트에도 적용됩니다.


<!-- the following are present prior to 1710 -->



### <a name="support-for-windows-10-edition-upgrade-policy------903672archived-1119689---"></a>Windows 10 버전 업그레이드 정책에 대한 지원  <!-- 903672(archived), 1119689 -->  
Windows 10 장치를 Windows 10 Education, Windows 10 Education N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional Education 및 Windows 10 Professional Education N으로 업그레이드하는 Windows 10 버전 업그레이드 정책을 만들 수 있습니다. Windows 10 버전 업그레이드에 대한 자세한 내용은 [Windows 10 버전 업그레이드 구성 방법](edition-upgrade-configure-windows-10.md)을 참조하세요.




<!-- the following are present prior to 1709 -->



### <a name="android-for-work-support-for-lookout----1087312---"></a>Android for Work의 Lookout 지원 <!-- 1087312 -->   
Lookout for Work 앱 사용 시 Lookout이 설치된 Intune 커넥터가Android for Work 장치를 지원할 예정입니다. 그러면 컨테이너 내부 또는 외부에서 Lookout 앱을 배포할 수 있습니다.

### <a name="intune-app-protection-and-citrix-mdx-development-tools----709185---"></a>Intune 앱 보호 및 Citrix MDX 개발 도구<!-- 709185 -->
Citrix XenMobile MDX와 Microsoft Intune의 조합으로 장치와 앱을 관리할 수 있습니다. 이 옵션을 사용하면 Citrix의 mVPN 기술을 사용하면서 Intune 앱 보호 정책으로 앱을 관리할 수 있습니다.

Intune 앱 래핑 도구와 iOS 및 Android용 Intune 앱 SDK를 포함하는 코드 리포지토리를 찾아 Citrix MDX mVPN 기술과 통합할 수 있습니다.




<!-- the following are present prior to 1711 -->


### <a name="redirecting-macos-users-to-our-new-company-portal-app---1380728--"></a>새 회사 포털 앱에 macOS 사용자 리디렉션<!--1380728-->   
최종 사용자가 macOS 장치를 등록하기 위해 회사 포털 웹 사이트에 로그인하는 경우 프로세스를 완료하기 위해 macOS용 새 회사 포털 앱을 다운로드하도록 리디렉션됩니다. 이는 macOS 장치에서 OS X El Capitan 10.11 이상을 사용하는 경우에 발생합니다. 



<!-- the following are present prior to 1709 -->

### <a name="intune-managed-browser-support-for-ios-and-android----1374196---"></a>iOS 및 Android를 위한 Intune Managed Browser 지원 <!-- 1374196 -->
2017년 10월을 기준으로 Android 앱에서 Intune Managed Browser 앱은 Android 4.4 이상을 실행하는 장치만 지원합니다. iOS의 Intune Managed Browser 앱은 iOS 9.0 이상을 실행하는 장치만 지원합니다. Android 및 iOS 이전 버전에서도 계속 Managed Browser를 사용할 수는 있지만 새로운 버전의 앱을 설치할 수 없고 모든 기능을 액세스하지 못할 수 있습니다. 이러한 장치를 지원되는 운영 체제 버전으로 업데이트하는 것이 좋습니다.


### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>사용자가 등록이 허용된 최대 장치 수에 도달하면 표시되는 향상된 오류 메시지 <!-- 1270370 -->
일반적인 오류 메시지 대신 Android 장치를 사용하는 최종 사용자에게 “IT 관리자가 허용한 최대 장치 수를 등록했습니다. 등록된 장치를 제거하거나 IT 관리자에게 도움을 요청하세요.”라는 친숙하고 조치를 수행할 수 있는 오류 메시지가 표시됩니다.




## <a name="notices"></a>알림

이번에는 활성 알림이 없습니다.




### <a name="see-also"></a>참고 항목
최근 개발 작업에 대한 자세한 내용은 [Microsoft Intune의 새로운 기능](whats-new.md)을 참조하세요.
