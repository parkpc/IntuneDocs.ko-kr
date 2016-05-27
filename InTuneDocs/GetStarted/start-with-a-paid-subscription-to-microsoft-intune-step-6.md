---
# required metadata

title: 정책 만들기 및 앱 게시 | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: e0d8e98f-7dd8-4cbf-887c-a9af63ffe970

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# 정책 만들기 및 앱 게시
Intune 정책은 모바일 장치에 대한 보안 설정을 제어하고, 컴퓨터에 대한 Windows 방화벽 및 Endpoint Protection 설정을 유지하고, 응용 프로그램을 배포하는 데 사용할 수 있는 설정을 제공합니다. [Microsoft Intune 정책을 사용하여 장치의 설정 및 기능 관리](/Intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) 및 [Microsoft Intune용 Endpoint Protection을 사용한 Windows PC의 보안 유지 방법](/Intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)에서 자세한 내용을 알아볼 수 있습니다..

Intune을 사용하여 두 가지 유형의 앱 설치를 수행할 수 있습니다. 그 중 첫 번째는 관리 컴퓨터에 앱을 자동으로 배포하는 **필수 설치**입니다. 다른 하나는 사용자가 앱을 컴퓨터에 설치할지 아니면 모바일 장치에 설치할지를 선택할 수 있도록 해당 앱 또는 앱의 링크를 Intune 회사 포털에 배포하는 **사용 가능한 설치**입니다.

<!-- this section really isn't necessary and confuses a lot of people because most mobile device apps aren't licensed this way (and our licensing/reporting features aren't super helpful). I think it's best to avoid this during a quick start guide.

Before using Intune to deploy apps, make sure that you have the appropriate licenses to publish, distribute, and use the app. The Licenses workspace lets you add and manage license agreement information for apps or software purchased through Microsoft Volume Licensing agreements, and for Microsoft or non-Microsoft software that was purchased by other means. You can then create license reports that display managed license usage information throughout your company to stay informed of license usage activity.
-->

아래 단계에서는 모바일 장치 구성 정책과 Windows PC 방화벽 정책을 설정하고, 모바일 장치를 등록한 후 장치에 대해 사용 가능한 설치로 Skype를 구성합니다.

> [!TIP]
> 새 정책을 추가 및 배포하고 나면 정책을 배포한 그룹 내의 모든 사용자나 장치가 설정을 기준 정책으로 상속합니다. 나중에 정책 작업 영역에서 언제든지 이러한 정책의 세부 정보를 검토하고 편집할 수 있습니다.


## 모바일 장치 구성 정책 만들기 및 배포

1.  [Intune 관리 콘솔](https://manage.microsoft.com/)을 엽니다..

2.  왼쪽 창에서 **정책** 아이콘을 선택합니다.

    ![admin-console-policy-workspace](./media/policy.png)

3.  **정책 개요** 페이지의 **작업** 목록에서 **정책 추가**를 선택합니다..

4.  정책 목록에서 정책을 만들 플랫폼을 확장하고 **일반 구성** > **권장 설정으로 정책 만들기 및 배포** > **정책 만들기**를 클릭합니다..

5.  **이 정책을 배포할 그룹을 선택합니다.**라는 메시지가 표시되면 사용 가능한 그룹 목록에서 **Intune 사용자**(이전 단계에서 만든 그룹)을 선택하고 **추가** > **확인**을 선택합니다..

정책이 **Intune 사용자** 그룹에 배포되며 구성 정책 목록에 표시됩니다. 해당 설정을 보려면 정책을 두 번 클릭합니다.

## 모바일 장치용으로 Skype 앱 게시

1.  [Intune 관리 콘솔](https://manage.microsoft.com/)에서 **앱** 아이콘을 선택한 다음 **앱** > **앱 추가**를 선택합니다. 메시지가 표시되면 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] 자격 증명을 입력합니다.

    ![admin-console-apps-workspace](./media/apps.png)

    > [!NOTE]
    > **Intune 소프트웨어 게시자** 를 처음으로 시작할 때에는 응용 프로그램이 설치되는 동안 짧은 지연이 발생합니다.

2.  보안 경고를 검토하고 **실행**을 선택합니다..

3.  **시작하기 전에** 페이지에서 **다음**을 선택합니다..

4.  **소프트웨어 설치** 페이지의 **이 소프트웨어를 장치에 사용하도록 설정하는 방법 선택**에서 **외부 링크**를 선택합니다..

5.  **URL 지정**에 소프트웨어의 외부 링크를 입력한 후 **다음**을 선택합니다. URL 앞에 **http://**가 추가되었는지 확인합니다. Skype 앱의 경우 사용 중인 모바일 장치 플랫폼과 일치하는 아래의 링크를 사용합니다.

    -   **iOS:**   [https://itunes.apple.com/us/app/skype-for-iphone/id304878510?mt%3D8](https://itunes.apple.com/us/app/skype-for-iphone/id304878510?mt%3D8)

    -   **Android:**  [https://play.google.com/store/apps/details?id=com.skype.raider](https://play.google.com/store/apps/details?id=com.skype.raider)

    -   **Windows Phone 8 또는 Windows Phone 8.1:**  [http://www.windowsphone.com/en-us/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51](http://www.windowsphone.com/en-us/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51)

6.  **소프트웨어 설명** 페이지에서 회사 포털의 소프트웨어 사용자에게 표시할 정보를 입력한 후 **다음**을 선택합니다. 다음 설정을 사용할 수 있습니다. 이 예제에서는 앱이 Skype라고 가정합니다.

    -   **게시자:** 게시자 이름으로 “Microsoft”를 입력합니다.

    -   **이름:** **Skype**를 입력합니다.

    -   **설명:** **Skype 통신 앱** 등의 소프트웨어 설명을 입력합니다.

    -   **범주:** 이 소프트웨어에 가장 잘 맞는 범주(예: **공동 작업**

    -   **회사 포털에서 이 항목을 추천 앱 및 하이라이트로 표시합니다.** 이 옵션을 선택하면 앱이 모바일 장치의 회사 포털에서 눈에 띄게 표시됩니다.

    -   **아이콘:** 아이콘을 소프트웨어와 연결할지 여부를 선택합니다. 선택적인 아이콘의 최대 크기는 250x250 픽셀이고 권장 크기는 32x32 픽셀입니다.

7.  **요약** 페이지에서 소프트웨어 정보를 확인한 후 **업로드**를 선택합니다. **닫기**를 선택하여 마법사를 종료합니다.

8.  [Intune 관리 콘솔](https://manage.microsoft.com/)에서 **앱** > **앱** > **Skype** > **배포 관리**를 선택합니다..

9. **그룹 선택** 페이지에서 **Intune 사용자**를 선택하여 해당 사용자 그룹에 소프트웨어를 배포한 후 **추가** > **다음**을 선택합니다..

10. **배포 작업** 페이지에 있는 그룹의 **승인** 열에서 **사용 가능한 설치** 를 선택합니다.

11. **마침**을 선택합니다..

이제 회사 포털에서 Skype 앱을 모바일 장치에 설치할 수 있지만, 그러려면 먼저 컴퓨터와 모바일 장치에 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] 소프트웨어를 설치해야 합니다.


### 다음 단계
축하합니다. Intune 빠른 시작 가이드의 6단계를 완료했습니다..

>[!div class="step-by-step"]

>[&larr; **사용자 및 장치 구성**](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)       [**회사 포털 사용자 지정** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-7.md)  


<!--HONumber=May16_HO1-->


