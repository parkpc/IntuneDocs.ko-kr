---
# required metadata

title: 향후 예정 사항 | Microsoft Intune
description:
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 05/03/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d

# optional metadata

#ROBOTS:
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

Intune에 대해 다음 변경 사항을 개발 중입니다. 이 모든 기능이 하이브리드 고객 배포(Intune과 Configuration Manager )용으로 지원될 예정입니다. 새로운 하이브리드 기능에 대한 자세한 내용은 [hybrid What’s New page](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx)(하이브리드 새로운 기능 페이지)를 참조하세요..

## 메시지 센터 등록
Intune을 [Office 365 관리 포털](https://portal.office.com/)로 마이그레이션하는 작업의 일환으로, 메시지 센터를 이용하여 새로운 기능 및 기타 알림을 전달하기 시작하려고 합니다.  또한, 함께 사용되는 Office 365 관리 모바일 앱을 설치하면, 휴대폰에서 알림을 수신하고 사용자 또는 메일 그룹을 대상으로 모든 메시지를 손쉽게 전달할 수 있습니다.<br>  
Intune의 새롭고 향상된 기능에 대한 정보를 포함하고 업데이트가 완료되면 알리기 위해서, 5월 릴리스부터 메시지 센터를 사용하기 시작할 예정입니다.  [Office 365 관리 포털](https://portal.office.com/)에 로그인하고 왼쪽 탐색 창에서 **메시지 센터** 옵션을 선택하여 메시지 센터를 확인하세요.
<!---TFS 1242782--->


## 앱 관리
- **브라우저에 대한 조건부 액세스.** 정책을 준수하고 관리되는 iOS 및 Android 장치에서만 액세스할 수 있도록, Exchange Online 및 SharePoint Online에 대한 조건부 액세스 정책을 설정할 수 있게 됩니다. iOS 및 Android 장치를 사용하여 Outlook Web Access(OWA) 및 SharePoint 사이트에 로그인하려는 최종 사용자에게는 Intune을 사용하여 장치를 등록하라는 메시지는 물론 로그인을 완료하기 전에 비호환 문제가 있으면 수정하라는 메시지를 표시하게 됩니다.
<!---TFS 1175844--->

- **MAM SDK: PIN 길이 구성 지원.** 장치 PIN과 유사하게 MAM 앱에 대한 PIN의 길이를 지정할 수 있게 됩니다. 이렇게 하려면, 여러분이 설정하는 새로운 제한 사항을 최종 사용자가 준수해야 합니다. 좀 더 길어진 입력을 설명하기 위해 약간 수정된 PIN 화면이 표시됩니다.
<!--- TFS 1104753--->

- **Outlook 연락처 동기화를 방지하기 위한 MAM 컨트롤(iOS).** 장치 등록 없이 새 설정을 모바일 응용 프로그램 관리에 사용할 수 있습니다. 이 설정을 사용하면 Intune 관리자는 응용 프로그램이 iOS 장치의 기본 주소록과 연락처를 동기화는 것을 막을 수 있습니다. 이 설정을 사용하는 경우 앱에서 연락처를 기본 주소록에 더 이상 저장할 수 없게 됩니다. 이 설정을 사용하지 않는 경우 앱에서 연락처를 기본 주소록에 저장할 수 있게 됩니다. Intune 관리자가 장치를 선택적으로 초기화하는 경우, 기본 주소록에 이미 저장되어 있는 모든 연락처가 제거됩니다. 이 새로운 설정은 iOS 장치의 Outlook 응용 프로그램에서 현재 지원됩니다.
<!---TFS item 1276166--->

- **Android용 비즈니스용 Skype.** Intune 관리자는 등록 정책 없이 MAM을 통해 비즈니스용 Skype를 관리할 수 있습니다.  사용자가 로그인하면, MAM 정책이 적용됩니다.
<!--- TFS item 1248444 --->

- **iOS용 비즈니스용 Skype.** Intune 관리자는 등록 정책 없이 MAM을 통해 비즈니스용 Skype를 관리할 수 있습니다.  사용자가 로그인하면, MAM 정책이 적용됩니다.
<!--- TFS item 1248443 --->

### Xamarin 지원
Microsoft Intune 앱 SDK는 다음 시나리오에서 Xamarin 앱을 지원합니다.

- Intune SDK를 사용하여 기존 LOB(기간 업무) 앱의 코드를 수정하거나 새 앱을 작성. [Microsoft Intune Github](https://github.com/msintuneappsdk) 페이지에서 플러그 인을 확보할 수 있습니다.
- Intune 앱 래핑 도구를 사용하여 기존 LOB(기간 업무) 앱에 MAM 지원을 추가.

사용할 방법을 선택하는 데 도움이 필요하면 [Microsoft Intune으로 모바일 응용 프로그램 관리용 앱을 준비하는 방법 결정](https://docs.microsoft.com/en-us/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune)을 참조하세요..
<!--- TFS 1061478 & TFS 1152340--->


## 장치 관리
- **Windows PC에 대한 원격 지원 세션** Windows 데스크톱 에이전트 관리 PC에 대한 TeamViewer 통합을 통해, 최종 사용자 지원팀 부서를 도와 Windows 데스크톱 에이전트 관리 컴퓨터에 원격 지원 세션을 연결할 수 있습니다. 여기에는 Windows 7, 8, 8.1 및 Windows 10이 포함됩니다.
<!--- TFS 1284856--->


<!--- TFS item 1274326 --->

## 액세스 제어
* **비즈니스용 Skype Online에서 조건부 액세스를 지원합니다.** Intune 관리자는 정책을 준수하고 관리되는 iOS 및 Android 장치에서만 액세스할 수 있도록, 비즈니스용 Skype Online에 대한 조건부 액세스 정책을 설정할 수 있게 됩니다. iOS 및 Android에서 비즈니스용 Skype 모바일 앱에 로그인하려고 하는 최종 사용자에게 Intune에 등록하고 로그인을 완료하기 전에 모든 비호환성 문제를 해결해야 한다는 메시지가 표시됩니다.
<!---TFS item 1254499--->

## 회사 포털
* **장치 식별 배너를 통해 최종 사용자에게 더 많은 정보를 제공합니다.** 최종 사용자가 회사 포털 웹 사이트를 사용하면 자신이 선택한 장치를 손쉽게 식별할 수 있게 됩니다. 잘못된 장치가 선택되면, 홈 페이지 배너의 “Tap here”(여기를 탭하세요) 링크를 탭하여 올바른 장치를 선택할 수 있게 됩니다.
<!--- TFS 1231157--->

* **Windows 앱 패키지는 회사 포털에서 직접 사용할 수 있습니다.** 이제 Windows 8, Windows 8.1, Windows RT PC 사용자가 회사 포털 웹 사이트에서 직접 Windows 앱 패키지(.appx 확장명 포함)를 설치할 수 있습니다. 이전에는, Intune 관리자가 배포하거나 사용자가 앱을 설치할 장치에 회사 포털 앱을 설치해야 했습니다.
<!--- TFS item 1082481 --->

* **사용자는 회사 포털에서 장치를 원격으로 잠글 수 있습니다.** 새 원격 잠금 옵션이 회사 포털 웹 사이트에 추가되어 사용자가 장치를 분실하거나 도난당한 경우 포털에서 자신의 장치를 원격으로 잠글 수 있습니다. 다음 표에는 Intune 및 Configuration Manager 포함 Intune의 원격 잠금에 대한 플랫폼별 지원이 나열되어 있습니다.
<!--- TFS item 1195661 --->

|플랫폼  |지원 세부 정보|
|---------|---------|
|iOS | 지원됨|
|Android | 지원됨|
|Windows Phone 8.1 | 지원됨|
|Windows 10 Mobile | 휴대폰에 암호가 설정된 경우에만 지원됨|
|PC(Windows 8.0 이전 버전) | 지원되지 않음|
|PC(Windows 8.1) | 지원되지 않음|
|Windows Phone 8.0 | 지원 안 됨|
|Windows 10 Desktop | 지원되지 않음|

## 서비스 중단
* **사용자 지정 그룹을 알림 규칙의 대상으로 지정하는 기능 제거.** 2016년 6월 초부터, 알림 규칙 만들기 마법사를 사용하여 사용자가 만든 그룹을 알림 규칙의 대상으로 지정할 수 없게 됩니다.

    현재는, Microsoft Intune 관리 콘솔의 사용자가 만든 그룹을 대상으로 지정하려면, **관리** > **알림 규칙** > **새 규칙 만들기**를 선택합니다. 알림 규칙 만들기 마법사의 2단계에서, 규칙의 대상이 되는 장치 그룹을 선택해야 합니다. 이 단계 즉, **장치 그룹 선택**은 Intune 콘솔에 사용되지 않을 예정입니다.

    **장치 그룹 선택**은 Intune의 6월 1606 릴리스 후에는 더 이상 지원되지 않습니다. 하지만, 2016년 8월까지는 이 옵션을 계속 볼 수 있습니다. 8월이 지나면, 두 달에 걸쳐 새로운 환경으로 테넌트를 단계적으로 변경하기 시작할 예정입니다. 2016년 10월까지, 기존의 모든 고객은 새로운 환경으로 전환됩니다. 새 환경으로 마이그레이션이 완료된 후에는, 특정 그룹을 알림 규칙의 대상으로 지정하는 옵션이 더 이상 제공되지 않을 것입니다.
<!---   TFS 1278864--->







### 참고 항목
최근 개발 작업에 대한 자세한 내용은 [What’s New in Microsoft Intune](whats-new-in-microsoft-intune.md)(Microsoft Intune의 새로운 기능)을 참조하세요.


<!--HONumber=May16_HO1-->


