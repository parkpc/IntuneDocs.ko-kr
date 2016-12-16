---
title: "최신 인증이 없는 앱 차단 | Microsoft Intune"
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
translationtype: Human Translation
ms.sourcegitcommit: 87e37cd8334ddb9331c0662b691545cd0ab0553a
ms.openlocfilehash: 5c95cd8510faa437a33ac25d6602a2bcc57c05d5


---

# <a name="block-apps-that-do-not-use-modern-authentication-adal"></a>최신 인증(ADAL)을 사용하지 않는 앱 차단
MAM 정책(MAM CA)을 사용하는 앱 조건부 액세스의 경우 OAuth2가 구현된 [최신 인증](https://support.office.com/en-US/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a)을 사용하는 응용 프로그램에서 사용됩니다. 최신 Office 모바일 및 데스크톱 응용 프로그램은 최신 인증을 사용하지만 기본 인증 및 양식 기반 인증과 같은 다른 인증 방법을 사용하는 타사 앱이나 이전 Office 앱도 있습니다.

이러한 앱에 대한 액세스를 차단하려면 다음을 권장합니다.

* 최신 인증 이외의 인증 프로토콜을 차단하도록 ADFS 클레임 규칙을 설정해야 합니다. 자세한 지침은 시나리오 3 - [브라우저 기반 응용 프로그램을 제외한 모든 O365 액세스 차단](https://technet.microsoft.com/library/dn592182.aspx)에서 제공됩니다.

>[!IMPORTANT]
>MAM CA는 Azure AD(Azure Active Directory) 인증서 기반 인증으로 사용할 수 없습니다. 한 번에 하나만 구성할 수 있습니다.



### <a name="see-also"></a>참고 항목
[Intune에서 지원하는 앱만 O365 서비스 액세스 허용](allow-policy-managed-apps-access-to-o365.md)



<!--HONumber=Dec16_HO2-->


