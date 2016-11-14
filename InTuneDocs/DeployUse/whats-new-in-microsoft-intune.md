---
<<<<<<< HEAD
redirect_url: https://docs.microsoft.com/intune/whats-new/whats-new-in-microsoft-intune
||||||| merged common ancestors
title: "새로운 기능 | Microsoft Intune"
description: "이번 달의 새로운 소식과 Microsoft Intune의 이전 릴리스 확인"
keywords: 
author: Lindavr
manager: angrobe
ms.date: 08/10/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: mamoriss
ms.suite: ems
=======
title: "새로운 기능 | Microsoft Intune"
description: "이번 달의 새로운 소식과 Microsoft Intune의 이전 릴리스 확인"
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 09/26/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: mamoriss
ms.suite: ems
>>>>>>> 359d4f486355df1be118d8fdb698694ae632df85
translationtype: Human Translation
<<<<<<< HEAD
ms.sourcegitcommit: 4b819b00273808296d3088413b70e4ce087efcf8
ms.openlocfilehash: 0ccbae6fbff7fab356ad5ecd2ab2f2b8b18db692
||||||| merged common ancestors
ms.sourcegitcommit: 500cc93b595e04cea987bda699abf94ae010443a
ms.openlocfilehash: 1f6a4b3988dbebce23a59b4ba14c79cd28cf6882


---

# Microsoft Intune의 새로운 기능
이번 Microsoft Intune 릴리스의 새로운 기능에 대해 알아봅니다. 이전 릴리스에 대한 정보뿐만 아니라 계획을 수립해야 하는 예정된 변경에 대해서도 알아볼 수 있습니다.

최종적으로는 이 모든 기능이 하이브리드 고객 배포(Intune과 Configuration Manager )용으로 지원될 예정입니다. 새로운 하이브리드 기능에 대한 자세한 내용은 [hybrid What’s New page](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx)(하이브리드 새로운 기능 페이지)를 참조하세요.
<!---@Barry, the above blurb stays in each version, but make sure Tyler signs off each time. Also, remember to set the ms.date in the metadata to the sprint release. --->

>[!IMPORTANT] 
>블로그 게시물 - Microsoft Intune을 사용하여 모바일 장치를 최신 상태로 유지<br>
>최근 iOS 장치에서 발생한 “Trident” 맬웨어 공격과 관련하여 Microsoft는 Intune을 활용해 장치를 안전한 최신 상태로 유지할 수 있는 다양한 방법을 파악할 수 있도록 새로운 블로그 게시물인 [Microsoft Intune을 사용하여 모바일 장치를 최신 상태로 유지](https://blogs.technet.microsoft.com/enterprisemobility/2016/08/26/ensuring-mobile-devices-are-up-to-date-using-microsoft-intune/)를 게시했습니다.


## 2016년 8월
## 앱 관리
<!---@Barry, I created the buckets of App management, Device management, etc but am not tied to them. Just wanted to break up and organize the feature list. If you're going to take over the Company Portal section, please talk to Stacie about how she's been organizing it. --->

### iOS 9.3에 대해 숨겨진/표시된 앱
iOS 9.3 이상을 실행하는 감독된 장치의 경우 iOS 일반 구성 정책에서 숨겨진/표시된 앱 목록을 사용하여 다음을 수행할 수 있습니다.
- 사용자로부터 숨길 앱 목록을 지정합니다. 사용자는 이러한 앱을 보거나 시작할 수 없습니다.
- 사용자가 보고 시작할 수 있는 앱 목록을 지정합니다. 다른 앱은 보거나 시작할 수 없습니다.

지정할 수 있는 앱에는 사용자가 배포한 앱과 메시지 및 메모와 같은 기본 제공 iOS 앱이 모두 포함됩니다. 자세한 내용은 [Microsoft Intune의 iOS 정책 설정]( https://docs.microsoft.com/intune/deploy-use/ios-policy-settings-in-microsoft-intune)을 참조하세요.
<!---TFS 1279009 checked--->
### Samsung KNOX 장치에 대해 허용된/차단된 앱 정책
이제 Samsung KNOX 장치용 사용자 지정 정책을 구성하여 다음 중 하나를 만들 수 있습니다.
- 장치에서 실행되지 않도록 차단할 앱 목록. 앱이 설치되었더라도 차단 목록에 정의된 앱은 장치에서 활성화할 수 없습니다.
- 장치 사용자가 Google Play 스토어에서 설치할 수 있도록 허용된 앱 목록. 다른 앱은 스토어에서 설치할 수 없습니다.

이러한 설정은 Samsung KNOX를 실행하는 장치에서만 사용할 수 있습니다.
자세한 내용은 [사용자 지정 정책을 사용하여 Samsung KNOX 장치에 대해 앱을 허용하거나 차단]( custom-policy-to-allow-and-block-samsung-knox-apps.md)을 참조하세요.
<!---TFS 1311629 checked --->
### MAM(모바일 응용 프로그램 관리) 정책과 호환되는 새로운 앱
[iOS](https://itunes.apple.com/app/yammer/id289559439?mt=8) 및 [Android](https://play.google.com/store/apps/details?id=com.yammer.v1)용 Yammer 앱은 이제 장치 등록 여부에 상관없이 [Intune MAM(모바일 응용 프로그램 관리) 정책](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)과 호환됩니다.

MAM과 호환되는 앱의 전체 목록은 [Microsoft Intune application partners](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners)(Microsoft Intune 응용 프로그램 파트너) 사이트를 참조하세요.
<!--- TFS 1252335 & 1252336 checked--->


<!--- I started putting TFS numbers in the What's Coming topic and found it helpful when updating the What's New. Up to you if you want to continue. --->

### Intune 뷰어 앱
2016년 8월부터 새 RMS 공유 앱의 릴리스에서 다음 Intune 뷰어 앱을 제거합니다.
- Intune AV 뷰어
- Intune PDF 뷰어
- Google Play의 Android용 Intune 이미지 뷰어

Intune 뷰어 앱을 사용하는 대신 [새로운 Android용 Microsoft Rights Management 공유 앱(RMS 공유)](https://docs.microsoft.com/en-us/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app)을 사용하는 것이 좋습니다. 이 앱을 통해 세 개의 별도 앱이 아니라 하나의 앱을 배포하여 Android 장치에서 회사 파일을 안전하게 볼 수 있습니다. Intune 뷰어 앱이 더 이상 지원되지 않으면 Google 스토어에서 제거되며 향후 사용할 수 없게 됩니다.

## 장치 관리
### Android 7.0 지원
Intune에서는 모바일 장치용으로 곧 출시 예정인 Android 7.0 운영 체제에 대해 “Day 0” 지원을 제공합니다.
<!---TFS 1262053--->
### Android 7.0 장치에서 Google의 원격 암호 재설정 기능 제거
Google에서 IT 관리자와 최종 사용자가 Android 7.0 장치의 암호를 원격으로 다시 설정하는 기능을 제거할 예정입니다. 이전에는 IT 관리자가 원격으로 사용자의 암호를 다시 설정하고, 최종 사용자가 회사 포털 웹 사이트에서 자신의 암호를 다시 설정할 수 있었습니다.



## 회사 포털 업데이트
### 회사 포털 웹 사이트
- **회사 포털에서 Microsoft로 피드백 링크** <br/>
회사 포털 웹 사이트에서 최종 사용자가 페이지 맨 아래에 새로 생긴 “피드백" 링크를 탭하여 사이트 사용 경험에 대해 피드백을 Microsoft에 보낼 수 있습니다. 익명으로 수집된 피드백은 Microsoft가 사용자를 위해 회사 포털 웹 사이트를 개선하는 데 도움이 됩니다.
<!--- TFS 1313657 checked--->

### iOS
- **최소 iOS 관리 브라우저 버전이 8.0으로 업데이트됨**<br/>
iOS 8.0 이상이 실행되는 장치를 지원하도록 iOS용 Microsoft Intune 관리 브라우저 앱이 업데이트되었습니다. iOS 7.1 장치는 기존의 관리 브라우저 앱을 사용할 수 있지만 새로운 관리 브라우저 기능을 액세스하고 완전히 사용하기 위해서는 iOS 8.0 이상으로 업데이트하는 것이 좋습니다.  
<!---TFS 1313253 checked--->

## 향후 예정 사항
### 2016년 9월부터 Intune 그룹에서 Azure Active Directory 그룹으로 전환
Intune은 Intune에서 AAD(Azure Active Directory) 보안 그룹을 사용자 및 장치 그룹으로 사용하는 새로운 그룹 관리 환경을 만들고 있습니다. 이러한 그룹은 **새 Azure 기반 Intune 관리 포털을 도입할 때 **모든 그룹 관리, 정책 배포 및 프로필 배포에 사용됩니다.

이 새로운 환경은 서비스 간에 그룹을 복제할 필요를 없애주고 **몇 가지 새로운 AADP(Azure Active Directory Premium) 그룹 기능에 대한 액세스를 허용하고** PowerShell 및 Graph를 사용하여 확장성을 제공합니다. 또한 엔터프라이즈 이동성 관리에서 그룹 관리 환경을 통합합니다.

보안 그룹으로의 이동을 설정하기 위해 **현재 관리 콘솔**의 환경이 약간 수정될 예정입니다. **이러한 변경 내용 및 AAD 보안 그룹의 사용 방식은 Intune 설명서에 기록됩니다**.

Intune을 처음 사용하는 고객은 **현재 테넌트보다 먼저 일부 보안 그룹의 변경**을 보게 될 것입니다.

그룹 관리에 대한 변경 내용 외에 **다음과 같은 기능은 더 이상 사용되지 않게 됩니다**.
- 새 그룹을 만드는 동안 구성원 또는 그룹 제외
- **그룹 해제된 사용자** 및 **그룹 해제된 장치** 그룹
- 서비스 관리자 역할의 **그룹 관리**
- 알림 규칙에 대한 사용자 지정 그룹 기반 경고
- 보고서에서 그룹으로 피벗
<!--- TFS 1295329--->

### Android용 회사 포털에 '알림' 추가
9월에는 홈페이지에 새 **알림** 아이콘을 추가하는 업데이트를 Android용 회사 포털에 릴리스할 예정입니다. 이 아이콘을 누르면 호환되지 않는 장치, 등록 업데이트 및 등록 활성화와 같이 회사 포털 앱에서 주의가 필요한 모든 항목을 최종 사용자에게 표시하는 **알림** 페이지로 이동됩니다. IOS 회사 포털 앱을 사용하는 경우에는 이미 알림을 제공받았을 것입니다. **알림** 페이지가 도입되면서 장치가 등록된 동안 Android용 회사 포털을 시작하거나 다시 시작할 때마다 **회사 액세스 설정** 페이지가 항상 표시되지는 않습니다. 많은 고객 여러분이 최종 사용자 지침을 만드는 데 도움을 주신 점을 알고 있습니다. 지침/스크린샷을 업데이트해야 할 때 미리 알려 주시는 점에 감사드립니다. 예정된 변경 내용을 환경에 반영하려면 설명서를 업데이트하세요. 업데이트된 스크린샷을 보려면 https://aka.ms/androidcpupdate로 이동하세요.  

### iOS 최종 사용자가 앱을 받는 방법에 대한 개선 사항
다음 변경 내용은 9월 iOS용 회사 포털 앱의 앱 타일에 적용되어, 사용를 회사 포털 웹 사이트라는 하나의 위치에서 모든 앱에 대한 다른 보기로 가리킵니다. 현재 Apple 제한 사항은 기간 업무 및 관리되는 App Store 앱이 회사 포털 앱에 나열되는 것을 금지하므로 사용자가 자신의 앱을 모두 찾으려면 여러 보기를 방문해야 합니다.

- 현재 **회사 앱** 타일은 회사 포털 웹 사이트의 모두 탭에 있는 모든 앱 목록을 가리키고 있으며, 계속해서 같은 방식으로 작동합니다. 타일 이름이 **모든 앱**으로 변경됩니다.
- **다른 앱** 타일은 현재 Apple이 표시를 허용하는 모든 회사 포털 앱이 나열된 회사 포털 앱 내 보기를 가리키고 있습니다. 타일 이름이 **추천 앱**으로 변경되며 타일을 탭하면 사용자는 회사 포털 웹 사이트의 추천 탭으로 이동하게 됩니다.
-  **카테고리** 타일은 앱의 범주를 나열하는 회사 포털 앱 내 보기를 현재 가리키고 있습니다. 타일 이름은 변경되지 않지만 이제 회사 포털 웹 사이트의 범주 탭을 가리키게 됩니다. 업데이트된 스크린샷은 [여기](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186)에서 볼 수 있습니다.
<!---TFS 1317133--->

### 클라우드 로드맵
[클라우드 플랫폼 로드맵](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)에서 Intune에 대해 예정된 개발 정보를 지속적으로 받습니다.

### 서비스 중단
<!---@Barry, we started listing service deprecations earlier this summer. --->
- **iOS 회사 포털 앱에 대한 지원의 변경 내용**<br/>
9월에 iOS용 Microsoft Intune 회사 포털 앱의 모든 사용자는 최신 버전을 사용해야 합니다. 새 사용자는 최신 버전만 다운로드할 수 있고 현재 사용자는 최신 버전으로 업데이트해야 합니다. 최신 버전을 사용하려면 iOS 8.0 이상이 필요하므로 이전 iOS 버전을 실행하는 장치는 장치를 iOS 8.0 이상으로 업데이트한 다음 회사 포털 앱을 최신 버전으로 업데이트할 때까지 회사 포털을 사용하거나 등록할 수 없습니다. iOS 8.0 이전 버전을 실행하는 등록된 장치는 Intune 관리자 콘솔에서 계속 관리되고 표시됩니다.  

- **최소 iOS 관리 브라우저 버전이 8.0으로 업데이트됨**<br/>
8월에 Intune은 iOS 8.0 이상이 실행되는 장치만 지원하는 업데이트된 iOS용 Microsoft Intune 관리 브라우저 앱을 릴리스할 예정입니다. IOS 7.1 장치는 기존의 관리 브라우저 앱을 사용할 수 있지만 새로운 관리 브라우저 기능을 액세스하고 완전히 사용하기 위해서는 iOS 8.0 이상으로 업데이트하는 것이 좋습니다.  
<!---TFS 1313253--->

- **Windows 8 및 Windows Phone 8용 회사 포털 앱이 사용되지 않음** <br/>
2016년 10월부터 Microsoft Intune에서는 Windows 8 및 Windows Phone 8 회사 포털 앱을 더 이상 지원하지 않습니다. 또한 Windows Phone 8 플랫폼도 지원되지 않습니다. 따라서 Windows Phone 8 장치를 등록하거나 업데이트할 수 없게 됩니다. 이미 등록된 Windows Phone 8 및 Windows 8 장치는 계속 관리할 수 있습니다. 서비스 중단 없이 이러한 장치에 앱을 계속 배포하려면 Windows Phone 8 및 Windows 8 장치를 Windows 8.1 및 Windows Phone 8.1로 업데이트하고 해당하는 Windows 8.1 및 Windows Phone 8.1 회사 포털 앱을 사용하세요.
<!---TFS 1255391--->

<!--- - **Custom Group Targeting of Notification Rules Removal.**<br/>
Intune notification rules define who an email alert will be sent to from Intune. Currently, you can configure notification rules to send emails to all users of devices in an Intune device group that you created. From around June 1st 2016 moving forward, targeting user-created groups will no longer be supported.

    Today, to target a notification rule to a group you created from the Microsoft Intune administration console, you would take the following steps:

    In the **Admin** workspace, click **Notification Rules** > **Create New Rule**

    In step two of the Create Notification Rule Wizard, select the device groups which the rule will target. This step, “select device groups”, is being removed from the Intune Console.

    The preliminary timeline for this change is as follows:
    - In August, 2016, new tenants will not see step two of the Create Notification Rule Wizard. Exiting tenants are unaffected.
    - Around September, 2016, some existing tenants will not see the “select device groups” in the wizard.
    - Around November, 2016, we expect that all tenants will not see the “select device groups” in the wizard.

--->



## 이전 Intune 릴리스
지난 6개월간 Intune에 릴리스된 목록을 보려면 [이전 Intune 릴리스](previous-intune-releases.md) 문서를 참조하세요.

### 참고 항목
* [Microsoft Intune 블로그](http://go.microsoft.com/fwlink/?LinkID=273882)
* [클라우드 플랫폼 로드맵](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
=======
ms.sourcegitcommit: ecf43b38e9593375981770583220d4ce2dfd709f
ms.openlocfilehash: 32610d4138fba82e034cc7dadccc09e0a6d31cd3


---
# Microsoft Intune의 새로운 기능 - 9월
이번 Microsoft Intune 릴리스의 새로운 기능에 대해 알아봅니다. 이전 릴리스에 대한 정보뿐만 아니라 계획을 수립해야 하는 예정된 변경에 대해서도 알아볼 수 있습니다.

최종적으로는 이 모든 기능이 하이브리드 고객 배포(Intune과 Configuration Manager )용으로 지원될 예정입니다. 새로운 하이브리드 기능에 대한 자세한 내용은 [hybrid What’s New page](https://technet.microsoft.com/library/mt718155.aspx)(하이브리드 새로운 기능 페이지)를 참조하세요.
<!---@Barry, the above blurb stays in each version, but make sure Tyler signs off each time. Also, remember to set the ms.date in the metadata to the sprint release. --->

>[!IMPORTANT]
>블로그 게시물 - Microsoft Intune을 사용하여 모바일 장치를 최신 상태로 유지<br>
>최근 iOS 장치에서 발생한 “Trident” 공격과 관련하여 Microsoft는 Intune을 활용해 장치를 안전한 최신 상태로 유지할 수 있는 다양한 방법을 파악할 수 있도록 새로운 블로그 게시물 [Ensuring mobile devices are up to date using Microsoft Intune](https://blogs.technet.microsoft.com/enterprisemobility/2016/08/26/ensuring-mobile-devices-are-up-to-date-using-microsoft-intune/)(Microsoft Intune을 사용하여 모바일 장치를 최신 상태로 유지)을 게시했습니다.

## 새로운 기능, 공지 사항 및 정보
* [Windows 조건부 액세스](#windows-conditional-access)
* [iOS 10 지원](#ios-10-support)
* [앱 래핑 도구는 Android 및 iOS에 대한 장치 등록 없이 MAM 지원](#app-wrapping-tool-supports-mam-without-device-enrollment-for-android-and-ios)
* [9월에 Intune 그룹에서 Azure Active Directory로 전환 시작](#intune-groups-begin-transitioning-to-azure-active-directory-in-september)
* [Android 장치를 보호하기 위한 Lookout 통합](#lookout-integration-to-protect-android-devices)
* [Android, iOS 및 Windows용 회사 포털 업데이트](#company-portal-updates)
* [Intune 용어](#intune-glossary)
* [향후 예정 사항](#whats-coming)

## Windows 조건부 액세스
이제 Intune 관리 콘솔을 통해 Windows PC가 Exchange Online 및 SharePoint Online에 액세스하지 못하도록 하는 조건부 액세스 정책을 만들 수 있습니다. 또한 Office 데스크톱 및 유니버설 응용 프로그램에 대한 액세스를 차단하기 위한 조건부 액세스 정책을 만들 수 있습니다. 

## iOS 10 지원
기존 Intune MDM 및 MAM 시나리오는 iOS 10과 호환됩니다. 팁은 [Intune Support Team Blog](https://blogs.technet.microsoft.com/intunesupport/2016/09/13/support-tip-intune-support-for-ios-10/)(Intune 지원 팀 블로그)를 참조하세요.

## 앱 래핑 도구는 Android 및 iOS에 대한 장치 등록 없이 MAM 지원
Intune 앱 래핑 도구는 iOS 및 Android용 LOB(기간 업무) 앱에서 Intune MAM을 사용하도록 설정하는 데 사용하는 명령줄 도구입니다. Intune을 통해 배포된 MAM 정책을 앱에서 적용할 수 있도록 앱에 Intune MAM SDK를 통합하는 가장 간단한 방법입니다. MAM 정책을 사용하여 다음을 수행할 수 있습니다.

1. 응용 프로그램의 데이터를 암호화합니다.
2. 정보 근로자가 앱을 시작할 때 PIN을 입력하도록 요구합니다.
3. 앱에서 다른 관리되는 앱으로만 데이터를 전송하도록 허용합니다.
4. 앱에서 데이터를 Android, iTunes 및 iCloud에 백업하지 못하게 합니다.
5. 다른 관리되는 앱으로 또는 이 앱에서 잘라내기, 복사 및 붙여넣기만 허용합니다.

업데이트된 Intune 앱 래핑 도구의 공개 미리 보기에서는 이제 iOS 및 Android의 내부 LOB 앱에서 장치 등록 없이도 MAM를 지원합니다. 즉, 최종 사용자가 장치를 Intune에 등록하지 않고도 MAM 지원 LOB 앱을 사용할 수 있습니다.

누구나 공개 미리 보기 소프트웨어를 테스트하고 msintuneappsdk의 GitHub에 있는 유용한 설명서를 읽을 수 있습니다.

http://www.github.com/msintuneappsdk/intune-app-wrapper-ios-preview

http://www.github.com/msintuneappsdk/intune-app-wrapper-android-preview

Android 및 iOS용 Microsoft Intune 앱 래퍼 시험판을 설치하고 사용하기 전에 다음을 수행해야 합니다.

* Android 및 iOS용 Microsoft Intune 앱 래퍼 시험판에 대한 Microsoft 사용 조건 검토
* 기록을 위해 사용 조건의 사본을 인쇄하여 보관. Android용 Microsoft Intune 앱 래핑 도구 시험판을 다운로드하고 사용하면 이러한 사용 조건에 동의하는 것입니다. 동의하지 않는 경우 소프트웨어를 사용하지 마세요.
<!---TFS 1235607--->

## 9월에 Intune 그룹에서 Azure Active Directory로 전환 시작
일부 새 Intune 계정은 Intune 사용자 그룹이 아닌 Azure Active Directory 보안 그룹을 사용합니다. Intune 포털 그룹 페이지에 Azure 관리 포털로 연결되는 링크가 있으면 보안 그룹을 사용 중인 것입니다.

## Android 장치를 보호하기 위한 Lookout 통합
Microsoft는 Android 장치에서 맬웨어, 위험한 앱 등을 감지하여 장치를 보호하기 위해 Lookout의 모바일 위협 방지 솔루션과 통합합니다. Lookout의 솔루션을 통해 위협 수준을 결정할 수 있고, 이 수준은 구성이 가능합니다. Lookout의 위협 평가를 기준으로 장치 준수를 결정하는 준수 정책 규칙을 Intune에서 만들 수 있습니다. 조건부 액세스 정책을 사용하여 장치 준수 상태에 따라 회사 리소스에 대한 액세스를 허용하거나 차단할 수 있습니다.

비준수 장치의 최종 사용자는 등록하라는 메시지가 표시되며 Android 장치에서 Lookout for Work 응용 프로그램을 설치하고, 앱을 활성화하고, Lookout for Work 응용 프로그램에 보고된 위협을 해결해야만 액세스 권한을 얻게 됩니다. 자세한 내용은 [Restrict access based on device, network, and application risk](restrict-access-based-on-device-network-app-risk.md)(장치, 네트워크 및 응용 프로그램 위험에 따라 액세스 제한)를 참조하세요.


## 회사 포털 업데이트

### Android

**Android용 회사 포털에 “알림” 추가**<br/>
홈페이지의 Android용 회사 포털에 새 알림 아이콘이 추가되었습니다. 이 아이콘을 누르면 호환되지 않는 장치, 등록 업데이트 및 등록 활성화와 같이 회사 포털 앱에서 주의가 필요한 모든 항목을 최종 사용자에게 표시하는 알림 페이지로 이동됩니다. iOS 회사 포털 앱에 이 알림 환경이 이미 있습니다. 새 알림 페이지가 있으면 장치가 등록된 동안 회사 포털을 시작하거나 다시 시작할 때마다 회사 액세스 설정 페이지가 항상 표시되지는 않습니다. 최종 사용자 지침을 만들 경우 이 변경 내용을 반영하도록 문서를 업데이트할 수 있습니다. 업데이트된 스크린샷은 [여기](https://aka.ms/androidcpupdate)에서 볼 수 있습니다.  
<!---TFS 1095560--->

**Android용 회사 포털에서 사용자 의견 제공**</br>
Android용 회사 포털의 메뉴에 새 항목이 추가되었습니다. **도움말 및 피드백** 세 가지 작업이 표시됩니다.
* **도움말 보기**를 사용하여 IT 부서에 회사 포털에 대한 문제를 보고할 수 있습니다. IT에서는 사용자 메일 클라이언트를 사용하여 메일을 작성하고 이 메일에 회사 포털 로그를 첨부합니다. **도움말 보기**가 **설정** 페이지의 **데이터 보내기** 기능을 대체합니다.
* **사용자 의견 제공**을 사용하여 회사 포털 팀에 사용자 의견을 제공할 수 있습니다.
* **앱 평가**를 사용하여 Google Play에서 회사 포털 앱 평가 또는 리뷰를 남길 수 있습니다.

### iOS
**iOS 회사 포털 앱에 대한 지원의 변경 내용**<br/>
이제 iOS용 Microsoft Intune 회사 포털 앱의 모든 사용자는 최신 버전을 사용해야 합니다. 새 사용자는 최신 버전만 다운로드할 수 있고 현재 사용자는 최신 버전으로 업데이트해야 합니다. 최신 버전을 사용하려면 iOS 8.0 이상이 필요하므로 이전 iOS 버전을 실행하는 장치는 장치를 iOS 8.0 이상으로 업데이트한 다음 회사 포털 앱을 최신 버전으로 업데이트할 때까지 회사 포털을 사용하거나 등록할 수 없습니다. iOS 8.0 이전 버전을 실행하는 등록된 장치는 Intune 관리자 콘솔에서 계속 관리되고 표시됩니다.
<!---TFS 1283165--->

**iOS 최종 사용자가 앱을 받는 방법에 대한 개선 사항**<br/>
iOS용 회사 포털 앱의 앱 타일이 다음과 같이 변경되어 사용자의 모든 앱에 대해 회사 포털 웹 사이트라는 하나의 위치에 있는 다른 보기를 가리킵니다. Apple 제한 사항에 따라 기간 업무 및 관리되는 앱 스토어 앱이 회사 포털 앱에 나열되지 못하므로 사용자는 앱을 모두 찾으려면 여러 보기를 방문해야 합니다.

- **회사 앱** 타일은 이전에 회사 포털 웹 사이트의 모두 탭에 있는 모든 앱 목록을 가리켰는데, 계속해서 같은 방식으로 작동합니다. 타일 이름은 **모든 앱**으로 변경되었습니다.
- **기타 앱** 타일은 기존에는 Apple이 회사 포털 앱에서 표시하도록 허용하는 모든 앱을 나열하는 회사 포털 앱 내의 보기를 가리켰습니다. 타일 이름이 **추천 앱**으로 변경되었으며 타일을 탭하면 회사 포털 웹 사이트의 추천 탭으로 이동됩니다.
-  **카테고리** 타일은 이전에 앱의 범주를 나열하는 회사 포털 앱 내 보기를 가리켰습니다. 타일 이름이 변경되지 않았지만 이제는 회사 포털 웹 사이트의 범주 탭을 가리킵니다.
업데이트된 스크린샷은 [여기](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186)에서 볼 수 있습니다.
<!---TFS 1317133--->

**IT Pro이 해당 앱 요구 사항을 설정하면 iOS Managed Browser 앱을 설치하라는 메시지가 나타납니다.**<br/>
웹 클립을 Managed Browser에서만 열 수 있도록 구성했지만 장치에 Managed Browser가 설치되어 있지 않은 경우 장치의 회사 포털 앱에서는 웹 클립을 설치하기 전에 먼저 Managed Browser를 설치하라는 메시지를 표시합니다.
<!---TFS 1228570--->

### Windows
**Windows Phone 8.1 회사 포털 앱에 추가된 사용자 의견 단추**<br/>
최종 사용자는 Windows Phone 8.1 회사 포털 앱의 새 “사용자 의견 보내기” 단추를 사용하여 앱에 대한 사용자 의견을 보낼 수 있습니다. 단추를 찾으려면 회사 포털 앱 화면의 오른쪽 아래에 있는 “세 점” 메뉴를 탭한 다음 **사용자 의견 보내기**를 탭합니다. 익명으로 수집된 피드백은 Microsoft가 사용자를 위해 회사 포털 앱 환경을 개선하는 데 도움이 됩니다.
<!---TFS 1317806--->

## Intune 용어</br>
Intune 제품에 사용되는 일부 용어를 이해하는 데 도움이 되도록 라이브러리에 새 [용어 항목](https://docs.microsoft.com/intune/understand-explore/intune-glossary)을 추가했습니다.

----------

## 향후 예정 사항

### Intune 그룹에서 Azure Active Directory 그룹으로의 전환
Intune은 Intune에서 AAD(Azure Active Directory) 보안 그룹을 사용자 및 장치 그룹으로 사용하는 새로운 그룹 관리 환경을 만들고 있습니다. 이러한 그룹은 **새 Azure 기반 Intune 관리 포털을 도입할 때 **모든 그룹 관리, 정책 배포 및 프로필 배포에 사용됩니다.

이 새로운 환경은 서비스 간에 그룹을 복제할 필요를 없애주고 **몇 가지 새로운 AADP(Azure Active Directory Premium) 그룹 기능에 대한 액세스를 허용하고** PowerShell 및 Graph를 사용하여 확장성을 제공합니다. 또한 엔터프라이즈 이동성 관리에서 그룹 관리 환경을 통합합니다.

보안 그룹으로의 이동을 설정하기 위해 **현재 관리 콘솔**의 환경이 약간 수정될 예정입니다. **이러한 변경 내용 및 AAD 보안 그룹의 사용 방식은 Intune 설명서에 기록됩니다**.

Intune을 처음 사용하는 고객은 **현재 테넌트보다 먼저 일부 보안 그룹의 변경**을 보게 될 것입니다.

그룹 관리에 대한 변경 내용 외에 **다음과 같은 기능은 더 이상 사용되지 않게 됩니다**.
- 새 그룹을 만드는 동안 구성원 또는 그룹 제외
- **그룹 해제된 사용자** 및 **그룹 해제된 장치** 그룹
- 서비스 관리자 역할의 **그룹 관리**
- 알림 규칙에 대한 사용자 지정 그룹 기반 경고
- 보고서에서 그룹으로 피벗
<!--- TFS 1295329--->

### Exchange Online 및 SharePoint Online에 대한 새로운 조건부 액세스 앱 정책
Exchange Online 및 SharePoint Online에 대한 액세스를 제한하여 Outlook, Word, Excel 및 OneDrive와 같은 Office 모바일 앱에서만 액세스할 수 있도록 할 수 있습니다. 이 새로운 기능은 Intune MAM(모바일 앱 관리) 정책과 완벽히 쌍을 이루어 기본 제공 메일 클라이언트나 Intune MAM 정책을 사용하여 구성되지 않은 기타 앱에 대한 액세스를 차단할 수 있습니다. 따라서 사용자는 Intune MAM을 사용하여 보호할 수 있는 앱에서 조직 데이터를 액세스하게 됩니다. Intune 모바일 앱 관리는 Azure portal을 통해 시작할 수 있습니다. "설정" 블레이드에서 새 조건부 액세스 섹션을 찾아보세요.


### 서비스 중단

- **Windows 8 및 Windows Phone 8용 회사 포털 앱이 사용되지 않음** <br/>
2016년 10월부터 Microsoft Intune에서는 Windows 8 및 Windows Phone 8 회사 포털 앱을 더 이상 지원하지 않습니다. 또한 Windows Phone 8 플랫폼도 지원되지 않습니다. 따라서 Windows Phone 8 장치를 등록하거나 업데이트할 수 없게 됩니다. 이미 등록된 Windows Phone 8 및 Windows 8 장치는 계속 관리할 수 있습니다. 서비스 중단 없이 이러한 장치에 앱을 계속 배포하려면 Windows Phone 8 및 Windows 8 장치를 Windows 8.1 및 Windows Phone 8.1로 업데이트하고 해당하는 Windows 8.1 및 Windows Phone 8.1 회사 포털 앱을 사용하세요.

### 참고 항목
* [Microsoft Intune 블로그](http://go.microsoft.com/fwlink/?LinkID=273882)
* [클라우드 플랫폼 로드맵](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [이전 Intune 릴리스](previous-intune-releases.md)
>>>>>>> 359d4f486355df1be118d8fdb698694ae632df85

---


<!--HONumber=Sep16_HO5-->


