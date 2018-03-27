---
title: "Android 사용자가 앱을 얻는 방법 | Microsoft 문서"
description: "최종 사용자에게 Android 앱을 제공하기 위한 방법"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33d1684-b1b5-44f7-9aac-c6d5186a5d7c
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 370dd5d4a96253f0b7d208ef85659beeace18739


---


# <a name="how-your-android-users-get-their-apps"></a>Android 사용자가 앱을 얻는 방법

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

이 정보를 사용하여 최종 사용자가 Microsoft Intune을 통해 배포하는 Android 앱을 얻는 방법과 위치를 이해합니다. 해당 정보는 네이티브 Android 장치와 Samsung Knox Standard 장치 등 장치 유형에 따라 다를 수 있습니다.

## <a name="native-non-samsung-knox-standard-android-devices"></a>네이티브(비 Samsung Knox 표준) Android 장치

| 앱 유형 | LOB(기간 업무) 앱 | Play 스토어 앱  |
| ------------- |-------------| -----|
| 사용 가능한 앱      | 회사 포털에서 **설치**를 누릅니다. 설치를 시작하려면 누르라는 알림이 나타납니다. 설치가 정상적으로 수행되면 알림이 사라집니다. | 사용자가 회사 포털에서 앱을 누르면 설치를 시작할 수 있는 Play 스토어의 앱 페이지로 이동됩니다.|
| Required apps      | 사용자에 앱을 설치해야 함을 나타내는 알림이 표시되며 이 알림은 해제할 수 없습니다. 설치를 시작하려면 알림을 누릅니다. 설치가 정상적으로 수행되면 알림이 사라집니다.    | 사용자에 앱을 설치해야 함을 나타내는 알림이 표시되며 이 알림은 해제할 수 없습니다. 알림을 누르며 설치를 시작할 수 있는 Play 스토어의 앱 페이지로 이동됩니다. 설치가 정상적으로 수행되면 알림이 사라집니다. |

## <a name="samsung-knox-standard-android-devices"></a>Samsung Knox Standard Android 장치

| 앱 유형 | LOB(기간 업무) 앱 | Play 스토어 앱  |
| ------------- |-------------| -----|
| 사용 가능한 앱      | 회사 포털에서 **설치**를 누릅니다. 추가 사용자 작업 없이도 앱이 설치됩니다. | 사용자가 회사 포털에서 앱을 누르면 설치를 시작할 수 있는 Play 스토어의 앱 페이지로 이동됩니다.|
| Required apps      | 추가 사용자 작업 없이도 앱이 설치됩니다.    | 사용자에 앱을 설치해야 함을 나타내는 알림이 표시되며 이 알림은 해제할 수 없습니다. 알림을 누르며 설치를 시작할 수 있는 Play 스토어의 앱 페이지로 이동됩니다. 설치가 정상적으로 수행되면 알림이 사라집니다. |

아래와 같이 앱은 관리되거나 관리되지 않을 수 있습니다. 앱을 관리되는 앱으로 만드는 프로세스는 모든 종류의 Android 장치에 대해 동일합니다.

**관리되는 앱** - 정책을 통해 관리할 수 있는 앱입니다. Intune에서 "래핑"했거나 Intune MAM(Mobile Application Management) SDK(소프트웨어 개발 키트)로 빌드되었습니다. 이러한 앱은 Intune에서 관리할 수 있고, 응용 프로그램 정책을 적용할 수 있습니다.

**관리되지 않는 앱** - 정책을 통해 관리할 수 없는 앱입니다. Intune에서 래핑되지 않았거나 Intune MAM SDK를 통합하지 않았습니다. 응용 프로그램 정책을 이러한 앱에 적용할 수 없습니다.

### <a name="see-also"></a>참고 항목
[Microsoft Intune을 사용하여 앱 추가](/intune/deploy-use/add-apps)

[iOS 사용자가 앱을 얻는 방법](how-your-ios-users-get-their-apps.md)

[Windows 사용자가 앱을 얻는 방법](how-your-windows-users-get-their-apps.md)



<!--HONumber=Dec16_HO2-->


