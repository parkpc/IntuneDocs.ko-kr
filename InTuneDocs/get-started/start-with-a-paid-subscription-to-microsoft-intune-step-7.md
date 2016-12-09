---
title: "회사 포털 사용자 지정 | Microsoft Intune"
description: "Intune 회사 포털을 사용하면 장치 등록, 앱 설치, IT 부서 정보 찾기 등과 같은 일반적인 작업 수행할 수 있습니다."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: eb4a9f01-f857-4563-ab6f-5d0d7dfa659d
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 04cccd410417dca4477c0d6cd61b0940dda8c389


---

# <a name="customize-the-company-portal"></a>회사 포털 사용자 지정
Intune 회사 포털에서 사용자는 회사 데이터에 액세스하고 장치 등록, 앱 설치, IT 부서 지원 정보 찾기 등의 일반적인 작업을 수행할 수 있습니다.

Intune 회사 포털은 사용자에게 회사 데이터 및 앱에 대한 액세스를 제공합니다. 회사 포털은 두 가지 형태로 사용할 수 있습니다.

-   **회사 포털 앱**: Intune으로 관리하는 장치에서 사용할 수 있는 응용 프로그램입니다. [Android](/Intune/EndUser/using-your-android-device-with-intune), [iOS](/Intune/EndUser/using-your-ios-or-mac-os-x-device-with-intune) 및 [Windows](/Intune/EndUser/using-your-windows-device-with-intune)용 회사 포털 앱에 대해 자세히 알아보세요.


- **회사 포털 웹 사이트**: 최종 사용자가 회사 포털 앱에서 지원하는 대부분의 작업을 수행할 수 있는 웹 사이트입니다. Intune 회사 포털 URL은 [http://portal.manage.microsoft.com](http://portal.manage.microsoft.com)입니다. [Intune 회사 포털 웹 사이트 사용](/Intune/EndUser/using-the-intune-company-portal-website)에서 이 웹 사이트에 대해 자세히 알아보세요.

> [!TIP]
> 회사 포털을 사용자 지정할 때는 구성이 회사 포털 웹 사이트 및 회사 포털 앱에 모두 적용됩니다.

사용자가 회사 포털에서 수행할 수 있는 몇 가지 작업은 다음과 같습니다.

-   장치 등록
-   장치 상태 보기
-   장치 초기화
-   암호 다시 설정
-   원격으로 장치 잠그기
-   조직에서 배포한 소프트웨어 다운로드
-   IT 부서에 지원 문의

> [!NOTE]
> 특정 국가에서는 회사 포털 앱을 아직 사용할 수 없습니다.
> __iOS__: iOS용 회사 포털 앱은 Apple iOS App Store의 [모든 사용 가능 지역](https://go.microsoft.com/fwlink/?linkid=831284)에 게시됩니다.
> __Android__: Android용 회사 포털 앱은 현재 중국에서 사용할 수 없습니다. 이러한 국가의 경우 대안으로 [Android 버전의 회사 포털 앱을 테스트용으로 로드](https://www.microsoft.com/en-us/download/details.aspx?id=49140)할 수 있습니다.  

## <a name="customize-company-portal-settings"></a>회사 포털 설정 사용자 지정
회사 포털을 사용자 지정하면 최종 사용자에게 친숙하고 유용한 환경을 제공하는 데 도움이 됩니다. [Microsoft Intune 관리자 콘솔](https://manage.microsoft.com)에 테넌트 또는 서비스 관리자로 로그인하고, **관리** &gt; **회사 포털**을 선택하여 회사 포털 설정을 구성합니다.

![admin-console-admin-workspace-comp-portal-settings](./media/companyportal.png)

## <a name="company-contact-information-and-privacy-statement"></a>회사 연락처 정보 및 개인정보취급방침
회사 이름은 회사 포털의 제목으로 표시됩니다. 연락처 정보 및 세부 정보는 회사 포털의 IT 담당자 화면에서 사용자에게 표시됩니다. 개인정보취급방침은 사용자가 개인정보취급방침 링크를 클릭하면 표시됩니다.

|필드 이름|최대 길이|추가 정보|
    |----------|------------------------|----------------|
    |회사 이름|40|이 이름은 회사 포털의 제목으로 표시됩니다.|
    |IT 부서 연락처 이름|40|이 이름은 **IT 담당자** 페이지에 표시됩니다.|
    |IT 부서 전화 번호|20|이 연락처 번호는 **IT 담당자** 페이지에 표시됩니다.|
    |IT 부서 전자 메일 주소|40|이 연락처 주소는 **IT 담당자** 페이지에 표시됩니다. 유효한 메일 주소를 **alias@domainname.com** 형식으로 입력해야 합니다.|
    |추가 정보|120|**IT 담당자** 페이지에 표시됩니다.|
    |회사 개인정보취급방침 URL|79|사용자가 회사 포털에서 개인정보취급방침 링크를 클릭할 때 표시되는 회사 개인정보취급방침을 지정할 수 있습니다. https://www.contoso.com 형식의 올바른 URL을 입력해야 합니다.|

## <a name="support-contacts"></a>지원 연락처
지원 웹 사이트가 회사 포털의 사용자에게 표시되어, 온라인 지원에 액세스할 수 있도록 합니다.

|필드 이름|최대 길이|추가 정보|
    |----------|------------------------|----------------|
    |지원 웹 사이트 URL|150|최종 사용자가 사용할 지원 웹 사이트가 있는 경우 여기에서 URL을 지정합니다. URL은 https://www.contoso.com 형식이어야 합니다. URL을 지정하지 않으면 회사 포털의 **IT 담당자** 페이지에서 지원 웹 사이트에 대해 아무 내용도 표시되지 않습니다.|
    |웹 사이트 이름|40|이 이름은 지원 웹 사이트의 URL에 대해 표시되는 식별 이름입니다. 지원 웹 사이트 URL을 지정하고 식별 이름을 지정하지 않으면 **IT 웹 사이트로 이동**이 회사 포털의 **IT 담당자** 페이지에 표시됩니다.|

## <a name="company-branding-customization"></a>회사 브랜딩 사용자 지정
회사 로고, 회사 이름, 테마 색 및 배경으로 회사 포털을 사용자 지정할 수 있습니다.

|필드 이름|추가 정보|
    |----------|----------------|
    |테마 색|회사 포털에 적용할 테마 색을 선택합니다.|
    |회사 로고 포함|이 옵션을 설정한 경우 회사 포털에서 표시할 회사 로고를 업로드할 수 있습니다. 회사 포털 배경이 흰색인 경우에 표시되는 로고 하나와 회사 포털 배경이 직접 선택한 테마 색을 사용하는 경우에 표시되는 로고 하나, 두 개의 로고를 업로드할 수 있습니다. 각 로고는 .png 또는 .jpg 파일 형식이어야 하며 최대 해상도가 400 x 100픽셀이고 크기가 750KB 이하여야 합니다.|
    |[!INCLUDE[win8_client_2](../includes/win8_client_2_md.md)] 회사 포털 앱의 배경 선택|이 설정은 [!INCLUDE[win8_client_2](../includes/win8_client_2_md.md)] 회사 포털 앱의 배경에만 적용됩니다.|


변경 내용을 저장한 후 관리 콘솔의 **회사 포털** 페이지 맨 아래에 제공된 링크를 사용하여 회사 포털 웹 사이트를 확인할 수 있습니다. 이러한 링크는 변경할 수 없습니다. 사용자가 로그인하면 이러한 링크가 회사 포털에 구독을 표시합니다.

>[!div class="step-by-step"]

>[&larr;**정책 및 앱 만들기**](.\start-with-a-paid-subscription-to-microsoft-intune-step-6.md)       [**장치 등록** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-8.md)  



<!--HONumber=Dec16_HO2-->


