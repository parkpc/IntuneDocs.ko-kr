---
title: "Microsoft Intune Preview의 새로운 기능"
titleSuffix: Intune Azure preview
description: "Intune Azure 미리 보기의 새로운 기능 알아보기"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/15/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: ffbc91edbdec4abbb5c3c9e28c3b44df03117492
ms.lasthandoff: 02/18/2017

---

# <a name="whats-new-in-the-microsoft-intune-preview"></a>Microsoft Intune Preview의 새로운 기능

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

공개 미리 보기가 진행되고 더 많은 기능이 추가되면 여기에서 알려 드리겠습니다.

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

