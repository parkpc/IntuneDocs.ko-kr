---
title: "Microsoft Intune의 새로운 기능"
titlesuffix: Azure portal
description: "Intune Azure 포털의 새로운 기능 알아보기"
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 10/05/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b2817537cd9bc5ec6b8e9f5800f0c8f87cfde189
ms.sourcegitcommit: 53a1f5226d1e1172f013a1b192321dde610b2d6c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2017
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

## <a name="week-of-october-2-2017"></a>2017년 10월 2일이 있는 주

### <a name="intune-apps"></a>Intune 앱

#### <a name="improvements-to-device-setup-workflow-in-company-portal---1490692--"></a>회사 포털의 향상된 장치 설정 워크플로 기능<!--1490692-->
Android용 회사 포털 앱에서 장치 설치 워크플로를 개선했습니다. 언어는 귀사를 위해 더욱 친숙하고 구체적으로 변경되었으며, 최대한 화면을 결합했습니다. 이러한 내용은 [앱 UI의 새로운 기능](whats-new-app-ui.md#week-of-october-2-2017) 페이지에서 확인할 수 있습니다.

#### <a name="improved-guidance-around-the-request-for-access-to-contacts-on-android-devices---1484985--"></a>Android 장치에서 연락처 액세스 요청에 대한 지침 개선<!--1484985-->

Android용 회사 포털 앱은 최종 사용자가 연락처 사용 권한을 허용하도록 해야 합니다. 최종 사용자가 이 액세스 권한을 거절하는 경우 조건부 액세스에 대한 권한을 부여한다고 경고하는 앱 내 알림이 표시됩니다. 

#### <a name="secure-startup-remediation-for-android---1490712--"></a>Android용 시작 업데이트 관리 보호<!--1490712-->

Android 장치를 가진 최종 사용자는 회사 포털 앱에서 비준수 이유를 누를 수 있습니다 가능하면 문제를 해결하기 위해 설정 앱의 올바른 위치로 직접 이동시킵니다. 

#### <a name="additional-push-notifications-for-end-users-on-the-company-portal-app-for-android-o---1475932---"></a>Android O용 회사 포털 앱에 최종 사용자에 대한 추가 푸시 알림<!---1475932--->

최종 사용자는 Android O용 회사 포털 앱이 Intune 서비스로부터 정책을 검색하는 등 백그라운드 작업을 수행하는 시기를 나타내는 추가 알림을 받게 됩니다. 그러면 회사 포털이 해당 장치에서 관리 작업을 수행할 때 최종 사용자에 대한 투명도가 증가합니다. Android O용 회사 포털 앱에 대한 전반적인 [회사 포털 UI의 최적화](https://blogs.technet.microsoft.com/intunesupport/2017/08/21/android-8-0-o-behaviour-changes-and-microsoft-intune)의 일부입니다. 

Android O에 설정된 새 UI 요소에 대한 최적화가 추가됩니다. 최종 사용자에게는 회사 포털에서 Intune 서비스의 정책을 검색하는 것과 같은 배경 작업을 수행하는 시기를 나타내는 추가 알림이 표시됩니다.  그러면 회사 포털이 해당 장치에서 관리 작업을 수행할 때 최종 사용자에 대한 투명도가 증가합니다.

#### <a name="new-behaviors-for-the-company-portal-app-for-android-with-work-profiles----1485783---"></a>회사 프로필을 사용하는 Android용 회사 포털 앱의 새로운 동작 <!---1485783--->

회사 프로필을 사용하여 Android for Work 장치를 등록하면 회사 프로필의 회사 포털 앱이 장치에서 관리 작업을 수행합니다. 

개인 프로필에서 MAM 지원 앱을 사용하는 경우가 아니면 Android용 회사 포털 앱은 더 이상 사용되지 않습니다. 회사 프로필 환경을 향상하기 위해 Intune이 회사 프로필을 등록한 후 개인 회사 포털 앱을 자동으로 숨깁니다.

Android용 회사 포털 앱은 [Play 스토어에서 회사 포털](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)을 검색하고 **사용**을 탭하여 개인 프로필에서 언제든지 사용할 수 있습니다.

#### <a name="company-portal-for-windows-81-and-windows-phone-81-moving-to-sustaining-mode---1428681--"></a>유지 모드로 전환되는 Windows 8.1 및 Windows Phone 8.1용 회사 포털 <!--1428681-->

2017년 10월부터 Windows 8.1 및 Windows Phone 8.1용 회사 포털 앱이 유지 모드로 전환됩니다. 앱과 등록 및 준수 같은 기존 시나리오가 이러한 플랫폼에서 계속 지원된다는 뜻입니다. 이러한 앱은 Microsoft 스토어 같은 기존 릴리스 채널을 통해 계속 다운로드할 수 있습니다. 

유지 모드가 되면 이러한 앱은 중요 보안 업데이트만 받습니다. 이러한 앱에 대해 릴리스되는 추가 업데이트 또는 기능은 없습니다. 새 기능의 경우 장치를 Windows 10 또는 Windows 10 Mobile로 업데이트하는 것이 좋습니다. 

### <a name="device-enrollment"></a>장치 등록

#### <a name="block-unsupported-samsung-knox-device-enrollment------1490695----"></a>지원되지 않는 Samsung KNOX 장치 등록 차단<!--- 1490695 --->

회사 포털 앱은 지원되는 Samsung KNOX 장치만을 등록하려고 합니다. KNOX 정품 인증 오류로 인해 MDM 등록을 방해하지 않도록 방지하기 위해 장치가 [Samsung에서 게시한 장치 목록](https://www.samsungknox.com/knox-supported-devices/knox-workspace)을 표시하는 경우에만 장치 등록을 시도합니다. 일부 Samsung 장치에는 KNOX를 지원하는 모델 번호가 있을 수 있습니다. 구매하고 배포하기 전에 장치 재판매인과 함께 KNOX 호환성을 검사합니다. [Android 및 Samsung KNOX 표준 정책 설정](/intune-classic/android-policy-settings-in-microsoft-intune.md#supported-samsung-knox-standard-devices)에서 확인된 장치의 전체 목록을 찾을 수 있습니다.

#### <a name="end-of-support-for-android-43-and-lower----1171126-1326920----"></a>Android 4.3 및 이전 버전에 대한 지원 종료 <!---1171126, 1326920 --->
관리되는 앱과 Android용 회사 포털 앱이 회사 리소스에 액세스하려면 Android 4.4 이상이 필요합니다. 12월까지 등록된 모든 장치는 12월에 강제 사용 중지되며, 따라서 회사 리소스에 액세스할 수 없게 됩니다. MDM 없이 앱 보호 정책을 사용 중인 경우 앱이 업데이트를 받지 못하며 해당 환경 품질이 시간이 흐름에 따라 저하됩니다.

#### <a name="inform-end-users-what-device-information-can-be-seen-on-enrolled-devices---1165314--"></a>등록된 장치에 표시되는 장치 정보를 최종 사용자에게 알리기<!--1165314-->
모든 회사 포털 앱의 장치 세부 정보 화면에 **소유권 형식**을 추가합니다. 그러면 [회사가 볼 수 있는 정보는 무엇인가요?](/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune) 문서에서 직접 개인 정보에 대한 자세한 내용을 찾아볼 수 있습니다. 이 기능은 나중에 모든 회사 포털 앱에 롤아웃될 예정입니다. [9월](https://docs.microsoft.com/intune/whats-new#week-of-september-11-2017)에 iOS에서 이 기능을 발표했습니다. 


## <a name="week-of-september-25-2017"></a>2017년 9월 25일이 있는 주

### <a name="device-enrollment"></a>장치 등록

#### <a name="intune-supports-ios-11---1428975--"></a>Intune은 iOS 11을 지원합니다.<!--1428975-->
Intune은 iOS 11을 지원합니다. [Intune 지원 블로그](https://blogs.technet.microsoft.com/intunesupport/2017/09/12/support-tip-intune-support-for-ios-11/)에서 이전에 발표되었습니다.

### <a name="end-of-support-for-ios-80----1164477---"></a>iOS 8.0에 대한 지원 종료 <!---1164477--->
관리되는 앱 및 iOS용 회사 포털 앱이 회사 리소스에 액세스하려면 iOS 9.0 이상이 필요합니다. 올해 9월 이전에 업데이트되지 않은 장치는 회사 포털 또는 해당 앱에 더 이상 액세스할 수 없게 됩니다. 

### <a name="intune-apps"></a>Intune 앱

#### <a name="refresh-action-added-to-the-company-portal-app-for-windows-10---1132468--"></a>Windows 10용 회사 포털 앱에 추가된 새로 고침 작업 <!--1132468-->

사용자는 Windows 10용 회사 포털 앱을 사용하여 새로 고침으로 끌어오거나 데스크톱에서 F5 키를 눌러서 앱에서 데이터를 새로 고칠 수 있습니다.

## <a name="week-of-september-11-2017"></a>2017년 9월 11일이 있는 주

### <a name="device-enrollment"></a>장치 등록

#### <a name="inform-end-users-what-device-information-can-be-seen-for-ios---739894--"></a>iOS에 대해 표시되는 장치 정보를 최종 사용자에게 알리기 <!--739894-->

iOS용 회사 포털 앱에서 장치 세부 정보 화면에 **소유권 형식**을 추가했습니다. 이를 통해 사용자는 Intune 최종 사용자 문서의 이 페이지에서 바로 개인 정보에 대한 자세한 내용을 찾을 수 있습니다. 정보 화면에서도 이 정보를 찾을 수 있습니다.

#### <a name="allow-end-users-to-access-the-company-portal-app-for-android-without-enrollment----1169910---"></a>최종 사용자가 등록 없이 Android용 회사 포털 앱에 액세스하도록 허용 <!---1169910--->

머지 않아 최종 사용자가 장치를 등록하지 않고도 Android용 회사 포털 앱에 액세스할 수 있게 됩니다. 앱 보호 정책을 사용하는 조직의 최종 사용자는 회사 포털 앱을 열 때 장치를 등록하라는 메시지를 더 이상 받지 않습니다. 최종 사용자가 장치를 등록하지 않고 회사 포털에서 앱을 설치할 수도 있습니다. 


#### <a name="easier-to-understand-phrasing-for-the-company-portal-app-for-android----1396349---"></a>Android용 회사 포털 앱의 구문을 쉽게 이해 <!---1396349--->  

최종 사용자가 쉽게 등록할 수 있도록 새로운 텍스트가 포함되어 Android용 회사 포털 앱의 등록 프로세스가 간소화되었습니다. 사용자 지정 등록 설명서가 있는 경우 새 화면을 반영하도록 업데이트할 수 있습니다. [Intune에 대한 UI 업데이트 및 최종 사용자 앱](whats-new-app-ui.md#week-of-september-11-2017) 페이지에서 샘플 이미지를 찾을 수 있습니다.

#### <a name="windows-10-company-portal-app-added-to-windows-information-protection-allow-policy----677129---"></a>Windows Information Protection 허용 정책에 추가된 Windows 10 회사 포털 앱 <!-- 677129 -->

Windows 10 회사 포털 앱이 WIP(Windows Information Protection)를 지원하도록 업데이트되었습니다. WIP 허용 정책에 앱을 추가할 수 있습니다. 이러한 변경으로 이제 앱을 **제외** 목록에 추가하지 않아도 됩니다.


## <a name="week-of-august-21-2017"></a>2017년 8월 21일 주

### <a name="device-enrollment"></a>장치 등록
#### <a name="improvements-to-device-overview----1404453---"></a>장치 개요의 향상된 기능<!-- 1404453 -->  
장치 개요의 향상된 기능에 이제 등록된 장치가 표시되지만 Exchange ActiveSync에서 관리하는 장치는 제외됩니다. Exchange ActiveSync 장치에는 등록된 장치와 동일한 관리 옵션이 없습니다. Azure Portal에서 Intune에 등록된 장치 수 및 플랫폼별 등록된 장치 수를 보려면 **장치** > **개요**로 이동합니다.

### <a name="device-management"></a>장치 관리
#### <a name="improvements-to-device-inventory-collected-by-intune"></a>Intune에서 수집하는 장치 인벤토리의 향상된 기능
<!-- 961134, 1104426, 1281327, 1333543 -->
이 릴리스에서는 관리하는 장치에서 수집하는 인벤토리에 대해 다음과 같은 기능이 향상되었습니다.
 
-   Android 장치의 경우, 각 장치에 대한 최신 패치 수준을 표시하는 장치 인벤토리에 이제 열을 추가할 수 있습니다. 확인하려면 장치 목록에 **보안 패치 수준** 열을 추가합니다.
-   장치 보기를 필터링할 때 이제 등록 날짜별로 장치를 필터링할 수 있습니다. 예를 들어 지정한 날짜 후에 등록한 장치만 표시할 수 있습니다.
-   **Last Check-in Date**(마지막 체크인 날짜) 항목에서 사용하는 필터가 향상되었습니다.
-   장치 목록에서 이제 회사 소유 장치의 전화 번호를 표시할 수 있습니다.
또한 필터 창을 사용하여 전화 번호로 장치를 검색할 수 있습니다.
 
장치 인벤토리에 대한 자세한 내용은 [Intune 장치 인벤토리를 확인하는 방법](device-inventory.md)을 참조하세요.

#### <a name="conditional-access-support-for-macos-devices"></a>macOS 장치에 대한 조건부 액세스 지원 
<!-- 720172 -->
이제 Mac 장치를 Intune에 등록하고 해당 장치 준수 정책을 준수하도록 요구하는 조건부 액세스 정책을 설정할 수 있습니다. 예를 들어 사용자가 macOS용 Intune 회사 포털 앱을 다운로드하고 해당 Mac 장치를 Intune에 등록할 수 있습니다. Intune은 Mac 장치가 PIN, 암호화, OS 버전, 시스템 무결성 등의 요구 사항을 준수하는지 여부를 평가합니다.

- [macOS 장치에 대한 조건부 액세스 지원](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)에 대해 알아보세요.

#### <a name="company-portal-app-for-macos-is-in-public-preview----1484796---"></a>macOS용 회사 포털 앱(공개 미리 보기) <!---1484796--->
macOS용 회사 포털 앱이 지금 Enterprise Mobility + Security의 조건부 액세스에 대한 공개 미리 보기의 일부로 제공됩니다. 이 릴리스에서는 macOS 10.11 이상을 지원합니다. [https://aka.ms/macOScompanyportal](https://aka.ms/macOScompanyportal)에서 다운로드하세요. 


#### <a name="new-device-restriction-settings-for-windows-10"></a>Windows 10의 새 장치 제한 설정    
<!--1063965, 1308850  -->
이 릴리스에서는 [Windows 10 장치 제한 프로필](/intune/device-restrictions-windows-10)에 대한 새로운 설정이 다음 범주에 추가되었습니다.

-   Windows Defender SmartScreen
-   앱 스토어

#### <a name="updates-to-the-windows-10-endpoint-protection-device-profile-for-bitlocker-settings"></a>BitLocker 설정에 대한 Windows 10 Endpoint Protection 장치 프로필 업데이트
<!--1459533 -->    
이 릴리스에서는 Windows 10 Endpoint Protection 장치 프로필에서 BitLocker 설정을 적용하는 방법에 대해 다음과 같은 기능이 향상되었습니다.
 
**Bitlocker OS 드라이브 설정** 아래의 **호환되지 않는 TPM 칩과 BitLocker** 설정의 경우 **차단**을 선택하면 이전에는 BitLocker가 실제로는 허용되었습니다. 이제 [차단]을 선택하면 BitLocker를 차단하도록 이 문제를 해결했습니다.
**Bitlocker OS 드라이브 설정** 아래의 **인증서 기반 데이터 복구 에이전트** 설정의 경우 이제 인증서 기반 데이터 복구 에이전트를 분명히 차단할 수 있습니다. 그러나 기본적으로 에이전트는 허용됩니다.
**Bitlocker 고정 데이터 드라이브 설정**아래의 **데이터 복구 에이전트** 설정의 경우 이제 데이터 복구 에이전트를 분명히 차단할 수 있습니다.
자세한 내용은 [Windows 10에 대한 Endpoint Protection 설정](endpoint-protection-windows-10.md)을 참조하세요.


### <a name="app-management"></a>앱 관리
#### <a name="new-signed-in-experience-for-android-company-portal-users-and-app-protection-policy-users----621669---"></a>Android 회사 포털 사용자와 앱 보호 정책 사용자의 새로 로그인된 환경 <!-- 621669 -->
이제 최종 사용자가 Android 장치를 등록하지 않고도 Android 회사 포털 앱을 사용하여 앱을 찾아보고 장치를 관리하고 IT 연락처 정보를 볼 수 있습니다. 또한 최종 사용자가 이미 Intune 앱 보호 정책을 통해 보호된 앱을 사용하고, Android 회사 포털을 시작하는 경우 최종 사용자에게 더 이상 장치를 등록하라는 메시지가 표시되지 않습니다.

### <a name="new-setting-in-the-android-company-portal-app-to-toggle-battery-optimization---1405990--"></a>배터리 최적화를 전환하는 Android 회사 포털 앱의 새 설정 <!--1405990-->
Android용 회사 포털 앱의 **설정** 페이지에는 사용자가 회사 포털 및 Microsoft Authenticator 앱의 배터리 최적화를 쉽게 해제할 수 있는 새 설정이 있습니다. 설정에 표시된 앱 이름은 회사 계정을 관리하는 앱에 따라 달라집니다. 메일과 데이터를 동기화하는 회사 앱의 성능을 향상시키기 위해 배터리 최적화를 끄는 것이 좋습니다. 

#### <a name="multi-identity-support-for-onenote-for-ios---------1234281---"></a>iOS용 OneNote에 대한 다중 ID 지원       <!-- 1234281 -->
최종 사용자는 이제 iOS용 Microsoft OneNote에서 여러 계정(회사 및 개인)을 사용할 수 있습니다. 개인 전자 필기장에 영향을 미치지 않고 회사 전자 필기장의 회사 데이터에 앱 보호 정책을 적용할 수 있습니다. 예를 들어 정책을 통해 사용자가 회사 전자 필기장에서 정보를 찾을 수는 있지만 회사 전자 필기장에서 개인 전자 필기장으로 회사 데이터를 복사하여 붙여넣을 수는 없도록 할 수 있습니다.
 
- Intune을 통해 [앱 보호 및 다중 ID](https://www.microsoft.com/cloud-platform/microsoft-intune-apps)를 지원하는 앱에 대해 자세히 알아봅니다.

#### <a name="new-settings-to-allow-and-block-apps-on-samsung-knox-standard-devices"></a>Samsung KNOX Standard 장치에서 앱을 허용 및 차단하는 새로운 설정
<!-- 1305423 822899-->  
이 릴리스에서는 다음 앱 목록을 지정할 수 있는 새로운 [장치 제한 설정](device-restrictions-android.md)이 추가되었습니다.
 
- 사용자 설치가 허용된 앱
- 사용자 실행이 차단된 앱
- 장치에서 사용자로부터 숨겨진 앱
 
URL, 패키지 이름 또는 관리하는 앱 목록을 통해 앱을 지정할 수 있습니다.

#### <a name="new-azure-ad-app-based-conditional-access-policy-ui-link-from-intune"></a>Intune의 새 Azure AD 앱 기반 조건부 액세스 정책 UI 링크
<!-- 1016201 -->
IT 관리자는 이제 Azure AD 워크로드에서 새 조건부 액세스 정책 UI를 통해 앱 기반 조건부 정책을 설정할 수 있습니다. Azure Portal의 Intune 앱 보호 섹션에 있는 앱 기반 조건부 액세스는 그대로 남아 있으며 나란히 함께 적용됩니다. Intune 워크로드에서 새 조건부 액세스 정책 UI에 연결하는 편리한 링크도 있습니다.

- [Azure AD 앱 기반 조건부 액세스](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-technical-reference)에 대해 자세히 알아보세요.


## <a name="notices"></a>알림

### <a name="ip-addresses-for-intune-updated----1175274---"></a>Intune의 IP 주소가 업데이트됨 <!-- 1175274 -->
방화벽 프록시 설정에 대해 [DNS 이름 및 IP 주소의 업데이트된 목록](/intune/network-bandwidth-use)이 제공됩니다.

### <a name="use-azure-active-directory-for-conditional-access----967947---"></a>조건부 액세스에 Azure Active Directory 사용 <!-- 967947 -->
Azure Portal의 Azure Active Directory 섹션에서 제공되는 조건부 액세스 기능은 Office 365 Exchange Online, SharePoint Online 등의 클라우드 앱에 대해 정책을 설정하기 위한 보다 강력하고 유연한 프레임워크를 제공합니다.  Intune 콘솔 대신 **Azure Active Directory의 조건부 액세스** 블레이드를 사용하여 정책을 구성할 수 있습니다. Intune 콘솔의 기존 정책은 Azure Portal에서 다시 만들어야 합니다. 자세한 내용은 [Azure AD 조건부 액세스 정책 만들기](/intune/conditional-access-exchange-create.md#create-azure-ad-conditional-access-policies-in-intune-azure-preview)를 참조하세요.

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Apple 등록 시나리오에 대한 직접 액세스 <!--951869-->
2017년 1월 이후에 만든 Intune 계정은 Azure 포털에서 장치 등록 워크로드를 사용하여 Apple 등록 시나리오에 직접 액세스할 수 있습니다. 이전에는 Intune 클래식 포털의 링크를 통해서만 Apple 등록 미리 보기에 액세스할 수 있었습니다. 2017년 1월 이전에 만든 Intune 계정은 일회성 마이그레이션을 수행해야 Azure에서 이러한 기능을 사용할 수 있습니다. 마이그레이션 일정은 아직 공지되지 않았지만 가능한 한 빠른 시일 내에 세부 정보가 제공될 예정입니다. 기존 계정에서 Azure 포털에 액세스할 수 없는 경우 평가판 계정을 만들어 새로운 환경을 테스트해 보는 것이 좋습니다.

### <a name="administration-roles-being-replaced-in-azure-portal"></a>Azure Portal에서 대체되는 관리 역할
Intune 클래식 포털(Silverlight)에서 사용된 기존 MAM(모바일 응용 프로그램 관리) 관리 역할(참가자, 소유자 및 읽기 전용)은 Intune Azure Portal에서 새로운 RBAC(역할 기반 관리 제어)의 전체 집합으로 대체됩니다. Azure Portal로 마이그레이션한 후에 이러한 새 관리 역할에 관리자를 다시 할당해야 합니다. RBAC 및 새 역할에 대한 자세한 내용은 [Microsoft Intune에 대한 역할 기반 액세스 제어](/intune/role-based-access-control)를 참조하세요.



## <a name="whats-coming"></a>향후 예정 사항

#### <a name="ios-11-mail-app-will-support-oauth----1196951---"></a>iOS 11 메일 앱의 OAuth 지원 <!---1196951--->
Intune을 사용하는 조건부 액세스는 OAuth를 통해 iOS 장치에서 더욱 안전한 인증을 지원합니다. 이를 지원하기 위해 iOS용 회사 포털 앱에 더욱 안전한 인증을 허용하는 다른 흐름이 생겼습니다. 최종 사용자가 메일 앱에서 새 Exchange 계정에 로그인하려고 할 때 웹 보기 메시지가 표시됩니다. Intune에 등록되면 기본 메일 앱이 인증서에 액세스하도록 허용할지를 묻는 메시지가 표시됩니다. 대부분의 최종 사용자에게 격리된 메일이 더 이상 표시되지 않습니다. 기존 메일 계정에서는 기본 인증 프로토콜을 계속 사용하므로 이러한 사용자에게는 격리 메일이 계속 배달됩니다. 최종 사용자에 대한 이 로그인 환경은 Office 모바일 앱의 로그인 환경과 비슷합니다.

### <a name="ui-updates-to-the-company-portal-website---1313244-part-2--"></a>회사 포털 웹 사이트의 UI 업데이트 <!--1313244 part 2-->
__추천 앱 업데이트__  
사용자가 추천하기 위해 선택한 앱을 찾아볼 수 있는 사이트에 전용 페이지를 추가하고 홈페이지의 추천 섹션에서 UI를 일부 조정했습니다. 이러한 변경 내용은 [앱 UI의 새로운 기능](whats-new-app-ui.md) 페이지에서 확인할 수 있습니다.

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

Azure Portal의 Intune으로 이동한 다음 [장치] > [모든 장치]에서 iOS 버전별로 필터링하여 iOS 9 이전 운영 체제를 사용하는 현재 장치를 모두 확인합니다.


### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple의 Application Transport Security 업데이트 요구 <!--748318-->
Apple에서는 ATS(Application Transport Security)에 대한 특정 요구 사항을 적용할 것이라고 발표했습니다. ATS는 HTTPS를 통한 모든 앱 통신에서 보다 엄격한 보안을 적용하는 데 사용됩니다. 이 변경 사항은 iOS 회사 포털 앱을 사용하는 Intune 고객에게 영향을 줍니다.

새로운 ATS 요구 사항을 적용하는 Apple TestFlight 프로그램을 통해 iOS용 회사 포털 앱 버전을 제공했습니다. ATS 준수를 테스트하는 데 이 버전을 사용해 보려면 이름, 성, 메일 주소, 회사 이름을 포함하여 <a href="mailto:CompanyPortalBeta@microsoft.com?subject=Register to TestFlight ATS Company Portal app">CompanyPortalBeta@microsoft.com</a>에 메일을 보내 주세요. 자세한 내용은 [Intune 지원 블로그](https://aka.ms/compportalats)를 참조하세요.

### <a name="see-also"></a>참고 항목
* [Microsoft Intune 블로그](http://go.microsoft.com/fwlink/?LinkID=273882)
* [클라우드 플랫폼 로드맵](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [What's new in the Company Portal UI](whats-new-app-ui.md)(회사 포털 UI의 새로운 기능)
* [지난 달의 새로운 기능](whats-new-archive.md)
