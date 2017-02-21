---
title: "30일 무료 평가판 등록 | Intune Azure 미리 보기 | Microsoft Docs"
description: "Intune Azure 미리 보기: Azure에서 Intune에 등록하는 방법입니다."
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 01/11/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 195931c0-8208-43bd-b0af-b1f8e469a32c
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: cd98141b4b377f0013607f2a2ebb93a93cd7f0ce
ms.openlocfilehash: ce69e7efbee286839a1bf3440db692bd237b0e06


---

# <a name="sign-up-for-a-microsoft-intune-free-trial-for-the-azure-portal-preview"></a>Azure Portal 미리 보기에 대한 Microsoft Intune 무료 평가판 등록

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

이 문서에서는 Azure Portal 미리 보기에 대한 Intune 독립 실행형 평가판에 등록하는 과정을 안내합니다. <!---and prepares your trial with some users so that you can then follow the associated evaluation guide to see how Intune manages mobile devices. ---> <!---or app data when devices are not enrolled in Intune.--->

<!--- ## Assumptions
This sign-up article and the evaluation guide assume you are using the trial for evaluation purposes only and intend to start with a clean environment when you subscribe.

To make it easy for you to get started with the trial, we are setting up a very simple environment that uses only Intune and assumes it will be your sole method of managing devices (known as the mobile device management authority). However, throughout the guide we will point you to deeper technical content if you want to explore farther.

You can do everything in the trial version that you can do in a subscription version; the only difference is you are limited to 100 user accounts in the trial.--->

<!--- ## Sign up for your trial--->
1. [Intune 등록](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20) 페이지를 방문하여 평가판 구독에 등록하는 양식을 작성합니다.

 <!--- If you have a work or school account and want to use that for your Intune trial, follow [these sign-in instructions](https://docs.microsoft.com/en-us/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-1) instead. However, this article assumes that you are not using such an account.---><br/> ![등록 페이지 이미지](./media/1-clicking-try.png)

 > [!TIP]
> 대부분의 IT 작업자 및 사용자가 여러분과 다른 로캘에 있는 경우 **회사 위치는 어디입니까?** 아래에서 로캘을 선택할 수 있습니다.

2. 등록 프로세스가 끝나면 새 계정 정보가 포함된 메시지가 제공됩니다. <br/> ![계정 정보 이미지](./media/2-end-of-sign-up-process.png) <br/>이제 **준비가 되었습니다.**를 클릭하면 테스트 환경에 사용자를 추가할 수 있는 Office 365 관리 센터로 이동합니다. <br/><br/>그러나 Intune Azure Portal Preview로 직접 이동하려면 새 브라우저 창을 열고 주소 표시줄에 **https://portal.azure.com**을 입력합니다. 그러면 제공된 자격 증명을 사용하여 로그인할 수 있는 Azure 로그인 페이지로 이동합니다. Intune 평가판에 로그인할 때마다 이 주소를 사용합니다. <br/> ![Azure Portal 로그인 페이지 이미지](./media/azure-portal-signin.png)

Intune Azure 미리 보기에 처음으로 로그온한 경우 Azure 대시보드에 Intune이 표시되지 않을 수 있습니다. Azure 대시보드에 Intune 서비스를 추가하려면 다음을 수행합니다.
1. 대시보드의 왼쪽에 있는 Azure 서비스 목록에서 **추가 서비스 >**를 선택하고 검색 상자에 **Intune**을 입력합니다.
2. 목록에서 **Intune**을 선택하고, 별표를 선택하여 서비스 목록에 서비스를 추가합니다.<br/> ![서비스 목록에서 Intune을 선택하는 이미지](./media/azure-add-intune1.png)
3. 그런 다음 서비스 목록에서 **Intune**을 선택하면 Intune 대시보드가 열립니다.

평가판에 등록하는 경우 등록 과정 중에 제공한 메일 주소로 계정 정보가 포함된 메일 메시지도 제공됩니다. 이 전자 메일을 통해 평가판이 활성화된 것을 확인합니다.


<!--- ## Add users
Before you leave the Office 365 Admin center for Intune, you need to add some users to your trial account.

In the Office 365 Admin center, you can add users individually or in bulk by uploading a .csv file. We will do both to set up your trial. However, in your production environment, you will probably want to take advantage of your Azure Active Directory user accounts, which you can learn more about in our [Getting Started guide](https://docs.microsoft.com/en-us/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3) and in the [Next steps](#Next-steps) section of this article.

### Add an individual user
1. Choose either of the options to add a use to open a form that allows you to create a user. Only the items starred with an asterisk (\*) are required.
![Image of add user button options](./media/sign-up/add-user.png)


2.  When you add the user, the final step will be to send the user an email with their temporary Intune password. For the purposes of this evaluation, use your own work email address so you will receive the log-on information and see the email your users will get. You can then use these user identities to enroll test devices.<br/>

 ![Image of add user final step](./media/sign-up/new-user-2.png)

3. If you want to assign a user an admin role after you create it, you can edit the role in the Office 365 Admin center by selecting the user name from your list of users, and then choosing **Edit** in the Role line to see the list of user roles you can select from and assign to that user.

 ![Image of user  role options](./media/sign-up/change-user-role.png)

### Import multiple users
1. You will find the wizard for importing multiple users in the **More** list.

 ![Image of option to add multiple users](./media/sign-up/add-multiple-users.png)

2. To help you set up your .csv file correctly, you can download a template file to populate with your user data. Download the .csv file that contains headers and sample user information to see exactly the kind of data is needed for each field.

 ![Image of first step in bulk enrollment wizard](./media/sign-up/bulk-enroll-step-1.png)


3. After you’ve created and saved your .csv file, choose **Browse** to select the file. Verify, and choose **Next**. Your users will be uploaded and added to your list of active users.

> [!NOTE]
> Your users won't show up in Intune until they've enrolled a device to be managed.

Now it’s time to head over to Intune to start managing your users, their devices, and their apps.--->

## <a name="keeping-the-admin-experiences-straight"></a>관리자 환경 계속 유지
<!---### Classic Intune
There are two portals you will use for classic Intune:
- The Office 365 Admin center ([portal.office.com](https://portal.office.com))
- The Intune administration console ([manage.microsoft.com](https://manage.microsoft.com))

Normally, you’ll do your work in the Intune administration console, shown below. This is the site where you set up and manage your groups, policies, devices, and apps.

![Image of Intune administration console](./media/sign-up/intune-admin-console.png)

However, you will use the Office 365 Admin center, shown below, to add and manage your users and other aspects of your account, including billing and support.

![Image of Office 365 Admin center](./media/sign-up/office-admin-center.png)

You can navigate from the Office 365 Admin center to the Intune admin console. The admin centers are under the last item in the left navigation pane. Choose **Intune** to open the Intune admin console in a new tab.

![Image of link to Intune administration console](./media/sign-up/link-to-intune.png)

To get from Intune back to the Office 365 Admin center, choose the **Add Users** task on the Groups Overview page.

![Image of link back to Office 365  Admin center](./media/sign-up/task-add-users.png)--->

<!---### Intune Azure preview--->
Intune Azure 미리 보기에 사용할 수 있는 포털은 다음과 같은 세 가지입니다.
- [Azure Portal에서 Intune의 기능](what-is-microsoft-intune.md)을 탐색할 수 있는 Azure의 Intune 대시보드([portal.azure.com](https://portal.azure.com))
- Azure Active Directory를 사용하지 않는 경우 사용자를 추가 및 관리할 수 있는Office 365 관리 센터([portal.office.com](https://portal.office.com)). 또한 대금 청구 및 지원을 포함하여 계정의 다른 측면을 관리할 수 있습니다.
- Azure에 아직 추가되지 않은 기능을 탐색할 수 있는 클래식 Intune 관리 콘솔([manage.microsoft.com](https://manage.microsoft.com))

일반적으로 아래에 표시된 Intune 대시보드에서 작업을 수행합니다. 이 사이트에서는 그룹, 정책, 장치 및 앱을 설정하고 관리할 수 있습니다.

**클래식 Intune 포털 열기** 타일을 선택하면 대시보드에서 클래식 Intune 관리 콘솔로 이동할 수 있습니다.

Intune Azure 미리 보기로 돌아가려면 브라우저 주소 표시줄에 https://portal.azure.com을 입력한 후 서비스 목록에서 **Intune**을 다시 선택합니다.

 ![Intune 대시보드의 이미지](./media/intune-azure-dashboard.png)


반면, 아래에 나와 있는 Office 365 관리 센터는 사용자 및 계정의 다른 측면(예: 대금 청구 및 지원)을 추가하고 관리하는 데 사용됩니다.

![Office 365 관리 센터의 이미지](./media/office-admin-center.png)

Office 365 관리 센터에서 Intune 대시보드로 이동하려면 브라우저 주소 표시줄에 https://portal.azure.com을 입력합니다. 서비스 목록에서 **Intune**을 선택합니다.

Intune에서 Office 365 관리 센터로 돌아가려면 브라우저 주소 표시줄에 https://portal.office.com을 입력합니다. Intune에 이미 로그인한 경우 Office 365 관리 센터로 바로 이동됩니다.

## <a name="next-steps"></a>다음 단계

### <a name="intune-azure-preview"></a>Intune Azure 미리 보기
[Azure Portal 미리 보기의 Intune](what-is-microsoft-intune.md)에 대해 자세히 알아보세요.
### <a name="classic-intune"></a>클래식 Intune
평가 시나리오: [Microsoft의 모바일 장치 관리 평가](https://docs.microsoft.com/intune/understand-explore/mobile-device-management-trial-guide-microsoft-intune)

### <a name="integration-with-other-products"></a>다른 제품과의 통합
Intune에서 Azure Active Directory 사용자 계정을 사용하는 방법을 자세히 알아봅니다.
- [ID 요구 사항](https://docs.microsoft.com/en-us/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview)
- [디렉터리 동기화 요구 사항](https://docs.microsoft.com/en-us/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements)
- [다단계 인증 요구 사항](https://docs.microsoft.com/en-us/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements)

[System Center Configuration Manager와 함께 Intune](https://docs.microsoft.com/en-us/sccm/mdm/understand/hybrid-mobile-device-management)를 사용하는 방법에 대해 자세히 알아보기



<!--HONumber=Feb17_HO1-->


