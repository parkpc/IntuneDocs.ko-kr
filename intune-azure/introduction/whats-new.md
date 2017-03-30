---
title: "Microsoft Intune Preview의 새로운 기능"
titleSuffix: Intune Azure preview
description: "Intune Azure 미리 보기의 새로운 기능 알아보기"
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 03/17/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 671d862c8d9a98e02f33d96cf6ceba712e740dec
ms.openlocfilehash: 586bdab54ee60ba8d620857ab3506aa27622d17a
ms.lasthandoff: 03/17/2017

---

# <a name="whats-new-in-the-microsoft-intune-preview"></a>Microsoft Intune Preview의 새로운 기능

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

공개 미리 보기가 진행되고 더 많은 기능이 추가되면 여기에서 알려 드리겠습니다.

> [!Note]
> Azure Portal 미리 보기와 관련하여 이 페이지에 표시된 변경 사항을 공개합니다. 그러나 Intune 서비스의 업데이트 방법 때문에 변경 사항이 즉시 제공되지 않을 수 있습니다.  Intune 서비스의 몇 가지 구성 요소를 순차적으로 업데이트해야 새 포털 기능을 사용할 수 있습니다. 이번 달 말에 공개되는 관련 변경 사항을 확인해 보세요.

## <a name="march-2017"></a>2017년 3월

### <a name="support-for-ios-lost-mode---431695--"></a>iOS 분실 모드 지원 <!--431695-->

iOS 9.3 이상 장치에 대해 Intune은 **분실 모드**를 추가 지원합니다. 장치를 잠가 모든 사용을 방지할 수 있으며 장치 잠금 화면의 메시지 및 연락처 전화 번호를 표시할 수 있습니다.

최종 사용자는 관리자가 분실 모드를 사용하지 않도록 설정할 때까지 장치의 잠금을 해제할 수 없습니다. 분실 모드가 설정된 경우 Intune 콘솔에서 **장치 찾기** 작업을 사용하여 장치의 지리적 위치를 지도에 표시할 수 있습니다.

장치는 DEP를 통해 등록되고 감독 모드 상태인 회사 소유의 iOS 장치여야 합니다.

자세한 내용은 [Microsoft Intune 장치 관리란?](/intune-azure/manage-devices/what-is)을 참조하세요.

### <a name="improvements-to-device-actions-report---677150--"></a>장치 작업 보고서의 향상된 기능 <!--677150-->

성능 향상을 위해 장치 작업 보고서를 개선했습니다. 또한 아제 상태별로 보고서를 필터링 수 있습니다. 예를 들어 완료된 장치 동작만 표시하도록 보고서를 필터링할 수 있습니다.

### <a name="actions-for-non-compliance---730266--"></a>비준수에 대한 작업<!--730266-->

**비준수에 대한 작업**은 정책을 준수하지 않는 장치에 조치를 취할 수 있는 준수 정책의 새로운 기능입니다. 단일 또는 여러 작업을 지정할 수 있으며, 이러한 작업이 수행되어야 하는 기간을 지정할 수 있습니다. 예를 들어 장치가 메일을 통해 비준수 상태가 된 직후에 사용자에게 비준수 장치를 알리거나 조건부 액세스를 통해 3일 유예 기간이 지난 후 비준수 장치가 회사 리소스에 액세스하는 것을 못하도록 차단할 수 있습니다.

### <a name="custom-app-categories---748805--"></a>사용자 지정 앱 범주<!--748805-->

이제 Intune에 추가하는 앱의 범주를 만들고, 편집하고, 할당할 수 있습니다. 현재 범주는 영어로만 지정할 수 있습니다.
[Intune에 앱을 추가하는 방법](/intune-azure/manage-apps/add-apps)을 참조하세요.

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

2017년 1월 이후에 만든 Intune 계정은 Azure Preview 포털에서 장치 등록 워크로드를 사용하여 Apple 등록 시나리오에 직접 액세스할 수 있습니다. 이전에는 클래식 Intune 포털의 링크를 통해서만 Apple 등록 미리 보기에 액세스할 수 있었습니다. 2017년 1월 이전에 만든 Intune 계정은 일회성 마이그레이션을 수행해야 Azure에서 이러한 기능을 사용할 수 있습니다. 마이그레이션 일정은 아직 공지되지 않았지만 가능한 한 빠른 시일 내에 세부 정보가 제공될 예정입니다. 기존 계정에서 미리 보기에 액세스할 수 없는 경우 평가판 계정을 만들어 새로운 경험을 테스트해 보는 것이 좋습니다.


## <a name="february-2017"></a>2017 년 2월

### <a name="ability-to-restrict-mobile-device-enrollment---747600-795782--"></a>모바일 장치 등록을 제한하는 기능 <!--747600, 795782-->
Intune은 등록할 수 있는 모바일 장치 플랫폼을 제어하는 새로운 등록 제한을 추가합니다. Intune은 모바일 장치 플랫폼을 iOS, macOS, Android, Windows 및 Windows Mobile로 구분합니다.

* 모바일 장치 등록을 제한해도 PC 클라이언트 등록은 제한되지 않습니다.  
* iOS 및 Android에 한해, 개인 소유 장치의 등록을 차단하는 한 가지 추가 옵션이 있습니다.

Intune은 [이 문서](https://docs.microsoft.com/en-us/intune/deploy-use/manage-corporate-owned-devices)에 설명된 대로 IT 관리자가 회사 소유로 표시하기 위한 조치를 취하지 않은 한 모든 새 장치를 개인 소유 장치로 표시합니다.

### <a name="view-all-actions-on-managed-devices---677150--"></a>관리 되는 장치에 관한 모든 작업 보기<!--677150-->
새 __장치 작업__ 보고서에는 장치의 공장 재설정과 같은 원격 작업을 수행한 사람이 누구인지 표시되며, 추가로 작업의 상태도 표시됩니다. [장치 관리란?](https://docs.microsoft.com/intune-azure/manage-devices/what-is)을 참조하세요.

### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>관리되지 않은 장치에서 할당된 앱에 액세스 가능 <!--664691-->
회사 포털 웹 사이트 디자인 변경의 일환으로, iOS 및 Android 사용자가 자기에게 할당된 앱을 관리되지 않는 장치에 "등록 없이 사용 가능"으로 설치할 수 있습니다. 사용자는 Intune 자격 증명을 사용하여 회사 포털 웹 사이트에 로그인하고 자기에게 할당된 앱의 목록을 볼 수 있습니다. "등록 없이 사용 가능" 앱의 앱 패키지는 회사 포털 웹 사이트를 통해 다운로드할 수 있습니다. 설치하려면 등록이 필요한 앱은 사용자가 앱을 설치하려 할 때 등록하라는 메시지가 표시되므로 이 변경의 영향을 받지 않습니다.

### <a name="custom-app-categories---748805--"></a>사용자 지정 앱 범주<!--748805-->
이제 Intune에 추가하는 앱의 범주를 만들고, 편집하고, 할당할 수 있습니다. 현재 범주는 영어로만 지정할 수 있습니다.
[Intune에 앱을 추가하는 방법](/intune-azure/manage-apps/add-apps)을 참조하세요.

### <a name="display-device-categories---814654--"></a>장치 범주 표시 <!--814654-->
이제 장치 목록에서 장치 범주를 열로 표시할 수 있습니다. 장치 속성 블레이드의 속성 섹션에서 범주를 편집할 수도 있습니다. [Intune에 앱을 추가하는 방법](/intune-azure/manage-apps/add-apps)을 참조하세요.

### <a name="configure-windows-update-for-business-settings---776716--"></a>비즈니스용 Windows 업데이트 설정 구성 <!--776716-->

Windows as a Service는 Windows 10 업데이트를 제공하는 새로운 서비스입니다. Windows 10부터는 새로운 기능 업데이트나 품질 업데이트에 모든 이전 업데이트의 내용이 포함됩니다. 따라서 최신 업데이트를 설치하면 Windows 10 장치가 완전히 최신 상태가 됩니다. 이전 버전의 Windows와 달리, 이제는 일부 업데이트가 아니라 전체 업데이트를 설치해야 합니다.

비즈니스용 Windows 업데이트를 사용하면 장치 그룹의 개별 업데이트를 승인할 필요가 없도록 업데이트 관리 환경을 단순화할 수 있습니다. 업데이트 출시 전략을 구성하여 현재 환경의 위험을 관리할 수 있으며 Windows 업데이트를 통해 적시에 업데이트가 설치됩니다. Microsoft Intune에서는 장치에서 업데이트 설정을 구성하는 기능 및 업데이트 설치를 지연하는 기능을 제공합니다. Intune에서는 업데이트를 저장하지 않고 업데이트 정책 할당만 저장합니다. 장치는 업데이트를 위해 Windows 업데이트에 직접 액세스합니다. Intune을 사용하여 **Windows 10 업데이트 링**을 구성 및 관리합니다. 업데이트 링에는 Windows 10 업데이트 설치 시기와 방법을 구성하는 설정 그룹이 포함됩니다. 자세한 내용은 [비즈니스용 Windows 업데이트 설정 구성](/intune-azure/configure-devices/how-to-configure-windows-update-for-business)을 참조하세요.

## <a name="january-2017"></a>2017년 1월

### <a name="assign-line-of-business-apps-whether-or-not-devices-are-enrolled---748823--"></a>장치가 등록되었는지 여부와 상관없는 LOB(기간 업무) 앱 <!--748823-->
장치가 Intune에 등록되었는지 여부와 상관없이 이제 저장소에서 사용자에게 LOB(기간 업무) 및 앱을 할당할 수 있습니다. 사용자 장치가 Intune에 등록되지 않은 경우 회사 포털 앱 대신에 회사 포털 웹 사이트로 이동하여 설치합니다. [앱 관리란?](/intune-azure/manage-apps/what-is-app-management)을 참조하세요.

### <a name="resolve-issue-where-ios-devices-are-inactive-or-the-admin-console-cannot-communicate-with-them"></a>iOS 장치가 비활성 상태이거나, 관리 콘솔에서 통신할 수 없는 경우 문제 해결
사용자 장치에서 Intune과의 연결이 끊기는 경우 회사 리소스에 대한 액세스 권한을 다시 얻도록 새로운 문제 해결 단계를 제공할 수 있습니다. [장치가 비활성 상태이거나 관리 콘솔이 장치와 통신할 수 없음](/intune-azure/enroll-devices/troubleshoot-device-enrollment#devices-are-inactive-or-the-admin-console-cannot-communicate-with-them)을 참조하세요.

## <a name="december-2016-initial-release"></a>2016년 12월(최초 릴리스)

### <a name="telecom-expense-management-integration-in-public-preview-of-azure-portal--747605--"></a>Azure Portal의 공개 미리 보기에서 이동통신 지출 관리 통합<!--747605-->
이제 Azure Portal 내에서 타사 TEM(이동통신 지출 관리) 서비스와의 통합 미리 보기를 시작합니다. Intune을 사용하여 국내 및 로밍 데이터 사용량을 제한할 수 있습니다. 우선 [Saaswedo](http://www.saaswedo.com)와의 통합으로 시작합니다. 평가판 테넌트에 이 기능을 사용하려면 [Microsoft 지원에 문의](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune)하세요.

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
Azure Portal에서는 Apple DEP(장치 등록 프로그램) 장치 일련 번호에 대한 "기본" 회사 장치 등록 프로필을 지원하지 않습니다. 클래식 Intune 콘솔에서 사용할 수 있는 이 기능은 의도치 않게 할당된 프로필을 방지하기 위해 중단됩니다. Azure Portal에서는 Apple DEP 계정에서 동기화된 일련 번호에 초기에 회사 장치 등록 프로필이 할당되지 않습니다.

#### <a name="how-this-affects-you"></a>이 옵션이 영향을 주는 방식
Azure Portal에서는 일부 Apple 장치에서 기본 프로필 정책을 설정할 수 없습니다. 클래식 Intune 콘솔에서는 이 기능을 계속 지원합니다.

#### <a name="how-to-get-ready-for-this-change"></a>이 변경 내용에 대비하는 방법
Microsoft에서는 이 변경 내용이 영향을 주는 경우 지원 관리자에게 알릴 수 있도록 이 정보를 미리 제공하고 있습니다. 이는 2017년 상반기로 예정된 Azure Portal로의 이동과 일치합니다.

