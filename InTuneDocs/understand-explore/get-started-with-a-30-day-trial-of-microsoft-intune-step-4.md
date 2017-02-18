---
title: "정책 만들기 및 사용자에게 앱 게시 | Microsoft 문서"
description: "Intune 무료 30일 평가판을 등록할 때 정책을 만들고 앱을 게시하는 방법"
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 12/12/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c3a17884-442a-44f5-bc81-4589e823f65e
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 53b05e0ad1be63315dcb5e5b9938a7d9459cb6c3
ms.openlocfilehash: edcef68c4dd6715c0e3b7c8a164d6266d1c154ae


---


# <a name="create-policies-and-publish-an-app-to-evaluation-users"></a>정책 만들기 및 평가판 사용자에게 앱 게시

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune 정책은 모바일 장치에 대한 보안 설정을 제어하고, 컴퓨터에 대한 Windows 방화벽 및 Endpoint Protection 설정을 유지하고, 응용 프로그램을 배포하는 데 사용할 수 있는 설정을 제공합니다. 평가판 사용 이후 프로덕션 환경에서 사용하도록 구성하는 장치에 대해 Intune을 사용하려는 경우에는 [Microsoft Intune 정책을 사용하여 장치의 설정 및 기능 관리](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) 및 [Microsoft Intune용 Endpoint Protection을 사용한 Windows PC의 보안 유지 방법](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)의 지침을 따라야 합니다.

Intune을 사용하여 두 가지 유형의 앱 설치를 수행할 수 있습니다. 그 중 첫 번째는 관리되는 장치에 앱을 자동으로 배포하는 **필수 설치**입니다. 다른 하나는 사용자가 앱을 컴퓨터에 설치할지 아니면 모바일 장치에 설치할지를 선택할 수 있도록 해당 앱 또는 앱의 링크를 Intune 회사 포털에 배포하는 **사용 가능한 설치**입니다.

Intune을 사용하여 앱을 배포하기 전에 앱 게시, 배포 및 사용을 위해 적합한 라이선스가 있는지 확인하세요. **라이선스** 작업 영역에서 Microsoft 볼륨 라이선스 계약을 통해 구매한 앱이나 소프트웨어와는 다른 방법으로 구매한 Microsoft 소프트웨어나 타사 앱 또는 소프트웨어에 대한 사용권 계약 정보를 추가하고 관리할 수 있습니다. 그런 다음 라이선스 사용 작업에 대한 정보를 받을 수 있도록 회사 전체의 관리되는 라이선스 사용 정보를 표시하는 라이선스 보고서를 만들 수 있습니다.

이 단계에서는 모바일 장치 구성 정책과 Windows 컴퓨터 방화벽 정책을 설정하고, 모바일 장치를 등록한 후 장치에 대해 사용 가능한 설치로 Skype를 구성합니다. 새 정책을 추가 및 배포하고 나면 정책을 배포한 그룹 내의 모든 사용자나 장치가 설정을 기준 정책으로 상속합니다. 나중에 관리 콘솔의 **정책** 작업 영역에서 언제든지 이러한 정책의 세부 정보를 검토하고 편집할 수 있습니다.

## <a name="create-and-deploy-a-mobile-device-configuration-policy"></a>모바일 장치 구성 정책 만들기 및 배포

1.  [Intune 관리 콘솔](https://manage.microsoft.com/)을 엽니다.

2.  왼쪽 창에서 **정책** 아이콘을 선택합니다.

3.  **정책 개요** 페이지의 **작업** 목록에서 **정책 추가**를 선택합니다.

4.  정책 목록에서 정책을 만들 플랫폼을 확장하고 **일반 구성**, **사용자 지정 정책 만들기 및 배포**를 차례로 선택한 후에 **정책 만들기**를 선택합니다.

5.  **이 정책을 배포할 그룹을 선택합니다.** 메시지가 나타나면 목록에서 **내 평가판 사용자**를 선택하고 **추가**&gt;**확인**을 선택합니다.

정책이 **내 평가판 사용자** 그룹에 배포되며 구성 정책 목록에 표시됩니다. 해당 설정을 보려면 정책을 두 번 클릭합니다.

## <a name="publish-the-skype-app-for-mobile-devices"></a>모바일 장치용으로 Skype 앱 게시

1.  [Intune 관리 콘솔](https://manage.microsoft.com/)에서 **앱** 아이콘을 선택한 다음 **앱** &gt; **앱 추가**를 선택합니다. 메시지가 표시되면 Intune 자격 증명을 입력합니다.

    > [!NOTE]
    > **Intune 소프트웨어 게시자** 를 처음으로 시작할 때에는 응용 프로그램이 설치되는 동안 짧은 지연이 발생합니다.

2.  보안 경고를 검토하고 **실행**을 선택합니다.

3.  **시작하기 전에** 페이지에서 **다음**을 선택합니다.

4.  **소프트웨어 설치** 페이지의 **이 소프트웨어를 장치에 사용하도록 설정하는 방법 선택**에서 **외부 링크**를 선택합니다.

5.  **URL 지정**에 소프트웨어의 외부 링크를 입력한 후 **다음**을 선택합니다. URL 앞에 **https://**가 추가되었는지 확인합니다. Skype 앱의 경우 사용 중인 모바일 장치 플랫폼과 일치하는 아래의 링크를 사용합니다.

    -   **iOS:** [https://itunes.apple.com/us/app/skype-for-iphone/id304878510?mt%3D8](https://itunes.apple.com/us/app/skype-for-iphone/id304878510?mt%3D8)

    -   **Android:** [https://play.google.com/store/apps/details?id=com.skype.raider](https://play.google.com/store/apps/details?id=com.skype.raider)

    -   **Windows Phone 8.1:** [http://www.windowsphone.com/en-us/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51](http://www.windowsphone.com/en-us/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51)

6.  **소프트웨어 설명** 페이지에서 회사 포털의 소프트웨어 사용자에게 표시할 정보를 입력한 후 **다음**을 선택합니다. 다음 설정을 사용할 수 있습니다. 이 예제에서는 앱이 Skype라고 가정합니다.

    -   **게시자:** 게시자 이름으로 **Microsoft**를 입력합니다.

    -   **이름:** **Skype**를 입력합니다.

    -   **설명:** **Skype 통신 앱** 등의 소프트웨어 설명을 입력합니다.

    -   **범주:** 이 소프트웨어에 가장 잘 맞는 범주(예: **공동 작업**

    -   **회사 포털에서 이 항목을 추천 앱 및 하이라이트로 표시합니다.** 이 옵션을 선택하면 앱이 모바일 장치의 회사 포털에서 눈에 띄게 표시됩니다.

    -   **아이콘:** (선택 사항) 소프트웨어에 아이콘을 연결할지 선택합니다. 최대 아이콘 크기는 250x250 픽셀이지만 권장 아이콘 크기는 32x32 픽셀입니다.

7.  **요약** 페이지에서 소프트웨어 정보를 확인한 후 **업로드**를 선택합니다. **닫기**를 선택하여 마법사를 종료합니다.

8.  [Intune 관리 콘솔](https://manage.microsoft.com/)에서 **앱** &gt; **앱** &gt; **Skype** &gt; **배포 관리**를 선택합니다.

9. **그룹 선택** 페이지에서 **내 평가판 사용자**를 선택하여 해당 사용자 그룹에 소프트웨어를 배포한 후 **추가** &gt; **다음**을 선택합니다.

10. **배포 작업** 페이지에 있는 그룹의 **승인** 열에서 **사용 가능한 설치** 를 선택합니다.

11. **마침**을 선택합니다.

## <a name="install-the-skype-app"></a>Skype 앱 설치
모바일 장치에서 회사 포털을 열고 **앱**을 선택한 후 Microsoft Skype를 설치합니다.

이것으로 Intune 모바일 장치 관리 가이드를 마칩니다. 다음 단계 섹션의 링크를 따라 Intune에 대해 보다 자세히 알아볼 수 있습니다.
## <a name="next-steps"></a>다음 단계
[Intune 기능](get-started-with-a-30-day-trial-of-microsoft-intune-step-6.md)에 대한 자세한 정보

[Intune을 사용하는 일반적인 방법](common-ways-to-use-intune.md) 읽어보기

[유료 구독](get-started-with-a-30-day-trial-of-microsoft-intune-step-7.md)으로 전환



<!--HONumber=Dec16_HO2-->


