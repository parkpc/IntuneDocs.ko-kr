---
title: "Microsoft Intune으로 모바일 응용 프로그램 관리용 앱을 준비하는 방법 결정 | Microsoft Intune"
description: 
keywords: 
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 29e22121-8268-48b5-a671-f940a6be1d24
ms.reviewer: jeffgilb
ms.suite: ems
ms.sourcegitcommit: 8c1f4f209c5ec704290882b8f6f71e0b1b01d21c
ms.openlocfilehash: 986d864a3169fa3b094241a3522e3f25b7bfe349


---

# Microsoft Intune으로 모바일 응용 프로그램 관리용 앱을 준비하는 방법 결정
Intune 앱 래핑 도구 또는 Intune 앱 SDK를 사용하여 앱에서 모바일 응용 프로그램 관리 정책을 사용할 수 있게 할 수 있습니다. 이 정보를 사용하여 이러한 두 가지 방법 및 사용 시기에 대해 알아보세요.

## Intune 앱 래핑 도구
앱 래핑 도구는 내부 LOB(기간 업무) 앱에 주로 사용됩니다. 이 도구는 앱을 둘러싸는 래퍼를 만들어 앱이 Intune 모바일 응용 프로그램 관리 정책에 의해 관리될 수 있게 하는 명령줄 응용 프로그램입니다. 도구를 사용하기 위해 소스 코드가 필요하지는 않지만 서명 자격 증명이 필요합니다.  서명 자격 증명에 대한 자세한 내용은 [Intune 블로그](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios/)를 참조하세요. 앱 래핑 도구 설명서는 [Android App Wrapping Tool](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)(앱 래핑 도구) 및 [iOS App Wrapping Tool](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)(iOS 앱 래핑 도구) 항목을 참조하세요.

앱 래핑 도구는 개발 시간 통합이 필요한 기능이나 앱 스토어 또는 Play 스토어의 앱을 지원하지 않습니다(다음 기능 비교 표 참조).

앱이 이미 작성되었거나 소스 코드를 사용할 수 없는 경우 SDK 대신 앱 래핑 도구를 사용해야 합니다.

## Intune 앱 SDK
앱 SDK는 주로 앱 스토어 또는 Play 스토어에 앱이 있으며 Intune으로 앱을 관리할 수 있기를 원하는 고객을 위해 설계되었습니다. 그러나 LOB 앱인 경우에도 모든 앱이 SDK 통합을 활용할 수 있습니다.

SDK에 대해 자세히 알아보려면 [개요](/intune/develop/intune-app-sdk) 항목을 참조하세요. SDK 사용을 시작하려면 [Microsoft Intune 앱 SDK 시작](/intune/develop/intune-app-sdk-get-started) 항목을 참조하세요.

## 기능 비교
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
|PIN 대신 지문 필요(iOS에만 해당)<br></br>**참고:** MAM 전용 환경에서만 사용할 수 있습니다.|X||
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

### 참고 항목
[Android 앱 래핑 도구](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)</br>
[iOS 앱 래핑 도구](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)</br>
[SDK를 사용하여 모바일 응용 프로그램 관리에 앱을 사용하도록 설정](use-the-sdk-to-enable-apps-for-mobile-application-management.md)



<!--HONumber=Jun16_HO4-->


