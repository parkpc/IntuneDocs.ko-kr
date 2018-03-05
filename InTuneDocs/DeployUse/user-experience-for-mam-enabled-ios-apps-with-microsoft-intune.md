---
title: "MAM 정책이 있는 iOS 앱 | Microsoft Intune"
description: "이 항목에서는 모바일 앱 관리 정책을 통해 iOS 앱이 관리될 때 예상되는 결과를 설명합니다."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 10/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b57e6525-b57c-4cb4-a84c-9f70ba1e8e19
ms.reviewer: andcerat
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 389daf0ed39fa2cd4b2e5d6e52cbd6809a568c9e
ms.openlocfilehash: 3f9d9c7cafcdac0db21e5ba35f713fe630c65b99


---

# iOS 앱이 MAM 정책으로 관리될 때 예상되는 상황
 이 항목에서는 MAM 정책이 있는 앱에 대한 사용자 환경을 설명합니다. MAM(모바일 응용 프로그램 관리) 정책은 회사 계정을 사용하여 앱에 액세스하거나 회사의 OneDrive 비즈니스 위치에 저장된 파일에 액세스하는 경우처럼 앱이 업무용으로 사용될 때만 적용됩니다.
##  앱 액세스

장치가 **Intune에 등록되지 않은** 경우 최종 사용자는 앱을 처음 사용할 때 앱을 다시 시작하도록 요구됩니다.  MAM 정책이 앱에 적용되려면 앱을 다시 시작해야 합니다. 다음 스크린샷은 Skype 앱을 사용하여 이러한 과정을 보여 줍니다.


![PIN 프롬프트를 보여 주는 iOS 장치의 스크린샷](../media/appmanagement/iOS_AppPINPrompt.png)

**Intune에서 관리를 위해 등록**된 장치의 경우 최종 사용자에게 앱이 현재 관리되고 있다는 메시지가 표시됩니다.

![PIN 프롬프트를 포함하는 회사 메시지에 의해 관리되는 iOS 장치를 보여 주는 스크린샷](../media/appmanagement/ios-managed-devices-pin-prompt.png)

##  다중 ID가 지원되는 앱 사용

MAM 정책은 업무용으로 앱을 사용할 때만 적용되므로 업무용인지 개인용인지에 따라 앱 동작이 달라질 수 있습니다.  

다중 ID를 지원하는 앱의 경우, Intune은 최종 사용자가 업무용으로 앱을 사용할 때만 MAM 정책을 적용합니다.  예를 들어 최종 사용자는 업무용 데이터에 액세스할 경우 PIN 프롬프트를 받습니다.  **Outlook 앱**에서는 최종 사용자가 앱을 시작할 때 PIN을 입력하라는 메시지가 표시됩니다. **OneDrive 앱**에서는 최종 사용자가 회사 계정을 입력할 때 PIN을 입력하라는 메시지가 표시됩니다.  Microsoft **Word**, **PowerPoint* 및 **Excel**의 경우에는 최종 사용자가 회사의 비즈니스용 OneDrive 위치에 저장된 문서에 액세스할 때 PIN을 입력하라는 메시지가 표시됩니다.
##  장치에서 사용자 계정 관리

Intune은 장치 당 하나의 사용자 계정에 MAM 정책을 배포하도록 지원합니다.

* 사용 중인 앱에 따라 두 번째 사용자는 장치에서 차단될 수도 있고 차단되지 않을 수도 있습니다. 그러나 어떤 경우이든 MAM 정책을 가져오는 첫 번째 사용자만이 정책에 영향을 받습니다.
  * **Microsoft Word**, **Excel** 및 **PowerPoint**는 두 번째 사용자 계정을 차단하지 않지만 두 번째 사용자 계정은 MAM 정책의 영향을 받지 않습니다.  

  * **OneDrive 및 Outlook 앱**의 경우 회사 계정을 하나만 사용할 수 있습니다.  해당 앱에서는 여러 회사 계정의 추가가 차단됩니다.  그러나 사용자를 제거하고 장치에 다른 사용자를 추가할 수 있습니다.

* MAM 정책을 배포하기 전에 장치에 기존의 여러 사용자 계정이 있으면 첫 번째 사용자에게 MAM 정책을 배포하는 계정은 Intune MAM 정책에 의해 관리됩니다.


여러 사용자 계정이 처리되는 방법을 더 깊게 이해하려면 아래 예제 시나리오를 참고합니다.

사용자 A는 **회사 X** 및 **회사 Y**에서 일합니다. 사용자 A는 각 회사에 회사 계정을 보유하고 둘 다 Intune를 사용하여 MAM 정책을 배포합니다. **회사 X**는 **회사 Y**보다 **먼저** MAM 정책을 배포합니다. **회사 X**와 연결된 계정은 MAM 정책을 가져오지만 회사 Y와 관련된 계정이 아닙니다. 회사 Y와 관련된 사용자 계정이 MAM 정책에 의해 관리되기를 바란다면 회사 X와 관련된 사용자 계정을 제거해야 합니다.
### 두 번째 계정 추가

iOS 장치를 사용하는 경우 동일한 장치에 두 번째 회사 계정을 추가하려고 하면 차단 메시지가 표시될 수 있습니다.  계정이 표시되고 제거하려는 계정을 선택할 수 있습니다.

![메시지 및 예 및 아니요 옵션을 차단하는 대화 상자의 스크린 샷](../media/AppManagement/iOS_SwitchUser.PNG)
## 다음 단계
[Android 앱이 MAM 정책으로 관리될 때 예상되는 상황](user-experience-for-mam-enabled-android-apps-with-microsoft-intune.md)
### 참고 항목
[Microsoft Intune으로 모바일 앱 관리 정책 만들기 및 배포](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Oct16_HO3-->


