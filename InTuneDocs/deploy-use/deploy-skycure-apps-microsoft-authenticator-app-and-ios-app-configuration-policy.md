---
title: "Skycure 앱, Microsoft Authenticator 앱 및 iOS 구성 정책 배포 | Microsoft Docs"
description: "Intune 클래식 콘솔로 Skycure 앱, Microsoft Authenticator 앱 및 iOS 구성 정책을 배포합니다."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 45826fbc-6df5-41b2-8e80-d1353f904b43
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: e10453155343bb7fd91a4fd3874d393ef78d0b1a
ms.openlocfilehash: 0b6f9bde77b5b88cc66ab10419b7d6e083f7cb6b
ms.lasthandoff: 04/25/2017


---

# <a name="deploy-skycure-apps-microsoft-authenticator-app-and-ios-app-configuration-policy"></a>Skycure 앱, Microsoft Authenticator 앱 및 iOS 앱 구성 정책 배포

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="before-you-begin"></a>시작하기 전에

-   [Intune 클래식 콘솔](https://manage.microsoft.com/)에서 아래 단계를 완료해야 합니다.

-   Skycure 관리 콘솔에서 이전에 구성된 Azure AD 계정, 즉 Intune 클래식 콘솔에 로그인할 때 사용한 계정과 동일한 계정을 사용해야 합니다.

-   다음 프로세스에 대해 잘 알고 있어야 합니다.

    -   [Intune을 사용하여 앱 배포](https://docs.microsoft.com/intune/deploy-use/deploy-apps-in-microsoft-intune)

    -   [iOS 앱 구성 정책 배포](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)

## <a name="to-deploy-skycure-apps-microsoft-authenticator-app-and-the-ios-app-configuration-policy"></a>Skycure 앱, Microsoft Authenticator 앱 및 iOS 앱 구성 정책을 배포하려면

1.  Intune 클래식 콘솔에서 **앱** &gt; **앱**을 선택하여 관리할 수 있는 앱 목록을 확인합니다.

2.  다음 앱을 선택합니다.

    a.  Microsoft Authenticator

    b.  Android용 Skycure 앱

    c.  IOS용 Skycure 앱

       ![Intune 클래식 콘솔에서 배포할 모든 앱](../media/mtp/skycure-deploy-app-1.png)

3.  **배포 관리**를 선택하고, Skycure 사용자가 있는 Azure AD 보안 그룹을 선택한 후 **다음**을 클릭합니다.

4.  **배포 작업** 페이지의 **승인** 드롭다운 목록에서 **필수 설치** 옵션을 선택한 후 **다음**을 클릭합니다.

    ![Intune 클래식 콘솔 배포 작업](../media/mtp/skycure-deploy-app-2.png)

5.  **VPN 프로필** 페이지의 **VPN 정책** 드롭다운 목록에서 **없음** 옵션을 선택한 후 **다음**을 클릭합니다.

6.  **모바일 앱 구성** 페이지의 **앱 구성 정책** 드롭다운 목록에서 이전에 만든 iOS 앱 구성 정책을 선택한 후 **마침**을 클릭합니다.

    ![Intune 클래식 콘솔 모바일 앱 구성](../media/mtp/skycure-deploy-app-3.png)

## <a name="next-steps"></a>다음 단계

[Intune과 Skycure 통합 설정](https://docs.microsoft.com/intune/deploy-use/setup-the-skycure-integration-with-Intune)

