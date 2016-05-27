---
# required metadata

title: 사용자 지정 도메인 이름 구성 | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 2382f36f-13d8-4a32-81ad-6cfa604889c3

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# 사용자 지정 도메인 이름 구성

Intune은 기본적으로, 처음 서비스를 구독할 때 생성된 **<domain>.onmicrosoft.com** 도메인 이름을 사용합니다. 조직이 사용자 지정 도메인을 소유한 경우 정기가입 시 지정한 도메인 이름 대신 해당 도메인을 사용하도록 Intune의 인스턴스를 구성할 수 있습니다.

새 사용자 계정을 만들거나 온-프레미스 Active Directory에서 계정을 동기화하기 전에 .onmicrosoft.com 도메인만 사용할지 아니면 사용자 지정 도메인 이름을 하나 이상 추가할지를 결정하는 것이 좋습니다. 사용자를 추가하기 전에 사용자 지정 도메인을 구성하면 사용자가 다른 도메인 리소스에 액세스하는 데 사용하는 자격 증명으로 로그인하도록 설정할 수 있으므로 구독의 사용자 ID를 간편하게 관리할 수 있습니다.

Microsoft의 클라우드 기반 서비스에 가입한 경우 해당 서비스의 인스턴스는 클라우드 기반 서비스의 ID 및 디렉터리 서비스를 제공하는 Microsoft [Azure AD 테넌트](http://technet.microsoft.com/library/jj573650.aspx#BKMK_WhatIsAnAzureADTenant)가 됩니다. 조직의 사용자 지정 도메인 이름을 사용하도록 Intune을 구성하는 작업은 다른 Azure AD 테넌트의 경우와 동일하므로 [도메인 추가](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/)에 설명된 정보 및 절차를 사용할 수 있습니다..

> [!TIP]
> Microsoft의 클라우드 기반 서비스를 통해 사용자 지정 도메인을 사용하는 것과 관련된 자세한 내용은 [Conceptual overview of custom domain names in Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-add-domain-concepts/)(Azure Active Directory의 사용자 지정 도메인 이름에 대한 개념 개요)를 참조하세요..

### 다음 단계
축하합니다. Intune 빠른 시작 가이드의 2단계를 완료했습니다..

>[!div class="step-by-step"]

>[&larr; **Intune에 로그인**](.\start-with-a-paid-subscription-to-microsoft-intune-step-1.md)     [**Intune에 사용자 추가** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-3.md)  


<!--HONumber=May16_HO1-->


