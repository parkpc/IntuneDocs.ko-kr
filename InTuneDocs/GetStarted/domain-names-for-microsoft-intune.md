---
title: "Microsoft Intune의 도메인 이름 | Microsoft Intune"
description: "Intune에 대한 도메인 이름 추가"
keywords: 
author: andredm7
manager: swadhwa
ms.date: 10/11/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c3c136f0-330d-432a-a91f-16f7dd097e55
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 38159f6dbcae2eeb4dca47141e60eed12cd7f6ee
ms.openlocfilehash: abcf37e7ec3150b5a2fe4cda910631f83d4c510a


---



# Microsoft Intune의 사용자 지정 도메인 이름

조직에서 Intune과 같은 Microsoft의 클라우드 기반 서비스에 등록하면 Azure Active Directory에 호스트된 초기 도메인 이름(예: **yourdomain.onmicrosoft.com**)이 제공됩니다. 이 예제에서 **yourdomain**는 등록할 때 선택한 도메인 이름이고, **onmicrosoft.com**은 구독에 추가하는 계정에 할당되는 접미사입니다.

이 초기 도메인 이름을 바꾸거나 제거할 수는 없습니다. 그러나 Intune에서 사용할 자체 사용자 지정 도메인 이름을 추가, 확인 또는 제거할 수 있습니다. 이렇게 하면 비즈니스 ID를 유지하려는 경우에 도움이 됩니다.

## 사용자 지정 도메인을 추가 및 확인하려면 

1. [Office 365 관리 포털](https://portal.office.com/Admin/Default.aspx)로 이동한 후 관리자 계정에 로그인합니다.

2. 탐색 창에서 **설정** &gt; **도메인**을 선택합니다.

3. **도메인 추가**를 선택하고 사용자 지정 도메인 이름을 입력합니다.

4. **도메인 확인** 대화 상자가 열리고 DNS 호스팅 공급자에서 TXT 레코드를 만들기 위한 값이 표시됩니다.
    - **GoDaddy 사용자**: Office 365 관리 포털은 사용자를 GoDaddy의 로그인 페이지로 리디렉션합니다. 자격 증명을 입력하고 도메인 변경 권한 계약에 동의하면 TXT 레코드가 자동으로 만들어집니다. 또는 [TXT 레코드를 만들](https://support.office.com/en-us/article/Create-DNS-records-at-GoDaddy-for-Office-365-f40a9185-b6d5-4a80-bb31-aa3bb0cab48a?ui=en-US&rs=en-US&ad=US) 수도 있습니다.
    - **Register.com 사용자**: [단계별 지침](https://support.office.com/en-us/article/Create-DNS-records-at-Register-com-for-Office-365-55bd8c38-3316-48ae-a368-4959b2c1684e?ui=en-US&rs=en-US&ad=US#BKMK_verify)에 따라 TXT 레코드를 만듭니다.

    > [!TIP] 
    > DNS 호스팅 공급자를 변경하는 동안 [Windows 장치 등록](/Intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune)을 위한 DNS 별칭(CNAME)을 만들어야 합니다.

사용자 지정 도메인을 추가 및 확인하는 단계는 [Azure Active Directory에서도 수행](https://azure.microsoft.com/en-us/documentation/articles/active-directory-add-domain/)할 수 있습니다.

하이브리드 클라우드 시나리오에서 사용자 지정 도메인 이름을 추가하고, 조직이 해당 이름을 소유하는지 확인한 후에는 온-프레미스 Active Directory에서 사용자 계정 관리를 계속 관리하고 Azure AD와 동기화할 수 있습니다.

## Azure AD와 온-프레미스 사용자를 동기화하려면##

1. 온-프레미스 Active Directory에서 사용자 지정 도메인에 대한 [UPN 접미사를 추가](https://technet.microsoft.com/en-us/library/cc772007.aspx)합니다.
2. 가져오려는 온-프레미스 사용자에 대한 새 UPN 접미사를 설정합니다.
3. [Azure AD Connect 동기화](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect/)를 실행하여 온-프레미스 사용자를 Azure AD와 통합합니다.
4. 사용자 계정 정보가 동기화되면 [Office 365 관리 포털](https://portal.office.com/Admin/Default.aspx)을 사용하여 Microsoft Intune 라이선스를 할당할 수 있습니다.

### 참고 항목

[Office 365의 초기 onmicrosoft.com 도메인 정보](https://support.office.com/en-us/article/About-your-initial-onmicrosoft-com-domain-in-Office-365-B9FC3018-8844-43F3-8DB1-1B3A8E9CFD5A?ui=en-US&rs=en-US&ad=US)

[Microsoft Intune을 시작하기 전에 알아두어야 할 사항](what-to-know-before-you-start-microsoft-intune.md)



<!--HONumber=Oct16_HO2-->


