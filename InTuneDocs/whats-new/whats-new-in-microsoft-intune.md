---
title: "새로운 기능 | Microsoft 문서"
description: "이번 달의 새로운 소식과 Microsoft Intune의 이전 릴리스 확인"
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 04/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 62dcb40ad5a7921c514a9d41da14b991e39f3bcd
ms.openlocfilehash: b3cf8d8f60482be2d4d903d1b2c00c1a3a392b73
ms.lasthandoff: 04/20/2017


---
# <a name="whats-new-in-microsoft-intune---april-2017"></a>Microsoft Intune의 새로운 기능 - 2017년 4월
이번 Microsoft Intune 릴리스의 새로운 기능에 대해 알아봅니다. 이전 릴리스에 대한 정보뿐만 아니라 계획을 수립해야 하는 예정된 변경에 대해서도 알아볼 수 있습니다.

> [!Note]
> 최종적으로는 이 모든 기능이 하이브리드 고객 배포(Intune과 Configuration Manager )용으로 지원될 예정입니다. 새로운 하이브리드 기능에 대한 자세한 내용은 [hybrid What’s New page](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management)(하이브리드 새로운 기능 페이지)를 참조하세요.

## <a name="new-capabilities"></a>새로운 기능

### <a name="improved-sign-in-experience-across-company-portal-apps-for-all-platforms---user-story-1132123--"></a>모든 플랫폼에 대해 회사 포털 앱 전체에서 로그인 환경 개선됨 <!--User Story 1132123-->

Android, iOS 및 Windows용 Intune 회사 포털 앱에 대한 로그인 환경을 개선하고 있습니다. Azure AD에서 이 변경 내용을 적용할 경우 회사 포털 앱에 대한 모든 플랫폼에서 새로운 사용자 환경이 자동으로 나타나게 됩니다. 또한 사용자가 이제 생성된 일회용 코드를 사용하여 다른 장치에서 회사 포털에 로그인할 수도 있습니다. 이 기능은 사용자가 자격 증명 없이 로그인해야 할 경우에 특히 유용합니다.

이전 로그인 환경, 자격 증명을 사용하는 새 로그인 환경, 그리고 다른 장치로부터의 새 로그인 환경에 대한 스크린샷은 [앱 UI의 새로운 기능](whats-new-in-intune-app-ui.md) 페이지에서 볼 수 있습니다.

### <a name="myapps-available-for-managed-browser---822308-822303--"></a>Managed Browser에 사용할 수 있는 MyApps <!--822308, 822303-->

Microsoft MyApps는 이제 Managed Browser 내에서 더 나은 지원을 제공합니다. 관리 대상으로 지정되지 않은 Managed Browser 사용자는 MyApps 서비스로 직접 연결되므로 관리자가 프로비전한 SaaS 앱에 액세스할 수 있습니다. Intune 관리 대상으로 지정된 사용자는 계속 기본 제공 Managed Browser 책갈피에서 MyApps에 액세스할 수 있습니다.

### <a name="new-icons-for-the-managed-browser-and-the-company-portal---918433-918431-971473--"></a>Managed Browser 및 회사 포털에 대한 새 아이콘 <!--918433, 918431, 971473-->

Managed Browser는 앱의 Android 및 iOS 버전 모두에 대한 업데이트된 아이콘을 수신합니다. 새 아이콘은 업데이트된 Intune 배지를 포함하므로 EM+S(Enterprise Mobility + Security)의 다른 앱과 더 일관된 환경을 제공합니다. [Intune 앱 UI 페이지의 새로운 기능](whats-new-in-intune-app-ui.md)에서 Managed Browser의 새 아이콘을 볼 수 있습니다.

회사 포털도 앱의 Android, iOS 및 Windows 버전에 대해 업데이트된 아이콘을 수신하므로 EM+S의 다른 앱과의 일관성을 개선합니다. 이러한 아이콘은 4월부터 5월 말까지 여러 플랫폼에서 점진적으로 출시됩니다.

### <a name="sign-in-progress-indicator-in-android-company-portal---953374--"></a>Android 회사 포털의 로그인 진행률 표시기 <!--953374-->

Android 회사 포털 앱의 업데이트에는 사용자가 앱을 시작하거나 다시 시작할 때 로그인 진행률 표시기가 표시됩니다. 표시기에서는 "연결 중..."에서부터 "로그인 중...", "보안 요구 사항을 확인하는 중..."까지 새로운 상태를 진행한 후 사용자가 앱에 액세스할 수 있도록 허용합니다. [Intune 앱 UI 페이지의 새로운 기능](whats-new-in-intune-app-ui.md)에서 Android용 회사 포털 앱의 새 화면을 볼 수 있습니다.

### <a name="block-apps-from-accessing-sharepoint-online----679339---"></a>앱의 SharePoint Online 액세스 차단 <!-- 679339 -->

이제 앱 보호 정책이 적용되지 않은 앱이 [SharePoint Online](/InTune/deploy-use/mam-ca-for-sharepoint-online)에 액세스하지 않도록 차단하는 앱 기반 조건부 액세스 정책을 만들 수 있습니다. 앱 기반 조건부 액세스 시나리오에서는 Azure Portal을 사용하여 SharePoint Online에 액세스할 앱을 지정할 수 있습니다.

### <a name="bulk-enroll-windows-10-devices----747607---"></a>Windows 10 장치 대량 등록 <!-- 747607 -->

이제 WCD(Windows 구성 디자이너)를 사용하여 Azure Active Directory 및 Intune에 대한 Windows 10 크리에이터 업데이트를 실행하는 많은 장치를 연결할 수 있습니다. Azure AD 테넌트에 대한 [대량 MDM 등록](/intune/deploy-use/bulk-enroll-windows)을 사용하도록 설정하려면 Windows 구성 디자이너를 사용하여 Azure AD 테넌트에 장치를 연결하는 프로비전 패키지를 만들고, 이 패키지를 대량으로 등록 및 관리할 회사 소유 장치에 적용합니다. 패키지가 장치에 적용되면, 장치가 Azure AD에 연결되고 Intune에 등록되며 Azure AD 사용자가 로그온할 수 있는 준비를 하게 됩니다.  Azure AD 사용자는 이러한 장치에서 표준 사용자이며 할당된 정책 및 필수 앱을 수신합니다. 셀프 서비스 및 회사 포털 시나리오의 경우 이번에는 지원되지 않습니다.

## <a name="notices"></a>알림

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Apple 등록 시나리오에 대한 직접 액세스 <!--951869-->

2017년 1월 이후에 만든 Intune 계정은 Azure Preview 포털에서 장치 등록 워크로드를 사용하여 Apple 등록 시나리오에 직접 액세스할 수 있습니다. 이전에는 클래식 Intune 포털의 링크를 통해서만 Apple 등록 미리 보기에 액세스할 수 있었습니다. 2017년 1월 이전에 만든 Intune 계정은 일회성 마이그레이션을 수행해야 Azure에서 이러한 기능을 사용할 수 있습니다. 마이그레이션 일정은 아직 공지되지 않았지만 가능한 한 빠른 시일 내에 세부 정보가 제공될 예정입니다. 기존 계정에서 미리 보기에 액세스할 수 없는 경우 평가판 계정을 만들어 새로운 경험을 테스트해 보는 것이 좋습니다.

### <a name="whats-coming-for-appx-in-intune-on-azure----1000270---"></a>Azure의 Intune에서 Appx에 대한 향후 변경 사항 <!-- 1000270 -->

Azure의 Intune으로 마이그레이션하는 과정의 일환으로 appx의 다음 세 가지 사항을 변경합니다.

1. MDM에 등록된 장치에만 배포할 수 있는 새 appx 앱 유형을 클래식 Intune 콘솔에 추가합니다.
2. Intune PC 에이전트를 통해 관리되는 PC만 대상으로 할 수 있도록 기존 appx 앱 유형의 용도를 변경합니다.
3. 마이그레이션과 함께 기존 appx를 모두 MDM appx로 변환합니다.

#### <a name="how-does-this-affect-me"></a>이 변경 사항은 어떤 영향을 미치나요?

Intune PC 에이전트를 통해 관리되는 장치의 기존 배포에는 아무런 영향을 주지 않습니다. 그러나 마이그레이션 후에는 이전에 대상으로 하지 않았던 Intune PC 에이전트를 통해 관리되는 새 장치에 마이그레이션된 appx를 배포할 수 없습니다.

#### <a name="what-action-do-i-need-to-take"></a>수행해야 하는 작업

마이그레이션 후 새 PC 배포를 수행하려면 appx를 PC appx로 다시 업로드해야 합니다. 자세한 내용은 [Appx changes in Intune on Azure](https://aka.ms/appxchange)(Azure의 Intune에서 Appx 변경 사항)를 참조하세요.  


## <a name="whats-new-in-the-public-preview-of-the-intune-admin-experience-on-azure---736542--"></a>Azure의 Intune 관리 환경 공개 미리 보기의 새로운 기능<!--736542-->

2017년 초에 Microsoft에서는 전체 관리 환경을 Azure로 마이그레이션합니다. 이를 통해 Graph API를 사용하여 확장 가능한 최신 서비스 플랫폼에서 핵심 EMS 워크플로에 대한 강력한 통합 관리를 지원합니다.

새 평가판 테넌트에서는 이번 달에 Azure Portal에서 새 관리 환경의 공개 미리 보기를 표시하기 시작합니다. 미리 보기 상태에서는 기존 Intune 콘솔의 기능과 패리티가 반복적으로 제공됩니다.

Azure Portal의 관리 환경에서는 이미 발표된 새 그룹화 및 대상 지정 기능을 사용합니다. 따라서 기존 테넌트가 새 그룹화 환경으로 마이그레이션될 때 사용자도 마이그레이션되어 테넌트에 새 관리 환경의 미리 보기가 표시됩니다. 그 동안 테넌트가 마이그레이션될 때까지 새 기능을 테스트하거나 살펴보려는 경우 새 Intune 평가판 계정에 등록하거나 [새 설명서](/intune-azure/introduction/whats-new)를 살펴보세요.

> [!Note]
> Azure Portal 미리 보기의 경우 이번 달 업데이트를 출시합니다. 그러나 Intune 서비스 출시 방법으로 인해 변경 사항을 곧바로 사용할 수 없을 수 있습니다.  Intune 서비스의 몇 가지 구성 요소를 순차적으로 업데이트해야 새 포털 기능을 사용할 수 있습니다. 이번 달 말에 배포되면 Azure Portal 미리 보기에서 이러한 변경 사항을 확인해 보세요. 전체 변경 사항 목록은 [Microsoft Intune Preview의 새로운 기능](/intune-azure/introduction/whats-new)을 참조하세요.

### <a name="administration-roles-being-replaced-in-azure-portal"></a>Azure Portal에서 대체되는 관리 역할

Intune 클래식 포털(Silverlight)에서 사용된 기존 MAM(모바일 응용 프로그램 관리) 관리 역할(참가자, 소유자 및 읽기 전용)은 Intune Azure Portal에서 새로운 RBAC(역할 기반 관리 제어)의 전체 집합으로 대체됩니다. Azure Portal로 마이그레이션한 후에 이러한 새 관리 역할에 관리자를 다시 할당해야 합니다. RBAC 및 새 역할에 대한 자세한 내용은 [Microsoft Intune에 대한 역할 기반 액세스 제어](/intune-azure/access-control/role-based-access-control)를 참조하세요.


## <a name="whats-coming"></a>향후 예정 사항

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple의 Application Transport Security 업데이트 요구 <!--748318-->

Apple에서는 2017년 봄부터 ATS(Application Transport Security)에 대한 특정 요구 사항을 적용할 것이라고 발표했습니다. ATS는 HTTPS를 통한 모든 앱 통신에서 보다 엄격한 보안을 적용하는 데 사용됩니다. 이 변경 사항은 iOS 회사 포털 앱을 사용하는 Intune 고객에게 영향을 줍니다. 자세한 내용은 [Intune 지원 블로그](https://aka.ms/compportalats)를 참조하세요.

### <a name="see-also"></a>참고 항목
* [Microsoft Intune 블로그](http://go.microsoft.com/fwlink/?LinkID=273882)
* [클라우드 플랫폼 로드맵](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Azure Tools의 새로운 기능](https://docs.microsoft.com/intune-azure/introduction/whats-new)
* [What's new in the Company Portal UI](https://docs.microsoft.com/intune/whats-new/whats-new-in-company-portal-ui)(회사 포털 UI의 새로운 기능)
* [새로운 기능 - 아카이브](whats-new-archive.md)

