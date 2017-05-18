---
title: "초기 버전 | Microsoft 문서"
description: 
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 33f3c8d91d5e4f17a4542d828d1883e33a339221
ms.openlocfilehash: afe06e523e7688cab2effeb6999be3193066add8
ms.contentlocale: ko-kr
ms.lasthandoff: 05/05/2017


---

# <a name="the-early-edition-for-microsoft-intune---may-2017"></a>Microsoft Intune 초기 버전 - 2017년 5월

**초기 버전**에서는 Microsoft Intune의 향후 릴리스에서 도입될 기능의 목록을 제공합니다. 이 정보는 NDA 하에 매우 제한적으로 제공되며, 변경될 수 있습니다. 여기 나열된 일부 기능은 마감일을 맞추지 못할 위험이 있으며 다음 릴리스까지 지연될 수 있습니다. 다른 기능은 고객용 준비 상태를 확인하기 위해, 파일럿(플라이팅) 테스트 중 입니다. 질문이나 궁금한 내용이 있으면 Intune/PM 담당자에게 연락하세요.

이 페이지는 정기적으로 업데이트됩니다. 추가 업데이트가 있는지 다시 확인하세요.

> [!Note]
> Intune에 대해 다음 변경 사항을 개발 중입니다. 최종적으로는 이 모든 기능이 하이브리드 고객 배포(Intune과 Configuration Manager )용으로 지원될 예정입니다. 새로운 하이브리드 기능에 대한 자세한 내용은 [hybrid What’s New page](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management)(하이브리드 새로운 기능 페이지)를 참조하세요.

## <a name="new-capabilities"></a>새로운 기능

### <a name="single-sign-on-support-from-the-company-portal-for-ios-to-outlook-for-ios---834012--"></a>iOS용 회사 포털에서 iOS용 Outlook으로의 Single Sign-On 지원 <!--834012-->

사용자는 같은 장치에서 같은 계정으로 iOS용 회사 포털 앱에 로그인되어 있는 경우 더 이상 Outlook 앱에 로그인할 필요가 없습니다. 사용자는 Outlook 앱을 시작할 때 계정을 선택하여 자동으로 로그인할 수 있습니다. 이 기능을 다른 Microsoft 앱에 추가하는 작업도 진행하는 중입니다.

### <a name="improved-notification-for-samsung-knox-startup-pins---1087143--"></a>Samsung KNOX 시작 PIN 알림 향상 <!--1087143-->

암호화를 준수하기 위해 최종 사용자가 Samsung KNOX 장치에서 시작 PIN을 설정해야 하는 경우 최종 사용자에게 표시되는 알림을 탭하면 최종 사용자가 설정 앱의 정확한 위치로 이동하게 됩니다.  이전에는 최종 사용자가 알림을 통해 암호 변경 화면으로 이동했습니다.

### <a name="promoting-the-most-current-version-of-the-company-portal-for-android---1098661--"></a>Android용 회사 포털의 최신 버전 승격 <!--1098661-->

Android용 회사 포털 앱의 새로운 권장 버전이 앱의 알림 화면에 릴리스되면 최종 사용자에게 앱 내 알림이 표시됩니다. 이 알림은 "회사 포털 업데이트를 사용할 수 있음"을 사용자에게 알립니다. 알림을 탭하면 사용할 수 있는 앱 스토어 목록을 보여 주는 웹 페이지가 열립니다. 이러한 앱 스토어에서 업데이트된 버전을 다운로드 할 수 있습니다. 

### <a name="improvements-to-app-syncing-with-windows-10-creators-update----676505---"></a>Windows 10 크리에이터 업데이트와 동기화하는 앱 개선 사항 <!-- 676505 -->

Windows 10용 회사 포털은 Windows 10 크리에이터 업데이트(1704)가 사용되는 장치의 앱 설치 요청 동기화를 자동으로 시작합니다. 이렇게 하면 "동기화 보류 중" 상태에 있는 동안의 앱 설치 지연 문제를 줄일 수 있습니다. 사용자가 수동으로 앱 내에서 동기화를 시작할 수도 있습니다. 

Windows 10용 회사 포털에서는 새로 고침 단추도 노출되므로 사용자가 필요할 때마다 앱의 콘텐츠를 새로 고칠 수 있습니다. 

## <a name="notices"></a>알림

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple의 Application Transport Security 업데이트 요구 <!--748318-->

Apple에서는 2017년 봄부터 ATS(Application Transport Security)에 대한 특정 요구 사항을 적용할 것이라고 발표했습니다. ATS는 HTTPS를 통한 모든 앱 통신에서 보다 엄격한 보안을 적용하는 데 사용됩니다. 이 변경 사항은 iOS 회사 포털 앱을 사용하는 Intune 고객에게 영향을 줍니다. 자세한 내용은 [Intune 지원 블로그](https://aka.ms/compportalats)를 참조하세요.

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Apple 등록 시나리오에 대한 직접 액세스 <!--951869-->

2017년 1월 이후에 만든 Intune 계정은 Azure Preview 포털에서 장치 등록 워크로드를 사용하여 Apple 등록 시나리오에 직접 액세스할 수 있습니다. 이전에는 클래식 Intune 포털의 링크를 통해서만 Apple 등록 미리 보기에 액세스할 수 있었습니다. 2017년 1월 이전에 만든 Intune 계정은 일회성 마이그레이션을 수행해야 Azure에서 이러한 기능을 사용할 수 있습니다. 마이그레이션 일정은 아직 공지되지 않았지만 가능한 한 빠른 시일 내에 세부 정보가 제공될 예정입니다. 기존 계정에서 미리 보기에 액세스할 수 없는 경우 평가판 계정을 만들어 새로운 경험을 테스트해 보는 것이 좋습니다.

### <a name="whats-coming-for-appx-in-intune-on-azure----1000270---"></a>Azure의 Intune에서 Appx에 대한 향후 변경 사항 <!-- 1000270 -->

Azure의 Intune으로 마이그레이션하는 과정의 일환으로 appx의 다음 세 가지 사항을 변경합니다.

1. MDM에 등록된 장치에만 배포할 수 있는 새 appx 앱 유형을 클래식 Intune 콘솔에 추가합니다.
2. Intune PC 에이전트를 통해 관리되는 PC만 대상으로 할 수 있도록 기존 appx 앱 유형의 용도를 변경합니다.
3. 마이그레이션과 함께 기존 appx를 모두 MDM appx로 변환합니다.

Intune PC 에이전트를 통해 관리되는 장치의 기존 배포에는 아무런 영향을 주지 않습니다. 그러나 마이그레이션 후에는 이전에 대상으로 하지 않았던 Intune PC 에이전트를 통해 관리되는 새 장치에 마이그레이션된 appx를 배포할 수 없습니다.

마이그레이션 후 새 PC 배포를 수행하려면 appx를 PC appx로 다시 업로드해야 합니다. 자세한 내용은 [Appx changes in Intune on Azure](https://aka.ms/appxchange)(Azure의 Intune에서 Appx 변경 사항)를 참조하세요.  


## <a name="public-preview-of-the-new-intune-admin-experience-on-azure---736542--"></a>Azure의 새 Intune 관리 환경에 대한 공개 미리 보기<!--736542-->

2017년 초에 Microsoft에서는 전체 관리 환경을 Azure로 마이그레이션합니다. 이를 통해 Graph API를 사용하여 확장 가능한 최신 서비스 플랫폼에서 핵심 EMS 워크플로에 대한 강력한 통합 관리를 지원합니다.

새 평가판 테넌트에서는 이번 달에 Azure Portal에서 새 관리 환경의 공개 미리 보기를 표시하기 시작합니다. 미리 보기 상태에서는 기존 Intune 콘솔의 기능과 패리티가 반복적으로 제공됩니다.

Azure Portal의 관리 환경에서는 이미 발표된 새 그룹화 및 대상 지정 기능을 사용합니다. 따라서 기존 테넌트가 새 그룹화 환경으로 마이그레이션될 때 사용자도 마이그레이션되어 테넌트에 새 관리 환경의 미리 보기가 표시됩니다. 그 동안 테넌트가 마이그레이션될 때까지 새 기능을 테스트하거나 살펴보려는 경우 새 Intune 평가판 계정에 등록하거나 [새 설명서](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune)를 살펴보세요.

### <a name="support-for-managed-configuration-options-for-android-apps----621621---"></a>Android 앱에 대해 관리되는 구성 옵션 지원 <!-- 621621 -->

관리되는 구성 옵션을 지원하는 Play 스토어의 Android 앱을 구성할 수 있습니다.  이 기능을 통해 앱에서 지원하는 구성 값 목록을 볼 수 있으며, 이 기능에서는 이러한 값을 구성할 수 있도록 하는 최고의 단계별 UI를 제공합니다.

### <a name="remote-assistance-for-android-devices----675418---"></a>Android 장치에 대한 원격 지원 <!-- 675418 -->

Intune에서는 [TeamViewer](https://www.teamviewer.com) 소프트웨어(별매)를 사용하여 Android 장치를 실행하는 사용자에게 원격 지원을 제공할 수 있도록 지원합니다.

### <a name="preconfigure-device-permissions-for-android-for-work-apps----621614---"></a>Android for Work 앱에 대한 장치 권한 미리 구성 <!-- 621614 -->

Android for Work 장치 작업 프로필에 배포된 앱의 경우 개별 앱에 대해 권한 상태를 구성할 수 있습니다. 기본적으로 위치 또는 장치 카메라에 대한 액세스와 같이 장치 권한이 필요한 Android 앱에서는 권한을 허용할 것인지 거부할 것인지 묻는 메시지를 사용자에게 표시합니다.  예를 들어, 앱에서 장치의 마이크를 사용하는 경우 앱에 마이크 사용 권한을 부여할 것인지 묻는 메시지가 최종 사용자에게 표시됩니다. 이 기능을 사용하면 최종 사용자 대신 권한을 정의할 수 있습니다.  관리자는 다음 권한을 구성할 수 있습니다.

- 사용자에게 알리지 않고 자동으로 거부
- 사용자에게 알리지 않고 자동으로 승인
- 사용자에게 허용할 것인지 거부할 것인지 묻는 메시지 표시

### <a name="define-app-specific-pin-for-android-for-work-devices---728976--"></a>Android for Work 장치에 대해 앱별 PIN 정의 <!--728976-->

Android for Work 장치로 관리되는 Android 7.0 이상 장치의 작업 프로필에 있는 앱에만 적용되는 암호 정책을 정의할 수 있습니다.  다음 옵션을 사용할 수 있습니다.

- 장치 전체 암호 정책만 정의 - 최종 사용자가 전체 장치를 잠금 해제하는 데 사용해야 하는 암호입니다.
- 작업 프로필 암호 정책만 정의 - 작업 프로필의 앱이 열릴 때마다 최종 사용자에게 암호를 입력하라는 메시지가 표시됩니다.
- 장치 및 작업 프로필 정책 모두 정의 - IT에서 장치 암호 정책 및 작업 프로필 암호 정책을 서로 다른 강도로 정의하도록 선택할 수 있습니다(예: 장치를 잠금 해제하려면 4자리 PIN을 사용하지만 작업 앱을 열려면 6자리 PIN을 사용하도록 정의).

>[!NOTE]
> Android 7.0 이상에서만 사용할 수 있습니다.  기본적으로 최종 사용자는 2개의 별도로 정의된 PIN을 사용 하도록 선택하거나 정의된 2개의 PIN을 둘 중 더 강도가 높은 PIN으로 결합하도록 선택할 수 있습니다.

### <a name="manage-password-and-other-android-for-work-settings---1102534--"></a>암호 및 다른 Android for Work 설정 관리 <!--1102534-->

Android for Work 장치에서 암호 및 회사 프로필 설정을 관리할 수 있도록 하는 새 Android for Work 장치 제한 정책을 추가했습니다.

###  <a name="new-web-content-filter-policy-for-ios-devices----723832---"></a>iOS 장치에 대한 새로운 웹 콘텐츠 필터 정책 <!-- 723832 -->

iOS 장치 사용자가 방문할 수 있는 웹 사이트를 다음 두 가지 방법 중 하나를 사용하여 제어할 수 있습니다.

  - Apple 기본 제공 웹 콘텐츠 필터를 사용하여 허용된 URL 및 차단된 URL을 추가합니다.
  - Safari 브라우저에서 지정한 웹 사이트만 액세스할 수 있도록 허용합니다. 지정한 각 사이트에 대한 책갈피가 Safari에서 만들어집니다.

### <a name="apple-school-manager-asm-support---748864--"></a>ASM(Apple School Manager) 지원 <!--748864-->

Intune은 Apple 장치 등록 프로그램 대신 ASM(Apple School Manager)을 사용하도록 지원하여 iOS 장치 기본 등록 기능을 제공합니다. 공유 iPad에 대해 교실 앱을 사용하고 Microsoft SDS(학교 데이터 동기화)를 통해 ASM에서 Azure Active Directory로 데이터를 동기화할 수 있도록 설정하려면 ASM 온보딩이 필요합니다.  

### <a name="shared-ipad-support---770395-1044681---"></a>공유 iPad 지원 <!--770395, 1044681 -->

Intune은 Apple 장치 등록 프로그램 또는 Apple School Manager의 등록 프로필에서 공유 iPad 모드 구성을 지원합니다. 이 설정을 통해 여러 관리되는 Apple ID가 동일한 장치에 로그인할 수 있습니다.

관리되는 Apple ID를 사용하여 공유 iPad에 로그인하는 학생을 포함하도록 iOS 교실 앱 관리에 대한 지원도 확장할 것입니다.

### <a name="new-windows-device-restriction-settings---978585--"></a>새로운 Windows 장치 제한 설정 <!--978585-->

무선 표시, 장치 검색, 작업 전환 및 SIM 카드 오류 메시지와 같은 기능을 제어하는 설정이 Windows 장치 제한 프로필에 추가될 예정입니다.

### <a name="office-365-proplus-app-available-for-windows-10-devices---1121362--"></a>Windows 10 장치에 사용할 수 있는 Office 365 ProPlus 앱 <!--1121362-->

Office 365 ProPlus 앱을 쉽게 Windows 10 장치에 할당할 수 있는 새로운 Office 365 ProPlus 앱 유형이 추가될 예정입니다. 또한 라이선스가 있는 경우 Microsoft Project 및 Microsoft Visio도 설치할 수 있습니다. 원하는 앱이 모두 번들로 묶여 Intune 콘솔의 앱 목록에 하나의 앱으로 표시됩니다.

### <a name="new-allowblock-list-for-the-managed-browser---682960--"></a>Managed Browser의 새 허용/차단 목록 <!--682960-->

Azure 포털의 Intune 응용 프로그램 구성 설정을 사용하여 Managed Browser의 도메인 및 URL 허용/차단 목록을 구성할 수 있습니다. 관리되는 장치에서 사용되든 관리되지 않는 장치에서 사용되든 관계없이 Managed Browser에 대해 구성될 수 있습니다.

### <a name="new-app-configuration-capabilities----677969---"></a>새 앱 구성 기능 <!-- 677969 -->

이 기능은 MDM(모바일 장치 관리) 앱 구성에 해당됩니다. 이 기능을 통해 관리자는 더 많은 앱 구성 값 즉 MAM의 앱 보호 정책을 통해 제공되는 앱 구성 값을 등록 채널 없이 적용할 수 있습니다.

### <a name="new-app-protection-policies-conditions-for-mam---679864--"></a>MAM의 새 앱 보호 정책 조건 <!--679864-->

등록 사용자 없이 관리 콘솔을 통해 다음 사항을 적용하는 요구 사항을 MAM에 대해 설정할 수 있습니다.

- 최소 응용 프로그램 버전
- 최소 운영 체제 버전
- 대상 응용 프로그램의 최소 Intune 앱 SDK 버전(iOS에만 해당)

이 기능은 iOS 및 Android 모두에 제공됩니다. Intune은 OS 플랫폼 버전, 응용 프로그램 버전 및 Intune 앱 SDK에 대해 최소 버전 적용을 지원합니다. iOS에서는 SDK가 통합된 응용 프로그램도 SDK 수준에서 최소 버전 적용을 설정할 수 있습니다.

위에 언급된 3가지 수준에서 앱 보호 정책을 통한 최소 요구 사항이 충족되지 않으면 사용자가 대상 응용 프로그램에 액세스할 수 없습니다. 이때 사용자는 계정을 제거하거나(다중 ID 응용 프로그램의 경우), 응용 프로그램을 닫거나, 해당 OS 또는 응용 프로그램 버전을 업데이트하여 요구 사항을 충족할 수 있습니다.

또한 관리 콘솔을 통해 추가 설정을 구성하여 OS 또는 응용 프로그램 업그레이드를 권장하는 비차단 알림을 제공할 수도 있습니다. 이 알림은 닫을 수 있고 응용 프로그램을 정상적으로 사용할 수 있습니다.

### <a name="change-your-mdm-authority-without-unenrolling-managed-devices---1103950--"></a>관리되는 장치를 등록 취소하지 않고 MDM 기관 변경 <!--1103950-->

Microsoft 지원에 문의하여 기존의 관리되는 장치를 등록 취소했다가 다시 등록할 필요 없이 MDM 기관을 변경할 수 있습니다. Configuration Manager 콘솔에서 MDM 기관을 Configuration Manager로 설정(하이브리드)에서 Microsoft Intune(독립 실행형)으로 또는 그 반대로 변경할 수 있습니다.


### <a name="see-also"></a>참고 항목
최근 개발 작업에 대한 자세한 내용은 [Microsoft Intune의 새로운 기능](whats-new-in-microsoft-intune.md)을 참조하세요.

