---
title: "초기 버전 | Microsoft Intune"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6dd584397451d38be86fa0780efff435ffb9b2af
ms.openlocfilehash: d70ebf87bc930f853741ddc0d572d2174c636dac


---

# <a name="the-early-edition-for-microsoft-intune---december"></a>Microsoft Intune 초기 버전 - 12월

**초기 버전**에서는 Microsoft Intune의 향후 릴리스에서 도입될 기능의 목록을 제공합니다. 이 정보는 NDA 하에 매우 제한적으로 제공되며, 변경될 수 있습니다. 여기 나열된 일부 기능은 마감일을 맞추지 못할 위험이 있으며 다음 릴리스까지 지연될 수 있습니다. 다른 기능은 고객용 준비 상태를 확인하기 위해, 파일럿(플라이팅) 테스트 중 입니다. 질문이나 궁금한 내용이 있으면 Intune/PM 담당자에게 연락하세요.

이 페이지는 정기적으로 업데이트됩니다. 추가 업데이트가 있는지 다시 확인하세요.

Intune에 대해 다음 변경 사항을 개발 중입니다. 최종적으로는 이 모든 기능이 하이브리드 고객 배포(Intune과 Configuration Manager )용으로 지원될 예정입니다. 새로운 하이브리드 기능에 대한 자세한 내용은 [hybrid What’s New page](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx)(하이브리드 새로운 기능 페이지)를 참조하세요.

<!--736542-->
## <a name="public-preview-of-the-new-intune-admin-experience-on-azure"></a>Azure의 새 Intune 관리 환경 공개 미리 보기

2017년 초에 Microsoft에서는 전체 관리 환경을 Azure로 마이그레이션합니다. 이를 통해 Graph API를 사용하여 확장 가능한 최신 서비스 플랫폼에서 핵심 EMS 워크플로에 대한 강력한 통합 관리를 지원합니다.

새 평가판 테넌트에서는 이번 달에 Azure Portal에서 새 관리 환경의 공개 미리 보기를 표시하기 시작합니다. 미리 보기 상태에서는 기존 Intune 콘솔의 기능과 패리티가 반복적으로 제공됩니다.

Azure Portal의 관리 환경에서는 이미 발표된 새 그룹화 및 대상 지정 기능을 사용합니다. 따라서 기존 테넌트가 새 그룹화 환경으로 마이그레이션될 때 사용자도 마이그레이션되어 테넌트에 새 관리 환경의 미리 보기가 표시됩니다. 그 동안 테넌트가 마이그레이션될 때까지 새 기능을 테스트하거나 살펴보려는 경우 새 Intune 평가판 계정에 등록하거나 새 설명서를 살펴보세요.

테넌트 마이그레이션 일정에 대한 질문이 있으면 [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com)으로 마이그레이션 팀에 문의하세요.

### <a name="telecom-expense-management-integration-in-public-preview-of-azure-portal--747605--"></a>Azure Portal의 공개 미리 보기에서 이동통신 지출 관리 통합<!--747605-->
이제 Azure Portal 내에서 타사 TEM(이동통신 지출 관리) 서비스와의 통합 미리 보기를 시작합니다. Intune을 사용하여 국내 및 로밍 데이터 사용량을 제한할 수 있습니다. 우선 [Saaswedo](http://www.saaswedo.com)와의 통합으로 시작합니다.

## <a name="new-capabilities"></a>새로운 기능

### <a name="multi-factor-authentication-across-all-platforms---747590--"></a>모든 플랫폼에서 다단계 인증 <!--747590-->
이제 선택한 사용자 그룹이 Azure 관리 포털에서 iOS, Android, Windows 8.1+ 또는 Windows Phone 8.1+ 장치를 등록할 때 Azure Active Directory의 Microsoft Intune 등록 응용 프로그램에서 MFA(Multi-Factor Authentication)를 구성하여 해당 사용자 그룹에 MFA를 적용할 수 있습니다.

### <a name="conditional-access-for-mam-with-sharepoint-online---vso-679339--"></a>SharePoint Online에서 MAM에 대한 조건부 액세스 <!--VSO 679339-->
Intune MAM(모바일 앱 관리) 정책에서 지원되지 않는 앱이 SharePoint Online에 액세스하지 못하도록 할 수 있습니다.  Intune 모바일 앱 관리는 Azure Portal에서 시작할 수 있습니다. SharePoint Online에 대한 옵션을 포함하는 __설정__ 블레이드의 __조건부 액세스__ 섹션을 찾아보세요. 이 기능은 나머지 서비스 릴리스와 별도로 제공됩니다.

### <a name="ability-to-restrict-intune-mobile-device-enrollment"></a>Intune 모바일 장치 등록을 제한하는 기능
Intune은 등록할 수 있는 모바일 장치 플랫폼을 제어하는 새로운 등록 제한을 추가합니다. Intune은 모바일 장치 플랫폼을 iOS, macOS, Android, Windows 및 Windows Mobile로 구분합니다. 
* macOS 및 Windows 8.1 이상은 모바일 장치 플랫폼으로 등록하는 것이 제한될 수 있습니다. 
* 모바일 장치 등록을 제한해도 PC 에이전트 등록은 제한되지 않습니다. 
* iOS에 한해, 개인 소유 장치의 등록을 차단하는 한 가지 추가 옵션이 있습니다. Intune은 [이 문서](https://docs.microsoft.com/en-us/intune/deploy-use/manage-corporate-owned-devices)에 설명된 대로 IT 관리자가 회사 소유로 표시하기 위한 조치를 취하지 않은 한 모든 새 장치를 개인 소유 장치로 표시합니다.


## <a name="notices"></a>알림

### <a name="multi-factor-authentication-on-enrollment-moving-to-the-azure-portal---vso-750545--"></a>등록에 대한 Multi-Factor Authentication이 Azure Portal로 이동 <!--VSO 750545-->
이전에는 관리자가 Intune 콘솔 또는 Configuration Manager(1610 릴리스 이전) 콘솔로 이동하여 Intune 등록에 대한 MFA를 설정했습니다. 이 업데이트된 기능을 사용하면 이제 [Microsoft Azure Portal](https://manage.windowsazure.com)에 Intune 자격 증명으로 로그인하고 Azure AD를 통해 MFA 설정을 구성합니다. 이 기능에 대한 자세한 내용은 [여기](https://aka.ms/mfa_ad)를 참조하세요.

### <a name="company-portal-app-for-android-now-available-in-china---vso-658093--"></a>이제 중국에서 Android용 회사 포털 앱 사용 가능 <!--VSO 658093-->
중국에서 Android 용 회사 포털 앱을 다운로드할 수 있도록 게시합니다. 중국에는 Google Play 스토어가 없으므로 Android 장치는 중국 앱 마켓플레이스에서 앱을 구입해야 합니다. Android용 회사 포털 앱은 360, Tencent, Xiaomi, Wandoujia 및 Huawei에서 다운로드할 수 있습니다. 

Android용 회사 포털 앱은 Google Play 서비스를 사용하여 Microsoft Intune 서비스와 통신합니다. 중국에서는 Google Play 서비스가 아직 제공되지 않으므로 다음 작업을 수행하면 완료까지 최대 8시간 걸릴 수 있습니다. 

|Intune 관리 콘솔| Android용 Intune 회사 포털 앱 |Intune 회사 포털 웹 사이트|   
|---|---|---|
|전체 초기화| 원격 장치 제거| 장치(로컬 및 원격) 제거|
|선택적 초기화| 장치 다시 설정| 장치 다시 설정|
|새 앱 또는 업데이트된 앱 배포| 사용 가능한 기간 업무 앱 설치| 장치 암호 재설정|
|원격 잠금|||
|암호 재설정|||

## <a name="deprecations"></a>지원 중단

### <a name="removal-of-exchange-online-mobile-inbox-policies---770687--"></a>Exchange Online 모바일 받은 편지함 정책 제거 <!--770687-->
12월부터 관리자는 더 이상 Intune 콘솔 내에서 Exchange Online(EAS) 모바일 사서함 정책을 보거나 구성할 수 없습니다. 12월과 1월 동안에 이 변경 내용이 모든 Intune 테넌트로 롤아웃됩니다. 모든 기존 정책은 구성된 상태로 유지됩니다. 새 정책을 구성하려면 Exchange 관리 셸을 사용하세요. 자세한 내용은 [여기](https://technet.microsoft.com/en-us/library/bb123783%28v=exchg.150%29.aspx)를 참조하세요.

### <a name="intune-av-player-image-viewer-and-pdf-viewer-apps-are-no-longer-supported-on-android---747553--"></a>Intune AV Player, 이미지 뷰어 및 PDF 뷰어 앱이 Android에서 더 이상 지원되지 않음 <!--747553-->
2016년 12월 중순부터 사용자는 더 이상 Intune AV Player, 이미지 뷰어 및 PDF 뷰어 앱을 사용할 수 없습니다. 이러한 앱은 Azure Information Protection 앱으로 대체되었습니다. Azure Information Protection 앱에 대한 자세한 내용은 [여기](https://docs.microsoft.com/information-protection/rms-client/mobile-app-faq)를 참조하세요.

### <a name="see-also"></a>참고 항목
최근 개발 작업에 대한 자세한 내용은 [Microsoft Intune의 새로운 기능](whats-new-in-microsoft-intune.md)을 참조하세요.



<!--HONumber=Nov16_HO5-->


