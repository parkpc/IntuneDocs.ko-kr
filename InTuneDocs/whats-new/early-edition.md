---
title: "초기 버전 | Microsoft 문서"
description: 
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 03/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 1ba0dab35e0da6cfe744314a4935221a206fcea7
ms.openlocfilehash: 3b355d43d4be05535f256d88a8648c2e67035882
ms.lasthandoff: 03/13/2017


---


# <a name="the-early-edition-for-microsoft-intune---march-2017"></a>Microsoft Intune 초기 버전 - 2017년 3월

**초기 버전**에서는 Microsoft Intune의 향후 릴리스에서 도입될 기능의 목록을 제공합니다. 이 정보는 NDA 하에 매우 제한적으로 제공되며, 변경될 수 있습니다. 여기 나열된 일부 기능은 마감일을 맞추지 못할 위험이 있으며 다음 릴리스까지 지연될 수 있습니다. 다른 기능은 고객용 준비 상태를 확인하기 위해, 파일럿(플라이팅) 테스트 중 입니다. 질문이나 궁금한 내용이 있으면 Intune/PM 담당자에게 연락하세요.

이 페이지는 정기적으로 업데이트됩니다. 추가 업데이트가 있는지 다시 확인하세요.

> [!Note]
> Intune에 대해 다음 변경 사항을 개발 중입니다. 최종적으로는 이 모든 기능이 하이브리드 고객 배포(Intune과 Configuration Manager )용으로 지원될 예정입니다. 새로운 하이브리드 기능에 대한 자세한 내용은 [hybrid What’s New page](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management)(하이브리드 새로운 기능 페이지)를 참조하세요.

## <a name="new-capabilities"></a>새로운 기능

### <a name="new-user-experience-for-the-company-portal-app-for-android---621622--"></a>Android용 회사 포털 앱의 새 사용자 환경 <!--621622-->

Android용 회사 포털 앱이 최신 모양과 느낌 및 더 나은 사용자 경험을 위해 사용자 인터페이스를 업데이트할 예정입니다. 중요한 업데이트는 다음과 같습니다.

- 색: 회사 포털 탭 머리글이 IT 관리자가 정의한 브랜드 색으로 지정됩니다.
- 앱: **앱** 탭에서 **추천 앱** 및 **모든 앱** 단추가 업데이트됩니다.
- 검색: **앱** 탭에서 **검색** 단추가 부동 작업 단추입니다.
- 앱 탐색: 보다 쉽게 탐색할 수 있도록 **모든 앱** 보기에 탭으로 구분된 **추천**, **전체** 및 **범주** 보기가 표시됩니다.
- 지원: 가독성 향상을 위해 **내 장치** 및 **IT 담당자** 탭이 업데이트됩니다.

이러한 변경 사항에 대한 자세한 내용은 [앱 UI 업데이트 페이지](whats-new-in-intune-app-ui.md]에서 확인할 수 있습니다.

### <a name="signing-script-for-windows-10-company-portal---941642--"></a>Windows 10 회사 포털용 서명 스크립트 <!--941642-->

Windows 10 회사 포털 앱을 다운로드하거나 사이드로드해야 하는 고객의 경우 스크립트를 사용하여 조직의 앱 서명 프로세스를 단순화하고 간소화할 수 있습니다.   스크립트 및 사용 지침을 다운로드하려면 TechNet 갤러리에서 [ Microsoft Intune Signing Script for Windows 10 Company Portal(Windows 10 회사 포털용 Microsoft Intune 서명 스크립트)](https://aka.ms/win10cpscript)을 참조하세요. 이 알림에 대한 자세한 내용은 Intune 지원 팀 블로그에서 [Updating your Windows 10 Company Portal app(Windows 10 회사 포털 앱 업데이트)](https://blogs.technet.microsoft.com/intunesupport/2017/03/13/updating-your-windows-10-company-portal-app/)을 참조하세요. 

## <a name="notices"></a>알림

### <a name="improved-support-for-android-users-based-in-china---720444--"></a>중국에 거주하는 Android 사용자에 대한 지원 향상 <!--720444-->

중국에는 Google Play 스토어를 사용할 수 없으므로 Android 장치 사용자는 중국 마켓플레이스에서 앱을 다운로드해야 합니다. 회사 포털은 중국의 Android 사용자가 현지 앱 스토어에서 회사 포털 및 Outlook 앱을 다운로드하도록 리디렉션하여 이 워크플로를 지원합니다. 이는 모바일 장치 관리 및 모바일 응용 프로그램 관리에 대한 조건부 액세스 정책이 설정된 경우 사용자 환경을 개선합니다. Android용 회사 포털 및 Outlook 앱은 다음과 같은 중국 앱 스토어에서 사용할 수 있습니다.

- [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
- [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)
- [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
- [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
- [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple의 Application Transport Security 업데이트 요구 <!--748318-->

Apple에서는 2017년 봄부터 ATS(Application Transport Security)에 대한 특정 요구 사항을 적용할 것이라고 발표했습니다. ATS는 HTTPS를 통한 모든 앱 통신에서 보다 엄격한 보안을 적용하는 데 사용됩니다. 이 변경 사항은 iOS 회사 포털 앱을 사용하는 Intune 고객에게 영향을 줍니다. 자세한 내용은 [Intune 지원 블로그](https://aka.ms/compportalats)를 참조하세요.

## <a name="public-preview-of-the-new-intune-admin-experience-on-azure---736542--"></a>Azure의 새 Intune 관리 환경에 대한 공개 미리 보기<!--736542-->

2017년 초에 Microsoft에서는 전체 관리 환경을 Azure로 마이그레이션합니다. 이를 통해 Graph API를 사용하여 확장 가능한 최신 서비스 플랫폼에서 핵심 EMS 워크플로에 대한 강력한 통합 관리를 지원합니다.

새 평가판 테넌트에서는 이번 달에 Azure Portal에서 새 관리 환경의 공개 미리 보기를 표시하기 시작합니다. 미리 보기 상태에서는 기존 Intune 콘솔의 기능과 패리티가 반복적으로 제공됩니다.

Azure Portal의 관리 환경에서는 이미 발표된 새 그룹화 및 대상 지정 기능을 사용합니다. 따라서 기존 테넌트가 새 그룹화 환경으로 마이그레이션될 때 사용자도 마이그레이션되어 테넌트에 새 관리 환경의 미리 보기가 표시됩니다. 그 동안 테넌트가 마이그레이션될 때까지 새 기능을 테스트하거나 살펴보려는 경우 새 Intune 평가판 계정에 등록하거나 [새 설명서](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune)를 살펴보세요.

### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>관리되지 않은 장치에서 할당된 앱에 액세스 가능 <!--664691-->

회사 포털 웹 사이트 디자인 변경의 일환으로, iOS 및 Android 사용자가 자기에게 할당된 앱을 관리되지 않는 장치에 "등록 없이 사용 가능"으로 설치할 수 있습니다. 사용자는 Intune 자격 증명을 사용하여 회사 포털 웹 사이트에 로그인하고 자기에게 할당된 앱의 목록을 볼 수 있습니다. "등록 없이 사용 가능" 앱의 앱 패키지는 회사 포털 웹 사이트를 통해 다운로드할 수 있습니다. 설치하려면 등록이 필요한 앱은 사용자가 앱을 설치하려 할 때 등록하라는 메시지가 표시되므로 이 변경의 영향을 받지 않습니다.

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

### <a name="additional-windows-10-upgrade-paths---903672--"></a>추가 Windows 10 업그레이드 경로 <!--903672-->

이제 버전 업그레이드 정책을 만들어 장치를 다음과 같은 추가 Windows 10 버전으로 업그레이드할 수 있습니다.

- Windows 10 Professional
- Windows 10 Professional KN
- Windows 10 Professional Education
- Windows 10 Professional Education N


### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Apple 등록 시나리오에 대한 직접 액세스 <!--951869-->

2017년 1월 이후에 만든 Intune 계정은 Azure Preview 포털에서 장치 등록 워크로드를 사용하여 Apple 등록 시나리오에 직접 액세스할 수 있습니다. 이전에는 클래식 Intune 포털의 링크를 통해서만 Apple 등록 미리 보기에 액세스할 수 있었습니다. 2017년 1월 이전에 만든 Intune 계정은 일회성 마이그레이션을 수행해야 Azure에서 이러한 기능을 사용할 수 있습니다. 마이그레이션 일정은 아직 공지되지 않았지만 가능한 한 빠른 시일 내에 세부 정보가 제공될 예정입니다. 기존 계정에서 미리 보기에 액세스할 수 없는 경우 평가판 계정을 만들어 새로운 경험을 테스트해 보는 것이 좋습니다.

### <a name="see-also"></a>참고 항목
최근 개발 작업에 대한 자세한 내용은 [Microsoft Intune의 새로운 기능](whats-new-in-microsoft-intune.md)을 참조하세요.

