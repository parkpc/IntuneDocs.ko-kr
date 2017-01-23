---
title: "Intune에서 Android 장치 등록 | Microsoft 문서"
description: "Intune에서 Android 장치를 등록하는 방법을 설명합니다."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0ed3a002-7533-4001-ae24-e10b64b66620
searchScope:
- Company Portal
ms.reviewer: arnab
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 3da636b15807623bb60895870e6d43cd2e0aa01c
ms.openlocfilehash: 4e28ce37559d209672dd4180eebfb07ffddd60c6


---


# <a name="enroll-your-android-device-in-intune"></a>Intune에서 Android 장치 등록

회사 또는 학교에서 Microsoft Intune을 사용하는 경우 Android 장치를 등록하여 회사 전자 메일, 파일 및 기타 리소스에 액세스 권한을 얻을 수 있습니다. 장치를 등록하면 IT 부서에서 해당 회사 또는 학교 리소스를 관리하고 보안을 유지하여 선호하는 장치를 자유롭게 사용하여 작업을 완료할 수 있습니다. 등록에 대해 자세히 알아보려면 [회사 포털 앱을 설치하고 장치를 등록하면 어떻게 되나요?](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-android.md)를 참조하세요.

이러한 등록 지침은 Samsung KNOX Android 장치와 "네이티브"(Samsung Knox가 아닌) Android 장치에 대한 것입니다. Samsung KNOX 장치가 있는지 확인하려면 **설정** > **장치 정보**로 이동합니다. 여기에 나열된 "KNOX 버전"이라는 단어가 보이지 않으면 네이티브 Android 장치가 있어야 합니다.

등록하기 전이나 이후에 장치 사용 방법을 가장 잘 설명하는 범주를 선택하라는 메시지가 표시될 수도 있습니다. IT 관리자는 이 범주를 사용하여 액세스할 수 있는 앱을 확인합니다.

Intune에서 장치를 등록하는 동안 오류가 발생할 경우 [IT 관리자에게 등록 오류를 보낼](send-enrollment-errors-to-your-it-admin-android.md) 수 있습니다.

**Android 장치를 등록하려면:**

1.  [Google Play](http://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)에서 무료 Intune 회사 포털 앱을 설치합니다.

2.  Microsoft Intune 회사 포털 앱을 엽니다.

3.  회사 포털의 **시작** 화면에서 **로그인**을 탭한 다음, 회사 또는 학교 계정으로 로그인합니다.

    ![android-company-portal-sign-in](./media/and-enroll-0-welcome-screen.png)   

4.  IT 관리자가 회사 사용 약관을 설정하는 경우 **동의함**을 탭하여 조건에 동의합니다.

    ![android-company-portal-sign-in](./media/and-enroll-3-accept-terms.png)

5.  회사 또는 학교 계정과 암호를 사용하여 회사 포털 앱에 로그인하고 **로그인**을 탭합니다.

    ![android-company-portal-sign-in](./media/and-enroll-2-cp-sign-in.png)

6.  **회사 액세스 설정** 화면에서 **시작**을 탭합니다.

    ![회사 액세스 설정 화면](./media/and-enroll-4a-comp-access-setup.png)

7.  **왜 장치를 등록하나요?** 화면에서 장치를 등록할 때 수행할 수 있는 작업을 확인하고 **계속**을 탭합니다.

    ![왜 장치를 등록하나요 화면](./media/and-enroll-4b-why-enroll.png)

8.  IT 관리자가 장치에서 볼 수 있는 사항과 볼 수 없는 사항의 목록을 검토하고 **계속**을 탭합니다.

    ![개인 정보 설정](./media/and-enroll-4c-we-care-privacy.png)

9.  **다음 단계는?** 화면에서 등록하는 동안 발생되는 작업을 확인하고 **등록**을 탭합니다.

    ![다음 단계는 화면](./media/and-enroll-4d-what-comes-next.png)

10.  Android 6.0 이상을 사용하는 경우 이 단계를 수행합니다. 그렇지 않으면 다음 단계로 진행합니다.

    IT 관리자가 특정 정책을 설정한 경우 다음과 같은 메시지가 표시될 수 있습니다.
    -   **회사 포털에서 통화를 하고 전화 통화를 관리하도록 허용하시나요?**

        ![android-company-portal-sign-in](./media/and-enroll-3a-allow-phone-access.png)

    이 메시지가 표시되면 **허용**을 탭합니다. **Microsoft는 결코 전화를 걸거나 전화 통화를 관리하지 않으므로** 허용을 탭하는 것이 안전합니다. Google이 메시지 텍스트를 제어하므로 Microsoft에서 변경할 수 없습니다. 액세스를 허용하면 장치를 통해 장치의 IMEI(International Mobile Station Equipment Identity) 번호를 Intune에 보내도록 허용하기만 하면 됩니다. IMEI 번호는 모바일 장치를 고유하게 식별하는 일련 번호와 같습니다.

    액세스를 거부하면 다음에 회사 포털에 로그인할 때 메시지가 다시 표시되지만, **다시 묻지 않음** 상자를 탭하여 이후 메시지를 해제할 수 있습니다. 사용자가 나중에 액세스를 허용할 경우 **설정** &gt; **앱** &gt; **회사 포털** &gt; **사용 권한** &gt; **전화**로 이동한 다음 사용 권한을 설정합니다.

    -   **회사 포털에 연락처에 대한 액세스를 허용하시나요?**

        ![android-company-portal-sign-in](./media/and-enroll-3b-allow-contacts-access.png)

    이 메시지가 표시되면 **허용**을 탭합니다. **Microsoft는 결코 연락처에 액세스하지 않으므로** 허용을 탭하는 것이 안전합니다. Google이 메시지 텍스트를 제어하므로 Microsoft에서 변경할 수 없습니다. 액세스를 허용하는 경우 회사 포털 앱을 통해서만 회사 계정을 만들고, 사용하고 관리할 수 있습니다.

    액세스를 거부하면 다음에 회사 포털에 로그인할 때 메시지가 다시 표시되지만, **다시 묻지 않음** 상자를 탭하여 이후 메시지를 해제할 수 있습니다. 사용자가 나중에 액세스를 허용할 경우 **설정** &gt; **앱** &gt; **회사 포털** &gt; **사용 권한** &gt; **전화**로 이동한 다음 사용 권한을 설정합니다.

11.  **활성화 장치 관리자** 화면에서 **활성화**를 탭합니다.

    ![장치 관리자 활성화 화면](./media/and-enroll-5-activate.png)

12.  지시에 따라 PIN이나 암호를 입력합니다. 이미 이 장치에서 암호나 PIN을 설정했다면 이 화면에 표시되지 않거나 새 PIN이나 암호를 입력할 필요가 없습니다.

    ![PIN 또는 암호 입력](./media/and-enroll-6-PIN-native.png)

13.  Samsung Knox 장치를 사용하는 경우 **확인**을 탭하면 장치가 등록되고 있음을 나타내는 메시지를 확인할 수 있습니다. 기본 Android 장치를 사용하는 경우 장치가 등록되고 있음을 보여 주는 다음 화면을 확인할 수 있습니다.

    ![Samsung KNOX 개인 정보 취급 방침](./media/and-enroll-7-knox-privacy-policy.png)

    이 화면은 장치가 등록되고 있음을 보여 줍니다.

    ![장치 등록 화면](./media/and-enroll-8-device-enrolling.png)

14. **회사 액세스 설정** 화면이 나타나면 **계속**을 탭합니다. 장치가 규정을 준수하지 않음을 나타내는 메시지가 표시되면 지침에 따라 문제를 해결하고 **계속**을 탭합니다.

    ![회사 액세스 설정 화면](./media/and-enroll-9-comp-access-setup.png)  

11. **회사 액세스 설정 완료** 화면에서 **완료**를 탭합니다. 이제 장치가 등록됩니다.

    ![회사 액세스 설정 완료 화면](./media/and-enroll-10-comp-access-setup-complete.png)

업무용 앱을 설치하기 전에 **설정** &gt; **보안**으로 이동하고 **알 수 없는 소스**를 설정합니다. 앱을 설치하기 전에 이 옵션을 설정하지 않으면 "설치가 차단되었습니다. 보안상의 이유로 장치가 알 수 없는 소스에서 가져온 앱의 설치를 차단하도록 설정되었습니다."라는 메시지가 표시됩니다. 오류 대화 상자에서 **설정**을 탭하여 **알 수 없는 소스** 옵션으로 이동할 수 있습니다.

여전히 도움이 필요하세요? IT 관리자에게 문의하거나(연락처 정보는 [회사 포털 웹 사이트](http://portal.manage.microsoft.com) 확인) Microsoft Android 팀(wintunedroidfbk@microsoft.com)으로 메일을 보내세요.



<!--HONumber=Jan17_HO1-->


