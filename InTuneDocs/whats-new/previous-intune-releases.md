---
title: "이전 릴리스 | Microsoft Intune"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 12/05/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 45dad14a-d412-488d-bb1e-ad990ea503df
ROBOTS: noindex,nofollow
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4dab832da4490c3df045d2c627b231028c92b25
ms.openlocfilehash: 3de5e57589a24600301e54a3b60eecb5321ff838


---

# <a name="previous-intune-releases"></a>이전 Intune 릴리스

이 페이지는 [Microsoft Intune의 새로운 기능](whats-new-in-microsoft-intune.md)에서 제공된 공지 사항이 포함되어 있는 목록입니다.

[!INCLUDE[wit_nextref](../includes/whats-new-last-six-months.md)]

## <a name="may-2016"></a>2016 년 5 월
이 모든 기능은 하이브리드 배포에 대해서도 지원됩니다(Configuration Manager with Intune). 새로운 하이브리드 기능에 대한 자세한 내용은 [Hybrid What’s New](https://technet.microsoft.com/en-us/library/mt718155.aspx)(하이브리드의 새로운 기능) 페이지를 참조하세요.

### <a name="documentation"></a>문서
[docs.microsoft.com](https://docs.microsoft.com/en-us/intune)의 미리 보기 버전에 오신 것을 환영합니다!
완전히 새로운 최신 콘텐츠 플랫폼으로, 사용자와 고객이 Intune을 쉽게 이해하고 사용할 수 있도록 설계되었습니다.
새로운 모든 기능에 대한 내용을 보려면 [Introducing docs.microsoft.com](https://docs.microsoft.com/teamblog/introducing-docs-microsoft-com/)(docs.microsoft.com 소개)을 참조하세요.

### <a name="intune-service-health"></a>Intune 서비스 상태
Intune에 대한 서비스 상태 정보는 다른 Microsoft 서비스와 함께 중앙 위치로 이동되었습니다. 이 정보는 이제 [Office 365 관리 포털](https://portal.office.com/Admin/Default.aspx)의 **서비스 상태**에서 찾을 수 있습니다.
자세한 내용은 [이 블로그 게시물](https://blogs.technet.microsoft.com/microsoftintune/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/)을 참조하세요.

### <a name="app-management"></a>앱 관리
- **MAM SDK: PIN 길이 구성 지원.** 장치 PIN과 유사하게 MAM 앱에 대한 PIN의 길이를 지정할 수 있게 됩니다. 이렇게 하려면, 여러분이 설정하는 새로운 제한 사항을 최종 사용자가 준수해야 합니다. 좀 더 길어진 입력을 설명하기 위해 약간 수정된 PIN 화면이 표시됩니다. 자세한 내용은 [MAM policy settings for Android](/intune/deploy-use/android-mam-policy-settings)(Android용 MAM 정책 설정) 및 [MAM policy settings for iOS](/intune/deploy-use/ios-mam-policy-settings)(iOS용 MAM 정책 설정)를 참조하세요.

- **비즈니스용 Skype for iOS 및 Android.** 이제 [등록 정책 없이 MAM](/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune)을 통해 비즈니스용 Skype를 관리할 수 있습니다. 사용자가 로그인하면 MAM 정책이 적용됩니다.

- **MAM 정책을 통해 새로운 앱을 관리할 수 있음.** 이제 Intune에 등록하지 않은 장치에서 Android용 Microsoft Word, Excel 및 PowerPoint 앱을 MAM 정책과 연결할 수 있습니다. 지원되는 앱의 전체 목록을 확인하려면 [Microsoft Intune application partners](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx)(Microsoft Intune 응용 프로그램 파트너) 페이지의 Microsoft Intune 모바일 응용 프로그램 갤러리로 이동합니다.


### <a name="company-portal-updates"></a>회사 포털 업데이트

#### <a name="android-company-portal-app"></a>Android 회사 포털 앱
- **최종 사용자 알림 메시지**: 이제 최종 사용자가 회사 포털에 장치를 등록하거나 회사 포털에서 장치를 제거하는 경우 Android 회사 포털 앱에 알림 메시지가 표시됩니다.

- **Android 회사 포털 앱의 장치 등록 관리자 계정의 변경 내용.** 성능과 확장성을 개선하기 위해 Intune은 Android 회사 포털 앱의 내 장치 창에 모든 DEM(장치 등록 관리자)을 더 이상 표시하지 않습니다. 앱을 실행하는 로컬 장치가 회사 포털 앱을 통해 등록된 경우에만 표시합니다. DEM 사용자가 로컬 장치에서 작업을 수행할 수 있지만, 등록된 다른 장치의 원격 관리는 Intune 관리 콘솔에서만 수행될 수 있습니다.

#### <a name="company-portal-website"></a>회사 포털 웹 사이트
- **회사 포털 웹 사이트: 장치 식별 배너를 통해 최종 사용자에게 더 많은 정보를 제공합니다.** 이제 최종 사용자가 회사 포털 웹 사이트를 사용할 때 자신이 선택한 장치를 더 쉽게 식별할 수 있습니다. 잘못된 장치를 선택하면 홈페이지 배너의 **여기를 누르세요** 링크를 탭하여 올바른 장치를 선택할 수 있습니다.

### <a name="service-deprecation"></a>서비스 중단
- **Intune 뷰어 앱.** 2016년 8월부터 새 RMS 공유 앱의 릴리스에서 다음 Intune 뷰어 앱을 제거합니다.
    - Intune AV 뷰어
    - Intune PDF 뷰어
    - Google Play의 Android용 Intune 이미지 뷰어

  Intune 뷰어 앱을 사용하는 대신 새로운 Android용 Microsoft Rights Management 공유 앱(RMS 공유)을 사용하는 것이 좋습니다. 이 앱을 통해 세 개의 별도 앱이 아니라 하나의 앱을 배포하여 Android 장치에서 회사 파일을 안전하게 볼 수 있습니다. RMS 공유 앱에 대해 자세히 알아보세요(설명서 링크 사용).

- **사용자 지정 그룹을 알림 규칙의 대상으로 지정하는 기능 제거.**
Intune 알림 규칙은 Intune에서 메일 경고를 보낼 대상자를 정의합니다. 현재 직접 만든 Intune 장치 그룹의 모든 장치 사용자에게 메일을 보내도록 알림 규칙을 구성할 수 있습니다. 2016년 6월 1일경부터는 사용자가 만든 그룹을 대상으로 지정하는 기능이 더 이상 지원되지 않습니다.

    이제 Microsoft Intune 관리 콘솔에서 직접 만든 그룹을 알림 규칙 대상으로 지정하려면 다음 단계를 수행하세요.

    **관리자** 작업 영역에서 **알림 규칙** > **새 규칙 만들기**를 클릭합니다.

    알림 규칙 만들기 마법사의 2단계에서 규칙의 대상이 되는 장치 그룹을 선택합니다. 이 단계 즉, “장치 그룹 선택”은 Intune 콘솔에서 제거됩니다.

    이러한 변경을 준비하기 위한 타임라인은 다음과 같습니다.
    - 2016년 6월에는 새 테넌트에 알림 규칙 만들기 마법사의 2단계가 표시되지 않습니다. 기존 테넌트는 영향을 받지 않습니다.
    - 2016년 8월경에는 일부 기존 테넌트에 마법사의 "장치 그룹 선택"이 표시되지 않습니다.
    - 2016년 10월경에는 모든 기존 테넌트에 마법사의 "장치 그룹 선택"이 표시되지 않을 것으로 예상됩니다.


- **iOS 회사 포털 앱에 대한 지원의 변경 내용**. 향후 몇 개월 내에 iOS용 Microsoft Intune 회사 포털 앱에 대한 업데이트가 있을 예정입니다. iOS 8.0 이상을 실행하는 장치만 지원됩니다. 사용자는 iOS 8.0 이전 버전을 실행하는 장치를 새로 등록할 수 없습니다. iOS 8.0 이전 버전을 실행하는 장치라도 기존에 등록된 장치는 계속 관리할 수 있으며 제한된 시간 동안은 회사 포털 앱을 계속 사용할 수 있습니다. 그러나 회사 포털 앱의 최신 버전에 액세스하려면 장치가 iOS 8.0 이상을 실행해야 합니다. Intune의 새로운 기능을 완전히 활용하려면 사용자에게 iOS 8.0 이상으로 업데이트하도록 알리는 것이 좋습니다.  


## <a name="april-2016"></a>2016년 4월
이 모든 기능은 하이브리드 고객에 대해서도 지원됩니다(Intune과 통합된 Configuration Manager).

### <a name="app-management"></a>앱 관리
- **MAM 사용자 규정 준수.**
이제 Azure Active Directory(AAD) 테넌트에 속하는 모든 사용자에 대한 응용 프로그램 관리 정책의 [상태](/intune/deploy-use/monitor-mobile-app-management-policies-with-Microsoft-Intune)를 볼 수 있습니다. 여기에는 다음 항목이 포함됩니다.
   - 장치
   - 장치의 앱

   상태 값:

   **Checked in**(체크 인 됨): 사용자에게 정책이 배포되었고, 회사 컨텍스트에서 앱이 사용되었으며, 성공적으로 정책이 수신되었다는 것을 나타냅니다.

    **Not checked in**(체크인 안됨): 사용자에게 정책이 배포되었지만, 그 뒤로 회사 컨텍스트에서 앱이 사용되지 않았다는 것을 나타냅니다.


- **Outlook 연락처 동기화를 방지하기 위한 MAM 컨트롤(Android).**
장치 등록 없이 새 설정을 [모바일 응용 프로그램 관리](/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune)에 사용할 수 있습니다. 이 설정을 통해 응용 프로그램이 Android 장치의 기본 주소록에 대해 연락처를 동기화하는 것을 방지할 수 있습니다. 이 설정을 사용하면, 대상 응용 프로그램은 연락처를 기본 주소록에 더 이상 저장할 수 없게 됩니다. 이 설정을 사용하지 않으면, 대상 응용 프로그램은 연락처를 기본 주소록에 저장할 수 있게 됩니다. [장치 또는 앱을 원격으로 초기](/intune/deploy-use/wipe-managed-company-app-data-with-Microsoft-Intune)화하는 경우, 기본 주소록에 이미 저장되어 있는 모든 연락처가 제거됩니다. 이 새로운 설정은 Android 장치의 Outlook 응용 프로그램에서 처음 지원됩니다.

### <a name="device-management"></a>장치 관리
- **회사 소유 장치에 대한 전화 번호 식별.** "회사"로 분류되는 전화는 이제 전체 전화 번호로 식별됩니다(예: 모바일 장치 인벤토리 보고서를 실행하는 경우). BYOD 전화 번호는 마지막 4자리만 표시되고 ****으로 계속 마스킹됩니다.


### <a name="company-portal-updates"></a>회사 포털 업데이트
**Android 회사 포털 앱** Intune에 장치를 등록하지 않았거나 올바른 인증서가 설치되지 않은 사용자는 Android 회사 포털 앱에 로그인할 수 있으며 “You cannot sign in because your device is missing a required certificate.”(장치에 필요한 인증서가 없어서 로그인할 수 없습니다.)라는 메시지를 보게 됩니다. 메시지에는 “해결 방법” 링크가 포함되며, 사용자가 이 링크를 탭하면 인증서 설치에 대한 지침을 볼 수 있습니다. 최종 사용자가 문제를 해결하기 위해 수행하는 단계를 보려면 [장치에 필요한 인증서가 없습니다.](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_cert_missing) 참조하세요.

**iOS 회사 포털 앱** 홈 화면의 콘텐츠를 새로 고치기 위해 끌어오기-새로 고침 작업에 대한 지원이 추가되었습니다. 여기에는 나열된 앱, 나열된 장치, 및 IT 연락처 정보가 포함됩니다. 끌어오기-새로 고침 작업은 정책 또는 준수 정보를 확인하지 않습니다. 이 작업은 현재 장치의 타일을 선택하고 **동기화** 단추를 탭하여 수행할 수 있습니다.

**Windows 10 Mobile 및 Windows Phone 8.1 회사 포털 앱** 최종 사용자가 기간 업무 앱을 설치하는 경우, 향상된 앱 설치 환경이 표시됩니다. 앱 설치가 너무 오래 걸리면, 사용자는 동기화 프로세스가 다시 시작되도록 장치를 수동으로 동기화할 수 있습니다. 최종 사용자 지침을 검토하려면 [앱 설치 속도를 높이기 위해 장치를 수동으로 동기화](https://technet.microsoft.com/library/mt427782.aspx#BKMK_win10m_wp81_sync_manually)를 참조하세요.

** 회사 포털 웹 사이트** Windows 10 Mobile 및 Windows Phone 8.1 사용자가 기간 업무 앱을 설치하는 경우, 다음과 같은 새로운 상태가 표시되어, 사용자의 설치 상태에 대해 보다 자세한 정보를 제공하게 됩니다.

* **장치가 동기화될 때까지 기다리는 중** – 사용자가 “설치”를 탭했고 이제 장치가 Intune 인프라와의 동기화를 시도합니다. 설치를 완료하려면 그 전에 동기화가 필요합니다. "장치가 동기화될 때까지 기다리는 중" 메시지 역시 사용자가 탭하면, 동기화 프로세스가 너무 오래 걸리거나 멈춘 경우 Intune에서 장치를 수동으로 동기화하는 방법에 대한 [지침](https://technet.microsoft.com/library/mt590895.aspx#BKMK_iwp_sync_manually)을 볼 수 있는 링크입니다.
* **다운로드 중** – 사용자의 다운로드 요청이 처리 중이며 장치가 앱을 다운로드 및 설치 중입니다.

이런 상태가 추가되기 전에는, 사용자에게 “설치 중” 상태만 보여줬기 때문에(화면에 수 시간 동안 유지되기도 하는) 앱 설치가 오래 걸리면 혼란스러웠습니다. 새로운 상태가 추가되었기 때문에, 이제 사용자들은 지원을 요청하는 대신 "장치가 동기화될 때까지 기다리는 중" 링크를 클릭하고 지침에 따라서 동기화 프로세스가 재시작되도록 강제 적용할 수 있습니다.

>[!div class="step-by-step"]

>[&larr; **Intune의 새로운 기능**](whats-new-in-microsoft-intune.md)    



<!--HONumber=Dec16_HO1-->


