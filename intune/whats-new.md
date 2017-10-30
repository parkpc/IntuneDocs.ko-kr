---
title: "Microsoft Intune의 새로운 기능"
titlesuffix: Azure portal
description: "Intune Azure 포털의 새로운 기능 알아보기"
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 10/19/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b77323c30dccf4c8b9e5c692a40aec7389809891
ms.sourcegitcommit: 128770ecc820f6ff3c99b15752bce7a58257f1d5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2017
---
# <a name="whats-new-in-microsoft-intune"></a>Microsoft Intune의 새로운 기능

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

매주 Microsoft Intune에 추가되는 새로운 기능에 대해 알아봅니다. [예정된 변경](#whats-coming), 서비스 관련 [중요 공지](#notices) 및 [이전 릴리스](whats-new-archive.md) 관련 정보에 대해서도 알아볼 수 있습니다.

> [!Note]
> 이러한 기능 중 대다수는 최종적으로 Configuration Manager를 사용하는 하이브리드 배포용으로 지원될 예정입니다. 새로운 하이브리드 기능에 대한 자세한 내용은 [hybrid What’s New page](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management)(하이브리드 새로운 기능 페이지)를 참조하세요.


<!-- Common categories:  
  ### Device enrollment
  ### Device management
  ### App management
  ### Device configuration
  ### Role-based access control
  ### Intune apps
  ### Monitor and troubleshoot

-->   
## <a name="week-of-october-16-2017"></a>2017년 10월 16일의 주

### <a name="device-enrollment"></a>장치 등록
#### <a name="windows-autopilot-deployment-program-support-in-microsoft-intune-----747617----"></a>Microsoft Intune의 Windows AutoPilot Deployment 프로그램 지원 <!-- 747617  -->
이제 Windows AutoPilot Deployment 프로그램과 함께 Microsoft Intune을 사용하여 사용자가 IT를 수반하지 않고도 회사 장치를 프로비전할 수 있습니다. OOBE(첫 실행 경험)를 사용자 지정하고, 사용자가 장치를 Azure AD에 조인하고 Intune에 등록하도록 안내할 수 있습니다. Microsoft Intune 및 Windows AutoPilot을 함께 사용하면 운영 체제 이미지를 배포, 유지 및 관리할 필요가 없습니다. 자세한 내용은 [Windows AutoPilot Deployment 프로그램을 사용하여 Windows 장치 등록](https://docs.microsoft.com/intune/enrollment-autopilot)을 참조하세요.

#### <a name="quick-start-for-device-enrollment-----1425655---"></a>장치 등록에 대한 빠른 시작 <!-- 1425655 --> 
빠른 시작은 이제 **장치 등록**에서 사용할 수 있으며, 플랫폼 관리 및 등록 프로세스 구성에 대한 참조 테이블을 제공합니다. 각 항목에 대한 간략한 설명과 단계별 지침이 포함된 설명서에 대한 링크는 시작을 간소화하는 데 유용한 설명서를 제공합니다.

#### <a name="device-categorization----1427491---"></a>장치 분류 <!-- 1427491 -->
**장치 > 개요** 블레이드의 등록된 장치 플랫폼 차트는 Android, iOS, macOS, Windows 및 Windows Mobile을 포함하여 플랫폼별로 장치를 구성합니다.  다른 운영 체제를 실행하는 장치는 "기타"로 그룹화됩니다.  여기에는 Blackberry, NOKIA 및 기타 업체에서 제조하는 장치가 포함됩니다.  

테넌트에서 영향을 받는 장치를 알아보려면 **관리 > 모든 장치**를 차례로 선택한 다음 **필터**를 사용하여 **OS** 필드를 제한합니다.



### <a name="device-management"></a>장치 관리
#### <a name="zimperium---new-mobile-threat-defense-partner------954681---"></a>Zimperium - 새 Mobile Threat Defense 파트너 <!-- 954681 -->  
Microsoft Intune과 통합되는 MTD(Mobile Threat Defense) 솔루션인 Zimperium에서 수행된 위험 평가에 기반하는 조건부 액세스를 사용하여 모바일 장치에서 회사 리소스에 대한 액세스를 제어할 수 있습니다.

##### <a name="how-integration-with-intune-works"></a>Intune과 통합하는 방법
위험은 Zimperium을 실행하는 장치에서 수집된 원격 분석에 따라 평가됩니다. Intune 장치 준수 정책을 통해 사용하도록 설정된 Zimperium 위험 평가에 따라 EMS 조건부 액세스 정책을 구성할 수 있습니다. 이 정책을 사용하여 회사 리소스에 액세스하는 미준수 장치를 감지된 위협에 따라 허용하거나 차단할 수 있습니다.

#### <a name="new-settings-for-windows-10-device-restriction-profile------978575-1308849---"></a>Windows 10 장치 제한 프로필에 대한 새로운 설정 <!--- 978575, 1308849, -->  
Windows Defender SmartScreen 범주의 Windows 10 장치 제한 프로필에 새 설정을 추가합니다.

Windows 10 장치 제한 프로필에 대한 세부 정보는 [Windows 10 이상 장치 제한 설정]( device-restrictions-windows-10.md)을 참조하세요.

#### <a name="remote-support-for-windows-and-windows-mobile-devices------1070473---"></a>Windows 및 Windows Mobile 장치에 대한 원격 지원 <!-- 1070473 -->  
Intune에서 이제 [TeamViewer](https://www.teamviewer.com) 소프트웨어(별매)를 사용하여 Windows 및 Windows Mobile 장치를 실행하는 사용자에게 원격 지원을 제공할 수 있습니다.

#### <a name="scan-devices-with-windows-defender----1280988--1280990-----"></a>Windows Defender를 사용하여 장치 검사 <!-- 1280988  1280990   -->
관리되는 Windows 10 장치에서 이제 Windows Defender 바이러스 백신을 사용하여 **빠른 검사**, **전체 검사** 및 **서명 업데이트**를 실행할 수 있습니다. 장치의 개요 블레이드에서 장치에서 실행할 작업을 선택합니다. 명령을 장치로 전송하기 전에 작업을 확인하는 메시지가 표시됩니다. 

**빠른 검사**: 빠른 검사는 레지스트리 키 및 알려진 Windows 시작 폴더처럼 맬웨어 레지스터가 시작하는 위치를 검사합니다. 빠른 검사에는 평균 5분이 걸립니다. 파일을 열고 닫을 때와 사용자가 폴더를 탐색할 때마다 파일을 검사하는 **항상 실시간 보호** 설정과 결합된 빠른 검사는 시스템이나 커널에 있을 수 있는 맬웨어로부터 보호합니다. 검사가 완료되면 장치에 검사 결과가 표시됩니다. 

**전체 검사**: 전체 검사는 맬웨어 위협이 발생한 장치에서 더 철저한 정리가 필요한 비활성 구성 요소가 있는지 확인할 때 유용할 수 있으며, 주문형 검사 실행에 유용합니다. 전체 검사는 실행하는 데 1시간이 걸릴 수 있습니다. 검사가 완료되면 장치에 검사 결과가 표시됩니다. 

**서명 업데이트**: 서명 업데이트 명령은 Windows Defender 바이러스 백신 맬웨어 정의 및 서명을 업데이트합니다. 이렇게 하면 Windows Defender 바이러스 백신에서 맬웨어를 검색하는 데 효과적입니다. 이 기능은 장치 인터넷 연결을 기다리는 Windows 10 장치 전용입니다. 

#### <a name="the-enabledisable-button-is-removed-from-the-intune-certificate-authority-page-of-the-intune-azure-portal-----1400455---"></a>Intune Azure 포털의 Intune 인증 기관 페이지에서 설정/해제 단추 제거 <!-- 1400455 -->
 Intune에서 인증서 커넥터를 설정하는 추가 단계를 제거하고 있습니다. 현재 인증서 커넥터를 다운로드한 다음 Intune 콘솔에서 이를 사용하도록 설정합니다. 그러나 Intune 콘솔에서 커넥터를 사용하지 않도록 설정하더라도 커넥터에서 인증서를 계속 발급합니다.

##### <a name="how-does-this-affect-me"></a>이 변경 사항은 어떤 영향을 미치나요?
설정/해제 단추는 10월부터 Azure Portal의 인증 기관 페이지에서 표시되지 않습니다. 커넥터 기능은 동일하게 그대로 유지됩니다. Intune에서 등록한 장치에는 인증서가 여전히 배포됩니다. 인증서 커넥터는 계속 다운로드하여 설치할 수 있습니다. 인증서 발급을 중지하려면 이제 인증서 커넥터를 사용하지 않도록 설정하는 대신 제거합니다.

##### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>이러한 변경에 대해 준비하려면 어떻게 해야 하나요?
현재 인증서 커넥터를 사용할 수 없도록 설정되어 있으면 제거해야 합니다.



### <a name="device-configuration"></a>장치 구성
#### <a name="new-settings-for-windows-10-team-device-restriction-profile-------1308838---"></a>Windows 10 Team 장치 제한 프로필에 대한 새로운 설정 <!--- 1308838 -->
이 릴리스에서는 Surface Hub 장치를 제어할 수 있도록 Windows 10 Team 장치 제한 프로필에 많은 새로운 설정을 추가했습니다.

이 프로필에 대한 자세한 내용은 [Windows 10 Team 장치 제한 설정](device-restrictions-windows-10-teams.md)을 참조하세요.

#### <a name="prevent-users-of-android-devices-from-changing-their-device-date-and-time-----1333292---"></a>Android 장치 사용자가 장치 날짜 및 시간을 변경하지 못하도록 함 <!-- 1333292 -->
[Android 사용자 지정 장치 정책](custom-settings-android.md)을 사용하여 Android 장치 사용자가 장치 날짜 및 시간을 변경하지 못하도록 할 수 있습니다.

그렇게 하려면 URI ./Vendor/MSFT/PolicyManager/My/System/AllowDateTimeChange를**TRUE**로 설정하여 Android 사용자 지정 정책을 구성한 다음 필요한 그룹에 할당합니다.

#### <a name="bitlocker-device-configuration----1397398---"></a>BitLocker 장치 구성 <!-- 1397398 -->
**Windows 암호화 > 기본 설정**에는 사용자의 장치에서 사용될 수 있는 다른 디스크 암호화에 대해 [경고 메시지](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#allowarningforotherdiskencryption)를 사용하지 않도록 설정할 수 있는 **다른 디스크 암호화에 대한 경고** 설정이 새로 포함되었습니다.  경고 메시지는 장치에 BitLocker를 설정하기 전에 최종 사용자 동의가 필요하며 최종 사용자가 확인할 때까지 BitLocker 설정이 차단됩니다.  새 설정을 통해 최종 사용자 경고를 사용하지 않도록 할 수 있습니다.


### <a name="app-management"></a>앱 관리
#### <a name="volume-purchase-program-for-business-apps-will-now-sync-to-your-intune-tenant----800882---"></a>Intune 테넌트로 동기화되는 비즈니스용 Volume Purchase Program 앱 <!-- 800882 -->  
타사 개발자가 앱을 iTunes Connect에서 지정한 권한 있는 비즈니스용 VPP(Volume Purchase Program) 구성원에 개인적으로 배포할 수 있습니다. 이러한 VPP for Business 멤버는 Volume Purchase Program 앱 스토어에 로그인하고 해당 앱을 구입할 수 있습니다.

이 릴리스에서는 이제 최종 사용자가 구매한 비즈니스용 VPP 앱이 Intune 테넌트로 동기화됩니다.

#### <a name="select-apple-country-store-to-sync-vpp-apps-----1332311---"></a>Apple 국가 스토어를 선택하여 VPP 앱 동기화  <!-- 1332311 -->  
VPP 토큰을 업로드할 때 VPP(Volume Purchase Program) 국가 스토어를 구성할 수 있습니다. Intune은 지정된 VPP 국가 스토어의 모든 로캘에 대해 VPP 앱을 동기화합니다.

> [!NOTE]  
> 현재 Intune은 Intune 테넌트가 생성된 Intune 로캘과 일치하는 VPP 국가 스토어의 VPP 앱만 동기화합니다.




### <a name="intune-apps"></a>Intune 앱
#### <a name="block-copy-and-paste-between-work-and-personal-profiles-in-android-for-work----1098994---"></a>Android for Work에서 회사 및 개인 프로필 간의 복사 및 붙여넣기 차단 <!-- 1098994 -->
이 릴리스에서는 Android for Work에 대한 회사 프로필을 구성하여 회사와 개인 앱 간에 복사 및 붙여넣기를 차단할 수 있습니다. **회사 프로필 설정**의 **Android for Work** 플랫폼에 대한 **장치 제한** 프로필에서 이 새 설정을 찾을 수 있습니다.

#### <a name="create-ios-apps-limited-to-specific-regional-apple-app-stores----1281692---"></a>특정 지역 Apple 앱 스토어로 제한된 iOS 앱 만들기 <!-- 1281692 -->
Apple 앱 스토어 관리되는 앱을 만드는 동안 국가 로캘을 지정할 수 있습니다.

> [!Note]  
> 현재 미국 국가별 스토어에 있는 Apple 앱 스토어 관리되는 앱만 만들 수 있습니다.

####  <a name="update-ios-vpp-user-and-device-licensed-apps-----1305564---"></a>iOS VPP 사용자 및 장치 사용이 허가된 앱 업데이트  <!-- 1305564 -->  
iOS VPP 토큰을 구성하여 Intune 서비스를 통해 해당 토큰에 대해 구입한 모든 앱을 업데이트할 수 있습니다. Intune은 앱 스토어 내의 VPP 앱 업데이트를 검색하고 장치가 체크 인하면 자동으로 장치에 푸시합니다.

VPP 토큰을 설정하고 자동 업데이트를 사용하도록 설정하는 단계는 [Microsoft Intune을 사용하여 대량 구매 프로그램을 통해 구매한 iOS 앱을 관리하는 방법](/intune/vpp-apps-ios)을 참조하세요.



### <a name="monitor-and-troubleshoot"></a>모니터링 및 문제 해결
#### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>Intune 데이터 웨어하우스 데이터 모델에 추가된 사용자 장치 연결 엔터티 컬렉션 <!-- 1187917 -->
이제 사용자와 장치 엔터티 컬렉션을 연결하는 사용자 장치 연결 정보를 사용하여 보고서 및 데이터 시각화를 작성할 수 있습니다. 데이터 모델은 데이터 웨어하우스 Intune 페이지에서 검색한 Power BI 파일(PBIX)이나 OData 끝점을 통해 액세스하거나 사용자 지정 클라이언트를 개발하여 액세스할 수 있습니다.

#### <a name="review-policy-compliance-for-windows-10-update-rings----1067886---"></a>Windows 10 업데이트 링에 대한 정책 준수 검토 <!-- 1067886 -->
[소프트웨어 업데이트 > 업데이트 링 배포 상태별]에서 Windows 10 업데이트 링에 대한 정책 보고서를 검토할 수 있습니다. 정책 보고서에는 구성한 업데이트 링에 대한 배포 상태가 포함됩니다. 

#### <a name="new-report-that-lists-ios-devices-with-older-ios-versions------1352223---"></a>이전 iOS 버전을 사용하는 iOS 장치를 나열하는 새 보고서   <!-- 1352223 -->
**오래된 iOS 장치** 보고서는 **소프트웨어 업데이트** 작업 영역에서 사용할 수 있습니다. iOS 업데이트 정책에서 대상으로 지정했으며 업데이트가 사용 가능한 감독된 iOS 장치 목록이 보고서에 표시됩니다. 장치가 자동으로 업데이트되지 않은 이유를 나타내는 각 장치의 상태를 볼 수 있습니다. 

#### <a name="view-app-protection-policy-assignments-for-troubleshooting-----1475003---"></a>문제 해결을 위해 앱 보호 정책 할당 보기 <!--  1475003 -->
이 예정된 릴리스에서는 **앱 보호 정책** 옵션이 문제 해결 블레이드에서 사용할 수 있는 **할당** 드롭다운 목록에 추가됩니다. 이제 앱 보호 정책을 선택하여 선택한 사용자에게 할당된 앱 보호 정책을 확인할 수 있습니다.



## <a name="week-of-october-2-2017"></a>2017년 10월 2일이 있는 주

### <a name="intune-apps"></a>Intune 앱
#### <a name="improvements-to-device-setup-workflow-in-company-portal---1490692--"></a>회사 포털의 향상된 장치 설정 워크플로 기능<!--1490692-->
Android용 회사 포털 앱에서 장치 설치 워크플로를 개선했습니다. 언어는 귀사를 위해 더욱 친숙하고 구체적으로 변경되었으며, 최대한 화면을 결합했습니다. 이러한 내용은 [앱 UI의 새로운 기능](whats-new-app-ui.md#week-of-october-2-2017) 페이지에서 확인할 수 있습니다.

#### <a name="improved-guidance-around-the-request-for-access-to-contacts-on-android-devices---1484985--"></a>Android 장치에서 연락처 액세스 요청에 대한 지침 개선<!--1484985-->

Android용 회사 포털 앱은 최종 사용자가 연락처 사용 권한을 허용하도록 해야 합니다. 최종 사용자가 이 액세스 권한을 거절하는 경우 조건부 액세스에 대한 권한을 부여한다고 경고하는 앱 내 알림이 표시됩니다. 

#### <a name="secure-startup-remediation-for-android---1490712--"></a>Android용 시작 업데이트 관리 보호<!--1490712-->

Android 장치를 가진 최종 사용자는 회사 포털 앱에서 비준수 이유를 누를 수 있습니다 가능하면 문제를 해결하기 위해 설정 앱의 올바른 위치로 직접 이동시킵니다. 

#### <a name="additional-push-notifications-for-end-users-on-the-company-portal-app-for-android-oreo---1475932--"></a>Android Oreo용 회사 포털 앱에서 최종 사용자를 위한 추가 푸시 알림 <!--1475932-->

최종 사용자에게 Intune 서비스의 정책 검색처럼 Android Oreo용 회사 포털 앱이 백그라운드 작업을 수행하는 시기를 알리는 추가 알림이 표시됩니다. 이를 통해 회사 포털이 장치에서 관리 작업을 수행하는 시기에 대해 최종 사용자에 대한 투명성이 증가됩니다. 이는 Android Oreo용 회사 포털 앱에 대한 전반적인 [회사 포털 UI 최적화](https://blogs.technet.microsoft.com/intunesupport/2017/08/21/android-8-0-o-behaviour-changes-and-microsoft-intune)의 일부입니다. 

Android Oreo에서 설정된 새로운 UI 요소를 추가로 최적화합니다.  최종 사용자는 회사 포털이 Intune 서비스로부터 정책을 검색하는 등 백그라운드 작업을 수행하는 시기를 나타내는 추가 알림을 받게 됩니다.  그러면 회사 포털이 해당 장치에서 관리 작업을 수행할 때 최종 사용자에 대한 투명도가 증가합니다.

#### <a name="new-behaviors-for-the-company-portal-app-for-android-with-work-profiles----1485783---"></a>회사 프로필을 사용하는 Android용 회사 포털 앱의 새로운 동작 <!---1485783--->

회사 프로필을 사용하여 Android for Work 장치를 등록하면 회사 프로필의 회사 포털 앱이 장치에서 관리 작업을 수행합니다. 

개인 프로필에서 MAM 지원 앱을 사용하는 경우가 아니면 Android용 회사 포털 앱은 더 이상 사용되지 않습니다. 회사 프로필 환경을 향상하기 위해 Intune이 회사 프로필을 등록한 후 개인 회사 포털 앱을 자동으로 숨깁니다.

Android용 회사 포털 앱은 [Play 스토어에서 회사 포털](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)을 검색하고 **사용**을 탭하여 개인 프로필에서 언제든지 사용할 수 있습니다.

#### <a name="company-portal-for-windows-81-and-windows-phone-81-moving-to-sustaining-mode---1428681--"></a>유지 모드로 전환되는 Windows 8.1 및 Windows Phone 8.1용 회사 포털 <!--1428681-->

2017년 10월부터 Windows 8.1 및 Windows Phone 8.1용 회사 포털 앱이 유지 모드로 전환됩니다. 앱과 등록 및 준수 같은 기존 시나리오가 이러한 플랫폼에서 계속 지원된다는 뜻입니다. 이러한 앱은 Microsoft 스토어 같은 기존 릴리스 채널을 통해 계속 다운로드할 수 있습니다. 

유지 모드가 되면 이러한 앱은 중요 보안 업데이트만 받습니다. 이러한 앱에 대해 릴리스되는 추가 업데이트 또는 기능은 없습니다. 새 기능의 경우 장치를 Windows 10 또는 Windows 10 Mobile로 업데이트하는 것이 좋습니다. 


### <a name="device-enrollment"></a>장치 등록

#### <a name="block-unsupported-samsung-knox-device-enrollment------1490695----"></a>지원되지 않는 Samsung KNOX 장치 등록 차단<!--- 1490695 --->

회사 포털 앱은 지원되는 Samsung KNOX 장치만을 등록하려고 합니다. KNOX 정품 인증 오류로 인해 MDM 등록을 방해하지 않도록 방지하기 위해 장치가 [Samsung에서 게시한 장치 목록](https://www.samsungknox.com/knox-supported-devices/knox-workspace)을 표시하는 경우에만 장치 등록을 시도합니다. 일부 Samsung 장치에는 KNOX를 지원하는 모델 번호가 있을 수 있습니다. 구매하고 배포하기 전에 장치 재판매인과 함께 KNOX 호환성을 검사합니다. [Android 및 Samsung KNOX 표준 정책 설정](/intune/supported-devices-browsers.md#intune-supported-devices)에서 확인된 장치의 전체 목록을 찾을 수 있습니다.

#### <a name="end-of-support-for-android-43-and-lower----1171126-1326920----"></a>Android 4.3 및 이전 버전에 대한 지원 종료 <!---1171126, 1326920 --->
Android용 회사 포털 앱과 관리되는 앱이 회사 리소스에 액세스하려면 Android 4.4 이상이 필요합니다. 12월까지 등록된 모든 장치는 12월에 강제 사용 중지되며, 따라서 회사 리소스에 액세스할 수 없게 됩니다. MDM 없이 앱 보호 정책을 사용 중인 경우 앱이 업데이트를 받지 못하며 해당 환경 품질이 시간이 흐름에 따라 저하됩니다.

#### <a name="inform-end-users-what-device-information-can-be-seen-on-enrolled-devices---1165314--"></a>등록된 장치에 표시되는 장치 정보를 최종 사용자에게 알리기<!--1165314-->
모든 회사 포털 앱의 장치 세부 정보 화면에 **소유권 형식**을 추가합니다. 그러면 [회사가 볼 수 있는 정보는 무엇인가요?](/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune) 문서에서 직접 개인 정보에 대한 자세한 내용을 찾아볼 수 있습니다. 이 기능은 나중에 모든 회사 포털 앱에 롤아웃될 예정입니다. [9월](https://docs.microsoft.com/intune/whats-new#week-of-september-11-2017)에 iOS에서 이 기능을 발표했습니다.


## <a name="week-of-september-25-2017"></a>2017년 9월 25일이 있는 주

### <a name="device-enrollment"></a>장치 등록

#### <a name="intune-supports-ios-11---1428975--"></a>Intune은 iOS 11을 지원합니다.<!--1428975-->
Intune은 iOS 11을 지원합니다. [Intune 지원 블로그](https://blogs.technet.microsoft.com/intunesupport/2017/09/12/support-tip-intune-support-for-ios-11/)에서 이전에 발표되었습니다.

#### <a name="end-of-support-for-ios-80----1164477---"></a>iOS 8.0에 대한 지원 종료 <!---1164477--->
관리되는 앱 및 iOS용 회사 포털 앱이 회사 리소스에 액세스하려면 iOS 9.0 이상이 필요합니다. 올해 9월 이전에 업데이트되지 않은 장치는 회사 포털 또는 해당 앱에 더 이상 액세스할 수 없게 됩니다. 

### <a name="intune-apps"></a>Intune 앱

#### <a name="refresh-action-added-to-the-company-portal-app-for-windows-10---1132468--"></a>Windows 10용 회사 포털 앱에 추가된 새로 고침 작업 <!--1132468-->
사용자는 Windows 10용 회사 포털 앱을 사용하여 새로 고침으로 끌어오거나 데스크톱에서 F5 키를 눌러서 앱에서 데이터를 새로 고칠 수 있습니다.



## <a name="notices"></a>알림

### <a name="new-path-for-managed-devices-in-graph-api----1586728---"></a>Graph API에서 관리되는 장치의 새로운 경로<!-- 1586728 -->
Graph API의 베타 버전에서 관리 장치에 액세스하는 데 사용되는 경로를 변경하고 있습니다. 

| | |
|--|--|
| 현재 경로 |  https://graph.microsoft.com/beta/managedDevices |
| 새로운 경로 | https://graph.microsoft.com/beta/deviceManagement/managedDevices |

10월 내내 두 경로가 모두 작동합니다. 10월 서비스 릴리스 후에는 새 경로만 작동합니다.  Graph API를 사용하여 관리되는 장치에 액세스하는 경우 새 경로로 스크립트 및 응용 프로그램을 업데이트하고 확인합니다. 추가 변경 내용은 월별 [Graph API 변경 로그](https://developer.microsoft.com/graph/docs/concepts/changelog)를 확인합니다.


### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Apple 등록 시나리오에 대한 직접 액세스 <!--951869-->
2017년 1월 이후에 만든 Intune 계정은 Azure 포털에서 장치 등록 워크로드를 사용하여 Apple 등록 시나리오에 직접 액세스할 수 있습니다. 이전에는 Intune 클래식 포털의 링크를 통해서만 Apple 등록 미리 보기에 액세스할 수 있었습니다. 2017년 1월 이전에 만든 Intune 계정은 일회성 마이그레이션을 수행해야 Azure에서 이러한 기능을 사용할 수 있습니다. 마이그레이션 일정은 아직 공지되지 않았지만 가능한 한 빠른 시일 내에 세부 정보가 제공될 예정입니다. 기존 계정에서 Azure 포털에 액세스할 수 없는 경우 평가판 계정을 만들어 새로운 환경을 테스트해 보는 것이 좋습니다.

### <a name="administration-roles-being-replaced-in-azure-portal"></a>Azure Portal에서 대체되는 관리 역할
Intune 클래식 포털(Silverlight)에서 사용된 기존 MAM(모바일 응용 프로그램 관리) 관리 역할(참가자, 소유자 및 읽기 전용)은 Intune Azure Portal에서 새로운 RBAC(역할 기반 관리 제어)의 전체 집합으로 대체됩니다. Azure Portal로 마이그레이션한 후에 이러한 새 관리 역할에 관리자를 다시 할당해야 합니다. RBAC 및 새 역할에 대한 자세한 내용은 [Microsoft Intune에 대한 역할 기반 액세스 제어](/intune/role-based-access-control)를 참조하세요.



## <a name="whats-coming"></a>향후 예정 사항

### <a name="changes-in-support-for-the-intune-ios-company-portal-app-----1164474----"></a>Intune iOS 회사 포털 앱에 대한 지원 변경 내용 <!-- 1164474  -->
iOS 9.0 이상을 실행하는 장치만 지원하는 iOS용 Microsoft Intune 회사 포털 앱의 새로운 버전이 곧 제공될 예정입니다. iOS 8을 지원하는 회사 포털 버전도 매우 짧은 시간 동안 사용할 수 있습니다. 그러나 MAM 지원 iOS 앱을 사용하는 경우 iOS 9.0 이상이 지원되므로 최종 사용자가 최신 OS로 업데이트하도록 하는 것이 좋습니다. 

#### <a name="how-does-this-affect-me"></a>이 변경 사항은 어떤 영향을 미치나요?
구체적인 날짜를 모르고 이 내용을 미리 알려드리는 것은 계획할 시간을 드리기 위해서입니다. 사용자가 iOS 9 이상으로 업데이트되도록 하고, 회사 포털 앱이 릴리스되면 최종 사용자에게 회사 포털 앱을 업데이트하도록 요청하세요.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>이러한 변경에 대해 준비하려면 어떻게 해야 하나요?
사용자에게 iOS 9.0 이상으로 업데이트하여 Intune의 새로운 기능을 완전히 활용하도록 권유합니다.  사용자에게 새 버전의 회사 포털을 설치하여 제공되는 새로운 기능을 활용하도록 권유합니다.

Azure Portal의 Intune으로 이동한 다음 [장치] > [모든 장치]에서 iOS 버전별로 필터링하여 iOS 9 이전 운영 체제를 사용하는 현재 장치를 모두 확인합니다.


### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple의 Application Transport Security 업데이트 요구 <!--748318-->
Apple에서는 ATS(Application Transport Security)에 대한 특정 요구 사항을 적용할 것이라고 발표했습니다. ATS는 HTTPS를 통한 모든 앱 통신에서 보다 엄격한 보안을 적용하는 데 사용됩니다. 이 변경 사항은 iOS 회사 포털 앱을 사용하는 Intune 고객에게 영향을 줍니다.

새로운 ATS 요구 사항을 적용하는 Apple TestFlight 프로그램을 통해 iOS용 회사 포털 앱 버전을 제공했습니다. ATS 준수를 테스트하는 데 이 버전을 사용해 보려면 이름, 성, 메일 주소, 회사 이름을 포함하여 <a href="mailto:CompanyPortalBeta@microsoft.com?subject=Register to TestFlight ATS Company Portal app">CompanyPortalBeta@microsoft.com</a>에 메일을 보내 주세요. 자세한 내용은 [Intune 지원 블로그](https://aka.ms/compportalats)를 참조하세요.

## <a name="see-also"></a>참고 항목
* [Microsoft Intune 블로그](http://go.microsoft.com/fwlink/?LinkID=273882)
* [클라우드 플랫폼 로드맵](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [What's new in the Company Portal UI](whats-new-app-ui.md)(회사 포털 UI의 새로운 기능)
* [지난 달의 새로운 기능](whats-new-archive.md)
