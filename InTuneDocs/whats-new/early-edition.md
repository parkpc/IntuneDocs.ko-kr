---
title: "초기 버전 | Microsoft 문서"
description: 
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 04/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: e5dd7cb5b320df7f443b52a1b502027fa3c4acaf
ms.openlocfilehash: 31f984fabd2373d242e5e3399bd0c82fbaf53070
ms.lasthandoff: 04/19/2017


---


# <a name="the-early-edition-for-microsoft-intune---april-2017"></a>Microsoft Intune 초기 버전 - 2017년 4월

**초기 버전**에서는 Microsoft Intune의 향후 릴리스에서 도입될 기능의 목록을 제공합니다. 이 정보는 NDA 하에 매우 제한적으로 제공되며, 변경될 수 있습니다. 여기 나열된 일부 기능은 마감일을 맞추지 못할 위험이 있으며 다음 릴리스까지 지연될 수 있습니다. 다른 기능은 고객용 준비 상태를 확인하기 위해, 파일럿(플라이팅) 테스트 중 입니다. 질문이나 궁금한 내용이 있으면 Intune/PM 담당자에게 연락하세요.

이 페이지는 정기적으로 업데이트됩니다. 추가 업데이트가 있는지 다시 확인하세요.

> [!Note]
> Intune에 대해 다음 변경 사항을 개발 중입니다. 최종적으로는 이 모든 기능이 하이브리드 고객 배포(Intune과 Configuration Manager )용으로 지원될 예정입니다. 새로운 하이브리드 기능에 대한 자세한 내용은 [hybrid What’s New page](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management)(하이브리드 새로운 기능 페이지)를 참조하세요.

## <a name="new-capabilities"></a>새로운 기능

### <a name="improved-app-install-status-for-the-windows-10-company-portal-app---676495--"></a>Windows 10 회사 포털 앱에 대해 앱 설치 상태 개선 <!--676495-->

Windows 10 회사 포털 앱에서는 이제 회사 포털에서 시작된 모든 최신 앱 설치에 대한 앱 설치 진행률 표시줄을 제공합니다.

### <a name="improved-status-messaging-in-the-company-portal-app-for-ios---744866--"></a>iOS용 회사 포털 앱에서 상태 메시지 개선 <!--744866-->

이제 iOS용 회사 포털 앱 내에서 더 구체적인 새 오류 메시지가 표시되므로 장치에서 진행되는 상황에 대한 정보에 더 쉽게 액세스할 수 있습니다. 기존에 이러한 오류 사례는 "회사 포털을 일시적으로 사용할 수 없음"이라는 일반 오류 메시지에 포함되었습니다. 또한 사용자가 인터넷에 연결되어 있지 않을 때 iOS에서 회사 포털을 시작하는 경우 이제 "인터넷 연결 없음"이라는 상태 표시줄이 홈페이지에 지속적으로 표시됩니다.

### <a name="myapps-available-for-managed-browser---822308-822303--"></a>Managed Browser에 사용할 수 있는 MyApps <!--822308, 822303-->

Microsoft MyApps는 이제 Managed Browser 내에서 더 나은 지원을 제공합니다. 관리 대상으로 지정되지 않은 Managed Browser 사용자는 MyApps 서비스로 직접 연결되므로 관리자가 프로비전한 SaaS 앱에 액세스할 수 있습니다. Intune 관리 대상으로 지정된 사용자는 계속 기본 제공 Managed Browser 책갈피에서 MyApps에 액세스할 수 있습니다.

### <a name="new-icons-for-the-managed-browser-and-the-company-portal---918433-918431--"></a>Managed Browser 및 회사 포털에 대한 새 아이콘 <!--918433, 918431-->

Managed Browser는 앱의 Android 및 iOS 버전 모두에 대한 업데이트된 아이콘을 수신합니다. 새 아이콘은 업데이트된 Intune 배지를 포함하므로 EM+S(Enterprise Mobility + Security)의 다른 앱과 더 일관된 환경을 제공합니다. [Intune 앱 UI 페이지의 새로운 기능](whats-new-in-intune-app-ui.md)에서 Managed Browser의 새 아이콘을 볼 수 있습니다.

회사 포털도 앱의 Android, iOS 및 Windows 버전에 대해 업데이트된 아이콘을 수신하므로 EM+S의 다른 앱과의 일관성을 개선합니다. 이러한 아이콘은 4월부터 5월 말까지 여러 플랫폼에서 점진적으로 출시됩니다.

### <a name="single-sign-on-support-from-the-company-portal-for-ios-to-outlook-for-ios---834012--"></a>iOS용 회사 포털에서 iOS용 Outlook으로의 Single Sign-On 지원 <!--834012-->

사용자는 같은 장치에서 같은 계정으로 iOS용 회사 포털 앱에 로그인되어 있는 경우 더 이상 Outlook 앱에 로그인할 필요가 없습니다. 사용자는 Outlook 앱을 시작할 때 계정을 선택하여 자동으로 로그인할 수 있습니다. 이 기능을 다른 Microsoft 앱에 추가하는 작업도 진행하는 중입니다.

### <a name="sign-in-progress-indicator-in-android-company-portal---953374--"></a>Android 회사 포털의 로그인 진행률 표시기 <!--953374-->

Android 회사 포털 앱의 업데이트에는 사용자가 앱을 시작하거나 다시 시작할 때 로그인 진행률 표시기가 표시됩니다. 표시기에서는 "연결 중..."에서부터 "로그인 중...", "보안 요구 사항을 확인하는 중..."까지 새로운 상태를 진행한 후 사용자가 앱에 액세스할 수 있도록 허용합니다. [Intune 앱 UI 페이지의 새로운 기능](whats-new-in-intune-app-ui.md)에서 Android용 회사 포털 앱의 새 화면을 볼 수 있습니다.


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

#### <a name="how-does-this-affect-me"></a>이 변경 사항은 어떤 영향을 미치나요?

Intune PC 에이전트를 통해 관리되는 장치의 기존 배포에는 아무런 영향을 주지 않습니다. 그러나 마이그레이션 후에는 이전에 대상으로 하지 않았던 Intune PC 에이전트를 통해 관리되는 새 장치에 마이그레이션된 appx를 배포할 수 없습니다.

#### <a name="what-action-do-i-need-to-take"></a>수행해야 하는 작업

마이그레이션 후 새 PC 배포를 수행하려면 appx를 PC appx로 다시 업로드해야 합니다. 자세한 내용은 [Appx changes in Intune on Azure](https://aka.ms/appxchange)(Azure의 Intune에서 Appx 변경 사항)를 참조하세요.  


## <a name="public-preview-of-the-new-intune-admin-experience-on-azure---736542--"></a>Azure의 새 Intune 관리 환경에 대한 공개 미리 보기<!--736542-->

2017년 초에 Microsoft에서는 전체 관리 환경을 Azure로 마이그레이션합니다. 이를 통해 Graph API를 사용하여 확장 가능한 최신 서비스 플랫폼에서 핵심 EMS 워크플로에 대한 강력한 통합 관리를 지원합니다.

새 평가판 테넌트에서는 이번 달에 Azure Portal에서 새 관리 환경의 공개 미리 보기를 표시하기 시작합니다. 미리 보기 상태에서는 기존 Intune 콘솔의 기능과 패리티가 반복적으로 제공됩니다.

Azure Portal의 관리 환경에서는 이미 발표된 새 그룹화 및 대상 지정 기능을 사용합니다. 따라서 기존 테넌트가 새 그룹화 환경으로 마이그레이션될 때 사용자도 마이그레이션되어 테넌트에 새 관리 환경의 미리 보기가 표시됩니다. 그 동안 테넌트가 마이그레이션될 때까지 새 기능을 테스트하거나 살펴보려는 경우 새 Intune 평가판 계정에 등록하거나 [새 설명서](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune)를 살펴보세요.

### <a name="support-for-managed-configuration-options-for-android-apps----621621---"></a>Android 앱에 대해 관리되는 구성 옵션 지원 <!-- 621621 -->

관리되는 구성 옵션을 지원하는 Play 스토어의 Android 앱을 Intune에서 구성할 수 있습니다.  이 기능을 통해 IT에서는 앱에서 지원하는 구성 값 목록을 볼 수 있으며, 이 기능에서는 이러한 값을 구성할 수 있도록 하는 최고의 단계별 UI를 제공합니다.

### <a name="remote-assistance-for-android-devices----675418---"></a>Android 장치에 대한 원격 지원 <!-- 675418 -->

Intune에서는 [TeamViewer](https://www.teamviewer.com) 소프트웨어(별매)를 사용하여 Android 장치를 실행하는 사용자에게 원격 지원을 제공할 수 있도록 지원합니다.

### <a name="new-android-policy-for-complex-pins----722069---"></a>복합 PIN에 대한 새 Android 정책 <!-- 722069 -->

Android 5.0 이상을 실행하는 장치에 대한 Android 장치 프로필에서 복합 숫자의 필수 암호 유형을 설정할 수 있습니다.  이 설정을 사용하면 장치 사용자가 1111 또는 1234와 같은 반복되거나 연속되는 숫자를 포함하는 PIN을 만들지 못하도록 할 수 있습니다.

### <a name="additional-support-for-android-for-work-devices"></a>Android for Work 장치에 대한 추가 지원

- **암호 및 회사 프로필 설정 관리**<!-- 612808 -->

  관리하는 Android for Work 장치에서 암호 및 회사 프로필 설정을 관리할 수 있도록 하는 새 Android for Work 장치 제한 정책을 추가했습니다.

- **회사 및 개인 프로필 간의 데이터 공유 허용**<!-- 1045102 -->

  회사 및 개인 프로필 간의 데이터 공유를 구성할 수 있도록 하는 새 옵션을 통해 Android for Work 장치 제한 프로필의 **회사 프로필과 개인 프로필 간 데이터 공유** 설정을 업데이트했습니다.

- **회사 및 개인 프로필 간의 복사 및 붙여넣기 제한**<!-- 1046094 -->

  Intune에서 Android for Work 장치를 관리할 때 회사 및 개인 앱 간에 복사 및 붙여넣기 작업을 할 수 있습니다. 이제 회사 및 개인 앱 간에 복사 및 붙여넣기 작업을 허용할지 여부를 제한할 수 있는 Android for Work 장치용 사용자 지정 장치 프로필을 추가했습니다.

### <a name="assign-lob-apps-to-ios-and-android-devices----1057568---"></a>iOS 및 Android 장치에 LOB 앱 할당 <!-- 1057568 -->

iOS용 기간 업무 앱(.ipa 파일)과 Android용 LOB 앱(.apk 파일)을 사용자 또는 장치에 할당할 수 있습니다.

###  <a name="new-policies-for-ios-devices----723774-723815-723826-723830-723832---"></a>iOS 장치에 대한 새 정책<!-- 723774, 723815, 723826, 723830, 723832 -->

- **Apps on Home screen**(홈 화면의 앱) - 장치 정책을 사용하여 사용자가 iOS 장치의 홈 화면에서 어떤 앱을 보게 할지 제어할 수 있습니다. 이 정책은 홈 화면의 레이아웃을 변경하지만 지정한 앱 중 설치되지 않은 앱은 배포하지 않습니다.

- **Connections to AirPrint devices**(AirPrint 장치에 대한 연결) - Intune 장치 정책을 사용하여 iOS 장치의 최종 사용자가 연결할 수 있는 AirPrint 장치(네트워크 프린터)를 제어할 수 있습니다.

- **Connections to AirPlay devices**(AirPlay 장치에 대한 연결) - Intune 장치 정책을 사용하여 iOS 장치의 최종 사용자가 연결할 수 있는 AirPlay 장치(Apple TV 등)를 제어할 수 있습니다.

- **Custom lock screen message**(사용자 지정 잠금 화면 메시지) - 사용자 iOS 장치의 잠금 화면에 표시할 사용자 지정 메시지를 구성하여 기본 잠금 화면 메시지를 대체할 수 있습니다.

- **Web content filter**(웹 콘텐츠 필터) - iOS 장치 사용자가 방문할 수 있는 웹 사이트를 다음 두 가지 방법 중 하나를 사용하여 제어할 수 있습니다.

  - Apple 기본 제공 웹 콘텐츠 필터를 사용하여 허용된 URL 및 차단된 URL을 추가합니다.
  - Safari 브라우저에서 지정한 웹 사이트만 액세스할 수 있도록 허용합니다. 지정한 각 사이트에 대한 책갈피가 Safari에서 만들어집니다.


### <a name="restrict-push-notifications-for-ios-apps----723767---"></a>iOS 앱에 대한 푸시 알림 제한 <!-- 723767 -->

Intune 장치 제한 프로필에서 iOS 장치에 대해 다음과 같은 알림 설정을 구성할 수 있습니다.

- 지정된 앱에 대한 알림을 완전히 켜거나 끕니다.
- 지정한 앱에 대해 알림 센터의 알림을 켜거나 끕니다.
- 경고 유형을 **없음**, **배너** 또는 **Modal Alert**(모달 경고)로 지정합니다.
- 이 앱에 대해 배지를 허용할지 여부를 지정합니다.
- 알림 소리를 허용할지 여부를 지정합니다.

### <a name="configure-ios-apps-to-run-in-single-app-mode-autonomously----737837---"></a>iOS 앱이 자체적으로 단일 앱 모드로 실행되도록 구성 <!-- 737837 -->

Intune 장치 프로필을 사용하여 iOS 장치에서 지정된 앱을 자체 단일 앱 모드로 실행하도록 구성할 수 있습니다. 이 모드를 구성하고 앱이 실행되면 장치가 잠기므로 해당 앱만 실행할 수 있습니다. 이 모드의 예로 사용자가 장치에서 테스트를 수행할 수 있도록 앱을 구성하는 경우를 들 수 있습니다. 앱의 작업이 완료되거나 이 정책을 제거하면 장치가 일반 상태로 돌아옵니다.

### <a name="configure-trusted-domains-for-email-and-web-browsing-on-ios-devices----723765---"></a>iOS 장치에서 메일 및 웹 검색을 위해 신뢰할 수 있는 도메인 구성 <!-- 723765 -->

iOS 장치 제한 프로필에서 다음과 같은 도메인 설정을 구성할 수 있습니다.

- **표시되지 않은 메일 도메인** - 사용자가 보내거나 받는 메일 중 여기에 지정하는 도메인과 일치하지 않는 메일은 신뢰할 수 없는 것으로 표시됩니다.

- **관리되는 웹 도메인** - 여기에 지정하는 URL에서 다운로드한 문서는 관리되는 문서로 간주됩니다(Safari에만 해당).  

- **Safari 암호 자동 채우기 도메인** - 여기에 지정하는 패턴과 일치하는 URL에서만 사용자가 Safari에 암호를 저장할 수 있습니다. 이 설정을 사용하려면 장치가 감독 모드여야 하며 여러 사용자용으로 구성되어 있지 않아야 합니다. (iOS 9.3 이상)


### <a name="vpp-apps-available-in-ios-company-portal----748782---"></a>iOS 회사 포털에서 사용할 수 있는 VPP 앱 <!-- 748782 -->

iOS 대량 구매(VPP) 앱을 **사용 가능한** 설치로 최종 사용자에게 할당할 수 있습니다. 최종 사용자는 앱을 설치하려면 Apple 스토어 계정이 필요합니다.

### <a name="synchronize-ebooks-from-apple-vpp-store----800878---"></a>Apple VPP 스토어에서 전자책 동기화 <!-- 800878 -->

Apple 대량 구매 프로그램 스토어에서 구매한 책을 Intune과 동기화하고 사용자에게 이러한 책을 할당할 수 있습니다.

### <a name="multi-user-management-for-samsung-knox-standard-devices----971988---"></a>Samsung KNOX Standard 장치에 대한 다중 사용자 관리 <!-- 971988 -->

Samsung KNOX Standard를 실행하는 장치가 이제 Intune의 다중 사용자 관리에서 지원됩니다. 따라서 최종 사용자가 Azure Active Directory 자격 증명을 사용하여 장치에서 로그인 및 로그아웃할 수 있고 장치는 사용 여부와 관계없이 중앙에서 관리됩니다.  최종 사용자가 로그인하면 앱에 액세스할 수 있고 추가로 앱에 정책을 적용할 수 있습니다. 사용자가 로그아웃하면 모든 앱 데이터가 지워집니다.

### <a name="additional-windows-device-restriction-settings----818566---"></a>추가 Windows 장치 제한 설정 <!-- 818566 -->

추가 Edge 브라우저 지원, 장치 잠금 화면 사용자 지정, 시작 메뉴 사용자 지정, Windows 추천 검색이 설정된 배경 화면, 프록시 설정 등과 같은 추가 Windows 장치 제한 설정에 대한 지원을 추가했습니다.

### <a name="multi-user-support-for-windows-10-creators-update----822547---"></a>Windows 10 크리에이터 업데이트에 대한 다중 사용자 지원 <!-- 822547 -->

Windows 10 크리에이터 업데이트를 실행하고 Azure Active Directory 도메인에 가입된 장치에 대한 다중 사용자 관리 지원을 추가했습니다. 따라서 여러 표준 사용자가 Azure AD 자격 증명을 사용하여 장치에 로그온할 때 각 사용자는 자신의 사용자 이름에 할당된 앱과 정책을 수신합니다. 현재 사용자가 앱 설치와 같은 셀프 서비스의 경우 회사 포털을 사용할 수 없습니다.

### <a name="fresh-start-for-windows-10-pcs---1004830---"></a>Windows 10 PC에서의 새로운 시작<!-- 1004830 -->

이 릴리스에서는 Windows 10 PC에 대한 새 [새로 시작] 장치 동작을 추가했습니다.  이 작업을 실행하면 PC에 설치된 모든 앱이 제거되고 PC가 자동으로 최신 버전의 Windows로 업데이트됩니다. 이 작업은 종종 새 PC와 함께 제공되는 미리 설치된 OEM 앱을 제거하는 데 사용할 수 있습니다. 이 장치 작업을 실행할 때 사용자 데이터를 유지할지 여부를 구성할 수 있습니다.

### <a name="additional-windows-10-upgrade-paths----903672---"></a>추가 Windows 10 업그레이드 경로 <!-- 903672 -->

이제 버전 업그레이드 정책을 만들어 장치를 다음과 같은 추가 Windows 10 버전으로 업그레이드할 수 있습니다.

- Windows 10 Professional
- Windows 10 Professional KN
- Windows 10 Professional Education
- Windows 10 Professional Education N

### <a name="bulk-enroll-windows-10-devices----747607---"></a>Windows 10 장치 대량 등록 <!-- 747607 -->

WCD(Windows 구성 디자이너)를 사용하여 Azure Active Directory 및 Intune에 대한 Windows 10 크리에이터 업데이트를 실행하는 많은 장치를 연결할 수 있습니다. Azure AD 테넌트에 대한 자동 MDM 등록을 사용하도록 설정하려면 Windows 구성 디자이너를 사용하여 Azure AD 테넌트에 장치를 연결하는 프로비전 패키지를 만들고, 이 패키지를 대량으로 등록 및 관리할 회사 소유 장치에 적용합니다. 패키지가 장치에 적용되면, 장치가 Azure AD에 연결되고 Intune에 등록되며 Azure AD 사용자가 로그온할 수 있는 준비를 갖추게 됩니다.  Azure AD 사용자는 이러한 장치에서 표준 사용자이며 할당된 정책 및 필수 앱을 수신합니다. 셀프 서비스 및 회사 포털 시나리오의 경우 이번에는 지원되지 않습니다.

### <a name="new-mam-settings-for-pin-and-managed-storage-locations----58112-736644---"></a>PIN 및 관리되는 저장소 위치에 대한 새 MAM 설정 <!-- 58112, 736644 -->

MAM(모바일 응용 프로그램 관리) 시나리오에 도움이 되는 두 가지 새 앱 설정이 제공됩니다.

- **Disable app PIN when device PIN is managed**(장치 PIN이 관리되는 경우 앱 PIN 사용 안 함) - 등록된 장치에 장치 PIN이 있는지 검색하고 있으면 앱 보호 정책에 따라 트리거되는 앱 PIN을 건너뜁니다. 이 설정을 사용하면 등록된 장치에서 MAM 지원 응용 프로그램을 여는 사용자에게 PIN 프롬프트가 표시되는 횟수를 줄일 수 있습니다. 이 기능은 Android 및 iOS 모두에 제공됩니다.

- **Select which storage services corporate data can be saved to**(회사 데이터를 저장할 저장소 서비스 선택) - 회사 데이터를 저장할 저장소 위치를 지정할 수 있습니다. 사용자가 선택된 저장소 위치 서비스에 저장할 수 있으므로 나열되지 않은 다른 저장소 위치는 모두 차단됩니다.

  지원되는 저장소 위치 서비스 목록:

  - OneDrive
  - 비즈니스 SharePoint Online
  - 로컬 저장소


### <a name="see-also"></a>참고 항목
최근 개발 작업에 대한 자세한 내용은 [Microsoft Intune의 새로운 기능](whats-new-in-microsoft-intune.md)을 참조하세요.

