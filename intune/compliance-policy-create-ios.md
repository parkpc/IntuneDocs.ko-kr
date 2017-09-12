---
title: "iOS에 대한 준수 정책을 만드는 방법"
titleSuffix: Azure portal
description: "iOS 장치에 대한 준수 정책을 만드는 방법을 알아봅니다.\""
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3cfb8222-d05b-49e3-ae6f-36ce1a16c61d
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3b0fdb06b072c325d30b3e5ee72f1982c5f61849
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/09/2017
---
# <a name="how-to-create-a-device-compliance-policy-for-ios-devices-in-intune"></a>Intune에서 iOS 장치에 대한 장치 준수 정책을 만드는 방법


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

준수 정책은 각 플랫폼에 대해 생성됩니다.  Azure Portal에서 준수 정책을 만들 수 있습니다. 준수 정책에 대한 정의는 [장치 준수란?](device-compliance.md) 항목을 참조하세요. 준수 정책을 만들기 전에 해결해야 하는 전제 조건을 자세히 알아보려면 [장치 준수 시작](device-compliance-get-started.md) 항목을 참조하세요.

아래 표에서는 준수 정책을 조건부 액세스 정책과 함께 사용할 경우 비준수 설정을 관리하는 방법을 설명합니다.

-------------------------------


| **정책 설정** | **iOS 8.0 이상** |
| --- | --- |
| **PIN 또는 암호 구성** | 재구성됨 |   
| **장치 암호화** | 재구성됨(PIN 설정) |
| **무단 해제 또는 루팅된 장치** | 격리됨(설정 아님)
| **전자 메일 프로필** | 격리됨 |
|**최소 OS 버전** | 격리됨 |
| **최대 OS 버전** | 격리됨 |  
| **Windows 상태 증명** | 해당 없음 |  
----------------------------


**재구성됨** = 장치 운영 체제에서 준수를 적용하도록 요구합니다. (예를 들어 사용자에게 PIN을 설정하도록 강제합니다.)

**격리됨** = 장치 운영 체제에서 준수를 적용하도록 요구하지 않습니다. (예를 들어, Android 장치에서 사용자에게 장치를 암호화하도록 강제하지 않습니다.) 장치가 호환되지 않으면 다음 작업이 수행됩니다.

- 조건부 액세스 정책이 사용자에게 적용될 경우 장치가 차단됩니다.
- 회사 포털은 모든 준수 문제에 대해 사용자에게 알립니다.

## <a name="create-a-compliance-policy-in-the-azure-portal"></a>Azure Portal에서 준수 정책 만들기

1. **Intune** 블레이드에서 **장치 준수 설정**을 선택합니다. **관리** 아래에서 **모든 장치 준수 정책**을 선택한 다음 **만들기**를 선택합니다.
2. 이름 및 설명을 입력하고 이 정책을 적용할 플랫폼을 선택합니다.
3. **준수 요구 사항**을 선택하여 **보안**, **장치 상태** 및 **장치 속성** 설정을 지정합니다. 작업이 끝나면 **확인**을 선택합니다.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant with this policy.
5. In the **Actions for noncompliance** blade, choose **Add** to create a new action.  The action parameters blade allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
7. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **Ok** when you are finished creating all the actions.--->

## <a name="assign-user-groups"></a>사용자 그룹 할당

준수 정책을 사용자에게 할당하려면 구성한 정책을 선택합니다. 기존 정책은 **준수 – 정책** 블레이드에서 찾을 수 있습니다.

1. 사용자에게 할당할 정책을 선택한 다음 **할당**을 선택합니다. **Azure Active Directory 보안 그룹**을 선택하고 정책에 할당할 수 있는 블레이드가 열립니다.
2. **그룹 선택**을 선택하여 Azure AD 보안 그룹을 표시하는 블레이드를 엽니다.  **선택**을 선택하면 정책이 사용자에게 배포됩니다.

사용자에게 정책을 적용했습니다.  정책의 대상 사용자가 사용하는 장치에 대해 준수 여부가 평가됩니다.

<!---## Compliance policy settings--->

## <a name="system-security-settings"></a>시스템 보안 설정

### <a name="password"></a>암호

- **모바일 장치의 잠금을 해제하는 데 암호 필요:** 장치에 액세스하기 전에 사용자가 암호를 입력하도록 하려면 **예**로 설정합니다. 암호를 사용하는 iOS 장치는 암호화됩니다.
- **단순 암호 허용**: 사용자가 **1234** 또는 **1111**과 같은 간단한 암호를 만들도록 하려면 **예**로 설정합니다.
- **최소 암호 길이**: 암호에 포함해야 하는 최소 자릿수 또는 문자 수를 지정합니다.
- **필수 암호 유형**: 사용자가 **영숫자** 암호 또는 **숫자** 암호를 만들어야 할지를 지정합니다.
- **최소 문자 집합 수**: **필수 암호 유형**을 **영숫자**로 설정한 경우 이 설정을 사용하여 암호에 포함해야 하는 최소 문자 집합 수를 지정합니다. 4가지 문자 집합은 다음과 같습니다.
  - 소문자
  - 대문자
  - 기호
  - 숫자

더 큰 값을 설정하면 사용자는 더욱 복잡한 암호를 만들어야 합니다.

iOS 장치의 경우 이 설정은 암호에 포함해야 하는 특수 문자(예: **!** , **#**, **&amp;**) 수를 나타냅니다.

- **암호를 요구하기 전까지 비활성 시간(분)**: 사용자가 해당 시간 내에 자신의 암호를 다시 입력해야 하는 유휴 시간을 지정합니다.
- **암호 만료(일)**: 암호가 만료된 후 새로 만들어야 하기 전까지의 일수를 선택합니다.
- **암호 기록 기억**: 이 설정을 **이전 암호 다시 사용 방지**와 함께 사용하여 사용자가 이전에 사용했던 암호를 만들지 못하게 제한할 수 있습니다.
- **이전 암호 다시 사용 방지**: **암호 기록 기억**을 선택한 경우 다시 사용할 수 없는 이전에 사용했던 암호 수를 지정합니다.
- **장치가 유휴 상태에서 되돌아오는 경우 암호 필요**: 이 설정은 **암호를 요구하기 전까지 비활성 시간(분)** 설정과 함께 사용해야 합니다. **암호를 요구하기 전까지 비활성 시간(분)** 설정에 지정된 시간 동안 비활성화 상태인 장치에 사용자가 액세스하려고 하면 암호를 입력하라는 메시지가 표시됩니다.

### <a name="email-profile"></a>전자 메일 프로필

- **메일 계정은 Intune을 통해 관리해야 함**: 이 옵션이 **예**로 설정된 경우 장치는 장치에 배포된 메일 프로필을 사용해야 합니다. 다음과 같은 상황에서는 장치가 정책을 준수하지 않는 것으로 간주됩니다.
  - 메일 프로필은 준수 정책의 대상으로 지정된 사용자 그룹 이외의 사용자 그룹에 배포됩니다.
  - 사용자가 장치에 배포된 Intune 메일 프로필과 일치하는 메일 계정을 이미 장치에서 설정했습니다. Intune은 사용자가 프로비전한 프로필을 덮어쓸 수 없으므로 이러한 프로필을 관리할 수 없습니다. 장치의 준수 상태를 유지하려면 사용자는 기존 메일 설정을 제거해야 합니다. 그런 다음 Intune이 관리되는 메일 프로필을 설치할 수 있습니다.
- **Intune에서 관리해야 하는 메일 프로필 선택**: **Intune에서 메일 계정을 관리해야 함** 설정을 선택할 경우 **선택**을 선택하여 Intune 메일 프로필을 지정합니다. 장치에 전자 메일 프로필이 있어야 합니다.

메일 프로필에 대한 자세한 내용은 [Microsoft Intune에서 메일 프로필을 사용하여 회사 메일에 대한 액세스 구성](https://docs.microsoft.com/intune-classic/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune)을 참조하세요.

## <a name="device-health-settings"></a>장치 상태 설정

- **장치는 탈옥 또는 루팅되지 않아야 함**: 이 설정을 사용하도록 설정하는 경우 탈옥된 장치는 비준수 상태가 됩니다.

## <a name="device-properties"></a>장치 속성

- **필요한 최소 OS**: 장치가 OS 최소 버전 요구 사항을 충족하지 못하면 비규격 장치로 보고됩니다. 업그레이드 방법에 대한 정보를 제공하는 링크가 표시됩니다. 사용자는 장치를 업그레이드하도록 선택할 수 있습니다. 그런 다음 회사 리소스에 액세스할 수 있습니다.
- **허용되는 최대 OS 버전**: 장치가 규칙에 지정된 버전 이후의 OS를 사용하는 경우 회사 리소스에 대한 액세스가 차단되고 IT 관리자에게 문의하라는 메시지가 사용자에게 표시됩니다. OS 버전 허용 규칙이 변경될 때까지 회사 리소스에 액세스하는 데 이 장치를 사용할 수 없습니다.

<!--- ## Next steps

[How to monitor device compliance](device-compliance-monitor.md)--->
