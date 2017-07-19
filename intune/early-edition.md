---
title: "초기 버전"
description: 
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 07/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 5eab3fb933b2999e23115091cf0ded3f140e114c
ms.sourcegitcommit: f5c6e8b218431dc9a8d85464d7f58adebd048866
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/06/2017
---
# <a name="the-early-edition-for-microsoft-intune---july-2017"></a>Microsoft Intune 초기 버전 - 2017년 7월

**초기 버전**에서는 Microsoft Intune의 향후 릴리스에서 도입될 기능의 목록을 제공합니다. 이 정보는 매우 제한적으로 제공되며 변경될 수 있습니다. 회사 외부에서 이 정보를 공유하지 마세요. 여기 나열된 일부 기능은 마감일을 맞추지 못할 위험이 있으며 다음 릴리스까지 지연될 수 있습니다. 다른 기능은 고객용 준비 상태를 확인하기 위해, 파일럿(플라이팅) 테스트 중 입니다. 질문이나 궁금한 내용이 있으면 Microsoft 제품 그룹 담당자에게 연락하세요.

이 페이지는 정기적으로 업데이트됩니다. 추가 업데이트가 있는지 다시 확인하세요.

> [!Note]
>Intune에 대해 다음 변경 사항을 개발 중입니다. 새로운 하이브리드 기능에 대한 자세한 내용은 [hybrid What’s New page](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management)(하이브리드 새로운 기능 페이지)를 참조하세요.

<!--

## What's coming to Intune on the Azure portal  
## What's coming to Intune apps
## Notices

-->



## <a name="whats-coming-to-intune-on-the-azure-portal"></a>Azure Portal의 Intune에 향후 포함될 예정인 기능

### <a name="easier-installation-of-office-365-apps-----1121362----"></a>Office 365 앱의 간편한 설치 <!--- 1121362 --->
새 **Office 365 ProPlus** 앱 유형을 통해 최신 버전의 Windows 10을 실행하는, 관리하는 장치에 Office 365 ProPlus 앱을 쉽게 할당할 수 있습니다. 또한 라이선스가 있는 경우 Microsoft Project 및 Microsoft Visio를 설치할 수 있습니다. 원하는 앱이 모두 번들로 묶여 Intune 콘솔의 앱 목록에 하나의 앱으로 표시됩니다.
 

### <a name="new-device-action-to-force-devices-to-sync-with-intune----711369---"></a>장치가 Intune과 동기화되도록 강제하는 새 장치 작업 <!-- 711369 -->    
선택한 장치가 Intune을 사용하여 즉시 체크 인하도록 강제하는 새 장치 작업이 추가되었습니다. 장치가 체크 인하면 장치에 할당된 보류 중인 작업 또는 정책을 즉시 받게 됩니다.  이 작업을 사용하면 예약된 다음 체크 인을 기다리지 않고 즉시 할당한 정책의 유효성을 검사하고 문제를 해결할 수 있습니다.

### <a name="actions-for-non-compliance----730266--"></a>비준수에 대한 작업 <!--730266-->     
*비준수에 대한 작업*은 정책을 준수하지 않는 장치에 조치를 취할 수 있는 준수 정책의 새로운 기능입니다. 단일 또는 여러 작업을 지정할 수 있으며, 이러한 작업이 수행되어야 하는 기간을 지정할 수 있습니다. 예를 들어 장치가 메일을 통해 비준수 상태가 된 직후에 사용자에게 비준수 장치를 알리거나 조건부 액세스를 통해 3일 유예 기간이 지난 후 비준수 장치가 회사 리소스에 액세스하는 것을 못하도록 차단할 수 있습니다.

### <a name="new-app-configuration-settings-for-the-intune-managed-browser-----682951----"></a>Intune Managed Browser에 대한 새로운 앱 구성 설정 <!--- 682951 --->
Intune Managed Browser 앱에 대한 구성이 더 추가될 예정입니다. 그러면 앱 구성 정책을 사용하여 브라우저의 책갈피와 기본 홈 페이지를 구성할 수 있습니다.

### <a name="restrict-android-and-ios-device-enrollment-restriction-by-os-version------1333256--1245463----"></a>OS 버전별 Android 및 iOS 장치 등록 제한 <!--- 1333256,  1245463 --->  
이제 Intune에서 운영 체제 버전 번호로 iOS 및 Android 등록을 제한하는 기능을 지원합니다. 이제 IT 관리자가 **Intune** > **등록 제한** > **장치 유형 제한** > **기본값** > **플랫폼 제한**에서 플랫폼 구성을 설정하여 최소 및 최대 운영 체제 값 사이로 등록을 제한할 수 있습니다. Android 운영 체제 버전은 Major.Minor.Build.Rev로 지정해야 하며, 여기서 Build 및 Rev는 선택 사항입니다. iOS 버전을 Major.Minor.Build로 지정해야 하며, 여기서 Build는 선택 사항입니다.

>[!NOTE]
>이 설정은 Apple 장비 등록 프로그램과 Apple School Manager 또는 Apple Configurator를 포함하는 Apple 등록 프로그램을 통한 등록을 제한하지 않습니다.

### <a name="restrict-android-ios-and-macos-device-personally-owned-device-enrollment------1333272--1333275-1245709----"></a>Android, iOS 및 macOS 장치에 대한 개인 소유 장치 등록 제한 <!--- 1333272,  1333275, 1245709 --->
이제 Intune에서 장치 일련 번호를 사용하여 iOS, Android 및 macOS에 대한 개인 소유 장치 등록을 제한하는 기능을 지원합니다. 일부 장치는 일련 번호를 보고하지 않습니다. 자세한 내용은 장치 제조업체에 문의하세요. 일련 번호를 Intune에 업로드하면 장치를 회사 소유로 미리 선언할 수 있습니다. 등록 제한을 사용하여 개인 소유(BYOD) 장치를 차단하고 회사 소유 장치에 대해서만 등록을 허용할 수 있습니다.

Intune 포털에서 일련 번호를 가져오려면 **장치 등록** > **회사 장치 식별자**로 이동한 다음 **추가**를 클릭하고 .CSV 파일(헤더 없음, 일련 번호와 IMEI 번호 등의 세부 정보를 위한 두 개의 열)을 업로드합니다.  개인 소유 장치를 제한하려면 **장치 등록** > **등록 제한**으로 이동합니다. **장치 유형 제한**에서 **기본값**을 선택한 다음 **플랫폼 구성**을 선택합니다. iOS, Android 및 macOS에 대해 개인 소유 장치를 **허용** 또는 **차단**할 수 있습니다. 

### <a name="force-supervised-ios-devices-to-automatically-install-the-latest-available-software-update----777100---"></a>감독된 iOS 장치에서 사용 가능한 최신 소프트웨어 업데이트를 자동으로 설치하도록 강제 <!-- 777100 -->   
감독된 iOS 장치에서 사용 가능한 최신 소프트웨어 업데이트를 자동으로 설치하도록 강제할 수 있는 소프트웨어 업데이트 작업 영역에서 새 정책을 사용할 수 있습니다. 이전 버전이 있는 iOS 장치 및 만료된 이유에 대한 요약이 나열된 새 보고서를 볼 수도 있습니다.

### <a name="new-settings-to-allow-and-block-apps-on-samsung-knox-standard-devices-----822899--1305423--"></a>Samsung KNOX Standard 장치에서 앱을 허용 및 차단하는 새로운 설정 <!-- 822899,  1305423-->   
다음 앱 목록을 지정할 수 있는 새로운 [장치 제한 설정](device-restrictions-android.md)이 추가되었습니다.
  - 사용자 설치가 허용된 앱
  - 사용자 실행이 차단된 앱
  - 장치에서 사용자로부터 숨겨진 앱  

URL, 패키지 이름 또는 관리하는 앱 목록을 통해 앱을 지정할 수 있습니다.

### <a name="android-for-work-support-for-lookout----1087312---"></a>Android for Work의 Lookout 지원 <!-- 1087312 -->   
Lookout for Work 앱 사용 시 Lookout이 설치된 Intune 커넥터가Android for Work 장치를 지원할 예정입니다. 그러면 컨테이너 내부 또는 외부에서 Lookout 앱을 배포할 수 있습니다.


### <a name="check-point-sandblast-mobile---new-mobile-threat-defense-partner-----954651--and--1172027----"></a>Check Point SandBlast Mobile - 새 Mobile Threat Defense 파트너 <!-- 954651  and  1172027 ? -->  
Microsoft Intune과 통합된 Mobile Threat Defense 솔루션인 Check Point SandBlast Mobile에서 수행한 위험 평가에 따라 조건부 액세스를 사용하여 회사 리소스에 대한 모바일 장치 액세스를 제어할 수 있습니다.

#### <a name="how-integration-with-intune-works"></a>Intune과 통합은 어떻게 작동하나요?
Check Point SandBlast Mobile을 실행하는 장치에서 수집된 원격 분석에 따라 위험이 평가됩니다. Intune 장치 준수 정책을 통해 사용하도록 설정된 Check Point SandBlast Mobile 위험 평가에 따라 EMS 조건부 액세스 정책을 구성할 수 있습니다. 검색된 위협에 따라 회사 리소스에 대한 비규격 장치 액세스를 허용하거나 차단할 수 있습니다.

### <a name="zimperium---new-mobile-threat-defense-partner------954681---"></a>Zimperium - 새 Mobile Threat Defense 파트너 <!-- 954681 -->
Microsoft Intune과 통합된 Mobile Threat Defense 솔루션인 Zimperium에서 수행한 위험 평가에 따라 조건부 액세스를 사용하여 회사 리소스에 대한 모바일 장치의 액세스를 제어할 수 있습니다.

#### <a name="how-integration-with-intune-works"></a>Intune과 통합은 어떻게 작동하나요?
위험은 Zimperium을 실행하는 장치에서 수집된 원격 분석에 따라 평가됩니다. Intune 장치 준수 정책을 통해 사용하도록 설정된 Zimperium 위험 평가에 따라 EMS 조건부 액세스 정책을 구성할 수 있습니다. 이 정책을 사용하여 회사 리소스에 액세스하는 미준수 장치를 감지된 위협에 따라 허용하거나 차단할 수 있습니다.

### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>온-프레미스 Exchange Connector 고가용성 지원 <!-- 676614 -->   
온-프레미스 Exchange Connector에 대해 여러 CAS(클라이언트 액세스 서버) 역할을 사용할 수 있습니다. 예를 들어 주 CA에서 오류가 발생할 경우 Exchange Connector는 다른 CAS로 대체하기 위한 쿼리를 수신합니다. 이 기능은 서비스가 중단되지 않도록 합니다.

### <a name="system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>Exchange Connector용 System Center Operations Manager 관리 팩 <!-- 885457 -->   
Exchange Connector 로그를 구문 분석하는 데 도움이 되도록 Exchange Connector용 System Center Operations Manager 관리 팩이 제공될 예정입니다. 그러면 문제를 해결해야 할 때 Intune을 다른 방식으로 모니터링할 수 있습니다.

### <a name="conditional-access-support-for-mac-devices-----720172---"></a>Mac 장치에 대한 조건부 액세스 지원 <!-- 720172 -->   
Mac 장치를 Intune에 등록하고 해당 장치 준수 정책을 준수하도록 요구하는 조건부 액세스 정책을 곧 설정할 수 있게 됩니다. 예를 들어 사용자가 macOS용 Intune 회사 포털 앱을 다운로드하고 해당 Mac 장치를 Intune에 등록할 수 있습니다. Intune은 Mac 장치가 PIN, 암호화, OS 버전, 시스템 무결성 등의 요구 사항을 준수하는지 여부를 평가합니다.

### <a name="end-of-support-for-ios-80----1164477---"></a>iOS 8.0에 대한 지원 종료 <!---1164477--->
관리되는 앱 및 iOS용 회사 포털 앱이 회사 리소스에 액세스하려면 iOS 9.0 이상이 필요합니다. 올해 9월 이전에 업데이트되지 않은 장치는 회사 포털 또는 해당 앱에 더 이상 액세스할 수 없게 됩니다. 12월에는 메일을 포함한 회사 리소스에 대한 모든 액세스가 차단됩니다. 

### <a name="end-of-support-for-android-43-and-lower----1171127---"></a>Android 4.3 및 이전 버전에 대한 지원 종료 <!---1171127--->
관리되는 앱과 Android용 회사 포털 앱이 회사 리소스에 액세스하려면 Android 4.4 이상이 필요합니다. 10월 이전에 업데이트되지 않은 장치는 회사 포털 또는 해당 앱에 더 이상 액세스할 수 없습니다. 12월에는 등록된 모든 장치의 사용이 강제로 중단되어 회사 리소스에 액세스할 수 없게 됩니다. MDM 없이 앱 보호 정책을 사용하는 경우 앱에 업데이트가 수신되지 않으며 시간이 지남에 따라 경험의 품질이 저하됩니다.





### <a name="platform-support-reminder-windows-phone-81-mainstream-support-will-end-july-11-2017----1327781---"></a>플랫폼 지원 미리 알림: Windows Phone 8.1 기본 지원이 2017년 7월 11일에 종료됨 <!-- 1327781 -->  
2017년 7월 11일에 Windows Phone 8.1 플랫폼의 기본 지원이 종료됩니다. Windows 8.1 PC 지원은 영향을 받지 않습니다.

Intune 서비스에서 관리되는 Windows Phone 8.1 장치에 대한 즉각적인 영향은 없습니다. 등록된 장치는 계속 작동하며 모든 정책, 구성 및 앱이 계속해서 예상대로 작동합니다. Intune 서비스 내의 Windows Phone 8.1 플랫폼과 Windows Phone 8.1 회사 포털 앱을 대상으로 하는 향상된 기능은 없습니다.

가능하면 빨리 해당 Windows Phone 8.1 장치를 Windows 10 Mobile로 업그레이드하는 것이 좋습니다. 




## <a name="whats-coming-to-intune-apps"></a>Intune 앱에 향후 포함될 예정인 기능

### <a name="improved-sign-in-experience-across-company-portal-apps-for-all-platforms---user-story-1132123--"></a>모든 플랫폼에 대해 회사 포털 앱 전체에서 로그인 환경 개선됨 <!--User Story 1132123-->    
Android, iOS 및 Windows용 Intune 회사 포털 앱에 대한 로그인 환경을 개선하게 될 향후 몇 개월 내에 제공될 변경이 있음을 알려드립니다. Azure AD에서 이 변경 내용을 적용할 경우 회사 포털 앱에 대한 모든 플랫폼에서 새로운 사용자 환경이 자동으로 나타나게 됩니다. 또한 사용자가 이제 생성된 일회용 코드를 사용하여 다른 장치에서 회사 포털에 로그인할 수도 있습니다. 이 기능은 사용자가 자격 증명 없이 로그인해야 할 경우에 특히 유용합니다.

이전 로그인 환경, 자격 증명을 사용하는 새 로그인 환경, 그리고 다른 장치로부터의 새 로그인 환경에 대한 스크린샷은 [앱 UI의 새로운 기능](whats-new-app-ui.md) 페이지에서 볼 수 있습니다.

### <a name="light-and-dark-modes-available-for-the-company-portal-app-for-windows-10----676547---"></a>Windows 10용 회사 포털 앱에 밝은 모드와 어두운 모드를 사용할 수 있음 <!---676547--->
최종 사용자가 Windows 10용 회사 포털 앱에 대한 색 모드를 사용자 지정할 수 있게 됩니다. 사용자는 회사 포털 앱의 설정 섹션에서 변경할 수 있습니다. 사용자가 앱을 다시 시작하면 변경 내용이 표시됩니다. Windows 10 버전 1607 이상에서는 앱 모드가 기본적으로 시스템 설정으로 지정됩니다. Windows 10 버전 1511 및 이전 버전을 실행하는 데스크톱에서는 앱 모드가 기본적으로 밝은 모드로 설정됩니다.

### <a name="enable-end-users-to-tag-their-device-group-in-the-company-portal-app-for-windows-10----807046--"></a>최종 사용자가 Windows 10용 회사 포털 앱에서 장치 그룹에 태그를 지정하도록 허용 <!---807046-->    
최종 사용자가 Windows 10용 회사 포털 앱 내에서 직접 태그를 지정하여 장치가 속하는 그룹을 선택할 수 있게 됩니다.

### <a name="allow-end-users-to-access-the-company-portal-app-for-android-without-enrollment----1169910---"></a>최종 사용자가 등록 없이 Android용 회사 포털 앱에 액세스하도록 허용 <!---1169910--->  
머지 않아 최종 사용자가 장치를 등록하지 않고도 Android용 회사 포털 앱에 액세스할 수 있게 됩니다. 앱 보호 정책을 사용하는 조직의 최종 사용자는 회사 포털 앱을 열 때 장치를 등록하라는 메시지를 더 이상 받지 않습니다. 최종 사용자가 장치를 등록하지 않고 회사 포털에서 앱을 설치할 수도 있습니다. 

### <a name="users-who-are-signed-in-to-exchange-can-automatically-access-the-company-portal-website-on-windows-10-devices---1323204--"></a>Exchange에 로그인한 사용자는 Windows 10 장치에서 회사 포털 웹 사이트에 자동으로 액세스할 수 있음 <!--1323204-->  
Exchange에 이미 인증된 Windows 10 사용자는 조건부 액세스 격리 메일 받고 메일의 링크를 클릭할 경우 회사 액세스 설정을 시작하기 전에 더 이상 브라우저에서 다시 인증할 필요가 없습니다.


## <a name="notices"></a>알림

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple의 Application Transport Security 업데이트 요구 <!--748318-->   
Apple에서는 2017년 봄부터 ATS(Application Transport Security)에 대한 특정 요구 사항을 적용할 것이라고 발표했습니다. ATS는 HTTPS를 통한 모든 앱 통신에서 보다 엄격한 보안을 적용하는 데 사용됩니다. 이 변경 사항은 iOS 회사 포털 앱을 사용하는 Intune 고객에게 영향을 줍니다. 자세한 내용은 [Intune 지원 블로그](https://aka.ms/compportalats)를 참조하세요.

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Apple 등록 시나리오에 대한 직접 액세스 <!--951869-->   
2017년 1월 이후에 만든 Intune 계정은 Azure Preview 포털에서 장치 등록 워크로드를 사용하여 Apple 등록 시나리오에 직접 액세스할 수 있습니다. 이전에는 클래식 Intune 포털의 링크를 통해서만 Apple 등록 미리 보기에 액세스할 수 있었습니다. 2017년 1월 이전에 만든 Intune 계정은 일회성 마이그레이션을 수행해야 Azure에서 이러한 기능을 사용할 수 있습니다. 마이그레이션 일정은 아직 공지되지 않았지만 가능한 한 빠른 시일 내에 세부 정보가 제공될 예정입니다. 기존 계정에서 미리 보기에 액세스할 수 없는 경우 평가판 계정을 만들어 새로운 경험을 테스트해 보는 것이 좋습니다.

### <a name="plan-for-change-intune-is-changing-the-intune-partner-portal-experience----1050016---"></a>변경 계획: Intune의 Intune 파트너 포털 환경 변화 <!-- 1050016 -->
2017년 5월 중순의 서비스 업데이트부터 manage.microsoft.com에서 Intune 파트너 페이지가 제거됩니다.  

파트너 관리자인 경우 더 이상 Intune 파트너 페이지에서 고객을 대신하여 작업을 보고 수행할 수 없지만, 대신 Microsoft의 다른 두 파트너 포털 중 하나에서 로그인해야 합니다.

[Microsoft 파트너 센터](https://partnercenter.microsoft.com/) 및 [Microsoft Office 365 파트너 관리 센터](https://portal.office.com/)를 통해, 관리하는 고객 계정에 로그인할 수 있습니다. 파트너로서 앞으로는 이러한 사이트 중 하나를 사용하여 고객을 관리하세요.



### <a name="see-also"></a>참고 항목
최근 개발 작업에 대한 자세한 내용은 [Microsoft Intune의 새로운 기능](whats-new.md)을 참조하세요.
