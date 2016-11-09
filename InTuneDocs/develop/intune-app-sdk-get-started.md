---
title: "Microsoft Intune 앱 SDK 시작 | Microsoft Intune"
description: 
keywords: 
author: Msmbaldwin
manager: jeffgilb
ms.date: 09/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 38ebd3f5-cfcc-4204-8a75-6e2f162cd7c1
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ed1008c786285821c608a8404805c6615c60507f
ms.openlocfilehash: c80868fdee79df62aae0aa64e378be5dcc9664ae


---

# <a name="getting-started-with-the-microsoft-intune-app-sdk"></a>Microsoft Intune 앱 SDK 시작

이 시작 가이드에서는 Microsoft Intune을 통해 모바일 앱을 모바일 응용 프로그램 관리에 사용할 수 있도록 빠르게 설정하는 방법을 안내합니다. 먼저 [Intune 앱 SDK 개요](intune-app-sdk.md) 항목에 열거되어 있는 Intune 앱 SDK의 이점을 이해하는 것이 좋습니다.

이 가이드에서는 Microsoft Intune을 사용하여 앱에서 모바일 앱 관리를 사용하도록 설정하는 데 필요한 주요 단계를 안내합니다. Intune 앱 SDK는 여러 플랫폼에서 유사한 시나리오를 지원하며 다양한 플랫폼에서 IT 관리자를 위한 일관된 환경을 만들기 위한 것입니다. 하지만 플랫폼의 제한으로 인해 특정 기능 지원에는 약간씩 차이가 있습니다.

# <a name="getting-started"></a>시작

## <a name="register-your-store-app-with-microsoft"></a>Microsoft에 스토어 앱 등록

**앱이 회사 내부용이고 공개 앱 스토어에 제공되지 않도록 할 경우**:

앱을 등록할 **필요가 없습니다**. 내부 기간 업무 앱의 경우 IT 관리자는 내부적으로 앱을 배포합니다. Intune에서는 SDK로 빌드된 앱을 감지하여 IT 관리자가 해당 앱에 MAM 정책 설정을 적용할 수 있도록 합니다. [SDK를 사용하여 MAM에 대해 iOS 또는 Android 모바일 앱 사용 설정](#enable-your-ios-or-android-mobile-app-for-mam-with-the-sdk) 섹션으로 건너뛸 수 있습니다.

**앱이 Apple 앱 스토어 또는 Google Play와 같은 공개 앱 스토어에 릴리스되는 경우**: 

먼저 **반드시** Microsoft Intune에 앱을 등록하고 등록 조건에 동의해야 합니다. 등록한 후 IT 관리자는 Intune 앱 파트너로 나열될 지원 앱에 Intune MAM 정책 설정을 적용할 수 있습니다. Microsoft Intune 팀에서 등록을 완료하고 확인할 때까지 Intune 관리자는 앱의 딥 링크에 MAM 정책을 적용할 수 없습니다. Microsoft는 앱을 해당 [Microsoft Intune Partners page](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-apps)(Microsoft Intune 파트너 페이지)에도 추가하며, 이 페이지에서는 앱이 Microsoft Intune MAM 정책을 지원함을 나타내기 위해 앱의 아이콘이 표시됩니다.

등록 프로세스를 시작하려면 **[Microsoft Intune 앱 파트너 설문지](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR6oOVGFZ3pxJmwSN1N_eXwJUQUc5Mkw2UVU0VzI5WkhQOEYyMENWNDBWRS4u)**를 작성하세요. 

Microsoft에서 귀하의 설문지 응답에 명시된 메일 주소를 사용하여 연락한 후 등록 프로세스를 진행합니다. 또한 연락해야 할 사항이 있는 경우 등록 메일 주소를 사용하여 연락합니다.

> [!NOTE]
> Microsoft Intune 팀에서 위의 양식이나 메일 서신을 통해 수집한 모든 정보에 [Microsoft 개인정보취급방침](https://www.microsoft.com/en-us/privacystatement/default.aspx)이 적용됩니다.

**등록 프로세스 진행 사항**: 

1. 설문지를 제출하고 나면 Microsoft에서 등록 메일 주소를 통해 연락을 드려 성공적인 수신을 확인하거나 등록을 완료하기 위해 필요한 추가 정보를 요청합니다. 
2. Microsoft는 사용자로부터 필요한 모든 정보를 받은 후 서명할 수 있는 Microsoft Intune 앱 파트너 계약서를 보냅니다. 이 계약에서는 Microsoft Intune 앱 파트너가 되려는 회사가 동의해야 하는 조건을 설명합니다. 
3. 또한 앱이 Microsoft Intune 서비스를 사용해 등록 완료되는 경우 및 앱이 [Microsoft Intune 파트너](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-apps) 사이트에서 추천 목록에 뜨는 경우에도 알려드립니다. 
4. 마지막으로 다음 월별 Intune 서비스 업데이트에 앱 딥 링크가 추가됩니다. 예를 들어 등록 정보가 7월에 완료되는 경우 앱 딥 링크는 8월 중순에 지원됩니다. 

스토어 앱의 딥 링크가 향후에 변경되면 앱을 다시 등록해야 합니다. 그뿐 아니라 새 버전의 Intune 앱 SDK를 사용하여 앱을 업데이트하는 경우에도 Microsoft에 알려 주세요.



## <a name="download-the-sdk-files"></a>SDK 파일 다운로드

네이티브 iOS 및 Android용 Intune 앱 SDK는 Microsoft GitHub 계정에서 호스트됩니다. 아래 공용 리포지토리에는 iOS 및 Android용 SDK 파일이 각각 포함되어 있습니다.

* [iOS용 Intune 앱 SDK](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios)
* [Android용 Intune 앱 SDK](https://github.com/msintuneappsdk/ms-intune-app-sdk-android)

**Xamarin 또는 Cordova 앱의 경우 아래의 개발자 도구를 사용하세요**.

* [Intune 앱 SDK Xamarin 구성 요소](https://github.com/msintuneappsdk/intune-app-sdk-xamarin)
* [Intune 앱 SDK Cordova 플러그 인](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam)

Microsoft 리포지토리에서 분기하고 끌어오는 데 사용할 수 있는 GitHub 계정을 등록하는 것이 좋습니다. GitHub에서는 개발자가 Microsoft 제품 팀과 커뮤니케이션하고, 문제를 개설하고 빠른 응답을 받으며, 릴리스 정보를 확인하고, Microsoft에 피드백을 제공할 수 있도록 하고 있습니다. GitHub 계정 및 리포지토리에 대한 문의 사항이 있는 경우 msintuneappsdk@microsoft.com으로 문의하세요.





## <a name="enable-your-ios-or-android-mobile-app-for-mam-with-the-sdk"></a>SDK를 사용하여 MAM에 대해 iOS 또는 Android 모바일 앱 사용 설정

Intune 앱 SDK를 네이티브 iOS 앱에 통합하려면 다음이 필요합니다. 

* **[iOS용 Intune 앱 SDK 개발자 가이드](intune-app-sdk-ios.md)**: 이 문서에서는 Intune 앱 SDK를 사용하여 모바일 iOS 앱을 사용하도록 설정하는 과정을 단계별로 안내합니다. 


Intune 앱 SDK를 네이티브 Android 앱에 통합하려면 다음이 필요합니다.

* **[Android용 Intune 앱 SDK 개발자 가이드](intune-app-sdk-android.md)**: 이 문서에서는 Intune 앱 SDK를 사용하여 모바일 Android 앱을 사용하도록 설정하는 과정을 단계별로 안내합니다. 

Intune 앱 SDK Xamarin 구성 요소 및 Intune 앱 SDK Cordova 플러그 인에 대한 설명서는 해당 GitHub 리포지토리 내에서 찾을 수 있습니다. 


## <a name="configuring-telemetry-for-your-app"></a>앱에 대한 원격 분석 구성

Microsoft Intune은 앱의 사용 통계에 대한 데이터를 수집합니다.

* **iOS용 Intune 앱 SDK**: SDK는 기본적으로 사용 이벤트에 대한 SDK 원격 분석 데이터를 기록합니다. 이 데이터는 Microsoft Intune로 전송됩니다.

    * 앱에서 Microsoft Intune으로 SDK 원격 분석 데이터를 보내지 않으려면 IntuneMAMSettings 사전에서 `MAMTelemetryDisabled` 속성을 "YES"로 설정하여 원격 분석 전송을 사용하지 않도록 설정해야 합니다.

* **Android용 Intune 앱 SDK**: 원격 분석 데이터가 SDK를 통해 기록되지 않습니다.

## <a name="test-your-mam-enabled-app-with-microsoft-intune"></a>Microsoft Intune을 사용하여 MAM 지원 앱 테스트

iOS 또는 Android 앱을 Intune 앱 SDK와 통합하는 데 필요한 단계를 완료한 후에는 모든 앱 관리 정책이 사용하도록 설정되어 최종 사용자 및 IT 관리자에 대해 작동하는지 확인해야 합니다. 통합된 앱을 테스트하려면 다음이 필요합니다.

<!--TODO-->

* **Microsoft Intune을 사용하여 MAM 지원 앱 테스트**: 이 문서에서는 Microsoft Intune을 사용하여 MAM 지원 iOS 또는 Android 앱을 테스트하는 방법을 단계별로 안내합니다. 이 문서는 SDK의 GitHub 리포지토리에서 찾을 수 있습니다.

* **Microsoft Intune 계정**: Microsoft Intune을 사용하여 MAM 지원 앱을 테스트하려면 Microsoft Intune 계정이 필요합니다. 
    * Intune MAM에 대해 iOS 또는 Android 스토어 앱을 사용하도록 설정하는 ISV인 경우 등록 단계에 설명된 대로 Microsoft Intune을 사용하여 등록을 완료하면 프로모션 코드를 받게 됩니다. 이 프로모션 코드를 사용하여 1년 연장 사용할 수 있는 Microsoft Intune 평가판에 등록할 수 있습니다. 
    * 스토어에 게시하지 않을 LOB(기간 업무) 앱을 개발 중인 경우에는 조직을 통해 Microsoft Intune에 대한 액세스 권한을 가져야 합니다. [Microsoft Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0)을 사용하여 1개월 무료 평가판에 등록할 수도 있습니다.




<!--HONumber=Nov16_HO1-->


