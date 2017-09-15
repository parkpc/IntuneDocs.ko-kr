---
title: "초기 버전"
description: 
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 09/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 31c3d3750aadbe8d302713f081f01f7c51d8ce96
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/09/2017
---
# <a name="the-early-edition-for-microsoft-intune---september-2017"></a>Microsoft Intune 초기 버전 - 2017년 9월

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


### <a name="google-play-protect-support-on-android----908720----"></a>Android에서 Google Play 보호 지원 <!-- 908720  -->  
Android Oreo가 출시되면서 Google은 사용자와 조직이 보안 앱과 보안 Android 이미지를 실행할 수 있는 Google Play 보호라는 보안 기능 제품군을 소개합니다. Intune은 SafetyNet 원격 증명을 비롯하여 Google Play 보호 기능을 지원합니다.  관리자는 Google Play 보호를 구성하고 정상 상태를 유지하는 데 필요한 준수 정책 요구 사항을 설정할 수 있습니다. **SafetyNet 장치 증명** 설정은 장치가 정상 상태이고 손상되지 않았음을 확인하기 위해 장치를 Google 서비스에 연결하도록 합니다. 또한 관리자는 Google Play 서비스에서 설치된 앱을 확인하도록 하기 위해 Android for Work에 대한 구성 프로필 설정을 설정할 수 있습니다.  장치가 Google Play 보호 요구 사항을 준수하지 않는 경우 조건부 액세스는 사용자가 회사 리소스에 액세스하는 것을 차단합니다. 

### <a name="prevent-users-of-android-devices-from-changing-their-device-date-and-time-----1333292---"></a>Android 장치 사용자가 장치 날짜 및 시간을 변경하지 못하도록 함 <!-- 1333292 -->
[Android 사용자 지정 장치 정책](custom-settings-android.md)을 사용하여 Android 장치 사용자가 장치 날짜 및 시간을 변경하지 못하도록 할 수 있습니다.
그렇게 하려면 URI ./Vendor/MSFT/PolicyManager/My/System/AllowDateTimeChange를**TRUE**로 설정하여 Android 사용자 지정 정책을 구성한 다음 필요한 그룹에 할당합니다.

### <a name="view-app-protection-policy-assignments-for-troubleshooting-----1475003---"></a>문제 해결을 위해 앱 보호 정책 할당 보기 <!--  1475003 -->
이 예정된 릴리스에서는 **앱 보호 정책** 옵션이 문제 해결 블레이드에서 사용할 수 있는 **할당** 드롭다운 목록에 추가됩니다. 이제 앱 보호 정책을 선택하여 선택한 사용자에게 할당된 앱 보호 정책을 확인할 수 있습니다.

### <a name="create-ios-apps-limited-to-specific-regional-apple-app-stores----1281692---"></a>특정 지역 Apple 앱 스토어로 제한된 iOS 앱 만들기 <!-- 1281692 -->
Apple 앱 스토어 관리되는 앱을 만드는 동안 국가 로캘을 지정할 수 있습니다.

> [!NOTE]  
> 현재는 미국 국가 스토어에 있는 Apple 앱 스토어 관리되는 앱만 만들 수 있습니다.

### <a name="select-apple-country-store-to-sync-vpp-apps-----1332311---"></a>Apple 국가 스토어를 선택하여 VPP 앱 동기화  <!-- 1332311 -->  
VPP 토큰을 업로드할 때 VPP(Volume Purchase Program) 국가 스토어를 구성할 수 있습니다. Intune은 지정된 VPP 국가 스토어의 모든 로캘에 대해 VPP 앱을 동기화합니다.

> [!NOTE]  
> 현재 Intune은 Intune 테넌트가 생성된 Intune 로캘과 일치하는 VPP 국가 스토어의 VPP 앱만 동기화합니다.

###  <a name="update-ios-vpp-user-and-device-licensed-apps-----1305564---"></a>iOS VPP 사용자 및 장치 사용이 허가된 앱 업데이트  <!-- 1305564 -->  
iOS VPP 토큰을 구성하여 Intune 서비스를 통해 해당 토큰에 대해 구입한 모든 앱을 업데이트할 수 있습니다. Intune은 앱 스토어 내의 VPP 앱 업데이트를 검색하고 장치가 체크 인하면 자동으로 장치에 푸시합니다.

### <a name="ios-11-support----1428975---"></a>iOS 11 지원 <!-- 1428975 -->
Apple에서 릴리스 시 Intune은 iOS 11을 지원합니다.

### <a name="new-settings-for-windows-10-team-device-restriction-profile------1308838----"></a>Windows 10 Team 장치 제한 프로필에 대한 새로운 설정 <!--- 1308838  -->
이번 릴리스에서 Microsoft는 Surface Hub 장치를 제어할 수 있도록 Windows 10 Team 장치 제한 프로필에 많은 새로운 설정을 추가합니다.
이 프로필에 대한 자세한 내용은 [Windows 10 Team 장치 제한 설정](device-restrictions-windows-10-teams.md)을 참조하세요.

### <a name="support-for-windows-10-edition-upgrade-policy------903672-1119689---"></a>Windows 10 버전 업그레이드 정책에 대한 지원  <!-- 903672, 1119689 -->  
Windows 10 장치를 Windows 10 Education, Windows 10 Education KN, Windows 10 Professional, Windows 10 Professional KN, Windows 10 Professional Education 및 Windows 10 Professional Education KN으로 업그레이드하는 Windows 10 버전 업그레이드 정책을 만들 수 있습니다. Windows 10 버전 업그레이드에 대한 자세한 내용은 [Windows 10 버전 업그레이드 구성 방법](edition-upgrade-configure-windows-10.md)을 참조하세요.

### <a name="review-policy-compliance-for-windows-10-update-rings----1352223---"></a>Windows 10 업데이트 링에 대한 정책 준수 검토 <!-- 1352223 -->  
**소프트웨어 업데이트** > **업데이트 링 배포 상태별**에서 Windows 10 업데이트 링에 대한 정책 보고서를 검토할 수 있습니다. 정책 보고서에는 구성한 업데이트 링에 대한 배포 상태가 포함됩니다. 

### <a name="windows-10-company-portal-app-added-to-windows-information-protection-allow-policy----677129---"></a>Windows Information Protection 허용 정책에 추가된 Windows 10 회사 포털 앱 <!-- 677129 -->  
Windows 10 회사 포털 앱이 WIP(Windows Information Protection)를 지원하도록 업데이트됩니다. 앱을 WIP 허용 정책에 추가할 수 있습니다. 이러한 변경으로 이제 앱을 **제외** 목록에 추가하지 않아도 됩니다. 

### <a name="remote-support-for-windows-and-windows-mobile-devices-----1070473---"></a>Windows 및 Windows Mobile 장치에 대한 원격 지원  <!-- 1070473 -->    
Intune에서는 [TeamViewer](https://www.teamviewer.com) 소프트웨어(별매)를 사용하여 Windows 및 Windows Mobile 장치를 실행하는 사용자에게 원격 지원을 제공할 수 있습니다.

### <a name="scan-devices-with-windows-defender----1280988--1280990-----"></a>Windows Defender를 사용하여 장치 검사 <!-- 1280988  1280990   -->
관리되는 Windows 10 장치에서 Windows Defender 바이러스 백신으로 **빠른 검사**, **전체 검사** 및 **서명 업데이트**를 실행할 수 있습니다. 장치의 개요 블레이드에서 장치에서 실행할 작업을 선택합니다. 명령을 장치로 전송하기 전에 작업을 확인하는 메시지가 표시됩니다. 

**빠른 검사**: 빠른 검사는 레지스트리 키 및 알려진 Windows 시작 폴더처럼 맬웨어 레지스터가 시작하는 위치를 검사합니다. 빠른 검사에는 평균 5분이 걸립니다. 파일을 열고 닫을 때와 사용자가 폴더를 탐색할 때마다 파일을 검사하는 **항상 실시간 보호** 설정과 결합된 빠른 검사는 시스템이나 커널에 있을 수 있는 맬웨어로부터 보호합니다. 검사가 완료되면 장치에 검사 결과가 표시됩니다. 

**전체 검사**: 전체 검사는 맬웨어 위협이 발생한 장치에서 더 철저한 정리가 필요한 비활성 구성 요소가 있는지 확인할 때 유용할 수 있으며, 주문형 검사 실행에 유용합니다. 전체 검사는 실행하는 데 1시간이 걸릴 수 있습니다. 검사가 완료되면 장치에 검사 결과가 표시됩니다. 

**서명 업데이트**: 서명 업데이트 명령은 Windows Defender 바이러스 백신 맬웨어 정의 및 서명을 업데이트합니다. 이렇게 하면 Windows Defender 바이러스 백신에서 맬웨어를 검색하는 데 효과적입니다. 이 기능은 장치 인터넷 연결을 기다리는 Windows 10 장치 전용입니다. 

### <a name="bitlocker-device-configuration----1397398---"></a>BitLocker 장치 구성 <!-- 1397398 -->  
**Windows 암호화 > 기본 설정**에는 사용자의 장치에서 사용될 수 있는 다른 디스크 암호화에 대한 [경고 메시지](https://docs.microsoft.com/en-us/windows/client-management/mdm/bitlocker-csp#allowarningforotherdiskencryption)를 사용하지 않도록 설정할 수 있는 새 **다른 디스크 암호화에 대한 경고** 설정이 포함됩니다.  경고 메시지는 장치에 BitLocker를 설정하기 전에 최종 사용자 동의가 필요하며 최종 사용자가 확인할 때까지 BitLocker 설정이 차단됩니다.  새 설정을 통해 최종 사용자 경고를 사용하지 않도록 할 수 있습니다.

### <a name="company-portal-for-windows-81-and-windows-phone-81-moving-to-sustaining-mode---1428681--"></a>유지 모드로 전환되는 Windows 8.1 및 Windows Phone 8.1용 회사 포털 <!--1428681-->
2017년 10월부터 Windows 8.1 및 Windows Phone 8.1용 회사 포털 앱이 유지 모드로 전환됩니다. 앱과 등록 및 준수 같은 기존 시나리오가 이러한 플랫폼에서 계속 지원된다는 뜻입니다. 이러한 앱은 Microsoft 스토어 같은 기존 릴리스 채널을 통해 계속 다운로드할 수 있습니다. 

유지 모드가 되면 이러한 앱은 중요 보안 업데이트만 받습니다. 이러한 앱에 대해 릴리스되는 추가 업데이트 또는 기능은 없습니다. 새 기능의 경우 장치를 Windows 10 또는 Windows 10 Mobile로 업데이트하는 것이 좋습니다. 

###  <a name="block-copy-and-paste-between-work-and-personal-profiles-in-android-for-work----1098994---"></a>Android for Work에서 회사 및 개인 프로필 간의 복사 및 붙여넣기 차단 <!-- 1098994 -->   
이 릴리스에서는 Android for Work에 대한 회사 프로필을 구성하여 회사와 개인 앱 간에 복사 및 붙여넣기를 차단할 수 있습니다. **회사 프로필 설정**의 **Android for Work** 플랫폼에 대한 **장치 제한** 프로필에서 이 새 설정을 찾을 수 있습니다.

### <a name="new-behaviors-for-the-company-portal-app-for-android-with-work-profiles----1485783---"></a>회사 프로필을 사용하는 Android용 회사 포털 앱의 새로운 동작 <!---1485783--->
회사 프로필을 사용하여 Android for Work 장치를 등록하면 회사 프로필의 회사 포털 앱이 장치에서 관리 작업을 수행합니다. 개인 프로필에서 MAM 지원 앱을 사용하는 경우가 아니면 Android용 회사 포털 앱은 더 이상 사용되지 않습니다. 회사 프로필 환경을 향상하기 위해 Intune이 회사 프로필을 등록한 후 개인 회사 포털 앱을 자동으로 숨깁니다.

Android용 회사 포털 앱은 [Play 스토어에서 회사 포털](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)을 검색하고 **사용**을 탭하여 개인 프로필에서 언제든지 사용할 수 있습니다.

### <a name="intune-mam--outlook-for-android-add-ins-----1450688---"></a>Android용 Intune MAM 및 Outlook 추가 기능  <!-- 1450688 -->
몇 주 후에 Office 팀은 Android의 Outlook용 추가 기능을 발표할 것입니다. 이 추가 기능 집합은 Windows, iOS, 웹 및 Mac의 Outlook에 이미 존재합니다. 추가 기능은 Exchange를 통해 관리되기 때문에 사용자는 Outlook 및 관리되지 않는 추가 기능 응용 프로그램에서 데이터와 메시지를 복사하고 공유할 수 있습니다(Exchange 관리자가 추가 기능에 대한 액세스를 해제하지 않은 경우). 

추가 기능에 대한 사용자 액세스 권한을 관리하려면 Exchange 관리자와 함께 작업하여 MAM 데이터 보호 정책이 추가 기능에 적용되도록 합니다.

#### <a name="how-does-this-affect-me"></a>이 변경 사항은 어떤 영향을 미치나요?
Exchange 정책이 이미 추가 기능을 사이드로드하거나 설치하지 않도록 설정된 경우 더 읽지 마세요. MAM 정책은 예상대로 적용됩니다. 그러나 Android의 Outlook 내에서 잘라내기, 복사 및 붙여넣기 작업을 제한하도록 MAM의 정책을 설정하고 Exchange의 추가 기능 정책을 설정하지 않은 경우, 기본적으로 사용자가 Outlook에 추가 기능을 설치할 수 있습니다. 이러한 추가 기능은 메시지 본문, 제목 및 기타 메시지 속성에 액세스할 수 있습니다. Exchange 관리자가 “내 마켓플레이스 앱” 및 “내 사용자 지정 앱” 역할을 제거하도록 하여 최종 사용자가 추가 기능을 설치하는 기능을 해제할 수 있습니다. 자세한 내용은 아래 공유된 추가 정보 링크를 참조하세요.

Exchange에서 설정 변경은 Windows, iOS, 웹, Mac 및 모바일의 Outlook에 적용됩니다. 

#### <a name="what-do-i-need-to-do"></a>어떤 작업을 수행해야 하나요?
지금 Exchange 정책을 검토합니다. IT 및 지원 센터 직원에게 알립니다. 궁금한 사항이 있으면 지원 팀에 문의하세요. 

### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>Intune 데이터 웨어하우스 데이터 모델에 추가된 사용자 장치 연결 엔터티 컬렉션 <!-- 1187917 -->
사용자와 장치 엔터티 컬렉션을 연결하는 사용자 장치 연결 정보를 사용하여 보고서 및 데이터 시각화를 작성할 수 있습니다. 데이터 모델은 데이터 웨어하우스 Intune 페이지에서 검색한 Power BI 파일(PBIX)이나 OData 끝점을 통해 액세스하거나 사용자 지정 클라이언트를 개발하여 액세스할 수 있습니다.


<!-- the following are present prior to 1709 -->

### <a name="actions-for-non-compliance----730266--"></a>비준수에 대한 작업 <!--730266-->     
*비준수에 대한 작업*은 정책을 준수하지 않는 장치에 조치를 취할 수 있는 준수 정책의 새로운 기능입니다. 단일 또는 여러 작업을 지정할 수 있으며, 이러한 작업이 수행되어야 하는 기간을 지정할 수 있습니다. 예를 들어 장치가 메일을 통해 비준수 상태가 된 직후에 사용자에게 비준수 장치를 알리거나 조건부 액세스를 통해 3일 유예 기간이 지난 후 비준수 장치가 회사 리소스에 액세스하는 것을 못하도록 차단할 수 있습니다.

### <a name="new-report-that-lists-ios-devices-with-older-ios-versions------1352223---"></a>이전 iOS 버전을 사용하는 iOS 장치를 나열하는 새 보고서   <!-- 1352223 -->
**오래된 iOS 장치** 보고서는 **소프트웨어 업데이트** 작업 영역에서 사용할 수 있습니다. iOS 업데이트 정책에서 대상으로 지정했으며 업데이트가 사용 가능한 감독된 iOS 장치 목록이 보고서에 표시됩니다. 장치가 자동으로 업데이트되지 않은 이유를 나타내는 각 장치의 상태를 볼 수 있습니다. 

### <a name="new-settings-for-windows-10-device-restriction-profile"></a>Windows 10 장치 제한 프로필에 대한 새로운 설정
<!--- 978575, 1308849, -->
Windows Defender SmartScreen 범주의 Windows 10 장치 제한 프로필에 새 설정을 추가합니다.

Windows 10 장치 제한 프로필에 대한 세부 정보는 [Windows 10 이상 장치 제한 설정]( device-restrictions-windows-10.md)을 참조하세요.

### <a name="android-for-work-support-for-lookout----1087312---"></a>Android for Work의 Lookout 지원 <!-- 1087312 -->   
Lookout for Work 앱 사용 시 Lookout이 설치된 Intune 커넥터가Android for Work 장치를 지원할 예정입니다. 그러면 컨테이너 내부 또는 외부에서 Lookout 앱을 배포할 수 있습니다.

### <a name="intune-app-protection-and-citrix-mdx-development-tools----709185---"></a>Intune 앱 보호 및 Citrix MDX 개발 도구<!-- 709185 -->
Citrix XenMobile MDX와 Microsoft Intune의 조합으로 장치와 앱을 관리할 수 있습니다. 이 옵션을 사용하면 Citrix의 mVPN 기술을 사용하면서 Intune 앱 보호 정책으로 앱을 관리할 수 있습니다.

Intune 앱 래핑 도구와 iOS 및 Android용 Intune 앱 SDK를 포함하는 코드 리포지토리를 찾아 Citrix MDX mVPN 기술과 통합할 수 있습니다.

### <a name="zimperium---new-mobile-threat-defense-partner------954681---"></a>Zimperium - 새 Mobile Threat Defense 파트너 <!-- 954681 -->
Microsoft Intune과 통합된 Mobile Threat Defense 솔루션인 Zimperium에서 수행한 위험 평가에 따라 조건부 액세스를 사용하여 회사 리소스에 대한 모바일 장치의 액세스를 제어할 수 있습니다.

#### <a name="how-integration-with-intune-works"></a>Intune과 통합은 어떻게 작동하나요?
위험은 Zimperium을 실행하는 장치에서 수집된 원격 분석에 따라 평가됩니다. Intune 장치 준수 정책을 통해 사용하도록 설정된 Zimperium 위험 평가에 따라 EMS 조건부 액세스 정책을 구성할 수 있습니다. 이 정책을 사용하여 회사 리소스에 액세스하는 미준수 장치를 감지된 위협에 따라 허용하거나 차단할 수 있습니다.

### <a name="new-azure-ad-conditional-access-policy-ui-link-from-intune-----1016201---"></a>Intune의새 Azure AD 조건부 액세스 정책 UI 링크  <!-- 1016201 -->
IT 관리자는 Azure AD 워크로드에서 새 조건부 액세스 정책 UI를 통해 앱 기반 조건부 정책을 설정할 수 있습니다. Azure의 Intune 앱 보호 섹션에 있는 앱 기반 조건부 액세스 정책은 그대로 남아 있으며 나란히 함께 적용됩니다. Intune 워크로드에서 Azure AD의 새 조건부 액세스 정책 UI에 연결하는 편리한 링크도 있습니다.

### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>온-프레미스 Exchange Connector 고가용성 지원 <!-- 676614 -->   
온-프레미스 Exchange Connector에 대해 여러 CAS(클라이언트 액세스 서버) 역할을 사용할 수 있습니다. 예를 들어 주 CA에서 오류가 발생할 경우 Exchange Connector는 다른 CAS로 대체하기 위한 쿼리를 수신합니다. 이 기능은 서비스가 중단되지 않도록 합니다.

### <a name="system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>Exchange Connector용 System Center Operations Manager 관리 팩 <!-- 885457 -->   
Exchange Connector 로그를 구문 분석하는 데 도움이 되도록 Exchange Connector용 System Center Operations Manager 관리 팩이 제공될 예정입니다. 이 관리 팩을 사용하면 문제를 해결해야 할 때 Intune을 다른 방식으로 모니터링할 수 있습니다.

### <a name="end-of-support-for-ios-80----1164477---"></a>iOS 8.0에 대한 지원 종료 <!---1164477--->
관리되는 앱 및 iOS용 회사 포털 앱이 회사 리소스에 액세스하려면 iOS 9.0 이상이 필요합니다. 올해 9월 이전에 업데이트되지 않은 장치는 회사 포털 또는 해당 앱에 더 이상 액세스할 수 없게 됩니다. 12월에는 메일을 포함한 회사 리소스에 대한 모든 액세스가 차단됩니다. 

### <a name="end-of-support-for-android-43-and-lower----1171127-1326920----"></a>Android 4.3 및 이전 버전에 대한 지원 종료 <!---1171127, 1326920 --->
관리되는 앱과 Android용 회사 포털 앱이 회사 리소스에 액세스하려면 Android 4.4 이상이 필요합니다. 10월이 시작되기 전에 업데이트되지 않은 장치는 더 이상 회사 포털 또는 이러한 앱에 액세스할 수 없습니다. 12월까지 등록된 모든 장치는 12월에 강제 사용 중지되며, 따라서 회사 리소스에 액세스할 수 없게 됩니다. MDM 없이 앱 보호 정책을 사용하는 경우 앱에 업데이트가 수신되지 않으며 시간이 지남에 따라 경험의 품질이 저하됩니다.

### <a name="platform-support-reminder-windows-phone-81-mainstream-support-will-end-july-11-2017----1327781---"></a>플랫폼 지원 미리 알림: Windows Phone 8.1 기본 지원이 2017년 7월 11일에 종료됨 <!-- 1327781 -->  
2017년 7월 11일에 Windows Phone 8.1 플랫폼의 기본 지원이 종료됩니다. Windows 8.1 PC 지원은 영향을 받지 않습니다.

Intune 서비스에서 관리되는 Windows Phone 8.1 장치에 대한 즉각적인 영향은 없습니다. 등록된 장치는 계속 작동하며 모든 정책, 구성 및 앱이 계속해서 예상대로 작동합니다. Intune 서비스 내의 Windows Phone 8.1 플랫폼과 Windows Phone 8.1 회사 포털 앱을 대상으로 하는 향상된 기능은 없습니다.

가능하면 빨리 해당 Windows Phone 8.1 장치를 Windows 10 Mobile로 업그레이드하는 것이 좋습니다. 





## <a name="intune-apps"></a>Intune 앱
### <a name="refresh-action-added-to-the-company-portal-app-for-windows-10---1132468--"></a>Windows 10용 회사 포털 앱에 추가된 새로 고침 작업 <!--1132468-->
Windows 10용 회사 포털 앱을 사용하는 사용자는 당겨서 새로 고치거나 데스크톱에서 F5 키를 눌러 앱의 데이터를 새로 고칠 수 있습니다.


### <a name="apps-that-are-available-with-or-without-enrollment-can-now-be-installed-without-being-prompted-for-enrollment----1334712---"></a>등록을 하거나 등록을 하지 않고 사용할 수 있는 앱이 이제 등록을 묻는 메시지가 표시되지 않고 설치될 수 있습니다. <!-- 1334712 -->
Android 회사 포털 앱에서 등록을 하거나 등록을 하지 않고 사용할 수 있는 회사 앱이 등록을 묻는 메시지가 표시되지 않고 설치될 수 있습니다.

### <a name="ios-company-portal-display-large-icons----1454593---"></a>iOS 회사 포털 큰 아이콘 표시 <!-- 1454593 -->
iOS 회사 포털에서 앱 타일에 아이콘을 표시하는 방법과 관련된 알려진 문제를 해결하는 중입니다. 120x120픽셀 이상의 앱 아이콘을 업로드하는 경우 이제 [회사 포털 웹 사이트](https://portal.manage.microsoft.com) 및 iOS 회사 포털의 앱 페이지에 앱 타일의 전체 크기로 표시됩니다.

### <a name="easier-to-understand-phrasing-for-the-company-portal-app-for-android------1396349---"></a>Android용 회사 포털 앱의 구문을 쉽게 이해  <!---1396349--->    
최종 사용자가 쉽게 등록할 수 있도록 새로운 텍스트가 포함되어 Android용 회사 포털 앱의 등록 프로세스가 간소화되었습니다. 


<!-- the following are present prior to 1709 -->


### <a name="intune-managed-browser-support-for-ios-and-android----1374196---"></a>iOS 및 Android를 위한 Intune Managed Browser 지원 <!---1374196--->
2017년 10월을 기준으로 Android 앱에서 Intune Managed Browser 앱은 Android 4.4 이상을 실행하는 장치만 지원합니다. iOS의 Intune Managed Browser 앱은 iOS 9.0 이상을 실행하는 장치만 지원합니다. Android 및 iOS 이전 버전에서도 계속 Managed Browser를 사용할 수는 있지만 새로운 버전의 앱을 설치할 수 없고 모든 기능을 액세스하지 못할 수 있습니다. 이러한 장치를 지원되는 운영 체제 버전으로 업데이트하는 것이 좋습니다.

### <a name="allow-end-users-to-access-the-company-portal-app-for-android-without-enrollment----1169910---"></a>최종 사용자가 등록 없이 Android용 회사 포털 앱에 액세스하도록 허용 <!---1169910--->  
머지 않아 최종 사용자가 장치를 등록하지 않고도 Android용 회사 포털 앱에 액세스할 수 있게 됩니다. 앱 보호 정책을 사용하는 조직의 최종 사용자는 회사 포털 앱을 열 때 장치를 등록하라는 메시지를 더 이상 받지 않습니다. 최종 사용자가 장치를 등록하지 않고 회사 포털에서 앱을 설치할 수도 있습니다. 

### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>사용자가 등록이 허용된 최대 장치 수에 도달하면 표시되는 향상된 오류 메시지 <!-- 1270370 -->
일반 오류 메시지 대신 최종 사용자에게 “IT 관리자가 허용한 최대 장치 수를 등록했습니다. 등록된 장치를 제거하거나 IT 관리자에게 도움을 요청하십시오.”라는 친숙하고 조치를 수행할 수 있는 오류 메시지가 표시됩니다.

### <a name="inform-end-users-what-device-information-can-be-seen-for-ios---739894--"></a>iOS에 대해 표시되는 장치 정보를 최종 사용자에게 알리기 <!--739894-->
iOS용 회사 포털 앱에서 장치 세부 정보 화면에 **소유권 형식**을 추가합니다. 그러면 이 페이지를 통해 Intune 최종 사용자 문서에서 직접 정책에 대한 자세한 내용을 찾아볼 수 있습니다. 정보 화면에서도 이 정보를 찾을 수 있습니다.

### <a name="apps-details-pages-display-new-information-for-android-devices---1287476--"></a>앱 세부 정보 페이지에서 Android 장치의 새 정보 표시 <!--1287476-->
Android용 회사 포털 앱의 앱 세부 정보 페이지에는 IT 관리자가 해당 앱에 대해 정의한 앱 범주가 표시됩니다.

### <a name="intune-mobile-application-management-mam-dialog-boxes-now-have-a-modern-interface----1199015---"></a>Intune MAM(모바일 응용 프로그램 관리) 대화 상자에는 이제 최신 인터페이스가 포함됨 <!-- 1199015 -->
Intune MAM(모바일 응용 프로그램 관리) 대화 상자가 최신 모양과 느낌으로 업데이트되었습니다. 대화 상자는 이전 스타일과 동일한 방식으로 작동합니다.

최신 Android 장치에서 Intune을 통해 표시되는 오류 또는 알림 대화 상자가 이제 업데이트된 모양과 느낌을 표시합니다.



## <a name="notices"></a>알림
### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple의 Application Transport Security 업데이트 요구 <!--748318-->   
Apple에서는 2017년 봄부터 ATS(Application Transport Security)에 대한 특정 요구 사항을 적용할 것이라고 발표했습니다. ATS는 HTTPS를 통한 모든 앱 통신에서 보다 엄격한 보안을 적용하는 데 사용됩니다. 이 변경 사항은 iOS 회사 포털 앱을 사용하는 Intune 고객에게 영향을 줍니다. 자세한 내용은 [Intune 지원 블로그](https://aka.ms/compportalats)를 참조하세요.

### <a name="plan-for-change-intune-is-changing-the-intune-partner-portal-experience----1050016---"></a>변경 계획: Intune의 Intune 파트너 포털 환경 변화 <!-- 1050016 -->
2017년 5월 중순의 서비스 업데이트부터 manage.microsoft.com에서 Intune 파트너 페이지가 제거됩니다.  

파트너 관리자인 경우 더 이상 Intune 파트너 페이지에서 고객을 대신하여 작업을 보고 수행할 수 없지만, 대신 Microsoft의 다른 두 파트너 포털 중 하나에서 로그인해야 합니다.

[Microsoft 파트너 센터](https://partnercenter.microsoft.com/) 및 [Microsoft Office 365 파트너 관리 센터](https://portal.office.com/)를 통해, 관리하는 고객 계정에 로그인할 수 있습니다. 파트너로서 앞으로는 이러한 사이트 중 하나를 사용하여 고객을 관리하세요.



### <a name="see-also"></a>참고 항목
최근 개발 작업에 대한 자세한 내용은 [Microsoft Intune의 새로운 기능](whats-new.md)을 참조하세요.
