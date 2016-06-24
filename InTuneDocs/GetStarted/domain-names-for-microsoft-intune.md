---
# required metadata

title: Microsoft Intune의 도메인 이름 | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: c3c136f0-330d-432a-a91f-16f7dd097e55

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---



# Microsoft Intune의 도메인 이름

Microsoft Intune을 설정하기 전에, 이 항목과 [Microsoft Intune을 시작하기 전에 알아두어야 할 사항](what-to-know-before-you-start-microsoft-intune.md)에 나열된 요구 사항을 검토합니다..

조직에서 Intune과 같은 Microsoft의 클라우드 서비스에 등록하면 초기 도메인 이름(예: **contoso.onmicrosoft.com**)이 제공됩니다. 이 예제에서 **contoso**는 등록할 때 선택한 도메인 이름이고, **onmicrosoft.com**은 구독에 추가하는 계정에 할당되는 접미사입니다. 등록 프로세스를 완료한 후에는 해당 도메인을 변경할 수 없습니다. 그러나 전역 관리자는 서비스에서 사용할 조직의 고유한 사용자 지정 도메인 이름을 추가하거나 이전에 추가한 도메인을 제거할 수 있습니다.

기본적으로, onmicrosoft domain을 사용할 경우 가져오는 각 사용자는 UPN(User Principal Name)의 **onmicrosoft.com** 접미사를 받습니다.

등록 시 제공된 도메인 이름 대신 고유한 도메인 이름을 사용하려면 Azure Active Directory에 해당 도메인 이름을 추가할 수 있습니다. 도메인을 추가했으며 해당 도메인이 사용자 소유인 것인지 확인되면 DNS 호스팅 공급자에서 DNS 리소스 레코드를 변경하여 도메인 이름을 포함하는 그룹 및 계정을 만들 수 있습니다. 사용자 지정 도메인을 사용하려는 경우 사용자 계정의 관리를 간소화하려면 구독에 사용자 지정 도메인 이름 구성을 수행한 후 로컬 Active Directory에서 사용자를 동기화할 수 있습니다.

Intune에 대한 도메인 이름 및 DNS 리소스 레코드를 구성하는 것은 다른 Azure Active Directory 테넌트의 경우와 동일합니다. 지침은 [Azure Active Directory를 사용하여 로그인을 단순화하기 위해 사용자 지정 도메인 이름 추가](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/)를 참조하세요.

### 참고 항목
[Microsoft Intune을 시작하기 전에 알아두어야 할 사항](what-to-know-before-you-start-microsoft-intune.md)


<!--HONumber=May16_HO1-->


