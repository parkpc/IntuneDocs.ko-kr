---
title: "iOS 사용자가 앱을 얻는 방법 | Microsoft Intune"
description: "최종 사용자에게 iOS 앱을 제공하기 위한 방법"
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 08/24/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e3135c1-df26-48c9-aa4c-cdab6168897a
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
<<<<<<< HEAD
||||||| merged common ancestors
<<<<<<<<< Temporary merge branch 1
=======
<<<<<<< HEAD
>>>>>>> 3cc2bcb16b2aaae00d16317c1b818ba25738a455
ms.sourcegitcommit: 52b9e786fe22b04081441db88a3629062fc85668
ms.openlocfilehash: a215d547507dcc460e83009cc6a04baf3fd8f4a4
<<<<<<< HEAD
||||||| merged common ancestors
||||||||| merged common ancestors
ms.sourcegitcommit: 9f1946c02c6267a22844106e8f72555ec5e9cabb
ms.openlocfilehash: 212dcd31697180dae61569dda13b56704a079bf4
=========
ms.sourcegitcommit: 37841027c7ae040163440a19f9e163fb4eb87233
ms.openlocfilehash: ad780fb3403f6caaee1218d785a5cad326c18df5
>>>>>>>>> Temporary merge branch 2
=======
||||||| merged common ancestors
ms.sourcegitcommit: 9f1946c02c6267a22844106e8f72555ec5e9cabb
ms.openlocfilehash: 212dcd31697180dae61569dda13b56704a079bf4
=======
ms.sourcegitcommit: 37841027c7ae040163440a19f9e163fb4eb87233
ms.openlocfilehash: ad780fb3403f6caaee1218d785a5cad326c18df5
>>>>>>> 359d4f486355df1be118d8fdb698694ae632df85
>>>>>>> 3cc2bcb16b2aaae00d16317c1b818ba25738a455


---


# iOS 사용자가 앱을 얻는 방법

이 정보를 사용하여 최종 사용자가 Microsoft Intune을 통해 배포하는 앱을 얻는 방법과 위치를 이해합니다.

**필요한 앱** - 플랫폼에 따라 최소한의 사용자 작업으로 장치에 설치되며, 관리자에게 필요한 앱입니다.

**사용 가능한 앱** - 회사 포털 앱 목록에 제공되며, 사용자가 필요에 따라 선택하여 설치할 수 있는 앱입니다.

**관리되는 앱** - 정책을 통해 관리할 수 있고 Intune에서 "래핑”했거나 Intune MAM(Mobile Application Management) SDK(소프트웨어 개발 키트)로 빌드된 앱입니다. 이러한 앱은 Intune에서 관리할 수 있고, 응용 프로그램 정책을 적용할 수 있습니다.

**관리되지 않는 앱** - 정책을 통해 관리할 수 있고 Intune에서 래핑되지 않았거나 Intune MAM SDK를 통합하지 않은 앱입니다. 응용 프로그램 정책을 이러한 앱에 적용할 수 없습니다.

<<<<<<< HEAD
||||||| merged common ancestors
<<<<<<<<< Temporary merge branch 1
=======
<<<<<<< HEAD
>>>>>>> 3cc2bcb16b2aaae00d16317c1b818ba25738a455
Apple 제한에 따라 기간 업무 앱과 관리되는 App Store 앱을 회사 포털 앱에 올릴 수 없습니다. 이 문제를 해결하기 위해 iOS용 회사 포털 앱의 앱 타일이 종류에 관계없이 모든 앱에 대해 단일 위치(회사 포털 웹 사이트)에서 서로 다른 보기를 가리킵니다.
<<<<<<< HEAD
||||||| merged common ancestors
||||||||| merged common ancestors
Apple 제한 사항은 기간 업무 및 관리되는 App Store 앱이 회사 포털 앱에 나열되는 것을 금지합니다. 따라서 사용자가 자신의 앱을 모두 찾으려면 여러 보기를 방문해야 합니다. 회사 포털 앱의 앱 페이지에 표시되는 개별 타일에 대한 앱은 다음과 같이 사용 가능합니다.
=========
Apple 제한에 따라 기간 업무 앱과 관리되는 App Store 앱을 회사 포털 앱에 올릴 수 없습니다. 이 문제를 해결하기 위해 iOS용 회사 포털 앱의 타일이 종류에 관계없이 모든 앱에 대해 단일 위치(회사 포털 웹 사이트)에서 서로 다른 보기를 가리킵니다.
>>>>>>>>> Temporary merge branch 2
=======
||||||| merged common ancestors
Apple 제한 사항은 기간 업무 및 관리되는 App Store 앱이 회사 포털 앱에 나열되는 것을 금지합니다. 따라서 사용자가 자신의 앱을 모두 찾으려면 여러 보기를 방문해야 합니다. 회사 포털 앱의 앱 페이지에 표시되는 개별 타일에 대한 앱은 다음과 같이 사용 가능합니다.
=======
Apple 제한에 따라 기간 업무 앱과 관리되는 App Store 앱을 회사 포털 앱에 올릴 수 없습니다. 이 문제를 해결하기 위해 iOS용 회사 포털 앱의 타일이 종류에 관계없이 모든 앱에 대해 단일 위치(회사 포털 웹 사이트)에서 서로 다른 보기를 가리킵니다.
>>>>>>> 359d4f486355df1be118d8fdb698694ae632df85
>>>>>>> 3cc2bcb16b2aaae00d16317c1b818ba25738a455

<<<<<<< HEAD
||||||| merged common ancestors
<<<<<<<<< Temporary merge branch 1
=======
<<<<<<< HEAD
>>>>>>> 3cc2bcb16b2aaae00d16317c1b818ba25738a455
- **회사 앱** 타일은 이전에 [회사 포털 웹 사이트](http://portal.manage.microsoft.com)의 모두 탭에 있는 모든 앱 목록을 가리켰으며, 계속해서 같은 방식으로 작동합니다. 타일 이름이 **모든 앱**으로 변경되었습니다.
<<<<<<< HEAD
||||||| merged common ancestors
||||||||| merged common ancestors
- **회사 앱** 타일은 [회사 포털 웹 사이트](http://portal.manage.microsoft.com)의 **모두** 탭에 있는 모든 앱 목록을 가리킵니다.
=========
- **회사 앱**은 이전에 [회사 포털 웹 사이트](http://portal.manage.microsoft.com)의 모두 탭에 있는 모든 앱 목록을 가리켰는데, 계속해서 같은 방식으로 작동합니다. 타일 이름은 **모든 앱**으로 변경되었습니다.
>>>>>>>>> Temporary merge branch 2
=======
||||||| merged common ancestors
- **회사 앱** 타일은 [회사 포털 웹 사이트](http://portal.manage.microsoft.com)의 **모두** 탭에 있는 모든 앱 목록을 가리킵니다.
=======
- **회사 앱**은 이전에 [회사 포털 웹 사이트](http://portal.manage.microsoft.com)의 모두 탭에 있는 모든 앱 목록을 가리켰는데, 계속해서 같은 방식으로 작동합니다. 타일 이름은 **모든 앱**으로 변경되었습니다.
>>>>>>> 359d4f486355df1be118d8fdb698694ae632df85
>>>>>>> 3cc2bcb16b2aaae00d16317c1b818ba25738a455

<<<<<<< HEAD
||||||| merged common ancestors
<<<<<<<<< Temporary merge branch 1
=======
<<<<<<< HEAD
>>>>>>> 3cc2bcb16b2aaae00d16317c1b818ba25738a455
- **다른 앱** 타일은 이전에 Apple이 표시를 허용하는 모든 회사 포털 앱이 나열된 회사 포털 앱 내 보기를 가리켰습니다. 타일 이름이 **추천 앱**으로 변경되었으며 타일을 탭하면 사용자는 회사 포털 웹 사이트의 추천 탭으로 이동하게 됩니다.
<<<<<<< HEAD
||||||| merged common ancestors
||||||||| merged common ancestors
- 현재 **다른 앱** 타일은 Apple에서 회사 포털 앱에 표시되도록 허용한 전체 앱이 나열된 회사 포털 앱 내 보기를 가리킵니다. 여기에는 기간 업무 및 관리되는 App Store 앱을 제외한 모든 앱이 포함됩니다.
=========
- **기타 앱**은 기존에는 Apple이 회사 포털 앱에서 표시하도록 허용하는 모든 앱을 나열한 회사 포털 앱 내의 보기를 가리켰습니다. 타일 이름이 **추천 앱**으로 변경되었으며 타일을 탭하면 회사 포털 웹 사이트의 추천 탭으로 이동됩니다.
>>>>>>>>> Temporary merge branch 2
=======
||||||| merged common ancestors
- 현재 **다른 앱** 타일은 Apple에서 회사 포털 앱에 표시되도록 허용한 전체 앱이 나열된 회사 포털 앱 내 보기를 가리킵니다. 여기에는 기간 업무 및 관리되는 App Store 앱을 제외한 모든 앱이 포함됩니다.
=======
- **기타 앱**은 기존에는 Apple이 회사 포털 앱에서 표시하도록 허용하는 모든 앱을 나열한 회사 포털 앱 내의 보기를 가리켰습니다. 타일 이름이 **추천 앱**으로 변경되었으며 타일을 탭하면 회사 포털 웹 사이트의 추천 탭으로 이동됩니다.
>>>>>>> 359d4f486355df1be118d8fdb698694ae632df85
>>>>>>> 3cc2bcb16b2aaae00d16317c1b818ba25738a455

<<<<<<< HEAD
||||||| merged common ancestors
<<<<<<<<< Temporary merge branch 1
=======
<<<<<<< HEAD
>>>>>>> 3cc2bcb16b2aaae00d16317c1b818ba25738a455
-  **카테고리** 타일은 이전에 앱의 범주를 나열하는 회사 포털 앱 내 보기를 가리켰습니다. 타일 이름이 변경되지 않았지만 이제는 회사 포털 웹 사이트의 범주 탭을 가리킵니다.
업데이트된 스크린샷은 [여기](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186)에서 볼 수 있습니다.
<<<<<<< HEAD
||||||| merged common ancestors
||||||||| merged common ancestors
- **카테고리** 타일은 앱의 범주를 나열하는 회사 포털 앱 내 보기를 현재 가리키고 있습니다.
=========
-  **카테고리**는 이전에 앱의 범주를 나열한 회사 포털 앱 내 보기를 가리켰습니다. 타일 이름이 변경되지 않았지만 이제는 회사 포털 웹 사이트의 범주 탭을 가리킵니다.
업데이트된 스크린샷은 [iOS 최종 사용자가 앱을 받는 방법에 대한 개선 사항](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186)에서 볼 수 있습니다.
>>>>>>>>> Temporary merge branch 2
=======
||||||| merged common ancestors
- **카테고리** 타일은 앱의 범주를 나열하는 회사 포털 앱 내 보기를 현재 가리키고 있습니다.
=======
-  **카테고리**는 이전에 앱의 범주를 나열한 회사 포털 앱 내 보기를 가리켰습니다. 타일 이름이 변경되지 않았지만 이제는 회사 포털 웹 사이트의 범주 탭을 가리킵니다.
업데이트된 스크린샷은 [iOS 최종 사용자가 앱을 받는 방법에 대한 개선 사항](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186)에서 볼 수 있습니다.
>>>>>>> 359d4f486355df1be118d8fdb698694ae632df85
>>>>>>> 3cc2bcb16b2aaae00d16317c1b818ba25738a455



###참고 항목
[Android 사용자가 앱을 얻는 방법](how-your-android-users-get-their-apps.md)</br>
[Windows 사용자가 앱을 얻는 방법](how-your-windows-users-get-their-apps.md)



<<<<<<< HEAD
||||||| merged common ancestors
<<<<<<<<< Temporary merge branch 1
=======
<<<<<<< HEAD
>>>>>>> 3cc2bcb16b2aaae00d16317c1b818ba25738a455
<!--HONumber=Sep16_HO3-->
<<<<<<< HEAD
||||||| merged common ancestors
||||||||| merged common ancestors
<!--HONumber=Aug16_HO4-->
=========
<!--HONumber=Oct16_HO2-->
>>>>>>>>> Temporary merge branch 2
=======
||||||| merged common ancestors
<!--HONumber=Aug16_HO4-->
=======
<!--HONumber=Oct16_HO2-->
>>>>>>> 359d4f486355df1be118d8fdb698694ae632df85
>>>>>>> 3cc2bcb16b2aaae00d16317c1b818ba25738a455


