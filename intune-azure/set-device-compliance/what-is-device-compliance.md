---
title: "장치 준수 | Intune Azure 미리 보기 | Microsoft Docs"
description: "Intune Azure 미리 보기: 이 항목에서는 Microsoft Intune의 장치 준수에 대해 알아봅니다."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a916fa0d-890d-4efb-941c-7c3c05f8fe7c
ms.reviewer: muhosabe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 7693d49e2f0fa6e4aa40b6bb71433a7eaab8dd15
ms.openlocfilehash: a4254503e4e6b86079f862966dee2727934f1ee6


---

# <a name="what-is-device-compliance-in-intune-azure-preview"></a>Intune Azure 미리 보기에서 장치 준수란?


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

회사 데이터를 보호하는 데 도움이 되려면 회사 앱 및 데이터에 액세스하는 데 사용되는 장치가 특정 규칙을 준수하는지 확인해야 합니다. 이러한 규칙에는 장치에 액세스하는 데 PIN을 사용하고 장치에 저장된 데이터를 암호화하는 규칙이 포함됩니다. 이러한 규칙의 집합을 **준수 정책**이라고 합니다.

##  <a name="how-should-i-use-a-device-compliance-policy"></a>장치 준수 정책은 어떻게 사용해야 합니까?
준수 정책을 조건부 액세스와 함께 사용하여 준수 정책 규칙을 준수하는 장치만 메일과 기타 서비스에 액세스할 수 있도록 허용할 수 있습니다.

또한 준수 정책을 조건부 액세스와 독립적으로 사용할 수 있습니다.
준수 정책을 독립적으로 사용하는 경우 대상 장치는 평가되고 준수 상태와 함께 보고됩니다. 예를 들어 암호화되지 않은 장치의 수 또는 탈옥 또는 루팅된 장치에 대한 보고서를 가져올 수 있습니다. 그러나 준수 정책을 독립적으로 사용하는 경우 회사 리소스에 대한 액세스 제한이 없습니다.

사용자에게 준수 정책을 배포합니다. 준수 정책을 사용자에게 배포하면 사용자 장치의 준수가 확인됩니다. 정책이 배포된 후 모바일 장치가 정책을 수신하기까지 걸리는 시간에 대해 알아보려면 장치의 설정 및 기능 관리를 참조하세요.

##  <a name="concepts"></a>개념
다음은 준수 정책 사용 방법을 이해하는 데 유용한 몇 가지 조건 및 개념입니다.

### <a name="compliance-requirements"></a>준수 요구 사항
준수 요구 사항은 기본적으로 준수 정책에 필요하거나 필요하지 않도록 지정할 수 있는 장치 PIN 또는 암호화 요구와 같은 규칙입니다.

<!---### Actions for noncompliance

You can specify what needs to happen when a device is determined as noncompliant. This can be a sequence of actions during a specific time.
When you specify these actions, Intune will automatically initiate them in the sequence you specify. See the following example of a sequence of
actions for a device that continues to be in the noncompliant status for
a week:

-   When the device is first determined to be non-compliant, an email with noncompliant notification is sent to the user.

-   3 days after initial noncompliance state, a follow up reminder is sent to the user.

-   5 days after initial noncompliance state, a final reminder with a notification that access to company resources will be blocked on the device in 2 days if the compliance issues are not remediated is sent to the user.

-   7 days after initial noncompliance state, access to company resources is blocked. This requires that you have conditional access policy that specifies that access from noncompliant devices should    be blocked for services such as Exchange and SharePoint.

### Grace Period

This is the time between when a device is first determined as
noncompliant to when access to company resources on that device is blocked. This time allows for time that the user has to resolve
compliance issues on the device. You can also use this time to create your action sequences to send notifications to the user before their access is blocked.

Remember that you need to implement conditional access policies in addition to compliance policies in order for access to company resources to be blocked.--->

##  <a name="differences-between-the-classic-intune-admin-console-and-intune-in-the-azure-portal"></a>클래식 Intune 관리 콘솔과 Azure Portal의 Intune 간 차이점


이전에 클래식 Intune 관리 콘솔을 사용한 경우 다음과 같은 차이점을 알면 Azure Portal의 새 장치 준수 워크플로로 전환하는 데 도움이 됩니다.


-   Azure Portal에서 준수 정책은 지원되는 각 플랫폼에 대해 개별적으로 생성됩니다. Intune 관리 콘솔에서는 하나의 준수 정책이 지원되는 모든 플랫폼에 공통적으로 적용되었습니다.


<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are intiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

##  <a name="next-steps"></a>다음 단계

[준수 정책 시작](get-started-with-device-compliance.md)


<!---### See also

Conditional access--->



<!--HONumber=Feb17_HO1-->


