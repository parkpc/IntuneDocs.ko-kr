---
# required metadata

title: 모바일 장치 등록 및 앱 설치 | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 5d3215e7-0a5c-44bd-afb0-aeafce98c43f

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# 모바일 장치 등록 및 앱 설치
Intune을 사용하여 모바일 장치 관리를 설정하려면 먼저 모바일 장치 관리 기관을 설정하고, 장치 플랫폼에 대한 관리를 사용하도록 설정한 다음, 회사 포털 앱을 사용하여 장치를 등록해야 합니다. 그러면 6단계에서 게시한 Microsoft Skype 응용 프로그램을 배포할 수 있습니다.

## 장치 관리를 사용하도록 설정하고 장치 등록

1.  **Intune을 모바일 장치 관리 기관으로 설정**
    [Intune 관리 콘솔](https://manage.microsoft.com/)에서 **관리** > **모바일 장치 관리**를 선택한 다음 **작업** 아래에서 **MDM 기관 설정** 선택합니다.  MDM 기관 대화 상자에서 **예**를 선택합니다.
    ![관리 콘솔. Intune에 MDM 설정](./media/mdmAuthority.png)

2.  **장치 플랫폼에 MDM을 사용하도록 설정**
    관리하려는 장치 플랫폼에 대해 모바일 장치 관리를 사용하도록 설정합니다. 플랫폼에 따라 각기 다른 요구 사항을 충족해야 합니다.

    -   **iOS 및 Mac OS X**: [Microsoft Intune을 사용한 iOS 및 Mac 관리 설정](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune)을 참조하세요..

    -   **Windows Phone**: [Microsoft Intune을 사용한 Windows Phone 관리 설정](/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune)을 참조하세요..

    -   **Android**: Android 모바일 장치에서는 사용자가 [Google Play](https://play.google.com/store/apps/details?id=com.skype.raider)에서 제공되는 회사 포털 앱을 사용하여 등록할 수 있습니다. Intune에서는 추가 구성을 수행할 필요가 없습니다.

3.  **장치 등록**:

    -   **Android** - [Google Play](http://go.microsoft.com/fwlink/p/?LinkId=386612)에서 사용할 수 있는 Microsoft Corporation의 **Intune 회사 포털** 앱을 설치하고 위에서 추가한 Intune 사용자 자격 증명을 사용하여 로그인합니다.

    -   **iOS 및 Mac OS X** - App Store에서 사용할 수 있는 Microsoft Corporation의 **Microsoft Intune 회사 포털** 앱을 설치하고 위에서 추가한 Intune 사용자 자격 증명을 사용하여 로그인합니다. **등록된 장치** 를 확인하고 자신의 장치를 추가합니다.

    -   **Windows Phone 8.1** - 사용자는 Windows Phone스토어에서 사용할 수 있는 Microsoft Corporation의 **회사 포털** 앱을 설치하고 위에서 추가한 Intune 사용자 자격 증명을 사용하여 로그인합니다.  **등록된 장치** 를 확인하고 자신의 장치를 추가합니다.

    -   **Windows Phone 8.0** - **시스템 설정** &gt; **회사 앱**을 선택하고 위에서 추가한 Intune 사용자 자격 증명을 사용하여 로그인합니다. 회사 포털 앱이 휴대폰에 배포됩니다.

    **서버 주소**에 대한 메시지가 표시되면 “manage.microsoft.com”을 입력합니다.

## 등록된 장치에 앱 설치
빠른 시작 가이드의 [6단계](start-with-a-paid-subscription-to-microsoft-intune-step-6.md)에서, Skype 앱을 사용자 지정 Intune 사용자 그룹에 게시했습니다. 이제 그 앱을 새로 등록된 장치에 설치하겠습니다.

등록된 모바일 장치에서 회사 포털을 열고 **앱**을 선택한 후 **Microsoft Skype**를 설치합니다..

[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]을 사용하는 모바일 장치 관리에 대한 자세한 내용은 [Microsoft Intune에 장치를 등록하도록 준비](/intune/deploy-use/get-ready-to-enroll-devices-in-microsoft-intune)를 참조하세요..


### 다음 단계
축하합니다. Intune 빠른 시작 가이드의 마지막 단계를 완료했습니다. 초기 구성을 완료했으니, 추가적인 MDM 기능 활성화를 고려할 수 있습니다.

>[!div class="step-by-step"]

>[&larr; **장치 등록**](.\start-with-a-paid-subscription-to-microsoft-intune-step-8.md)     [**구성 후 작업** &rarr;](.\post-configuration-tasks.md)  


<!--HONumber=May16_HO1-->


