---
title: 초기 버전
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: e91745abb7c3409b31724101b3071157407acec9
ms.sourcegitcommit: 54fc806036f84a8667cf8f74086358bccd30aa7d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2018
---
# <a name="the-early-edition-for-microsoft-intune---march-2018"></a>Microsoft Intune 초기 버전 - 2018년 3월

**초기 버전**에서는 Microsoft Intune의 향후 릴리스에서 도입될 기능의 목록을 제공합니다. 이 정보는 제한적으로 제공되며 변경될 수 있습니다. 회사 외부에서 이 정보를 공유하지 마세요. 여기 나열된 일부 기능은 마감일을 맞추지 못할 위험이 있으며 다음 릴리스까지 지연될 수 있습니다. 다른 기능은 고객용 준비 상태를 확인하기 위해, 파일럿(플라이팅) 테스트 중 입니다. 질문이나 궁금한 내용이 있으면 Microsoft 제품 그룹 담당자에게 연락하세요.

이 페이지는 정기적으로 업데이트됩니다. 추가 업데이트가 있는지 다시 확인하세요.

> [!Note]
>Intune에 대해 다음 변경 사항을 개발 중입니다. 새로운 하이브리드 기능에 대한 자세한 내용은 [Hybrid What’s New](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management)(하이브리드의 새로운 기능) 페이지를 참조하세요.

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->

## <a name="intune-in-the-azure-portal"></a>Azure Portal의 Intune

<!-- 1803 start -->

#### <a name="multiple-exchange-connector-support----2070451---"></a>여러 Exchange Connector 지원 <!-- 2070451 -->

더 이상 테넌트당 하나의 Microsoft Intune Exchange Connector로 제한되지 않습니다. 여러 온-프레미스 Exchange 조직을 사용하여 Intune 조건부 액세스를 설치할 수 있도록 Intune은 여러 Exchange Connector를 지원합니다.

Intune 온-프레미스 Exchange Connector를 사용하여 장치가 Intune에 등록했는지 여부 및 Intune 장치 준수 정책을 준수하는지 여부에 따라 온-프레미스 Exchange 사서함에 대한 장치 액세스를 관리할 수 있습니다. 커넥터를 설정하려면 Azure Portal에서 Intune 온-프레미스 Exchange Connector를 다운로드해 이를 Exchange 조직의 서버에 설치합니다. Microsoft Intune 대시보드에서 **온-프레미스 액세스**를 선택한 다음, **설치** 아래에서 **Exchange ActiveSync Connector**를 선택합니다. Exchange 온-프레미스 Connector를 다운로드하고 Exchange 조직의 서버에 설치합니다. 더 이상 테넌트당 하나의 Exchange Connector로 제한되지 않으므로 추가 Exchange 조직이 있는 경우 동일한 다운로드 절차를 따라 각 추가 Exchange 조직에 대해 커넥터를 설치할 수 있습니다.

### <a name="support-coming-for-new-cisco-anyconnect-client-for-ios----1333708---"></a>IOS용 새 Cisco AnyConnect 클라이언트에 대한 지원 <!-- 1333708 -->

iOS용 Cisco AnyConnect를 위해 만든 새 VPN 프로필은 Cisco AnyConnect 4.0.7x 이상과 작동합니다. 기존 iOS Cisco AnyConnect VPN 프로필은 **Cisco Legacy AnyConnect**로 레이블이 지정되고 오늘과 마찬가지로 앞으로도 Cisco AnyConnect 4.0.5x와 계속 작동합니다.

> [!NOTE]
> 이러한 변경은 iOS에만 해당되며, Android, Android for Work 및 macOS에 대해 단 하나의 Cisco AnyConnect 옵션만 계속 있게 됩니다. 

#### <a name="more-information"></a>추가 정보

새 Cisco AnyConnect 앱 및 Cisco Legacy AnyConnect 앱은 별도 앱이기 때문에 새 iOS Cisco AnyConnect VPN 프로필을 만들어 새 앱을 지원해야 합니다. 사용자 환경에서 AnyConnect 클라이언트를 관리하는 경우 새 Cisco AnyConnect 앱도 함께 배포해야 합니다. 업그레이드를 완료하려면 Cisco Legacy AnyConnect VPN 프로필을 삭제하고 Cisco Legacy AnyConnect 앱을 제거해야 합니다. 

초기 릴리스에서 새 AnyConnect 클라이언트에 대해 NAC(네트워크 액세스 제어) 통합이 작동하지 않습니다. 당사는 Intune의 향후 릴리스에서 NAC 통합 기능을 제공하기 위해 Cisco와 협력합니다.

### <a name="enhanced-jailbreak-detection----846515---"></a>향상된 탈옥 검색 <!-- 846515 -->

향상된 탈옥 검색은 Intune이 무단 해제된 장치를 평가하는 방법을 향상시키는 새 준수 설정입니다. 이 설정은 장치의 위치 확인 서비스를 사용하고 배터리 사용에 영향을 주도록 더 자주 Intune을 사용하여 장치를 체크 인하게 합니다.

### <a name="ability-to-deploy-required-line-of-business-lob-apps-to-all-users-on-windows-10-desktop-devices----1627835-rs4---"></a>Windows 10 Desktop 장치의 모든 사용자에게 필수 LOB(기간 업무) 앱을 배포하는 기능 <!-- 1627835 RS4 -->
고객은 필수 LOB(기간 업무) Windows 10 앱을 장치 컨텍스트에 설치하도록 배포할 수 있습니다. 이렇게 하면 이러한 앱을 장치의 모든 사용자가 사용할 수 있습니다. 이 기능은 Windows 10 Desktop 장치에만 적용됩니다. 

### <a name="expiring-line-of-business-lob-apps-for-microsoft-intune----748789---"></a>Microsoft Intune에 대해 LOB(기간 업무) 앱 만료 <!-- 748789 -->
Azure Portal에서 Intune은 막 만료될 LOB 앱에 경고를 보냅니다. 새 버전의 LOB 앱을 업로드할 때 Intune은 앱 목록에서 만료 알림을 제거합니다.

### <a name="company-portal-enrollment-improved----1874230--"></a>회사 포털 등록 향상<!-- 1874230-->
Windows 10 Build 1703 이상에서 회사 포털을 사용하여 장치를 등록하는 사용자는 해당 앱을 종료하지 않고 등록의 첫 번째 단계를 완료할 수 있습니다.

### <a name="new-management-name-column----1333586---"></a>새 관리 이름 열 <!-- 1333586 -->
**관리 이름**이라는 새 열은 장치 블레이드에 추가됩니다. 이 이름은 다음 수식에 따라 장치당 할당된 자동 생성되고 편집할 수 없는 이름입니다. 
- 모든 장치에 대한 기본 이름: <username>_<devicetype>_<enrollmenttimestamp>
- 대량으로 추가된 장치에 대해: <PackageId/ProfileId>_<DeviceType>_<EnrollmentTime> 
 
이 열은 장치 블레이드에서 선택적입니다. 이 열은 기본으로 사용할 수 없으며 열 선택기를 통해서만 액세스할 수 있습니다. 장치 이름은 이 새 열에서 영향을 받지 않습니다.

### <a name="new-settings-for-windows-defender-security-center-notifications-device-configuration-profile----1631906---"></a>WDSC(Windows Defender 보안 센터) 알림 장치 구성 프로필에 대한 새 설정 <!-- 1631906 -->

3가지 새 설정이 WDSC(Windows Defender 보안 센터) 알림 장치 구성 프로필에 추가됩니다.

관리자는 다음을 할 수 있습니다.

- ID Pillar 숨기기
- 하드웨어 Pillar 및 그 하위 설정 숨기기
- 랜섬웨어 Pillar(비즈니스용 OneDrive 파일 복원) 숨기기

WDSC 앱에서 이러한 Pillar를 숨길 경우 최종 사용자는 이러한 설정을 구성할 수 없으며 숨겨진 구성 요소와 연결된 모든 알림이 생성되지 않습니다.

### <a name="mam-policies-targeted-based-on-management-state----1665993---"></a>관리 상태에 따라 대상으로 지정된 MAM 정책 <!-- 1665993 -->

장치의 관리 상태에 따라 MAM 정책을 대상으로 지정할 수 있습니다.

- **iOS 장치** - 관리되지 않는 장치(MAM만 해당) 또는 Intune 관리 장치를 대상으로 지정할 수 있습니다.
- **Android 장치** - 관리되지 않는 장치, Intune 관리 장치 및 Intune 관리 Android Enterprise 프로필(이전의 Android for Work)을 대상으로 지정할 수 있습니다.

### <a name="configure-gatekeeper-to-control-macos-app-download-source----1690459--"></a>macOS 앱 다운로드 원본을 제어하려면 Gatekeeper 구성 <!-- 1690459-->

해당 앱을 어디서 다운로드할 수 있는지 제어하여 앱에서 장치를 보호하기 위해 Gatekeeper를 구성할 수 있습니다. **Mac 앱 스토어**, **Mac 앱 스토어 및 확인된 개발자** 또는 **원격** 등의 다운로드 원본을 구성할 수 있습니다. 사용자가 이러한 Gatekeeper 제어를 재정의하기 위해 제어-클릭을 사용하여 앱을 설치할 수 있는지 여부를 구성할 수 있습니다.

이러한 설정은 **장치 구성** -> **프로필 만들기** -> **macOS** -> **끝점 보호** 아래에 있습니다.

### <a name="configure-the-mac-application-firewall----1690461---"></a>Mac 응용 프로그램 방화벽 구성 <!-- 1690461 -->

Mac 응용 프로그램 방화벽을 구성할 수 있습니다. 포트당이 아닌 응용 프로그램당을 기반으로 연결을 제어하는 데 이 방화벽을 사용할 수 있습니다. 이렇게 하면 쉽게 방화벽 보호의 이점을 얻고 바람직하지 않은 앱이 합법적인 앱에 대해 네트워크 포트 열기를 제어하는 것을 방지할 수 있습니다.
 
이 기능은 **장치 구성** -> **프로필 만들기** -> **macOS** -> **끝점 보호** 아래에서 찾을 수 있습니다.

일단 방화벽 설정을 사용하면 두 가지 전략을 사용하여 방화벽을 구성할 수 있습니다.

- 들어오는 모든 연결 차단

   대상 장치에 대해 들어오는 모든 연결을 차단할 수 있습니다. 이 작업 수행을 선택한 경우 모든 앱에 대해 들어오는 연결이 차단됩니다. 

- 특정 앱 허용 또는 차단

   들어오는 연결을 특정 앱이 수신하는 것을 허용하거나 차단할 수 있습니다. 검색 요청에 응답하지 않도록 은폐 모드를 사용할 수도 있습니다.
 
#### <a name="more-information"></a>추가 정보

- 들어오는 모든 연결 차단

   이는 모든 공유 서비스(예: 파일 공유, 화면 공유)가 들어오는 연결을 수신하는 것을 차단합니다. 들어오는 연결을 여전히 수신할 수 있는 시스템 서비스는 다음과 같습니다.
   - configd - DHCP 및 다른 네트워크 구성 서비스 구현
   - mDNSResponder - Bonjour 구현
   - racoon - IPSec 구현

   공유 서비스를 사용하려면 **들어오는 연결**이 **구성 되지 않음** (**차단**하지 않음)으로 설정되게 합니다.

- 은폐 모드

   이 모드를 사용하여 컴퓨터가 검색 요청에 응답하지 않게 합니다. 그래도 컴퓨터는 권한이 부여된 앱에 대해 들어오는 요청에는 응답합니다. ICMP(ping)와 같은 예기치 않은 요청은 무시합니다.
 

### <a name="updating-the-help-and-feedback-experience-on-company-portal-app-for-android---1631531---"></a>Android용 회사 포털 앱에서 도움말 및 피드백 환경 업데이트 <!--1631531 -->

Android 앱에 대한 모범 사례에 맞우기 위게 Android용 회사 포털 앱에서 도움말 및 피드백 환경을 업데이트합니다. **도움말 및 피드백** 메뉴 항목을 고유의 **도움말** 및 **피드백 보내기** 메뉴 항목으로 나누기 위해 향후 몇 개월 동안 Android용 회사 포털 앱을 업데이트합니다. **도움말** 페이지는 **질문과 대답** 섹션 및 **이메일 지원** 버튼이 특징적으로 최종 사용자가 Microsoft에 로그를 업로드하고 이 문제를 설명하는 고객 지원팀에 이메일을 보내도록 지원합니다. **피드백 보내기**는 사용자를 표준 Microsoft 피드백 제출 과정으로 이끌어 사용자가 "마음에 듭니다," "마음에 들지 않습니다" 또는 “잘 모르겠습니다” 여부를 선택하게 합니다.

### <a name="custom-book-categories-for-volume-purchase-program-vpp-ebooks----1488911---"></a>VPP(대량 구매 프로그램) 전자책에 대한 사용자 지정 책 범주 <!-- 1488911 -->
사용자 지정 전자책 범주를 만든 다음, 해당 사용자 지정 전자책 범주에 VPP 전자책을 할당할 수 있습니다. 그러면 최종 사용자는 새로 만든 전자책 범주 및 해당 범주에 할당된 책을 확인할 수 있습니다.

#### <a name="company-portal-for-android-visual-updates---976944---"></a>Android용 회사 포털 시각적 업데이트 <!--976944 -->

Android의 [자료 디자인](https://material.io/) 지침에 따라 Android용 회사 포털 앱을 업데이트합니다. 앱을 릴리스할 때 [앱 UI의 새로운 기능](whats-new-app-ui.md) 아티클에 새 아이콘의 이미지를 게시합니다. 

### <a name="edge-mobile-support-for-intune-app-protection-policies----1817882---"></a>Intune 앱 보호 정책용 Edge 모바일 지원<!-- 1817882 -->

모바일 장치용 Microsoft Edge 브라우저는 Intune에 정의된 앱 보호 정책을 지원합니다.

### <a name="use-fully-distinguished-name-as-subject-for-scep-certificate---2221763-eeready--"></a>SCEP 인증서에 대한 제목으로 정식 고유 이름 사용<!--2221763 eeready-->
SCEP 인증서 프로필을 만들 때 주체 이름을 입력합니다. 정식 고유 이름을 주체로 사용할 수 있습니다. **주체 이름**에서 **사용자 지정**을 선택한 다음, `CN={{OnPrem_Distinguished_Name}}`을 입력합니다. `{{OnPrem_Distinguished_Name}}` 변수를 사용하려면 [Azure AD(Active Directory) Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)를 사용하는 `onpremisesdistingishedname` 사용자 특성을 Azure AD와 동기화해야 합니다. 

### <a name="ios-devices-are-prompted-for-a-pin-every-15-minutes---1550837-eeready--"></a>iOS 장치에 15분마다 PIN을 입력하라는 메시지가 표시됩니다.<!--1550837 eeready-->
준수 또는 구성 정책을 iOS 장치에 적용하면 사용자에게 15분마다 PIN을 설정하라는 메시지가 표시됩니다. 사용자가 PIN을 설정할 때까지 계속 메시지가 표시됩니다.

### <a name="enable-bluetooth-contact-sharing---android-for-work---1098983-eeready--"></a>Bluetooth 연락처 공유 사용 - Android for Work<!--1098983 eeready-->
기본적으로 Android는 작업 프로필의 연락처를 Bluetooth 장치와 동기화하지 않도록 방지합니다. 결과적으로 작업 프로필 연락처는 Bluetooth 장치의 발신자 ID에 표시되지 않습니다.

**Android for Work** > **장치 제한** > **작업 프로필 설정**에서 새 설정이 지정됩니다.
- Bluetooth를 통한 연락처 공유

Intune 관리자는 공유할 수 있도록 이러한 설정을 구성할 수 있습니다. 핸즈 프리 사용에 호출자 ID를 표시하는 자동차 기반 Bluetooth 장치를 사용하여 장치를 연결하는 경우에 유용합니다. 사용하도록 설정하면 작업 프로필 연락처가 표시됩니다. 사용하지 않도록 설정하면 작업 프로필 연락처가 표시되지 않습니다.

적용 대상: Android OS v6.0 이상의 Android 작업 프로필 장치입니다.

### <a name="schedule-your-automatic-updates---1805514---"></a>자동 업데이트를 예약합니다.<!--1805514 -->

Intune에서는 [Windows Update 링 설정](windows-update-for-business-configure.md)을 사용하여 자동 업데이트를 설치하도록 제어할 수 있습니다. 주, 일, 시간을 비롯한 되풀이 업데이트를 예약할 수 있습니다. 

### <a name="disable-checks-on-device-restart---1805490---"></a>장치를 다시 시작에 대한 검사를 사용하지 않습니다.<!--1805490 -->

Intune에서는 [소프트웨어 업데이트를 관리](windows-update-for-business-configure.md)하는 컨트롤을 제공합니다. **검사 다시 시작** 속성을 추가하고 기본적으로 사용합니다. 장치를 다시 시작할 때 발생하는 일반적인 검사(예: 활성 사용자, 배터리 수준 등)를 건너뛰려면 **건너뛰기**를 선택합니다. 

<!-- 1802 start -->

### <a name="new-enrollment-failure-trend-chart-and-failure-reasons-table----1471783---"></a>새 등록 실패 추세 차트 및 실패 이유 테이블 <!-- 1471783 -->

등록 개요 페이지에서 등록 실패의 추세와 실패 원인 상위 5개를 확인할 수 있습니다. 차트 또는 테이블을 클릭하면 세부 사항을 드릴스루하여 문제 해결 도움말 및 재구성 제안을 찾을 수 있습니다.

### <a name="customize-your-company-portal-themes-with-hex-codes---1049561---"></a>16진수 코드를 사용하여 회사 포털 테마 사용자 지정 <!--1049561 -->

16진수 코드를 사용하여 회사 포털 앱에서 테마 색을 사용자 지정할 수 있습니다. 16진수 코드를 입력하면 Intune은 [WCAG 2.0 표준](http://www.w3.org/TR/WCAG20)에 따라 텍스트 색과 배경색 간의 대비가 가장 높은 텍스트 색을 결정합니다. **모바일 앱** > **회사 포털**에서 텍스트 색과 회사 로고를 미리 볼 수 있습니다. 

### <a name="new-windows-defender-credential-guard-settings-added-to-endpoint-protection-settings---1102252---"></a>엔드포인트 보호 설정에 추가된 새 Windows Defender Credential Guard 설정 <!--1102252 --> 

새 [Windows Defender Credential Guard](https://docs.microsoft.com/windows/access-protection/credential-guard/credential-guard] 설정이 **장치 구성** > **프로필** > **Endpoint Protection**에 추가됩니다. 다음 설정이 추가됩니다. 

- 플랫폼 보안 수준: 다음에 재부팅할 때 플랫폼 보안 수준의 사용 여부를 지정합니다. 가상화 기반 보안에는 보안 부팅 필요합니다. 필요에 따라 DMA(직접 메모리 액세스) 보호를 사용하여 가상화 기반 보안을 설정할 수 있습니다. DMA 보호는 하드웨어 지원이 필요하며 올바르게 구성된 장치에서만 작동합니다.
- 가상화 기반 보안: 다음에 재부팅할 때 가상화 기반 보안의 사용 여부를 지정합니다. 
- Windows Defender Credential Guard: 보안 부팅을 사용하는 플랫폼 보안 수준 및 가상화 기반 보안을 모두 사용하는 경우 다음에 재부팅할 때 자격 증명을 보호하려면 가상화 기반 보안을 사용하여 Credential Guard를 켜면 됩니다. 사용 가능한 옵션으로는 **사용 안 함**, **UEFI 잠금을 사용하여 설정**, **잠금 없이 설정** 및 **구성되지 않음**이 있습니다. 
  - "사용 안 함" 옵션은 이전에 "잠금 없이 설정" 옵션을 사용하여 Credential Guard를 켠 경우 원격으로 Credential Guard를 끄는 옵션입니다.

  - "UEFI 잠금을 사용하여 설정" 옵션을 사용하면 레지스트리 키 또는 그룹 정책을 사용하여 Credential Guard를 해제할 수 없습니다. 이 설정을 사용한 후 Credential Guard를 해제하려면 실존하는 사용자로 각 컴퓨터에서 그룹 정책을 "사용 안 함"으로 설정하고 보안 기능을 제거하여 UEFI에 남아 있는 구성을 지워야 합니다. UEFI 구성이 지속되는 한, Credential Guard가 계속 사용됩니다.

  - "잠금 없이 설정" 옵션을 선택하면 그룹 정책을 사용하여 원격으로 Credential Guard를 해제할 수 있습니다. 이 설정을 사용하는 장치는 Windows 10(버전 1511) 이상에서 실행되어야 합니다.

  - "구성되지 않음" 옵션은 정책 설정을 정의되지 않은 상태로 유지합니다. 그룹 정책은 레지스트리에 정책 설정을 쓰지 않으며, 따라서 컴퓨터 또는 사용자에게 영향을 주지 않습니다. 레지스트리에 현재 설정이 있는 경우 수정되지 않습니다.

### <a name="reset-passwords-for-android-o-devices----1238299---"></a>O Android 장치의 암호 다시 설정<!-- 1238299 -->
등록된 Android O 장치의 암호를 다시 설정할 수 있습니다. Android O 장치에 "암호 다시 설정" 요청을 보내면 Android O 장치는 현재 사용자의 새 장치 잠금 해제 암호 또는 관리되는 프로필 챌린지를 설정합니다. 암호 또는 챌린지는 장치에 프로필 소유자 또는 장치 소유자가 있는지 여부를 기반으로 전송되며, 즉시 적용됩니다.

### <a name="local-device-security-option-settings----1251887---"></a>로컬 장치 보안 옵션 설정 <!-- 1251887 -->
새 로컬 장치 보안 옵션 설정을 사용하여 Windows 10 장치에서 보안 설정을 사용하도록 설정할 수 있습니다. Windows 10 장치 구성 정책을 만들 때 Endpoint Protection 범주에서 이러한 설정을 찾아보세요.

### <a name="new-printer-settings-for-education-profiles----1308900---"></a>교육 프로필에 대한 새 프린터 설정 <!-- 1308900 -->

교육 프로필의 경우 **프린터** 범주의 **프린터**, **기본 프린터**, **새 프린터추가**에서 새 설정을 사용할 수 있습니다. 

### <a name="ios-app-provisioning-configuration----1581650---"></a>iOS 앱 프로비전 구성 <!-- 1581650 -->
보안 그룹을 포함 또는 제거하여 앱이 만료되지 않게 방지하는 IOS 앱 프로비전 프로필을 할당할 수 있습니다.

### <a name="new-windows-defender-application-guard-settings----1631890---"></a>새 Windows Defender Application Guard 설정 <!-- 1631890 -->

- **그래픽 가속 사용**

관리자는 Windows Defender Application Guard에 그래픽 가상 프로세서를 사용할 수 있습니다. 이 설정은 CPU가 그래픽 렌더링을 vGPU에 오프로드하는 것을 허용합니다. 이렇게 하면 컨테이너 내에서 그래픽 집약적인 웹 사이트를 작업하거나 비디오를 볼 때 성능을 향상할 수 있습니다.

- **SaveFilestoHost**

관리자는 컨테이너에서 실행되는 Microsoft Edge에서 호스트 파일 시스템으로 파일을 전달하도록 설정할 수 있습니다. 이 설정을 켜면 사용자가 컨테이너의 Microsoft Edge에서 호스트 파일 시스템으로 파일을 다운로드할 수 있습니다.

### <a name="including-and-excluding-app-assignment-based-on-groups-for-android-enterprise----1813081---"></a>Android Enterprise에 대한 그룹에 따라 앱 할당 포함 및 제외 <!-- 1813081 -->
Android Enterprise(이전의 Android for Work)는 앱을 할당하는 동안 그리고 할당 유형을 선택한 후 제외 기능을 지원합니다.

<!-- the following are present prior to 1802 -->

### <a name="targeting-compliance-policies-to-devices-in-device-groups---1307012---"></a>장치 그룹의 장치를 준수 정책의 대상으로 지정 <!--1307012 -->

사용자 그룹의 사용자를 준수 정책의 대상으로 지정할 수 있습니다. 장치 그룹의 장치를 준수 정책의 대상으로 지정할 수 있습니다.

<!-- the following are present prior to 1801 -->

### <a name="app-protection-policies-----679615---"></a>앱 보호 정책 <!-- 679615 -->
Intune 앱 보호 정책은 전체 테넌트의 모든 사용자에 대해 보호를 빠르게 사용할 수 있도록 전역 기본 정책을 만드는 기능을 제공합니다.

### <a name="configure-an-ios-app-pin----1586774---"></a>iOS 앱 PIN 구성 <!-- 1586774 -->
곧 사용자는 대상 iOS 앱에 대한 PIN이 필요하게 됩니다. Azure Portal을 통해 며칠 내에 PIN 요구 사항 및 만료 날짜를 구성할 수 있습니다. 필요한 경우 사용자는 iOS 앱에 대한 액세스를 얻기 전에 새 PIN을 설정 및 사용해야 합니다. Intune 앱 SDK와 함께 앱 보호가 설정된 iOS 앱만 이 기능을 지원합니다.

<!-- the following are present prior to 1711 -->

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Azure Active Directory 웹 사이트에는 Intune Managed Browser 앱이 필요하고 Managed Browser(공개 미리 보기)에 Single Sign-On을 지원할 수 있습니다.<!-- 710595 -->   
Azure AD(Azure Active Directory)를 사용하면 모바일 장치에서 웹 사이트에 대한 액세스를 Intune Managed Browser 앱으로 제한할 수 있습니다. Managed Browser에서 웹 사이트 데이터는 최종 사용자 개인 데이터와 별도로 안전하게 유지됩니다. 또한 Managed Browser는 Azure AD에서 보호하는 사이트에 Single Sign-On 기능을 지원합니다. Managed Browser에 로그인하거나 Intune에서 관리하는 다른 앱과 함께 장치에서 Managed Browser를 사용하면 사용자에게 자격 증명을 입력하지 않고도 Azure AD에서 보호되는 회사 사이트에 액세스할 수 있습니다. 이 기능은 OWA(Outlook Web Access) 및 SharePoint Online과 같은 사이트뿐만 아니라 Azure 앱 프록시를 통해 액세스되는 인트라넷 리소스와 같은 다른 회사 사이트에도 적용됩니다.

<!-- the following are present prior to 1711 -->

### <a name="redirecting-macos-users-to-the-new-company-portal-app---1380728--"></a>새 회사 포털 앱에 macOS 사용자 리디렉션 <!--1380728-->   
최종 사용자가 macOS 장치를 등록하기 위해 회사 포털 웹 사이트에 로그인하는 경우 프로세스를 완료하기 위해 macOS용 새 회사 포털 앱을 다운로드하도록 리디렉션됩니다. 이는 macOS 장치에서 OS X El Capitan 10.11 이상을 사용하는 경우에 발생합니다. 

<!-- the following are present prior to 1709 -->

### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>사용자가 등록이 허용된 최대 장치 수에 도달하면 표시되는 향상된 오류 메시지 <!-- 1270370 -->
일반적인 오류 메시지 대신 Android 장치를 사용하는 최종 사용자에게 “IT 관리자가 허용한 최대 장치 수를 등록했습니다. 등록된 장치를 제거하거나 IT 관리자에게 도움을 요청하세요.”라는 친숙하고 조치를 수행할 수 있는 오류 메시지가 표시됩니다.



## <a name="notices"></a>알림

이번에는 활성 알림이 없습니다.



### <a name="see-also"></a>참고 항목
최근 개발 작업에 대한 자세한 내용은 [Microsoft Intune의 새로운 기능](whats-new.md)을 참조하세요.


