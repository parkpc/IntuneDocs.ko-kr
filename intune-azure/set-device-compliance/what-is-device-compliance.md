---
title: "장치 정책 준수"
titleSuffix: Intune Azure preview
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
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: f316b332c3f1b80b9d6af488943298fcfea13741
ms.openlocfilehash: 8cc5e12308871a3b023bed49e9647b888971f849
ms.lasthandoff: 03/30/2017


---

# <a name="what-is-device-compliance-in-intune-azure-preview"></a>Intune Azure 미리 보기에서 장치 준수란?

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Intune의 장치 준수 정책은 Intune 및 EMS 조건부 액세스 정책을 준수하는 것으로 간주되기 위해 장치가 준수해야 하는 규칙 및 설정을 정의합니다. 장치 준수 정책을 사용하여 장치를 모니터링하고 준수 문제를 수정할 수도 있습니다. 

이러한 규칙에는 다음이 포함됩니다.

- 장치에 액세스하는 데 암호 사용
- 암호화
- 장치의 무단 해제 또는 루팅 여부
- 필요한 최소 OS 버전
- 허용된 최대 OS 버전
- 장치가 Mobile Threat Defense 수준 이하여야 함

<!---##  Concepts
Following are some terms and concepts that are useful to understanding how to use compliance policies.

### Device compliance requirements
Compliance requirements are essentially rules like requiring a device PIN or encryption that you can specify as required or not required for a compliance policy.

### Actions for noncompliance

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

##  <a name="how-should-i-use-a-device-compliance-policy"></a>장치 준수 정책은 어떻게 사용해야 합니까?

### <a name="using-ems-conditional-access"></a>EMS 조건부 액세스 사용
준수 정책을 EMS 조건부 액세스와 함께 사용하여 하나 이상의 장치 준수 정책 규칙을 준수하는 장치만 메일 및 기타 회사 리소스에 액세스하도록 허용할 수 있습니다.

### <a name="not-using-ems-conditional-access"></a>EMS 조건부 액세스 사용 안 함
또한 장치 준수 정책을 EMS 조건부 액세스와 독립적으로 사용할 수 있습니다.
준수 정책을 독립적으로 사용하는 경우 대상 장치는 평가되고 준수 상태와 함께 보고됩니다. 예를 들어 암호화되지 않은 장치의 수나 무단 해제 또는 루팅된 장치에 대한 보고서를 가져올 수 있습니다. 그러나 준수 정책을 독립적으로 사용하는 경우 회사 리소스에 대한 액세스 제한이 없습니다.

사용자에게 준수 정책을 배포합니다. 준수 정책을 사용자에게 배포하면 사용자 장치의 준수가 확인됩니다. 정책이 배포된 후 모바일 장치가 정책을 수신하기까지 걸리는 시간에 대해 알아보려면 장치의 설정 및 기능 관리를 참조하세요.

##  <a name="intune-classic-admin-console-vs-intune-azure-preview-portal"></a>Intune 클래식 관리 콘솔과 Intune Azure Preview 포털

Intune 클래식 관리 콘솔을 사용해 왔다면 다음과 같은 차이점을 알면 Azure Portal의 새 장치 준수 정책 워크플로로 전환하는 데 도움이 됩니다.

-   Azure Portal에서 준수 정책은 지원되는 각 플랫폼에 대해 개별적으로 생성됩니다. Intune 관리 콘솔에서는 하나의 준수 정책이 지원되는 모든 플랫폼에 공통적으로 적용되었습니다.

<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are intiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

##  <a name="migration-from-intune-classic-console-to-intune-azure-preview-portal"></a>Intune 클래식 콘솔에서 Intune Azure Preview 포털로 마이그레이션

[Intune 클래식 콘솔](https://manage.microsoft.com)에서 만든 장치 준수 정책은 새 [Intune Azure Portal](https://portal.azure.com)에 표시되지 않습니다. 그러나 해당 정책은 여전히 사용자를 대상으로 하며 Intune 클래식 콘솔을 통해 관리할 수 있습니다.

Intune Azure Portal에서 새 장치 준수와 관련된 기능을 활용하려는 경우 Intune Azure Portal 자체에서 새로운 장치 준수 정책을 만들어야 합니다. Intune 클래식 포털에서도 장치 준수 정책을 할당받은 사용자에게 Intune Azure Portal의 새 장치 준수 정책을 할당하는 경우 Intune Azure Portal의 장치 준수 정책이 Intune 클래식 콘솔에서 만든 정책보다 우선합니다.

##  <a name="next-steps"></a>다음 단계

[장치 준수 정책 시작](get-started-with-device-compliance.md)


<!---### See also

Conditional access--->

