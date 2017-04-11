---
title: "새로운 기능 | Microsoft 문서"
description: "이번 달의 새로운 소식과 Microsoft Intune의 이전 릴리스 확인"
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 03/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: c473a1f05b0a7b0ce5205598b2b9a9b86bfe6c1d
ms.openlocfilehash: bddd8c0dc74835f74a71af1d900d43d84aab894c
ms.lasthandoff: 03/29/2017


---
# <a name="whats-new-in-microsoft-intune---march-2017"></a>Microsoft Intune의 새로운 기능 - 2017년 3월
이번 Microsoft Intune 릴리스의 새로운 기능에 대해 알아봅니다. 이전 릴리스에 대한 정보뿐만 아니라 계획을 수립해야 하는 예정된 변경에 대해서도 알아볼 수 있습니다.

> [!Note]
> 최종적으로는 이 모든 기능이 하이브리드 고객 배포(Intune과 Configuration Manager )용으로 지원될 예정입니다. 새로운 하이브리드 기능에 대한 자세한 내용은 [hybrid What’s New page](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management)(하이브리드 새로운 기능 페이지)를 참조하세요.

## <a name="new-capabilities"></a>새로운 기능

### <a name="support-for-skycure"></a>Skycure에 대한 지원

이제 Microsoft Intune과 통합된 Mobile Threat Defense 솔루션인 Skycure에서 수행한 위험 평가에 따라 조건부 액세스를 사용하여 회사 리소스에 대한 모바일 장치의 액세스를 제어할 수 있습니다. 위험은 다음을 비롯하여 Skycure를 실행하는 장치에서 수집된 원격 분석에 따라 평가됩니다.

- 물리적 방어
- 네트워크 방어
- 응용 프로그램 방어
- 취약성 방어

Intune 장치 준수 정책을 통해 사용하도록 설정된 Skycure 위험 평가에 따라 EMS 조건부 액세스 정책을 구성할 수 있습니다. 이러한 정책을 사용하여 검색된 위협에 따라 회사 리소스에 대한 비규격 장치 액세스를 허용하거나 차단할 수 있습니다. 자세한 내용은 [Skycure Mobile Threat Defense 커넥터](/intune/deploy-use/skycure-mobile-threat-defense-connector)를 참조하세요.

### <a name="new-user-experience-for-the-company-portal-app-for-android---621622--"></a>Android용 회사 포털 앱의 새 사용자 환경 <!--621622-->

Android용 회사 포털 앱이 최신 모양과 느낌 및 더 나은 사용자 경험을 위해 사용자 인터페이스를 업데이트할 예정입니다. 중요한 업데이트는 다음과 같습니다.

- 색: 회사 포털 탭 머리글이 IT 관리자가 정의한 브랜드 색으로 지정됩니다.
- 앱: **앱** 탭에서 **추천 앱** 및 **모든 앱** 단추가 업데이트됩니다.
- 검색: **앱** 탭에서 **검색** 단추가 부동 작업 단추입니다.
- 앱 탐색: 보다 쉽게 탐색할 수 있도록 **모든 앱** 보기에 탭으로 구분된 **추천**, **전체** 및 **범주** 보기가 표시됩니다.
- 지원: 가독성 향상을 위해 **내 장치** 및 **IT 담당자** 탭이 업데이트됩니다.

이러한 변경에 대한 자세한 내용은 [Intune 최종 사용자 앱 UI 업데이트](whats-new-in-intune-app-ui.md)를 참조하세요.

### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>관리되지 않은 장치에서 할당된 앱에 액세스 가능 <!--664691-->

회사 포털 웹 사이트 디자인 변경의 일환으로, iOS 및 Android 사용자가 자기에게 할당된 앱을 관리되지 않는 장치에 "등록 없이 사용 가능"으로 설치할 수 있습니다. 사용자는 Intune 자격 증명을 사용하여 회사 포털 웹 사이트에 로그인하고 자기에게 할당된 앱의 목록을 볼 수 있습니다. "등록 없이 사용 가능" 앱의 앱 패키지는 회사 포털 웹 사이트를 통해 다운로드할 수 있습니다. 설치하려면 등록이 필요한 앱은 사용자가 앱을 설치하려 할 때 등록하라는 메시지가 표시되므로 이 변경의 영향을 받지 않습니다.

### <a name="signing-script-for-windows-10-company-portal---941642--"></a>Windows 10 회사 포털용 서명 스크립트 <!--941642-->

Windows 10 회사 포털 앱을 다운로드하거나 사이드로드해야 하는 경우 스크립트를 사용하여 조직의 앱 서명 프로세스를 단순화하고 간소화할 수 있습니다.   스크립트 및 사용 지침을 다운로드하려면 TechNet 갤러리에서 [ Microsoft Intune Signing Script for Windows 10 Company Portal(Windows 10 회사 포털용 Microsoft Intune 서명 스크립트)](https://aka.ms/win10cpscript)을 참조하세요. 이 알림에 대한 자세한 내용은 Intune 지원 팀 블로그에서 [Updating your Windows 10 Company Portal app(Windows 10 회사 포털 앱 업데이트)](https://blogs.technet.microsoft.com/intunesupport/2017/03/13/updating-your-windows-10-company-portal-app/)을 참조하세요.


## <a name="notices"></a>알림

### <a name="support-for-ios-103"></a>iOS 10.3에 대한 지원

iOS 10.3 릴리스가 2017년 3월 27일에 iOS 사용자에게 배포되기 시작했습니다. 기존의 모든 Intune MDM 및 MAM 시나리오는 최신 버전의 Apple OS와 호환됩니다. 현재 iOS 장치 관리에 사용할 수 있는 기존의 모든 Intune 기능은 사용자가 장치 및 앱을 iOS 10.3으로 업그레이드할 때도 계속 작동할 것으로 예상합니다.

현재 공유할 만한 알려진 문제는 없습니다. iOS 10.3 관련 문제가 발생하는 경우 [Intune 지원 팀](/intune/troubleshoot/contact-assisted-phone-support-for-microsoft-intune)에 연락해 주시기 바랍니다.

### <a name="improved-support-for-android-users-based-in-china---720444--"></a>중국에 거주하는 Android 사용자에 대한 지원 향상 <!--720444-->

중국에는 Google Play 스토어를 사용할 수 없으므로 Android 장치 사용자는 중국 마켓플레이스에서 앱을 다운로드해야 합니다. 회사 포털은 중국의 Android 사용자가 현지 앱 스토어에서 회사 포털 및 Outlook 앱을 다운로드하도록 리디렉션하여 이 워크플로를 지원합니다. 이는 모바일 장치 관리 및 모바일 응용 프로그램 관리에 대한 조건부 액세스 정책이 설정된 경우 사용자 환경을 개선합니다. Android용 회사 포털 및 Outlook 앱은 다음과 같은 중국 앱 스토어에서 사용할 수 있습니다.

- [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
- [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)
- [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
- [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
- [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)

### <a name="best-practice-make-sure-your-company-portal-apps-are-up-to-date---879465--"></a>모범 사례: 회사 포털 앱을 최신으로 유지하기<!--879465-->

2016년 12월 Microsoft는 iOS, Android, Windows 8.1 이상 또는 Windows Phone 8.1 이상 장치를 등록할 때 사용자 그룹에 대한 MFA(다단계 인증) 적용을 사용하도록 설정한 업데이트를 릴리스했습니다. 이 기능은 Android(v5.0.3419.0 이상) 및 iOS(v2.1.17 이상)에 대한 특정 기준 버전의 회사 포털 앱 없이는 작동할 수 없습니다.

Microsoft는 지원되는 모든 플랫폼에서 콘솔 및 회사 포털 앱에 새로운 기능을 추가함으로써 지속적으로 Intune을 개선하고 있습니다. 결과적으로, Microsoft는 현재 버전의 회사 포털 앱에서 발견되는 문제에 대해서만 수정 사항을 릴리스합니다. 따라서 최상의 사용자 환경을 위해 최신 버전의 회사 포털 앱을 사용하는 것이 좋습니다.

>[!Tip]
> 사용자에게 해당 앱 스토어에서 자동으로 앱을 업데이트하도록 장치를 설정하게 요청하세요. Android 회사 포털 앱을 네트워크 공유에서 사용 가능하도록 한 경우에는 [Microsoft 다운로드 센터](https://www.microsoft.com/download/details.aspx?id=49140)에서 최신 버전을 다운로드할 수 있습니다.

### <a name="microsoft-teams-is-now-enabled-for-mam-on-ios-and-android"></a>iOS 및 Android에서 Microsoft Teams의 MAM 활성화

Microsoft는 Microsoft Teams의 일반적인 가용성을 발표했습니다. iOS 및 Android용 업데이트된 Microsoft Teams 앱은 이제 Intune MAM(모바일 앱 관리) 기능이 활성화되었습니다. 따라서 대화 및 회사 데이터를 보호하면서도 팀원들이 여러 장치에서 자유롭게 작업하도록 할 수 있습니다. 자세한 내용은 Enterprise Mobility + Security 블로그에서 [Microsoft Teams 알림](https://blogs.technet.microsoft.com/enterprisemobility/2017/03/14/microsoft-teams-is-now-generally-available-and-mam-enabled-on-ios-and-android/)을 참조하세요.


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
* [클라우드 플랫폼 로드맵](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Azure Tools의 새로운 기능](https://docs.microsoft.com/intune-azure/introduction/whats-new)
* [What's new in the Company Portal UI](https://docs.microsoft.com/intune/whats-new/whats-new-in-company-portal-ui)(회사 포털 UI의 새로운 기능)
* [새로운 기능 - 아카이브](whats-new-archive.md)

