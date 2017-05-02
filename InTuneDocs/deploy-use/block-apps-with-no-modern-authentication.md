---
title: "최신 인증이 없는 앱 차단"
description: 
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 098b652c-01e0-45d1-a731-620b0d3dc7c1
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: e5dd7cb5b320df7f443b52a1b502027fa3c4acaf
ms.openlocfilehash: abfb3912ba6dfa6802e1321782afd155a96fbefc
ms.lasthandoff: 04/19/2017


---

# <a name="block-apps-that-do-not-use-modern-authentication-adal"></a>최신 인증(ADAL)을 사용하지 않는 앱 차단

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

앱 보호 정책을 사용하는 앱 조건부 액세스의 경우 응용 프로그램에서 OAuth2 구현인 [최신 인증](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a)을 사용해야 합니다. 최신 Office 모바일 및 데스크톱 응용 프로그램은 최신 인증을 사용하지만 기본 인증 및 양식 기반 인증과 같은 다른 인증 방법을 사용하는 타사 앱이나 이전 Office 앱도 있습니다.

이러한 앱에 대한 액세스를 차단하려면 다음을 권장합니다.

* 최신 인증 이외의 인증 프로토콜을 차단하도록 ADFS 클레임 규칙을 설정해야 합니다. 자세한 지침은 시나리오 3 - [브라우저 기반 응용 프로그램을 제외한 모든 O365 액세스 차단](https://technet.microsoft.com/library/dn592182.aspx)에서 제공됩니다.
* **SharePoint Online**의 경우 PowerShell commandlet [Set-SPOTenant](https://technet.microsoft.com/library/fp161390.aspx)를 사용하여 SharePoint Online 서비스에서 최신이 아닌 인증을 사용하지 않도록 설정하여 레거시 인증 프로토콜 속성을 false로 설정합니다.

```
 Set-SPOTenant -LegacyAuthProtocolsEnabled $false
 
```


>[!IMPORTANT]
>앱 기반 CA는 Azure AD(Azure Active Directory) 인증서 기반 인증으로 사용할 수 없습니다. 한 번에 하나만 구성할 수 있습니다.

### <a name="see-also"></a>참고 항목
[Intune에서 지원하는 앱만 O365 서비스 액세스 허용](allow-policy-managed-apps-access-to-o365.md)

