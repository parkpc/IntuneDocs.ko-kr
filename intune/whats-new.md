---
title: "Microsoft Intune의 새로운 기능"
titleSuffix: Intune on Azure
description: "Intune Azure 포털의 새로운 기능 알아보기"
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 07/03/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: fdda99bfd72c71d36a19449d43bc6cbf6a00babe
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2017
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
-->   



## <a name="week-of-june-26th-2017"></a>2017년 6월 26일 주

### <a name="role-based-access-control"></a>역할 기반 액세스 제어
#### <a name="new-role-based-administration-access-for-intune-admins------1099990---"></a>Intune 관리자를 위한 새로운 역할 기반 관리 액세스 기능 <!-- 1099990 -->  
Azure AD 조건부 액세스 정책 확인, 작성, 수정 및 삭제를 위한 새로운 조건부 액세스 관리자 역할이 추가될 예정입니다. 이전에는 전역 관리자 및 보안 관리자에게만 이 권한이 있었습니다. 이제는 Intune 관리자에게도 이 역할 권한을 부여할 수 있으며, 그러면 관리자가 조건부 액세스 정책에 액세스할 수 있습니다.


### <a name="device-enrollment"></a>장치 등록
#### <a name="tag-corporate-owned-devices-with-serial-number----1215070---"></a>일련 번호를 사용하여 회사 소유 장치 태그 지정 <!-- 1215070 -->  
이제 Intune에서 회사 장치 식별자로 iOS, macOS 및 Android 일련 번호 업로드를 지원합니다. 지금은 일련 번호를 사용하여 개인용 장치의 등록을 차단할 수 없습니다. 등록 중에 일련 번호를 확인하지 않기 때문입니다. 일련 번호로 개인용 장치를 차단하는 기능은 조만간 공개될 예정입니다.


### <a name="device-management"></a>장치 관리
#### <a name="new-remote-actions-for-ios-devices----854689---"></a>iOS 장치에 대한 새 원격 작업 <!-- 854689 -->
이 릴리스에서는 iOS 장치에 대한 두 가지 새 원격 장치 작업이 추가되었습니다.

-   [현재 사용자 로그아웃](device-logout-user.md) - 선택한 iOS 장치의 현재 사용자를 로그아웃합니다.
-   [사용자 제거](device-remove-user.md) - iOS 장치의 로컬 캐시에서 선택한 사용자를 삭제합니다.


이러한 원격 작업을 통해 관리자는 공유 iPad에 캐시된 사용자 계정을 관리하고 장치에 현재 로그인한 사용자를 로그아웃할 수 있습니다.

등록하는 동안 관리자는 장치에 캐시할 수 있는 최대 사용자 계정 수를 결정합니다. "사용자 제거"를 통해 관리자는 캐시된 특정 사용자를 제거할 수 있습니다.

"현재 사용자 로그아웃"은 장치에 현재 로그인한 사용자를 로그아웃합니다. 이 작업은 일반적으로 장치 작업이 있는 장치 개요 블레이드의 맨 위에 있습니다.

"사용자 제거"는 장치의 로컬 캐시에서 지정된 사용자를 삭제합니다. 이 작업은 "모니터" -> "사용자"로 이동한 다음 목록에서 특정 사용자를 마우스 오른쪽 단추로 클릭하면 찾을 수 있습니다. 동기화되지 않은 사용자 계정과 연결된 데이터는 모두 손실됩니다. 또한 사용자 목록에서 사용자가 제거된 것이 반영되려면 최대 24시간이 걸릴 수 있습니다.

#### <a name="support-for-shared-ipads-with-the-ios-classroom-app----1044681---"></a>iOS 교실 앱을 통해 공유 iPad 지원 <!-- 1044681 -->
이 릴리스에서는 관리되는 Apple ID를 사용하여 공유 iPad에 로그인하는 학생을 포함하도록 iOS 교실 앱 관리 지원이 확장되었습니다.


### <a name="app-management"></a>앱 관리  
#### <a name="support-for-offline-apps-from-the-windows-store-for-business-----777044----"></a>비즈니스용 Windows 스토어의 오프라인 앱 지원 <!--- 777044 --->
이제 비즈니스용 Windows 스토어에서 구매한 오프라인 앱이 Intune 포털에 동기화됩니다. 그런 다음 이러한 앱을 장치 그룹 또는 사용자 그룹에 배포할 수 있습니다. 즉, 오프라인 앱이 스토어가 아닌 Intune을 통해 설치됩니다.

#### <a name="microsoft-teams-is-now-part-of-the-app-based-ca-list-of-approved-apps------1257019---"></a>이제 Microsoft Teams가 승인된 앱의 앱 기반 CA 목록에 포함됨 <!-- 1257019 -->

이제 iOS 및 Android용 Microsoft Teams 앱이 Exchange 및 SharePoint Online용 앱 기반 조건부 액세스 정책에 대해 승인된 앱에 포함됩니다. 현재 앱 기반 조건부 액세스를 사용하는 모든 테넌트에 대해 Azure Portal의 Intune 앱 보호 블레이드를 통해 앱을 구성할 수 있습니다.

#### <a name="managed-browser-and-app-proxy-integration----1287310---"></a>Managed Browser 및 앱 프록시 통합<!-- 1287310 -->
 이제 Intune Managed Browser가 Azure AD 응용 프로그램 프록시 서비스와 통합되어 사용자가 원격으로 작업하는 경우에도 내부 웹 사이트에 액세스하도록 허용할 수 있습니다. 브라우저의 사용자는 일반적인 방법으로 사이트 URL을 입력하면 되고, Managed Browser가 응용 프로그램 프록시 웹 게이트웨이를 통해 요청을 라우팅합니다. 자세한 내용은 [Managed Browser 정책을 사용하여 인터넷 액세스 관리](app-configuration-managed-browser.md)를 참조하세요.


#### <a name="new-app-configuration-settings-for-the-intune-managed-browser----682951---"></a>Intune Managed Browser에 대한 새로운 앱 구성 설정 <!-- 682951 -->
이 릴리스에서는 iOS 및 Android용 Intune Managed Browser 앱에 대한 구성이 더 추가되었습니다. 이제 앱 구성 정책을 사용하여 브라우저의 책갈피와 기본 홈페이지를 구성할 수 있습니다.
자세한 내용은 [Managed Browser 정책을 사용하여 인터넷 액세스 관리](app-configuration-managed-browser.md)를 참조하세요.




### <a name="device-configuration"></a>장치 구성  
#### <a name="bitlocker-settings-for-windows-10-----951707---"></a>Windows 10에 대한 BitLocker 설정 <!-- 951707 -->
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

## <a name="week-of-june-12-2017"></a>2017년 6월 12일 주

### <a name="company-portal-app-for-android-now-has-a-new-end-user-experience-for-app-protection-policies---1305217--"></a>이제 Android용 회사 포털 앱에 앱 보호 정책에 대한 새로운 최종 사용자 환경이 있음 <!--1305217-->
고객 의견에 따라 Android용 회사 포털 앱에 **회사 콘텐츠 액세스** 단추가 표시됩니다. 이는 Intune 모바일 응용 프로그램 관리의 기능인 앱 보호 정책을 지원하는 앱만 액세스하면 되는 경우 최종 사용자가 불필요하게 등록 프로세스를 수행하지 않도록 하기 위한 것입니다. 이러한 변경 내용은 [앱 UI의 새로운 기능](whats-new-app-ui.md) 페이지에서 확인할 수 있습니다.

### <a name="new-menu-action-to-easily-remove-company-portal---1164569--"></a>회사 포털을 쉽게 제거할 수 있는 새로운 메뉴 작업 <!--1164569-->
사용자 여러분의 의견에 따라 장치에서 회사 포털 제거를 시작할 수 있는 새로운 메뉴 작업이 Android용 회사 포털 앱에 추가되었습니다. 이 작업을 수행하면 Intune 관리에서 장치가 제거되므로 사용자가 장치에서 앱을 제거할 수 있습니다. 이러한 변경 내용은 [앱 UI의 새로운 기능](whats-new-app-ui.md) 페이지 및 [Android 최종 사용자 설명서](/intune-user-help/unenroll-your-device-from-intune-android)에서 확인할 수 있습니다.

### <a name="improvements-to-app-syncing-with-windows-10-creators-update---676505--"></a>Windows 10 크리에이터스 업데이트와 동기화하는 앱 개선 사항 <!--676505-->

Windows 10용 회사 포털 앱은 이제 Windows 10 크리에이터스 업데이트(버전 1703)가 설치되어 있는 장치의 앱 설치 요청 동기화를 자동으로 시작합니다. 이렇게 하면 "동기화 보류 중" 상태에 있는 동안의 앱 설치 지연 문제를 줄일 수 있습니다. 사용자가 수동으로 앱 내에서 동기화를 시작할 수도 있습니다. 이러한 변경 내용은 [앱 UI의 새로운 기능](whats-new-app-ui.md) 페이지에서 확인할 수 있습니다.

### <a name="new-guided-experience-for-windows-10-company-portal----1058938---"></a>Windows 10 회사 포털에 대한 새로운 단계별 환경 <!---1058938--->

Windows 10용 회사 포털 앱에 식별되거나 등록되지 않은 장치에 대한 단계별 Intune 연습 환경이 포함될 예정입니다. 새 환경에서는 Azure Active Directory 등록(조건부 액세스 기능에 필요) 및 MDM 등록(장치 관리 기능에 필요) 과정을 사용자에게 안내하는 단계별 지침을 제공합니다. 회사 포털 홈 페이지에서 안내 방식 환경에 액세스할 수 있습니다. 사용자는 등록을 완료하지 않아도 앱을 계속 사용할 수는 있지만 기능이 제한됩니다.

이 업데이트는 Windows 10 1주년 업데이트(빌드 1607) 이상을 실행하는 장치에서만 표시됩니다. 이러한 변경 내용은 [앱 UI의 새로운 기능](whats-new-app-ui.md) 페이지에서 확인할 수 있습니다.

## <a name="week-of-june-5-2017"></a>2017년 6월 5일 주

### <a name="microsoft-intune-and-conditional-access-admin-consoles-are-generally-available"></a>Microsoft Intune 및 조건부 액세스 관리 콘솔 일반 공급

Azure 관리 콘솔과 조건부 액세스 관리 콘솔에서 새로운 Intune이 일반 공급됩니다. 이제 Azure의 Intune을 통해 모든 Intune MAM 및 MDM 기능을 통합된 단일 관리 환경에서 관리하고 Azure AD 그룹화 및 대상 지정 기능을 활용할 수 있습니다. Azure의 조건부 액세스 기능은 통합된 단일 콘솔에서 Azure AD와 Intune의 다양한 기능을 함께 제공합니다. 그리고 관리 측면에서 볼 때 Azure 플랫폼으로 이전하면 최신 브라우저를 사용할 수 있습니다.

이제 Intune은 portal.azure.com에서 Azure 콘솔에 **미리 보기** 레이블 없이 표시됩니다.

그룹을 마이그레이션할 수 있도록 작업 수행을 요청하는 일련의 메시지 중 하나가 메시지 센터에 수신된 경우가 아니면 현재 기존 고객이 수행해야 하는 작업은 없습니다. Microsoft에서 발생한 버그로 인해 마이그레이션이 오래 걸린다는 메시지 센터 공지가 수신되었을 수도 있습니다. Microsoft는 영향받는 모든 고객의 마이그레이션을 정상적으로 완료하기 위해 지속적으로 노력하고 있습니다.

### <a name="improvements-to-the-app-tiles-in-the-company-portal-app-for-ios"></a>iOS 용 회사 포털 앱의 앱 타일 개선 사항
사용자가 회사 포털에 대해 설정하는 브랜딩 색을 반영하도록 홈 페이지의 앱 타일 디자인이 업데이트되었습니다. 자세한 내용은 [앱 UI의 새로운 기능](whats-new-app-ui.md)을 참조하세요.

### <a name="account-picker-now-available-for-the-company-portal-app-for-ios"></a>이제 iOS용 회사 포털 앱에서 계정 선택기 사용 가능
iOS 장치 사용자가 회사 또는 학교 계정을 사용하여 다른 Microsoft 앱에 로그인하는 경우 회사 포털에 로그인할 때 새로운 계정 선택기가 표시될 수 있습니다. 자세한 내용은 [앱 UI의 새로운 기능](whats-new-app-ui.md)을 참조하세요.

## <a name="week-of-may-29-2017"></a>2017년 5월 29일 주

### <a name="change-your-mdm-authority-without-unenrolling-managed-devices---1103950--"></a>관리되는 장치를 등록 취소하지 않고 MDM 기관 변경 <!--1103950-->

이제 Microsoft 지원에 문의하여 기존의 관리 장치를 등록 취소했다가 다시 등록할 필요 없이 MDM 기관을 변경할 수 있습니다. Configuration Manager 콘솔에서 MDM 기관을 Configuration Manager로 설정(하이브리드)에서 Microsoft Intune(독립 실행형)으로 또는 그 반대로 [변경](/sccm/mdm/deploy-use/change-mdm-authority)할 수 있습니다.


### <a name="improved-notification-for-samsung-knox-startup-pins---1087143--"></a>Samsung KNOX 시작 PIN 알림 향상 <!--1087143-->
암호화를 준수하기 위해 최종 사용자가 Samsung KNOX 장치에서 시작 PIN을 설정해야 하는 경우 최종 사용자에게 표시되는 알림을 탭하면 최종 사용자가 설정 앱의 정확한 위치로 이동하게 됩니다.  이전에는 최종 사용자가 알림을 통해 암호 변경 화면으로 이동했습니다.


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
스토어에서 제공되는 일부 Android 앱은 IT 관리자가 작업 프로필에서 앱이 실행되는 방법을 제어할 수 있는 관리되는 구성 옵션을 지원합니다. Intune에서는 이제 앱이 지원하는 구성을 확인하고 구성 디자이너 또는 JSON 편집기를 사용하여 Intune 포털에서 구성을 수행할 수 있습니다. 자세한 내용은 [Android for Work용 앱 구성 사용](app-configuration-policies-use-android.md)을 참조하세요.

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
 작업 프로필 암호 정책만 정의 - 작업 프로필의 앱이 열릴 때마다 사용자에게 암호를 입력하라는 메시지가 표시됩니다.
- 장치 및 작업 프로필 정책 모두 정의 - IT 관리자가 장치 암호 정책 및 작업 프로필 암호 정책을 서로 다른 강도로 정의하도록 선택할 수 있습니다(예: 장치를 잠금 해제하려면 4자리 PIN을 사용하지만 작업 앱을 열려면 6자리 PIN을 사용하도록 정의).

자세한 내용은 [Microsoft Intune의 Android for Work 장치 제한 설정](device-restrictions-android-for-work.md)을 참조하세요.

> [!NOTE]
> 이 기능은 Android 7.0 이상에서만 사용할 수 있습니다.  기본적으로 최종 사용자는 2개의 별도로 정의된 PIN을 사용하거나 정의된 2개의 PIN을 둘 중 더 강도가 높은 PIN으로 결합하도록 선택할 수 있습니다.

#### <a name="new-settings-for-windows-10-devices----978585---"></a>Windows 10 장치의 새로운 설정 <!-- 978585 -->

무선 표시, 장치 검색, 작업 전환 및 SIM 카드 오류 메시지와 같은 기능을 제어하는 새로운 [Windows 장치 제한 설정](device-restrictions-windows-10.md)이 추가되었습니다.

#### <a name="updates-to-certificate-configuration----918991-and-823198---"></a>인증서 구성 업데이트 <!-- 918991 and 823198 -->

SCEP 인증서 프로필을 만들 때 iOS, Android 및 Windows 장치에 대해 **주체 이름 형식**에서 **사용자 지정** 옵션을 사용할 수 있습니다. 이 업데이트 전에는 iOS 장치에서만 **사용자 지정** 필드가 제공되었습니다. 자세한 내용은 [SCEP 인증서 프로필을 만드는 방법] (certificates-scep-configure.md#how-to-create-a-scep-certificate-profile)을 참조하세요.

PKCS 인증서 프로필을 만들 때 **주체 대체 이름**에서 **사용자 지정 Azure AD 특성**을 사용할 수 있습니다. **사용자 지정 Azure AD 특성**을 선택하면 **부서** 옵션을 사용할 수 있습니다. 자세한 내용은 [PKCS 인증서 프로필을 만드는 방법] (certficates-pfx-configure.md#how-to-create-a-pkcs-certificate-profile)을 참조하세요.

#### <a name="configure-multiple-apps-that-can-run-when-an-android-device-is-in-kiosk-mode----662059---"></a>Android 장치가 키오스크 모드일 때 실행할 수 있는 여러 앱 구성 <!-- 662059 -->

이전에는 ndroid 장치가 키오스크 모드일 때 실행하도록 허용된 앱 하나만 구성할 수 있었습니다. 이제는 앱 ID 또는 토어 URL을 사용하거나 이미 관리 중인 Android 앱을 선택하여 여러 앱을 구성할 수 있습니다. 자세한 내용은 [키오스크 모드 설정](device-restrictions-android.md#kiosk)을 참조하세요.


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

### <a name="platform-support-reminder-windows-phone-81-mainstream-support-will-end-july-11-2017"></a>플랫폼 지원 미리 알림: Windows Phone 8.1 기본 지원이 2017년 7월 11일에 종료됨
<!-- 1327781 -->

2017년 7월 11일에 Windows Phone 8.1 플랫폼의 기본 지원이 종료됩니다. Windows 8.1 PC 지원은 영향을 받지 않습니다.

Intune 서비스에서 관리되는 Windows Phone 8.1 장치에 대한 즉각적인 영향은 없습니다. 등록된 장치는 계속 작동하며 모든 정책, 구성 및 앱이 계속해서 예상대로 작동합니다. Intune 서비스 내의 Windows Phone 8.1 플랫폼과 Windows Phone 8.1 회사 포털 앱을 대상으로 하는 향상된 기능은 없습니다. 

가능하면 빨리 해당 Windows Phone 8.1 장치를 Windows 10 Mobile로 업그레이드하는 것이 좋습니다. 

### <a name="changes-in-support-for-the-intune-ios-company-portal-app-----1164474----"></a>Intune iOS 회사 포털 앱에 대한 지원 변경 내용 <!-- 1164474  -->


iOS 9.0 이상을 실행하는 장치만 지원하는 iOS용 Microsoft Intune 회사 포털 앱의 새로운 버전이 곧 제공될 예정입니다. iOS 8을 지원하는 회사 포털 버전도 매우 짧은 시간 동안 사용할 수 있습니다. 그러나 MAM 지원 iOS 앱을 사용하는 경우 iOS 9.0 이상이 지원되므로 최종 사용자가 최신 OS로 업데이트하도록 하는 것이 좋습니다. 

#### <a name="how-does-this-affect-me"></a>이 변경 사항은 어떤 영향을 미치나요?
구체적인 날짜를 모르고 이 내용을 미리 알려드리는 것은 계획할 시간을 드리기 위해서입니다. 사용자가 iOS 9 이상으로 업데이트되도록 하고, 회사 포털 앱이 릴리스되면 최종 사용자에게 회사 포털 앱을 업데이트하도록 요청하세요.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>이러한 변경에 대해 준비하려면 어떻게 해야 하나요?

사용자에게 iOS 9.0 이상으로 업데이트하여 Intune의 새로운 기능을 완전히 활용하도록 권유합니다.  사용자에게 새 버전의 회사 포털을 설치하여 제공되는 새로운 기능을 활용하도록 권유합니다.

Azure Portal의 Intune으로 이동한 다음 장치 > 모든 장치에서 iOS 버전별로 필터링하여 iOS 9 이전 운영 체제를 사용하는 현재 장치를 모두 확인합니다.

### <a name="improved-sign-in-experience-across-company-portal-apps-for-all-platforms---user-story-1132123--"></a>모든 플랫폼에 대해 회사 포털 앱 전체에서 로그인 환경 개선됨 <!--User Story 1132123-->

Android, iOS 및 Windows용 Intune 회사 포털 앱에 대한 로그인 환경을 개선하게 될 향후 몇 개월 내에 제공될 변경이 있음을 알려드립니다. Azure AD에서 이 변경 내용을 적용할 경우 회사 포털 앱에 대한 모든 플랫폼에서 새로운 사용자 환경이 자동으로 나타나게 됩니다. 또한 사용자가 이제 생성된 일회용 코드를 사용하여 다른 장치에서 회사 포털에 로그인할 수도 있습니다. 이 기능은 사용자가 자격 증명 없이 로그인해야 할 경우에 특히 유용합니다.

이전 로그인 환경, 자격 증명을 사용하는 새 로그인 환경, 그리고 다른 장치로부터의 새 로그인 환경에 대한 스크린샷을 확인하려면 [앱 UI의 새로운 기능](/intune/whats-new-app-ui)을 참조하세요.

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
