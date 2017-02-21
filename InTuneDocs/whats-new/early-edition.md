---
title: "초기 버전 | Microsoft 문서"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 68c7a23dc8769330c14f74e6aebb07eeb188a991
ms.openlocfilehash: 4bc9a2799bcce035c6847b7b2884ee24160426da


---


# <a name="the-early-edition-for-microsoft-intune---february-2017"></a>Microsoft Intune 초기 버전 - 2017년 2월

**초기 버전**에서는 Microsoft Intune의 향후 릴리스에서 도입될 기능의 목록을 제공합니다. 이 정보는 NDA 하에 매우 제한적으로 제공되며, 변경될 수 있습니다. 여기 나열된 일부 기능은 마감일을 맞추지 못할 위험이 있으며 다음 릴리스까지 지연될 수 있습니다. 다른 기능은 고객용 준비 상태를 확인하기 위해, 파일럿(플라이팅) 테스트 중 입니다. 질문이나 궁금한 내용이 있으면 Intune/PM 담당자에게 연락하세요.

이 페이지는 정기적으로 업데이트됩니다. 추가 업데이트가 있는지 다시 확인하세요.

> [!Note]
> Intune에 대해 다음 변경 사항을 개발 중입니다. 최종적으로는 이 모든 기능이 하이브리드 고객 배포(Intune과 Configuration Manager )용으로 지원될 예정입니다. 새로운 하이브리드 기능에 대한 자세한 내용은 [hybrid What’s New page](https://docs.microsoft.com/en-us/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management)(하이브리드 새로운 기능 페이지)를 참조하세요.

## <a name="new-capabilities"></a>새로운 기능

### <a name="modernizing-the-company-portal-website---753980--"></a>회사 포털 웹 사이트 현대화 <!--753980-->
회사 포털 웹 사이트는 관리 장치가 없는 사용자를 대상으로 하는 앱을 지원합니다. 이 웹 사이트는 새로운 대비 색 구성표, 동적 일러스트레이션, 기술 지원팀 연락처 세부 정보 및 기존 관리 장치에 대한 정보를 포함하는 "햄버거 메뉴" ![이제 회사 포털 웹 사이트 왼쪽 상단에 추가된 햄버거 메뉴의 작은 이미지](./media/CP_hamburger_menu.png)를 사용하여 다른 Microsoft 제품 및 서비스에 맞춥니다. 방문 페이지는 추천 및 최근에 업데이트된 앱에 대한 슬라이드를 포함하여 사용자가 사용할 수 있는 앱을 강조하도록 재조정됩니다. [UI 업데이트 페이지](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui)에서 이전 및 이후 이미지를 찾을 수 있습니다.

### <a name="new-guided-experience-for-windows-10-company-portal---713927--"></a>Windows 10 회사 포털에 대한 새로운 단계별 환경 <!--713927-->
3월부터 Windows 10용 회사 포털에 식별되거나 등록되지 않은 장치에 대한 단계별 Intune 연습 환경이 포함됩니다. 새 환경에서는 사용자의 Windows 10 빌드에 맞게 사용자 지정된 단계별 지침을 제공합니다. 이를 통해 사용자는 AAD 등록(조건부 액세스 식별 기능에 필요) 및 MDM 등록(장치 관리 기능에 필요)을 수행할 수 있습니다. 단계별 환경은 회사 포털 홈에서 액세스할 수 있으며 선택 사항입니다. 사용자는 등록을 완료하지 않은 경우에도 앱을 계속 사용할 수 있지만 기능이 제한될 수 있습니다.

###

## <a name="notices"></a>알림

### <a name="group-migration-will-not-require-any-updates-to-groups-or-policies-for-ios-devices---898837--"></a>iOS 장치의 그룹 또는 정책에 대한 업데이트에는 그룹 마이그레이션이 필요 없음 <!--898837-->
회사 장치 등록 프로필에서 미리 할당된 모든 Intune 장치 그룹마다, Azure Active Directory 장치 그룹으로 마이그레이션하는 동안 회사 장치 등록 프로필 이름을 기반으로 AAD에 동적인 장치 그룹이 생성됩니다. 그러면 장치가 등록될 때 자동으로 그룹화되어 원래 Intune 그룹과 동일한 정책 및 앱을 받습니다.

테넌트가 그룹화 및 타기팅을 위한 마이그레이션 프로세스에 들어가고 나면, Intune은 회사 장치 등록 프로필을 통해 타기팅된 Intune 그룹에 맞는 동적 AAD 그룹을 자동으로 생성합니다. Intune 관리자가 타기팅된 Intune 그룹을 삭제해도 해당되는 동적 AAD 그룹은 삭제되지 않습니다. 그룹의 구성원과 동적 쿼리는 지워지지만, 그룹 자체는 IT 관리자가 AAD 포털을 통해 제거할 때까지 남습니다.

마찬가지로 IT 관리자가 회사 장치 등록 프로필을 통해 타기팅되는 Intune 그룹이 무엇인지 변경할 경우, Intune에서는 새 프로필 할당을 반영한 새 동적 그룹을 생성하지만 이전 할당에 대해 생성된 동적 그룹을 제거하지는 않습니다t.

### <a name="new-mdm-server-address-for-windows-devices---893007--"></a>Windows 장치의 새 MDM 서버 주소 <!--893007-->
Windows 및 Windows Phone 사용자가 MDM 서버 주소 입력 메시지가 표시되었을 때 __manage.microsoft.com__을 입력할 경우 장치 등록이 실패합니다. MDM 서버 주소가 __manage.microsoft.com__에서 __enrollment.manage.microsoft.com__으로 변경됩니다. 사용자에게 Windows 또는 Windows Phone 장치를 등록하는 동안 MDM 서버 주소를 입력하라는 메시지가 표시되면 __enrollment.manage.microsoft.com__을 사용하라고 알리세요. 이 업데이트에 따라 __EnterpriseEnrollment.contoso.com__을 __manage.microsoft.com__으로 리디렉션하는 DNS CNAME은 모두 __EnterpriseEnrollment.contoso.com__에서 __EnterpriseEnrollment-s.manage.microsoft.com__으로 리디렉션하는 DNS CNAME으로 바꿔야 합니다. 이 변경에 대한 자세한 내용을 보려면 [aka.ms/intuneenrollsvrchange](https://aka.ms/intuneenrollsvrchange)를 방문하세요.

### <a name="new-user-experience-for-the-company-portal-app-for-android---621622--"></a>Android용 회사 포털 앱의 새 사용자 환경 <!--621622-->
3월부터, Android용 회사 포털 앱이 [material design guidelines](https://material.io/guidelines/material-design/introduction.html)(재료 디자인 지침)에 따라 모양과 느낌이 더욱 세련되어집니다. 이러한 향상된 사용자 환경에는 다음이 포함됩니다.

* __색__: 탭 헤더에 사용자 지정 색상표에 따라 색을 표시할 수 있습니다.
* __인터페이스__: 앱 탭에서 추천 앱 및 모든 앱 단추가 업데이트되었습니다. 검색 단추는 이제 부동 작업 단추입니다.
* __탐색__: 모든 앱은 쉽게 탐색할 수 있도록 추천, 전체 및 범주 탭으로 구분된 뷰를 표시합니다.
* __서비스__: 내 장치 및 IT 담당자 탭 가독성을 개선했습니다.

[UI 업데이트 페이지](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui)에서 이전 및 이후 이미지를 찾을 수 있습니다.

### <a name="associate-multiple-management-tools-with-the-windows-store-for-business---926135--"></a>비즈니스용 Windows 스토어와 여러 관리 도구 연결<!--926135-->
둘 이상의 관리 도구를 사용하여 비즈니스용 Windows 스토어 앱을 배포하는 경우, 이전에는 그 중에 하나만 비즈니스용 Windows 스토어에 연결할 수 있었습니다. 이제 Intune 및 Configuration Manager와 같은 여러 관리 도구를 스토어에 연결할 수 있습니다. 자세한 내용은 [Microsoft Intune을 사용하여 비즈니스용 Windows 스토어에서 구입한 앱 관리](https://docs.microsoft.com/en-us/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune#associate-your-windows-store-for-business-account-with-intune)를 참조하세요.

## <a name="public-preview-of-the-new-intune-admin-experience-on-azure---736542--"></a>Azure의 새 Intune 관리 환경에 대한 공개 미리 보기<!--736542-->

2017년 초에 Microsoft에서는 전체 관리 환경을 Azure로 마이그레이션합니다. 이를 통해 Graph API를 사용하여 확장 가능한 최신 서비스 플랫폼에서 핵심 EMS 워크플로에 대한 강력한 통합 관리를 지원합니다.

새 평가판 테넌트에서는 이번 달에 Azure Portal에서 새 관리 환경의 공개 미리 보기를 표시하기 시작합니다. 미리 보기 상태에서는 기존 Intune 콘솔의 기능과 패리티가 반복적으로 제공됩니다.

Azure Portal의 관리 환경에서는 이미 발표된 새 그룹화 및 대상 지정 기능을 사용합니다. 따라서 기존 테넌트가 새 그룹화 환경으로 마이그레이션될 때 사용자도 마이그레이션되어 테넌트에 새 관리 환경의 미리 보기가 표시됩니다. 그 동안 테넌트가 마이그레이션될 때까지 새 기능을 테스트하거나 살펴보려는 경우 새 Intune 평가판 계정에 등록하거나 [새 설명서](https://docs.microsoft.com/en-us/intune-azure/introduction/what-is-microsoft-intune)를 살펴보세요.

테넌트 마이그레이션 일정에 대한 질문이 있으면 [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com)으로 마이그레이션 팀에 문의하세요.

### <a name="february-2017"></a>2017 년 2월

#### <a name="ability-to-restrict-mobile-device-enrollment---747600-795782--"></a>모바일 장치 등록을 제한하는 기능 <!--747600, 795782-->
Intune은 등록할 수 있는 모바일 장치 플랫폼을 제어하는 새로운 등록 제한을 추가합니다. Intune은 모바일 장치 플랫폼을 iOS, macOS, Android, Windows 및 Windows Mobile로 구분합니다.

* 모바일 장치 등록을 제한해도 PC 클라이언트 등록은 제한되지 않습니다.  
* iOS 및 Android에 한해, 개인 소유 장치의 등록을 차단하는 한 가지 추가 옵션이 있습니다.

Intune은 [이 문서](https://docs.microsoft.com/en-us/intune/deploy-use/manage-corporate-owned-devices)에 설명된 대로 IT 관리자가 회사 소유로 표시하기 위한 조치를 취하지 않은 한 모든 새 장치를 개인 소유 장치로 표시합니다.

#### <a name="view-all-actions-on-managed-devices---677150--"></a>관리 되는 장치에 관한 모든 작업 보기<!--677150-->
새 __장치 작업__ 보고서에는 장치의 공장 재설정과 같은 원격 작업을 수행한 사람이 누구인지 표시되며, 추가로 작업의 상태도 표시됩니다.

#### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>관리되지 않은 장치에서 할당된 앱에 액세스 가능 <!--664691-->
회사 포털 웹 사이트 디자인 변경의 일환으로, iOS 및 Android 사용자가 자기에게 할당된 앱을 관리되지 않는 장치에 "등록 없이 사용 가능"으로 설치할 수 있습니다. 사용자는 Intune 자격 증명을 사용하여 회사 포털 웹 사이트에 로그인하고 자기에게 할당된 앱의 목록을 볼 수 있습니다. "등록 없이 사용 가능" 앱의 앱 패키지는 회사 포털 웹 사이트를 통해 다운로드할 수 있습니다. 설치하려면 등록이 필요한 앱은 사용자가 앱을 설치하려 할 때 등록하라는 메시지가 표시되므로 이 변경의 영향을 받지 않습니다.

#### <a name="custom-app-categories---748805--"></a>사용자 지정 앱 범주<!--748805-->
이제 Intune에 추가하는 앱의 범주를 만들고, 편집하고, 할당할 수 있습니다. 현재 범주는 영어로만 지정할 수 있습니다.
[Intune에 앱을 추가하는 방법](/intune-azure/manage-apps/add-apps)을 참조하세요.

#### <a name="display-device-categories---814654--"></a>장치 범주 표시 <!--814654-->
이제 장치 목록에서 장치 범주를 열로 표시할 수 있습니다. 장치 속성 블레이드의 속성 섹션에서 범주를 편집할 수도 있습니다.

### <a name="january-2017"></a>2017년 1월

#### <a name="custom-app-categories---748805--"></a>사용자 지정 앱 범주<!--748805-->
이제 Intune에 추가하는 앱의 범주를 만들고, 편집하고, 할당할 수 있습니다. 현재 범주는 영어로만 지정할 수 있습니다.

#### <a name="assign-line-of-business-apps-whether-or-not-devices-are-enrolled---748803--"></a>장치가 등록되었는지 여부와 상관없는 LOB(기간 업무) 앱 <!--748803-->
장치가 Intune에 등록되었는지 여부와 상관없이 이제 저장소에서 사용자에게 LOB(기간 업무) 및 앱을 할당할 수 있습니다. 사용자 장치가 Intune에 등록되지 않은 경우 회사 포털 앱 대신에 회사 포털 웹 사이트로 이동하여 설치합니다.

### <a name="december-2016"></a>2016년 12월

#### <a name="telecom-expense-management-integration-in-public-preview-of-azure-portal--747605--"></a>Azure Portal의 공개 미리 보기에서 이동통신 지출 관리 통합<!--747605-->
이제 Azure Portal 내에서 타사 TEM(이동통신 지출 관리) 서비스와의 통합 미리 보기를 시작합니다. Intune을 사용하여 국내 및 로밍 데이터 사용량을 제한할 수 있습니다. 우선 [Saaswedo](http://www.saaswedo.com)와의 통합으로 시작합니다. 평가판 테넌트에 이 기능을 사용하려면 [Microsoft 지원에 문의](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune)하세요.

### <a name="see-also"></a>참고 항목
최근 개발 작업에 대한 자세한 내용은 [Microsoft Intune의 새로운 기능](whats-new-in-microsoft-intune.md)을 참조하세요.



<!--HONumber=Feb17_HO2-->


