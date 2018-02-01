---
title: "지난 달의 새로운 Microsoft Intune 기능"
titlesuffix: Azure portal
description: "Intune 새로운 기능 페이지에서 이전 공지 사항 검토"
keywords: 
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9ba01d60-4a03-4e3e-9aba-8be905c0054c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0d6513b570851473651fbfa38dbb4dc1b6c91036
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2018
---
# <a name="whats-new-in-the-microsoft-intune---previous-months"></a>Microsoft Intune의 새로운 기능 - 지난 달

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="september-2017"></a>2017년 9월

### <a name="inform-end-users-what-device-information-can-be-seen-for-ios---739894--"></a>iOS에 대해 표시되는 장치 정보를 최종 사용자에게 알리기 <!--739894-->

iOS용 회사 포털 앱에서 장치 세부 정보 화면에 **소유권 형식**을 추가했습니다. 이를 통해 사용자는 Intune 최종 사용자 문서의 이 페이지에서 바로 개인 정보에 대한 자세한 내용을 찾을 수 있습니다. 정보 화면에서도 이 정보를 찾을 수 있습니다.

### <a name="allow-end-users-to-access-the-company-portal-app-for-android-without-enrollment----1169910---"></a>최종 사용자가 등록 없이 Android용 회사 포털 앱에 액세스하도록 허용 <!---1169910--->

머지 않아 최종 사용자가 장치를 등록하지 않고도 Android용 회사 포털 앱에 액세스할 수 있게 됩니다. 앱 보호 정책을 사용하는 조직의 최종 사용자는 회사 포털 앱을 열 때 장치를 등록하라는 메시지를 더 이상 받지 않습니다. 최종 사용자가 장치를 등록하지 않고 회사 포털에서 앱을 설치할 수도 있습니다. 


### <a name="easier-to-understand-phrasing-for-the-company-portal-app-for-android----1396349---"></a>Android용 회사 포털 앱의 구문을 쉽게 이해 <!---1396349--->  

최종 사용자가 쉽게 등록할 수 있도록 새로운 텍스트가 포함되어 Android용 회사 포털 앱의 등록 프로세스가 간소화되었습니다. 사용자 지정 등록 설명서가 있는 경우 새 화면을 반영하도록 업데이트할 수 있습니다. [Intune에 대한 UI 업데이트 및 최종 사용자 앱](whats-new-app-ui.md#week-of-september-11-2017) 페이지에서 샘플 이미지를 찾을 수 있습니다.

### <a name="windows-10-company-portal-app-added-to-windows-information-protection-allow-policy----677129---"></a>Windows Information Protection 허용 정책에 추가된 Windows 10 회사 포털 앱 <!-- 677129 -->

Windows 10 회사 포털 앱이 WIP(Windows Information Protection)를 지원하도록 업데이트되었습니다. WIP 허용 정책에 앱을 추가할 수 있습니다. 이러한 변경으로 이제 앱을 **제외** 목록에 추가하지 않아도 됩니다.


## <a name="august-2017"></a>2017년 8월

### <a name="improvements-to-device-overview----1404453---"></a>장치 개요의 향상된 기능<!-- 1404453 -->  
장치 개요의 향상된 기능에 이제 등록된 장치가 표시되지만 Exchange ActiveSync에서 관리하는 장치는 제외됩니다. Exchange ActiveSync 장치에는 등록된 장치와 동일한 관리 옵션이 없습니다. Azure Portal에서 Intune에 등록된 장치 수 및 플랫폼별 등록된 장치 수를 보려면 **장치** > **개요**로 이동합니다.

### <a name="improvements-to-device-inventory-collected-by-intune"></a>Intune에서 수집하는 장치 인벤토리의 향상된 기능
<!-- 961134, 1104426, 1281327, 1333543 -->
이 릴리스에서는 관리하는 장치에서 수집하는 인벤토리에 대해 다음과 같은 기능이 향상되었습니다.
 
-   Android 장치의 경우, 각 장치에 대한 최신 패치 수준을 표시하는 장치 인벤토리에 이제 열을 추가할 수 있습니다. 확인하려면 장치 목록에 **보안 패치 수준** 열을 추가합니다.
-   장치 보기를 필터링할 때 이제 등록 날짜별로 장치를 필터링할 수 있습니다. 예를 들어 지정한 날짜 후에 등록한 장치만 표시할 수 있습니다.
-   **Last Check-in Date**(마지막 체크인 날짜) 항목에서 사용하는 필터가 향상되었습니다.
-   장치 목록에서 이제 회사 소유 장치의 전화 번호를 표시할 수 있습니다.
또한 필터 창을 사용하여 전화 번호로 장치를 검색할 수 있습니다.
 
장치 인벤토리에 대한 자세한 내용은 [Intune 장치 인벤토리를 확인하는 방법](device-inventory.md)을 참조하세요.

### <a name="conditional-access-support-for-macos-devices"></a>macOS 장치에 대한 조건부 액세스 지원 
<!-- 720172 -->
이제 Mac 장치를 Intune에 등록하고 해당 장치 준수 정책을 준수하도록 요구하는 조건부 액세스 정책을 설정할 수 있습니다. 예를 들어 사용자가 macOS용 Intune 회사 포털 앱을 다운로드하고 해당 Mac 장치를 Intune에 등록할 수 있습니다. Intune은 Mac 장치가 PIN, 암호화, OS 버전, 시스템 무결성 등의 요구 사항을 준수하는지 여부를 평가합니다.

- [macOS 장치에 대한 조건부 액세스 지원](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)에 대해 알아보세요.

### <a name="company-portal-app-for-macos-is-in-public-preview----1484796---"></a>macOS용 회사 포털 앱(공개 미리 보기) <!---1484796--->
macOS용 회사 포털 앱이 지금 Enterprise Mobility + Security의 조건부 액세스에 대한 공개 미리 보기의 일부로 제공됩니다. 이 릴리스에서는 macOS 10.11 이상을 지원합니다. [https://aka.ms/macOScompanyportal](https://aka.ms/macOScompanyportal)에서 다운로드하세요. 


### <a name="new-device-restriction-settings-for-windows-10"></a>Windows 10의 새 장치 제한 설정    
<!--1063965, 1308850  -->
이 릴리스에서는 [Windows 10 장치 제한 프로필](/intune/device-restrictions-windows-10)에 대한 새로운 설정이 다음 범주에 추가되었습니다.

-   Windows Defender SmartScreen
-   앱 스토어

### <a name="updates-to-the-windows-10-endpoint-protection-device-profile-for-bitlocker-settings"></a>BitLocker 설정에 대한 Windows 10 Endpoint Protection 장치 프로필 업데이트
<!--1459533 -->    
이 릴리스에서는 Windows 10 Endpoint Protection 장치 프로필에서 BitLocker 설정을 적용하는 방법에 대해 다음과 같은 기능이 향상되었습니다.
 
**Bitlocker OS 드라이브 설정** 아래의 **호환되지 않는 TPM 칩과 BitLocker** 설정의 경우 **차단**을 선택하면 이전에는 BitLocker가 실제로는 허용되었습니다. 이제 [차단]을 선택하면 BitLocker를 차단하도록 이 문제를 해결했습니다.
**Bitlocker OS 드라이브 설정** 아래의 **인증서 기반 데이터 복구 에이전트** 설정의 경우 이제 인증서 기반 데이터 복구 에이전트를 분명히 차단할 수 있습니다. 그러나 기본적으로 에이전트는 허용됩니다.
**Bitlocker 고정 데이터 드라이브 설정**아래의 **데이터 복구 에이전트** 설정의 경우 이제 데이터 복구 에이전트를 분명히 차단할 수 있습니다.
자세한 내용은 [Windows 10에 대한 Endpoint Protection 설정](endpoint-protection-windows-10.md)을 참조하세요.


### <a name="new-signed-in-experience-for-android-company-portal-users-and-app-protection-policy-users----621669---"></a>Android 회사 포털 사용자와 앱 보호 정책 사용자의 새로 로그인된 환경 <!-- 621669 -->
이제 최종 사용자가 Android 장치를 등록하지 않고도 Android 회사 포털 앱을 사용하여 앱을 찾아보고 장치를 관리하고 IT 연락처 정보를 볼 수 있습니다. 또한 최종 사용자가 이미 Intune 앱 보호 정책을 통해 보호된 앱을 사용하고, Android 회사 포털을 시작하는 경우 최종 사용자에게 더 이상 장치를 등록하라는 메시지가 표시되지 않습니다.

### <a name="new-setting-in-the-android-company-portal-app-to-toggle-battery-optimization---1405990--"></a>배터리 최적화를 전환하는 Android 회사 포털 앱의 새 설정 <!--1405990-->
Android용 회사 포털 앱의 **설정** 페이지에는 사용자가 회사 포털 및 Microsoft Authenticator 앱의 배터리 최적화를 쉽게 해제할 수 있는 새 설정이 있습니다. 설정에 표시된 앱 이름은 회사 계정을 관리하는 앱에 따라 달라집니다. 메일과 데이터를 동기화하는 회사 앱의 성능을 향상시키기 위해 배터리 최적화를 끄는 것이 좋습니다. 

### <a name="multi-identity-support-for-onenote-for-ios---------1234281---"></a>iOS용 OneNote에 대한 다중 ID 지원       <!-- 1234281 -->
최종 사용자는 이제 iOS용 Microsoft OneNote에서 여러 계정(회사 및 개인)을 사용할 수 있습니다. 개인 전자 필기장에 영향을 미치지 않고 회사 전자 필기장의 회사 데이터에 앱 보호 정책을 적용할 수 있습니다. 예를 들어 정책을 통해 사용자가 회사 전자 필기장에서 정보를 찾을 수는 있지만 회사 전자 필기장에서 개인 전자 필기장으로 회사 데이터를 복사하여 붙여넣을 수는 없도록 할 수 있습니다.
 
- Intune을 통해 [앱 보호 및 다중 ID](https://www.microsoft.com/cloud-platform/microsoft-intune-apps)를 지원하는 앱에 대해 자세히 알아봅니다.

### <a name="new-settings-to-allow-and-block-apps-on-samsung-knox-standard-devices"></a>Samsung Knox Standard 장치에서 앱을 허용 및 차단하는 새로운 설정
<!-- 1305423 822899-->  
이 릴리스에서는 다음 앱 목록을 지정할 수 있는 새로운 [장치 제한 설정](device-restrictions-android.md)이 추가되었습니다.
 
- 사용자 설치가 허용된 앱
- 사용자 실행이 차단된 앱
- 장치에서 사용자로부터 숨겨진 앱
 
URL, 패키지 이름 또는 관리하는 앱 목록을 통해 앱을 지정할 수 있습니다.

### <a name="new-azure-ad-app-based-conditional-access-policy-ui-link-from-intune"></a>Intune의 새 Azure AD 앱 기반 조건부 액세스 정책 UI 링크
<!-- 1016201 -->
IT 관리자는 이제 Azure AD 워크로드에서 새 조건부 액세스 정책 UI를 통해 앱 기반 조건부 정책을 설정할 수 있습니다. Azure Portal의 Intune 앱 보호 섹션에 있는 앱 기반 조건부 액세스는 그대로 남아 있으며 나란히 함께 적용됩니다. Intune 워크로드에서 새 조건부 액세스 정책 UI에 연결하는 편리한 링크도 있습니다.

- [Azure AD 앱 기반 조건부 액세스](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-technical-reference)에 대해 자세히 알아보세요.



## <a name="july-2017"></a>2017년 7월

### <a name="restrict-android-and-ios-device-enrollment-restriction-by-os-version------1333256--1245463----"></a>OS 버전별 Android 및 iOS 장치 등록 제한 <!--- 1333256,  1245463 --->
이제 Intune에서 운영 체제 버전 번호로 iOS 및 Android 등록을 제한하는 기능을 지원합니다. IT 관리자는 **장치 유형 제한** 아래에서 최소 운영 체제 값과 최대 운영 체제 값 사이의 범위에서 등록을 제한하는 플랫폼 구성을 설정할 수 있습니다. Android 운영 체제 버전은 Major.Minor.Build.Rev로 지정해야 하며 여기서 Minor, Build, Rev는 선택 사항입니다. iOS 버전을 Major.Minor.Build로 지정해야 하며, 여기서 Minor와 Build는 선택 사항입니다. [장치 등록 제한 사항](enrollment-restrictions-set.md)에 대해 자세히 알아보세요.

>[!NOTE]
>Apple 등록 프로그램이나 Apple Configurator를 통해 등록을 제한하지 않습니다.

### <a name="restrict-android-ios-and-macos-device-personally-owned-device-enrollment------1333272--1333275-1245709----"></a>Android, iOS 및 macOS 장치에 대한 개인 소유 장치 등록 제한 <!--- 1333272,  1333275, 1245709 --->
Intune은 회사 장치 IMEI 번호를 허용 목록에 추가하여 개인 장치 등록을 제한할 수 있습니다. 이제 이 기능이 iOS, Android 및 macOS에서 장치 일련 번호를 사용하는 방법으로 확장되었습니다. 일련 번호를 Intune에 업로드하면 장치를 회사 소유로 미리 선언할 수 있습니다. 등록 제한을 사용하여 개인 소유(BYOD) 장치를 차단하고 회사 소유 장치에 대해서만 등록을 허용할 수 있습니다. [장치 등록 제한 사항](enrollment-restrictions-set.md)에 대해 자세히 알아보세요.

일련 번호를 가져오려면 **장치 등록** > **회사 장치 식별자**로 이동한 다음 **추가**를 클릭하고 .CSV 파일(헤더 없음, 일련 번호와 IMEI 번호 등의 세부 정보를 위한 두 개의 열)을 업로드합니다.  개인 소유 장치를 제한하려면 **장치 등록** > **등록 제한**으로 이동합니다. **장치 유형 제한**에서 **기본값**을 선택한 다음 **플랫폼 구성**을 선택합니다. iOS, Android 및 macOS에 대해 개인 소유 장치를 **허용** 또는 **차단**할 수 있습니다. 


### <a name="new-device-action-to-force-devices-to-sync-with-intune----711369---"></a>장치가 Intune과 동기화되도록 강제하는 새 장치 작업 <!-- 711369 -->
이번 릴리스에서는 선택한 장치가 Intune을 사용하여 즉시 체크 인하도록 강제하는 새 장치 작업이 추가되었습니다. 장치가 체크 인하면 장치에 할당된 보류 중인 작업 또는 정책을 즉시 받게 됩니다.  이 작업을 사용하면 예약된 다음 체크 인을 기다리지 않고 즉시 할당한 정책의 유효성을 검사하고 문제를 해결할 수 있습니다.
자세한 내용은 [장치 동기화](device-sync.md)를 참조하세요.

### <a name="force-supervised-ios-devices-to-automatically-install-the-latest-available-software-update----777100---"></a>감독된 iOS 장치에서 사용 가능한 최신 소프트웨어 업데이트를 자동으로 설치하도록 강제 <!-- 777100 -->
감독된 iOS 장치에서 사용 가능한 최신 소프트웨어 업데이트를 자동으로 설치하도록 강제할 수 있는 소프트웨어 업데이트 작업 영역에서 새 정책을 사용할 수 있습니다. 자세한 내용은 [iOS 업데이트 정책 구성](/intune/software-updates-ios)을 참조하세요.

### <a name="check-point-sandblast-mobile---new-mobile-threat-defense-partner-----954651-1172027---"></a>Check Point SandBlast Mobile - 새 Mobile Threat Defense 파트너 <!-- 954651, 1172027 -->
Microsoft Intune과 통합된 Mobile Threat Defense 솔루션인 Checkpoint SandBlast Mobile에서 수행한 위험 평가에 따라 조건부 액세스를 사용하여 회사 리소스에 대한 모바일 장치 액세스를 제어할 수 있습니다.

#### <a name="how-integration-with-intune-works"></a>Intune과 통합은 어떻게 작동하나요?
Checkpoint SandBlast Mobile을 실행하는 장치에서 수집된 원격 분석에 따라 위험이 평가됩니다. Intune 장치 준수 정책을 통해 사용하도록 설정된 Checkpoint SandBlast Mobile 위험 평가에 따라 EMS 조건부 액세스 정책을 구성할 수 있습니다. 검색된 위협에 따라 회사 리소스에 대한 비규격 장치 액세스를 허용하거나 차단할 수 있습니다.


### <a name="deploy-an-app-as-available-in-the-microsoft-store-for-business----748101---"></a>비즈니스용 Microsoft 스토어에서 사용 가능한 앱 배포 <!-- 748101 -->
이번 릴리스에서는 관리자가 비즈니스용 Microsoft 스토어를 사용 가능으로 할당할 수 있습니다. 사용 가능으로 할당하면 최종 사용자는 Microsoft 스토어로 리디렉션 없이 회사 포털 앱이나 웹 사이트에서 앱을 설치할 수 있습니다.

### <a name="ui-updates-to-the-company-portal-website---1313244-part-1--"></a>회사 포털 웹 사이트의 UI 업데이트 <!--1313244 part 1-->
최종 사용자 경험을 향상시키기 위해 [회사 포털 웹 사이트](https://portal.manage.microsoft.com)의 UI를 여러 개 업데이트했습니다.

- __앱 타일 향상__ 앱 아이콘을 감지할 수 없는 경우 아이콘이 아이콘의 주요 색상을 기반으로 자동 생성된 배경과 함께 표시됩니다. 해당되는 경우 이 배경이 이전에 앱 타일에 표시된 회색 테두리를 대체합니다.

    회사 포털 웹 사이트는 향후 릴리스에서 가능하면 큰 아이콘을 표시합니다. IT 관리자가 최소 크기가 120x120픽셀인 고해상도 아이콘을 사용하여 앱을 게시하는 것이 좋습니다. 

- __탐색 변경 내용__: 탐색 모음 항목이 왼쪽 상단에 있는 햄버거 메뉴로 이동되었습니다. 범주 페이지가 제거되었습니다. 이제 사용자가 찾아보는 동안 범주별로 콘텐츠를 필터링할 수 있습니다.

- __추천 앱 업데이트__ 사용자가 추천하기 위해 선택한 앱을 찾아볼 수 있는 사이트에 전용 페이지를 추가하고 홈페이지의 추천 섹션에서 UI를 일부 조정했습니다.

### <a name="ibooks-support-for-the-company-portal-website---1231841--"></a>회사 포털 웹 사이트에 대한 iBooks 지원<!--1231841-->
사용자가 iBooks를 찾고 다운로드할 수 있도록 회사 포털 웹 사이트에 전용 페이지를 추가했습니다. 


### <a name="additional-help-desk-troubleshooting-details------applies-to-1263399-1326964-1341642----"></a>추가 지원 센터 문제 해결 세부 정보 <!---  Applies to 1263399, 1326964, 1341642 --->
Intune의 문제 해결 표시가 업데이트되고 관리자 및 지원 센터 직원에게 제공하는 정보에 문제 해결 표시가 추가되었습니다. 이제 그룹 멤버 자격을 기반으로 사용자의 모든 할당을 요약하는 **할당** 표를 볼 수 있습니다. 이 목록에는 다음이 포함됩니다.
- 모바일 앱
- 규정 준수 정책
- 구성 프로필
 
또한 이제 **장치** 표에는 **Azure AD 조인 유형** 및 **Azure AD 준수** 열이 포함됩니다. 자세한 내용은 [사용자가 문제 해결할 수 있도록 도움](help-desk-operators.md)을 참조하세요.



### <a name="intune-data-warehouse-public-preview"></a>Intune 데이터 웨어하우스(공개 미리 보기)
Intune 데이터 웨어하우스 샘플 데이터는 테넌트에 대한 과거 보기를 제공합니다. 여러 분석 도구와 호환 가능한 OData 링크인 Power BI 파일(PBIX)을 사용하거나 REST API를 사용하여 데이터에 액세스할 수 있습니다. 자세한 내용은 [Intune 데이터 웨어하우스 사용](reports-nav-create-intune-reports.md)을 참조하세요.


### <a name="light-and-dark-modes-available-for-the-company-portal-app-for-windows-10----676547---"></a>Windows 10용 회사 포털 앱에 밝은 모드와 어두운 모드를 사용할 수 있음 <!---676547--->
최종 사용자가 Windows 10용 회사 포털 앱에 대한 색 모드를 사용자 지정할 수 있게 됩니다. 사용자는 회사 포털 앱의 설정 섹션에서 변경할 수 있습니다. 사용자가 앱을 다시 시작하면 변경 내용이 표시됩니다. Windows 10 버전 1607 이상에서는 앱 모드가 기본적으로 시스템 설정으로 지정됩니다. Windows 10 버전 1511 이상에서는 앱 모드가 기본적으로 밝은 모드로 설정됩니다.

### <a name="enable-end-users-to-tag-their-device-group-in-the-company-portal-app-for-windows-10----807046--"></a>최종 사용자가 Windows 10용 회사 포털 앱에서 장치 그룹에 태그를 지정하도록 허용 <!---807046-->
이제 최종 사용자가 Windows 10용 회사 포털 앱 내에서 직접 태그를 지정하여 장치가 속하는 그룹을 선택할 수 있게 됩니다.



## <a name="june-2017"></a>2017년 6월

### <a name="new-role-based-administration-access-for-intune-admins------1099990---"></a>Intune 관리자를 위한 새로운 역할 기반 관리 액세스 기능 <!-- 1099990 -->  
Azure AD 조건부 액세스 정책 확인, 작성, 수정 및 삭제를 위한 새로운 조건부 액세스 관리자 역할이 추가될 예정입니다. 이전에는 전역 관리자 및 보안 관리자에게만 이 권한이 있었습니다. 이제는 Intune 관리자에게도 이 역할 권한을 부여할 수 있으며, 그러면 관리자가 조건부 액세스 정책에 액세스할 수 있습니다.


### <a name="tag-corporate-owned-devices-with-serial-number----1215070---"></a>일련 번호를 사용하여 회사 소유 장치 태그 지정 <!-- 1215070 -->  
이제 Intune에서 회사 장치 식별자로 iOS, macOS 및 Android 일련 번호 업로드를 지원합니다. 지금은 일련 번호를 사용하여 개인용 장치의 등록을 차단할 수 없습니다. 등록 중에 일련 번호를 확인하지 않기 때문입니다. 일련 번호로 개인용 장치를 차단하는 기능은 조만간 공개될 예정입니다.


### <a name="new-remote-actions-for-ios-devices----854689---"></a>iOS 장치에 대한 새 원격 작업 <!-- 854689 -->
이 릴리스에서는 Apple 교실 앱을 관리하는 공유 iPad 장치에 대한 새로운 두 가지 원격 장치 작업이 추가되었습니다.

-   [현재 사용자 로그아웃](device-logout-user.md) - 선택한 iOS 장치의 현재 사용자를 로그아웃합니다.
-   [사용자 제거](device-remove-user.md) - iOS 장치의 로컬 캐시에서 선택한 사용자를 삭제합니다.


### <a name="support-for-shared-ipads-with-the-ios-classroom-app----1044681---"></a>iOS 교실 앱을 통해 공유 iPad 지원 <!-- 1044681 -->
이 릴리스에서는 관리되는 Apple ID를 사용하여 공유 iPad에 로그인하는 학생을 포함하도록 iOS 교실 앱 관리 지원이 확장되었습니다.


### <a name="changes-to-intune-built-in-apps----1332306---"></a>Intune 기본 제공 앱에 대한 변경 내용 <!-- 1332306 -->
이전에는 Intune에 신속하게 할당할 수 있는 많은 기본 제공 앱이 포함되어 있었습니다. 사용자 의견에 따라 이 목록은 제거되었으며 더 이상 기본 제공 앱은 표시되지 않습니다.
그러나 이미 기본 제공 앱을 할당한 경우 이러한 앱은 여전히 앱 목록에 표시됩니다. 필요에 따라 이러한 앱을 계속 할당할 수 있습니다.
이후 릴리스에는 Azure Portal에서 기본 제공 앱을 더 쉽게 선택하고 할당하는 방법이 추가될 예정입니다.

### <a name="easier-installation-of-office-365-apps-----1121362----"></a>Office 365 앱의 간편한 설치 <!--- 1121362 --->
새 **Office 365 ProPlus** 앱 유형을 통해 최신 버전의 Windows 10을 실행하는, 관리하는 장치에 Office 365 ProPlus 2016 앱을 쉽게 할당할 수 있습니다. 또한 라이선스가 있는 경우 Microsoft Project 및 Microsoft Visio를 설치할 수 있습니다. 원하는 앱이 모두 번들로 묶여 Intune 콘솔의 앱 목록에 하나의 앱으로 표시됩니다.
자세한 내용은 [Windows 10용 Office 365 앱을 추가하는 방법](apps-add-office365.md)을 참조하세요.


### <a name="support-for-offline-apps-from-the-microsoft-store-for-business-----777044----"></a>비즈니스용 Microsoft 스토어의 오프라인 앱 지원 <!--- 777044 --->
이제 비즈니스용 Microsoft 스토어에서 구매한 오프라인 앱이 Azure Portal에 동기화됩니다. 그런 다음 이러한 앱을 장치 그룹 또는 사용자 그룹에 배포할 수 있습니다. 즉, 오프라인 앱이 스토어가 아닌 Intune을 통해 설치됩니다.

### <a name="microsoft-teams-is-now-part-of-the-app-based-ca-list-of-approved-apps------1257019---"></a>이제 Microsoft Teams가 승인된 앱의 앱 기반 CA 목록에 포함됨 <!-- 1257019 -->
이제 iOS 및 Android용 Microsoft Teams 앱이 Exchange 및 SharePoint Online용 앱 기반 조건부 액세스 정책에 대해 승인된 앱에 포함됩니다. 현재 앱 기반 조건부 액세스를 사용하는 모든 테넌트에 대해 Azure Portal의 Intune 앱 보호 블레이드를 통해 앱을 구성할 수 있습니다.

### <a name="managed-browser-and-app-proxy-integration----1287310---"></a>Managed Browser 및 앱 프록시 통합<!-- 1287310 -->
이제 Intune Managed Browser가 Azure AD 응용 프로그램 프록시 서비스와 통합되어 사용자가 원격으로 작업하는 경우에도 내부 웹 사이트에 액세스하도록 허용할 수 있습니다. 브라우저의 사용자는 일반적인 방법으로 사이트 URL을 입력하면 되고, Managed Browser가 응용 프로그램 프록시 웹 게이트웨이를 통해 요청을 라우팅합니다. 자세한 내용은 [Managed Browser 정책을 사용하여 인터넷 액세스 관리](app-configuration-managed-browser.md)를 참조하세요.

### <a name="new-app-configuration-settings-for-the-intune-managed-browser----682951---"></a>Intune Managed Browser에 대한 새로운 앱 구성 설정 <!-- 682951 -->
이 릴리스에서는 iOS 및 Android용 Intune Managed Browser 앱에 대한 구성이 더 추가되었습니다. 이제 앱 구성 정책을 사용하여 브라우저의 책갈피와 기본 홈페이지를 구성할 수 있습니다.
자세한 내용은 [Managed Browser 정책을 사용하여 인터넷 액세스 관리](app-configuration-managed-browser.md)를 참조하세요.

### <a name="bitlocker-settings-for-windows-10-----951707---"></a>Windows 10에 대한 BitLocker 설정 <!-- 951707 -->
이제 새로운 Intune 장치 프로필을 사용하여 Windows 10 장치에 대한 BitLocker 설정을 구성할 수 있습니다. 예를 들어 장치가 암호화되도록 요구하고 BitLocker를 켤 때 적용되는 설정을 더 구성할 수도 있습니다.
자세한 내용은 [Windows 10에 대한 Endpoint Protection 설정](endpoint-protection-windows-10.md)을 참조하세요.

### <a name="new-settings-for-windows-10-device-restriction-profile-----978527--978550-978569-1050031-1058611-----"></a>Windows 10 장치 제한 프로필에 대한 새로운 설정 <!--- 978527,  978550, 978569, 1050031, 1058611,  --->
이 릴리스에서는 Windows 10 장치 제한 프로필에 대한 새로운 설정이 다음 범주에 추가되었습니다.

-  Windows Defender
-  셀룰러 및 연결
-  잠긴 화면 환경
-  개인 정보 취급 방침
-  검색
-  Windows 추천
-  Edge 브라우저

Windows 10 설정에 대한 자세한 내용은 [Windows 10 이상 장치 제한 설정](device-restrictions-windows-10.md)을 참조하세요.


### <a name="company-portal-app-for-android-now-has-a-new-end-user-experience-for-app-protection-policies---1305217--"></a>이제 Android용 회사 포털 앱에 앱 보호 정책에 대한 새로운 최종 사용자 환경이 있음 <!--1305217-->
고객 의견에 따라 Android용 회사 포털 앱에 **회사 콘텐츠 액세스** 단추가 표시됩니다. 이러한 작업은 최종 사용자가 Intune 모바일 응용 프로그램 관리의 기능인 앱 보호 정책을 지원하는 앱에만 액세스하면 될 경우 불필요하게 등록 프로세스를 거치지 않도록 하기 위한 것입니다. 이러한 변경 내용은 [앱 UI의 새로운 기능](whats-new-app-ui.md) 페이지에서 확인할 수 있습니다.

### <a name="new-menu-action-to-easily-remove-company-portal---1164569--"></a>회사 포털을 쉽게 제거할 수 있는 새로운 메뉴 작업 <!--1164569-->
사용자 여러분의 의견에 따라 장치에서 회사 포털 제거를 시작할 수 있는 새로운 메뉴 작업이 Android용 회사 포털 앱에 추가되었습니다. 이 작업은 사용자가 장치에서 앱을 제거할 수 있도록 Intune 관리에서 장치를 제거합니다. 이러한 변경 내용은 [앱 UI의 새로운 기능](whats-new-app-ui.md) 페이지 및 [Android 최종 사용자 설명서](/intune-user-help/unenroll-your-device-from-intune-android)에서 확인할 수 있습니다.

### <a name="improvements-to-app-syncing-with-windows-10-creators-update---676505--"></a>Windows 10 크리에이터스 업데이트와 동기화하는 앱 개선 사항 <!--676505-->
Windows 10용 회사 포털 앱은 이제 Windows 10 크리에이터스 업데이트(버전 1703)가 설치되어 있는 장치의 앱 설치 요청 동기화를 자동으로 시작합니다. 이렇게 하면 "동기화 보류 중" 상태에 있는 동안의 앱 설치 지연 문제를 줄일 수 있습니다. 또한 사용자는 앱 내에서 수동으로 동기화를 시작할 수 있습니다. 이러한 변경 내용은 [앱 UI의 새로운 기능](whats-new-app-ui.md) 페이지에서 확인할 수 있습니다.

### <a name="new-guided-experience-for-windows-10-company-portal----1058938---"></a>Windows 10 회사 포털에 대한 새로운 단계별 환경 <!---1058938--->
Windows 10용 회사 포털 앱에 식별되거나 등록되지 않은 장치에 대한 단계별 Intune 연습 환경이 포함될 예정입니다. 새 환경에서는 Azure Active Directory 등록(조건부 액세스 기능에 필요) 및 MDM 등록(장치 관리 기능에 필요) 과정을 사용자에게 안내하는 단계별 지침을 제공합니다. 회사 포털 홈 페이지에서 안내 방식 환경에 액세스할 수 있습니다. 사용자는 이러한 등록을 완료하지 않아도 앱을 계속 사용할 수 있지만 제한된 기능만 사용할 수 있습니다.

이 업데이트는 Windows 10 1주년 업데이트(빌드 1607) 이상을 실행하는 장치에서만 표시됩니다. 이러한 변경 내용은 [앱 UI의 새로운 기능](whats-new-app-ui.md) 페이지에서 확인할 수 있습니다.


### <a name="microsoft-intune-and-conditional-access-admin-consoles-are-generally-available"></a>Microsoft Intune 및 조건부 액세스 관리 콘솔 일반 공급
Azure Portal 관리 콘솔과 조건부 액세스 관리 콘솔에서 새로운 Intune이 일반 공급됩니다. 이제 Azure Portal의 Intune을 통해 모든 Intune MAM 및 MDM 기능을 통합된 단일 관리 환경에서 관리하고 Azure AD 그룹화 및 대상 지정 기능을 활용할 수 있습니다. Azure의 조건부 액세스 기능은 통합된 단일 콘솔에서 Azure AD와 Intune의 다양한 기능을 함께 제공합니다. 그리고 관리 측면에서 볼 때 Azure 플랫폼으로 이전하면 최신 브라우저를 사용할 수 있습니다.

이제 Intune은 Azure Portal(portal.azure.com)에서 **미리 보기** 레이블 없이 표시됩니다.

그룹을 마이그레이션할 수 있도록 작업 수행을 요청하는 일련의 메시지 중 하나가 메시지 센터에 수신된 경우가 아니면 현재 기존 고객이 수행해야 하는 작업은 없습니다. Microsoft에서 발생한 버그로 인해 마이그레이션이 오래 걸린다는 메시지 센터 공지가 수신되었을 수도 있습니다. Microsoft는 영향받는 모든 고객의 마이그레이션을 정상적으로 완료하기 위해 지속적으로 노력하고 있습니다.

### <a name="improvements-to-the-app-tiles-in-the-company-portal-app-for-ios"></a>iOS 용 회사 포털 앱의 앱 타일 개선 사항
사용자가 회사 포털에 대해 설정하는 브랜딩 색을 반영하도록 홈 페이지의 앱 타일 디자인이 업데이트되었습니다. 자세한 내용은 [앱 UI의 새로운 기능](whats-new-app-ui.md)을 참조하세요.

### <a name="account-picker-now-available-for-the-company-portal-app-for-ios"></a>이제 iOS용 회사 포털 앱에서 계정 선택기 사용 가능
iOS 장치 사용자가 회사 또는 학교 계정을 사용하여 다른 Microsoft 앱에 로그인하는 경우 회사 포털에 로그인할 때 새로운 계정 선택기가 표시될 수 있습니다. 자세한 내용은 [앱 UI의 새로운 기능](whats-new-app-ui.md)을 참조하세요.

## <a name="may-2017"></a>2017년 5월

### <a name="change-your-mdm-authority-without-unenrolling-managed-devices---1103950--"></a>관리되는 장치를 등록 취소하지 않고 MDM 기관 변경 <!--1103950-->
이제 Microsoft 지원에 문의하여 기존의 관리 장치를 등록 취소했다가 다시 등록할 필요 없이 MDM 기관을 변경할 수 있습니다. Configuration Manager 콘솔에서 MDM 기관을 Configuration Manager로 설정(하이브리드)에서 Microsoft Intune(독립 실행형)으로 또는 그 반대로 [변경](/sccm/mdm/deploy-use/change-mdm-authority)할 수 있습니다.


### <a name="improved-notification-for-samsung-knox-startup-pins---1087143--"></a>Samsung Knox 시작 PIN 알림 향상 <!--1087143-->
암호화를 준수하기 위해 최종 사용자가 Samsung Knox 장치에서 시작 PIN을 설정해야 하는 경우 최종 사용자에게 표시되는 알림을 탭하면 최종 사용자가 설정 앱의 정확한 위치로 이동하게 됩니다.  이전에는 최종 사용자가 알림을 통해 암호 변경 화면으로 이동했습니다.

### <a name="device-enrollment"></a>장치 등록

#### <a name="apple-school-manager-asm-support-with-shared-ipad----748864-770395--"></a>공유 iPad에 대한 ASM(Apple School Manager) 지원 <!-- 748864, 770395-->

이제 Intune은 Apple 장비 등록 프로그램 대신 ASM(Apple School Manager)을 사용하도록 지원하여 iOS 장치 기본 등록 기능을 제공합니다. 공유 iPad에 대해 교실 앱을 사용하고 Microsoft SDS(학교 데이터 동기화)를 통해 ASM에서 Azure Active Directory로 데이터를 동기화할 수 있도록 설정하려면 ASM 온보딩이 필요합니다. 자세한 내용은 [Apple School Manager를 통해 iOS 장치 등록 기능 사용](apple-school-manager-set-up-ios.md)을 참조하세요.

> [!NOTE]
> 교실 앱을 사용할 수 있도록 공유 iPad를 구성하려면 Azure의 iOS Education 구성(아직 제공되지 않음)이 필요합니다.  이 기능은 곧 추가될 예정입니다.

### <a name="device-management"></a>장치 관리

#### <a name="provide-remote-assistance-to-android-devices-using-teamviewer----675418---"></a>TeamViewer를 사용하여 Android 장치에 대한 원격 지원 제공 <!-- 675418 -->

이제 Intune에서는 [TeamViewer](https://www.teamviewer.com) 소프트웨어(별매)를 사용하여 Android 장치를 실행하는 사용자에게 원격 지원을 제공할 수 있도록 지원합니다. 자세한 내용은 [Intune Android 관리 장치에 대한 원격 지원 제공](device-profile-android-teamviewer.md)을 참조하세요.

### <a name="app-management"></a>앱 관리

#### <a name="new-app-protection-policies-conditions-for-mam----679864---"></a>MAM의 새 앱 보호 정책 조건 <!-- 679864 -->

이제 등록 사용자가 없는 MAM에 대해 다음 정책을 적용하는 요구 사항을 설정할 수 있습니다.

- 최소 응용 프로그램 버전
- 최소 운영 체제 버전
- 대상 응용 프로그램의 최소 Intune 앱 SDK 버전(iOS에만 해당)

이 기능은 Android 및 iOS 둘 다에서 제공됩니다. Intune은 OS 플랫폼 버전, 응용 프로그램 버전 및 Intune 앱 SDK에 대해 최소 버전 적용을 지원합니다. iOS에서는 SDK가 통합된 응용 프로그램도 SDK 수준에서 최소 버전 적용을 설정할 수 있습니다. 위에 언급된 세 가지 수준에서 앱 보호 정책을 통한 최소 요구 사항이 충족되지 않으면 사용자가 대상 응용 프로그램에 액세스할 수 없습니다. 이때 사용자는 계정을 제거하거나(다중 ID 응용 프로그램의 경우), 응용 프로그램을 닫거나, 해당 OS 또는 응용 프로그램 버전을 업데이트할 수 있습니다.

또한 추가 설정을 구성하여 OS 또는 응용 프로그램 업그레이드를 권장하는 비차단 알림을 제공할 수도 있습니다. 이 알림은 닫을 수 있고 응용 프로그램을 정상적으로 사용할 수 있습니다.

자세한 내용은 [iOS 앱 보호 정책 설정](app-protection-policy-settings-ios.md) 및 [Android 앱 보호 정책 설정](app-protection-policy-settings-android.md)을 참조하세요.

#### <a name="configure-app-configurations-for-android-for-work----621621---"></a>Android for Work용 앱 구성을 위한 구성 작업 <!-- 621621 -->
스토어에서 제공되는 일부 Android 앱은 IT 관리자가 작업 프로필에서 앱이 실행되는 방법을 제어할 수 있는 관리되는 구성 옵션을 지원합니다. Intune에서는 이제 앱이 지원하는 구성을 확인하고 구성 디자이너 또는 JSON 편집기를 사용하여 Azure Portal에서 구성을 수행할 수 있습니다. 자세한 내용은 [Android for Work용 앱 구성 사용](app-configuration-policies-use-android.md)을 참조하세요.

#### <a name="new-app-configuration-capability-for-mam-without-enrollment----677969---"></a>등록 없이도 MAM에 대해 새로운 앱 구성 기능 사용 가능 <!-- 677969 -->
이제 등록 채널이 없는 MAM을 통해서 앱 구성 정책을 만들 수 있습니다. 이 기능은 MDM(모바일 장치 관리) 앱 구성에서 제공되는 앱 구성 정책과 동일합니다. 등록 없이 MAM을 사용하여 앱을 구성하는 예를 확인하려면 [Microsoft Intune에서 Managed Browser를 사용하여 인터넷 액세스 관리](app-configuration-managed-browser.md)를 참조하세요.

#### <a name="configure-allowed-and-blocked-url-lists-for-the-managed-browser----682960---"></a>Managed Browser용 허용 URL 목록 및 차단 URL 목록 구성 <!-- 682960 -->
이제 Azure 포털에서 앱 구성 설정을 사용하여 Intune Managed Browser용으로 허용 도메인/URL 및 차단 도메인/URL 목록을 구성할 수 있습니다. Managed Browser를 사용 중인 장치(관리 장치 또는 관리되지 않는 장치)에 관계없이 이러한 설정을 구성할 수 있습니다. 자세한 내용은 [Microsoft Intune에서 Managed Browser 정책을 사용하여 인터넷 액세스 관리](app-configuration-managed-browser.md)를 참조하세요.

#### <a name="app-protection-policy-helpdesk-view----1069473---"></a>앱 보호 정책 기술 지원팀 보기 <!-- 1069473 -->
IT 기술 지원팀 사용자는 이제 문제 해결 블레이드에서 사용자에게 할당된 앱 보호 정책 앱의 상태와 사용자 라이선스 상태를 확인할 수 있습니다. 자세한 내용은 [문제 해결](./help-desk-operators.md)을 참조하세요.

### <a name="device-configuration"></a>장치 구성

#### <a name="control-website-visits-on-ios-devices----723832---"></a>iOS 장치에서 웹 사이트 방문 제어 <!-- 723832 -->
이제 iOS 장치 사용자가 방문할 수 있는 웹 사이트를 다음 두 가지 방법 중 하나를 사용하여 제어할 수 있습니다.

- Apple 기본 제공 웹 콘텐츠 필터를 사용하여 허용된 URL 및 차단된 URL을 추가합니다.

- Safari 브라우저에서 지정한 웹 사이트만 액세스할 수 있도록 허용합니다. 지정한 각 사이트에 대한 책갈피가 Safari에서 만들어집니다.

자세한 내용은 [iOS 장치에 대한 웹 콘텐츠 필터 설정](web-content-filter-settings-ios.md)을 참조하세요.

#### <a name="preconfigure-device-permissions-for-android-for-work-apps----621614---"></a>Android for Work 앱에 대한 장치 권한 미리 구성 <!-- 621614 -->
Android for Work 장치 작업 프로필에 배포된 앱의 경우 이제 개별 앱에 대해 권한 상태를 구성할 수 있습니다.  기본적으로 위치 또는 장치 카메라에 대한 액세스와 같이 장치 권한이 필요한 Android 앱에서는 권한을 허용할 것인지 거부할 것인지 묻는 메시지를 사용자에게 표시합니다.  예를 들어, 앱에서 장치의 마이크를 사용하는 경우 앱에 마이크 사용 권한을 부여할 것인지 묻는 메시지가 최종 사용자에게 표시됩니다. 이 기능을 사용하면 최종 사용자 대신 권한을 정의할 수 있습니다.  a) 사용자에게 알리지 않고 자동으로 거부하거나, b) 사용자에게 알리지 않고 자동으로 승인하거나, c) 수락/거부 여부를 선택하라는 메시지를 사용자에게 표시하도록 권한을 구성할 수 있습니다. 자세한 내용은 [Microsoft Intune의 Android for Work 장치 제한 설정](device-restrictions-android-for-work.md)을 참조하세요.

#### <a name="define-app-specific-pin-for-android-for-work-devices----728976-1102534---"></a>Android for Work 장치에 대해 앱별 PIN 정의 <!-- 728976, 1102534 -->
관리자는 Android for Work 장치로 관리되는 작업 프로필이 있는 Android 7.0 이상 장치에 대해 작업 프로필에 있는 앱에만 적용되는 암호 정책을 정의할 수 있습니다.  다음 옵션을 사용할 수 있습니다.

- 장치 전체 암호 정책만 정의 - 사용자가 전체 장치를 잠금 해제하는 데 사용해야 하는 암호입니다.
- 작업 프로필 암호 정책만 정의 - 작업 프로필의 앱이 열릴 때마다 사용자에게 암호를 입력하라는 메시지가 표시됩니다.
- 장치 및 작업 프로필 정책 모두 정의 - IT 관리자가 장치 암호 정책 및 작업 프로필 암호 정책을 서로 다른 강도로 정의하도록 선택할 수 있습니다(예: 장치를 잠금 해제하려면 4자리 PIN을 사용하지만 작업 앱을 열려면 6자리 PIN을 사용하도록 정의).

자세한 내용은 [Microsoft Intune의 Android for Work 장치 제한 설정](device-restrictions-android-for-work.md)을 참조하세요.

> [!NOTE]
> 이 기능은 Android 7.0 이상에서만 사용할 수 있습니다.  기본적으로 최종 사용자는 2개의 별도로 정의된 PIN을 사용하거나 정의된 2개의 PIN을 둘 중 더 강도가 높은 PIN으로 결합하도록 선택할 수 있습니다.

#### <a name="new-settings-for-windows-10-devices----978585---"></a>Windows 10 장치의 새로운 설정 <!-- 978585 -->
무선 표시, 장치 검색, 작업 전환 및 SIM 카드 오류 메시지와 같은 기능을 제어하는 새로운 [Windows 장치 제한 설정](device-restrictions-windows-10.md)이 추가되었습니다.

#### <a name="updates-to-certificate-configuration----918991-and-823198---"></a>인증서 구성 업데이트 <!-- 918991 and 823198 -->
SCEP 인증서 프로필을 만들 때 iOS, Android 및 Windows 장치에 대해 **주체 이름 형식**에서 **사용자 지정** 옵션을 사용할 수 있습니다. 이 업데이트 전에는 iOS 장치에서만 **사용자 지정** 필드가 제공되었습니다. 자세한 내용은 [SCEP 인증서 프로필을 만드는 방법] (certificates-scep-configure.md#how-to-create-a-scep-certificate-profile)을 참조하세요.

PKCS 인증서 프로필을 만들 때 **주체 대체 이름**에서 **사용자 지정 Azure AD 특성**을 사용할 수 있습니다. **사용자 지정 Azure AD 특성**을 선택하면 **부서** 옵션을 사용할 수 있습니다. 자세한 내용은 [PKCS 인증서 프로필을 만드는 방법](certficates-pfx-configure.md#create-a-device-configuration-profile)을 참조하세요.

#### <a name="configure-multiple-apps-that-can-run-when-an-android-device-is-in-kiosk-mode----662059---"></a>Android 장치가 키오스크 모드일 때 실행할 수 있는 여러 앱 구성 <!-- 662059 -->
이전에는 ndroid 장치가 키오스크 모드일 때 실행하도록 허용된 앱 하나만 구성할 수 있었습니다. 이제는 앱 ID 또는 토어 URL을 사용하거나 이미 관리 중인 Android 앱을 선택하여 여러 앱을 구성할 수 있습니다. 자세한 내용은 [키오스크 모드 설정](device-restrictions-android.md#kiosk)을 참조하세요.



## <a name="april-2017"></a>2017년 4월

### <a name="support-for-managing-the-apple-classroom-app"></a>Apple 교실 앱 관리 지원
이제 iPad 장치에서 iOS 교실 앱을 관리할 수 있습니다. 교사 iPad에서 정확한 수업 및 학생 데이터를 사용하여 교실 앱을 설정하고 수업에 등록된 학생 iPad를 구성하면 앱을 사용하여 학생 iPad를 제어할 수 있습니다.
자세한 내용은 [iOS 교육 설정 구성](education-settings-configure-ios.md)을 참조하세요.

### <a name="support-for-managed-configuration-options-for-android-apps----621621---"></a>Android 앱에 대해 관리되는 구성 옵션 지원 <!-- 621621 -->
관리되는 구성 옵션을 지원하는 Play 스토어의 Android 앱을 이제 Intune에서 구성할 수 있습니다.  이 기능을 통해 IT에서는 앱에서 지원하는 구성 값 목록을 볼 수 있으며, 이 기능에서는 이러한 값을 구성할 수 있도록 하는 최고의 단계별 UI를 제공합니다.

### <a name="new-android-policy-for-complex-pins----722069---"></a>복합 PIN에 대한 새 Android 정책 <!-- 722069 -->
Android 5.0 이상을 실행하는 장치에 대한 Android 장치 프로필에서 복합 숫자의 필수 [암호](device-restrictions-android.md#password) 유형을 설정할 수 있습니다.  이 설정을 사용하면 장치 사용자가 1111 또는 1234와 같은 반복되거나 연속되는 숫자를 포함하는 PIN을 만들지 못하도록 할 수 있습니다.

### <a name="additional-support-for-android-for-work-devices"></a>Android for Work 장치에 대한 추가 지원
- **암호 및 회사 프로필 설정 관리**<!-- 612808 -->

  이제 이 새로운 Android for Work 장치 제한 정책을 사용하여, 관리하는 Android for Work 장치에서 암호 및 회사 프로필 설정을 관리할 수 있습니다.

- **회사 및 개인 프로필 간의 데이터 공유 허용**<!-- 1045102 -->

이제 이 Android for Work 장치 제한 프로필에는 회사 및 개인 프로필 간의 데이터 공유를 구성할 수 있도록 하는 새 옵션이 포함되어 있습니다.

- **회사 및 개인 프로필 간의 복사 및 붙여넣기 제한**<!-- 1046094 -->

  이제 새로운 Android for Work 장치용 사용자 지정 장치 프로필을 사용하여 회사 및 개인 앱 간에 복사 및 붙여넣기 작업을 허용할지 여부를 제한할 수 있습니다.

자세한 내용은 [Android for Work용 장치 제한](device-restrictions-android-for-work.md)을 참조하세요.

### <a name="assign-lob-apps-to-ios-and-android-devices----1057568---"></a>iOS 및 Android 장치에 LOB 앱 할당 <!-- 1057568 -->
이제 [iOS](lob-apps-ios.md)용 LOB(기간 업무) 앱(.ipa 파일)과 [Android](lob-apps-android.md)용 LOB 앱(.apk 파일)을 사용자 또는 장치에 할당할 수 있습니다.


###  <a name="new-device-policies-for-ios----723774-723815-723826-723830---"></a>iOS에 대한 새 장치 정책 <!-- 723774, 723815, 723826, 723830 -->
- **Apps on Home screen**(홈 화면의 앱) - 앱 사용자가 [iOS 장치의 홈 화면](home-screen-settings-ios.md)에서 어떤 앱을 보게 할지 제어할 수 있습니다. 이 정책은 홈 화면의 레이아웃을 변경하지만 앱을 배포하지 않습니다.

- **Connections to AirPrint devices**(AirPrint 장치에 대한 연결) - iOS 장치의 최종 사용자가 연결할 수 있는 [AirPrint](air-print-settings-ios-macos.md) 장치(네트워크 프린터)를 제어할 수 있습니다.

- **Connections to AirPlay devices**(AirPlay 장치에 대한 연결) - iOS 장치의 최종 사용자가 연결할 수 있는 [AirPlay 장치](airplay-settings-ios.md)(Apple TV 등)를 제어할 수 있습니다.

- **Custom lock screen message**(사용자 지정 잠금 화면 메시지) - 사용자 iOS 장치의 잠금 화면에 표시할 사용자 지정 메시지를 구성하여 기본 잠금 화면 메시지를 대체할 수 있습니다. 자세한 내용은 [iOS 장치에서 분실 모드 활성화](device-lost-mode.md)를 참조하세요.

### <a name="restrict-push-notifications-for-ios-apps----723767---"></a>iOS 앱에 대한 푸시 알림 제한 <!-- 723767 -->
Intune 장치 제한 프로필에서 이제 iOS 장치에 대해 다음과 같은 [알림 설정](app-notification-settings-ios.md)을 구성할 수 있습니다.

- 지정된 앱에 대한 알림을 완전히 켜거나 끕니다.
- 지정한 앱에 대해 알림 센터의 알림을 켜거나 끕니다.
- 경고 유형을 **없음**, **배너** 또는 **Modal Alert**(모달 경고)로 지정합니다.
- 이 앱에 대해 배지를 허용할지 여부를 지정합니다.
- 알림 소리를 허용할지 여부를 지정합니다.

### <a name="configure-ios-apps-to-run-in-single-app-mode-autonomously----737837---"></a>iOS 앱이 자체적으로 단일 앱 모드로 실행되도록 구성 <!-- 737837 -->
이제 Intune 장치 프로필을 사용하여 iOS 장치에서 지정된 앱을 [자체 단일 앱 모드](device-restrictions-ios.md#autonomous-single-app-mode-supervised-only)로 실행하도록 구성할 수 있습니다. 이 모드를 구성하고 앱이 실행되면 장치가 잠기므로 해당 앱만 실행할 수 있습니다. 이 모드의 예로 사용자가 장치에서 테스트를 수행할 수 있도록 앱을 구성하는 경우를 들 수 있습니다. 앱의 작업이 완료되거나 이 정책을 제거하면 장치가 일반 상태로 돌아옵니다.

### <a name="configure-trusted-domains-for-email-and-web-browsing-on-ios-devices----723765---"></a>iOS 장치에서 메일 및 웹 검색을 위해 신뢰할 수 있는 도메인 구성 <!-- 723765 -->
이제 iOS 장치 제한 프로필에서 다음과 같은 [도메인 설정](device-restrictions-ios.md#domains)을 구성할 수 있습니다.

- **표시되지 않은 메일 도메인** - 사용자가 보내거나 받는 메일 중 여기에 지정하는 도메인과 일치하지 않는 메일은 신뢰할 수 없는 것으로 표시됩니다.

- **관리되는 웹 도메인** - 여기에 지정하는 URL에서 다운로드한 문서는 관리되는 문서로 간주됩니다(Safari에만 해당).  

- **Safari 암호 자동 채우기 도메인** - 여기에 지정하는 패턴과 일치하는 URL에서만 사용자가 Safari에 암호를 저장할 수 있습니다. 이 설정을 사용하려면 장치가 감독 모드여야 하며 여러 사용자용으로 구성되어 있지 않아야 합니다. (iOS 9.3 이상)


### <a name="vpp-apps-available-in-ios-company-portal----748782---"></a>iOS 회사 포털에서 사용할 수 있는 VPP 앱 <!-- 748782 -->
이제 iOS VPP(대량 구매) 앱을 **사용 가능한** 설치로 최종 사용자에게 할당할 수 있습니다. 최종 사용자는 앱을 설치하려면 Apple 스토어 계정이 필요합니다.

### <a name="synchronize-ebooks-from-apple-vpp-store----800878---"></a>Apple VPP 스토어에서 전자책 동기화 <!-- 800878 -->
이제 Apple 대량 구매 프로그램 스토어에서 구매한 책을 [Intune과 동기화](vpp-apps-ios.md)하고 사용자에게 책을 할당할 수 있습니다.

### <a name="multi-user-management-for-samsung-knox-standard-devices----971988---"></a>Samsung Knox Standard 장치에 대한 다중 사용자 관리 <!-- 971988 -->
Samsung Knox Standard를 실행하는 장치가 이제 Intune의 [다중 사용자 관리](android-enroll.md)에서 지원됩니다. 따라서 최종 사용자가 Azure Active Directory 자격 증명을 사용하여 장치에서 로그인 및 로그아웃할 수 있고 장치는 사용 여부와 관계없이 중앙에서 관리됩니다.  최종 사용자는 로그인하면 앱에 액세스할 수 있고 앱에 정책을 적용할 수도 있습니다. 사용자가 로그아웃하면 모든 앱 데이터가 지워집니다.

### <a name="additional-windows-device-restriction-settings----818566---"></a>추가 Windows 장치 제한 설정 <!-- 818566 -->
추가 Edge 브라우저 지원, 장치 잠금 화면 사용자 지정, 시작 메뉴 사용자 지정, Windows 추천 검색이 설정된 배경 화면, 프록시 설정 등과 같은 추가 [Windows 장치 제한 설정](device-restrictions-windows-10.md)에 대한 지원을 추가했습니다.

### <a name="multi-user-support-for-windows-10-creators-update----822547---"></a>Windows 10 크리에이터스 업데이트에 대한 다중 사용자 지원 <!-- 822547 -->
Windows 10 크리에이터스 업데이트를 실행하고 Azure Active Directory 도메인에 가입된 장치에 대한 [다중 사용자 관리](windows-enroll.md) 지원을 추가했습니다. 따라서 여러 표준 사용자가 Azure AD 자격 증명을 사용하여 장치에 로그인할 때 각 사용자는 자신의 사용자 이름에 할당된 앱과 정책을 수신합니다. 현재 사용자가 앱 설치와 같은 셀프 서비스의 경우 회사 포털을 사용할 수 없습니다.

### <a name="fresh-start-for-windows-10-pcs---1004830---"></a>Windows 10 PC에서의 새로운 시작<!-- 1004830 -->
Windows 10 PC에 대한 [새로운 시작 장치 작업](device-fresh-start.md)을 이제 사용 가능합니다.  이 작업을 실행하면 PC에 설치된 모든 앱이 제거되고 PC가 자동으로 최신 버전의 Windows로 업데이트됩니다. 이 작업은 종종 새 PC와 함께 제공되는 미리 설치된 OEM 앱을 제거하는 데 사용할 수 있습니다. 이 장치 작업을 실행할 때 사용자 데이터를 유지할지 여부를 구성할 수 있습니다.

### <a name="additional-windows-10-upgrade-paths----903672---"></a>추가 Windows 10 업그레이드 경로 <!-- 903672 -->
이제 [버전 업그레이드 정책을 만들어 장치를 다음과 같은 추가 Windows 10 버전으로 업그레이드](edition-upgrade-configure-windows-10.md)할 수 있습니다.

- Windows 10 Professional
- Windows 10 Professional KN
- Windows 10 Professional Education
- Windows 10 Professional Education N

### <a name="bulk-enroll-windows-10-devices----747607---"></a>Windows 10 장치 대량 등록 <!-- 747607 -->
이제 WCD(Windows 구성 디자이너)를 사용하여 Azure Active Directory 및 Intune에 대한 Windows 10 크리에이터스 업데이트를 실행하는 많은 장치를 연결할 수 있습니다. Azure AD 테넌트에 대한 [대량 MDM 등록](windows-bulk-enroll.md)을 사용하도록 설정하려면 Windows 구성 디자이너를 사용하여 Azure AD 테넌트에 장치를 연결하는 프로비전 패키지를 만들고, 이 패키지를 대량으로 등록 및 관리할 회사 소유 장치에 적용합니다. 패키지가 장치에 적용되면, 장치가 Azure AD에 연결되고 Intune에 등록되며 Azure AD 사용자가 로그온할 수 있는 준비를 하게 됩니다.  Azure AD 사용자는 이러한 장치에서 표준 사용자이며 할당된 정책 및 필수 앱을 수신합니다. 셀프 서비스 및 회사 포털 시나리오의 경우 현재 지원되지 않습니다.

### <a name="new-mam-settings-for-pin-and-managed-storage-locations----581122-736644---"></a>PIN 및 관리되는 저장소 위치에 대한 새 MAM 설정 <!-- 581122, 736644 -->
이제 MAM(모바일 응용 프로그램 관리) 시나리오에 도움이 되는 두 가지 새 앱 설정이 제공됩니다.

- **Disable app PIN when device PIN is managed**(장치 PIN이 관리되는 경우 앱 PIN 사용 안 함) - 등록된 장치에 장치 PIN이 있는지 검색하고 있으면 앱 보호 정책에 따라 트리거되는 앱 PIN을 건너뜁니다. 이 설정을 사용하면 등록된 장치에서 MAM 지원 응용 프로그램을 여는 사용자에게 PIN 프롬프트가 표시되는 횟수를 줄일 수 있습니다. 이 기능은 Android 및 iOS 모두에 제공됩니다.

- **Select which storage services corporate data can be saved to**(회사 데이터를 저장할 저장소 서비스 선택) - 회사 데이터를 저장할 저장소 위치를 지정할 수 있습니다. 사용자가 선택된 저장소 위치 서비스에 저장할 수 있으므로 나열되지 않은 다른 저장소 위치는 모두 차단됩니다.

  지원되는 저장소 위치 서비스 목록:

  - OneDrive
  - 비즈니스 SharePoint Online
  - 로컬 저장소

### <a name="help-desk-troubleshooting-portal----907448---"></a>기술 지원팀의 문제 해결 포털 <!-- 907448 -->
새로운 [문제 해결 포털](help-desk-operators.md)을 사용하면 도움말 센터 운영자 및 Intune 관리자가 사용자와 장치를 확인하고 Intune 기술 문제를 해결하는 작업을 수행할 수 있습니다.

## <a name="march-2017"></a>2017년 3월

### <a name="support-for-ios-lost-mode---431695--"></a>iOS 분실 모드 지원 <!--431695-->
iOS 9.3 이상 장치에 대해 Intune은 **분실 모드**를 추가 지원합니다. 장치를 잠가 모든 사용을 방지할 수 있으며 장치 잠금 화면의 메시지 및 연락처 전화 번호를 표시할 수 있습니다.

최종 사용자는 관리자가 분실 모드를 사용하지 않도록 설정할 때까지 장치의 잠금을 해제할 수 없습니다. 분실 모드가 설정된 경우 Intune 콘솔에서 **장치 찾기** 작업을 사용하여 장치의 지리적 위치를 지도에 표시할 수 있습니다.

장치는 DEP를 통해 등록되고 감독 모드 상태인 회사 소유의 iOS 장치여야 합니다.

자세한 내용은 [Microsoft Intune 장치 관리란?](device-management.md)을 참조하세요.

### <a name="improvements-to-device-actions-report---677150--"></a>장치 작업 보고서의 향상된 기능 <!--677150-->
성능 향상을 위해 장치 작업 보고서를 개선했습니다. 또한 아제 상태별로 보고서를 필터링 수 있습니다. 예를 들어 완료된 장치 동작만 표시하도록 보고서를 필터링할 수 있습니다.

### <a name="custom-app-categories---748805--"></a>사용자 지정 앱 범주<!--748805-->
이제 Intune에 추가하는 앱의 범주를 만들고, 편집하고, 할당할 수 있습니다. 현재 범주는 영어로만 지정할 수 있습니다.
[Intune에 앱을 추가하는 방법](apps-add.md)을 참조하세요.

### <a name="assign-lob-apps-to-users-with-unenrolled-devices---748823--"></a>등록 취소된 장치 사용자에게 LOB 앱 할당 <!--748823-->
장치가 Intune에 등록되었는지 여부와 상관없이 이제 저장소에서 사용자에게 LOB(기간 업무) 앱을 할당할 수 있습니다. 사용자 장치가 Intune에 등록되지 않은 경우 회사 포털 앱 대신에 회사 포털 웹 사이트로 이동하여 설치해야 합니다.

### <a name="new-compliance-reports---846671--"></a>새로운 준수 보고서 <!--846671-->
이제 준수 보고서에 회사 장치의 준수 포스처가 제공되므로 사용자에게 발생한 준수 관련 문제를 신속하게 해결할 수 있습니다. 확인할 수 있는 정보

- 장치의 전체 준수 상태
- 개별 설정에 대한 준수 상태
- 개별 정책에 대한 준수 상태

또한 이러한 보고서에서 개별 장치로 드릴다운하여 해당 장치에 영향을 주는 특정 설정 및 정책을 볼 수 있습니다.

<!--- You can now create an edition upgrade policy to upgrade devices to the following additional Windows 10 editions:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N --->

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Apple 등록 시나리오에 대한 직접 액세스 <!--951869-->
2017년 1월 이후에 만든 Intune 계정은 Azure 포털에서 장치 등록 워크로드를 사용하여 Apple 등록 시나리오에 직접 액세스할 수 있습니다. 이전에는 Azure Portal의 링크를 통해서만 Apple 등록 미리 보기에 액세스할 수 있었습니다. 2017년 1월 이전에 만든 Intune 계정은 일회성 마이그레이션을 수행해야 Azure에서 이러한 기능을 사용할 수 있습니다. 마이그레이션 일정은 아직 공지되지 않았지만 가능한 한 빠른 시일 내에 세부 정보가 제공될 예정입니다. 기존 계정에서 미리 보기에 액세스할 수 없는 경우 평가판 계정을 만들어 새로운 경험을 테스트해 보는 것이 좋습니다.


## <a name="february-2017"></a>2017 년 2월

### <a name="ability-to-restrict-mobile-device-enrollment---747600-795782--"></a>모바일 장치 등록을 제한하는 기능 <!--747600, 795782-->
Intune은 등록할 수 있는 모바일 장치 플랫폼을 제어하는 새로운 등록 제한을 추가합니다. Intune은 모바일 장치 플랫폼을 iOS, macOS, Android, Windows 및 Windows Mobile로 구분합니다.

* 모바일 장치 등록을 제한해도 PC 클라이언트 등록은 제한되지 않습니다.  
* iOS 및 Android에 한해, 개인 소유 장치의 등록을 차단하는 한 가지 추가 옵션이 있습니다.

Intune은 [이 문서](https://docs.microsoft.com/intune-classic/deploy-use/manage-corporate-owned-devices)에 설명된 대로 IT 관리자가 회사 소유로 표시하기 위한 조치를 취하지 않은 한 모든 새 장치를 개인 소유 장치로 표시합니다.

### <a name="view-all-actions-on-managed-devices---677150--"></a>관리 되는 장치에 관한 모든 작업 보기<!--677150-->
새 __장치 작업__ 보고서에는 장치의 공장 재설정과 같은 원격 작업을 수행한 사람이 누구인지 표시되며, 추가로 작업의 상태도 표시됩니다. [장치 관리란?](device-management.md)을 참조하세요.

### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>관리되지 않은 장치에서 할당된 앱에 액세스 가능 <!--664691-->
회사 포털 웹 사이트 디자인 변경의 일환으로, iOS 및 Android 사용자가 자기에게 할당된 앱을 관리되지 않는 장치에 "등록 없이 사용 가능"으로 설치할 수 있습니다. 사용자는 Intune 자격 증명을 사용하여 회사 포털 웹 사이트에 로그인하고 자기에게 할당된 앱의 목록을 볼 수 있습니다. "등록 없이 사용 가능" 앱의 앱 패키지는 회사 포털 웹 사이트를 통해 다운로드할 수 있습니다. 설치하려면 등록이 필요한 앱은 사용자가 앱을 설치하려 할 때 등록하라는 메시지가 표시되므로 이 변경의 영향을 받지 않습니다.

### <a name="custom-app-categories---748805--"></a>사용자 지정 앱 범주<!--748805-->
이제 Intune에 추가하는 앱의 범주를 만들고, 편집하고, 할당할 수 있습니다. 현재 범주는 영어로만 지정할 수 있습니다.
[Intune에 앱을 추가하는 방법](apps-add.md)을 참조하세요.

### <a name="display-device-categories---814654--"></a>장치 범주 표시 <!--814654-->
이제 장치 목록에서 장치 범주를 열로 표시할 수 있습니다. 장치 속성 블레이드의 속성 섹션에서 범주를 편집할 수도 있습니다. [Intune에 앱을 추가하는 방법](apps-add.md)을 참조하세요.

### <a name="configure-windows-update-for-business-settings---776716--"></a>비즈니스용 Windows 업데이트 설정 구성 <!--776716-->

Windows as a Service는 Windows 10 업데이트를 제공하는 새로운 서비스입니다. Windows 10부터는 새로운 기능 업데이트나 품질 업데이트에 모든 이전 업데이트의 내용이 포함됩니다. 따라서 최신 업데이트를 설치하면 Windows 10 장치가 완전히 최신 상태가 됩니다. 이전 버전의 Windows와 달리, 이제는 일부 업데이트가 아니라 전체 업데이트를 설치해야 합니다.

비즈니스용 Windows 업데이트를 사용하면 장치 그룹의 개별 업데이트를 승인할 필요가 없도록 업데이트 관리 환경을 단순화할 수 있습니다. 업데이트 출시 전략을 구성하여 현재 환경의 위험을 관리할 수 있으며 Windows 업데이트를 통해 적시에 업데이트가 설치됩니다. Microsoft Intune에서는 장치에서 업데이트 설정을 구성하는 기능 및 업데이트 설치를 지연하는 기능을 제공합니다. Intune에서는 업데이트를 저장하지 않고 업데이트 정책 할당만 저장합니다. 장치는 업데이트를 위해 Windows 업데이트에 직접 액세스합니다. Intune을 사용하여 **Windows 10 업데이트 링**을 구성 및 관리합니다. 업데이트 링에는 Windows 10 업데이트 설치 시기와 방법을 구성하는 설정 그룹이 포함됩니다. 자세한 내용은 [비즈니스용 Windows 업데이트 설정 구성](windows-update-for-business-configure.md)을 참조하세요.
