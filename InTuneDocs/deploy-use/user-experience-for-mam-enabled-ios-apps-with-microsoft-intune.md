---
title: "앱 보호 정책을 사용하는 iOS 앱 | Microsoft Docs"
description: "이 항목에서는 앱 보호 정책을 통해 iOS 앱이 관리될 때 예상되는 결과를 설명합니다."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 03/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b57e6525-b57c-4cb4-a84c-9f70ba1e8e19
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 665d3347636d5ec0c698ffb93b768028c9d59ce3
ms.openlocfilehash: fba18027039a0e49c5301f9d1a16947e97408034
ms.lasthandoff: 03/07/2017


---

# <a name="what-to-expect-when-your-ios-app-is-managed-by-app-protection-policies"></a>iOS 앱이 앱 보호 정책으로 관리될 때 예상되는 상황

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

 이 항목에서는 앱 보호 정책이 적용되는 앱에 대한 사용자 환경을 설명합니다. 앱 보호 정책은 사용자가 회사 계정을 사용하여 앱에 액세스하거나 회사의 OneDrive 비즈니스 위치에 저장된 파일에 액세스하는 경우처럼 앱이 업무용으로 사용될 때만 적용됩니다.

##  <a name="access-apps"></a>앱 액세스

장치가 **Intune에 등록되지 않은** 경우 사용자가 앱을 처음 사용할 때 앱을 다시 시작하라는 메시지가 표시됩니다.  앱 보호 정책을 앱에 적용할 수 있도록 앱을 다시 시작해야 합니다. 

<!--- The following screenshot from the Skype app illustrates this restart request: --->


<!---  ![Screenshot of the iOS device showing PIN prompt](../media/appmanagement/iOS_AppPINPrompt.png) --->

**Intune에서 관리를 위해 등록**된 장치의 경우 사용자에게 앱이 현재 관리되고 있다는 메시지가 표시됩니다.

##  <a name="use-apps-with-multi-identity-support"></a>다중 ID가 지원되는 앱 사용

앱 보호 정책은 앱을 업무용으로 사용할 때만 적용됩니다. 즉, 앱을 업무용으로 사용하는지 아니면 개인용으로 사용하는지에 따라 작동 방식이 달라질 수 있습니다.

 예를 들어 사용자가 업무 데이터에 액세스하면 PIN 프롬프트가 표시됩니다. **Outlook 앱**에서는 사용자가 앱을 시작할 때 PIN을 입력하라는 메시지가 표시됩니다. **OneDrive 앱**에서는 사용자가 회사 계정을 입력할 때 PIN을 입력하라는 메시지가 표시됩니다.  Microsoft **Word**, **PowerPoint** 및 **Excel**의 경우에는 사용자가 회사의 비즈니스용 OneDrive 위치에 저장된 문서에 액세스할 때 PIN을 입력하라는 메시지가 표시됩니다.

##  <a name="manage-user-accounts-on-the-device"></a>장치에서 사용자 계정 관리

Intune에서는 장치당 하나의 사용자 계정에만 앱 보호 정책을 배포할 수 있습니다.

* 사용 중인 앱에 따라 두 번째 사용자는 장치에서 차단될 수 있습니다. 그러나 어떤 경우이든 앱 보호 정책을 가져오는 첫 번째 사용자만이 정책에 영향을 받습니다.
  * **Microsoft Word**, **Excel** 및 **PowerPoint**는 두 번째 사용자 계정을 차단하지 않지만 두 번째 사용자 계정은 앱 보호 정책의 영향을 받지 않습니다.  

  * **OneDrive** 및 **Outlook 앱**의 경우 회사 계정을 하나만 사용할 수 있습니다. 이러한 앱용으로 회사 계정을 여러 개 추가할 수는 없습니다. 그러나 사용자를 제거하고 장치에 다른 사용자를 추가할 수 있습니다.

* 앱 보호 정책을 배포하기 전에 장치에 기존의 여러 사용자 계정이 있으면 첫 번째 사용자에게 앱 보호 정책을 배포하는 계정은 Intune 앱 보호 정책에 의해 관리됩니다.


여러 사용자 계정이 처리되는 방법을 더욱 상세하게 파악하려면 다음 예제 시나리오를 확인하세요.

사용자 A는 **회사 X** 및 **회사 Y**에서 일합니다. 사용자 A는 각 회사에 회사 계정을 보유하고 둘 다 Intune을 사용하여 앱 보호 정책을 배포합니다. **회사 X**는 **회사 Y**보다 **먼저** 앱 보호 정책을 배포합니다. **회사 X**와 연결된 계정은 앱 보호 정책을 가져오지만 회사 Y와 연결된 계정은 앱 보호 정책을 가져오지 않습니다. 회사 Y와 연결된 사용자 계정을 앱 보호 정책으로 관리하려는 경우에는 회사 X와 연결된 사용자 계정을 제거해야 합니다.

### <a name="add-a-second-account"></a>두 번째 계정 추가

iOS 장치를 사용하는 경우 해당 장치에 두 번째 회사 계정을 추가하려고 하면 차단 메시지가 표시될 수 있습니다. 이 경우 계정이 표시되면 제거할 계정을 선택할 수 있습니다.

## <a name="next-steps"></a>다음 단계
[Android 앱이 앱 보호 정책으로 관리될 때 예상되는 상황](user-experience-for-mam-enabled-android-apps-with-microsoft-intune.md)
### <a name="see-also"></a>참고 항목
[Microsoft Intune으로 모바일 앱 관리 정책 만들기 및 배포](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)

