---
title: "Microsoft Intune 앱 SDK 시작 | Microsoft Intune"
description: 
keywords: 
author: Msmbaldwin
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 38ebd3f5-cfcc-4204-8a75-6e2f162cd7c1
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b7f62c5ee18d8f69fa174f09a1c46b6925c7517c
ms.openlocfilehash: a042f0c6206e9aaf4ec0eb012a70930aa95ecc47


---

# Microsoft Intune 앱 SDK 시작

이 시작 가이드에서는 Microsoft Intune을 통해 모바일 앱을 모바일 응용 프로그램 관리에 사용할 수 있도록 빠르게 설정하는 방법을 안내합니다. 먼저 [Intune 앱 SDK 개요](intune-app-sdk.md) 항목에 열거되어 있는 Intune 앱 SDK의 이점을 이해하는 것이 좋습니다.

이 가이드에서는 Microsoft Intune을 사용하여 앱에서 모바일 앱 관리를 사용하도록 설정하는 데 필요한 주요 단계를 안내합니다. Intune 앱 SDK는 여러 플랫폼에서 유사한 시나리오를 지원하며 다양한 플랫폼에서 IT 관리자를 위한 일관된 환경을 만들기 위한 것입니다. 하지만 플랫폼의 제한으로 인해 특정 기능 지원에는 약간씩 차이가 있습니다.

# 시작

## Microsoft Connect 등록

Intune 앱 SDK는 현재 Microsoft Connect를 통해 액세스할 수 있으며 등록이 필요합니다. 이를 위해서는 회사 메일을 사용하여 [Microsoft 계정](https://connect.microsoft.com/ConfigurationManagervnext/InvitationUse.aspx?ProgramID=8967&InvitationID=8967-YJYJ-8G6X)을 등록하세요.

등록은 Intune 팀에서 요청을 검토할 때까지 보류 중 상태로 유지됩니다. 일반적인 응답 시간은 업무일 기준 2~3일 이내입니다. 승인되면 사용 중인 플랫폼용 Intune 앱 SDK와 모든 관련 가이드를 다운로드하는 링크가 포함된 메일 알림을 받습니다. 이러한 가이드는 MSDN 사이트에서도 액세스할 수 있습니다.

## Microsoft Intune을 사용하여 스토어 앱 등록

**사용 설정한 앱이 회사 내부용이며 Apple 또는 Google 앱 스토어에 게시하지 않으려는 경우**: 앱을 등록할 필요가 없습니다. 이러한 내부 앱의 경우 IT 관리자는 배포를 위해 Microsoft Intune 콘솔에 직접 로드하며, 그러면 Intune은 앱이 SDK를 사용하여 빌드되었음을 감지하고 앱에 MAM 정책을 적용하는 옵션을 IT 관리자에게 제시합니다. [SDK를 사용하여 MAM에 대해 iOS 또는 Android 모바일 앱 사용 설정](#enable-your-ios-or-android-mobile-app-for-mam-with-the-sdk) 섹션으로 건너뛸 수 있습니다.

**Apple 또는 Google 앱 스토어를 통해 고객에게 게시할 앱을 개발하는 ISV인 경우**: 먼저 Microsoft Intune을 사용해 앱을 등록하고 등록 조건에 동의해야 합니다. 이때 앱의 딥 링크를 제공할 수 있습니다. 나중에 IT 관리자는 앱에 Intune MAM 정책을 적용할 수 있습니다. Microsoft Intune 팀에서 등록을 완료하고 확인할 때까지 앱의 딥 링크에는 관리 콘솔에서 MAM 정책을 적용하는 옵션이 지정되지 않습니다. Microsoft는 또한 Microsoft Intune 파트너 웹 사이트를 유지하며, 이 사이트에서 앱이 등록되므로 고객은 MAM 정책이 지원된다는 점을 알게 됩니다.

등록 프로세스를 시작하려면 [Microsoft Intune 파트너 계약](https://connect.microsoft.com/ConfigurationManagervnext/Survey/Survey.aspx?SurveyID=17806)을 **검토하고 서명**하세요. 이 계약에서는 Microsoft Intune 앱 파트너가 되려는 회사가 동의해야 하는 조건을 설명합니다. 이 문서를 보려면 먼저 로그인해야 합니다. Intune 앱 SDK Microsoft Connect 사이트에 있는 설문 조사 탭 아래 또는 다음 위치에서 이 계약을 찾을 수 있습니다. 앱 이름, 회사 이름, Google 또는 iTunes 스토어에서의 앱 딥 링크 등을 제공하도록 요청합니다.

![Microsoft Connect](../media/microsoft-connect.png)

Microsoft는 등록 메일 주소를 사용하여 등록 프로세스 수신을 확인하고 완료합니다. 또한 연락해야 할 사항이 있는 경우 등록 메일 주소를 사용하여 연락합니다.

**등록 프로세스 진행 사항**: 양식을 제출하고 나면 Microsoft에서 등록 메일 주소를 통해 연락을 드려 성공적인 수신을 확인하거나 등록을 완료하기 위해 필요한 추가 정보를 요청합니다. 또한 앱이 Microsoft Intune을 사용해 등록 완료되는 경우 및 앱이 Microsoft Intune 파트너 사이트에서 추천 목록에 뜨는 경우에도 연락을 드립니다. 정보 수신이 확인된 후에는 앱 딥 링크가 다음번 월별 Intune 서비스 업데이트에 포함됩니다. 예를 들어 등록 정보가 7월에 완료되는 경우 앱 딥 링크는 8월 중순에 지원됩니다. 스토어 앱의 딥 링크가 향후에 변경되면 앱을 다시 등록해야 합니다. 뿐만 아니라 새 버전의 Intune 앱 SDK를 사용하여 앱을 업데이트하는 경우에도 Microsoft에 알려 주세요.

**참고**: Intune 팀에서 위의 양식이나 메일 서신을 통해 수집한 모든 정보에 [Microsoft 개인정보취급방침](https://www.microsoft.com/en-us/privacystatement/default.aspx)이 적용됩니다.

## SDK를 사용하여 MAM에 대해 iOS 또는 Android 모바일 앱 사용 설정

iOS 모바일 앱을 사용하도록 설정하려면 다음이 필요합니다.

1. **[iOS용 Intune 앱 SDK 개발자 가이드](intune-app-sdk-ios.md)**: 이 문서에서는 Intune 앱 SDK를 사용하여 모바일 iOS 앱을 사용하도록 설정하는 과정을 단계별로 안내합니다. 이 문서는 Intune 앱 SDK 패키지의 일부로 다운로드한 문서 폴더에서 찾을 수 있습니다.
2. **iOS용 Intune 앱 SDK**: Microsoft Intune에서 다운로드한 Intune 앱 SDK 패키지의 일부로서, 서명된 폴더 “Intune App SDK for iOS”를 찾을 수 있습니다. 이 폴더에는 iOS용 Intune 앱 SDK 콘텐츠가 모두 들어 있습니다.

Intune 앱 SDK를 사용하여 Android 모바일 앱을 사용하도록 설정하려면 다음이 필요합니다.

1. **[Android용 Intune 앱 SDK 개발자 가이드](intune-app-sdk-android.md)**: 이 문서에서는 Intune 앱 SDK를 사용하여 모바일 Android 앱을 사용하도록 설정하는 과정을 단계별로 안내합니다. 이 문서는 Intune 앱 SDK 패키지의 일부로 다운로드한 문서 폴더에서 찾을 수 있습니다.
2. **Android용 Intune 앱 SDK**: Microsoft Intune에서 다운로드한 Intune 앱 SDK 패키지의 일부로서, 서명된 폴더 “Intune App SDK for Android”를 찾을 수 있습니다. 이 폴더에는 Android용 Intune 앱 SDK 콘텐츠가 모두 들어 있습니다.

## 앱에 대한 원격 분석 해제

**iOS용 Intune 앱 SDK**: SDK는 기본적으로 사용 이벤트에 대한 SDK 원격 분석 데이터를 기록합니다. 이 데이터는 Microsoft Intune로 전송됩니다.

응용 프로그램에서 Microsoft Intune에 SDK 원격 분석 데이터를 보내지 않도록 선택하는 경우 **IntuneMAMSettings** 에서 `MAMTelemetryDisabled` 속성을 ‘YES’로 설정하여 SDK 원격 분석 전송을 `IntuneMAMSettings`.

**Android용 Intune 앱 SDK**: SDK 원격 분석 데이터가 SDK를 통해 기록되지 않습니다.

## Microsoft Intune을 사용하여 MAM 지원 앱 테스트

iOS 또는 Android Intune 앱 SDK를 지원(Intune 앱 SDK를 통합)하는 데 필요한 단계를 완료한 후에는 모든 앱 관리 정책이 사용하도록 설정되어 최종 사용자 및 IT 관리자용으로 작동하는지 확인해야 합니다. 지원 앱을 테스트하려면 다음이 필요합니다.

1. **Microsoft Intune을 사용하여 MAM 지원 앱 테스트**: 이 문서에서는 Microsoft Intune을 사용하여 MAM 지원 iOS 또는 Android 앱을 테스트하는 방법을 단계별로 안내합니다. 이 문서는 Intune 앱 SDK 패키지의 일부로 다운로드한 문서 폴더에서 찾을 수 있습니다.
2. **Microsoft Intune 계정**: Microsoft Intune을 사용하여 MAM 지원 앱을 테스트하려면 Microsoft Intune 계정이 필요합니다. MAM에 대해 iOS 또는 Android 스토어 앱을 사용하도록 설정하는 ISV는 등록 단계의 설명대로 Microsoft Intune을 사용하여 등록을 완료하면 프로모션 코드를 받습니다. 이 프로모션 코드를 사용하여 1년 연장 사용할 수 있는 Microsoft Intune 평가판에 등록할 수 있습니다. 스토어에 게시하지 않을 LOB(기간 업무) 앱을 개발 중인 경우에는 조직을 통해 Microsoft Intune에 대한 액세스 권한을 가져야 합니다. [Microsoft Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0)을 사용하여 1개월 무료 평가판에 등록할 수도 있습니다.




<!--HONumber=Jun16_HO4-->


