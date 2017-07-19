---
title: "iOS 장치에 대한 Intune 앱 알림 설정"
titleSuffix: Intune on Azure
description: "iOS 장치에서 앱의 알림을 제어하는 데 사용할 수 있는 설정을 알아봅니다.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bda26d1d-2a3b-4669-adf8-a5aa7f994916
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 36a9e9a5be9b2dc45ded1a99c7a5871780f7d9b2
ms.sourcegitcommit: c9b3a95bf529b6cb2a2bdacbc49127dfa0c233e5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/05/2017
---
# <a name="intune-app-notifications-settings-for-ios-devices"></a>iOS 장치에 대한 Intune 앱 알림 설정

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

장치에 설치된 앱에서 알림을 전송하는 방식을 구성할 수 있습니다. 이 설정은 iOS 9.3 이상을 실행하는 감독 모드 장치를 지원합니다.

## <a name="configure-settings"></a>설정 구성

1. 장치 기능 블레이드에서 **앱 알림(감독 모드인 경우에만)**을 선택합니다.
2. **앱 알림** 블레이드에서 **추가**를 선택한 후 다음 값을 구성합니다.
    - **앱 번들 ID** - 구성할 앱의 **번들 ID**를 입력합니다. 도움말은 이 항목의 **기본 제공 iOS 앱에 대한 번들 ID 참조**를 참조하세요.
    - **앱 이름** - 구성할 앱 이름을 입력합니다. 이 이름은 장치에 표시되지 않으며, 목록에서 앱을 식별하는 데 사용됩니다.
    - **게시자** - 구성할 앱의 게시자를 입력합니다. 게시자 이름은 장치에 표시되지 않으며, 목록에서 앱을 식별하는 용도로만 사용됩니다.
    - **알림** - 앱에서 장치에 알림을 보내는 작업을 사용하도록 설정하거나, 사용하지 않도록 설정합니다. 이 설정을 사용하지 않도록 설정하면 다음 설정도 사용되지 않습니다.
        - **알림 센터에 표시** - 장치의 알림 센터에서 알림을 표시하도록 앱을 허용하려면 이 설정을 사용하도록 지정합니다.
        - **잠금 화면에 표시** - 장치 잠금 화면에 앱의 알림을 표시하려면 이 설정을 사용하도록 지정합니다.
        - **경고 유형** - 장치 잠금이 해제되는 경우 원하는 알림 유형을 선택합니다.
            - **없음** - 알림이 표시되지 않습니다.
            - **배너** - 알림을 보여 주는 배너가 간단하게 표시됩니다.
            - **모달** - 알림이 표시되면 장치를 계속 사용하기 전에 사용자가 수동으로 알림을 해제해야 합니다.
        - **앱 아이콘 배지** - 앱에서 알림을 보냈음을 나타내는 배지를 앱 아이콘에 추가하려면 이 설정을 사용하도록 지정합니다.
        - **소리** - 알림이 전달될 때 소리를 재생하려면 이 설정을 사용하도록 지정합니다.
3. 필요에 맞게 앱을 계속 추가합니다. 작업이 끝나면 **확인**을 선택합니다.
4. **프로필 만들기** 블레이드로 돌아갈 때까지 **확인**을 선택한 다음 **만들기**를 선택합니다. 


## <a name="bundle-id-reference-for-built-in-ios-apps"></a>기본 제공 iOS 앱에 대한 번들 ID 참조

이 목록에서는 몇 가지 일반적인 기본 제공 iOS 앱의 번들 ID를 보여줍니다. 다른 앱의 번들 ID를 찾으려면 소프트웨어 공급업체에 문의하세요. 

|||
|-|-|
|앱 이름|BundleID|
|앱 스토어|com.apple.AppStore|
|계산기|com.apple.calculator|
|일정|com.apple.mobilecal|
|카메라|com.apple.camera|
|시계|com.apple.mobiletimer|
|나침반|com.apple.compass|
|연락처|com.apple.MobileAddressBook|
|FaceTime|com.apple.facetime|
|친구 찾기|com.apple.mobileme.fmf1|
|나의 iPhone 찾기|com.apple.mobileme.fmip1|
|게임 센터|com.apple.gamecenter|
|GarageBand|com.apple.mobilegarageband|
|상태|com.apple.Health|
|iBooks|com.apple.iBooks|
|iTunes Store|com.apple.MobileStore|
|iTunes U|com.apple.itunesu|
|키노트|com.apple.Keynote|
|Mail|com.apple.mobilemail|
|맵|com.apple.Maps|
|메시지|com.apple.MobileSMS|
|음악|com.apple.Music|
|뉴스|com.apple.news|
|참고|com.apple.mobilenotes|
|숫자|com.apple.Numbers|
|페이지|com.apple.Pages|
|Photo Booth|com.apple.Photo-Booth|
|사진|com.apple.mobileslideshow|
|Podcasts|com.apple.podcasts|
|미리 알림|com.apple.reminders|
|Safari|com.apple.mobilesafari|
|설정|com.apple.Preferences|
|주식|com.apple.stocks|
|팁|com.apple.tips|
|동영상|com.apple.videos|
|음성 메모|com.apple.VoiceMemos|
|Wallet|com.apple.Passbook|
|보기|com.apple.Bridge|
|날씨|com.apple.weather|

## <a name="next-steps"></a>다음 단계

이제 선택한 그룹에 장치 프로필을 할당할 수 있습니다. 자세한 내용은 [장치 프로필을 할당하는 방법](device-profile-assign.md)을 참조하세요.
