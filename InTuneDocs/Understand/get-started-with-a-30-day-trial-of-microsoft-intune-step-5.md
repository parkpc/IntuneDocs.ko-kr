---
title: "평가판 모바일 장치 등록 | Microsoft Intune"
description: "Intune 무료 30일 평가판을 등록할 때 모바일 장치를 등록하고 앱을 설치하는 방법"
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 08/09/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47806f69-303d-41d9-9b0e-9b9445ea24ac
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 581e880fa4308ec627f5b2c1242fb5b30b713743
ms.openlocfilehash: 7bd5f5d8f4931133a8ef1e697b2fec4cccd07b83


---

# 평가판 모바일 장치 등록 및 앱 설치
Intune을 사용하여 모바일 장치 관리를 설정하려면 먼저 모바일 장치 관리 기관을 설정하고, 장치 플랫폼에 대한 관리를 사용하도록 설정한 다음, 회사 포털 앱을 사용하여 장치를 등록해야 합니다. 그러면 게시한 Microsoft Skype 응용 프로그램을 배포할 수 있습니다.

## 장치 관리를 위한 서비스 준비

1.  **Intune을 모바일 장치 관리 기관으로 설정**

    [Intune 관리 콘솔](https://manage.microsoft.com/)에서 **관리** &gt; **모바일 장치 관리**를 선택합니다. **작업** > **MDM 기관 설정**을 선택한 다음 **MDM 기관** 대화 상자에서 **예**를 선택합니다.

2.  **장치 플랫폼에 MDM을 사용하도록 설정**

    관리하려는 장치 플랫폼에 대해 모바일 장치 관리를 사용하도록 설정합니다. 플랫폼에 따라 각기 다른 요구 사항을 충족해야 합니다.

    -   **iOS 및 Mac OS X**: [Microsoft Intune을 사용한 iOS 및 Mac 관리 설정](/Intune/Deploy-Use/set-up-ios-and-mac-management-with-microsoft-intune)을 참조하세요.

    -   **Android**: Android 모바일 장치에서는 사용자가 Google Play에서 제공되는 회사 포털 앱을 사용하여 등록할 수 있습니다. Intune에서는 추가 구성을 수행할 필요가 없습니다.

    -   **Windows Phone**: [Microsoft Intune을 사용한 Windows Phone 관리 설정](/Intune/Deploy-Use/set-up-windows-phone-management-with-microsoft-intune)을 참조하세요.

## 테스트 장치 등록

### iOS 및 Mac OS X
App Store에서 Microsoft Corporation의 **Microsoft Intune 회사 포털** 앱을 설치하고 위에서 추가한 Intune 사용자 자격 증명을 사용하여 로그인합니다. **등록된 장치**를 확인하고 자신의 장치를 추가합니다.

### Android
[Google Play](http://go.microsoft.com/fwlink/p/?LinkId=386612)에서 사용할 수 있는 Microsoft Corporation의 **Intune 회사 포털** 앱을 설치하고 위에서 추가한 Intune 사용자 자격 증명을 사용하여 로그인합니다.

### Windows Phone 8.1
사용자는 Windows Phone스토어에서 사용할 수 있는 Microsoft Corporation의 **회사 포털** 앱을 설치하고 위에서 추가한 Intune 사용자 자격 증명을 사용하여 로그인합니다.  **등록된 장치**를 확인하고 자신의 장치를 추가합니다.

## 이전에 배포된 앱 설치
모바일 장치에서 회사 포털을 열고 **앱**을 선택한 후 **Microsoft Skype**를 설치합니다.

Intune을 사용하는 모바일 장치 관리에 대한 자세한 내용은 [Microsoft Intune에 장치를 등록하도록 준비](/Intune/deploy-use/prerequisites-for-enrollment)를 참조하세요.

### 다음 단계
축하합니다. *Microsoft Intune 평가판* 연습의 5단계를 완료했습니다.

>[!div class="step-by-step"]

>[&larr; **정책 만들기**](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-4.md)     [**옵션 및 추가 기능** &rarr;](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-6.md)  



<!--HONumber=Oct16_HO2-->


