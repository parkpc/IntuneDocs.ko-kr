---
title: "사용자 지정 도메인 이름 구성 | Microsoft 문서"
description: "Intune 구독에 대한 사용자 지정 도메인 이름 추가"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/14/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2382f36f-13d8-4a32-81ad-6cfa604889c3
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab6d9b6b296fb4e1fb0aaa9496fede28976728dc
ms.openlocfilehash: 86062a73092f6e438de7a315d9ec1c2f395c9c50
ms.lasthandoff: 04/14/2017


---


# <a name="configure-a-custom-domain-name"></a>사용자 지정 도메인 이름 구성

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

이 항목에서는 관리자가 DNS CNAME를 만들어 로그온 환경을 간소화하고 사용자 지정하는 방법을 알려줍니다.

조직에서 Intune과 같은 Microsoft의 클라우드 기반 서비스에 등록하면 Azure AD(Active Directory)에 호스트된 초기 도메인 이름(예: **yourdomain.onmicrosoft.com**)이 제공됩니다. 이 예제에서 **yourdomain**는 등록할 때 선택한 도메인 이름이고, **onmicrosoft.com**은 구독에 추가하는 계정에 할당되는 접미사입니다. 조직이 사용자 지정 도메인을 소유한 경우 정기가입 시 지정한 도메인 이름 대신 해당 도메인을 사용하도록 Intune의 인스턴스를 구성할 수 있습니다.

사용자 계정을 만들거나 온-프레미스 Active Directory를 동기화하기 전에 .onmicrosoft.com 도메인만 사용할지 아니면 사용자 지정 도메인 이름을 하나 이상 추가할지를 결정하는 것이 좋습니다. 사용자를 추가하기 전에 사용자 지정 도메인을 구성하면 사용자가 다른 도메인 리소스에 액세스하는 데 사용하는 자격 증명으로 로그인하도록 설정할 수 있으므로 구독의 사용자 ID를 간편하게 관리할 수 있습니다.

Microsoft의 클라우드 기반 서비스에 가입한 경우 해당 서비스의 인스턴스는 클라우드 기반 서비스의 ID 및 디렉터리 서비스를 제공하는 Microsoft [Azure AD 테넌트](http://technet.microsoft.com/library/jj573650.aspx#BKMK_WhatIsAnAzureADTenant)가 됩니다. 조직의 사용자 지정 도메인 이름을 사용하도록 Intune을 구성하는 작업은 다른 Azure AD 테넌트의 경우와 동일하므로 [도메인 추가](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/)에 설명된 정보 및 절차를 사용할 수 있습니다.

> [!TIP]
> Microsoft의 클라우드 기반 서비스를 통해 사용자 지정 도메인을 사용하는 것과 관련된 자세한 내용은 [Conceptual overview of custom domain names in Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-add-domain-concepts/)(Azure Active Directory의 사용자 지정 도메인 이름에 대한 개념 개요)를 참조하세요.

이 초기 도메인 이름을 바꾸거나 제거할 수는 없습니다. 그러나 Intune에서 사용할 자체 사용자 지정 도메인 이름을 추가, 확인 또는 제거할 수 있습니다. 이렇게 하면 비즈니스 ID를 유지하려는 경우에 도움이 됩니다.

## <a name="to-add-and-verify-your-custom-domain"></a>사용자 지정 도메인을 추가 및 확인하려면

1. [Office 365 관리 포털](https://portal.office.com/Admin/Default.aspx)로 이동한 후 관리자 계정에 로그인합니다.

2. 탐색 창에서 **설정** &gt; **도메인**을 선택합니다.

3. **도메인 추가**를 선택하고 사용자 지정 도메인 이름을 입력합니다.

4. **도메인 확인** 대화 상자가 열리고 DNS 호스팅 공급자에서 TXT 레코드를 만들기 위한 값이 표시됩니다.
    - **GoDaddy 사용자**: Office 365 관리 포털은 사용자를 GoDaddy의 로그인 페이지로 리디렉션합니다. 자격 증명을 입력하고 도메인 변경 권한 계약에 동의하면 TXT 레코드가 자동으로 만들어집니다. 또는 [TXT 레코드를 만들](https://support.office.com/article/Create-DNS-records-at-GoDaddy-for-Office-365-f40a9185-b6d5-4a80-bb31-aa3bb0cab48a) 수도 있습니다.
    - **Register.com 사용자**: [단계별 지침](https://support.office.com/article/Create-DNS-records-at-Register-com-for-Office-365-55bd8c38-3316-48ae-a368-4959b2c1684e#BKMK_verify)에 따라 TXT 레코드를 만듭니다.

    > [!TIP]
    > DNS 호스팅 공급자를 변경하는 동안 [Windows 장치 등록](/Intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune)을 위한 DNS 별칭(CNAME)을 만들어야 합니다.

사용자 지정 도메인을 추가 및 확인하는 단계는 [Azure Active Directory에서도 수행](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/)할 수 있습니다.

[Office 365의 초기 onmicrosoft.com 도메인 정보](https://support.office.com/article/About-your-initial-onmicrosoft-com-domain-in-Office-365-B9FC3018-8844-43F3-8DB1-1B3A8E9CFD5A)에서 자세한 내용을 확인할 수 있습니다.

>[!div class="step-by-step"]

>[&larr;**Intune에 로그인**](.\start-with-a-paid-subscription-to-microsoft-intune-step-1.md)     [**Intune에 사용자 추가** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-3.md)  

