---
# required metadata

title: SharePoint Online에 대한 액세스 제한 | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: b088e5a0-fd4a-4fe7-aa49-cb9c8cfb1585

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune을 사용하여 SharePoint Online에 대한 액세스 제한
[!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] 조건부 액세스를 사용하여 SharePoint Online에 있는 파일에 대한 액세스를 제어합니다.
조건부 액세스에는 두 구성 요소가 포함되어 있습니다.
- 장치를 준수로 간주하기 위해 장치가 준수해야 하는 장치 규정 준수 정책
- 장치에서 서비스에 액세스하기 위해 충족해야 하는 조건을 지정하는 조건부 액세스 정책
조건부 액세스가 어떻게 작동하는지에 대한 자세한 내용은 [전자 메일 및 O365 서비스에 대한 액세스 제한](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) 항목을 읽어보세요.

사용자가 자신의 장치에 있는 OneDrive와 같은 지원되는 앱을 사용하여 파일에 연결하려고 하면 다음 평가 작업이 수행됩니다.

![장치에서 SharePoint에 대한 액세스가 허용 또는 차단되는지 여부를 결정하는 결정 지점을 보여 주는 다이어그램 ](../media/ConditionalAccess8-6.png)

>[!IMPORTANT]
>앱에서 최신 인증을 사용한 PC 및 Windows 10 Mobile 장치에 대한 조건부 액세스는 현재 일부 Intune 고객에게만 제공됩니다. 이러한 기능을 이미 사용 중인 경우 어떠한 조치도 취할 필요가 없습니다. 계속 사용할 수 있습니다.

>앱에서 최신 인증을 사용하여 PC 또는 Windows 10 Mobile에 대한 조건부 액세스 정책을 만들지 않았고 작업을 수행하려면 요청을 제출해야 합니다.  알려진 문제에 대한 자세한 정보와 이 기능에 액세스하는 방법은 [Connect 사이트](http://go.microsoft.com/fwlink/?LinkId=761472)에서 확인할 수 있습니다..

SharePoint Online에 대한 조건부 액세스 정책을 구성하기 **전에** 다음을 수행해야 합니다.
- **SharePoint Online 구독**이 있어야 하며 사용자는 SharePoint Online의 라이선스를 취득해야 합니다.
- **Enterprise Mobility Suite** 또는 **Azure Active Directory Premium**에 대한 구독이 있어야 합니다..

  필수 파일에 연결하려면 장치가 다음과 같아야 합니다.
-   [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]에 **등록**되어 있거나 도메인에 가입된 PC이어야 합니다.

-   **장치를 Azure Active Directory에 등록**해야 합니다(이 등록은 다음에 장치를 등록하면 자동으로 수행됨 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]).


-   배포된 모든 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] 규정 준수 정책을 준수해야 합니다.

장치 상태는 지정한 조건에 따라 파일에 대한 액세스를 부여하거나 차단하는 Azure Active Directory에 저장됩니다.

조건이 충족되지 않으면 사용자가 로그인할 때 다음 메시지 중 하나가 표시됩니다.

-   장치를 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]에 등록하지 않았거나 Azure Active Directory에 등록하지 않은 경우, 회사 포털 앱을 설치하고 등록하는 방법에 관한 지침이 포함된 메시지가 표시됩니다.

-   장치가 규정을 준수하지 않으면 사용자가 문제에 관한 정보와 이를 해결하는 방법을 확인할 수 있는 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] 회사 포털 웹 사이트로 이동하는 메시지가 표시됩니다.

## 모바일 장치에 대한 지원
- iOS 7.1 이상
- Android 4.0 이상, Samsung Knox Standard 4.0 이상
- Windows Phone 8.1 이상

## PC 지원
- Windows 8.1 이상(Intune에 등록된 경우)
- Windows 7.0 또는 Windows 8.1(도메인에 가입된 경우)

  - 도메인에 가입된 PC의 경우 Azure Active Directory에 [자동으로 등록](https://azure.microsoft.com/en-us/documentation/articles/active-directory-conditional-access-automatic-device-registration/)하도록 설정해야 합니다.
Intune 및 Office 365 고객의 경우에는 AAD DRS가 자동으로 활성화됩니다. ADFS 장치 등록 서비스를 이미 배포한 고객의 온-프레미스 Active Directory에는 등록된 장치가 표시되지 않습니다.

  - 정책이 도메인 가입을 요구하도록 설정되어 있지만 PC가 도메인에 가입되지 않은 경우 IT 관리자에게 문의하라는 메시지가 표시됩니다.

  - 정책이 도메인 가입 또는 규정 준수를 요구하도록 설정되어 있는 경우 PC가 요구 사항을 충족하지 않으면 회사 포털 앱을 설치하고 등록하는 방법에 대한 지침이 포함된 메시지가 표시됩니다.
-    [Office 365 최신 인증을 사용](https://support.office.com/en-US/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a)하도록 설정해야 하며 최신 Office 업데이트를 모두 설치해야 합니다.

    최신 인증을 사용하는 경우 Office 2013 Windows 클라이언트에 ADAL(Active Directory Authentication Library) 기반 로그인 기능이 제공되며, **다단계 인증** 및 **인증서 기반 인증**과 같은 더욱 효율적인 보안 기능을 사용할 수 있습니다..


## SharePoint Online에 대한 조건부 액세스 구성

### 1단계: Active Directory 보안 그룹 구성
시작하기 전에 조건부 액세스 정책에 대한 Azure Active Directory 보안 그룹을 구성합니다. **Office 365 관리 센터**또는 **Intune 계정 포털**에서 이러한 그룹을 구성할 수 있습니다. 이러한 그룹을 대상에 사용하거나 정책에서 사용자를 제외합니다. 사용자가 정책의 대상인 경우 해당 사용자가 사용하는 각 장치가 규정을 준수해야 리소스에 액세스할 수 있습니다.

SharePoint Online 정책에 두 그룹 유형을 지정할 수 있습니다.

-   **대상 그룹** – 정책이 적용되는 사용자 그룹을 포함합니다.

-   **제외된 그룹** – 정책에서 제외되는 사용자 그룹을 포함합니다.

사용자가 두 그룹에 모두 속한 경우에는 정책에서 제외됩니다.

### 2단계: 준수 정책 구성 및 배포
아직 수행하지 않은 경우 규정 준수 정책을 만들고 SharePoint Online 정책의 대상이 될 사용자에게 배포합니다.

> [!NOTE]
> 규정 준수 정책을 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] 그룹에 배포하는 동안 Azure Active Directory 보안 그룹을 조건부 액세스 정책의 대상으로 합니다.

준수 정책을 구성하는 방법에 대한 자세한 내용은 [규정 준수 정책 만들기](create-a-device-compliance-policy-in-microsoft-intune.md)를 참조하세요..

> [!IMPORTANT]
> 규정 준수 정책을 배포하지 않은 경우 장치는 준수하는 것으로 간주됩니다.

준비가 되었으면 **3단계**를 계속합니다..

### 3단계: SharePoint Online 정책 구성
다음으로 관리되고 규정을 준수하는 장치만 SharePoint Online에 액세스할 수 있도록 요구하는 정책을 구성합니다. 이 정책은 Azure Active Directory에 저장됩니다.

#### <a name="bkmk_spopolicy"></a>

1.  [Microsoft Intune 관리 콘솔](https://manage.microsoft.com)에서 **정책** > **조건부 액세스** > **SharePoint Online 정책**을 클릭합니다..
![SharePoint Online 정책 페이지의 스크린샷](../media/IntuneSASharePointOnlineCAPolicy.png)

2.  **SharePoint Online에 대한 조건적 액세스 정책 사용**을 선택합니다..

3.  **응용 프로그램 액세스** 아래에서 다음 플랫폼에 조건부 액세스 정책을 적용하도록 선택할 수 있습니다.

    -   **모든 플랫폼**

        이 경우 **SharePoint Online**에 액세스하는 데 사용되는 모든 장치가 Intune에 등록되고 정책을 준수해야 합니다.  **최신 인증**을 사용하는 모든 클라이언트 응용 프로그램에는 조건부 액세스 정책이 적용됩니다. 플랫폼이 현재 Intune에서 지원되지 않는 경우 **SharePoint Online**에 대한 액세스는 차단됩니다.
        >[!TIP]
        >PC에 대한 조건부 액세스를 아직 사용하지 않는 경우 이 옵션이 표시되지 않습니다.  대신 **특정 플랫폼**을 사용합니다. PC에 대한 조건부 액세스는 현재 일부 Intune 고객에게만 제공됩니다.   알려진 문제에 대한 자세한 정보와 이 기능에 액세스하는 방법은 [Microsoft Connect 사이트](http://go.microsoft.com/fwlink/?LinkId=761472)에서 확인할 수 있습니다..

    -   **특정 플랫폼**

         지정한 장치 플랫폼에서 최신 인증을 사용하는 모든 클라이언트 앱에 조건부 액세스 정책이 적용됩니다.

     Windows PC의 경우, 해당 PC가 도메인에 가입되어 있거나 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] 에 등록되어 있고 규정을 준수해야 합니다. 다음 요구 사항을 설정할 수 있습니다.

     -   **장치가 도메인에 가입되어 있거나 규정을 준수해야 합니다.** PC가 도메인에 가입되어 있거나 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]에 설정된 정책을 준수하는 경우 이 옵션을 선택합니다. PC가 이러한 요구 사항을 하나라도 충족하지 않을 경우 사용자에게 다음에 장치를 등록하라는 메시지가 표시됩니다. [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

     -   **장치가 도메인에 가입되어 있어야 합니다.** 즉, Exchange Online에 액세스하려면 PC가 도메인에 가입되어 있어야 하는 경우 이 옵션을 선택합니다. PC가 도메인에 가입되지 않은 경우, 메일 액세스가 차단되고 사용자에게 IT 관리자에게 문의하라는 메시지가 표시됩니다.

     -   **장치가 규정을 준수해야 합니다.** PC가 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]에 등록되어 있고 규정을 준수해야 하는 경우 이 옵션을 선택합니다. PC가 등록되어 있지 않은 경우 등록 방법에 대한 지침이 포함된 메시지가 표시됩니다.

4.  **대상 그룹**에서 **수정** 을 클릭하여 정책을 적용할 Azure Active Directory 보안 그룹을 선택합니다. 모든 사용자 또는 선택한 사용자 그룹을 대상으로 지정할 수 있습니다.

5.  **제외된 그룹**에서 필요에 따라 **수정** 을 클릭하여 이 정책에서 제외된 Azure Active Directory 보안 그룹을 선택합니다.

6.  작업이 끝나면 **저장**을 클릭합니다..

조건부 액세스 정책을 배포할 필요는 없으며, 즉시 적용됩니다.

### 4단계: 규정 준수 및 조건부 액세스 정책 모니터링
**그룹** 작업 영역에서 장치의 상태를 볼 수 있습니다.

모든 모바일 장치 그룹을 선택하고 **장치** 탭에서 다음 **필터**중 하나를 선택합니다.

-   **AAD에 등록되지 않은 장치** – 이러한 장치는 SharePoint Online에서 차단됩니다.

-   **규정을 준수하지 않은 장치** – 이러한 장치는 SharePoint Online에서 차단됩니다.

-   **AAD에 등록되어 있고 규정을 준수하는 장치** – 이러한 장치 SharePoint Online에 액세스할 수 있습니다.

### 참고 항목
[Microsoft Intune을 사용한 메일 및 O365 서비스 액세스 제한](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)


<!--HONumber=May16_HO1-->


