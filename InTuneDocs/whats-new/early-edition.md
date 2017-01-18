---
title: "초기 버전 | Microsoft 문서"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 12/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 18d47678b0fbdbd98502f2d3b469b202b567b2e7
ms.openlocfilehash: 3c7edc236878232c6f4c0ae993733c967946e765


---

# <a name="the-early-edition-for-microsoft-intune---january"></a>Microsoft Intune 초기 버전 - 1월

**초기 버전**에서는 Microsoft Intune의 향후 릴리스에서 도입될 기능의 목록을 제공합니다. 이 정보는 NDA 하에 매우 제한적으로 제공되며, 변경될 수 있습니다. 여기 나열된 일부 기능은 마감일을 맞추지 못할 위험이 있으며 다음 릴리스까지 지연될 수 있습니다. 다른 기능은 고객용 준비 상태를 확인하기 위해, 파일럿(플라이팅) 테스트 중 입니다. 질문이나 궁금한 내용이 있으면 Intune/PM 담당자에게 연락하세요.

이 페이지는 정기적으로 업데이트됩니다. 추가 업데이트가 있는지 다시 확인하세요.

> [!Note]
> Intune에 대해 다음 변경 사항을 개발 중입니다. 최종적으로는 이 모든 기능이 하이브리드 고객 배포(Intune과 Configuration Manager )용으로 지원될 예정입니다. 새로운 하이브리드 기능에 대한 자세한 내용은 [hybrid What’s New page](https://docs.microsoft.com/en-us/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management)(하이브리드 새로운 기능 페이지)를 참조하세요.

## <a name="new-capabilities"></a>새로운 기능

### <a name="actions-for-non-compliance---730266--"></a>비준수에 대한 작업<!--730266-->
_비준수에 대한 작업_은 정책을 준수하지 않는 장치에 조치를 취할 수 있는 준수 정책의 새로운 기능입니다. 단일 또는 여러 작업을 지정할 수 있으며, 이러한 작업이 수행되어야 하는 기간을 지정할 수 있습니다. 예를 들어 장치가 메일을 통해 비준수 상태가 된 직후에 사용자에게 비준수 장치를 알리거나 조건부 액세스를 통해 3일 유예 기간이 지난 후 비준수 장치가 회사 리소스에 액세스하는 것을 못하도록 차단할 수 있습니다.

### <a name="in-console-reports-for-mam-without-enrollment---677961--"></a>등록과 상관없는 MAM에 대한 콘솔 내 보고서<!--677961-->
등록된 장치 및 등록되지 않은 장치 모두에 대한 새 앱 보호 보고서가 추가되었습니다. [intune을 사용하여 모바일 앱 관리 정책을 모니터링할 수 있는 방법은 여기](https://docs.microsoft.com/en-us/intune/deploy-use/monitor-mobile-app-management-policies-with-microsoft-intune)에서 확인하세요.

### <a name="conditional-access-for-mam-with-sharepoint-online---679339--"></a>SharePoint Online에서 MAM에 대한 조건부 액세스 <!--679339-->
Intune MAM(모바일 앱 관리) 정책에서 지원되지 않는 앱이 SharePoint Online에 액세스하지 못하도록 할 수 있습니다.  Intune 모바일 앱 관리는 Azure Portal에서 시작할 수 있습니다. SharePoint Online에 대한 옵션을 포함하는 __설정__ 블레이드의 __조건부 액세스__ 섹션을 찾아보세요. 이 기능은 나머지 서비스 릴리스와 별도로 제공됩니다. <!--Find out more about this new feature [here](https://docs.microsoft.com/intune/deploy-use/mam-ca-for-sharepoint-online).-->

### <a name="android-711-support---694397--"></a>Android 7.1.1 지원<!--694397-->
Intune은 이제 Android 7.1.1을 완벽하게 지원하고 관리합니다.

## <a name="notices"></a>알림

### <a name="defaulting-to-managing-windows-desktop-devices-through-windows-settings---663050--"></a>Windows 설정을 통해 Windows 데스크톱 장치 관리를 기본값으로 설정<!--663050-->
Windows 10 데스크톱을 등록하는 기본 동작이 바뀌고 있습니다. 새 등록은 PC 에이전트를 통해서가 아니라 일반적인 MDM 에이전트 등록 흐름을 따릅니다.

회사 포털 웹 사이트는 Windows 10 데스크톱 사용자에게 모바일 장치로 Windows 10 데스크톱 컴퓨터를 추가하는 과정을 안내하는 등록 지침을 제공합니다. 현재 등록된 PC에는 영향을 주지 않으며, [원하는 경우](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune) 조직에서 PC 에이전트를 사용하여 Windows 10 데스크톱을 계속 관리할 수 합니다.

### <a name="company-portal-for-ios-links-open-inside-the-app---665954--"></a>iOS용 회사 포털 링크가 앱 내에서 열림<!--665954-->
설명서 및 앱에 대한 링크를 포함하여 iOS용 회사 포털 앱 내의 링크는 Safari의 앱 내 보기를 사용하여 회사 포털 앱에서 직접 열립니다. 이 업데이트는 1월에 서비스 업데이트에서 별도로 제공됩니다.

### <a name="improving-mobile-app-management-support-for-selective-wipe---581242--"></a>선택적 초기화에 대한 모바일 앱 관리 지원 향상 <!--581242-->
"앱 데이터를 초기화하기 전의 오프라인 간격" 정책으로 인해 데이터가 자동으로 제거되는 경우 회사 또는 학교 데이터에 다시 액세스하는 방법에 대한 추가 지침이 최종 사용자에게 제공됩니다.<!--, or the removal of the Intune Company Portal on Android.-->

### <a name="new-documentation-for-app-protection-policies---583398--"></a>앱 보호 정책에 대한 새 설명서<!--583398-->
iOS 및 Android 앱에서 Intune 앱 래핑 도구 또는 Intune 앱 SDK를 사용하여 앱 보호 정책(MAM 정책이라고도 함)을 사용하도록 설정하려는 관리자 및 앱 개발자를 위한 설명서를 업데이트했습니다.

다음 문서가 업데이트되었습니다.

* [Microsoft Intune으로 모바일 응용 프로그램 관리용 앱을 준비하는 방법 결정](https://docs.microsoft.com/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune)
* [Intune 앱 래핑 도구를 사용하여 모바일 응용 프로그램 관리를 위해 iOS 앱 준비](https://docs.microsoft.com/intune/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)
* [Microsoft Intune 앱 SDK 시작](https://docs.microsoft.com/intune/develop/intune-app-sdk-get-started)
* [iOS용 Intune 앱 SDK 개발자 가이드](https://docs.microsoft.com/intune/develop/intune-app-sdk-ios)

다음 문서가 문서 라이브러리에 새로 추가되었습니다.

* [Intune 앱 SDK Cordova 플러그 인](https://docs.microsoft.com/intune/develop/intune-app-sdk-cordova)
* [Intune 앱 SDK Xamarin 구성 요소](https://docs.microsoft.com/intune/develop/intune-app-sdk-xamarin)

### <a name="progress-bar-when-launching-the-company-portal-on-ios---665978--"></a>iOS에서 회사 포털을 시작할 경우의 진행률 표시줄 <!--665978-->
iOS용 회사 포털은 수행되는 로드 프로세스에 대한 정보를 사용자에게 제공하는 시작 화면의 진행률 표시줄을 도입하기로 했습니다. 진행률 표시줄이 단계적으로 회전자를 바꿀 예정입니다. 즉, 일부 사용자에게는 새로운 진행률 표시줄이 표시되지만 다른 사용자에게는 계속 회전자가 표시됩니다.

## <a name="public-preview-of-the-new-intune-admin-experience-on-azure---736542--"></a>Azure의 새 Intune 관리 환경에 대한 공개 미리 보기<!--736542-->

2017년 초에 Microsoft에서는 전체 관리 환경을 Azure로 마이그레이션합니다. 이를 통해 Graph API를 사용하여 확장 가능한 최신 서비스 플랫폼에서 핵심 EMS 워크플로에 대한 강력한 통합 관리를 지원합니다.

새 평가판 테넌트에서는 이번 달에 Azure Portal에서 새 관리 환경의 공개 미리 보기를 표시하기 시작합니다. 미리 보기 상태에서는 기존 Intune 콘솔의 기능과 패리티가 반복적으로 제공됩니다.

Azure Portal의 관리 환경에서는 이미 발표된 새 그룹화 및 대상 지정 기능을 사용합니다. 따라서 기존 테넌트가 새 그룹화 환경으로 마이그레이션될 때 사용자도 마이그레이션되어 테넌트에 새 관리 환경의 미리 보기가 표시됩니다. 그 동안 테넌트가 마이그레이션될 때까지 새 기능을 테스트하거나 살펴보려는 경우 새 Intune 평가판 계정에 등록하거나 [새 설명서](https://docs.microsoft.com/en-us/intune-azure/introduction/what-is-microsoft-intune)를 살펴보세요.

테넌트 마이그레이션 일정에 대한 질문이 있으면 [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com)으로 마이그레이션 팀에 문의하세요.

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



<!--HONumber=Dec16_HO4-->


