---
title: "회사 포털 앱에 로그인하는 방법 | Microsoft Docs"
description: "여러 플랫폼에서 회사 포털 앱에 로그인하는 방법을 알아보세요."
keywords: 
author: barlanmsft
ms.author: barlan
manager: dougeby
ms.date: 10/25/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cfd214bc-f072-4808-af2e-a3cbf7af9bca
searchScope:
- User help
ROBOTS: 
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: c4ae7373627c914b89629464c53240c8b07a28df
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2018
---
# <a name="how-do-i-sign-in-to-the-company-portal-app---user-story-1132123--"></a>회사 포털 앱에 로그인하려면 어떻게 하나요? <!--User Story 1132123-->

회사 포털 앱을 사용하여 메일, 비즈니스 앱 등의 회사 리소스에 액세스합니다. 회사 포털에 로그인할 수 있는 두 가지 주요 방법은 다음과 같습니다.

* 업무용 메일 주소 및 암호 사용
* 다른 장치에서 로그인

다음 그림은 iOS용이지만 Android 및 Windows 장치에 대한 프로세스도 거의 동일합니다.

## <a name="signing-in-with-your-email-address-and-password"></a>메일 주소 및 암호를 사용하여 로그인

1. 장치에서 회사 포털 앱을 열고 **로그인**을 탭합니다.

  ![웹 사이트가 그림으로 표시되면서 그 앞에 사람 아이콘이 포함된 회사 포털 로그인 페이지 그 아래 “로그인” 단추가 있습니다. Microsoft 개인 정보 및 쿠키 정보로 이동하게 하는 하단의 링크](/intune/media/cp_ios_aad_signin_after_1704_001.png)

  회사 포털 앱이 없나요? [iOS](install-and-sign-in-to-the-intune-company-portal-app-ios.md) 또는 [Android](install-the-company-portal-app-android.md)에 대해 설치하고 다운로드하는 방법을 확인합니다.

2. **회사 또는 학교 계정**을 입력합니다.

  ![사용자는 같은 화면에서 전자 메일 및 암호 대신 전자 메일 주소만 입력하라는 메시지를 받습니다.](/intune/media/cp_ios_aad_signin_after_1704_002.png)

3. 메일 주소가 허용될 때까지 잠시 기다린 다음 암호를 입력합니다.

  ![전자 메일 주소가 승인된 후에 암호를 입력하라는 메시지가 표시됩니다.](/intune/media/cp_ios_aad_signin_after_1704_003.png)

4. 회사 포털에서 사용자 로그인이 허용되면 사용자가 로그인되며, 회사 리소스에 액세스할 수 있습니다.   

  ![인증 프로세스를 진행하고 나면 회사 포털 앱에 로그인되며 이 상태는 로드 중 막대로 표현됩니다.](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_007.png)

## <a name="signing-in-with-certificate-based-authentication"></a>인증서 기반 인증으로 로그인

1.  장치에서 회사 포털 앱을 엽니다.

2.  **회사 또는 학교 계정**을 입력합니다.

3.  **인증서로 로그인** 링크를 탭합니다.

4.  인증서를 사용하려면 **계속**을 탭합니다.

## <a name="signing-in-from-another-device"></a>다른 장치에서 로그인

암호를 사용하여 회사 리소스에 로그인하지 않는 경우 적절한 액세스 수준을 가진 적절한 사용자임을 확인하는 방법으로 다른 장치를 사용할 수 있습니다. 회사에서 스마트 카드를 사용하여 컴퓨터에 액세스하는 경우 다른 장치를 사용하여 로그인해야 할 수 있습니다.

1. 메일 주소를 입력하는 대신 메일 텍스트 상자 아래에 있는 **다른 장치에서 로그인** 링크를 선택합니다.

  ![웹 사이트가 그림으로 표시되면서 그 앞에 사람 아이콘이 포함된 회사 포털 로그인 페이지 그 아래 “로그인” 단추가 있습니다. Microsoft 개인 정보 및 쿠키 정보로 이동하게 하는 하단의 링크](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_001.png)

2. 회사 포털에 로그인하기 위한 고유한 일회성 코드를 받게 됩니다.

  ![회사 컴퓨터의 고유 암호를 사용하여 aka.ms/devicelogin 페이지로 이동하여 로그인 시 해당 코드를 사용하라는 지침이 제공됩니다.](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_003.png)

3. 다른 장치에서 브라우저를 열고 [https://aka.ms/devicelogin](https://aka.ms/devicelogin)으로 이동하여 코드를 입력합니다.

  ![회사 포털 앱이 아닌 작업 컴퓨터에서 사용자 브라우저 이미지 표시되는 "장치 로그인" 페이지에서 사용자에게 회사 포털 앱에서 받은 코드를 입력하라는 메시지가 나타납니다.](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_004.png)

4. **장치 로그인** 페이지에서 코드가 확인되면 __계속__을 선택하여 회사 포털이 다른 장치에서 로그인을 허용하도록 합니다.

  ![사용자는 필드에 고유한 코드를 입력하고 "장치 로그인" 사이트에서 Intune 회사 포털이 로그인에 필요한 인증을 수신하는 올바른 앱인지 확인을 요구합니다.](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_005.png)

5. 코드가 확인되고 나면 창을 닫아도 됩니다.

  ![사용자가 장치에서 회사 포털 앱에 로그인했으며 이 페이지를 닫을 수 있음을 언급하는 확인 페이지](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_006.png)

6. 원래 장치에서 회사 포털 앱이 로그인을 시작합니다.

  ![인증 프로세스를 진행하고 나면 회사 포털 앱에 로그인되며 해당 프로세스는 로드 중 막대로 표시됩니다.](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_007.png)

여전히 도움이 필요하세요? 회사 지원 부서에 문의하세요. 연락처 정보는 [회사 포털 웹 사이트](https://portal.manage.microsoft.com#HelpDeskDialog)를 참조하세요.
