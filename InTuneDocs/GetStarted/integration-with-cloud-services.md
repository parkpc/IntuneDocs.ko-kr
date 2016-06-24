---
# required metadata

title: Microsoft 클라우드 서비스 및 제품과 Intune 통합 | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 49675811-08a3-408f-810b-89552ff404bd

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft 클라우드 서비스 및 제품과 Intune 통합

[!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)]을 설정하기 전에, 이 항목과 [Microsoft Intune을 시작하기 전에 알아두어야 할 사항](what-to-know-before-you-start-microsoft-intune.md)에 나열된 요구 사항을 검토합니다..
##다른 Microsoft 클라우드 서비스와 통합


[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] 은 다른 Microsoft 클라우드 서비스와 공통 기반을 공유합니다. 동일한 계정을 사용하여 여러 클라우드 서비스에 가입한 경우 해당 서비스는 동일한 Microsoft Azure AD 인프라를 사용하며 Azure AD의 테넌트가 됩니다. Azure AD는 Microsoft 클라우드 서비스의 주요 디렉터리 및 ID 관리 기능을 제공합니다.

TechNet Library에서 [Azure AD 관리](http://technet.microsoft.com/library/hh967611.aspx)에 대해 자세히 알아봅니다.

## 다른 Microsoft 제품과의 통합
[!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)]을 독립 실행형 클라우드 서비스 또는 다른 제품과 통합된 클라우드 서비스로 사용할 수 있습니다. 현재는 [!INCLUDE[cmshort](../includes/cmshort_md.md)]만 다음와(과) 직접 통합할 수 있습니다. [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]와 [!INCLUDE[cmshort](../includes/cmshort_md.md)]을 통합하는 결정은 [!INCLUDE[cmshort](../includes/cmshort_md.md)] 내에서가 아니라 [!INCLUDE[wit_icp_1](../includes/wit_icp_1_md.md)] 콘솔에서 모바일 장치 관리 기관을 설정해야 하는 영구적인 선택입니다. 모바일 장치 관리 기관을 설정한 후에는 이 구성을 변경하거나 되돌릴 수 없습니다.

[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]을 [!INCLUDE[cmshort](../includes/cmshort_md.md)]와 함께 사용하는 경우 [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)]을 사용하여 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]를 관리하지 않고 [!INCLUDE[cmshort](../includes/cmshort_md.md)] 콘솔을 대신 사용합니다. [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] 은 여전히 Azure의 해당 클라우드 저장소를 사용하여 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

자세한 내용은 [!INCLUDE[cm5short](../includes/cm5short_md.md)] SP1 문서의 [Configuration Manager 및 Microsoft Intune을 사용하여 모바일 장치 관리](http://msdn.microsoft.com/library/2c6bd0e5-d436-41c8-bf38-30152d76be10)를 참조하세요.

### 참고 항목
[Microsoft Intune을 시작하기 전에 알아두어야 할 사항](what-to-know-before-you-start-microsoft-intune.md)

<!--HONumber=May16_HO1-->


