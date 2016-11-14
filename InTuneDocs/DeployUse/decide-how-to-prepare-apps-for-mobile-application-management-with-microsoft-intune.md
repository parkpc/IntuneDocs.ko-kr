<<<<<<< HEAD
||||||| merged common ancestors
<<<<<<<<< Temporary merge branch 1
=======
<<<<<<< HEAD
>>>>>>> 3cc2bcb16b2aaae00d16317c1b818ba25738a455
---
title: "모바일 응용 프로그램 관리를 위해 앱 준비 | Microsoft Intune"
description: "이 항목의 정보는 LOB(기간 업무) 앱이 모바일 앱 관리 정책을 사용하도록 하기 위해 앱 줄 바꿈 도구 및 앱 SDK를 사용해야 하는 경우를 결정하는 데 도움이 됩니다."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 29e22121-8268-48b5-a671-f940a6be1d24
ms.reviewer: oldang
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 70f9fb5580b114fe1ba14a1bd05de58467d5cd00
ms.openlocfilehash: b5dd5bec0910a8ce3a940b5ed288907aba0f7ee4

<<<<<<< HEAD
||||||| merged common ancestors
||||||||| merged common ancestors
---
title: "모바일 응용 프로그램 관리를 위해 앱 준비 | Microsoft Intune"
description: "이 항목의 정보는 LOB(기간 업무) 앱이 모바일 앱 관리 정책을 사용하도록 하기 위해 앱 줄 바꿈 도구 및 앱 SDK를 사용해야 하는 경우를 결정하는 데 도움이 됩니다."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 07/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 29e22121-8268-48b5-a671-f940a6be1d24
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: be1ebcdf2514e45d383dd49890e0e21acf6ede44
ms.openlocfilehash: d2d11cc8bed7575b2fe818c9aa5b2359a62a77e0

=========
---
title: "모바일 응용 프로그램 관리를 위해 앱 준비 | Microsoft Intune"
description: "이 항목의 정보는 LOB(기간 업무) 앱이 모바일 앱 관리 정책을 사용하도록 하기 위해 앱 줄 바꿈 도구 및 앱 SDK를 사용해야 하는 경우를 결정하는 데 도움이 됩니다."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 29e22121-8268-48b5-a671-f940a6be1d24
ms.reviewer: oldang
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: df1b58d5ce94c985e71f3afbe228dba9438040dc
ms.openlocfilehash: d79c498fd775ee9b3d59761fec2fe6ebba116d6d

>>>>>>>>> Temporary merge branch 2
=======
||||||| merged common ancestors
---
title: "모바일 응용 프로그램 관리를 위해 앱 준비 | Microsoft Intune"
description: "이 항목의 정보는 LOB(기간 업무) 앱이 모바일 앱 관리 정책을 사용하도록 하기 위해 앱 줄 바꿈 도구 및 앱 SDK를 사용해야 하는 경우를 결정하는 데 도움이 됩니다."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 07/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 29e22121-8268-48b5-a671-f940a6be1d24
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: be1ebcdf2514e45d383dd49890e0e21acf6ede44
ms.openlocfilehash: d2d11cc8bed7575b2fe818c9aa5b2359a62a77e0

=======
---
title: "모바일 응용 프로그램 관리를 위해 앱 준비 | Microsoft Intune"
description: "이 항목의 정보는 LOB(기간 업무) 앱이 모바일 앱 관리 정책을 사용하도록 하기 위해 앱 줄 바꿈 도구 및 앱 SDK를 사용해야 하는 경우를 결정하는 데 도움이 됩니다."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 29e22121-8268-48b5-a671-f940a6be1d24
ms.reviewer: oldang
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: df1b58d5ce94c985e71f3afbe228dba9438040dc
ms.openlocfilehash: d79c498fd775ee9b3d59761fec2fe6ebba116d6d

>>>>>>> 359d4f486355df1be118d8fdb698694ae632df85
>>>>>>> 3cc2bcb16b2aaae00d16317c1b818ba25738a455

---

# Microsoft Intune으로 모바일 응용 프로그램 관리용 앱을 준비하는 방법 결정
Intune 앱 래핑 도구 또는 Intune 앱 SDK를 사용하여 앱에서 MAM(모바일 응용 프로그램 관리) 정책을 사용할 수 있게 할 수 있습니다. 이 정보를 사용하여 이러한 두 가지 방법 및 사용 시기에 대해 알아보세요.

## Intune 앱 래핑 도구
앱 래핑 도구는 내부 LOB(기간 업무) 앱에 주로 사용됩니다. 이 도구는 앱을 둘러싸는 래퍼를 만들어 앱이 Intune 모바일 응용 프로그램 관리 정책에 의해 관리될 수 있게 하는 명령줄 응용 프로그램입니다. 도구를 사용하기 위해 소스 코드가 필요하지는 않지만 서명 자격 증명이 필요합니다.  서명 자격 증명에 대한 자세한 내용은 [Intune 블로그](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios/)를 참조하세요. 앱 래핑 도구 설명서는 [Android App Wrapping Tool](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)(앱 래핑 도구) 및 [iOS App Wrapping Tool](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)(iOS 앱 래핑 도구) 항목을 참조하세요.

앱 래핑 도구는 개발 시간 통합이 필요한 기능이나 앱 스토어 또는 Play 스토어의 앱을 지원하지 않습니다(다음 기능 비교 표 참조).

앱이 이미 작성되었거나 소스 코드를 사용할 수 없는 경우 SDK 대신 앱 래핑 도구를 사용해야 합니다.

<<<<<<< HEAD
||||||| merged common ancestors
<<<<<<<<< Temporary merge branch 1
=======
<<<<<<< HEAD
>>>>>>> 3cc2bcb16b2aaae00d16317c1b818ba25738a455
**Intune에 등록되지 않은 장치에 대해 MAM을 위한 앱 래핑 도구가 현재 공개 미리 보기에서 지원됩니다. 자세한 내용은 [Protect LOB apps on devices not enrolled in Intune](protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune.md)(Intune에 등록되지 않은 장치에서 LOB 앱 보호) 항목**을 참조하세요.

### 지원되는 플랫폼

|**앱 래핑 도구** | **Xamarin** |**Cordova** |
|------|----|----|
|**iOS** |예|예|
|**Android**| 아니요 |예|
<<<<<<< HEAD
||||||| merged common ancestors
||||||||| merged common ancestors
=========
**Intune에 등록되지 않은 장치의 MAM용 앱 래핑 도구에 대한 자세한 내용은 [Microsoft Intune에 등록되지 않은 장치의 기간 업무 앱 및 데이터 보호](protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune.md)를 참조하세요**.

### 지원되는 앱 개발 플랫폼

|**앱 래핑 도구** | **Xamarin** |**Cordova** |
|------|----|----|
|**iOS** |예|예|
|**Android**| 아니요 |예|

>>>>>>>>> Temporary merge branch 2
=======
||||||| merged common ancestors
=======
**Intune에 등록되지 않은 장치의 MAM용 앱 래핑 도구에 대한 자세한 내용은 [Microsoft Intune에 등록되지 않은 장치의 기간 업무 앱 및 데이터 보호](protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune.md)를 참조하세요**.

### 지원되는 앱 개발 플랫폼

|**앱 래핑 도구** | **Xamarin** |**Cordova** |
|------|----|----|
|**iOS** |예|예|
|**Android**| 아니요 |예|

>>>>>>> 359d4f486355df1be118d8fdb698694ae632df85
>>>>>>> 3cc2bcb16b2aaae00d16317c1b818ba25738a455
## Intune 앱 SDK
앱 SDK는 주로 앱 스토어 또는 Play 스토어에 앱이 있으며 Intune으로 앱을 관리할 수 있기를 원하는 고객을 위해 설계되었습니다. 그러나 LOB 앱인 경우에도 모든 앱이 SDK 통합을 활용할 수 있습니다.

SDK에 대해 자세히 알아보려면 [개요](/intune/develop/intune-app-sdk) 항목을 참조하세요. SDK 사용을 시작하려면 [Microsoft Intune 앱 SDK 시작](/intune/develop/intune-app-sdk-get-started) 항목을 참조하세요.

<<<<<<< HEAD
||||||| merged common ancestors
<<<<<<<<< Temporary merge branch 1
=======
<<<<<<< HEAD
>>>>>>> 3cc2bcb16b2aaae00d16317c1b818ba25738a455
### 지원되는 플랫폼
|**Intune 앱 SDK** |**Xamarin** |**Cordova**
|------|----|----|
|**iOS**|예 – Intune App SDK Xamarin 구성 요소 사용|예 – Intune App SDK Cordova 플러그인 사용|
|**Android**| 예 – Intune App SDK Xamarin 구성 요소 사용|예 – Intune App SDK Cordova 플러그인 사용|

<<<<<<< HEAD
||||||| merged common ancestors
||||||||| merged common ancestors
=========
### 지원되는 앱 개발 플랫폼

|**Intune 앱 SDK** |**Xamarin** |**Cordova**
|------|----|----|
|**iOS**|예 – Intune App SDK Xamarin 구성 요소 사용|예 – Intune App SDK Cordova 플러그인 사용|
|**Android**| 예 – Intune App SDK Xamarin 구성 요소 사용|예 – Intune App SDK Cordova 플러그인 사용|

>>>>>>>>> Temporary merge branch 2
=======
||||||| merged common ancestors
=======
### 지원되는 앱 개발 플랫폼

|**Intune 앱 SDK** |**Xamarin** |**Cordova**
|------|----|----|
|**iOS**|예 – Intune App SDK Xamarin 구성 요소 사용|예 – Intune App SDK Cordova 플러그인 사용|
|**Android**| 예 – Intune App SDK Xamarin 구성 요소 사용|예 – Intune App SDK Cordova 플러그인 사용|

>>>>>>> 359d4f486355df1be118d8fdb698694ae632df85
>>>>>>> 3cc2bcb16b2aaae00d16317c1b818ba25738a455
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
<<<<<<< HEAD
||||||| merged common ancestors
<<<<<<<<< Temporary merge branch 1
||||||||| merged common ancestors

=========
|장치 등록이 제외된 MAM에 대한 지원|X|X|
>>>>>>>>> Temporary merge branch 2
=======
<<<<<<< HEAD
||||||| merged common ancestors

=======
|장치 등록이 제외된 MAM에 대한 지원|X|X|
>>>>>>> 359d4f486355df1be118d8fdb698694ae632df85
>>>>>>> 3cc2bcb16b2aaae00d16317c1b818ba25738a455
### 참고 항목

[Android 앱 래핑 도구](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)</br>
[iOS 앱 래핑 도구](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)</br>
[SDK를 사용하여 모바일 응용 프로그램 관리에 앱을 사용하도록 설정](use-the-sdk-to-enable-apps-for-mobile-application-management.md)


<<<<<<< HEAD
||||||| merged common ancestors
<<<<<<<<< Temporary merge branch 1
||||||||| merged common ancestors
<!--HONumber=Jul16_HO5-->
=========
<!--HONumber=Sep16_HO4-->
>>>>>>>>> Temporary merge branch 2
=======
<<<<<<< HEAD
||||||| merged common ancestors
<!--HONumber=Jul16_HO5-->
=======
<!--HONumber=Sep16_HO4-->
>>>>>>> 359d4f486355df1be118d8fdb698694ae632df85
>>>>>>> 3cc2bcb16b2aaae00d16317c1b818ba25738a455

<!--HONumber=Sep16_HO2-->


