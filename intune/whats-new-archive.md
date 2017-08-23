---
title: "지난 달의 새로운 Microsoft Intune 기능"
titleSuffix: Intune on Azure
description: "Intune 새로운 기능 페이지에서 이전 공지 사항 검토"
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 8/02/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9ba01d60-4a03-4e3e-9aba-8be905c0054c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 31617fb9992937f43f5bfc3b882f09d4be7de7b6
ms.sourcegitcommit: 1c71fff769ca0097faf46fc2b58b953ff28386e8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2017
---
# <a name="whats-new-in-the-microsoft-intune---previous-months"></a>Microsoft Intune의 새로운 기능 - 지난 달

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

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
이후 릴리스에서, Intune 포털에서 기본 제공 앱을 더 쉽게 선택하고 할당하는 방법이 추가될 예정입니다.

### <a name="easier-installation-of-office-365-apps-----1121362----"></a>Office 365 앱의 간편한 설치 <!--- 1121362 --->
새 **Office 365 ProPlus** 앱 유형을 통해 최신 버전의 Windows 10을 실행하는, 관리하는 장치에 Office 365 ProPlus 2016 앱을 쉽게 할당할 수 있습니다. 또한 라이선스가 있는 경우 Microsoft Project 및 Microsoft Visio를 설치할 수 있습니다. 원하는 앱이 모두 번들로 묶여 Intune 콘솔의 앱 목록에 하나의 앱으로 표시됩니다.
자세한 내용은 [Windows 10용 Office 365 앱을 추가하는 방법](apps-add-office365.md)을 참조하세요.


### <a name="support-for-offline-apps-from-the-microsoft-store-for-business-----777044----"></a>비즈니스용 Microsoft 스토어의 오프라인 앱 지원 <!--- 777044 --->
이제 비즈니스용 Microsoft 스토어에서 구매한 오프라인 앱이 Intune 포털에 동기화됩니다. 그런 다음 이러한 앱을 장치 그룹 또는 사용자 그룹에 배포할 수 있습니다. 즉, 오프라인 앱이 스토어가 아닌 Intune을 통해 설치됩니다.

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
고객 의견에 따라 Android용 회사 포털 앱에 **회사 콘텐츠 액세스** 단추가 표시됩니다. 이는 Intune 모바일 응용 프로그램 관리의 기능인 앱 보호 정책을 지원하는 앱만 액세스하면 되는 경우 최종 사용자가 불필요하게 등록 프로세스를 수행하지 않도록 하기 위한 것입니다. 이러한 변경 내용은 [앱 UI의 새로운 기능](whats-new-app-ui.md) 페이지에서 확인할 수 있습니다.

### <a name="new-menu-action-to-easily-remove-company-portal---1164569--"></a>회사 포털을 쉽게 제거할 수 있는 새로운 메뉴 작업 <!--1164569-->
사용자 여러분의 의견에 따라 장치에서 회사 포털 제거를 시작할 수 있는 새로운 메뉴 작업이 Android용 회사 포털 앱에 추가되었습니다. 이 작업을 수행하면 Intune 관리에서 장치가 제거되므로 사용자가 장치에서 앱을 제거할 수 있습니다. 이러한 변경 내용은 [앱 UI의 새로운 기능](whats-new-app-ui.md) 페이지 및 [Android 최종 사용자 설명서](/intune-user-help/unenroll-your-device-from-intune-android)에서 확인할 수 있습니다.

### <a name="improvements-to-app-syncing-with-windows-10-creators-update---676505--"></a>Windows 10 크리에이터스 업데이트와 동기화하는 앱 개선 사항 <!--676505-->
Windows 10용 회사 포털 앱은 이제 Windows 10 크리에이터스 업데이트(버전 1703)가 설치되어 있는 장치의 앱 설치 요청 동기화를 자동으로 시작합니다. 이렇게 하면 "동기화 보류 중" 상태에 있는 동안의 앱 설치 지연 문제를 줄일 수 있습니다. 사용자가 수동으로 앱 내에서 동기화를 시작할 수도 있습니다. 이러한 변경 내용은 [앱 UI의 새로운 기능](whats-new-app-ui.md) 페이지에서 확인할 수 있습니다.

### <a name="new-guided-experience-for-windows-10-company-portal----1058938---"></a>Windows 10 회사 포털에 대한 새로운 단계별 환경 <!---1058938--->
Windows 10용 회사 포털 앱에 식별되거나 등록되지 않은 장치에 대한 단계별 Intune 연습 환경이 포함될 예정입니다. 새 환경에서는 Azure Active Directory 등록(조건부 액세스 기능에 필요) 및 MDM 등록(장치 관리 기능에 필요) 과정을 사용자에게 안내하는 단계별 지침을 제공합니다. 회사 포털 홈 페이지에서 안내 방식 환경에 액세스할 수 있습니다. 사용자는 등록을 완료하지 않아도 앱을 계속 사용할 수는 있지만 기능이 제한됩니다.

이 업데이트는 Windows 10 1주년 업데이트(빌드 1607) 이상을 실행하는 장치에서만 표시됩니다. 이러한 변경 내용은 [앱 UI의 새로운 기능](whats-new-app-ui.md) 페이지에서 확인할 수 있습니다.


### <a name="microsoft-intune-and-conditional-access-admin-consoles-are-generally-available"></a>Microsoft Intune 및 조건부 액세스 관리 콘솔 일반 공급
Azure 관리 콘솔과 조건부 액세스 관리 콘솔에서 새로운 Intune이 일반 공급됩니다. 이제 Azure의 Intune을 통해 모든 Intune MAM 및 MDM 기능을 통합된 단일 관리 환경에서 관리하고 Azure AD 그룹화 및 대상 지정 기능을 활용할 수 있습니다. Azure의 조건부 액세스 기능은 통합된 단일 콘솔에서 Azure AD와 Intune의 다양한 기능을 함께 제공합니다. 그리고 관리 측면에서 볼 때 Azure 플랫폼으로 이전하면 최신 브라우저를 사용할 수 있습니다.

이제 Intune은 portal.azure.com에서 Azure 콘솔에 **미리 보기** 레이블 없이 표시됩니다.

그룹을 마이그레이션할 수 있도록 작업 수행을 요청하는 일련의 메시지 중 하나가 메시지 센터에 수신된 경우가 아니면 현재 기존 고객이 수행해야 하는 작업은 없습니다. Microsoft에서 발생한 버그로 인해 마이그레이션이 오래 걸린다는 메시지 센터 공지가 수신되었을 수도 있습니다. Microsoft는 영향받는 모든 고객의 마이그레이션을 정상적으로 완료하기 위해 지속적으로 노력하고 있습니다.

### <a name="improvements-to-the-app-tiles-in-the-company-portal-app-for-ios"></a>iOS 용 회사 포털 앱의 앱 타일 개선 사항
사용자가 회사 포털에 대해 설정하는 브랜딩 색을 반영하도록 홈 페이지의 앱 타일 디자인이 업데이트되었습니다. 자세한 내용은 [앱 UI의 새로운 기능](whats-new-app-ui.md)을 참조하세요.

### <a name="account-picker-now-available-for-the-company-portal-app-for-ios"></a>이제 iOS용 회사 포털 앱에서 계정 선택기 사용 가능
iOS 장치 사용자가 회사 또는 학교 계정을 사용하여 다른 Microsoft 앱에 로그인하는 경우 회사 포털에 로그인할 때 새로운 계정 선택기가 표시될 수 있습니다. 자세한 내용은 [앱 UI의 새로운 기능](whats-new-app-ui.md)을 참조하세요.

## <a name="may-2017"></a>2017년 5월

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
- 작업 프로필 암호 정책만 정의 - 작업 프로필의 앱이 열릴 때마다 사용자에게 암호를 입력하라는 메시지가 표시됩니다.
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

### <a name="multi-user-management-for-samsung-knox-standard-devices----971988---"></a>Samsung KNOX Standard 장치에 대한 다중 사용자 관리 <!-- 971988 -->
Samsung KNOX Standard를 실행하는 장치가 이제 Intune의 [다중 사용자 관리](android-enroll.md)에서 지원됩니다. 따라서 최종 사용자가 Azure Active Directory 자격 증명을 사용하여 장치에서 로그인 및 로그아웃할 수 있고 장치는 사용 여부와 관계없이 중앙에서 관리됩니다.  최종 사용자는 로그인하면 앱에 액세스할 수 있고 앱에 정책을 적용할 수도 있습니다. 사용자가 로그아웃하면 모든 앱 데이터가 지워집니다.

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
2017년 1월 이후에 만든 Intune 계정은 Azure 포털에서 장치 등록 워크로드를 사용하여 Apple 등록 시나리오에 직접 액세스할 수 있습니다. 이전에는 클래식 Intune 포털의 링크를 통해서만 Apple 등록 미리 보기에 액세스할 수 있었습니다. 2017년 1월 이전에 만든 Intune 계정은 일회성 마이그레이션을 수행해야 Azure에서 이러한 기능을 사용할 수 있습니다. 마이그레이션 일정은 아직 공지되지 않았지만 가능한 한 빠른 시일 내에 세부 정보가 제공될 예정입니다. 기존 계정에서 미리 보기에 액세스할 수 없는 경우 평가판 계정을 만들어 새로운 경험을 테스트해 보는 것이 좋습니다.


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

## <a name="january-2017"></a>2017년 1월

### <a name="assign-line-of-business-apps-whether-or-not-devices-are-enrolled---748823--"></a>장치가 등록되었는지 여부와 상관없는 LOB(기간 업무) 앱 <!--748823-->
장치가 Intune에 등록되었는지 여부와 상관없이 이제 저장소에서 사용자에게 LOB(기간 업무) 및 앱을 할당할 수 있습니다. 사용자 장치가 Intune에 등록되지 않은 경우 회사 포털 앱 대신에 회사 포털 웹 사이트로 이동하여 설치합니다. [앱 관리란?](app-management.md)을 참조하세요.

### <a name="resolve-issue-where-ios-devices-are-inactive-or-the-admin-console-cannot-communicate-with-them"></a>iOS 장치가 비활성 상태이거나, 관리 콘솔에서 통신할 수 없는 경우 문제 해결
사용자 장치에서 Intune과의 연결이 끊기는 경우 회사 리소스에 대한 액세스 권한을 다시 얻도록 새로운 문제 해결 단계를 제공할 수 있습니다. [장치가 비활성 상태이거나 관리 콘솔이 장치와 통신할 수 없음](enrollment-troubleshoot.md#devices-are-inactive-or-the-admin-console-cannot-communicate-with-them)을 참조하세요.

## <a name="december-2016-initial-release"></a>2016년 12월(최초 릴리스)

### <a name="telecom-expense-management-integration-in-azure-portal--747605--"></a>Azure Portal에 이동통신 지출 관리 통합<!--747605-->
이제 Azure Portal 내에서 타사 TEM(이동통신 지출 관리) 서비스와의 통합 미리 보기를 시작합니다. Intune을 사용하여 국내 및 로밍 데이터 사용량을 제한할 수 있습니다. 우선 [Saaswedo](http://www.saaswedo.com)와의 통합으로 시작합니다. 평가판 테넌트에 이 기능을 사용하려면 [Microsoft 지원에 문의](https://docs.microsoft.com/intune-classic/troubleshoot/get-support)하세요.

- 저장소에서 iOS, Android 및 Windows 장치로 앱 배포 및 관리
- 저장소에서 iOS, Android 및 Windows 장치로 LOB(기간 업무) 앱 배포 및 관리
- iOS 및 Windows 장치에 대량 구매 앱 배포 및 관리
- Android, iOS 및 Windows 장치용 웹앱 배포 및 관리
- iOS 관리 앱 구성 프로필
- 앱 보호 정책을 구성하고 LOB(기간 업무) 앱을 Intune에 등록되지 않은 장치에 배포
- VPN 프로필, 앱별 VPN, Wi-Fi, 메일 및 인증서 프로필
- 규정 준수 정책
- Azure AD에 대한 조건부 액세스
- 온-프레미스 Exchange에 대한 조건부 액세스
- 장치 등록
- 역할 기반 액세스 제어

## <a name="deprecated-features-in-the-azure-portal"></a>Azure Portal에서 사용되지 않는 기능

### <a name="support-for-row-by-row-review-of-hardware-identifiers"></a>하드웨어 식별자의 행 단위 검토 지원
Azure Portal에서 IMEI 번호 및 Apple 일련 번호에 대한 하드웨어 식별자의 행 단위 검토를 지원하지 않습니다. 클래식 Intune 콘솔에서 쉼표로 구분된 값(.csv) 파일에서 세부 정보를 가져와 개별 하드웨어 식별자에 대한 기존 정보를 덮어쓸 수 있습니다. Azure Portal에는 모든 하드웨어 식별자에 대한 세부 정보를 자동으로 덮어쓰거나 기존 식별자에 대한 새 세부 정보를 무시하는 간소화된 단일 옵션이 있습니다.

#### <a name="how-this-affects-you"></a>이 옵션이 영향을 주는 방식
Azure Portal에서는 업데이트할 IMEI(International Mobile Equipment Identity) 장치를 행 단위로 결정할 수 없습니다. 클래식 Intune 콘솔에서는 이 기능을 계속 지원합니다.

#### <a name="how-to-get-ready-for-this-change"></a>이 변경 내용에 대비하는 방법
Microsoft에서는 이 변경 내용이 영향을 주는 경우 지원 관리자에게 알릴 수 있도록 이 정보를 미리 제공하고 있습니다. 이 변경 내용은 2017년 상반기로 예정된 Azure Portal로의 이동과 일치합니다.


### <a name="support-for-default-corporate-device-enrollment-profiles-in-apple-dep"></a>Apple DEP에서 기본 회사 장치 등록 프로필 지원
Azure Portal에서는 Apple DEP(장비 등록 프로그램) 장치 일련 번호에 대한 "기본" 회사 장치 등록 프로필을 지원하지 않습니다. 클래식 Intune 콘솔에서 사용할 수 있는 이 기능은 의도치 않게 할당된 프로필을 방지하기 위해 중단됩니다. Azure Portal에서는 Apple DEP 계정에서 동기화된 일련 번호에 초기에 회사 장치 등록 프로필이 할당되지 않습니다.

#### <a name="how-this-affects-you"></a>이 옵션이 영향을 주는 방식
Azure Portal에서는 일부 Apple 장치에서 기본 프로필 정책을 설정할 수 없습니다. 클래식 Intune 콘솔에서는 이 기능을 계속 지원합니다.

#### <a name="how-to-get-ready-for-this-change"></a>이 변경 내용에 대비하는 방법
Microsoft에서는 이 변경 내용이 영향을 주는 경우 지원 관리자에게 알릴 수 있도록 이 정보를 미리 제공하고 있습니다. 이는 2017년 상반기로 예정된 Azure Portal로의 이동과 일치합니다.

### <a name="see-also"></a>참고 항목
최근 개발 작업에 대한 자세한 내용은 [Microsoft Intune의 새로운 기능](whats-new.md)을 참조하세요.
