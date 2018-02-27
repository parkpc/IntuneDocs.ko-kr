---
title: "Intune 장치 준수 정책"
titleSuffix: Azure portal
description: "이 항목에서는 Microsoft Intune의 장치 준수에 대해 알아봅니다.\""
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 2/6/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 98a9a93efb93697b454cb9bc06d1ac268ebaf9d8
ms.sourcegitcommit: cccbb6730a8c84dc3a62093b8910305081ac9d24
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2018
---
# <a name="get-started-with-intune-device-compliance-policies"></a>Intune 장치 준수 정책 시작

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="what-is-device-compliance-in-intune"></a>Intune의 장치 준수란?

Intune 장치 준수 정책은 장치가 Intune에서 준수되는 것으로 간주하기 위해 준수해야 하는 규칙 및 설정을 정의합니다.

이러한 규칙에는 다음이 포함됩니다.

- 장치에 액세스하는 데 암호 사용

- 암호화

- 장치의 무단 해제 또는 루팅 여부

- 필요한 최소 OS 버전

- 허용된 최대 OS 버전

- 장치가 Mobile Threat Defense 수준 이하여야 함

장치 준수 정책을 사용하여 장치에서 준수 상태를 모니터링할 수도 있습니다.

### <a name="device-compliance-requirements"></a>장치 정책 준수 요구 사항

준수 요구 사항은 기본적으로 준수 정책에 필요하거나 필요하지 않도록 지정할 수 있는 장치 PIN 또는 암호화 요구와 같은 규칙입니다.

<!---### Actions for noncompliance

You can specify what needs to happen when a device is determined as noncompliant. This can be a sequence of actions during a specific time.
When you specify these actions, Intune will automatically initiate them in the sequence you specify. See the following example of a sequence of
actions for a device that continues to be in the noncompliant status for
a week:

-   When the device is first determined to be noncompliant, an email with noncompliant notification is sent to the user.

-   3 days after initial noncompliance state, a follow up reminder is sent to the user.

-   5 days after initial noncompliance state, a final reminder with a notification that access to company resources will be blocked on the device in 2 days if the compliance issues are not remediated is sent to the user.

-   7 days after initial noncompliance state, access to company resources is blocked. This requires that you have conditional access policy that specifies that access from noncompliant devices should    be blocked for services such as Exchange and SharePoint.

### Grace Period

This is the time between when a device is first determined as
noncompliant to when access to company resources on that device is blocked. This time allows for time that the user has to resolve
compliance issues on the device. You can also use this time to create your action sequences to send notifications to the user before their access is blocked.

Remember that you need to implement conditional access policies in addition to compliance policies in order for access to company resources to be blocked.--->

##  <a name="pre-requisites"></a>필수 구성 요소

Intune에서 장치 준수 정책을 사용하려면 다음과 같은 구독이 있어야 합니다.

- Intune EMS

- Azure AD Premium

###  <a name="supported-platforms"></a>지원되는 플랫폼:

-   Android

-   iOS

-   macOS(미리 보기)

-   Windows 8.1

-   Windows Phone 8.1

-   Windows 10

> [!IMPORTANT]
> 준수 상태를 보고하려면 장치가 Intune에 등록되어야 합니다.

## <a name="how-intune-device-compliance-policies-work-with-azure-ad"></a>Azure AD에서 Intune 장치 준수 정책이 사용되는 방식

장치가 Intune에 등록되면 Azure AD 등록 프로세스가 수행되고 추가 정보를 사용하여 장치 특성이 Azure AD로 업데이트됩니다. 하나의 주요 장치 정보는 장치 준수 상태로, 조건부 액세스 정책에서 메일 및 기타 회사 리소스에 대한 액세스를 차단하거나 허용하는 데 사용됩니다.

- [Azure AD 등록 프로세스](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction)에 대해 자세히 알아보세요.

### <a name="assigning-a-resulting-device-configuration-profile-status"></a>결과 장치 구성 프로필 상태 할당

장치에 할당된 여러 구성 프로필이 있고 장치에 두 개 이상의 할당된 구성 프로필에 대한 다양한 준수 상태가 있는 경우 단일 결과 준수 상태가 할당되어야 합니다. 이 할당은 각 호환성 상태에 할당된 개념적 심각도 수준을 기반으로 합니다. 각 호환성 상태에는 다음과 같은 심각도 수준이 있습니다.


|상태  |심각도  |
|---------|---------|
|Pending     |1|
|성공     |2|
|Failed     |3|
|오류     |4|

두 개 이상의 구성 프로필의 결과 상태는 장치에 할당된 모든 프로필의 가장 높은 심각도 수준을 선택하여 할당됩니다.

예를 들어, 장치에 할당된 프로필이 보류 중 상태 하나(심각도 = 1), 성공 상태 하나(심각도 = 2), 오류 상태 하나(심각도 = 4)와 같이 세 가지가 있습니다. 오류 상태는 가장 높은 심각도 수준이므로 세 개의 프로필 모두에 대한 결과 준수 상태로 할당됩니다.

### <a name="assigning-an-ingraceperiod-status-for-an-assigned-compliance-policy"></a>할당된 준수 정책에 대한 InGracePeriod 상태 할당

준수 정책에 대한 InGracePeriod 상태는 할당된 준수 정책에 대한 장치의 실제 상태와 장치의 유예 기간의 조합을 고려하여 지정된 값입니다. 

특히 장치에 할당된 준수 정책에 대한 NonCompliant 상태가 있고,

- 장치에 할당된 유예 기간이 없는 경우 준수 정책에 할당된 값은 NonCompliant입니다.
- 장치에 유예 기간이 만료된 경우 준수 정책에 할당된 값은 NonCompliant입니다.
- 장치에 향후 유예 기간이 있는 경우 준수 정책에 할당된 값은 InGracePeriod입니다.

다음 표에 이전 지점이 요약되어 있습니다.


|실제 준수 상태|할당된 유예 기간의 값|유효 준수 상태|
|---------|---------|---------|
|NonCompliant |할당된 유예 시간 없음 |NonCompliant |
|NonCompliant |어제 날짜|NonCompliant|
|NonCompliant |향후 날짜|InGracePeriod|

장치 준수 정책 모니터링에 대한 자세한 내용은 [Intune 장치 준수 정책 모니터링](compliance-policy-monitor.md)을 참조하세요.

### <a name="assigning-a-resulting-compliance-policy-status"></a>결과 준수 정책 상태 할당

장치에 할당된 여러 준수 정책이 있고 장치에 두 개 이상의 할당된 준수 정책에 대한 다양한 준수 상태가 있는 경우, 단일 결과 준수 상태가 할당되어야 합니다. 이 할당은 각 호환성 상태에 할당된 개념적 심각도 수준을 기반으로 합니다. 각 호환성 상태에는 다음과 같은 심각도 수준이 있습니다. 

|상태  |심각도  |
|---------|---------|
|Unknown     |1|
|NotApplicable     |2|
|규정|3|
|InGracePeriod|4|
|NonCompliant|5|
|오류|6|

두 개 이상의 준수 정책의 결과 상태는 장치에 할당된 모든 정책의 가장 높은 심각도 수준을 선택하여 결정됩니다.
 
예를 들어, 장치에는 할당된 준수 정책이 알 수 없는 상태 하나(심각도 = 1), 호환 상태 하나(심각도 = 3), InGracePeriod 상태 하나(심각도 = 4)와 같이 세 가지가 있습니다. InGracePeriod 상태는 가장 높은 심각도 수준이므로 세 개의 프로필 모두에 대한 결과 준수 상태로 할당됩니다.  

##  <a name="ways-to-use-device-compliance-policies"></a>장치 준수 정책을 사용하는 방법

### <a name="with-conditional-access"></a>조건부 액세스 사용
준수 정책을 조건부 액세스와 함께 사용하여 하나 이상의 장치 준수 정책 규칙을 준수하는 장치만 메일 및 기타 회사 리소스에 액세스하도록 허용할 수 있습니다.

### <a name="without-conditional-access"></a>조건부 액세스 사용 안 함
또한 장치 준수 정책을 조건부 액세스와 독립적으로 사용할 수 있습니다. 준수 정책을 독립적으로 사용하는 경우 대상 장치는 평가되고 준수 상태와 함께 보고됩니다. 예를 들어 암호화되지 않은 장치의 수나 무단 해제 또는 루팅된 장치에 대한 보고서를 가져올 수 있습니다. 그러나 준수 정책을 독립적으로 사용하는 경우 회사 리소스에 대한 액세스 제한이 없습니다.

사용자에게 준수 정책을 배포합니다. 준수 정책을 사용자에게 배포하면 사용자 장치의 준수가 확인됩니다. 정책이 배포된 후 모바일 장치가 정책을 수신하기까지 걸리는 시간에 대해 알아보려면 [Microsoft Intune의 장치 프로필 문제 해결](device-profile-troubleshoot.md#how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-assigned)을 참조하세요.

#### <a name="actions-for-non-compliance"></a>비준수에 대한 작업

비준수에 대한 작업을 사용하면 준수 정책 기준을 충족하지 않는 장치에 적용되는 작업을 시간순으로 구성할 수 있습니다. 자세한 내용은 [비준수에 대한 작업 자동화](actions-for-noncompliance.md)를 참조하세요.

##  <a name="using-device-compliance-policies-in-the-intune-classic-portal-vs-azure-portal"></a>장치 준수 정책 사용: Intune 클래식 포털 및 Azure 포털

주요 차이점을 알면 Azure Portal의 새 장치 준수 정책 워크플로로 전환하는 데 도움이 됩니다.

- Azure Portal에서 준수 정책은 지원되는 각 플랫폼에 대해 개별적으로 생성됩니다.
- Intune 클래식 콘솔에서는 하나의 장치 준수 정책이 지원되는 모든 플랫폼에 공통적으로 적용되었습니다.

<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are intiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

##  <a name="migrate-device-compliance-policies-from-the-intune-classic-portal-to-the-azure-portal"></a>Intune 클래식 포털에서 Azure Portal로 장치 준수 정책 마이그레이션

[Intune 클래식 포털](https://manage.microsoft.com)에서 만든 장치 준수 정책은 새 [Intune Azure Portal](https://portal.azure.com)에 표시되지 않습니다. 그러나 해당 정책은 여전히 사용자를 대상으로 하며 Intune 클래식 포털을 통해 관리할 수 있습니다.

Azure Portal에서 새 장치 준수와 관련된 기능을 활용하려는 경우 Azure Portal 자체에서 새로운 장치 준수 정책을 만들어야 합니다. Intune 클래식 포털에서도 장치 준수 정책을 할당받은 사용자에게 Azure Portal의 새 장치 준수 정책을 할당하는 경우 Intune Azure Portal의 장치 준수 정책이 Intune 클래식 포털에서 만든 정책보다 우선합니다.

##  <a name="next-steps"></a>다음 단계

- 다음 플랫폼에 대한 장치 준수 정책을 만듭니다.

   - [OWA(Outlook Web Access)](compliance-policy-create-android.md)
   - [Android for Work](compliance-policy-create-android-for-work.md)
   - [iOS](compliance-policy-create-ios.md)
   - [macOS](compliance-policy-create-mac-os.md)
   - [Windows](compliance-policy-create-windows.md)

- Intune 데이터 웨어하우스 정책 엔터티에 대한 자세한 내용은 [정책 엔터티에 대한 참조](reports-ref-policy.md)를 확인하세요.
