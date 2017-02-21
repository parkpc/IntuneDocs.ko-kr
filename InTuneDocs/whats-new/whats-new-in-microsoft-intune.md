---
title: "새로운 기능 | Microsoft 문서"
description: "이번 달의 새로운 소식과 Microsoft Intune의 이전 릴리스 확인"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: cacampbell
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 053cf0a1b5d06496397b36cbd1a7ebdce420fed3
ms.openlocfilehash: 5158d58c32066ea720335a878fef87451542c195


---
# <a name="whats-new-in-microsoft-intune---january-2017"></a>Microsoft Intune의 새로운 기능 - 2017년 1월
이번 Microsoft Intune 릴리스의 새로운 기능에 대해 알아봅니다. 이전 릴리스에 대한 정보뿐만 아니라 계획을 수립해야 하는 예정된 변경에 대해서도 알아볼 수 있습니다.

> [!Note]
> 최종적으로는 이 모든 기능이 하이브리드 고객 배포(Intune과 Configuration Manager )용으로 지원될 예정입니다. 새로운 하이브리드 기능에 대한 자세한 내용은 [hybrid What’s New page](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management)(하이브리드 새로운 기능 페이지)를 참조하세요.

## <a name="new-capabilities"></a>새로운 기능

<!--### Actions for non-compliance <!--730266
_Actions for non-compliance_ is a new feature of compliance policies that lets you take action on devices that are out of compliance. You can specify single or multiple actions and specify the time period at which those actions must occur. For example, you can notify users of non-compliant devices immediately after the devices become non-compliant through email, or you can block non-compliant devices from accessing corporate resources after a 3-day grace period via Conditional Access.-->

### <a name="in-console-reports-for-mam-without-enrollment---677961--"></a>등록과 상관없는 MAM에 대한 콘솔 내 보고서<!--677961-->
등록된 장치 및 등록되지 않은 장치 모두에 대한 새 앱 보호 보고서가 추가되었습니다. [intune을 사용하여 모바일 앱 관리 정책을 모니터링할 수 있는 방법은 여기](https://docs.microsoft.com/intune/deploy-use/monitor-mobile-app-management-policies-with-microsoft-intune)에서 확인하세요.

<!--### Conditional access for MAM with SharePoint Online <!--679339
You can block apps that are not supported by Intune mobile app management (MAM) policies from accessing SharePoint Online.  You can get started using Intune mobile app management in the Azure portal. Look for the __Conditional Access__ section in the __Settings__ blade which will include the option for SharePoint Online. This feature will ship separately from the rest of the service release. <!--Find out more about this new feature [here](https://docs.microsoft.com/intune/deploy-use/mam-ca-for-sharepoint-online).-->

### <a name="android-711-support---694397--"></a>Android 7.1.1 지원<!--694397-->
Intune은 이제 Android 7.1.1을 완벽하게 지원하고 관리합니다.

### <a name="resolve-issue-where-ios-devices-are-inactive-or-the-admin-console-cannot-communicate-with-them---unknown--"></a>iOS 장치가 비활성 상태이거나, 관리 콘솔에서 통신할 수 없는 경우 문제 해결 <!--unknown-->
사용자 장치에서 Intune과의 연결이 끊기는 경우 회사 리소스에 대한 액세스 권한을 다시 얻도록 새로운 문제 해결 단계를 제공할 수 있습니다. [장치가 비활성 상태이거나, 관리 콘솔에서 통신할 수 없음](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#devices-are-inactive-or-the-admin-console-cannot-communicate-with-them)을 참조하세요.

## <a name="notices"></a>알림

### <a name="defaulting-to-managing-windows-desktop-devices-through-windows-settings---663050--"></a>Windows 설정을 통해 Windows 데스크톱 장치 관리를 기본값으로 설정<!--663050-->
Windows 10 데스크톱을 등록하는 기본 동작이 바뀌고 있습니다. 새 등록은 PC 에이전트를 통해서가 아니라 일반적인 MDM 에이전트 등록 흐름을 따릅니다.

회사 포털 웹 사이트는 Windows 10 데스크톱 사용자에게 모바일 장치로 Windows 10 데스크톱 컴퓨터를 추가하는 과정을 안내하는 등록 지침을 제공합니다. 현재 등록된 PC에는 영향을 주지 않으며, [원하는 경우](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune) 조직에서 PC 에이전트를 사용하여 Windows 10 데스크톱을 계속 관리할 수 합니다.

<!--### Company Portal for iOS links open inside the app <!--665954
Links inside of the Company Portal app for iOS, including those to documentation and apps, will open directly in the Company Portal app using an in-app view of Safari. This update will ship separately from the service update in January.-->

### <a name="improving-mobile-app-management-support-for-selective-wipe---581242--"></a>선택적 초기화에 대한 모바일 앱 관리 지원 향상 <!--581242-->
"앱 데이터를 초기화하기 전의 오프라인 간격" 정책으로 인해 데이터가 자동으로 제거되는 경우 회사 또는 학교 데이터에 다시 액세스하는 방법에 대한 추가 지침이 최종 사용자에게 제공됩니다.<!--, or the removal of the Intune Company Portal on Android.-->

### <a name="company-portal-for-ios-links-open-inside-the-app---665954--"></a>iOS용 회사 포털 링크가 앱 내에서 열림<!--665954-->
설명서 및 앱에 대한 링크를 포함하여 iOS용 회사 포털 앱 내의 링크는 Safari의 앱 내 보기를 사용하여 회사 포털 앱에서 직접 열립니다. 이 업데이트는&1;월에 서비스 업데이트에서 별도로 제공됩니다.

### <a name="modernizing-the-company-portal-website---753980--"></a>회사 포털 웹 사이트 현대화 <!--753980-->
2월부터 회사 포털 웹 사이트는 관리 장치가 없는 사용자를 대상으로 하는 앱을 지원합니다. 이 웹 사이트는 새로운 대비 색 구성표, 동적 일러스트레이션, 기술 지원팀 연락처 세부 정보 및 기존 관리 장치에 대한 정보를 포함하는 "햄버거 메뉴" ![회사 포털 웹 사이트 햄버거 메뉴](./media/CP_hamburger_menu.png)를 사용하여 다른 Microsoft 제품 및 서비스에 맞춥니다. 방문 페이지는 추천 및 최근에 업데이트된 앱에 대한 슬라이드를 포함하여 사용자가 사용할 수 있는 앱을 강조하도록 재조정됩니다. [Intune 앱 UI의 새로운 기능](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui#January_2017) 페이지에서 사용 가능한 이전 및 이후 이미지를 찾을 수 있습니다.

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

<!--### Progress bar when launching the Company Portal on iOS <!--665978
The Company Portal for iOS is introducing a progress bar on the launch screen to provide the user with information about the loading processes that occur. There will be a phased rollout of the progress bar to replace the spinner. This means that some of your users will see the new progress bar while others will continue to see the spinner.-->

### <a name="progress-bar-when-launching-the-company-portal-on-ios---665978--"></a>iOS에서 회사 포털을 시작할 경우의 진행률 표시줄 <!--665978-->
iOS용 회사 포털은 수행되는 로드 프로세스에 대한 정보를 사용자에게 제공하는 시작 화면의 진행률 표시줄을 도입하기로 했습니다. 진행률 표시줄이 단계적으로 회전자를 바꿀 예정입니다. 즉, 일부 사용자에게는 새로운 진행률 표시줄이 표시되지만 다른 사용자에게는 계속 회전자가 표시됩니다.

## <a name="whats-new-in-the-public-preview-of-the-intune-admin-experience-on-azure---736542--"></a>Azure의 Intune 관리 환경 공개 미리 보기의 새로운 기능<!--736542-->

2017년 초에 Microsoft에서는 전체 관리 환경을 Azure로 마이그레이션합니다. 이를 통해 Graph API를 사용하여 확장 가능한 최신 서비스 플랫폼에서 핵심 EMS 워크플로에 대한 강력한 통합 관리를 지원합니다.

새 평가판 테넌트에서는 이번 달에 Azure Portal에서 새 관리 환경의 공개 미리 보기를 표시하기 시작합니다. 미리 보기 상태에서는 기존 Intune 콘솔의 기능과 패리티가 반복적으로 제공됩니다.

Azure Portal의 관리 환경에서는 이미 발표된 새 그룹화 및 대상 지정 기능을 사용합니다. 따라서 기존 테넌트가 새 그룹화 환경으로 마이그레이션될 때 사용자도 마이그레이션되어 테넌트에 새 관리 환경의 미리 보기가 표시됩니다. 그 동안 테넌트가 마이그레이션될 때까지 새 기능을 테스트하거나 살펴보려는 경우 새 Intune 평가판 계정에 등록하거나 [새 설명서](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune)를 살펴보세요.

테넌트 마이그레이션 일정에 대한 질문이 있으면 [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com)으로 마이그레이션 팀에 문의하세요.

Azure의 Intune 미리 보기에 대한 새로운 기능은 [여기](https://docs.microsoft.com/intune-azure/introduction/whats-new)에서 찾을 수 있습니다.

### <a name="see-also"></a>참고 항목
* [Microsoft Intune 블로그](http://go.microsoft.com/fwlink/?LinkID=273882)
* [클라우드 플랫폼 로드맵](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Azure Tools의 새로운 기능](https://docs.microsoft.com/intune-azure/introduction/whats-new)
* [What's new in the Company Portal UI](https://docs.microsoft.com/intune/whats-new/whats-new-in-company-portal-ui)(회사 포털 UI의 새로운 기능)
* [새로운 기능 - 아카이브](whats-new-archive.md)



<!--HONumber=Feb17_HO1-->


