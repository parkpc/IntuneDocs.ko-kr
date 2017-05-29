---
title: "조건부 액세스란?"
titleSuffix: Intune Azure preview
description: "Intune Azure 미리 보기: 사용자 및 장치가 Microsoft Intune Azure 미리 보기에서 회사 리소스에 액세스하기 위해 충족해야 하는 조건을 정의하는 방법을 알아봅니다."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1973f38-ea55-43eb-a151-505fb34a8afb
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 8ab6d782460a857a0901abd9bd567365ee2e3f70
ms.contentlocale: ko-kr
ms.lasthandoff: 05/23/2017


---

# <a name="what-is-conditional-access"></a>조건부 액세스란?


[!INCLUDE[azure_preview](./includes/azure_preview.md)]


이 항목에서는 Enterprise Mobility + Security에 적용되는 조건부 액세스 및 Intune의 조건부 액세스 기능을 설명합니다.

EMS(Enterprise Mobility + Security)의 조건부 액세스는 Azure Active Directory Premium 및 Microsoft Intune의 기능을 활용하여 회사 데이터의 보안을 유지하는 동시에 직원들이 모든 장치에서 최상의 업무를 수행할 수 있는 환경을 조성하는 데 필요한 제어 권한을 제공합니다.

조건부 액세스를 사용하면 위치, 장치 및 사용자 상태, 응용 프로그램 민감도 등을 기반으로 회사 데이터에 대한 액세스를 제한하는 조건을 정의할 수 있습니다.

장치의 관점에서 Intune과 Azure Active Directory는 함께 작동하여 관리되는 준수 장치에서만 메일 및 Office 365 서비스에 액세스할 수 있도록 합니다. 예를 들어 Azure Active Directory에서 도메인에 가입된 컴퓨터 또는 모바일 장치 관리 응용 프로그램(예: Intune)에 등록된 모바일 장치에서만 Office 365 서비스에 액세스할 수 있도록 하는 정책을 설정할 수 있습니다. Intune을 사용하여 장치의 준수 상태를 평가하는 장치 준수 프로필을 설정할 수 있습니다. 준수 상태는 사용자가 회사 리소스에 액세스하려고 하면 Azure Active Directory에서 정책을 적용하는 데 사용되도록 Azure Active Directory에 보고됩니다. Intune의 장치 준수에 대해 알아보려면 [장치 준수란?](device-compliance.md)을 참조하세요.

Azure Active Directory를 통해 Exchange Online과 같은 클라우드 앱에 대한 조건부 액세스를 구성할 수 있습니다. 자세한 내용은 [이 문서](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)를 참조하세요.

## <a name="on-premises-conditional-access-in-intune"></a>Intune의 온-프레미스 조건부 액세스

Intune의 조건부 액세스를 사용하여 장치 관리 및 등록을 기반으로 **Exchange 온-프레미스**에 대한 액세스를 허용하거나 차단할 수 있습니다.

장치 준수 프로필 설정은 장치의 규정 준수를 평가하는 데 사용됩니다. 조건부 액세스에서는 이 평가를 사용하여 Exchange 온-프레미스에 대한 액세스를 허용하거나 차단합니다. 조건부 액세스를 장치 준수 프로필과 함께 사용하면 준수 장치에서만 Exchange 온-프레미스에 액세스할 수 있습니다. 특정 플랫폼을 허용 또는 차단하거나 Intune에서 관리되지 않는 장치를 즉시 차단하는 등 보다 세분화된 제어를 위해 조건부 액세스에서 고급 설정을 구성할 수 있습니다.

장치 준수 프로필 및 조건부 액세스는 사용자에게 할당됩니다. 사용자가 Exchange 온-프레미스에 액세스하는 데 사용하는 모든 장치에 대해 준수 여부가 확인됩니다. 장치를 사용하는 사용자는 준수 프로필이 할당되어 있어야 장치에 대한 준수 여부가 평가됩니다. 사용자에게 규정 준수 정책이 배포되지 않은 경우 장치는 준수하는 것으로 간주되며 액세스 제한이 적용되지 않습니다.

장치가 설정된 조건을 충족하지 않는 경우 최종 사용자에게 장치를 등록하고 비준수의 원인이 되는 문제를 해결하는 과정이 안내됩니다.

## <a name="next-steps"></a>다음 단계

[Exchange 온-프레미스에 대한 조건부 액세스 정책을 만드는 방법](conditional-access-exchange-create.md)

[Azure Active Directory에서 조건부 액세스를 구성하는 방법](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)

