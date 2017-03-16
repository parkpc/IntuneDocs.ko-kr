---
title: "새로운 기능 | Microsoft 문서"
description: "이번 달의 새로운 소식과 Microsoft Intune의 이전 릴리스 확인"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 03/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: a9336e3d230de962d2623dd627e45c6e9262a822
ms.openlocfilehash: cfe4a0bb802956278387ac2a39d5316482e09332
ms.lasthandoff: 03/01/2017


---
# <a name="whats-new-in-microsoft-intune---february-2017"></a>Microsoft Intune의 새로운 기능 - 2017년 2월
이번 Microsoft Intune 릴리스의 새로운 기능에 대해 알아봅니다. 이전 릴리스에 대한 정보뿐만 아니라 계획을 수립해야 하는 예정된 변경에 대해서도 알아볼 수 있습니다.

> [!Note]
> 최종적으로는 이 모든 기능이 하이브리드 고객 배포(Intune과 Configuration Manager )용으로 지원될 예정입니다. 새로운 하이브리드 기능에 대한 자세한 내용은 [hybrid What’s New page](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management)(하이브리드 새로운 기능 페이지)를 참조하세요.

## <a name="new-capabilities"></a>새로운 기능

### <a name="modernizing-the-company-portal-website---753980--"></a>회사 포털 웹 사이트 현대화 <!--753980-->
회사 포털 웹 사이트는 관리 장치가 없는 사용자를 대상으로 하는 앱을 지원합니다. 이 웹 사이트는 새로운 대비 색 구성표, 동적 일러스트레이션, 기술 지원팀 연락처 세부 정보 및 기존 관리 장치에 대한 정보를 포함하는 "햄버거 메뉴" ![이제 회사 포털 웹 사이트 왼쪽 상단에 추가된 햄버거 메뉴의 작은 이미지](./media/CP_hamburger_menu.png)를 사용하여 다른 Microsoft 제품 및 서비스에 맞춥니다. 방문 페이지는 추천 및 최근에 업데이트된 앱에 대한 슬라이드를 포함하여 사용자가 사용할 수 있는 앱을 강조하도록 재조정됩니다. [UI 업데이트 페이지](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui)에서 이전 및 이후 이미지를 찾을 수 있습니다.

### <a name="new-guided-experience-for-windows-10-company-portal---713927--"></a>Windows 10 회사 포털에 대한 새로운 단계별 환경 <!--713927-->
3월부터 Windows 10용 회사 포털에 식별되거나 등록되지 않은 장치에 대한 단계별 Intune 연습 환경이 포함됩니다. 새 환경에서는 사용자의 Windows 10 빌드에 맞게 사용자 지정된 단계별 지침을 제공합니다. 이를 통해 사용자는 AAD 등록(조건부 액세스 식별 기능에 필요) 및 MDM 등록(장치 관리 기능에 필요)을 수행할 수 있습니다. 단계별 환경은 회사 포털 홈에서 액세스할 수 있으며 선택 사항입니다. 사용자는 등록을 완료하지 않은 경우에도 앱을 계속 사용할 수 있지만 기능이 제한될 수 있습니다.

## <a name="notices"></a>알림

### <a name="group-migration-will-not-require-any-updates-to-groups-or-policies-for-ios-devices---898837--"></a>iOS 장치의 그룹 또는 정책에 대한 업데이트에는 그룹 마이그레이션이 필요 없음 <!--898837-->
회사 장치 등록 프로필에서 미리 할당된 모든 Intune 장치 그룹마다, Azure Active Directory 장치 그룹으로 마이그레이션하는 동안 회사 장치 등록 프로필 이름을 기반으로 AAD에 동적인 장치 그룹이 생성됩니다. 그러면 장치가 등록될 때 자동으로 그룹화되어 원래 Intune 그룹과 동일한 정책 및 앱을 받습니다.

테넌트가 그룹화 및 타기팅을 위한 마이그레이션 프로세스에 들어가고 나면, Intune은 회사 장치 등록 프로필을 통해 타기팅된 Intune 그룹에 맞는 동적 AAD 그룹을 자동으로 생성합니다. Intune 관리자가 타기팅된 Intune 그룹을 삭제해도 해당되는 동적 AAD 그룹은 삭제되지 않습니다. 그룹의 구성원과 동적 쿼리는 지워지지만, 그룹 자체는 IT 관리자가 AAD 포털을 통해 제거할 때까지 남습니다.

마찬가지로 IT 관리자가 회사 장치 등록 프로필을 통해 타기팅되는 Intune 그룹이 무엇인지 변경할 경우, Intune에서는 새 프로필 할당을 반영한 새 동적 그룹을 생성하지만 이전 할당에 대해 생성된 동적 그룹을 제거하지는 않습니다t.

### <a name="defaulting-to-managing-windows-desktop-devices-through-windows-settings---663050--"></a>Windows 설정을 통해 Windows 데스크톱 장치 관리를 기본값으로 설정<!--663050-->
Windows 10 데스크톱을 등록하는 기본 동작이 바뀌고 있습니다. 새 등록은 PC 에이전트를 통해서가 아니라 일반적인 MDM 에이전트 등록 흐름을 따릅니다. 회사 포털 웹 사이트는 Windows 10 데스크톱 사용자에게 모바일 장치로 Windows 10 데스크톱 컴퓨터를 추가하는 과정을 안내하는 등록 지침을 제공합니다. 현재 등록된 PC에는 영향을 주지 않으며, [원하는 경우](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune) 조직에서 PC 에이전트를 사용하여 Windows 10 데스크톱을 계속 관리할 수 합니다.

### <a name="improving-mobile-app-management-support-for-selective-wipe---581242--"></a>선택적 초기화에 대한 모바일 앱 관리 지원 향상 <!--581242-->
"앱 데이터를 초기화하기 전의 오프라인 간격" 정책으로 인해 데이터가 자동으로 제거되는 경우 회사 또는 학교 데이터에 다시 액세스하는 방법에 대한 추가 지침이 최종 사용자에게 제공됩니다.<!--, or the removal of the Intune Company Portal on Android.-->

### <a name="company-portal-for-ios-links-open-inside-the-app---665954--"></a>iOS용 회사 포털 링크가 앱 내에서 열림<!--665954-->
설명서 및 앱에 대한 링크를 포함하여 iOS용 회사 포털 앱 내의 링크는 Safari의 앱 내 보기를 사용하여 회사 포털 앱에서 직접 열립니다. 이 업데이트는&1;월에 서비스 업데이트에서 별도로 제공됩니다.

### <a name="new-mdm-server-address-for-windows-devices---893007--"></a>Windows 장치의 새 MDM 서버 주소 <!--893007-->
Windows 및 Windows Phone 사용자가 MDM 서버 주소 입력 메시지가 표시되었을 때 __manage.microsoft.com__을 입력할 경우 장치 등록이 실패합니다. MDM 서버 주소가 __manage.microsoft.com__에서 __enrollment.manage.microsoft.com__으로 변경됩니다. 사용자에게 Windows 또는 Windows Phone 장치를 등록하는 동안 MDM 서버 주소를 입력하라는 메시지가 표시되면 __enrollment.manage.microsoft.com__을 사용하라고 알리세요. CNAME 설정을 변경할 필요는 없습니다. 이 변경에 대한 자세한 내용을 보려면 [aka.ms/intuneenrollsvrchange](https://aka.ms/intuneenrollsvrchange)를 방문하세요.

### <a name="new-user-experience-for-the-company-portal-app-for-android---621622--"></a>Android용 회사 포털 앱의 새 사용자 환경 <!--621622-->
3월부터, Android용 회사 포털 앱이 [material design guidelines](https://material.io/guidelines/material-design/introduction.html)(재료 디자인 지침)에 따라 모양과 느낌이 더욱 세련되어집니다. 이러한 향상된 사용자 환경에는 다음이 포함됩니다.

* __색__: 탭 헤더에 사용자 지정 색상표에 따라 색을 표시할 수 있습니다.
* __인터페이스__: 앱 탭에서 추천 앱 및 모든 앱 단추가 업데이트되었습니다. 검색 단추는 이제 부동 작업 단추입니다.
* __탐색__: 모든 앱은 쉽게 탐색할 수 있도록 추천, 전체 및 범주 탭으로 구분된 뷰를 표시합니다.
* __서비스__: 내 장치 및 IT 담당자 탭 가독성을 개선했습니다.

[UI 업데이트 페이지](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui)에서 이전 및 이후 이미지를 찾을 수 있습니다.

### <a name="associate-multiple-management-tools-with-the-windows-store-for-business---926135--"></a>비즈니스용 Windows 스토어와 여러 관리 도구 연결<!--926135-->
둘 이상의 관리 도구를 사용하여 비즈니스용 Windows 스토어 앱을 배포하는 경우, 이전에는 그 중에 하나만 비즈니스용 Windows 스토어에 연결할 수 있었습니다. 이제 Intune 및 Configuration Manager와 같은 여러 관리 도구를 스토어에 연결할 수 있습니다. 자세한 내용은 [Microsoft Intune을 사용하여 비즈니스용 Windows 스토어에서 구입한 앱 관리](https://docs.microsoft.com/en-us/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune#associate-your-windows-store-for-business-account-with-intune)를 참조하세요.

## <a name="whats-new-in-the-public-preview-of-the-intune-admin-experience-on-azure---736542--"></a>Azure의 Intune 관리 환경 공개 미리 보기의 새로운 기능<!--736542-->

2017년 초에 Microsoft에서는 전체 관리 환경을 Azure로 마이그레이션합니다. 이를 통해 Graph API를 사용하여 확장 가능한 최신 서비스 플랫폼에서 핵심 EMS 워크플로에 대한 강력한 통합 관리를 지원합니다.

새 평가판 테넌트에서는 이번 달에 Azure Portal에서 새 관리 환경의 공개 미리 보기를 표시하기 시작합니다. 미리 보기 상태에서는 기존 Intune 콘솔의 기능과 패리티가 반복적으로 제공됩니다.

Azure Portal의 관리 환경에서는 이미 발표된 새 그룹화 및 대상 지정 기능을 사용합니다. 따라서 기존 테넌트가 새 그룹화 환경으로 마이그레이션될 때 사용자도 마이그레이션되어 테넌트에 새 관리 환경의 미리 보기가 표시됩니다. 그 동안 테넌트가 마이그레이션될 때까지 새 기능을 테스트하거나 살펴보려는 경우 새 Intune 평가판 계정에 등록하거나 [새 설명서](https://docs.microsoft.com/intune-azure/introduction/whats-new)를 살펴보세요.

테넌트 마이그레이션 일정에 대한 질문이 있으면 [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com)으로 마이그레이션 팀에 문의하세요.

Azure의 Intune 미리 보기에 대한 새로운 기능은 [여기](https://docs.microsoft.com/intune-azure/introduction/whats-new)에서 찾을 수 있습니다.

## <a name="whats-coming"></a>향후 예정 사항

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple의 Application Transport Security 업데이트 요구 <!--748318-->

Apple에서는 2017년 봄부터 ATS(Application Transport Security)에 대한 특정 요구 사항을 적용할 것이라고 발표했습니다. ATS는 HTTPS를 통한 모든 앱 통신에서 보다 엄격한 보안을 적용하는 데 사용됩니다. 이 변경 사항은 iOS 회사 포털 앱을 사용하는 Intune 고객에게 영향을 줍니다. 자세한 내용은 [Intune 지원 블로그](https://aka.ms/compportalats)를 참조하세요. 

### <a name="see-also"></a>참고 항목
* [Microsoft Intune 블로그](http://go.microsoft.com/fwlink/?LinkID=273882)
* [클라우드 플랫폼 로드맵](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Azure Tools의 새로운 기능](https://docs.microsoft.com/intune-azure/introduction/whats-new)
* [What's new in the Company Portal UI](https://docs.microsoft.com/intune/whats-new/whats-new-in-company-portal-ui)(회사 포털 UI의 새로운 기능)
* [새로운 기능 - 아카이브](whats-new-archive.md)

