---
title: "초기 버전"
description: 
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/24/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 7d54cb060dc44d29c95203138396f771abbb2325
ms.sourcegitcommit: 6d69403266dbcb31c879432719798935c94917fa
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2018
---
# <a name="the-early-edition-for-microsoft-intune---february-2018"></a>Microsoft Intune 초기 버전 - 2018년 2월

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


<!-- 1802 start -->

### <a name="new-enrollment-failure-trend-chart-and-failure-reasons-table----1471783---"></a>새 등록 실패 추세 차트 및 실패 이유 테이블 <!-- 1471783 -->

등록 개요 페이지에서 등록 실패의 추세와 실패 원인 상위 5개를 확인할 수 있습니다. 차트 또는 테이블을 클릭하면 세부 사항을 드릴스루하여 문제 해결 도움말 및 재구성 제안을 찾을 수 있습니다.

### <a name="prevent-end-users-from-adding-or-removing-accounts-in-the-work-profile----1728700---"></a>최종 사용자가 작업 프로필의 계정을 추가 또는 삭제하지 못하게 방지 <!-- 1728700 -->    
Gmail 앱을 Android for Work 프로필에 배포하면, Android for Work 장치 제한 프로필에서 **계정 추가 및 제거** 설정을 사용하여 최종 사용자가 작업 프로필에 계정을 추가하거나 삭제하지 못하게 할 수 있습니다.

### <a name="app-protection-policies-----679615---"></a>앱 보호 정책 <!-- 679615 -->
Intune 앱 보호 정책은 전체 테넌트의 모든 사용자에 대해 보호를 빠르게 사용할 수 있도록 전역 기본 정책을 만드는 기능을 제공합니다.

### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685---"></a>여러 Apple DEP/Apple School Manager 계정에 대한 Intune 지원 <!-- 747685 -->

Intune은 최대 100개의 다른 Apple DEP(장비 등록 프로그램) 또는 Apple School Manager 계정의 장치 등록을 지원합니다. 업로드된 각 토큰을 등록 프로필과 장치에 대해 별도로 관리할 수 있습니다. 업로드된 DEP/School Manager 토큰마다 다른 등록 프로필을 자동으로 할당할 수 있습니다. School Manager 토큰이 여러 개 업로드된 경우 한 번에 하나의 토큰만 Microsoft School Data Sync와 공유할 수 있습니다.

Graph를 통해 Apple DEP 또는 ASM을 관리하기 위한 베타 Graph API 및 게시된 스크립트는 마이그레이션 후 더 이상 작동하지 않습니다. 새 베타 Graph API가 개발 중이며 마이그레이션 후 릴리스될 예정입니다.

### <a name="windows-defender-health-status-and-threat-status-reports---854704---"></a>Windows Defender 상태 및 위협 상태 보고서 <!--854704 -->

Windows Defender의 상태를 이해하는 것은 Windows PC 관리의 핵심입니다.  Intune은 Windows Defender 에이전트의 상태에 새 보고서와 작업을 추가합니다. 장치 정책 준수 워크로드에 상태 롤업 보고서를 사용하면 다음 작업이 필요한 장치를 볼 수 있습니다.

- 서명 업데이트
- 다시 시작
- 수동 작업
- 전체 검사
- 개입이 필요한 기타 에이전트 상태

경우에 따라 서명 업데이트 트리거 같은 원격 수정 작업을 수행할 수 있습니다.  또한 보고서에는 **정리**로 보고되는 PC 수가 표시됩니다.

각 상태 범주에 대한 드릴인 보고서에는 주의가 필요한 개별 PC 또는 **정리**로 보고되는 PC가 나열됩니다.

### <a name="protocol-exceptions-for-applications---1035509-eeready--"></a>응용 프로그램에 대한 프로토콜 예외 <!--1035509 eeready-->

Intune MAM(모바일 응용 프로그램 관리) 데이터 전송 정책에 대한 예외를 만들어서 관리되지 않는 응용 프로그램을 열 수 있습니다. 이러한 응용 프로그램은 IT가 신뢰할 수 있는 것이어야 합니다. 관리자가 만드는 예외를 제외하고, 데이터 전송 정책을 **관리되는 앱만**으로 설정하는 경우 데이터 전송은 Intune에서 관리하는 응용 프로그램으로 계속 제한됩니다. 프로토콜(iOS) 또는 패키지(Android)를 사용하여 제한을 만들 수 있습니다.

예를 들어 Webex 패키지를 MAM 데이터 전송 정책의 예외로 추가할 수 있습니다. 이렇게 하면 관리되는 Outlook 이메일 메시지의 Webex 링크가 Webex 응용 프로그램에서 바로 열립니다. 관리되지 않는 다른 응용 프로그램에서는 데이터 전송이 계속 제한됩니다.

### <a name="customize-your-company-portal-themes-with-hex-codes---1049561-eeready--"></a>16진수 코드를 사용하여 회사 포털 테마 사용자 지정 <!--1049561 eeready-->

16진수 코드를 사용하여 회사 포털 앱에서 테마 색을 사용자 지정할 수 있습니다. 16진수 코드를 입력하면 Intune은 [WCAG 2.0 표준](http://www.w3.org/TR/WCAG20)에 따라 텍스트 색과 배경색 간의 대비가 가장 높은 텍스트 색을 결정합니다. **모바일 앱** > **회사 포털**에서 텍스트 색과 회사 로고를 미리 볼 수 있습니다. 

### <a name="new-windows-defender-credential-guard-settings-added-to-endpoint-protection-settings---1102252---"></a>엔드포인트 보호 설정에 추가된 새 Windows Defender Credential Guard 설정 <!--1102252 --> 

새 [Windows Defender Credential Guard](https://docs.microsoft.com/windows/access-protection/credential-guard/credential-guard] 설정은 **장치 구성** > **프로필** > **엔드포인트 보호**에 추가됩니다. 다음 설정이 추가됩니다. 

- 플랫폼 보안 수준: 다음에 재부팅할 때 플랫폼 보안 수준의 사용 여부를 지정합니다. 가상화 기반 보안에는 보안 부팅 필요합니다. 필요에 따라 DMA(직접 메모리 액세스) 보호를 사용하여 가상화 기반 보안을 설정할 수 있습니다. DMA 보호는 하드웨어 지원이 필요하며 올바르게 구성된 장치에서만 작동합니다.
- 가상화 기반 보안: 다음에 재부팅할 때 가상화 기반 보안의 사용 여부를 지정합니다. 
- Windows Defender Credential Guard: 보안 부팅을 사용하는 플랫폼 보안 수준 및 가상화 기반 보안을 모두 사용하는 경우 다음에 재부팅할 때 자격 증명을 보호하려면 가상화 기반 보안을 사용하여 Credential Guard를 켜면 됩니다. 사용 가능한 옵션으로는 **사용 안 함**, **UEFI 잠금을 사용하여 설정**, **잠금 없이 설정** 및 **구성되지 않음**이 있습니다. 
  - "사용 안 함" 옵션은 이전에 "잠금 없이 설정" 옵션을 사용하여 Credential Guard를 켠 경우 원격으로 Credential Guard를 끄는 옵션입니다.

  - "UEFI 잠금을 사용하여 설정" 옵션을 사용하면 레지스트리 키 또는 그룹 정책을 사용하여 Credential Guard를 해제할 수 없습니다. 이 설정을 사용한 후 Credential Guard를 해제하려면 실존하는 사용자로 각 컴퓨터에서 그룹 정책을 "사용 안 함"으로 설정하고 보안 기능을 제거하여 UEFI에 남아 있는 구성을 지워야 합니다. UEFI 구성이 지속되는 한, Credential Guard가 계속 사용됩니다.

  - "잠금 없이 설정" 옵션을 선택하면 그룹 정책을 사용하여 원격으로 Credential Guard를 해제할 수 있습니다. 이 설정을 사용하는 장치는 Windows 10(버전 1511) 이상에서 실행되어야 합니다.

  - "구성되지 않음" 옵션은 정책 설정을 정의되지 않은 상태로 유지합니다. 그룹 정책은 레지스트리에 정책 설정을 쓰지 않으며, 따라서 컴퓨터 또는 사용자에게 영향을 주지 않습니다. 레지스트리에 현재 설정이 있는 경우 수정되지 않습니다.

### <a name="synchronize-and-deploy-sparsely-bundled-windows-store-for-business-apps---1222672---"></a>부분적으로 번들된 비즈니스용 Windows 스토어 앱 동기화 및 배포 <!--1222672 -->
비즈니스용 Windows 스토어에서 구매한 오프라인 앱이 Intune 포털에 동기화됩니다. 그런 다음 이러한 앱을 장치 그룹 또는 사용자 그룹에 배포할 수 있습니다. 오프라인 앱은 스토어가 아닌 Intune을 통해 설치됩니다.

### <a name="reset-passwords-for-android-o-devices----1238299---"></a>O Android 장치의 암호 다시 설정<!-- 1238299 -->
등록된 Android O 장치의 암호를 다시 설정할 수 있습니다. Android O 장치에 "암호 다시 설정" 요청을 보내면 Android O 장치는 현재 사용자의 새 장치 잠금 해제 암호 또는 관리되는 프로필 챌린지를 설정합니다. 암호 또는 챌린지는 장치에 프로필 소유자 또는 장치 소유자가 있는지 여부를 기반으로 전송되며, 즉시 적용됩니다.

### <a name="local-device-security-option-settings----1251887---"></a>로컬 장치 보안 옵션 설정 <!-- 1251887 -->
새 로컬 장치 보안 옵션 설정을 사용하여 Windows 10 장치에서 보안 설정을 사용하도록 설정할 수 있습니다. Windows 10 장치 구성 정책을 만들 때 Endpoint Protection 범주에서 이러한 설정을 찾아보세요.

### <a name="new-printer-settings-for-education-profiles----1308900---"></a>교육 프로필에 대한 새 프린터 설정 <!-- 1308900 -->

교육 프로필의 경우 **프린터** 범주의 **프린터**, **기본 프린터**, **새 프린터추가**에서 새 설정을 사용할 수 있습니다. 

### <a name="new-privacy-settings-for-device-restrictions---1308926---"></a>장치 제안에 대한 새로운 개인 정보 설정 <!--1308926 -->

장치에 대한 두 가지 새로운 개인 정보 설정을 사용할 수 있습니다.

- **사용자 작업 게시**: 작업 전환기에서 공유 경험 및 최근에 사용된 리소스 검색을 차단하려면 이 옵션을 **차단**으로 설정합니다.

- **로컬 작업만**: 로컬 작업에 대해서만 작업 전환기에서 공유 경험 및 최근에 사용된 리소스 검색을 차단하려면 이 옵션을 **차단**으로 설정합니다.

### <a name="macos-company-portal-support-for-enrollments-that-use-the-device-enrollment-manager----1352411---"></a>macOS 회사 포털은 장치 등록 관리자를 사용한 등록을 지원 <!-- 1352411 -->

사용자는 macOS 회사 포털에 등록할 때 장치 등록 관리자를 사용할 수 있습니다.

#### <a name="new-settings-for-the-edge-browser---1469166---"></a>Edge 브라우저에 대한 새 설정 <!--1469166 -->

Microsoft Edge 브라우저에서는 두 가지 새로운 설정인 **자주 사용하는 파일 경로** 및 **즐겨찾기에 대한 변경**을 사용할 수 있습니다. 

### <a name="windows-information-protection-wip-encrypted-data-in-windows-search-results----1469193---"></a>Windows 검색 결과의 WIP(Windows Information Protection) 암호화된 데이터 <!-- 1469193 -->

WIP(Windows Information Protection) 정책의 새 설정을 사용하면 WIP 암호화된 데이터를 Windows 검색 결과에 포함할지 여부를 제어할 수 있습니다.

### <a name="line-of-business-lob-app-support-for-macos----1473977---"></a>macOS에 대한 LOB(기간 업무) 앱 지원 <!-- 1473977 -->
Intune은 macOS LOB 앱을 설치하는 기능을 제공할 예정입니다. LOB 앱은 관리자가 설치 파일을 제공하면 사용자가 Intune을 사용하여 장치에 앱을 설치하는 앱입니다. macOS LOB 앱 지원의 일환으로, 관리자는 macOS용 Microsoft Intune 앱 래핑 도구를 사용하여 macOS LOB(기간 업무) 앱을 미리 처리해야 합니다.

### <a name="configure-resource-account-settings-for-surface-hubs----1475674---"></a>Surface Hub에 대한 리소스 계정 설정 구성 <!-- 1475674 -->

Surface Hub에 대한 리소스 계정 설정을 원격으로 구성할 수 있습니다.

리소스 계정은 Surface Hub가 Skype/Exchange에 인증하는 데 사용되므로 모임에 참여할 수 있습니다. Surface Hub가 모임에서 회의실로 표시되도록 고유한 리소스 계정을 만들 수 있습니다. 예를 들어 **회의실 B41/6233**이라는 리소스 계정을 만들 수 있습니다.

> [!NOTE]
> - 필드를 비워 두면 장치에서 이전에 구성된 특성이 재정의됩니다.
>
> - 리소스 계정 속성은 Surface Hub에서 동적으로 변경할 수 있습니다. 예를 들어 암호 순환이 켜져 있으면 Azure 콘솔의 값이 장치에서 현실을 반영할 때까지 다소 시간이 걸릴 수 있습니다. 
>
>   리소스 계정 정보를 하드웨어 인벤토리에(이미 7일 간격이 있음) 또는 읽기 전용 속성으로 포함하면 현재 Surface Hub에 구성된 내용을 이해할 수 있습니다. 원격 작업을 실행한 후 정확도를 높이려면 Surface Hub에서 계정/매개 변수 업데이트 작업을 실행하는 즉시 매개 변수 상태를 가져오면 됩니다.

### <a name="ios-app-provisioning-configuration----1581650---"></a>iOS 앱 프로비전 구성 <!-- 1581650 -->
보안 그룹을 포함 또는 제거하여 앱이 만료되지 않게 방지하는 IOS 앱 프로비전 프로필을 할당할 수 있습니다.

### <a name="new-windows-defender-exploit-guard-settings----631893---"></a>새로운 Windows Defender Exploit Guard 설정 <!-- 631893 -->

6개의 새 **공격 노출 영역 축소** 설정 및 확장된 **폴더 액세스 제어: 폴더 보호** 기능이 제공될 예정입니다. 이러한 설정은 Device configuration\Profiles\에서 찾을 수 있습니다.
profile\Endpoint protection\Windows Defender Exploit Guard를 만드세요.

#### <a name="attack-surface-reduction"></a>공격 노출 영역 축소

|설정 이름  |설정 옵션  |설명  |
|---------|---------|---------|
|고급 랜섬웨어 보호|사용, 감사, 구성되지 않음|적극적인 랜섬웨어 보호를 사용합니다.|
|Windows 로컬 보안 기관 하위 시스템에서 도용하는 자격 증명에 플래그 지정|사용, 감사, 구성되지 않음|Windows 로컬 보안 기관 하위 시스템(lsass.exe)에서 도용하는 자격 증명에 플래그를 지정합니다.|
|PSExec 및 WMI 명령에서 프로세스 만들기|차단, 감사, 구성되지 않음|PSExec 및 WMI 명령에서 발생하는 프로세스 만들기를 차단합니다.|
|USB에서 실행되는 신뢰할 수 없고 서명되지 않은 프로세스|차단, 감사, 구성되지 않음|USB에서 실행되는 신뢰할 수 없고 서명되지 않은 프로세스를 차단합니다.|
|출현율, 나이 또는 신뢰할 수 있는 목록 기준을 충족하지 않는 실행 파일|차단, 감사, 구성되지 않음|실행 파일이 출현율, 나이 또는 신뢰할 수 있는 목록 기준을 충족하지 않으면 실행을 차단합니다.|

#### <a name="controlled-folder-access"></a>폴더 액세스 제어

|설정 이름  |설정 옵션  |설명  |
|---------|---------|---------|
|폴더 보호(이미 구현됨)|구성되지 않음, 사용, 감사만(이미 구현됨)<br><br> **새 항목**<br>디스크 수정 차단, 디스크 수정 감사|
인증되지 않은 앱이 파일 및 폴더를 무단으로 변경할 수 없도록 보호합니다.<br><br>**사용**: 신뢰할 수 없는 앱이 보호되는 폴더의 파일을 수정 또는 삭제하거나 디스크 섹터에 쓰는 것을 차단합니다.<br><br>
**디스크 수정만 차단**:<br>신뢰할 수 없는 앱이 디스크 섹터에 쓰는 것을 차단합니다. 신뢰할 수 없는 앱이 보호되는 폴더의 파일을 여전히 수정하거나 삭제할 수 있습니다.|

### <a name="new-windows-defender-application-guard-settings----1631890---"></a>새 Windows Defender Application Guard 설정 <!-- 1631890 -->

- **그래픽 가속 사용**

관리자는 Windows Defender Application Guard에 그래픽 가상 프로세서를 사용할 수 있습니다. 이 설정은 CPU가 그래픽 렌더링을 vGPU에 오프로드하는 것을 허용합니다. 이렇게 하면 컨테이너 내에서 그래픽 집약적인 웹 사이트를 작업하거나 비디오를 볼 때 성능을 향상할 수 있습니다.

- **SaveFilestoHost**

관리자는 컨테이너에서 실행되는 Microsoft Edge에서 호스트 파일 시스템으로 파일을 전달하도록 설정할 수 있습니다. 이 설정을 켜면 사용자가 컨테이너의 Microsoft Edge에서 호스트 파일 시스템으로 파일을 다운로드할 수 있습니다.

### <a name="see-enrollment-restrictions-per-user----1634444---"></a>사용자별 등록 제한 보기 <!-- 1634444 -->
문제 해결 블레이드에서 각 사용자에게 적용되는 등록 제한을 볼 수 있습니다.

### <a name="configuring-a-self-updating-mobile-msi-app----1740840---"></a>자체 업데이트 모바일 MSI 앱 구성 <!-- 1740840 -->
버전 확인 프로세스를 무시하도록 알려진 자체 업데이트 모바일 MSI 앱을 구성할 수 있습니다. 이 기능은 경합 상태를 방지하는 데 유용합니다. 예를 들어 앱 개발자가 앱을 자동 업데이트하는 동시에 Intune에서도 앱을 업데이트하는 경우 경합이 발생할 수 있습니다. 둘 다 Windows 클라이언트에서 앱 버전을 적용하려 시도할 수 있으며, 이로 인해 충돌이 발생할 수 있습니다.

### <a name="additions-to-system-security-settings-for-windows-10-and-later-compliance-policies---1704133---"></a>Windows 10 및 향후 규정 준수 정책에 대한 시스템 보안 설정 추가 <!--1704133 -->

방화벽과 Windows Defender 바이러스 백신을 반드시 사용하게 하는 것을 포함하여 Windows 10 규정 준수 설정이 추가될 예정입니다.

### <a name="including-and-excluding-app-assignment-based-on-groups-for-android-enterprise----1813081---"></a>Android Enterprise에 대한 그룹에 따라 앱 할당 포함 및 제외 <!-- 1813081 -->
Android Enterprise(이전의 Android for Work)는 앱을 할당하는 동안 그리고 할당 유형을 선택한 후 제외 기능을 지원합니다.


### <a name="related-sets-of-app-licenses-supported-in-intune----1864117---"></a>Intune에서 지원되는 관련 앱 라이선스 집합 <!-- 1864117 -->
Azure Portal의 Intune은 관련 앱 라이선스 집합을 UI에서 단일 앱 항목으로 지원할 예정입니다. 또한 비즈니스용 Microsoft 스토어에서 동기화되는 오프라인 라이선스 앱은 단일 앱 항목으로 통합되고, 개별 패키지의 배포 세부 정보는 단일 항목으로 마이그레이션됩니다. Azure Portal에서 관련 앱 라이선스 집합을 보려면 **모바일 앱** 블레이드에서 **앱 라이선스**를 선택합니다.

<!-- the following are present prior to 1802 -->

### <a name="new-option-for-user-authentication-for-apple-bulk-enrollment----747625---"></a>Apple 대량 등록을 위한 새로운 사용자 인증 옵션 <!-- 747625 -->
Intune은 다음 등록 방법에 대해 회사 포털 앱을 사용하여 장치를 인증하는 옵션을 제공합니다.

- Apple 장비 등록 프로그램
- Apple School Manager
- Apple Configurator 등록

회사 포털 옵션을 사용하면 이러한 등록 방법을 차단하지 않고 Azure Active Directory 다단계 인증을 적용할 수 있습니다.

회사 포털 옵션을 사용할 경우 Intune은 사용자 선호도 등록을 위한 iOS 설정 도우미의 사용자 인증을 건너뜁니다. 따라서 처음에는 장치가 사용자 없는 장치로 등록되므로 사용자 그룹의 구성 또는 정책을 받지 않습니다. 장치 그룹의 구성과 정책만 받습니다. 그러나 Intune이 장치에 회사 포털 앱을 자동으로 설치합니다. 회사 포털 앱을 시작하고 로그인하는 첫 번째 사용자가 Intune에서 해당 장치와 연결됩니다. 사용자는 이때 사용자 그룹의 구성과 정책을 받습니다. 사용자 연결을 변경하려면 다시 등록해야 합니다.

### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685---"></a>여러 Apple DEP/Apple School Manager 계정에 대한 Intune 지원 <!-- 747685 -->
Intune은 최대 100개의 다른 Apple DEP(장비 등록 프로그램) 또는 Apple School Manager 계정의 장치 등록을 지원합니다. 업로드된 각 토큰을 등록 프로필과 장치에 대해 별도로 관리할 수 있습니다. 업로드된 DEP/School Manager 토큰마다 다른 등록 프로필을 자동으로 할당할 수 있습니다. School Manager 토큰이 여러 개 업로드된 경우 한 번에 하나의 토큰만 Microsoft School Data Sync와 공유할 수 있습니다.

Graph를 통해 Apple DEP 또는 ASM을 관리하기 위한 베타 Graph API 및 게시된 스크립트는 마이그레이션 후 더 이상 작동하지 않습니다. 새 베타 Graph API가 개발 중이며 마이그레이션 후 릴리스될 예정입니다.

### <a name="select-device-categories-by-using-the-access-work-or-school-settings----1058963---"></a>회사 또는 학교 액세스 설정을 사용하여 장치 범주 선택 <!-- 1058963 -->
[장치 그룹 매핑](https://docs.microsoft.com/intune/device-group-mapping)을 사용하도록 설정한 경우, Windows 10의 사용자에게 **설정** > **계정** > **회사 또는 학교 액세스**의 **연결** 단추를 통해 등록한 후 또는 첫 실행 경험 중에 장치 범주를 선택하라는 메시지가 표시됩니다.

### <a name="targeting-compliance-policies-to-devices-in-device-groups---1307012---"></a>장치 그룹의 장치를 준수 정책의 대상으로 지정 <!--1307012 -->

사용자 그룹의 사용자를 준수 정책의 대상으로 지정할 수 있습니다. 장치 그룹의 장치를 준수 정책의 대상으로 지정할 수 있습니다.

### <a name="windows-information-protection-wip-encrypted-data-in-windows-search-results----1469193---"></a>Windows 검색 결과의 WIP(Windows Information Protection) 암호화된 데이터 <!-- 1469193 -->

WIP(Windows Information Protection) 정책의 새 설정을 사용하면 WIP 암호화된 데이터를 Windows 검색 결과에 포함할지 여부를 제어할 수 있습니다.

### <a name="remote-printing-over-a-secure-network----1709994----"></a>보안 네트워크를 통한 원격 인쇄 <!-- 1709994  -->
PrinterOn의 무선 모바일 인쇄 솔루션을 사용하면 사용자가 보안 네트워크를 통해 언제 어디서나 원격으로 인쇄할 수 있습니다. PrinterOn은 iOS 및 Android용 Intune 앱 SDK와 둘 다 통합됩니다. 관리 콘솔의 Intune **앱 보호 정책** 블레이드를 통해 이 앱을 앱 보호 정책의 대상으로 지정할 수 있습니다. 최종 사용자는 Intune 에코시스템에서 사용하기 위해 Play 스토어 또는 iTunes를 통해 'PrinterOn for Microsoft' 앱을 다운로드할 수 있습니다.



### <a name="microsoft-graph-api-for-intune---general-availability-----1833289---"></a>Intune용 Microsoft Graph API - 일반 공급 <!-- 1833289 -->
Microsoft Graph의 Intune API를 사용하면 Intune 서비스의 관리 작업을 자동화하기 위한 데이터와 메서드를 프로그래밍 방식으로 액세스할 수 있습니다.  이러한 API가 **일반 공급**되므로 고객, 파트너 및 개발자는 이 API를 활용하여 Intune 또는 Microsoft Graph를 통해 사용할 수 있는 기타 Microsoft 서비스가 필요하거나 관련이 있는 사내 또는 상용 솔루션과 통합할 수 있습니다.

<!-- the following are present prior to 1801 -->

### <a name="app-protection-policies-----679615---"></a>앱 보호 정책 <!-- 679615 -->
Intune 앱 보호 정책은 전체 테넌트의 모든 사용자에 대해 보호를 빠르게 사용할 수 있도록 전역 기본 정책을 만드는 기능을 제공합니다.

### <a name="new-ios-device-action------1244701---"></a>새로운 iOS 장치 작업 <!-- 1244701 -->
iOS 10.3 감독된 장치를 종료할 수 있습니다. 이 작업을 수행하면 최종 사용자에게 경고하지 않고 장치가 즉시 종료됩니다. **장치** 워크로드에서 장치를 선택하면 장치 속성에서 **시스템 종료(감독 모드인 경우에만)** 작업을 찾을 수 있습니다.

### <a name="intune-provides-the-account-move-operation-----1573558-1579830---"></a>Intune에서 계정 이동 작업 제공 <!-- 1573558, 1579830 -->
**계정 이동**은 ASU(Azure Scale Unit) 간에 테넌트를 마이그레이션합니다. **계정 이동**의 경우 이를 요청하기 위해 Intune 지원 팀에 전화를 거는 경우와 같이 고객이 시작하는 시나리오와 Microsoft가 백 엔드에서 서비스를 조정해야 하는 경우와 같이 Microsoft가 주도하는 시나리오에 둘 다 사용될 수 있습니다. **계정 이동** 중에 테넌트는 ROM(읽기 전용 모드)로 전환됩니다. ROM 기간에는 등록, 장치 이름 바꾸기, 준수 상태 업데이트와 같은 서비스 작업이 실패합니다.

변경 내용은 한 앱이 서로 다른 앱 의도로 여러 그룹에 할당된 경우의 혼란을 해결합니다.

11월 서비스 릴리스 전에 정보 근로자 포털 및 회사 포털에서 사용할 수 있는 앱을 갖길 원하는 경우 다음과 같은 두 가지 옵션이 있습니다.

1. 그룹에 대한 **해당 없음** 할당을 제거합니다.
2. **필수 및 사용 가능** 의도가 할당된 멤버가 포함되지 않은 새 그룹을 만들고 해당 그룹을 **해당 없음**으로 할당합니다.

자세한 내용은 [Microsoft intune을 사용하여 그룹에 앱을 할당하는 방법](apps-deploy.md)을 참조하세요.

> [!Note]
> 릴리스 후에는 Intune 클래식 콘솔에서 MDM(모바일 장치 관리) 앱 할당을 보거나 수정할 수 없습니다. 단, Azure 콘솔 또는 Intune Graph API를 사용하여 앱 할당을 만들 수 있습니다.

### <a name="configure-an-ios-app-pin----1586774---"></a>iOS 앱 PIN 구성 <!-- 1586774 -->
곧 사용자는 대상 iOS 앱에 대한 PIN이 필요하게 됩니다. Azure Portal을 통해 며칠 내에 PIN 요구 사항 및 만료 날짜를 구성할 수 있습니다. 필요한 경우 사용자는 iOS 앱에 대한 액세스를 얻기 전에 새 PIN을 설정 및 사용해야 합니다. Intune 앱 SDK와 함께 앱 보호가 설정된 iOS 앱만 이 기능을 지원합니다.

### <a name="user-experience-update-for-the-company-portal-app-for-ios---1412866--"></a>iOS용 회사 포털 앱의 사용자 환경 업데이트 <!--1412866-->

iOS용 회사 포털 앱에 대한 주요 사용자 환경 업데이트를 출시합니다. 이 업데이트는 사용성 및 접근성이 향상된 최신 모양과 느낌이 포함된 완전한 시각적 재설계를 특징으로 합니다. 현재 모든 iOS 회사 포털 기능이 유지됩니다.

사용자가 사용하고 피드백으로 제공할 수 있도록, Apple TestFlight 프로그램을 통해 iOS용 회사 포털 앱의 업데이트된 시험판 버전을 제공하고 있습니다. TestFlight를 사용하려면 https://aka.ms/intune_ios_cp_testflight에서 등록합니다. 

![새 ios 회사 포털 앱에 대한 티저(teaser) 이미지](./media/ios-cp-app-redesign-1801-teaser.png)

<!-- the following are present prior to 1711 -->

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Azure Active Directory 웹 사이트에는 Intune Managed Browser 앱이 필요하고 Managed Browser(공개 미리 보기)에 Single Sign-On을 지원할 수 있습니다.<!-- 710595 -->   
Azure AD(Azure Active Directory)를 사용하면 모바일 장치에서 웹 사이트에 대한 액세스를 Intune Managed Browser 앱으로 제한할 수 있습니다. Managed Browser에서 웹 사이트 데이터는 최종 사용자 개인 데이터와 별도로 안전하게 유지됩니다. 또한 Managed Browser는 Azure AD에서 보호하는 사이트에 Single Sign-On 기능을 지원합니다. Managed Browser에 로그인하거나 Intune에서 관리하는 다른 앱과 함께 장치에서 Managed Browser를 사용하면 사용자에게 자격 증명을 입력하지 않고도 Azure AD에서 보호되는 회사 사이트에 액세스할 수 있습니다. 이 기능은 OWA(Outlook Web Access) 및 SharePoint Online과 같은 사이트뿐만 아니라 Azure 앱 프록시를 통해 액세스되는 인트라넷 리소스와 같은 다른 회사 사이트에도 적용됩니다.

<!-- the following are present prior to 1709 -->
### <a name="intune-app-protection-and-citrix-mdx-development-tools----709185---"></a>Intune 앱 보호 및 Citrix MDX 개발 도구<!-- 709185 -->
Citrix XenMobile MDX와 Microsoft Intune의 조합으로 장치와 앱을 관리할 수 있습니다. 이 옵션을 사용하면 Citrix의 mVPN 기술을 사용하면서 Intune 앱 보호 정책으로 앱을 관리할 수 있습니다.

Intune 앱 래핑 도구와 iOS 및 Android용 Intune 앱 SDK를 포함하는 코드 리포지토리를 찾아 Citrix MDX mVPN 기술과 통합할 수 있습니다.

<!-- the following are present prior to 1711 -->

### <a name="redirecting-macos-users-to-the-new-company-portal-app---1380728--"></a>새 회사 포털 앱에 macOS 사용자 리디렉션 <!--1380728-->   
최종 사용자가 macOS 장치를 등록하기 위해 회사 포털 웹 사이트에 로그인하는 경우 프로세스를 완료하기 위해 macOS용 새 회사 포털 앱을 다운로드하도록 리디렉션됩니다. 이는 macOS 장치에서 OS X El Capitan 10.11 이상을 사용하는 경우에 발생합니다. 

<!-- the following are present prior to 1709 -->

### <a name="intune-managed-browser-support-for-ios-and-android----1374196---"></a>iOS 및 Android를 위한 Intune Managed Browser 지원 <!-- 1374196 -->
2017년 10월을 기준으로 Android 앱에서 Intune Managed Browser 앱은 Android 4.4 이상을 실행하는 장치만 지원합니다. iOS의 Intune Managed Browser 앱은 iOS 9.0 이상을 실행하는 장치만 지원합니다. Android 및 iOS 이전 버전에서도 계속 Managed Browser를 사용할 수는 있지만 새로운 버전의 앱을 설치할 수 없고 모든 기능을 액세스하지 못할 수 있습니다. 이러한 장치를 지원되는 운영 체제 버전으로 업데이트하는 것이 좋습니다.

### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>사용자가 등록이 허용된 최대 장치 수에 도달하면 표시되는 향상된 오류 메시지 <!-- 1270370 -->
일반적인 오류 메시지 대신 Android 장치를 사용하는 최종 사용자에게 “IT 관리자가 허용한 최대 장치 수를 등록했습니다. 등록된 장치를 제거하거나 IT 관리자에게 도움을 요청하세요.”라는 친숙하고 조치를 수행할 수 있는 오류 메시지가 표시됩니다.



## <a name="notices"></a>알림

이번에는 활성 알림이 없습니다.



### <a name="see-also"></a>참고 항목
최근 개발 작업에 대한 자세한 내용은 [Microsoft Intune의 새로운 기능](whats-new.md)을 참조하세요.


