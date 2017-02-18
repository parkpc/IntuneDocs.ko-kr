---
title: "Android for Work 앱 구성 정책 | Microsoft 문서"
description: "Intune에서 모바일 앱 구성 정책을 사용하여 사용자가 Android for Work 앱을 실행할 때 필요할 수도 있는 설정을 제공할 수 있습니다."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fc6b645a-e837-4b2a-a10f-144065cbd8dd
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 31e28514ab4bdb0f5af261a1f7c87633ca0bd4a6
ms.openlocfilehash: 58671d037c7f62e5fdaa56657737a4470c90bdb7


---

# <a name="configure-android-for-work-apps-with-mobile-app-configuration-policies-in-microsoft-intune"></a>Microsoft Intune에서 모바일 앱 구성 정책을 사용하여 Android for Work 앱 구성

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

[!INCLUDE[wit_nextref](../includes/afw_rollout_disclaimer.md)]

Microsoft Intune에서 모바일 앱 구성 정책을 사용하여 사용자가 앱을 실행할 때 필요할 수 있는 설정을 제공할 수 있습니다. 예를 들어 사용자가 앱에서 다음 사항을 지정해야 할 수 있습니다.

-   사용자 지정 포트 번호
-   언어 설정
-   회사 로고와 같은 브랜딩 설정

사용자가 설정을 잘못 입력하면 기술 지원팀의 부담이 증가하며 새 앱 도입이 지연됩니다.

사용자가 앱을 실행하기 전에 모바일 앱 구성 정책을 통해 이러한 설정을 장치에 배포할 수 있습니다. 배포한 설정은 자동으로 제공되므로 사용자가 아무런 작업을 수행할 필요가 없습니다.

앱 구성 정책을 활용하려면 앱 개발자가 앱을 만들 때 엔터프라이즈 앱 구성을 공개했어야 합니다. 예를 들어 Google Chrome에서는 기본 책갈피, 허용되거나 거부된 사이트 등을 설정할 수 있게 하는 설정을 공개합니다. 이러한 설정이 지원되는지 확인하고 정책에서 지정하는 방법을 확인하려면 앱 개발자에게 문의하세요.

앱 구성 정책은 구성할 앱을 배포한 동일한 사용자에게 배포합니다. 앱 설정은 앱이 실행될 때 적용됩니다.

## <a name="configure-a-mobile-app-configuration-policy"></a>모바일 앱 구성 정책 구성

1.  [Microsoft Intune 관리 콘솔](https://manage.microsoft.com)에서 **정책** &gt; **개요** &gt; **정책 추가**를 선택합니다.

2.  정책 목록에서 **Android for Work**를 확장하고 **모바일 앱 구성 정책(Android for Work)**을 선택한 다음 **정책 만들기**를 선택합니다.

    > [!TIP]
    > 이 정책 유형에는 사용자 지정 설정만 구성할 수 있습니다. 권장 설정은 사용할 수 없습니다.

3.  **정책 만들기** 페이지의 **일반** 섹션에서 모바일 앱 구성 정책의 이름을 입력하고 원하는 경우 설명을 입력합니다.

4. 이 페이지의 **모바일 앱 구성 정책** 섹션에서 다음 정보를 지정합니다.
    - **이 구성이 적용되는 응용 프로그램의 패키지 ID** - 패키지 ID는 Google Play 페이지의 앱 URL의 'id =' 섹션에서 찾을 수 있습니다. 예를 들어 Microsoft Excel 앱의 패키지 ID는 **com.microsoft.office.excel**입니다.
    - 텍스트 상자에서 구성할 앱 설정에 대한 데이터를 입력합니다. 이러한 설정은 앱 공급업체에서 가져옵니다. 일부 앱에서는 이 설정을 지원하지 않습니다.
5.  **유효성 검사**를 클릭하여 입력한 데이터가 올바른 속성 목록 형식인지 확인합니다.

    > [!IMPORTANT]
    > **유효성 검사**를 클릭하면 Intune에서는 입력한 구성 데이터가 올바른 형식인지 확인합니다. 그러나 해당 데이터가 연결된 앱에서 작동하는지는 확인되지 않습니다.

6.  완료되면 **정책 저장**을 클릭합니다.

새 정책이 **구성 정책** 노드에 표시됩니다.


## <a name="deploy-the-app-configuration-policy"></a>앱 구성 정책 배포
모바일 앱 구성 정책을 만든 후에는 정책 설정을 적용할 앱을 배포한 동일한 사용자에게 배포해야 합니다.

정책을 배포하는 방법에 대해 자세히 알아보려면 [구성 정책 배포](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies#deploy-a-configuration-policy)를 참조하세요.

Android for Work 장치에 앱을 배포하는 방법에 대한 자세한 내용은 [Intune을 사용하여 Android for Work 앱을 배포하는 방법](android-for-work-apps.md)을 참조하세요.

배포된 앱은 장치에서 실행하면 모바일 앱 구성 정책에서 구성한 설정을 사용하여 실행됩니다.

> [!TIP]
> 앱당 앱 구성 정책을 하나만 사용자에게 배포합니다.



<!--HONumber=Feb17_HO1-->


