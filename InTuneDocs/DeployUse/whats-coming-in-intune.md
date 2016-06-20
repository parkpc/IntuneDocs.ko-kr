---
# required metadata

title: 향후 예정 사항 | Microsoft Intune
description:
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 05/17/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d

# optional metadata

ROBOTS: noindex,nofollow
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune의 향후 예정 사항
이 정보는 NDA 하에 매우 제한적으로 제공되며, 변경될 수 있습니다. 여기 나열된 일부 기능은 마감일을 맞추지 못할 위험이 있으며 다음 릴리스까지 지연될 수 있습니다. 다른 기능은 고객용 준비 상태를 확인하기 위해, 파일럿(플라이팅) 테스트 중 입니다. 질문이나 궁금한 내용이 있으면 Intune/PM 담당자에게 연락하세요.

이 페이지는 정기적으로 업데이트됩니다. 다시 방문하여, 향후 예정 사항에 새로운 업데이트가 있는지 확인하십시오.

Intune에 대해 다음 변경 사항을 개발 중입니다. 이 모든 기능이 하이브리드 고객 배포(Intune과 Configuration Manager )용으로 지원될 예정입니다. 새로운 하이브리드 기능에 대한 자세한 내용은 [hybrid What’s New page](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx)(하이브리드 새로운 기능 페이지)를 참조하세요.


## 앱 관리
- **Windows 10 엔터프라이즈 데이터 정책의 변경 내용.** Windows 10 엔터프라이즈 데이터 정책에서 앱 정책이 개선되었으므로 앱 규칙(이전의 보호된 앱)을 사용하여 구성된 정책을 저장하면 구성한 기존 규칙이 손실됩니다. 계속하려면 이러한 앱 규칙을 다시 구성해야 합니다.

- **브라우저에 대한 조건부 액세스.** 정책을 준수하고 관리되는 iOS 및 Android 장치에서만 액세스할 수 있도록, Exchange Online 및 SharePoint Online에 대한 조건부 액세스 정책을 설정할 수 있게 됩니다. iOS 및 Android 장치를 사용하여 Outlook Web Access(OWA) 및 SharePoint 사이트에 로그인하려는 최종 사용자에게는 Intune을 사용하여 장치를 등록하라는 메시지는 물론 로그인을 완료하기 전에 비호환 문제가 있으면 수정하라는 메시지를 표시하게 됩니다.
<!---TFS 1175844--->

- **Dynamics CRM Online에서 조건부 액세스를 지원합니다.** 고객은 정책을 준수하고 관리되는 iOS 및 Android 장치에서만 액세스할 수 있도록, Dynamics CRM Online에 대한 조건부 액세스 정책을 설정할 수 있게 됩니다. iOS 및 Android에서 Dynamics CRM 모바일 앱에 로그인하려고 하는 최종 사용자에게 Intune에 등록하고 로그인을 완료하기 전에 모든 비호환성 문제를 해결해야 한다는 메시지가 표시됩니다.
<!---TFS1295358--->

### Xamarin 지원
Microsoft Intune 앱 SDK는 다음 시나리오에서 Xamarin 앱을 지원합니다.

- Intune SDK를 사용하여 기존 LOB(기간 업무) 앱의 코드를 수정하거나 새 앱을 작성. [Microsoft Intune Github](https://github.com/msintuneappsdk) 페이지에서 플러그 인을 확보할 수 있습니다.
- Intune 앱 래핑 도구를 사용하여 기존 LOB(기간 업무) 앱에 MAM 지원을 추가.

사용할 방법을 선택하는 데 도움이 필요하면 [Microsoft Intune으로 모바일 응용 프로그램 관리용 앱을 준비하는 방법 결정](https://docs.microsoft.com/en-us/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune)을 참조하세요.
<!--- TFS 1061478 & TFS 1152340--->


## 회사 포털
**iOS 회사 포털 앱의 장치 등록 관리자 계정의 변경 내용.** 성능과 확장성을 개선하기 위해 Intune은 iOS 회사 포털 앱의 내 장치 창에 모든 DEM(장치 등록 관리자)을 더 이상 표시하지 않습니다. 앱을 실행하는 로컬 장치가 회사 포털 앱을 통해 등록된 경우에만 표시합니다. DEM 사용자가 로컬 장치에서 작업을 수행할 수 있지만, 등록된 다른 장치의 원격 관리는 Intune 관리 콘솔에서만 수행될 수 있습니다.  또한 Intune은 Apple 장치 등록 프로그램 또는 Apple Configurator 도구에서 DEM 계정을 사용하지 않을 예정입니다. 이 두 가지 등록 방식은 공유 iOS 장치에 대해 사용자 정보가 없는 등록을 지원합니다.  DEM 계정은 공유 장치에 대해 사용자 정보가 없는 등록을 사용할 수 없는 경우에만 사용합니다.
<!---TFS 1233681--->

## 서비스 중단
**Windows 8 및 Windows Phone 8용 회사 포털 앱은 2016년 9월부터 사용되지 않습니다.** 2016년 9월부터 Microsoft Intune은 Windows Phone 8 및 Windows 8 플랫폼용 Microsoft Intune 회사 포털 앱에 대한 지원을 종료합니다. 장치를 Windows 8.1 및 Windows Phone 8.1로 업데이트하고 해당하는 Windows 8.1 및 Windows Phone 8.1 회사 포털 앱을 사용하여 이러한 장치에 앱을 계속 배포하세요.
<!---TFS 1255391--->

**사용자 지정 그룹을 알림 규칙의 대상으로 지정하는 기능 제거.**
Intune 알림 규칙은 Intune에서 메일 경고를 보낼 대상자를 정의합니다. 현재 직접 만든 Intune 장치 그룹의 모든 장치 사용자에게 메일을 보내도록 알림 규칙을 구성할 수 있습니다. 2016년 6월 1일경부터는 사용자가 만든 그룹을 대상으로 지정하는 기능이 더 이상 지원되지 않습니다.

이러한 변경을 준비하기 위한 타임라인은 다음과 같습니다.
- 2016년 6월에는 새 테넌트에 알림 규칙 만들기 마법사의 2단계가 표시되지 않습니다. 기존 테넌트는 영향을 받지 않습니다.
- 2016년 8월경에는 일부 기존 테넌트에 마법사의 "장치 그룹 선택"이 표시되지 않습니다.
- 2016년 10월경에는 모든 기존 테넌트에 마법사의 "장치 그룹 선택"이 표시되지 않을 것으로 예상됩니다.

<!---   TFS 1278864--->
**iOS 회사 포털 앱에 대한 지원의 변경 내용.**
사용자는 최신 iOS 회사 포털 앱으로 업데이트해야 합니다. 향후 몇 개월 내에 iOS용 Microsoft Intune 회사 포털 앱의 모든 사용자는 최신 버전을 사용해야 합니다. 새 사용자는 최신 버전만 다운로드할 수 있고 현재 사용자는 최신 버전으로 업데이트해야 합니다. 최신 버전을 사용하려면 iOS 8.0 이상이 필요하므로 이전 iOS 버전을 실행하는 장치는 장치를 iOS 8.0 이상으로 업데이트한 다음 회사 포털 앱을 최신 버전으로 업데이트할 때까지 회사 포털을 사용하거나 등록할 수 없습니다. iOS 8.0 이전 버전을 실행하는 등록된 장치는 Intune 관리자 콘솔에서 계속 관리되고 표시됩니다.  

**Intune 뷰어 앱.** 2016년 8월부터 새 RMS 공유 앱의 릴리스에서 다음 Intune 뷰어 앱을 제거합니다.
- Intune AV 뷰어
- Intune PDF 뷰어
- Google Play의 Android용 Intune 이미지 뷰어

Intune 뷰어 앱을 사용하는 대신 새로운 Android용 Microsoft Rights Management 공유 앱(RMS 공유)을 사용하는 것이 좋습니다. 이 앱을 통해 세 개의 별도 앱이 아니라 하나의 앱을 배포하여 Android 장치에서 회사 파일을 안전하게 볼 수 있습니다. RMS 공유 앱에 대해 자세히 알아보세요(설명서 링크 사용).


### 참고 항목
최근 개발 작업에 대한 자세한 내용은 [What’s New in Microsoft Intune](whats-new-in-microsoft-intune.md)(Microsoft Intune의 새로운 기능)을 참조하세요.


<!--HONumber=Jun16_HO2-->


