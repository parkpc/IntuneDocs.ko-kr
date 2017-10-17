---
title: "Skycure 앱, Microsoft Authenticator 앱 및 iOS 구성 정책 추가"
description: "Intune 클래식 포털로 Skycure 앱, Microsoft Authenticator 앱 및 iOS 구성 정책을 추가합니다."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 018d26f4-4a75-4e27-bb04-54f54106cb2f
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 3e2dd0675042e63e056254d1b85955f66d5dc3f2
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/10/2017
---
# <a name="add-skycure-apps-microsoft-authenticator-app-and-ios-configuration-policy"></a>Skycure 앱, Microsoft Authenticator 앱 및 iOS 구성 정책 추가

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

최종 사용자가 모바일 장치에서 위협이 식별될 때 알림을 받을 수 있도록 Skycure 앱을 추가 및 배포하고, 위협을 해결하기 위한 지침을 받으려면 Intune을 사용해야 합니다.

또한 사용자가 Azure AD를 통해 검사된 ID를 사용할 수 있도록 [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to)가 필요하며, Skycure 앱에 로그인할 때마다 사용자 이름 및 암호를 입력하지 않고도 Intune 및 Azure AD SSO(Single Sign-On)를 사용할 수 있도록 Skycure iOS 앱임을 알리는 iOS 앱 구성 정책이 필요합니다.

## <a name="before-you-begin"></a>시작하기 전에

-   [Intune 클래식 포털](https://manage.microsoft.com/)에서 아래 단계를 완료해야 합니다.

-   Skycure 관리 콘솔에서 이전에 구성된 Azure AD 계정, 즉 Intune 클래식 포털에 로그인하는 데 사용되는 계정과 같은 계정을 사용해야 합니다.

-   사용할 수 있는 Skycure 통합 파일이 있어야 합니다. 이 파일은 Skycure 관리 콘솔에서 이전에 다운로드한 .zip 파일로, iOS 앱 구성 정책 매개 변수가 있는 **skycure\_configuration.plist** 파일이 포함되어 있습니다.

-   다음 프로세스에 대해 잘 알고 있어야 합니다.

    -   [Intune에 앱 추가](/intune-classic/deploy-use/add-apps)

    -   [Intune에 iOS 앱 구성 정책 추가](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)

## <a name="to-add-the-skycure-app-for-android"></a>Android용 Skycure 앱을 추가하려면

1.  Intune 클래식 포털에서 **앱** &gt; **앱 추가**를 선택하여 Intune 소프트웨어 게시자를 시작한 후 **다음**을 클릭합니다.

2.  **소프트웨어 설치** 페이지에서 **외부 링크**를 선택한 다음 **URL 지정**에서 [Android용 Skycure 앱 URL](https://play.google.com/store/apps/details?id=com.skycure.skycure)을 붙여넣습니다.

    ![Intune 소프트웨어 게시자에서 URL 지정](../media/mtp/skycure-add-apps-1.png)

3.  **소프트웨어 설명** 페이지에서 **게시자**, **이름** 및 **설명**을 입력하고 **회사 포털에서 이 항목을 강조 표시 및 추천 앱으로 표시** 옵션을 선택한 후 **다음**을 클릭합니다.

    ![Intune 소프트웨어 게시자 소프트웨어 설명](../media/mtp/skycure-add-apps-2.png)

4.  **업로드**, **닫기**를 차례로 클릭합니다.

## <a name="to-add-the-skycure-app-for-ios"></a>iOS용 Skycure 앱을 추가하려면

1.  Intune 클래식 포털에서 **앱** &gt; **앱 추가**를 선택하여 Intune 소프트웨어 게시자를 시작한 후 **다음**을 클릭합니다.

2.  **소프트웨어 설치** 페이지에서 **앱 스토어에서 관리되는 iOS 앱**을 선택한 다음 **URL 지정**에서 [iOS용 Skycure 앱 URL](https://itunes.apple.com/us/app/skycure/id695620821?mt=8)을 붙여넣습니다.

    ![Intune 소프트웨어 게시자에서 관리하는 iOS 앱](../media/mtp/skycure-add-apps-3.png)

3.  **소프트웨어 설명** 페이지에서 **게시자**, **이름** 및 **설명**을 입력하고 **회사 포털에서 이 항목을 강조 표시 및 추천 앱으로 표시** 옵션을 선택한 후 **다음**을 클릭합니다.

    ![Intune 소프트웨어 게시자 옵션](../media/mtp/skycure-add-apps-4.png)

4.  **요구 사항** 페이지의 **모바일 장치 유형**에서 **모두** 옵션을 선택한 후 **다음**을 클릭합니다.

5.  **업로드**, **닫기**를 차례로 클릭합니다.

## <a name="to-add-the-microsoft-authenticator-app-for-ios"></a>iOS용 Microsoft Authenticator 앱을 추가하려면

1.  Intune 클래식 포털에서 **앱** &gt; **앱 추가**를 선택하여 Intune 소프트웨어 게시자를 시작한 후 **다음**을 클릭합니다.

2.  **소프트웨어 설치** 페이지에서 **앱 스토어에서 관리되는 iOS 앱**을 선택한 다음 **URL 지정**에서 [iOS용 Microsoft Authenticator URL](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8)을 붙여넣습니다.

    ![Intune 소프트웨어 게시자에서 관리되는 iOS 앱 2](../media/mtp/skycure-add-apps-5.png)

3.  **소프트웨어 설명** 페이지에서 **게시자**, **이름** 및 **설명**을 입력하고 **회사 포털에서 이 항목을 강조 표시 및 추천 앱으로 표시** 옵션을 선택한 후 **다음**을 클릭합니다.

    ![Intune 소프트웨어 게시자에서 관리되는 iOS 앱 3](../media/mtp/skycure-add-apps-6.png)

4.  **요구 사항** 페이지의 **모바일 장치 유형**에서 **모두** 옵션을 선택한 후 **다음**을 클릭합니다.

5.  **업로드**, **닫기**를 차례로 클릭합니다.

## <a name="to-add-the-skycure-ios-app-configuration-policy"></a>Skycure iOS 앱 구성 정책을 추가하려면

1.  Intune 클래식 포털에서 **정책** &gt; **개요 &gt; 정책 추가**를 선택합니다.

2.  정책 목록에서 **iOS**를 확장하고 **모바일 앱 구성 정책(iOS 8.0 이상)**을 선택한 다음 **정책 만들기**를 선택합니다.

    ![iOS 앱 구성 정책](../media/mtp/skycure-add-apps-7.png)

3.  **정책 만들기** 페이지의 **일반** 섹션에서 iOS 앱 구성 정책의 이름을 입력하고 필요에 따라 설명을 입력합니다.

    a.  메모장과 같은 텍스트 편집기를 사용하여 **skycure\_configuration.plist** 파일을 열고 콘텐츠를 복사하여 **모바일 앱 구성 정책** 본문에 붙여넣고, **유효성 검사**, **정책 저장**을 차례로 선택합니다.

       ![iOS 앱 구성 정책 2](../media/mtp/skycure-add-apps-8.png)

## <a name="next-steps"></a>다음 단계

[Skycure 앱, Microsoft Authenticator 앱 및 iOS 앱 구성 정책 배포](/intune-classic/deploy-use/deploy-skycure-apps-microsoft-authenticator-app-and-ios-app-configuration-policy)
