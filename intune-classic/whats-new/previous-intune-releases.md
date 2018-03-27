---
title: 이전 릴리스
description: ''
keywords: ''
author: barlanmsft
ms.author: barlan
manager: dougeby
ms.date: 02/13/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 45dad14a-d412-488d-bb1e-ad990ea503df
ROBOTS: NOINDEX,NOFOLLOW
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 76e53cabba9b684170d659ae5b8ef884bfe9abaa
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2018
---
# <a name="previous-intune-releases"></a>이전 Intune 릴리스

이 페이지는 [Microsoft Intune의 새로운 기능](whats-new-in-microsoft-intune.md)에서 제공된 공지 사항이 포함되어 있는 목록입니다.

[!INCLUDE[wit_nextref](../includes/whats-new-last-six-months.md)]

## <a name="july-2016"></a>2016년 7월

### <a name="app-management"></a>앱 관리

__앱 프로비전 프로필 업데이트 환경 개선__ Apple iOS LOB(기간 업무) 모바일 앱은 프로비전 프로필을 포함하고 인증서로 코드에 서명하여 빌드됩니다. 앱이 iOS 장치에서 실행되면 iOS는 iOS 앱의 무결성을 확인하고 프로비전 프로필에 정의된 정책을 적용합니다.

일반적으로 앱에 서명하기 위해 사용하는 엔터프라이즈 서명 인증서는 3년 동안 유지됩니다. 그러나 프로비전 프로필은 1년 후에 만료됩니다. 이 업데이트를 사용하면 Intune은 인증서가 여전히 유효한 동안 만료일이 다가오는 앱이 있는 장치에 새 프로비전 프로필 정책을 미리 배포하기 위한 도구를 제공합니다. 자세한 내용은 [iOS 모바일 프로비전 프로필 정책을 사용하여 LOB(기간 업무) 앱을 최신 상태로 유지](/intune-classic/deploy-use/ios-mobile-app-provisioning-profiles)를 참조하세요.
<!--- TFS 1280247--->

__Intune용 Xamarin SDK 앱을 사용할 수 있음__ Intune 앱 SDK Xamarin 구성 요소를 사용하면 Xamarin으로 빌드된 모바일 iOS 및 Android 앱에서 Intune 모바일 앱 관리 기능을 설정할 수 있습니다. [Xamarin 스토어](https://components.xamarin.com/view/Microsoft.Intune.MAM) 또는 [Microsoft Intune Github 페이지](https://github.com/msintuneappsdk)에서 해당 구성 요소를 찾을 수 있습니다.
<!--- TFS 1061478 --->

### <a name="device-management"></a>장치 관리
__증가된 장치 등록 제한__ Intune은 사용자당 구성 가능한 최대 장치 등록 제한을 5대에서 15대로 늘립니다.
<!---TFS 1289896 --->

__Intune 클라이언트 소프트웨어를 실행하는 Windows PC용 TeamViewer__
[TeamViewer](/intune-classic/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client).
<!---TFS 1284856--->

### <a name="company-portal-updates"></a>회사 포털 업데이트

__회사 포털 웹 사이트__
- **Windows 장치를 등록할 때 향상된 최종 사용자 환경**<br/>
조건부 액세스를 사용하는 경우 회사 포털 웹 사이트에서 Windows 8.1, Windows 10 Desktop 및 Windows 10 Mobile 등록 단계가 명확해졌습니다. 이제 "장치 등록" 및 "작업 공간 연결" 단계가 별도로 표시되므로, WPJ(작업 공간 연결) 오류가 발생한 경우 장치의 상태를 더욱 쉽게 확인하고 프로세스를 완료할 수 있습니다. 또한 별도의 단계를 통해 IT 관리자의 문제 해결 프로세스를 간소화할 수 있을 것으로 예상됩니다. 이전에는 최종 사용자가 등록하려고 할 때 WPJ를 제외한 모든 등록 단계가 정상적으로 수행되면, 등록된 장치가 사용자의 장치 목록에 나타나지 않아 혼동을 줄 수 있었습니다.

__OWA(Outlook Web Access)__
- **Android 회사 포털 앱**<br/>
Android 최종 사용자에게 장치에 필요한 인증서가 없다는 오류 메시지가 표시될 경우 "이 문제를 해결하는 방법" 단추를 탭하면 IT 관리자가 인증서 문제를 해결할 수 있는 [단계](/intune-classic/troubleshoot/troubleshoot-device-enrollment-in-intune#android-certificate-issues)를 확인할 수 있습니다.

- **테스트용으로 앱 설치를 등록된 장치로 제한**<br/>
장치가 Android용 Intune 회사 포털 앱을 사용하여 Intune에 등록되어 있지 않으면 더 이상 Android 장치에 회사 포털 웹 사이트를 통해 응용 프로그램을 설치할 수 없습니다.
<!---TFS 1299082--->

__iOS__
- **iOS 회사 포털 앱의 장치 등록 관리자 계정의 변경 내용**<br/>
성능과 확장성을 개선하기 위해, Intune은 iOS 회사 포털 앱의 **내 장치** 창에 더 이상 모든 장치 등록 관리자(DEM)를 표시하지 않을 예정입니다. 앱을 실행하는 로컬 장치가 회사 포털 앱을 통해 등록된 경우에만 표시합니다.

DEM 사용자는 로컬 장치에서 작업을 수행할 수 있지만 다른 등록된 장치의 원격 관리는 Intune 관리 콘솔에서만 수행할 수 있습니다. 또한 Intune은 Apple 장비 등록 프로그램 또는 Apple Configurator 도구에서 DEM 계정 사용을 더 이상 지원하지 않습니다. 두 등록 방법은 모두 공유 iOS 장치에 대한 사용자가 지정되지 않은 등록을 이미 지원합니다.

공유 장치에 대한 사용자가 지정되지 않은 등록을 사용할 수 없는 경우만 DEM 계정을 사용합니다. 자세한 내용은 [Microsoft Intune에서 장치 등록 관리자를 사용하여 회사 소유의 장치 등록](/intune-classic/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)을 참조하세요.
<!---TFS 1233681--->

### <a name="change-of-names-for-windows-features"></a>Windows 기능의 이름 변경
- 이제 [Microsoft Passport for Windows](/intune-classic/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune)를 **비즈니스용 Windows Hello**라고 합니다.
- [엔터프라이즈 데이터 보호](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune)를 **Windows 정보 보호**라고 합니다.


## <a name="june-2016"></a>2016년 6월
### <a name="intune-service-health"></a>Intune 서비스 상태
Intune에 대한 서비스 상태 정보는 다른 Microsoft 서비스와 함께 중앙 위치로 이동되었습니다. 이 정보는 이제 Office 365 관리 포털의 서비스 상태에서 찾을 수 있습니다. 자세한 내용은 [이 블로그 게시물](https://blogs.technet.microsoft.com/enterprisemobility/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/)을 참조하세요.

### <a name="app-management"></a>앱 관리
- **Windows 10 엔터프라이즈 데이터 정책 구성 환경이 개선되었습니다.** 앱 규칙 생성, 네트워크 경계 정의 지정 및 기타 엔터프라이즈 데이터 보호 설정과 관련된 Windows 10 엔터프라이즈 데이터 보호 정책 구성 환경이 개선되었습니다. 자세한 내용은 [Create an enterprise data protection (EDP) policy using Microsoft Intune](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune)(Microsoft Intune을 사용하여 EDP(엔터프라이즈 데이터 보호) 정책 만들기)을 참조하세요.


### <a name="device-management"></a>장치 관리
- **원치 않는 앱으로부터 보호하기 위한 Windows Defender 정책 설정.** **사용자 동의 없이 설치된 응용 프로그램 검색**이라고 하는 새로운 Windows Defender 설정이 Windows 10 Desktop 및 Mobile에 대한 일반 구성 정책에 추가되었습니다. 이 설정을 사용하여 Windows Defender에서 사용자 동의 없이 설치된 소프트웨어로 분류된 프로그램에 대해 등록된 Windows 데스크톱 컴퓨터를 보호할 수 있습니다. 실행 중인 이러한 응용 프로그램으로부터 보호하거나 감사 모드를 사용하여 사용자 동의 없이 응용 프로그램이 설치될 때 보고할 수 있습니다. 자세한 내용은 [Microsoft Intune의 Windows 10 정책 설정](/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune)을 참조하세요.
<!---TFS 1244478--->

### <a name="conditional-access"></a>조건부 액세스
- **Intune에 대한 Cisco ISE 네트워크 액세스 제어 정책.**  Cisco ISE(Identity Service Engine) 2.1 및 Microsoft Intune을 사용하는 고객은 ISE에서 네트워크 액세스 제어 정책을 설정할 수 있습니다.

    이 정책을 사용하여 WiFi 또는 VPN을 통해 네트워크에 연결해야 하는 장치는 다음 조건을 충족해야 액세스가 허용됩니다.

    * Intune에서 관리되어야 합니다.
    * 배포된 Intune 준수 정책을 준수해야 함

 비규격 장치의 최종 사용자는 액세스하기 위해 등록하고 준수 문제를 해결하도록 요구됩니다.
- **브라우저에 대한 조건부 액세스.** 관리되는 규격 iOS 및 Android 장치의 지원되는 웹 브라우저에서만 액세스할 수 있도록 [Exchange Online](/intune-classic/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune)에 대한 조건부 액세스 정책을 설정할 수 있습니다. iOS 및 Android 장치를 사용하여 OWA(Outlook Web Access) 및 SharePoint 사이트에 로그인하려는 최종 사용자에게는 Intune에 장치를 등록하고 비규격 문제를 해결해야 로그인을 완료할 수 있다는 메시지가 표시됩니다.
<!---TFS 1175844--->

- **Dynamics CRM Online에서 조건부 액세스를 지원합니다.** 정책을 준수하고 관리되는 iOS 및 Android 장치에서만 액세스할 수 있도록, [Dynamics CRM Online](/intune-classic/deploy-use/restrict-access-to-dynamics-crm-online-with-microsoft-intune)에 대한 조건부 액세스 정책을 설정할 수 있습니다. iOS 및 Android에서 Dynamics CRM 모바일 앱에 로그인하려고 하는 최종 사용자에게 Intune에 등록하고 로그인을 완료하기 전에 모든 비호환성 문제를 해결해야 한다는 메시지가 표시됩니다.
<!---TFS1295358--->

### <a name="intune-company-portal-updates"></a>Intune 회사 포털 업데이트

__Android 회사 포털 앱__

- IT 관리자가 새 “장치가 알 수 없는 소스의 앱 설치를 방지해야 함(Android 4.0 이상)” 정책을 적용하면 Android 4.0 이상 장치를 사용하는 최종 사용자에게 "알 수 없는 소스에서의 설치를 금지해야 합니다." 메시지가 표시됩니다. **설정** > **보안**으로 이동한 후 **알 수 없는 원본**을 해제해야 합니다. 규정 준수 메시지의 링크를 클릭하면 해당 메시지에 대한 추가 [정보](/intune-user-help/you-are-asked-to-turn-off-unknown-sources-android)와 설정을 해제해야 하는 이유가 표시됩니다.

- IT 관리자가 새 “앱의 보안 위협 검색을 사용하도록 장치가 설정되어 있어야 함(Android 4.0 이상)” 정책을 적용하면 Android 4.0 이상 장치를 사용하는 최종 사용자에게 "장치의 보안 위협 검색" 메시지가 표시됩니다. 사용자는 **설정** > **Google** > **보안**으로 이동한 후 **장치의 보안 위협 검색**을 켜야 합니다. 규정 준수 메시지의 링크를 클릭하면 해당 메시지에 대한 추가 [정보](/intune-user-help/you-are-asked-to-turn-on-scan-device-for-security-threats-android)와 설정을 켜야 하는 이유가 표시됩니다.

- IT 관리자가 새 "USB 디버깅을 사용하지 않도록 설정되어야 함(Android 4.2 이상)" 정책을 적용하면 Android 4.2 이상 장치를 사용하는 최종 사용자에게 "USB 디버깅을 사용하지 않도록 설정해야 합니다." 메시지가 표시됩니다. **설정** > **개발자 옵션**으로 이동하여 **USB 디버깅**을 해제해야 합니다. 규정 준수 메시지의 링크를 클릭하면 해당 메시지에 대한 추가 [정보](/intune-user-help/you-are-asked-to-turn-off-usb-debugging-android)와 설정을 해제해야 하는 이유가 표시됩니다.

- IT 관리자가 새 "최소 Android 보안 패치 수준(Android 6.0 이상)" 정책을 적용하면 Android 6.0 이상 장치를 사용하는 최종 사용자에게 "이 장치는 최소 Android 보안 패치 수준을 충족하지 않습니다." 메시지가 표시됩니다. 사용자는 필수 보안 패치를 설치해야 합니다. 규정 준수 메시지의 링크를 클릭하면 필수 보안 패치를 설치하고 현재 설치되어 있는 보안 패치를 확인하는 방법에 대한 [정보](/intune-user-help/you-are-asked-to-turn-on-scan-device-for-security-threats-android)가 표시됩니다.

__iOS 회사 포털 앱__

- 최종 사용자가 기간 업무 앱을 설치하는 경우, 향상된 앱 설치 환경이 표시됩니다. 앱 설치가 너무 오래 걸리면, 사용자는 동기화 프로세스가 다시 시작되도록 장치를 수동으로 동기화할 수 있습니다. 최종 사용자 지침을 검토하려면 [iOS 장치를 수동으로 동기화](/intune-user-help/sync-your-device-manually-ios)를 참조하세요.

- iOS에 대한 Microsoft Intune 회사 포털 앱은 iOS 버전 8.0 이상을 지원하도록 업데이트되었습니다. 이 업데이트를 사용하면 장치가 iOS 버전 8.0 이상을 실행하는 경우 최종 사용자가 회사 포털 앱을 설치하고 Intune에 새 장치를 등록할 수 있습니다. 지원되지 않는 iOS 버전을 실행 중이고 이미 등록된 장치가 있는 사용자는 자신의 장치에 있는 회사 포털 앱을 계속 사용할 수 있습니다.

## <a name="may-2016"></a>2016 년 5 월
이 모든 기능은 하이브리드 배포에 대해서도 지원됩니다(Configuration Manager with Intune). 새로운 하이브리드 기능에 대한 자세한 내용은 [Hybrid What’s New](https://technet.microsoft.com/library/mt718155.aspx)(하이브리드의 새로운 기능) 페이지를 참조하세요.

### <a name="documentation"></a>문서
[docs.microsoft.com](https://docs.microsoft.com/intune)의 미리 보기 버전에 오신 것을 환영합니다!
완전히 새로운 최신 콘텐츠 플랫폼으로, 사용자와 고객이 Intune을 쉽게 이해하고 사용할 수 있도록 설계되었습니다.
새로운 모든 기능에 대한 내용을 보려면 [Introducing docs.microsoft.com](https://docs.microsoft.com/teamblog/introducing-docs-microsoft-com/)(docs.microsoft.com 소개)을 참조하세요.

### <a name="intune-service-health"></a>Intune 서비스 상태
Intune에 대한 서비스 상태 정보는 다른 Microsoft 서비스와 함께 중앙 위치로 이동되었습니다. 이 정보는 이제 [Office 365 관리 포털](https://portal.office.com/Admin/Default.aspx)의 **서비스 상태**에서 찾을 수 있습니다.
자세한 내용은 [이 블로그 게시물](https://blogs.technet.microsoft.com/microsoftintune/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/)을 참조하세요.

### <a name="app-management"></a>앱 관리
- **MAM SDK: PIN 길이 구성 지원.** 장치 PIN과 유사하게 MAM 앱에 대한 PIN의 길이를 지정할 수 있게 됩니다. 이렇게 하려면, 여러분이 설정하는 새로운 제한 사항을 최종 사용자가 준수해야 합니다. 좀 더 길어진 입력을 설명하기 위해 약간 수정된 PIN 화면이 표시됩니다. 자세한 내용은 [Android에 대한 MAM 정책 설정](/intune-classic/deploy-use/ios-mam-policy-settings)을 참조합니다.

- **비즈니스용 Skype for iOS 및 Android.** 이제 [등록 정책 없이 MAM](/intune-classic/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune)을 통해 비즈니스용 Skype를 관리할 수 있습니다. 사용자가 로그인하면 MAM 정책이 적용됩니다.

- **MAM 정책을 통해 새로운 앱을 관리할 수 있음.** 이제 Intune에 등록하지 않은 장치에서 Android용 Microsoft Word, Excel 및 PowerPoint 앱을 MAM 정책과 연결할 수 있습니다. 지원되는 앱의 전체 목록을 확인하려면 [Microsoft Intune application partners](https://www.microsoft.com/server-cloud/products/microsoft-intune/partners.aspx)(Microsoft Intune 응용 프로그램 파트너) 페이지의 Microsoft Intune 모바일 응용 프로그램 갤러리로 이동합니다.


### <a name="company-portal-updates"></a>회사 포털 업데이트

#### <a name="android-company-portal-app"></a>Android 회사 포털 앱
- **최종 사용자 알림 메시지**: 이제 최종 사용자가 회사 포털에 장치를 등록하거나 회사 포털에서 장치를 제거하는 경우 Android 회사 포털 앱에 알림 메시지가 표시됩니다.

- **Android 회사 포털 앱의 장치 등록 관리자 계정의 변경 내용.** 성능과 확장성을 개선하기 위해 Intune은 Android 회사 포털 앱의 내 장치 창에 모든 DEM(장치 등록 관리자)을 더 이상 표시하지 않습니다. 앱을 실행하는 로컬 장치가 회사 포털 앱을 통해 등록된 경우에만 표시합니다. DEM 사용자가 로컬 장치에서 작업을 수행할 수 있지만, 등록된 다른 장치의 원격 관리는 Intune 관리 콘솔에서만 수행될 수 있습니다.

#### <a name="company-portal-website"></a>회사 포털 웹 사이트
- **회사 포털 웹 사이트: 장치 식별 배너를 통해 최종 사용자에게 더 많은 정보를 제공합니다.** 이제 최종 사용자가 회사 포털 웹 사이트를 사용할 때 자신이 선택한 장치를 더 쉽게 식별할 수 있습니다. 잘못된 장치를 선택하면 홈페이지 배너의 **여기를 누르세요** 링크를 탭하여 올바른 장치를 선택할 수 있습니다.

### <a name="service-deprecation"></a>서비스 중단
- **Intune 뷰어 앱.** 2016년 8월부터 새 RMS 공유 앱의 릴리스에서 다음 Intune 뷰어 앱을 제거합니다.
    - Intune AV 뷰어
    - Intune PDF 뷰어
    - Google Play의 Android용 Intune 이미지 뷰어

  Intune 뷰어 앱을 사용하는 대신 새로운 Android용 Microsoft Rights Management 공유 앱(RMS 공유)을 사용하는 것이 좋습니다. 이 앱을 통해 세 개의 별도 앱이 아니라 하나의 앱을 배포하여 Android 장치에서 회사 파일을 안전하게 볼 수 있습니다. RMS 공유 앱에 대해 자세히 알아보세요(설명서 링크 사용).

- **사용자 지정 그룹을 알림 규칙의 대상으로 지정하는 기능 제거.**
Intune 알림 규칙은 Intune에서 메일 경고를 보낼 대상자를 정의합니다. 현재 직접 만든 Intune 장치 그룹의 모든 장치 사용자에게 메일을 보내도록 알림 규칙을 구성할 수 있습니다. 2016년 6월 1일경부터는 사용자가 만든 그룹을 대상으로 지정하는 기능이 더 이상 지원되지 않습니다.

    이제 Microsoft Intune 관리 콘솔에서 직접 만든 그룹을 알림 규칙 대상으로 지정하려면 다음 단계를 수행하세요.

    **관리자** 작업 영역에서 **알림 규칙** > **새 규칙 만들기**를 클릭합니다.

    알림 규칙 만들기 마법사의 2단계에서 규칙의 대상이 되는 장치 그룹을 선택합니다. 이 단계 즉, “장치 그룹 선택”은 Intune 콘솔에서 제거됩니다.

    이러한 변경을 준비하기 위한 타임라인은 다음과 같습니다.
    - 2016년 6월에는 새 테넌트에 알림 규칙 만들기 마법사의 2단계가 표시되지 않습니다. 기존 테넌트는 영향을 받지 않습니다.
    - 2016년 8월경에는 일부 기존 테넌트에 마법사의 "장치 그룹 선택"이 표시되지 않습니다.
    - 2016년 10월경에는 모든 기존 테넌트에 마법사의 "장치 그룹 선택"이 표시되지 않을 것으로 예상됩니다.


- **iOS 회사 포털 앱에 대한 지원의 변경 내용**. 향후 몇 개월 내에 iOS용 Microsoft Intune 회사 포털 앱에 대한 업데이트가 있을 예정입니다. iOS 8.0 이상을 실행하는 장치만 지원됩니다. 사용자는 iOS 8.0 이전 버전을 실행하는 장치를 새로 등록할 수 없습니다. iOS 8.0 이전 버전을 실행하는 장치라도 기존에 등록된 장치는 계속 관리할 수 있으며 제한된 시간 동안은 회사 포털 앱을 계속 사용할 수 있습니다. 그러나 회사 포털 앱의 최신 버전에 액세스하려면 장치가 iOS 8.0 이상을 실행해야 합니다. Intune의 새로운 기능을 완전히 활용하려면 사용자에게 iOS 8.0 이상으로 업데이트하도록 알리는 것이 좋습니다.  


## <a name="april-2016"></a>2016년 4월
이 모든 기능은 하이브리드 고객에 대해서도 지원됩니다(Intune과 통합된 Configuration Manager).

### <a name="app-management"></a>앱 관리
- **MAM 사용자 규정 준수.**
이제 Azure Active Directory(AAD) 테넌트에 속하는 모든 사용자에 대한 응용 프로그램 관리 정책의 [상태](/intune-classic/deploy-use/monitor-mobile-app-management-policies-with-Microsoft-Intune)를 볼 수 있습니다. 여기에는 다음 항목이 포함됩니다.
   - 장치
   - 장치의 앱

   상태 값:

   **Checked in**(체크 인 됨): 사용자에게 정책이 배포되었고, 회사 컨텍스트에서 앱이 사용되었으며, 성공적으로 정책이 수신되었다는 것을 나타냅니다.

    **Not checked in**(체크인 안됨): 사용자에게 정책이 배포되었지만, 그 뒤로 회사 컨텍스트에서 앱이 사용되지 않았다는 것을 나타냅니다.


- **Outlook 연락처 동기화를 방지하기 위한 MAM 컨트롤(Android).**
[모바일 응용 프로그램 관리](/intune-classic/deploy-use/wipe-managed-company-app-data-with-Microsoft-Intune)에 대한 새 설정을 사용할 수 있습니다. 기본 주소록에 이미 저장된 연락처는 삭제됩니다. 이 새로운 설정은 처음에 Android 장치의 Outlook 응용 프로그램에서 지원됩니다.

### <a name="device-management"></a>장치 관리
- **회사 소유 장치에 대한 전화 번호 식별.** "회사"로 분류되는 전화는 이제 전체 전화 번호로 식별됩니다(예: 모바일 장치 인벤토리 보고서를 실행하는 경우). BYOD 전화 번호는 마지막 4자리만 표시되고 ****으로 계속 마스킹됩니다.


### <a name="company-portal-updates"></a>회사 포털 업데이트
**Android 회사 포털 앱** Intune에 장치를 등록하지 않았거나 올바른 인증서가 설치되지 않은 사용자는 Android 회사 포털 앱에 로그인할 수 있으며 “You cannot sign in because your device is missing a required certificate.”(장치에 필요한 인증서가 없어서 로그인할 수 없습니다.)라는 메시지를 보게 됩니다. 메시지에는 “해결 방법” 링크가 포함되며, 사용자가 이 링크를 탭하면 인증서 설치에 대한 지침을 볼 수 있습니다. 최종 사용자가 문제를 해결하기 위해 수행하는 단계를 보려면 [장치에 필요한 인증서가 없습니다.](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_cert_missing) 참조하세요.

**iOS 회사 포털 앱** 홈 화면의 콘텐츠를 새로 고치기 위해 끌어오기-새로 고침 작업에 대한 지원이 추가되었습니다. 여기에는 나열된 앱, 나열된 장치, 및 IT 연락처 정보가 포함됩니다. 끌어오기-새로 고침 작업은 정책 또는 준수 정보를 확인하지 않습니다. 이 작업은 현재 장치의 타일을 선택하고 **동기화** 단추를 탭하여 수행할 수 있습니다.

**Windows 10 Mobile 및 Windows Phone 8.1 회사 포털 앱** 최종 사용자가 기간 업무 앱을 설치하는 경우, 향상된 앱 설치 환경이 표시됩니다. 앱 설치가 너무 오래 걸리면, 사용자는 동기화 프로세스가 다시 시작되도록 장치를 수동으로 동기화할 수 있습니다. 최종 사용자 지침을 검토하려면 [앱 설치 속도를 높이기 위해 장치를 수동으로 동기화](https://technet.microsoft.com/library/mt427782.aspx#BKMK_win10m_wp81_sync_manually)를 참조하세요.

 **회사 포털 웹 사이트** Windows 10 Mobile 및 Windows Phone 8.1 사용자가 기간 업무 앱을 설치하는 경우, 다음과 같은 새로운 상태가 표시되어, 사용자의 설치 상태에 대해 보다 자세한 정보를 제공하게 됩니다.

* **장치가 동기화될 때까지 기다리는 중** – 사용자가 “설치”를 탭했고 이제 장치가 Intune 인프라와의 동기화를 시도합니다. 설치를 완료하려면 그 전에 동기화가 필요합니다. "장치가 동기화될 때까지 기다리는 중" 메시지 역시 사용자가 탭하면, 동기화 프로세스가 너무 오래 걸리거나 멈춘 경우 Intune에서 장치를 수동으로 동기화하는 방법에 대한 [지침](https://technet.microsoft.com/library/mt590895.aspx#BKMK_iwp_sync_manually)을 볼 수 있는 링크입니다.
* **다운로드 중** – 사용자의 다운로드 요청이 처리 중이며 장치가 앱을 다운로드 및 설치 중입니다.

이런 상태가 추가되기 전에는, 사용자에게 “설치 중” 상태만 보여줬기 때문에(화면에 수 시간 동안 유지되기도 하는) 앱 설치가 오래 걸리면 혼란스러웠습니다. 새로운 상태가 추가되었기 때문에, 이제 사용자들은 지원을 요청하는 대신 "장치가 동기화될 때까지 기다리는 중" 링크를 클릭하고 지침에 따라서 동기화 프로세스가 재시작되도록 강제 적용할 수 있습니다.

>[!div class="step-by-step"]

>[&larr; **Intune의 새로운 기능**](whats-new-in-microsoft-intune.md)    
