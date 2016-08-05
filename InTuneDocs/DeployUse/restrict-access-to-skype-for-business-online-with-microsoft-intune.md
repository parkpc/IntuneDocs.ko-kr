---
title: "비즈니스용 Skype Online에 대한 액세스 제한 | Microsoft Intune"
description: "조건부 액세스로 비즈니스용 Skype Online을 보호하고 액세스를 제어합니다."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1b2d7125-f63f-43cf-ac1e-94fbedf2a7e8
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: be1ebcdf2514e45d383dd49890e0e21acf6ede44
ms.openlocfilehash: 27d993974d71b34b36cbd3216b83a1303689bf15


---

# Microsoft Intune을 사용하여 비즈니스용 Skype Online에 대한 액세스 제한
**비즈니스용 Skype Online**에 대한 조건부 액세스 정책을 사용하여 비즈니스용 Skype Online에 대한 액세스를 제어합니다.
조건부 액세스에는 두 구성 요소가 포함되어 있습니다.
- 장치를 준수로 간주하기 위해 장치가 준수해야 하는 장치 규정 준수 정책
- 장치에서 서비스에 액세스하기 위해 충족해야 하는 조건을 지정하는 조건부 액세스 정책
조건부 액세스가 어떻게 작동하는지에 대한 자세한 내용은 [전자 메일 및 O365 서비스에 대한 액세스 제한](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) 문서를 읽어보세요.

대상 사용자가 장치에서 비즈니스용 Skype Online을 사용하려고 시도하는 경우 다음 평가가 발생합니다.

![장치가 비즈니스용 Skype Online 대한 액세스를 허용 또는 차단할지를 결정하는 데 사용되는 결정 지점을 보여 주는 다이어그램](../media/ConditionalAccess_SkypeforBusiness.png)

비즈니스용 Skype Online에 대한 조건부 액세스 정책을 구성하기 **전에** 다음을 수행해야 합니다.
- **비즈니스용 Skype Online 구독**이 있고 비즈니스용 Skype Online 라이선스를 사용자에게 할당해야 합니다.
- **Enterprise Mobility Suite** 또는 **Azure Active Directory Premium**에 대한 구독이 있어야 합니다.
-   비즈니스용 Skype Online에 대해 [최신 인증을 사용하도록 설정](https://docs.microsoft.com/en-us/intune/deploy-use/restrict-access-to-skype-for-business-online-with-microsoft-intune)합니다.
-  모든 최종 사용자가 **비즈니스용 Skype Online**을 사용 중이어야 합니다. 비즈니스용 Skype Online과 비즈니스용 Skype 온-프레미스를 함께 배포한 경우 최종 사용자에게 조건부 액세스 정책이 적용되지 않습니다.

    비즈니스용 Skype Online에 액세스해야 하는 장치는 다음과 같아야 합니다.

-   **Android** 또는 **iOS** 장치여야 합니다.

-   [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]에 **등록**되어 있어야 합니다.

-   배포된 모든 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] 규정 준수 정책을 **준수**해야 합니다.


장치 상태는 지정한 조건에 따라 액세스를 부여하거나 차단하는 Azure Active Directory에 저장됩니다.

조건이 충족되지 않으면 사용자가 로그인할 때 다음 메시지 중 하나가 표시됩니다.

-   장치를 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]에 등록하지 않았거나 Azure Active Directory에 등록하지 않은 경우, 회사 포털 앱을 설치하고 등록하는 방법에 관한 지침이 포함된 메시지가 표시됩니다.

-   장치가 규정을 준수하지 않으면 사용자가 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] 회사 포털 웹 사이트 또는 회사 포털 앱으로 이동하는 메시지가 표시되며 여기에서 문제에 대한 정보와 이를 해결하는 방법을 확인할 수 있습니다.

## 비즈니스용 Skype Online에 대한 조건부 액세스 구성

### 1단계: Active Directory 보안 그룹 구성
시작하기 전에 조건부 액세스 정책에 대한 Azure Active Directory 보안 그룹을 구성합니다. **Office 365 관리 센터**에서 이러한 그룹을 구성할 수 있습니다. 이러한 그룹을 대상에 사용하거나 정책에서 사용자를 제외합니다. 사용자가 정책의 대상인 경우 해당 사용자가 사용하는 각 장치가 규정을 준수해야 리소스에 액세스할 수 있습니다.

비즈니스용 Skype 정책에 사용할 두 가지 그룹 유형을 지정할 수 있습니다.

-   **대상 그룹** – 정책이 적용되는 사용자 그룹을 포함합니다.

-   **제외된 그룹** – 정책에서 제외되는 사용자 그룹을 포함합니다.

사용자가 두 그룹에 모두 속한 경우에는 정책에서 제외됩니다.

### 2단계: 준수 정책 구성 및 배포
정책의 영향을 받을 모든 장치에 규정 준수 정책을 [만들고](create-a-device-compliance-policy-in-microsoft-intune.md) [배포](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md)합니다. **대상 그룹**에서 사용자가 사용하는 모든 장치가 됩니다.

> [!NOTE]
> 규정 준수 정책을 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] 그룹에 배포하는 동안 Azure Active Directory 보안 그룹을 조건부 액세스 정책의 대상으로 합니다.


> [!IMPORTANT]
> 규정 준수 정책을 배포하지 않은 경우 장치는 준수하는 것으로 간주됩니다.

준비가 되었으면 **3단계**를 계속합니다.

### 3단계: 비즈니스용 Skype Online 정책 구성
다음으로 관리되고 규정을 준수하는 장치만 비즈니스용 Skype Online에 액세스할 수 있도록 요구하는 정책을 구성합니다. 이 정책은 Azure Active Directory에 저장됩니다.

####
1.  [Microsoft Intune 관리 콘솔](https://manage.microsoft.com)에서 **정책** > **조건부 액세스** > **비즈니스용 Skype Online 정책**을 클릭합니다.

![비즈니스용 Skype Online 조건부 액세스 정책 페이지의 스크린샷](./media/conditional_access_SFBPolicy.png)

2.  **조건부 액세스 정책 사용**을 선택합니다.

3.  **응용 프로그램 액세스** 아래에서 다음 플랫폼에 조건부 액세스 정책을 적용하도록 선택할 수 있습니다.

    -   **iOS**

    -   **Android**

4.   **대상 그룹**에서 **수정** 을 클릭하여 정책을 적용할 Azure Active Directory 보안 그룹을 선택합니다. 모든 사용자 또는 선택한 사용자 그룹을 대상으로 지정할 수 있습니다.

5.   **제외된 그룹**에서 필요에 따라 **수정** 을 클릭하여 이 정책에서 제외된 Azure Active Directory 보안 그룹을 선택합니다.

6.  작업이 끝나면 **저장**을 클릭합니다.

이제 비즈니스용 Skype Online에 대한 조건부 액세스를 구성했습니다. 조건부 액세스 정책을 배포할 필요는 없으며, 즉시 적용됩니다.


## 준수 및 조건부 액세스 정책 모니터링
**그룹** 작업 영역에서 장치의 조건부 액세스 상태를 볼 수 있습니다.

모든 모바일 장치 그룹을 선택하고 **장치** 탭에서 다음 **필터**중 하나를 선택합니다.

* **AAD에 등록되지 않은 장치** – 이러한 장치는 비즈니스용 Skype Online에서 차단됩니다.

* **규정을 준수하지 않는 장치** – 이러한 장치는 비즈니스용 Skype Online에서 차단됩니다.

* **AAD에 등록되어 있고 규정을 준수하는 장치** – 이러한 장치는 비즈니스용 Skype Online에 액세스할 수 있습니다.



<!--HONumber=Jul16_HO5-->


