---
title: "Microsoft Intune의 새로운 기능"
titleSuffix: Intune on Azure
description: "Intune Azure 포털의 새로운 기능 알아보기"
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 08/10/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f915c805b20e88c661ad52e280a31054bbebce02
ms.sourcegitcommit: 2ed8d1c39d4b3e3282111f1d758afb3a50f19f8f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/10/2017
---
# <a name="whats-new-in-microsoft-intune"></a>Microsoft Intune의 새로운 기능

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

매주 Microsoft Intune에 추가되는 새로운 기능에 대해 알아봅니다. [예정된 변경](#whats-coming), 서비스 관련 [중요 공지](#notices) 및 [이전 릴리스](whats-new-archive.md) 관련 정보에 대해서도 알아볼 수 있습니다.

> [!Note]
> 이러한 기능 중 대다수는 최종적으로 Configuration Manager를 사용하는 하이브리드 배포용으로 지원될 예정입니다. 새로운 하이브리드 기능에 대한 자세한 내용은 [hybrid What’s New page](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management)(하이브리드 새로운 기능 페이지)를 참조하세요.


<!-- Common categories:  
  ### Role-based access control
  ### Device enrollment
  ### Device management
  ### App management
  ### Device configuration
  ### Intune apps
-->   

## <a name="week-of-july-31-2017"></a>2017년 7월 31일 주

### <a name="device-enrollment"></a>장치 등록  

#### <a name="restrict-android-and-ios-device-enrollment-restriction-by-os-version------1333256--1245463----"></a>OS 버전별 Android 및 iOS 장치 등록 제한 <!--- 1333256,  1245463 --->
이제 Intune에서 운영 체제 버전 번호로 iOS 및 Android 등록을 제한하는 기능을 지원합니다. IT 관리자는 **장치 유형 제한** 아래에서 최소 운영 체제 값과 최대 운영 체제 값 사이의 범위에서 등록을 제한하는 플랫폼 구성을 설정할 수 있습니다. Android 운영 체제 버전은 Major.Minor.Build.Rev로 지정해야 하며 여기서 Minor, Build, Rev는 선택 사항입니다. iOS 버전을 Major.Minor.Build로 지정해야 하며, 여기서 Minor와 Build는 선택 사항입니다. [장치 등록 제한 사항](enrollment-restrictions-set.md)에 대해 자세히 알아보세요.

>[!NOTE]
>Apple 등록 프로그램이나 Apple Configurator를 통해 등록을 제한하지 않습니다.

#### <a name="restrict-android-ios-and-macos-device-personally-owned-device-enrollment------1333272--1333275-1245709----"></a>Android, iOS 및 macOS 장치에 대한 개인 소유 장치 등록 제한 <!--- 1333272,  1333275, 1245709 --->
Intune은 회사 장치 IMEI 번호를 화이트 리스트에 등록하여 개인 장치 등록을 제한할 수 있습니다. 이제 이 기능이 iOS, Android 및 macOS에서 장치 일련 번호를 사용하는 방법으로 확장되었습니다. 일련 번호를 Intune에 업로드하면 장치를 회사 소유로 미리 선언할 수 있습니다. 등록 제한을 사용하여 개인 소유(BYOD) 장치를 차단하고 회사 소유 장치에 대해서만 등록을 허용할 수 있습니다. [장치 등록 제한 사항](enrollment-restrictions-set.md)에 대해 자세히 알아보세요.

일련 번호를 가져오려면 **장치 등록** > **회사 장치 식별자**로 이동한 다음 **추가**를 클릭하고 .CSV 파일(헤더 없음, 일련 번호와 IMEI 번호 등의 세부 정보를 위한 두 개의 열)을 업로드합니다.  개인 소유 장치를 제한하려면 **장치 등록** > **등록 제한**으로 이동합니다. **장치 유형 제한**에서 **기본값**을 선택한 다음 **플랫폼 구성**을 선택합니다. iOS, Android 및 macOS에 대해 개인 소유 장치를 **허용** 또는 **차단**할 수 있습니다. 


### <a name="device-management"></a>장치 관리   

#### <a name="new-device-action-to-force-devices-to-sync-with-intune----711369---"></a>장치가 Intune과 동기화되도록 강제하는 새 장치 작업 <!-- 711369 -->
이번 릴리스에서는 선택한 장치가 Intune을 사용하여 즉시 체크 인하도록 강제하는 새 장치 작업이 추가되었습니다. 장치가 체크 인하면 장치에 할당된 보류 중인 작업 또는 정책을 즉시 받게 됩니다.  이 작업을 사용하면 예약된 다음 체크 인을 기다리지 않고 즉시 할당한 정책의 유효성을 검사하고 문제를 해결할 수 있습니다.
자세한 내용은 [장치 동기화](device-sync.md)를 참조하세요.

#### <a name="force-supervised-ios-devices-to-automatically-install-the-latest-available-software-update----777100---"></a>감독된 iOS 장치에서 사용 가능한 최신 소프트웨어 업데이트를 자동으로 설치하도록 강제 <!-- 777100 -->
감독된 iOS 장치에서 사용 가능한 최신 소프트웨어 업데이트를 자동으로 설치하도록 강제할 수 있는 소프트웨어 업데이트 작업 영역에서 새 정책을 사용할 수 있습니다. 자세한 내용은 [iOS 업데이트 정책 구성](/intune/software-updates-ios)을 참조하세요.


#### <a name="check-point-sandblast-mobile---new-mobile-threat-defense-partner-----954651-1172027---"></a>Check Point SandBlast Mobile - 새 Mobile Threat Defense 파트너 <!-- 954651, 1172027 -->
Microsoft Intune과 통합된 Mobile Threat Defense 솔루션인 Checkpoint SandBlast Mobile에서 수행한 위험 평가에 따라 조건부 액세스를 사용하여 회사 리소스에 대한 모바일 장치 액세스를 제어할 수 있습니다.

##### <a name="how-integration-with-intune-works"></a>Intune과 통합은 어떻게 작동하나요?
Checkpoint SandBlast Mobile을 실행하는 장치에서 수집된 원격 분석에 따라 위험이 평가됩니다. Intune 장치 준수 정책을 통해 사용하도록 설정된 Checkpoint SandBlast Mobile 위험 평가에 따라 EMS 조건부 액세스 정책을 구성할 수 있습니다. 검색된 위협에 따라 회사 리소스에 대한 비규격 장치 액세스를 허용하거나 차단할 수 있습니다.


### <a name="app-management"></a>앱 관리

#### <a name="deploy-an-app-as-available-in-the-microsoft-store-for-business----748101---"></a>비즈니스용 Microsoft 스토어에서 사용 가능한 앱 배포 <!-- 748101 -->
이번 릴리스에서는 관리자가 비즈니스용 Microsoft 스토어를 사용 가능으로 할당할 수 있습니다. 사용 가능으로 할당하면 최종 사용자는 Microsoft 스토어로 리디렉션 없이 회사 포털 앱이나 웹 사이트에서 앱을 설치할 수 있습니다.


### <a name="intune-apps"></a>Intune 앱  

#### <a name="ui-updates-to-the-company-portal-website---1313244-part-1--"></a>회사 포털 웹 사이트의 UI 업데이트 <!--1313244 part 1-->
최종 사용자 경험을 향상시키기 위해 [회사 포털 웹 사이트](https://portal.manage.microsoft.com)의 UI를 여러 개 업데이트했습니다.

- __앱 타일 향상__ 앱 아이콘을 감지할 수 없는 경우 아이콘이 아이콘의 주요 색상을 기반으로 자동 생성된 배경과 함께 표시됩니다. 해당되는 경우 이 배경이 이전에 앱 타일에 표시된 회색 테두리를 대체합니다.

    회사 포털 웹 사이트는 향후 릴리스에서 가능하면 큰 아이콘을 표시합니다. IT 관리자가 최소 크기가 120x120픽셀인 고해상도 아이콘을 사용하여 앱을 게시하는 것이 좋습니다. 

- __탐색 변경 내용__: 탐색 모음 항목이 왼쪽 상단에 있는 햄버거 메뉴로 이동되었습니다. 범주 페이지가 제거되었습니다. 이제 사용자가 찾아보는 동안 범주별로 콘텐츠를 필터링할 수 있습니다.

- __추천 앱 업데이트__ 사용자가 추천하기 위해 선택한 앱을 찾아볼 수 있는 사이트에 전용 페이지를 추가하고 홈페이지의 추천 섹션에서 UI를 일부 조정했습니다.

#### <a name="ibooks-support-for-the-company-portal-website---1231841--"></a>회사 포털 웹 사이트에 대한 iBooks 지원<!--1231841-->
사용자가 iBooks를 찾고 다운로드할 수 있도록 회사 포털 웹 사이트에 전용 페이지를 추가했습니다. 

### <a name="reporting"></a>보고

#### <a name="intune-data-warehouse-public-preview"></a>Intune 데이터 웨어하우스(공개 미리 보기)

Intune 데이터 웨어하우스 샘플 데이터는 테넌트에 대한 과거 보기를 제공합니다. 여러 분석 도구와 호환 가능한 OData 링크인 Power BI 파일(PBIX)을 사용하거나 REST API를 사용하여 데이터에 액세스할 수 있습니다. 자세한 내용은 [Intune 데이터 웨어하우스 사용](reports-nav-create-intune-reports.md)을 참조하세요.


## <a name="week-of-july-23rd-2017"></a>2017년 7월 23일 주

### <a name="light-and-dark-modes-available-for-the-company-portal-app-for-windows-10----676547---"></a>Windows 10용 회사 포털 앱에 밝은 모드와 어두운 모드를 사용할 수 있음 <!---676547--->
최종 사용자가 Windows 10용 회사 포털 앱에 대한 색 모드를 사용자 지정할 수 있게 됩니다. 사용자는 회사 포털 앱의 설정 섹션에서 변경할 수 있습니다. 사용자가 앱을 다시 시작하면 변경 내용이 표시됩니다. Windows 10 버전 1607 이상에서는 앱 모드가 기본적으로 시스템 설정으로 지정됩니다. Windows 10 버전 1511 이상에서는 앱 모드가 기본적으로 밝은 모드로 설정됩니다.

### <a name="enable-end-users-to-tag-their-device-group-in-the-company-portal-app-for-windows-10----807046--"></a>최종 사용자가 Windows 10용 회사 포털 앱에서 장치 그룹에 태그를 지정하도록 허용 <!---807046-->
이제 최종 사용자가 Windows 10용 회사 포털 앱 내에서 직접 태그를 지정하여 장치가 속하는 그룹을 선택할 수 있게 됩니다.




## <a name="notices"></a>알림

### <a name="ip-addresses-for-intune-updated----1175274---"></a>Intune의 IP 주소가 업데이트됨 <!-- 1175274 -->
방화벽 프록시 설정에 대해 [DNS 이름 및 IP 주소의 업데이트된 목록](/intune/network-bandwidth-use)이 제공됩니다.

### <a name="use-azure-active-directory-for-conditional-access----967947---"></a>조건부 액세스에 Azure Active Directory 사용 <!-- 967947 -->
Azure 콘솔의 Azure Active Directory 섹션에서 제공되는 조건부 액세스 기능은 Office 365 Exchange Online, SharePoint Online 등의 클라우드 앱에 대해 정책을 설정하기 위한 보다 강력하고 유연한 프레임워크를 제공합니다.  클래식 Intune 콘솔 대신 **Azure Active Directory의 조건부 액세스** 블레이드를 사용하여 정책을 구성할 수 있습니다. 클래식 Intune 콘솔의 기존 정책은 Azure 콘솔에서 다시 만들어야 합니다. 자세한 내용은 [Azure AD 조건부 액세스 정책 만들기](/intune/conditional-access-exchange-create.md#create-azure-ad-conditional-access-policies-in-intune-azure-preview)를 참조하세요.

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Apple 등록 시나리오에 대한 직접 액세스 <!--951869-->
2017년 1월 이후에 만든 Intune 계정은 Azure 포털에서 장치 등록 워크로드를 사용하여 Apple 등록 시나리오에 직접 액세스할 수 있습니다. 이전에는 클래식 Intune 포털의 링크를 통해서만 Apple 등록 미리 보기에 액세스할 수 있었습니다. 2017년 1월 이전에 만든 Intune 계정은 일회성 마이그레이션을 수행해야 Azure에서 이러한 기능을 사용할 수 있습니다. 마이그레이션 일정은 아직 공지되지 않았지만 가능한 한 빠른 시일 내에 세부 정보가 제공될 예정입니다. 기존 계정에서 Azure 포털에 액세스할 수 없는 경우 평가판 계정을 만들어 새로운 환경을 테스트해 보는 것이 좋습니다.

### <a name="administration-roles-being-replaced-in-azure-portal"></a>Azure Portal에서 대체되는 관리 역할
Intune 클래식 포털(Silverlight)에서 사용된 기존 MAM(모바일 응용 프로그램 관리) 관리 역할(참가자, 소유자 및 읽기 전용)은 Intune Azure Portal에서 새로운 RBAC(역할 기반 관리 제어)의 전체 집합으로 대체됩니다. Azure Portal로 마이그레이션한 후에 이러한 새 관리 역할에 관리자를 다시 할당해야 합니다. RBAC 및 새 역할에 대한 자세한 내용은 [Microsoft Intune에 대한 역할 기반 액세스 제어](/intune/role-based-access-control)를 참조하세요.



## <a name="whats-coming"></a>향후 예정 사항

### <a name="end-of-support-for-ios-80----1164477---"></a>iOS 8.0에 대한 지원 종료 <!---1164477--->
관리되는 앱 및 iOS용 회사 포털 앱이 회사 리소스에 액세스하려면 iOS 9.0 이상이 필요합니다. 올해 9월 이전에 업데이트되지 않은 장치는 회사 포털 또는 해당 앱에 더 이상 액세스할 수 없게 됩니다. 

### <a name="ui-updates-to-the-company-portal-website---1313244-part-2--"></a>회사 포털 웹 사이트의 UI 업데이트 <!--1313244 part 2-->
__추천 앱 업데이트__  
사용자가 추천하기 위해 선택한 앱을 찾아볼 수 있는 사이트에 전용 페이지를 추가하고 홈페이지의 추천 섹션에서 UI를 일부 조정했습니다. 이러한 변경 내용은 [앱 UI의 새로운 기능](whats-new-app-ui.md) 페이지에서 확인할 수 있습니다.


### <a name="end-of-support-for-android-43-and-lower----1171127-1326920----"></a>Android 4.3 및 이전 버전에 대한 지원 종료 <!---1171127, 1326920 --->
관리되는 앱과 Android용 회사 포털 앱이 회사 리소스에 액세스하려면 Android 4.4 이상이 필요합니다. 10월이 시작되기 전에 업데이트되지 않은 장치는 더 이상 회사 포털 또는 이러한 앱에 액세스할 수 없습니다. 12월까지 등록된 모든 장치는 12월에 강제 사용 중지되며, 따라서 회사 리소스에 액세스할 수 없게 됩니다. MDM 없이 앱 보호 정책을 사용 중인 경우 앱이 업데이트를 받지 못하며 해당 환경 품질이 시간이 흐름에 따라 저하됩니다.


### <a name="platform-support-reminder-windows-phone-81-mainstream-support-ended-july-11-2017"></a>플랫폼 지원 알림: Windows Phone 8.1 기본 지원은 2017년 7월 11일에 종료됩니다.
<!-- 1327781 -->
2017년 7월 11부터 Windows Phone 8.1 플랫폼 기본 지원이 종료됩니다. Windows 8.1 PC 지원은 영향을 받지 않습니다.

Intune 서비스에서 관리되는 Windows Phone 8.1 장치에 대한 즉각적인 영향은 없습니다. 등록된 장치는 계속 작동하며 모든 정책, 구성 및 앱이 계속해서 예상대로 작동합니다. Intune 서비스 내의 Windows Phone 8.1 플랫폼과 Windows Phone 8.1 회사 포털 앱을 대상으로 하는 향상된 기능은 없습니다.

가능하면 빨리 해당 Windows Phone 8.1 장치를 Windows 10 Mobile로 업그레이드하는 것이 좋습니다. 

### <a name="changes-in-support-for-the-intune-ios-company-portal-app-----1164474----"></a>Intune iOS 회사 포털 앱에 대한 지원 변경 내용 <!-- 1164474  -->
iOS 9.0 이상을 실행하는 장치만 지원하는 iOS용 Microsoft Intune 회사 포털 앱의 새로운 버전이 곧 제공될 예정입니다. iOS 8을 지원하는 회사 포털 버전도 매우 짧은 시간 동안 사용할 수 있습니다. 그러나 MAM 지원 iOS 앱을 사용하는 경우 iOS 9.0 이상이 지원되므로 최종 사용자가 최신 OS로 업데이트하도록 하는 것이 좋습니다. 

#### <a name="how-does-this-affect-me"></a>이 변경 사항은 어떤 영향을 미치나요?
구체적인 날짜를 모르고 이 내용을 미리 알려드리는 것은 계획할 시간을 드리기 위해서입니다. 사용자가 iOS 9 이상으로 업데이트되도록 하고, 회사 포털 앱이 릴리스되면 최종 사용자에게 회사 포털 앱을 업데이트하도록 요청하세요.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>이러한 변경에 대해 준비하려면 어떻게 해야 하나요?
사용자에게 iOS 9.0 이상으로 업데이트하여 Intune의 새로운 기능을 완전히 활용하도록 권유합니다.  사용자에게 새 버전의 회사 포털을 설치하여 제공되는 새로운 기능을 활용하도록 권유합니다.

Azure Portal의 Intune으로 이동한 다음 장치 > 모든 장치에서 iOS 버전별로 필터링하여 iOS 9 이전 운영 체제를 사용하는 현재 장치를 모두 확인합니다.

### <a name="plan-for-change-intune-is-changing-the-intune-partner-portal-experience----1050016---"></a>변경 계획: Intune의 Intune 파트너 포털 환경 변화 <!-- 1050016 -->
2017년 5월 중순의 서비스 업데이트부터 manage.microsoft.com에서 Intune 파트너 페이지가 제거됩니다.  

파트너 관리자인 경우 더 이상 Intune 파트너 페이지에서 고객을 대신하여 작업을 보고 수행할 수 없지만, 대신 Microsoft의 다른 두 파트너 포털 중 하나에서 로그인해야 합니다.

[Microsoft 파트너 센터](https://partnercenter.microsoft.com/) 및 [Microsoft Office 365 파트너 관리 센터](https://portal.office.com/)를 통해, 관리하는 고객 계정에 로그인할 수 있습니다. 파트너로서 앞으로는 이러한 사이트 중 하나를 사용하여 고객을 관리하세요.


### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple의 Application Transport Security 업데이트 요구 <!--748318-->
Apple에서는 ATS(Application Transport Security)에 대한 특정 요구 사항을 적용할 것이라고 발표했습니다. ATS는 HTTPS를 통한 모든 앱 통신에서 보다 엄격한 보안을 적용하는 데 사용됩니다. 이 변경 사항은 iOS 회사 포털 앱을 사용하는 Intune 고객에게 영향을 줍니다.

새로운 ATS 요구 사항을 적용하는 Apple TestFlight 프로그램을 통해 iOS용 회사 포털 앱 버전을 제공했습니다. ATS 준수를 테스트하는 데 이 버전을 사용해 보려면 이름, 성, 메일 주소, 회사 이름을 포함하여 <a href="mailto:CompanyPortalBeta@microsoft.com?subject=Register to TestFlight ATS Company Portal app">CompanyPortalBeta@microsoft.com</a>에 메일을 보내 주세요. 자세한 내용은 [Intune 지원 블로그](https://aka.ms/compportalats)를 참조하세요.

### <a name="see-also"></a>참고 항목
* [Microsoft Intune 블로그](http://go.microsoft.com/fwlink/?LinkID=273882)
* [클라우드 플랫폼 로드맵](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [What's new in the Company Portal UI](whats-new-app-ui.md)(회사 포털 UI의 새로운 기능)
* [지난 달의 새로운 기능](whats-new-archive.md)
