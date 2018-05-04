---
title: 초기 버전
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b003fde011fd3a727c7c7a163fedb1dae6779425
ms.sourcegitcommit: 407191a92ef356a3d196b6f9959b9b033190ca2c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="the-early-edition-for-microsoft-intune---april-2018"></a>Microsoft Intune 초기 버전 - 2018년 4월

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

<!-- 1804 start -->

### <a name="show-caller-id-in-personal-profile---android-for-work---1098984---"></a>개인 프로필에 발신자 ID 표시 - Android for Work <!--1098984 -->
장치에서 개인 프로필을 사용하는 경우 회사 연락처의 발신자 ID 정보가 최종 사용자에게 표시되지 않을 수 있습니다. 

이 업데이트에서는 **Android for Work** > **장치 제한** > **작업 프로필 설정**에서 새 설정이 지정됩니다.
- 개인 프로필에 회사 연락처의 발신자 ID 표시

사용하도록 설정하면(구성하지 않음) 회사 연락처의 발신자 정보가 개인 프로필에 표시됩니다. 차단하면 회사 연락처의 발신자 번호가 개인 프로필에 표시되지 않습니다. 

적용 대상: Android OS v6.0 이상의 Android 회사 프로필 장치

### <a name="new-windows-defender-credential-guard-settings-added-to-endpoint-protection-settings---1102252-----from-1802--"></a>엔드포인트 보호 설정에 추가된 새 Windows Defender Credential Guard 설정 <!--1102252 --><!--from 1802-->

새 [Windows Defender Credential Guard](https://docs.microsoft.com/windows/access-protection/credential-guard/credential-guard) 설정이 **장치 구성** > **프로필** > **Endpoint Protection**에 추가됩니다. 다음 설정이 추가됩니다.

- 플랫폼 보안 수준: 다음에 재부팅할 때 플랫폼 보안 수준의 사용 여부를 지정합니다. 가상화 기반 보안에는 보안 부팅 필요합니다. 필요에 따라 DMA(직접 메모리 액세스) 보호를 사용하여 가상화 기반 보안을 설정할 수 있습니다. DMA 보호는 하드웨어 지원이 필요하며 올바르게 구성된 장치에서만 작동합니다.
- 가상화 기반 보안: 다음에 재부팅할 때 가상화 기반 보안의 사용 여부를 지정합니다.
- Windows Defender Credential Guard: 보안 부팅을 사용하는 플랫폼 보안 수준 및 가상화 기반 보안을 모두 사용하는 경우 다음에 재부팅할 때 자격 증명을 보호하려면 가상화 기반 보안을 사용하여 Credential Guard를 켜면 됩니다. 사용 가능한 옵션으로는 **사용 안 함**, **UEFI 잠금을 사용하여 설정**, **잠금 없이 설정** 및 **구성되지 않음**이 있습니다.
  - "사용 안 함" 옵션은 이전에 "잠금 없이 설정" 옵션을 사용하여 Credential Guard를 켠 경우 원격으로 Credential Guard를 끄는 옵션입니다.

  - "UEFI 잠금을 사용하여 설정" 옵션을 사용하면 레지스트리 키 또는 그룹 정책을 사용하여 Credential Guard를 해제할 수 없습니다. 이 설정을 사용한 후 Credential Guard를 해제하려면 실존하는 사용자로 각 컴퓨터에서 그룹 정책을 "사용 안 함"으로 설정하고 보안 기능을 제거하여 UEFI에 남아 있는 구성을 지워야 합니다. UEFI 구성이 지속되는 한, Credential Guard가 계속 사용됩니다.

  - "잠금 없이 설정" 옵션을 선택하면 그룹 정책을 사용하여 원격으로 Credential Guard를 해제할 수 있습니다. 이 설정을 사용하는 장치는 Windows 10(버전 1511) 이상에서 실행되어야 합니다.

  - "구성되지 않음" 옵션은 정책 설정을 정의되지 않은 상태로 유지합니다. 그룹 정책은 레지스트리에 정책 설정을 쓰지 않으며, 따라서 컴퓨터 또는 사용자에게 영향을 주지 않습니다. 레지스트리에 현재 설정이 있는 경우 수정되지 않습니다.

### <a name="passcode-support-for-mam-pin-on-android---1438086---"></a>Android에서 MAM PIN에 대한 암호 지원<!-- 1438086 -->

Intune 관리자는 숫자 MAM PIN 대신 암호를 적용하는 응용 프로그램 시작 요구 사항을 설정할 수 있습니다. 항목이 구성되면 사용자는 MAM 지원 응용 프로그램에 대한 액세스 권한을 가져오기 전에 메시지가 표시될 때 암호를 설정하고 사용합니다. 암호는 하나 이상의 특수 문자 또는 대/소문자 알파벳을 포함한 숫자 PIN으로 정의됩니다. Intune은 기존 숫자 PIN과 유사한 방식으로 암호를 지원합니다. 즉, 최소 길이를 설정하며 관리자 콘솔을 통해 반복 문자 및 시퀀스를 허용합니다. 이 기능을 사용하려면 Android에서 회사 포털의 최신 버전이 필요합니다. 현재 iOS에서는 이 기능을 사용할 수 있습니다.

###  <a name="block-camera-and-screen-captures-on-android-for-work----1098977-eeready--"></a>Android for Work에서 카메라 및 화면 캡처 차단 <!-- 1098977 eeready-->
두 개의 새로운 속성은 Android 장치에 대한 장치 제한을 구성할 때 차단할 수 있습니다. 
- 카메라: 장치에서 모든 카메라에 대한 액세스 차단
- 화면 캡처: 화면 캡처를 차단하고, 안전하지 않은 비디오 출력의 디스플레이 장치에 콘텐츠가 표시되지 않도록 방지

Android for Work에 적용됩니다.

### <a name="line-of-business-lob-app-support-for-macos----1473977---"></a>macOS에 대한 LOB(기간 업무) 앱 지원 <!-- 1473977 -->
Microsoft Intune은 Azure Portal에서 macOS LOB 앱을 설치하는 기능을 제공할 예정입니다. GitHub에서 사용할 수 있는 도구에서 미리 처리된 macOS LOB 앱을 Intune에 추가할 수 있습니다. Azure Portal에서 **Intune** 블레이드의 **모바일 앱**을 선택합니다. **모바일 앱** 블레이드에서 **앱** > **추가**를 선택합니다. **앱 추가** 블레이드에서 **LOB(기간 업무) 앱**을 선택합니다. 

### <a name="support-for-user-less-devices----1637553---"></a>사용자가 지정되지 않은 장치에 대한 지원 <!-- 1637553 -->
Intune은 Microsoft Surface Hub와 같은 사용자가 지정되지 않은 장치에서 준수를 평가하는 기능을 지원할 예정입니다. 준수 정책은 특정 장치를 대상으로 지정할 수 있습니다. 따라서 연결된 사용자가 없는 장치에 대해 준수(및 비준수)를 확인할 수 있습니다.

### <a name="additions-to-local-device-security-options-settings----1403702---"></a>로컬 장치 보안 옵션 설정에 대한 추가 <!-- 1403702 -->
Windows 10 장치에 대한 추가 로컬 장치 보안 옵션 설정을 구성할 수 있습니다. 추가 설정은 Microsoft Network Client, Microsoft Network Server, 네트워크 액세스 및 보안 및 대화형 로그온의 영역에서 사용될 수 있습니다. Windows 10 장치 구성 정책을 만들 때 Endpoint Protection 범주에서 이러한 설정을 찾아보세요.

### <a name="require-installation-of-policies-apps-certificate-and-network-profiles----1553555---"></a>정책, 앱, 인증서 및 네트워크 프로필의 설치 필요 <!-- 1553555 -->
관리자는 AutoPilot 장치를 프로비전하는 동안 Intune에서 정책, 앱, 인증서 및 네트워크 프로필을 설치할 때까지 최종 사용자가 Windows 10 RS4 데스크톱에 액세스하지 못하도록 차단할 수 있습니다.

### <a name="rules-for-removing-devices----1609459---"></a>장치 제거에 대한 규칙 <!-- 1609459 -->
설정한 일 수 동안 체크 인하지 않은 장치를 자동으로 제거할 수 있는 새 규칙이 제공됩니다. 새 규칙을 보려면 **Intune** 창으로 이동하여 **장치**를 선택하고 **장치 제거 규칙**을 선택합니다.

### <a name="prevent-consumer-apps-and-experiences-on-windows-10-enterprise-rs4-autopilot-devices---1621980---"></a>Windows 10 Enterprise RS4 Autopilot 장치에서 소비자 앱과 경험을 방지<!-- 1621980 -->
Windows 10 Enterprise RS4 AutoPilot 장치에서 소비자 앱 및 환경을 설치하지 못하도록 방지할 수 있습니다. 이 기능을 확인하려면 **Intune** > **장치 등록** > **Windows 등록** > **Windows AutoPilot 프로필** > **새로 만들기** > **등록 설정**으로 이동합니다. 

### <a name="advanced-threat-protection-integrated-with-intune----1629303---"></a>Intune과 통합된 Advanced Threat Protection <!-- 1629303 -->
[ATP(Advanced Threat Protection)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/dashboard-windows-defender-advanced-threat-protection)는 Windows 10 장치의 위험 수준을 표시합니다. Intune에서 Windows 10 장치의 준수를 평가할 때 ATP 위험 점수가 이 평가에 포함됩니다. 조건부 액세스와 함께 ATP를 사용하면 네트워크를 보호하는 데 도움이 됩니다.

### <a name="new-enrollment-steps-for-users-on-devices-with-macos-high-sierra-10132---1734567---"></a>macOS High Sierra 10.13.2+를 사용하는 장치에서 사용자를 위한 새로운 등록 단계 <!--1734567 -->
macOS high Sierra 10.13.2에 “사용자 승인” MDM 등록의 개념이 도입되었습니다. 앞으로 승인된 등록을 사용하면 Intune에서 몇 가지 중요한 보안 설정을 관리할 수 있습니다. 자세한 내용은 Apple의 지원 문서를 참조하세요. https://support.apple.com/HT208019

macOS 회사 포털을 사용하여 등록된 장치는 최종 사용자가 시스템 기본 설정을 열고 수동으로 승인을 제공하지 않는 한 “사용자 승인되지 않음”으로 간주됩니다. 이를 위해 macOS 회사 포털은 이제 macOS 10.13.2 이상의 사용자에게 등록 프로세스 마지막 단계에서 해당 등록을 수동으로 승인하도록 안내합니다. Intune 관리 콘솔은 등록된 장치가 사용자 승인되지 않은 경우 보고합니다.

### <a name="delete-autopilot-devices----1713650---"></a>Autopilot 장치 삭제 <!-- 1713650 -->
Intune 관리자가 Autopilot 장치를 삭제할 수 있습니다.

### <a name="built-in-all-users-and-all-devices-group-for-android-for-work-afw-app-assignment----1813073---"></a>AFW(Android for Work) 앱 할당을 위한 기본 제공된 모든 사용자 및 모든 장치 그룹 <!-- 1813073 -->
AFW 앱 할당을 위해 기본 제공된 **모든 사용자** 및 **모든 장치** 그룹을 활용할 수 있습니다. 자세한 내용은 [Microsoft Intune에서 앱 할당 포함 및 제외](apps-inc-exl-assignments.md)를 참조하세요.

### <a name="improved-device-deletion-experience---1832333---"></a>향상된 장치 삭제 환경 <!--1832333 -->
이제 Intune에서 장치를 삭제하기 전에 회사 데이터를 제거하거나 장치를 출하 시 설정으로 리셋할 필요가 없습니다.

새 환경을 보려면 Intune에 로그인하고 **장치** > **모든 장치** > 장치 이름 > **삭제**를 선택합니다.

 초기화/사용 중지 확인을 수행하려면 **삭제**하기 전에 **회사 데이터 제거** 및 **출하 시 설정으로 리셋**을 실행하여 표준 장치 수명 주기를 사용할 수 있습니다. 

### <a name="autopilot-profiles-moving-to-group-targeting----1877935---"></a>Autopilot 프로필을 대상 지정 그룹으로 이동 <!-- 1877935 -->
현재 AutoPilot 배포 프로필을 선택된 장치에 할당할 수 있습니다. 4월 말경 이러한 프로필을 다음과 같이 할당하게 됩니다.
- AutoPilot 장치가 포함된 (Azure AD) 그룹을 만듭니다.
- Azure AD 그룹에 원하는 프로필을 할당합니다. 이제 AutoPilot 프로필을 해당 그룹의 AutoPilot 장치에 할당할 수 있습니다.

### <a name="play-sounds-on-ios-when-in-lost-mode----1629303---"></a>분실 모드에 있을 때 iOS에서 소리 재생 <!-- 1629303 -->
감독 중인 iOS 장치가 MDM(모바일 장치 관리) [분실 모드](device-lost-mode.md)에 있는 경우 소리를 재생할 수 있습니다(**장치** > **모든 장치** > iOS 장치 선택 > **개요** > **자세히**). 소리는 장치가 분실 모드에서 제거되거나 사용자가 장치에서 소리를 사용하지 않도록 설정할 때까지 계속 재생할 수 있습니다. iOS 장치 9.3 이상에서 적용됩니다.

### <a name="intune-will-reinstall-required-apps-that-are-uninstalled-by-users----1947010---"></a>사용자가 제거한 필수 앱을 Intune에서 다시 설치함 <!-- 1947010 -->
최종 사용자가 필수 앱을 제거할 경우 Intune에서 7일 재평가 주기를 기다리지 않고 24시간 이내에 앱을 자동으로 다시 설치합니다.

### <a name="use-a-custom-subject-name-on-scep-certificate----2064190---"></a>SCEP 인증서에서 사용자 지정 주체 이름 사용 <!-- 2064190 -->
SCEP 인증서 프로필에서 사용자 지정 주체에 **OnPremisesSamAccountName** 일반 이름을 사용할 수 있습니다. 예를 들어 `CN={OnPremisesSamAccountName})`를 사용할 수 있습니다.

### <a name="send-diagnostic-reports-in-company-portal-app-for-macos----2216677---"></a>macOS용 회사 포털 앱에 진단 보고서 보내기 <!-- 2216677 -->
사용자가 Intune 관련 오류를 보고하는 방법을 개선하기 위해 macOS 장치에 대한 회사 포털 앱이 업데이트됩니다. 회사 포털 앱에서 직원들은 다음을 수행할 수 있습니다.
- Microsoft 개발자 팀에 직접 진단 보고서를 업로드합니다.
- 인시던트 ID를 회사의 IT 지원 팀에게 이메일로 전송합니다.

### <a name="always-on-vpn-for-windows-10---1333666---"></a>Always On VPN for Windows 10 <!--1333666 -->

현재 [Always On](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-auto-trigger-profile#always-on)은 OMA-URI를 통해 만든 사용자 지정 VPN(가상 사설망) 프로필을 사용하여 Windows 10 장치에서 사용할 수 있습니다.

이 업데이트를 사용하면 관리자는 Azure Portal의 Intune에서 직접 Always On for Windows 10 VPN 프로필을 사용하도록 설정할 수 있습니다. Always On VPN 프로필은 다음과 같은 경우 자동으로 연결됩니다.

- 자신의 장치에 사용자가 로그인하는 경우
- 장치의 네트워크가 변경되는 경우
- 장치의 화면이 꺼졌다가 다시 켜지는 경우

### <a name="improved-error-messaging-for-apple-mdm-push-certificate-upload-failure----2172331---"></a>Apple MDM 푸시 인증서 업로드 실패에 대한 향상된 오류 메시지 <!-- 2172331 -->

오류 메시지는 기존 MDM 인증서를 갱신할 때 동일한 Apple ID를 사용해야 함을 설명합니다.

###  <a name="device-profile-chart-and-status-list-show-all-devices-in-a-group----1449153-eeready---"></a>장치 프로필 차트 및 상태 목록에서 그룹의 모든 장치를 표시 <!-- 1449153 eeready -->
장치 프로필을 구성할 때(**장치 구성** > **프로필**), iOS와 같은 장치 프로필을 선택합니다. iOS 장치 및 비 iOS 장치를 포함하는 그룹에 이 프로필을 할당합니다. 그래픽 차트 수는 프로필이 iOS *및* 비 iOS 장치에 적용되었음을 나타냅니다(**장치 구성** > **프로필** > 기존 프로필 선택 > **개요**). **개요** 탭에서 그래픽 차트를 선택하면 **장치 상태**에 iOS 장치 대신 그룹의 모든 장치가 나열됩니다. 

이 업데이트를 사용하면 그래픽 차트(**장치 구성** > **프로필** > 기존 프로필 선택 > **개요**)에는 특정 장치 프로필에 대한 개수만 항목만 표시됩니다. 예를 들어 구성 장치 프로필이 iOS 장치에 적용되는 경우 차트는 iOS 장치의 개수만 나열됩니다. 그래픽 차트를 선택하고 **장치 상태**를 열면 iOS 장치만 나열됩니다.

이 업데이트를 수행하는 동안 그래픽 사용자 차트는 일시적으로 제거됩니다. 


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

### <a name="ability-to-deploy-required-line-of-business-lob-apps-to-all-users-on-windows-10-desktop-devices----1627835-rs4---"></a>Windows 10 Desktop 장치의 모든 사용자에게 필수 LOB(기간 업무) 앱을 배포하는 기능 <!-- 1627835 RS4 -->
고객은 필수 LOB(기간 업무) Windows 10 앱을 장치 컨텍스트에 설치하도록 배포할 수 있습니다. 이렇게 하면 이러한 앱을 장치의 모든 사용자가 사용할 수 있습니다. 이 기능은 Windows 10 Desktop 장치에만 적용됩니다.

### <a name="company-portal-enrollment-improved----1874230--"></a>회사 포털 등록 향상<!-- 1874230-->
Windows 10 Build 1703 이상에서 회사 포털을 사용하여 장치를 등록하는 사용자는 해당 앱을 종료하지 않고 등록의 첫 번째 단계를 완료할 수 있습니다.

### <a name="updating-the-help-and-feedback-experience-on-company-portal-app-for-android---1631531---"></a>Android용 회사 포털 앱에서 도움말 및 피드백 환경 업데이트 <!--1631531 -->

Android 앱에 대한 모범 사례에 맞우기 위게 Android용 회사 포털 앱에서 도움말 및 피드백 환경을 업데이트합니다. **도움말 및 피드백** 메뉴 항목을 고유의 **도움말** 및 **피드백 보내기** 메뉴 항목으로 나누기 위해 향후 몇 개월 동안 Android용 회사 포털 앱을 업데이트합니다. **도움말** 페이지는 **질문과 대답** 섹션 및 **이메일 지원** 버튼이 특징적으로 최종 사용자가 Microsoft에 로그를 업로드하고 이 문제를 설명하는 고객 지원팀에 이메일을 보내도록 지원합니다. **피드백 보내기**는 사용자를 표준 Microsoft 피드백 제출 과정으로 이끌어 사용자가 "마음에 듭니다," "마음에 들지 않습니다" 또는 “잘 모르겠습니다” 여부를 선택하게 합니다.

<!-- 1802 start -->

### <a name="new-printer-settings-for-education-profiles----1308900---"></a>교육 프로필에 대한 새 프린터 설정 <!-- 1308900 -->

교육 프로필의 경우 **프린터** 범주의 **프린터**, **기본 프린터**, **새 프린터추가**에서 새 설정을 사용할 수 있습니다.

<!-- the following are present prior to 1801 -->

### <a name="app-protection-policies-----679615---"></a>앱 보호 정책 <!-- 679615 -->
Intune 앱 보호 정책은 전체 테넌트의 모든 사용자에 대해 보호를 빠르게 사용할 수 있도록 전역 기본 정책을 만드는 기능을 제공합니다.

<!-- the following are present prior to 1711 -->

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Azure Active Directory 웹 사이트에는 Intune Managed Browser 앱이 필요하고 Managed Browser(공개 미리 보기)에 Single Sign-On을 지원할 수 있습니다.<!-- 710595 -->   
Azure AD(Azure Active Directory)를 사용하면 모바일 장치에서 웹 사이트에 대한 액세스를 Intune Managed Browser 앱으로 제한할 수 있습니다. Managed Browser에서 웹 사이트 데이터는 최종 사용자 개인 데이터와 별도로 안전하게 유지됩니다. 또한 Managed Browser는 Azure AD에서 보호하는 사이트에 Single Sign-On 기능을 지원합니다. Managed Browser에 로그인하거나 Intune에서 관리하는 다른 앱과 함께 장치에서 Managed Browser를 사용하면 사용자에게 자격 증명을 입력하지 않고도 Azure AD에서 보호되는 회사 사이트에 액세스할 수 있습니다. 이 기능은 OWA(Outlook Web Access) 및 SharePoint Online과 같은 사이트뿐만 아니라 Azure 앱 프록시를 통해 액세스되는 인트라넷 리소스와 같은 다른 회사 사이트에도 적용됩니다.




## <a name="notices"></a>알림

이번에는 활성 알림이 없습니다.


### <a name="see-also"></a>참고 항목
최근 개발 작업에 대한 자세한 내용은 [Microsoft Intune의 새로운 기능](whats-new.md)을 참조하세요.


