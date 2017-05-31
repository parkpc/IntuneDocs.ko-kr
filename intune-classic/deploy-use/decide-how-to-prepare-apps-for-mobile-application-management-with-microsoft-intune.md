---
title: "Microsoft Intune으로 모바일 응용 프로그램 관리용 앱을 준비하는 방법 결정 | Microsoft Docs"
description: "이 항목의 정보는 LOB(기간 업무) 앱이 모바일 앱 관리 정책을 사용하도록 하기 위해 앱 줄 바꿈 도구 및 앱 SDK를 사용해야 하는 경우를 결정하는 데 도움이 됩니다."
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 02/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 29e22121-8268-48b5-a671-f940a6be1d24
ms.reviewer: oldang
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 8ee746ec2ccd9b924c242e956a8c89fba248ca96
ms.contentlocale: ko-kr
ms.lasthandoff: 05/23/2017


---

# <a name="prepare-line-of-business-apps-for-mam"></a>MAM용 기간 업무 준비

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune 앱 래핑 도구 또는 Intune 앱 SDK를 사용하여 앱에서 MAM(모바일 응용 프로그램 관리) 정책을 사용할 수 있게 할 수 있습니다. 이 정보를 사용하여 이러한 두 가지 방법 및 사용 시기에 대해 알아보세요.

## <a name="intune-app-wrapping-tool"></a>Intune 앱 래핑 도구
앱 래핑 도구는 내부 LOB(기간 업무) 앱에 주로 사용됩니다. 이 도구는 앱을 둘러싸는 래퍼를 만들어 앱이 Intune 모바일 앱 관리 정책에 의해 관리될 수 있게 하는 명령줄 응용 프로그램입니다.

도구를 사용하기 위해 소스 코드가 필요하지는 않지만 서명 자격 증명이 필요합니다.  서명 자격 증명에 대한 자세한 내용은 [Intune 블로그](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios/)를 참조하세요. 앱 래핑 도구 설명서는 [Android App Wrapping Tool](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)(앱 래핑 도구) 및 [iOS App Wrapping Tool](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)(iOS 앱 래핑 도구) 항목을 참조하세요.

앱 래핑 도구는 Apple 앱 스토어 또는 Google Play 스토어에서 앱을 지원하지 **않습니다**. 개발자 통합이 필요한 특정 기능을 지원하지도 않습니다(다음 기능 비교 표 참조).


Intune에 등록되지 않은 장치의 MAM용 앱 래핑 도구에 대한 자세한 내용은 [Microsoft Intune에 등록되지 않은 장치의 기간 업무 앱 및 데이터 보호](protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune.md)를 참조하세요.

### <a name="reasons-to-use-the-app-wrapping-tool"></a>앱 줄 바꿈 도구를 사용하는 이유
* 앱에 기본 제공 데이터 보호 기능이 없습니다.
* 앱이 간단합니다.
* 앱이 내부적으로 배포됩니다.
* 앱의 소스 코드에 액세스할 수 없습니다.
* 앱을 개발하지 않았습니다.
* 앱에 최소한의 사용자 인증 환경이 있습니다.


### <a name="supported-app-development-platforms"></a>지원되는 앱 개발 플랫폼

|**앱 래핑 도구** | **Xamarin** |**Cordova** |
|------|----|----|
|**iOS** |예|예|
|**Android**| 아니요 |예|

## <a name="intune-app-sdk"></a>Intune 앱 SDK
앱 SDK는 주로 Apple 앱 스토어 및/또는 Google Play 스토어에 앱이 있으며 Intune으로 앱을 관리할 수 있기를 원하는 고객을 위해 설계되었습니다. 그러나 기간 업무 앱을 비롯한 모든 앱은 SDK 통합을 활용할 수 있습니다.

SDK에 대해 자세히 알아보려면 [개요](../develop/intune-app-sdk.md) 항목을 참조하세요. SDK 사용을 시작하려면 [Microsoft Intune 앱 SDK 시작](../develop/intune-app-sdk-get-started.md) 항목을 참조하세요.

### <a name="reasons-to-use-the-sdk"></a>SDK를 사용하는 이유
* 앱에 기본 제공 데이터 보호 기능이 없습니다.
* 앱이 복잡하며 다양한 환경을 포함하고 있습니다.
* 앱이 Google Play 또는 Apple의 앱 스토어와 같은 공개 앱 스토어에 배포됩니다.
* 앱 개발자이며 SDK를 사용할 수 있는 기술적 배경을 가지고 있습니다.
* 앱에 다른 SDK 통합이 있습니다.
* 앱이 자주 업데이트됩니다.

### <a name="supported-app-development-platforms"></a>지원되는 앱 개발 플랫폼

|**Intune 앱 SDK** |**Xamarin** |**Cordova**
|------|----|----|
|**Android**|예 – [Intune 앱 SDK Xamarin 구성 요소](../develop/intune-app-sdk-xamarin.md) 사용|예 – [Intune 앱 SDK Cordova 플러그인](../develop/intune-app-sdk-cordova.md) 사용|
|**OWA(Outlook Web Access)**| 예 – [Intune 앱 SDK Xamarin 구성 요소](../develop/intune-app-sdk-xamarin.md) 사용|예 – [Intune 앱 SDK Cordova 플러그인](../develop/intune-app-sdk-cordova.md) 사용|

## <a name="feature-comparison"></a>기능 비교
이 표에는 앱 SDK 및 앱 래핑 도구에 사용할 수 있는 설정이 나와 있습니다.

> [!NOTE]
> 앱 래핑 도구는 Intune 독립 실행형 또는 Configuration Manager가 포함된 Intune과 함께 사용할 수 있습니다.

|기능|앱 SDK|앱 래핑 도구|
|-----------|---------------------|-----------|
|웹 콘텐츠가 회사에서 관리되는 브라우저에 표시되도록 제한|X|X|
|Android, iTunes 또는 iCloud 백업 차단|X|X|
|앱이 다른 앱으로 데이터를 전송하도록 허용|X|X|
|앱이 다른 앱의 데이터를 받도록 허용|X|X|
|다른 앱에서 잘라내기, 복사 및 붙여넣기 제한|X|X|
|액세스 시 단순 PIN 필요|X|X|
|기본 제공 앱 PIN을 Intune PIN으로 바꾸기|X||
|PIN을 다시 설정하기 전 시도 횟수 지정|X|X|
|PIN 대신 지문 허용 |X|X|
|액세스 시 회사 자격 증명 필요|X|X|
|관리되는 앱이 무단 해제 또는 루팅된 장치를 실행하지 못하도록 차단|X|X|
|앱 데이터 암호화|X|X|
|지정된 시간(분) 후에 액세스 요구 사항 다시 확인|X|X|
|오프라인 유예 기간 지정|X|X|
|화면 캡처 차단(Android에만 해당)|X|X|
|전체 초기화|X|X|
|선택적 초기화 <br></br>**참고:** iOS의 경우 관리 프로필을 제거하면 앱도 제거됩니다.|X||
|"다른 이름으로 저장" 차단 |X||
|다중 ID 지원|X||
|장치 등록이 제외된 MAM에 대한 지원|X|X|
|사용자 지정 가능한 스타일 |X|||
### <a name="see-also"></a>참고 항목

[Android 앱 래핑 도구](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)</br>
[iOS 앱 래핑 도구](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)</br>
[SDK를 사용하여 모바일 응용 프로그램 관리에 앱을 사용하도록 설정](use-the-sdk-to-enable-apps-for-mobile-application-management.md)

