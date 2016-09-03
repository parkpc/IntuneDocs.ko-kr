---
title: "이전 릴리스 | Microsoft Intune"
description: 
keywords: 
author: Lindavr
manager: angrobe
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 45dad14a-d412-488d-bb1e-ad990ea503df
ROBOTS: noindex,nofollow
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 57570fcf2f738b68a01bb1c5fc8962c7ef117920
ms.openlocfilehash: 43546721245f92309d86c496dbcde7900a598ed0


---

# 이전 Intune 릴리스
## 2016년 7월
### 앱 관리
#### 앱 프로비전 프로필 업데이트 환경 개선
Apple iOS LOB(기간 업무) 모바일 앱은 프로비전 프로필을 포함하고 인증서로 코드에 서명하여 빌드됩니다. 앱이 iOS 장치에서 실행되면 iOS는 iOS 앱의 무결성을 확인하고 프로비전 프로필에 정의된 정책을 적용합니다.

일반적으로 앱에 서명하기 위해 사용하는 엔터프라이즈 서명 인증서는 3년 동안 유지됩니다. 그러나 프로비전 프로필은 1년 후에 만료됩니다. 이 업데이트를 사용하면 Intune은 인증서가 여전히 유효한 동안 만료일이 다가오는 앱이 있는 장치에 새 프로비전 프로필 정책을 미리 배포하기 위한 도구를 제공합니다. 자세한 내용은 [iOS 모바일 프로비전 프로필 정책을 사용하여 LOB(기간 업무) 앱을 최신 상태로 유지](/intune/deploy-use/ios-mobile-app-provisioning-profiles)를 참조하세요.
<!--- TFS 1280247--->
#### Intune용 Xamarin SDK 앱을 사용할 수 있음
Intune 앱 SDK Xamarin 구성 요소를 사용하면 Xamarin으로 빌드된 모바일 iOS 및 Android 앱에서 Intune 모바일 앱 관리 기능을 설정할 수 있습니다. [Xamarin 스토어](https://components.xamarin.com/view/Microsoft.Intune.MAM) 또는 [Microsoft Intune Github 페이지](https://github.com/msintuneappsdk)에서 해당 구성 요소를 찾을 수 있습니다.
<!--- TFS 1061478 --->

### 장치 관리
#### 증가된 장치 등록 제한
Intune은 사용자당 구성 가능한 최대 장치 등록 제한을 5대에서 15대로 늘립니다.
<!---TFS 1289896 --->

#### Intune 클라이언트 소프트웨어를 실행하는 Windows PC용 TeamViewer 통합
Intune 클라이언트를 실행하는 Windows PC용 [TeamViewer](https://www.teamviewer.com) 통합을 통해 Windows PC와 원격 지원 세션을 설정하여 최종 사용자 지원 센터 부서를 지원할 수 있습니다. 여기에는 Windows 7, 8, 8.1 및 Windows 10이 포함됩니다. 자세한 내용은 [Microsoft Intune 컴퓨터 클라이언트를 사용한 일반 Windows PC 관리 작업](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md) 항목을 참조하세요.
<!---TFS 1284856--->

### 회사 포털 업데이트
#### 회사 포털 웹 사이트
- **Windows 장치를 등록할 때 향상된 최종 사용자 환경**<br/>
조건부 액세스를 사용하는 경우 회사 포털 웹 사이트에서 Windows 8.1, Windows 10 Desktop 및 Windows 10 Mobile 등록 단계가 명확해졌습니다. 이제 "장치 등록" 및 "작업 공간 연결" 단계가 별도로 표시되므로, WPJ(작업 공간 연결) 오류가 발생한 경우 장치의 상태를 더욱 쉽게 확인하고 프로세스를 완료할 수 있습니다. 또한 별도의 단계를 통해 IT 관리자의 문제 해결 프로세스를 간소화할 수 있을 것으로 예상됩니다. 이전에는 최종 사용자가 등록하려고 할 때 WPJ를 제외한 모든 등록 단계가 정상적으로 수행되면, 등록된 장치가 사용자의 장치 목록에 나타나지 않아 혼동을 줄 수 있었습니다.

#### Android
- **Android 회사 포털 앱**<br/>
Android 최종 사용자에게 장치에 필수 인증서가 없다는 오류 메시지가 표시되면 "이 문제를 해결하는 방법" 단추를 눌러 누락된 인증서를 설치하기 위한 [단계](/intune/enduser/your-device-is-missing-a-required-certificate-android#your-device-is-missing-a-certificate-required-by-your-it-administrator)를 진행할 수 있습니다. 이러한 단계를 완료해도 "누락된 인증서" 오류 메시지가 추가로 표시될 경우 IT 관리자에게 문의하여 IT 관리자가 인증서 문제를 해결하는 데 사용할 수 있는 단계가 포함된 [링크](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#android-certificate-issues)를 제공해야 합니다.

- **테스트용으로 앱 설치를 등록된 장치로 제한**<br/>
장치가 Android용 Intune 회사 포털 앱을 사용하여 Intune에 등록되어 있지 않으면 더 이상 Android 장치에 회사 포털 웹 사이트를 통해 응용 프로그램을 설치할 수 없습니다.
<!---TFS 1299082--->

#### iOS
- **iOS 회사 포털 앱의 장치 등록 관리자 계정의 변경 내용**<br/>
성능과 확장성을 개선하기 위해, Intune은 iOS 회사 포털 앱의 **내 장치** 창에 더 이상 모든 장치 등록 관리자(DEM)를 표시하지 않을 예정입니다. 앱을 실행하는 로컬 장치가 회사 포털 앱을 통해 등록된 경우에만 표시합니다.

DEM 사용자가 로컬 장치에서 작업을 수행할 수 있지만, 등록된 다른 장치의 원격 관리는 Intune 관리 콘솔에서만 수행될 수 있습니다. 또한 Intune은 Apple 장치 등록 프로그램 또는 Apple Configurator 도구에서 DEM 계정을 사용하지 않을 예정입니다. 이 두 가지 등록 방식은 공유 iOS 장치에 대해 사용자 정보가 없는 등록을 지원합니다.

DEM 계정은 공유 장치에 대해 사용자 정보가 없는 등록을 사용할 수 없는 경우에만 사용합니다. 자세한 내용은 [Microsoft Intune에서 장치 등록 관리자를 사용하여 회사 소유의 장치 등록](https://docs.microsoft.com/en-us/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)을 참조하세요.
<!---TFS 1233681--->

### Windows 기능의 이름 변경
- 이제 [Microsoft Passport for Windows](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md)를 **비즈니스용 Windows Hello**라고 합니다.
- [엔터프라이즈 데이터 보호](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune)를 **Windows 정보 보호**라고 합니다.

## 2016년 6월
### Intune 서비스 상태
Intune에 대한 서비스 상태 정보는 다른 Microsoft 서비스와 함께 중앙 위치로 이동되었습니다. 이 정보는 이제 Office 365 관리 포털의 서비스 상태에서 찾을 수 있습니다. 자세한 내용은 [이 블로그 게시물](https://blogs.technet.microsoft.com/enterprisemobility/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/)을 참조하세요.

### 앱 관리
- **Windows 10 엔터프라이즈 데이터 정책 구성 환경이 개선되었습니다.** 앱 규칙 생성, 네트워크 경계 정의 지정 및 기타 엔터프라이즈 데이터 보호 설정과 관련된 Windows 10 엔터프라이즈 데이터 보호 정책 구성 환경이 개선되었습니다. 자세한 내용은 [Create an enterprise data protection (EDP) policy using Microsoft Intune](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune)(Microsoft Intune을 사용하여 EDP(엔터프라이즈 데이터 보호) 정책 만들기)을 참조하세요.


### 장치 관리
- **원치 않는 앱으로부터 보호하기 위한 Windows Defender 정책 설정.** **사용자 동의 없이 설치된 응용 프로그램 검색**이라고 하는 새로운 Windows Defender 설정이 Windows 10 Desktop 및 Mobile에 대한 일반 구성 정책에 추가되었습니다. 이 설정을 사용하여 Windows Defender에서 사용자 동의 없이 설치된 소프트웨어로 분류된 프로그램에 대해 등록된 Windows 데스크톱 컴퓨터를 보호할 수 있습니다. 실행 중인 이러한 응용 프로그램으로부터 보호하거나 감사 모드를 사용하여 사용자 동의 없이 응용 프로그램이 설치될 때 보고할 수 있습니다. 자세한 내용은 [Microsoft Intune의 Windows 10 정책 설정](https://docs.microsoft.com/en-us/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)을 참조하세요.
<!---TFS 1244478--->

### 조건부 액세스
- **Intune에 대한 Cisco ISE 네트워크 액세스 제어 정책.**  Cisco ISE(Identity Service Engine) 2.1 및 Microsoft Intune을 사용하는 고객은 ISE에서 네트워크 액세스 제어 정책을 설정할 수 있습니다.

    이 정책을 사용하여 WiFi 또는 VPN을 통해 네트워크에 연결해야 하는 장치는 다음 조건을 충족해야 액세스가 허용됩니다.

    * Intune에서 관리되어야 합니다.
    * 배포된 Intune 준수 정책을 준수해야 합니다.

 비규격 장치의 최종 사용자는 액세스하기 위해 등록하고 준수 문제를 해결하도록 요구됩니다.
- **브라우저에 대한 조건부 액세스.** 정책을 준수하고 관리되는 iOS 및 Android 장치의 지원되는 웹 브라우저에서만 액세스할 수 있도록 [Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md) 및 [SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)에 대한 조건부 액세스 정책을 설정할 수 있게 됩니다. iOS 및 Android 장치를 사용하여 Outlook Web Access(OWA) 및 SharePoint 사이트에 로그인하려는 최종 사용자에게는 Intune을 사용하여 장치를 등록하라는 메시지는 물론 로그인을 완료하기 전에 비호환 문제가 있으면 수정하라는 메시지를 표시하게 됩니다.
<!---TFS 1175844--->

- **Dynamics CRM Online에서 조건부 액세스를 지원합니다.** 정책을 준수하고 관리되는 iOS 및 Android 장치에서만 액세스할 수 있도록, [Dynamics CRM Online](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md)에 대한 조건부 액세스 정책을 설정할 수 있습니다. iOS 및 Android에서 Dynamics CRM 모바일 앱에 로그인하려고 하는 최종 사용자에게 Intune에 등록하고 로그인을 완료하기 전에 모든 비호환성 문제를 해결해야 한다는 메시지가 표시됩니다.
<!---TFS1295358--->

##E 회사 포털 업데이트

#### Android 회사 포털 앱

- IT 관리자가 새 “장치가 알 수 없는 소스의 앱 설치를 방지해야 함(Android 4.0 이상)” 정책을 적용하면 Android 4.0 이상 장치를 사용하는 최종 사용자에게 "알 수 없는 소스에서의 설치를 금지해야 합니다." 메시지가 표시됩니다. **설정** > **보안**으로 이동한 후 **알 수 없는 원본**을 해제해야 합니다. 규정 준수 메시지의 링크를 클릭하면 해당 메시지에 대한 추가 [정보](/Intune/EndUser/you-are-asked-to-turn-off-unknown-sources-android)와 설정을 해제해야 하는 이유가 표시됩니다.

- IT 관리자가 새 “앱의 보안 위협 검색을 사용하도록 장치가 설정되어 있어야 함(Android 4.0 이상)” 정책을 적용하면 Android 4.0 이상 장치를 사용하는 최종 사용자에게 "장치의 보안 위협 검색" 메시지가 표시됩니다. 사용자는 **설정** > **Google** > **보안**으로 이동한 후 **장치의 보안 위협 검색**을 켜야 합니다. 규정 준수 메시지의 링크를 클릭하면 해당 메시지에 대한 추가 [정보](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android)와 설정을 켜야 하는 이유가 표시됩니다.

- IT 관리자가 새 "USB 디버깅을 사용하지 않도록 설정되어야 함(Android 4.2 이상)" 정책을 적용하면 Android 4.2 이상 장치를 사용하는 최종 사용자에게 "USB 디버깅을 사용하지 않도록 설정해야 합니다." 메시지가 표시됩니다. **설정** > **개발자 옵션**으로 이동하여 **USB 디버깅**을 해제해야 합니다. 규정 준수 메시지의 링크를 클릭하면 해당 메시지에 대한 추가 [정보](/Intune/EndUser/you-are-asked-to-turn-off-usb-debugging-android)와 설정을 해제해야 하는 이유가 표시됩니다.

- IT 관리자가 새 "최소 Android 보안 패치 수준(Android 6.0 이상)" 정책을 적용하면 Android 6.0 이상 장치를 사용하는 최종 사용자에게 "이 장치는 최소 Android 보안 패치 수준을 충족하지 않습니다." 메시지가 표시됩니다. 사용자는 필수 보안 패치를 설치해야 합니다. 규정 준수 메시지의 링크를 클릭하면 필수 보안 패치를 설치하고 현재 설치되어 있는 보안 패치를 확인하는 방법에 대한 [정보](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android)가 표시됩니다.

#### iOS 회사 포털 앱

- 최종 사용자가 기간 업무 앱을 설치하는 경우, 향상된 앱 설치 환경이 표시됩니다. 앱 설치가 너무 오래 걸리면, 사용자는 동기화 프로세스가 다시 시작되도록 장치를 수동으로 동기화할 수 있습니다. 최종 사용자 지침을 검토하려면 [iOS 장치를 수동으로 동기화](/Intune/EndUser/sync-your-device-manually-ios)를 참조하세요.

- iOS에 대한 Microsoft Intune 회사 포털 앱은 iOS 버전 8.0 이상을 지원하도록 업데이트되었습니다. 이 업데이트를 사용하면 장치가 iOS 버전 8.0 이상을 실행하는 경우에만 최종 사용자가 Intune에서 회사 포털 앱을 설치하고 새 장치를 등록할 수 있습니다. 지원되지 않는 iOS 버전을 실행 중이고 이미 등록된 장치가 있는 사용자는 자신의 장치에 있는 회사 포털 앱을 계속 사용할 수 있습니다.


## 2016년 5월

이 모든 기능은 하이브리드 배포에 대해서도 지원됩니다(Configuration Manager with Intune). 새로운 하이브리드 기능에 대한 자세한 내용은 [Hybrid What’s New](https://technet.microsoft.com/en-us/library/mt718155.aspx)(하이브리드의 새로운 기능) 페이지를 참조하세요.

### 문서
[docs.microsoft.com](https://docs.microsoft.com/en-us/intune)의 미리 보기 버전에 오신 것을 환영합니다!
완전히 새로운 최신 콘텐츠 플랫폼으로, 사용자와 고객이 Intune을 쉽게 이해하고 사용할 수 있도록 설계되었습니다.
새로운 모든 기능에 대한 내용을 보려면 [Introducing docs.microsoft.com](https://docs.microsoft.com/teamblog/introducing-docs-microsoft-com/)(docs.microsoft.com 소개)을 참조하세요.

### Intune 서비스 상태
Intune에 대한 서비스 상태 정보는 다른 Microsoft 서비스와 함께 중앙 위치로 이동되었습니다. 이 정보는 이제 [Office 365 관리 포털](https://portal.office.com/Admin/Default.aspx)의 **서비스 상태**에서 찾을 수 있습니다.
자세한 내용은 [이 블로그 게시물](https://blogs.technet.microsoft.com/microsoftintune/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/)을 참조하세요.


### 앱 관리
- **MAM SDK: PIN 길이 구성 지원.** 장치 PIN과 유사하게 MAM 앱에 대한 PIN의 길이를 지정할 수 있게 됩니다. 이렇게 하려면, 여러분이 설정하는 새로운 제한 사항을 최종 사용자가 준수해야 합니다. 좀 더 길어진 입력을 설명하기 위해 약간 수정된 PIN 화면이 표시됩니다. 자세한 내용은 [MAM policy settings for Android](android-mam-policy-settings.md)(Android용 MAM 정책 설정) 및 [MAM policy settings for iOS](ios-mam-policy-settings.md)(iOS용 MAM 정책 설정)를 참조하세요.

- **비즈니스용 Skype for iOS 및 Android.** 이제 [등록 정책 없이 MAM](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)을 통해 비즈니스용 Skype를 관리할 수 있습니다. 사용자가 로그인하면 MAM 정책이 적용됩니다.

- **MAM 정책을 통해 새로운 앱을 관리할 수 있음.** 이제 Intune에 등록하지 않은 장치에서 Android용 Microsoft Word, Excel 및 PowerPoint 앱을 MAM 정책과 연결할 수 있습니다. 지원되는 앱의 전체 목록을 확인하려면 [Microsoft Intune application partners](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx)(Microsoft Intune 응용 프로그램 파트너) 페이지의 Microsoft Intune 모바일 응용 프로그램 갤러리로 이동합니다.


### 회사 포털 업데이트

#### Android 회사 포털 앱
- **최종 사용자 알림 메시지**: 이제 최종 사용자가 회사 포털에 장치를 등록하거나 회사 포털에서 장치를 제거하는 경우 Android 회사 포털 앱에 알림 메시지가 표시됩니다.

- **Android 회사 포털 앱의 장치 등록 관리자 계정의 변경 내용.** 성능과 확장성을 개선하기 위해 Intune은 Android 회사 포털 앱의 내 장치 창에 모든 DEM(장치 등록 관리자)을 더 이상 표시하지 않습니다. 앱을 실행하는 로컬 장치가 회사 포털 앱을 통해 등록된 경우에만 표시합니다. DEM 사용자가 로컬 장치에서 작업을 수행할 수 있지만, 등록된 다른 장치의 원격 관리는 Intune 관리 콘솔에서만 수행될 수 있습니다.

#### 회사 포털 웹 사이트
- **회사 포털 웹 사이트: 장치 식별 배너를 통해 최종 사용자에게 더 많은 정보를 제공합니다.** 이제 최종 사용자가 회사 포털 웹 사이트를 사용할 때 자신이 선택한 장치를 더 쉽게 식별할 수 있습니다. 잘못된 장치를 선택하면 홈페이지 배너의 **여기를 누르세요** 링크를 탭하여 올바른 장치를 선택할 수 있습니다.

## 향후 예정 사항
- **메시지 센터 UI 등록**. Intune을 [Office 365 관리 포털](https://portal.office.com/)로 마이그레이션하는 작업의 일환으로, 메시지 센터를 이용하여 새로운 기능 및 기타 알림을 전달하기 시작하려고 합니다. 또한, 함께 사용되는 Office 365 관리 모바일 앱을 설치하면, 휴대폰에서 알림을 수신하고 사용자 또는 메일 그룹을 대상으로 모든 메시지를 손쉽게 전달할 수 있습니다.
Intune의 새롭고 향상된 기능에 대한 정보를 포함하고 업데이트가 완료되면 알리기 위해서, 5월 릴리스부터 메시지 센터를 사용하기 시작할 예정입니다. [Office 365 관리 포털](https://portal.office.com/)에 로그인하고 왼쪽 탐색 창에서 “메시지 센터” 옵션을 선택하여 메시지 센터를 확인하세요.

- **장치 등록 관리자 계정의 변경 내용**. 성능과 확장성을 개선하기 위해 Intune은 iOS 회사 포털 앱의 **내 장치** 창에 **모든** DEM(장치 등록 관리자)을 더 이상 표시하지 않습니다. 앱을 실행하는 로컬 장치가 회사 포털 앱을 통해 등록된 경우에만 표시합니다. DEM 사용자가 로컬 장치에서 작업을 수행할 수 있지만, 등록된 다른 장치의 원격 관리는 Intune 관리 콘솔에서만 수행될 수 있습니다. 또한 Intune은 Apple 장치 등록 프로그램 또는 Apple Configurator 도구에서 DEM 계정을 사용하지 않을 예정입니다. 이 두 가지 등록 방식은 공유 iOS 장치에 대해 사용자 정보가 없는 등록을 지원합니다. DEM 계정은 공유 장치에 대해 사용자 정보가 없는 등록을 사용할 수 없는 경우에만 사용합니다.

### 클라우드 로드맵
[클라우드 플랫폼 로드맵](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)에서 Intune에 대해 예정된 개발 정보를 지속적으로 받습니다.

### 서비스 중단
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


## 2016년 4월
이 모든 기능은 하이브리드 고객에 대해서도 지원됩니다(Intune과 통합된 Configuration Manager).
### 앱 관리
- **MAM 사용자 규정 준수.**
이제 Azure Active Directory(AAD) 테넌트에 속하는 모든 사용자에 대한 응용 프로그램 관리 정책의 [상태](monitor-mobile-app-management-policies-with-Microsoft-Intune.md)를 볼 수 있습니다. 여기에는 다음 항목이 포함됩니다.
   - 장치
   - 장치의 앱

   상태 값:

   **Checked in**(체크 인 됨): 사용자에게 정책이 배포되었고, 회사 컨텍스트에서 앱이 사용되었으며, 성공적으로 정책이 수신되었다는 것을 나타냅니다.

    **Not checked in**(체크인 안됨): 사용자에게 정책이 배포되었지만, 그 뒤로 회사 컨텍스트에서 앱이 사용되지 않았다는 것을 나타냅니다.


- **Outlook 연락처 동기화를 방지하기 위한 MAM 컨트롤(Android).**
장치 등록 없이 새 설정을 [모바일 응용 프로그램 관리](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)에 사용할 수 있습니다. 이 설정을 통해 응용 프로그램이 Android 장치의 기본 주소록에 대해 연락처를 동기화하는 것을 방지할 수 있습니다. 이 설정을 사용하면, 대상 응용 프로그램은 연락처를 기본 주소록에 더 이상 저장할 수 없게 됩니다. 이 설정을 사용하지 않으면, 대상 응용 프로그램은 연락처를 기본 주소록에 저장할 수 있게 됩니다. [장치 또는 앱을 원격으로 초기](wipe-managed-company-app-data-with-Microsoft-Intune.md)화하는 경우, 기본 주소록에 이미 저장되어 있는 모든 연락처가 제거됩니다. 이 새로운 설정은 Android 장치의 Outlook 응용 프로그램에서 처음 지원됩니다.

### 장치 관리
- **회사 소유 장치에 대한 전화 번호 식별.** "회사"로 분류되는 전화는 이제 전체 전화 번호로 식별됩니다(예: 모바일 장치 인벤토리 보고서를 실행하는 경우). BYOD 전화 번호는 마지막 4자리만 표시되고 ****으로 계속 마스킹됩니다.


### 회사 포털 업데이트
**Android 회사 포털 앱** Intune에 장치를 등록하지 않았거나 올바른 인증서가 설치되지 않은 사용자는 Android 회사 포털 앱에 로그인할 수 있으며 “You cannot sign in because your device is missing a required certificate.”(장치에 필요한 인증서가 없어서 로그인할 수 없습니다.)라는 메시지를 보게 됩니다. 메시지에는 “해결 방법” 링크가 포함되며, 사용자가 이 링크를 탭하면 인증서 설치에 대한 지침을 볼 수 있습니다. 최종 사용자가 문제를 해결하기 위해 수행하는 단계를 보려면 [장치에 필요한 인증서가 없습니다.](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_cert_missing) 참조하세요.

**iOS 회사 포털 앱** 홈 화면의 콘텐츠를 새로 고치기 위해 끌어오기-새로 고침 작업에 대한 지원이 추가되었습니다. 여기에는 나열된 앱, 나열된 장치, 및 IT 연락처 정보가 포함됩니다. 끌어오기-새로 고침 작업은 정책 또는 준수 정보를 확인하지 않습니다. 이 작업은 현재 장치의 타일을 선택하고 **동기화** 단추를 탭하여 수행할 수 있습니다.

**Windows 10 Mobile 및 Windows Phone 8.1 회사 포털 앱** 최종 사용자가 기간 업무 앱을 설치하는 경우, 향상된 앱 설치 환경이 표시됩니다. 앱 설치가 너무 오래 걸리면, 사용자는 동기화 프로세스가 다시 시작되도록 장치를 수동으로 동기화할 수 있습니다. 최종 사용자 지침을 검토하려면 [앱 설치 속도를 높이기 위해 장치를 수동으로 동기화](https://technet.microsoft.com/library/mt427782.aspx#BKMK_win10m_wp81_sync_manually)를 참조하세요.

** 회사 포털 웹 사이트** Windows 10 Mobile 및 Windows Phone 8.1 사용자가 기간 업무 앱을 설치하는 경우, 다음과 같은 새로운 상태가 표시되어, 사용자의 설치 상태에 대해 보다 자세한 정보를 제공하게 됩니다.

* **장치가 동기화될 때까지 기다리는 중** – 사용자가 “설치”를 탭했고 이제 장치가 Intune 인프라와의 동기화를 시도합니다. 설치를 완료하려면 그 전에 동기화가 필요합니다. "장치가 동기화될 때까지 기다리는 중" 메시지 역시 사용자가 탭하면, 동기화 프로세스가 너무 오래 걸리거나 멈춘 경우 Intune에서 장치를 수동으로 동기화하는 방법에 대한 [지침](https://technet.microsoft.com/library/mt590895.aspx#BKMK_iwp_sync_manually)을 볼 수 있는 링크입니다.
* **다운로드 중** – 사용자의 다운로드 요청이 처리 중이며 장치가 앱을 다운로드 및 설치 중입니다.

이런 상태가 추가되기 전에는, 사용자에게 “설치 중” 상태만 보여줬기 때문에(화면에 수 시간 동안 유지되기도 하는) 앱 설치가 오래 걸리면 혼란스러웠습니다. 새로운 상태가 추가되었기 때문에, 이제 사용자들은 지원을 요청하는 대신 "장치가 동기화될 때까지 기다리는 중" 링크를 클릭하고 지침에 따라서 동기화 프로세스가 재시작되도록 강제 적용할 수 있습니다.


## 2016년 3월
### 2016년 3월 29일 기준 새로운 기능
Windows 10 일반 구성 정책으로 업데이트를 제외하고, 2016년 3월 29일에 릴리스된 모든 기능이 하이브리드 고객에 대해서도 지원됩니다(Configuration Manager가 Intune과 통합됨). Windows 10 일반 구성 정책 업데이트를 위한 하이브리드 지원도 곧 제공됩니다. 이러한 기능 중 일부에는 최신 버전의 Configuration Manager가 필요할 수 있습니다.

### 앱 관리
- **Outlook 연락처 동기화를 방지하기 위한 MAM 컨트롤(iOS).** 장치 등록 없이 새 설정을 모바일 응용 프로그램 관리에 사용할 수 있습니다. 이 설정을 통해 응용 프로그램이 iOS 장치의 기본 주소록에 대해 연락처를 동기화하는 것을 방지할 수 있습니다. 이 설정을 사용하는 경우 앱에서 연락처를 기본 주소록에 더 이상 저장할 수 없게 됩니다. 이 설정을 사용하지 않는 경우 앱에서 연락처를 기본 주소록에 저장할 수 있게 됩니다. 장치를 선택적으로 초기화하는 경우 기본 주소록에 이미 저장되어 있는 모든 연락처가 제거됩니다. 이 새로운 설정은 iOS 장치의 Outlook 응용 프로그램에서 지원됩니다. 이 내용과 기타 설정에 대한 자세한 내용은 [MAM 정책 만들기 및 배포](https://technet.microsoft.com/en-us/library/dn292747.aspx)를 참조하세요.

### 액세스 제어
- **비즈니스용 Skype Online에서 조건부 액세스를 지원합니다.** 비즈니스용 Skype Online에 대한 조건부 액세스 정책을 설정하여 관리되는 호환 iOS 및 Android 장치에서만 액세스할 수 있습니다. iOS 및 Android에서 비즈니스용 Skype 모바일 앱에 로그인하려고 하는 최종 사용자에게 Intune에 등록하고 로그인을 완료하기 전에 모든 비호환성 문제를 해결해야 한다는 메시지가 표시됩니다. 자세한 내용은 [비즈니스용 Skype Online에 대한 액세스 관리](https://technet.microsoft.com/en-us/library/mt695297.aspx)를 참조하세요.

### 장치 관리
- **iOS 9.3에 대한 Intune 지원.** 3월 21일 월요일, Apple은 iOS 9.3의 가용성을 발표했습니다. Microsoft Intune이 최신 버전의 Apple 모바일 운영 체제와 호환되도록 끊임없이 노력해왔으며 [Intune이 iOS 9.3 장치 관리를 지원함을 발표하게 되어 기쁩니다](https://blogs.technet.microsoft.com/microsoftintune/2016/03/23/microsoft-intune-provides-support-for-ios-9-3/).

  iOS 장치 관리에 사용할 수 있는 기존의 모든 Intune 기능은 사용자가 자신이 장치를 iOS 9.3으로 업그레이드함에 따라 계속해서 원활하게 작동합니다. 또한 오늘 하이브리드 고객에 대해서도 iOS 9.3이 지원됩니다(Configuration Manager가 Intune과 통합됨).

- **Windows 10 일반 구성 정책에는 이제 등록된 Windows 10 PC에서 Windows Defender를 관리하는 설정이 포함됩니다.** 자세한 내용은 [Microsoft Intune의 Windows 10 구성 정책 설정](https://technet.microsoft.com/en-us/library/mt404697.aspx)을 참조하세요.


### 회사 포털

- **Windows 앱 패키지는 회사 포털 웹 사이트에서 직접 사용할 수 있습니다.** 이제 Windows 8, Windows 8.1, Windows RT PC 사용자가 회사 포털 웹 사이트에서 직접 Windows 앱 패키지(.appx 확장명 포함)를 설치할 수 있습니다. 이전에는 직접 배포하거나 사용자가 앱을 설치할 장치에 회사 포털 앱을 설치해야 했습니다.

- **사용자는 회사 포털 웹 사이트에서 장치를 원격으로 잠글 수 있습니다.** 새 원격 잠금 옵션이 회사 포털 웹 사이트에 추가되어 사용자가 장치를 분실하거나 도난당한 경우 포털에서 자신의 장치를 원격으로 잠글 수 있습니다. [최종 사용자 지침](https://technet.microsoft.com/library/mt590895.aspx/?wt.mc_id=ui#BKMK_iwp_remote_lock)을 참조하세요. 다음 표에는 Intune 독립 실행형 및 Configuration Manager 포함 Intune의 원격 잠금에 대한 플랫폼별 지원이 나열되어 있습니다.

|플랫폼 | 지원 세부 정보|
|---------|----------------|
|Android |지원됨|
|iOS |지원됨|
|Windows 10 Mobile |휴대폰에 암호가 설정된 경우에만 지원됨|
|Windows 10 Desktop |지원되지 않음|
|Windows Phone 8.1 |휴대폰에 암호가 설정된 경우에만 지원됨|
|Windows Phone 8.0 |지원되지 않음|
|PC(Windows 8.0 이전 버전) |지원되지 않음|
|PC(Windows 8.1) |지원되지 않음|

### 2016년 3월 10일 기준 새로운 기능

### 앱 관리

- **타사 MDM 솔루션에 등록된 장치에 대해 iOS "다음에서 열기" 관리 활용** 타사 MDM(모바일 장치 관리) 공급업체를 사용하여 iOS "다음에서 열기" 관리를 활용할 수 있습니다. 구성 프로필 설정에서 제한 사항을 설정하고 [iOS 앱 간에 데이터 전송 관리](manage-data-transfer-between-ios-apps-with-microsoft-intune.md)를 사용하여 앱을 배포할 수 있습니다.

     이 방법은 다음과 같은 두 가지 주요 이점이 있습니다.

     1. 사용자가 회사 계정으로 로그인해야 클라우드 서비스 또는 다른 앱에서 회사 데이터에 액세스할 수 있습니다. 이렇게 하면 데이터에 액세스할 때 MAM(모바일 앱 관리) 정책이 적용됩니다.

     2. 관리되는 메일 프로필 및 타사 MDM 솔루션을 통해 배포된 기타 관리되는 앱은 Intune MAM 정책이 있는 앱과 파일 및 데이터를 공유할 수 있습니다.

- **Intune에 등록되지 않은 장치에 대한 MAM 정책을 사용하여 Microsoft Outlook 앱 관리** 이제 Intune 모바일 응용 프로그램 관리 정책을 사용하여 Intune에 등록되지 않은 장치의 Microsoft Outlook 앱을 관리할 수 있습니다. MAM 기능이 있는 업데이트된 Microsoft Outlook 앱은 [iOS](https://itunes.apple.com/us/app/microsoft-outlook-email-calendar/id951937596?mt=8) 및 [Android](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook) 장치 둘 다에 사용할 수 있습니다. [모바일 앱 관리 정책 만들기 및 배포](https://technet.microsoft.com/library/mt627829.aspx) 항목의 지침에 따라 MAM 정책을 만듭니다.  


- **모바일 앱 구성 정책을 사용하면 보다 유연성 있게 iOS 앱에 대한 사용자 세부 정보를 지정할 수 있습니다.** iOS 앱을 열 때 필요할 수 있는 사용자 설정을 제공할 수 있습니다. 예를 들어 네트워크 포트나 사용자 이름을 제공할 수 있습니다. 자세한 내용은 [Microsoft Intune에서 모바일 앱 구성 정책을 사용하여 iOS 앱 구성](configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune.md)을 참조하세요.


- **엔터프라이즈의 Intune 관리 iOS 장치에 Microsoft Intune용 Adobe Reader 배포** 이제 Intune 모바일 응용 프로그램 관리 정책을 사용하여 등록된 장치에서 iOS용 Adobe Reader 앱을 관리할 수 있습니다.

- **배포된 웹 클립이 Managed Browser에서 열리는지 확인** iOS 및 Android 장치에서 Managed Browser를 통해서만 열 수 있는 대상 지정 웹 클립을 배포할 수 있습니다. 예를 들어 회사 포털을 통해 회사 리소스에 대한 링크를 배포하면 사용자가 링크로 이동할 때 MAM 정책으로 보호될 수 있는 Managed Browser에서 바로 열립니다. 자세한 내용은 [앱 배포](deploy-apps.md)를 참조하세요.


- **Intune 관리자 콘솔에서 Windows 10 장치에 대한 비즈니스용 Windows 스토어 앱 찾기, 관리 및 배포** 앱을 찾고 관리하고 관리 중인 Windows 10 장치에 배포하는 데 도움이 되는 비즈니스용 Windows 스토어 지원을 Intune에서 사용할 수 있습니다. 비즈니스용 Windows 스토어를 사용하면 Intune 관리자 콘솔(다른 앱 관리에 사용하는 콘솔과 같음)에서 이러한 앱을 배포하고 모니터링하는 과정을 관리할 수 있습니다. 특히, 비즈니스용 Windows 스토어는 "온라인 사용이 허가된 앱"의 콘텐츠와 라이선스를 관리합니다. 자세한 내용은 [비즈니스용 Windows 스토어에서 구입한 앱 관리](manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune.md)를 참조하세요.


### 장치 관리
- **iOS 장치에 대한 PFX 인증서 배포** Intune 관리자는 iOS 장치에서 Wi-Fi, 메일 및 VPN 인증에 사용되는 iOS PFX 인증서를 만들고 배포할 수 있습니다. Android 및 Windows 10 장치에서는 이 기능을 이미 사용할 수 있습니다. 자세한 내용은 [인증서 프로필을 사용하여 회사 리소스에 대한 액세스 사용](secure-resource-access-with-certificate-profiles.md)을 참조하세요.


- **사용자 범주 선택에 따라 서로 다른 장치 그룹에 앱 및 정책 적용** 이제 Intune 관리자가 등록 중에 사용자가 선택하는 사용자 지정 장치 범주를 정의할 수 있습니다. 예를 들어 관리자는 사용자가 "현금 등록기", "배달 트럭" 또는 "인벤토리 공간"에 사용되는 장치를 등록할지 여부를 지정할 수 있습니다. 선택한 범주에 따라 장치는 등록된 장치에 다른 앱과 정책을 배포하는 데 사용될 수 있는 Intune 장치 그룹의 구성원이 됩니다. 자세한 내용은 [장치 그룹 매핑을 사용하여 장치 분류](categorize-devices-with-device-group-mapping-in-microsoft-intune.md)를 참조하세요.

### Microsoft 회사 포털에 대한 변경 사항 및 업데이트
이 릴리스에서는 회사 포털에 다음과 같은 변경 내용을 적용했습니다.

**Android 회사 포털 앱**

* 사용자가 MAM(모바일 응용 프로그램 관리)에서 관리되는 앱을 시작하면 앱이 회사에서 관리됨을 알리는 메시지가 나타납니다. 이제 사용자가 “자세한 정보” 링크를 탭하여 여기서 “관리되는 앱”이 의미하는 바에 대한 [자세한 내용](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_use_mgd_apps)을 확인할 수 있습니다. 앱을 시작할 때 메시지가 더 이상 표시되지 않도록 "다시 표시 안 함"을 탭할 수도 있습니다.
* 사용자에게 등록 과정을 안내하고 사용자가 등록해야 이유 및 IT 관리자가 등록 된 장치에서 볼 수 있는 사항과 볼 수 없는 사항에 대한 자세한 정보를 제공하는 새 화면이 추가되었습니다. 자세한 내용은 [등록 지침](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_enroll_devc)을 참조하세요.
* 이제 등록 오류 메시지가 회사 포털 앱에 표시됩니다. 이전에는 이러한 메시지가 회사 포털 웹 사이트에 표시되었습니다. 이러한 변경은 두 개의 장소가 아니라 한 장소에 모든 오류 메시지가 표시됨을 의미합니다.


**iOS 회사 포털 앱**
* 사용자가 MAM(모바일 응용 프로그램 관리)에서 관리되는 앱을 시작하면 앱이 회사에서 관리됨을 알리는 메시지가 나타납니다. 이제 사용자가 “자세한 정보” 링크를 탭하여 여기서 “관리되는 앱”이 의미하는 바에 대한 [자세한 내용](https://technet.microsoft.com/library/mt598622.aspx#BKMK_ios_use_mgd_apps)을 확인할 수 있습니다. 앱을 시작할 때 메시지가 더 이상 표시되지 않도록 "다시 표시 안 함"을 탭할 수도 있습니다.
* 사용자에게 등록 과정을 안내하고 사용자가 등록해야 이유 및 IT 관리자가 등록 된 장치에서 볼 수 있는 사항과 볼 수 없는 사항에 대한 자세한 정보를 제공하는 새 화면이 추가되었습니다. 자세한 내용은 [등록 지침](https://technet.microsoft.com/library/mt598622.aspx#BKMK_enroll_ios_device)을 참조하세요.
* 이제 등록 오류 메시지가 회사 포털 앱에 표시됩니다. 이전에는 이러한 메시지가 회사 포털 웹 사이트에 표시되었습니다. 이러한 변경은 두 개의 장소가 아니라 한 장소에 모든 오류 메시지가 표시됨을 의미합니다.




## 2016년 2월
### Microsoft 회사 포털에 대한 변경 사항 및 업데이트

이 릴리스에서는 회사 포털에 다음과 같은 변경 내용을 적용했습니다.

#### Android 회사 포털 앱
- 사용자에게 등록 과정을 안내하고 사용자가 등록해야 이유 및 IT 관리자가 등록 된 장치에서 볼 수 있는 사항과 볼 수 없는 사항에 대한 자세한 정보를 제공하는 새 화면이 추가되었습니다. 자세한 내용은 [등록 지침](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_enroll_devc)을 참조하세요.
- 이제 등록 오류 메시지가 회사 포털 앱에 표시됩니다. 이전에는 이러한 메시지가 회사 포털 웹 사이트에 표시되었습니다. 이러한 변경은 두 개의 장소가 아니라 한 장소에 모든 오류 메시지가 표시됨을 의미합니다.

#### iOS 회사 포털 앱
 - 사용자에게 등록 과정을 안내하고 사용자가 등록해야 이유 및 IT 관리자가 등록 된 장치에서 볼 수 있는 사항과 볼 수 없는 사항에 대한 자세한 정보를 제공하는 새 화면이 추가되었습니다. 자세한 내용은 [등록 지침](https://technet.microsoft.com/library/mt598622.aspx#BKMK_enroll_ios_device)을 참조하세요.

 - 이제 등록 오류 메시지가 회사 포털 앱에 표시됩니다. 이전에는 이러한 메시지가 회사 포털 웹 사이트에 표시되었습니다. 이러한 변경은 두 개의 장소가 아니라 한 장소에 모든 오류 메시지가 표시됨을 의미합니다.


## 2016년 1월

### Windows 10 기능 활용
* **상태 증명 서비스를 사용한 조건부 액세스** 이제 Intune 관리자가 Intune 관리 콘솔에서 Windows 10 디바이스 상태 증명의 상태를 볼 수 있습니다. 디바이스 상태 증명을 사용하여 관리자는 클라이언트 컴퓨터가 신뢰할 수 있는 BIOS, TPM 및 소프트웨어 구성을 갖는지 확인할 수 있습니다. 디바이스 상태 증명을 지원하려면 클라이언트 장치에서 TPM 2가 설정된 Windows 10이 실행되고 있어야 합니다. 디바이스 상태 증명은 다음 각각에 대해 사용하도록 설정된 장치 수를 표시합니다.
    * 맬웨어 방지 조기 실행
    * BitLocker
    * 보안 부팅
    * 코드 무결성

    디바이스 상태 설정, 수집되는 데이터 요소 및 상태 증명 보고서에 대한 자세한 내용은 [Microsoft Intune에 대한 장치 규정 준수 정책 소개](introduction-to-device-compliance-policies-in-microsoft-intune.md)를 참조하세요. [HAS 서비스 정보](https://msdn.microsoft.com/en-us/library/dn934876.aspx)에서는 서비스에 대해 자세히 설명합니다.

* **Windows 10 Passport for Work 정책 및 인증서 관리** Intune에서는 Active Directory 또는 Azure Active Directory 계정을 사용하여 암호, 스마트 카드 또는 가상 스마트 카드를 대신하는 Windows 10의 대체 로그인 방법인 [Microsoft Passport for Work와 통합](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md)할 수 있습니다. Passport를 사용하면 암호 대신 사용자 제스처를 사용하여 로그인할 수 있습니다. 사용자 제스처는 단순 PIN, 생체 인식 인증(예: Windows Hello) 또는 외부 장치(예: 지문 판독기)일 수 있습니다.

* **특정 앱에 대한 VPN** VPN을 통해 자동으로 회사 네트워크에 연결되는 앱을 선택할 수 있습니다. 사용자가 Microsoft Intune에서 VPN 프로필을 사용하여 회사에 연결하도록 지원에 설명된 대로 VPN 프로필을 설정할 때 앱 목록을 만듭니다.

* **Windows 10 전체 초기화 지원** 이제 Intune 관리 콘솔을 통해 Intune에 등록된 Windows 10 Desktop 장치의 원격 전체 초기화를 실행할 수 있습니다. Windows 10 전체 초기화는 장치를 공장 기본 설정으로 되돌립니다.


### Apple VPP(Volume Purchase Program) 업데이트
이제 Intune에서 [비즈니스용 Apple VPP(Volume Purchase Program)를 통해 구입한 앱의 관리](manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune.md)를 도와줍니다. 여기에는 Apple과 Intune 간의 라이선스 정보 동기화와 배포한 각 앱의 복사본 수 추적이 포함됩니다.

### IMEI 번호를 사용하여 회사 소유의 장치 식별
이제 회사 소유의 모바일 장치를 식별하는 데 도움이 되는 IMEI 번호가 있는 모바일 장치 플랫폼에 대해 [IMEI(International Mobile Equipment Identity) 번호를 가져올](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md) 수 있습니다. Intune에 등록되고 나면 가져온 IMEI 번호가 있는 장치에는 회사 태그가 지정되며, 이 태그를 사용하여 개인 소유 장치에 적용되는 정책과 다른 정책을 적용할 수 있습니다.

### 이제 더 많은 앱이 Intune MAM 정책과 호환됨
이제 Microsoft 파트너의 추가 앱이 Intune MAM(모바일 응용 프로그램 관리) 정책과 호환됩니다(Intune에서 관리되는 장치의 경우).
* Box for EMM(Box Inc) – iOS에만 해당
* Adobe Reader(Adobe) – Android에만 해당
* Foxit PDF Reader(Foxit Corporation) – iOS 및 Android


### IE9 지원이 1월에 종료됨
Internet Explorer 9는 2016년 2월부터 더 이상 Microsoft Intune 회사 포털 웹 사이트, Intune 계정 포털 및 Intune 관리 콘솔에 액세스하기 위한 공식 브라우저로 지원되지 않습니다. Internet Explorer 10 이상으로 마이그레이션해야 합니다.


>[!div class="step-by-step"]

>[&larr; **Intune의 새로운 기능**](whats-new-in-microsoft-intune.md)    



<!--HONumber=Aug16_HO3-->


