---
title: "iOS 사용자가 앱을 얻는 방법 | Microsoft Intune"
description: "최종 사용자에게 iOS 앱을 제공하기 위한 방법"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e3135c1-df26-48c9-aa4c-cdab6168897a
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 3ba0a5cda91164761c4576df935c54390bc78f8c


---


# <a name="how-your-ios-users-get-their-apps"></a>iOS 사용자가 앱을 얻는 방법

이 정보를 사용하여 최종 사용자가 Microsoft Intune을 통해 배포하는 앱을 얻는 방법과 위치를 이해합니다.

**필요한 앱**--플랫폼에 따라 최소한의 사용자 작업으로 장치에 설치되며, 관리자에게 필요한 앱입니다.

**사용 가능한 앱**--회사 포털 앱 목록에 제공되며, 사용자가 필요에 따라 선택하여 설치할 수 있는 앱입니다.

**관리되는 앱**--정책을 통해 관리할 수 있고 Intune에서 "래핑"했거나 Intune MAM(Mobile Application Management) SDK(소프트웨어 개발 키트)로 빌드된 앱입니다. 이러한 앱은 Intune에서 관리할 수 있고, 응용 프로그램 정책을 적용할 수 있습니다.

**관리되지 않는 앱**--정책을 통해 관리할 수 있고 Intune에서 래핑되지 않았거나 Intune MAM SDK를 통합하지 않은 앱입니다. 응용 프로그램 정책을 이러한 앱에 적용할 수 없습니다.

Apple 제한에 따라 기간 업무 앱과 관리되는 App Store 앱을 회사 포털 앱에 올릴 수 없습니다. 이 문제를 해결하기 위해 iOS용 회사 포털 앱의 타일이 종류에 관계없이 모든 앱에 대해 단일 위치(회사 포털 웹 사이트)에서 서로 다른 보기를 가리킵니다.

등록된 사용자는 회사 포털 앱의 앱 화면에서 다음 타일을 탭하여 앱을 얻습니다.

- **모든 앱**은 [회사 포털 웹 사이트](http://portal.manage.microsoft.com)의 모두 탭에 있는 모든 앱 목록을 가리킵니다.

- **추천 앱**을 선택하면 회사 포털 웹 사이트의 추천 탭으로 이동합니다.

- **범주**는 회사 포털 웹 사이트의 범주 탭을 가리킵니다.

 
![iOS 회사 포털 앱 화면](./media/ios-cp-app-main-apps-screen.png)

앱을 추가하고 이러한 타일에 삽입하는 방법에 대한 자세한 내용은 [Intune에 등록된 장치용 앱 추가](https://docs.microsoft.com/intune/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune.md)를 참조하세요.

### <a name="see-also"></a>참고 항목
[Android 사용자가 앱을 얻는 방법](how-your-android-users-get-their-apps.md)

[Windows 사용자가 앱을 얻는 방법](how-your-windows-users-get-their-apps.md)



<!--HONumber=Nov16_HO1-->


