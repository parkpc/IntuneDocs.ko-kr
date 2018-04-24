---
title: Microsoft Intune에서 iOS 장치 규정 준수 정책 만들기 - Azure | Microsoft Docs
description: iOS 장치에 대한 Microsoft Intune 장치 규정 준수 정책을 만들어서 이메일 계정을 입력하고, 무단 해제된 장치를 확인하고, 최소 및 최대 운영 체제를 확인하고, 암호 길이 및 장치 비활성화를 비롯한 암호 제한을 설정합니다.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/20/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3cfb8222-d05b-49e3-ae6f-36ce1a16c61d
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 887f45cdc79aa5e45de3e8a1df5d12665d2ed8ab
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="add-a-device-compliance-policy-for-ios-devices-in-intune"></a>Intune에서 iOS 장치에 대한 장치 준수 정책 추가

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune iOS 장치 준수 정책은 iOS 장치가 준수하도록 충족해야 하는 규칙과 설정을 결정합니다. 조건부 액세스 정책을 사용하여 장치 준수 정책을 사용하는 경우 회사 리소스에 대한 액세스를 허용하거나 차단할 수 있습니다. 장치 보고서를 가져오 고 비준수에 대해 조치를 할 수 있습니다. Intune Azure Portal에서 각 플랫폼에 대한 장치 준수 정책을 만듭니다. 준수 정책을 만들기 전에 필요한 준수 정책 및 필수 구성 요소에 대해 자세히 알아보려면 [장치 준수 시작](device-compliance-get-started.md)을 참조하세요.

다음 표에서는 준수 정책을 조건부 액세스 정책과 함께 사용할 경우 비준수 설정을 관리하는 방법을 설명합니다.

| **정책 설정** | **iOS 8.0 이상** |
| --- | --- |
| **PIN 또는 암호 구성** | 재구성됨 |
| **장치 암호화** | 재구성됨(PIN 설정) |
| **무단 해제 또는 루팅된 장치** | 격리됨(설정 아님)
| **전자 메일 프로필** | 격리됨 |
|**최소 OS 버전** | 격리됨 |
| **최대 OS 버전** | 격리됨 |
| **Windows 상태 증명** | 해당 없음 |

**재구성됨** = 장치 운영 체제에서 준수를 적용하도록 요구합니다. (예를 들어 사용자에게 PIN을 설정하도록 강제합니다.)

**격리됨** = 장치 운영 체제에서 준수를 적용하도록 요구하지 않습니다. (예를 들어, Android 장치에서 사용자에게 장치를 암호화하도록 강제하지 않습니다.) 장치가 호환되지 않으면 다음 작업이 수행됩니다.

- 조건부 액세스 정책이 사용자에게 적용될 경우 장치가 차단됩니다.
- 회사 포털은 모든 준수 문제에 대해 사용자에게 알립니다.

## <a name="create-a-compliance-policy-in-the-azure-portal"></a>Azure Portal에서 준수 정책 만들기

1. [Azure 포털](https://portal.azure.com)에 로그인합니다.
2. **모든 서비스**를 선택하고 **Intune**에서 필터링하고 **Microsoft Intune**을 선택합니다.
3. **장치 준수** > **정책** > **정책 만들기**를 선택합니다.
4. 이름 및 설명을 입력하고 이 정책을 적용할 플랫폼을 선택합니다.
5. **설정**을 선택하고, **이메일**, **장치 상태**, **장치 속성** 및 **시스템 보안** 설정을 입력합니다. 작업이 완료되면 **확인**을 선택합니다.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant with this policy.
5. In the **Actions for noncompliance** pane, choose **Add** to create a new action.  The action parameters pane allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
7. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **Ok** when you are finished creating all the actions.--->

## <a name="assign-user-groups"></a>사용자 그룹 할당

준수 정책을 사용자에게 할당하려면 구성한 정책을 선택합니다. 기존 정책은 **장치 준수 정책** 창에서 확인할 수 있습니다.

1. 사용자에게 할당할 정책을 선택한 다음 **할당**을 선택합니다. **Azure Active Directory 보안 그룹**을 선택하고 정책에 할당할 수 있는 경우 창이 열립니다.
2. **그룹 선택**을 선택하여 Azure AD 보안 그룹을 표시하는 창을 엽니다.  **저장**을 선택하면 정책이 사용자에게 배포됩니다.

사용자에게 정책을 적용했습니다.  정책의 대상이 되는 사용자가 사용하는 장치에 대한 규정 준수 여부가 평가됩니다.

<!---## Compliance policy settings--->

## <a name="email"></a>메일

- **메일 계정은 Intune을 통해 관리해야 함:** 이 옵션이 **예**로 설정된 경우 장치는 장치에 배포된 메일 프로필을 사용해야 합니다. 다음과 같은 상황에서는 장치가 정책을 준수하지 않는 것으로 간주됩니다.
  - 메일 프로필은 준수 정책의 대상으로 지정된 사용자 그룹 이외의 사용자 그룹에 배포됩니다.
  - 사용자가 장치에 배포된 Intune 메일 프로필과 일치하는 메일 계정을 이미 장치에서 설정했습니다. Intune은 사용자가 프로비전한 프로필을 덮어쓸 수 없으므로 이러한 프로필을 관리할 수 없습니다. 장치의 준수 상태를 유지하려면 사용자는 기존 메일 설정을 제거해야 합니다. 그런 다음 Intune이 관리되는 메일 프로필을 설치할 수 있습니다.
- **Intune에서 관리해야 하는 메일 프로필 선택**: **Intune에서 메일 계정을 관리해야 함** 설정을 선택할 경우 **선택**을 선택하여 Intune 메일 프로필을 지정합니다. 장치에 전자 메일 프로필이 있어야 합니다.

메일 프로필에 대한 자세한 내용은 [Microsoft Intune에서 메일 프로필을 사용하여 회사 메일에 대한 액세스 구성](https://docs.microsoft.com/intune-classic/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune)을 참조하세요.

## <a name="device-health"></a>Device health

- **무단 해제된 장치**: 이 설정을 사용하도록 설정하면 무단 해제된 장치는 규정을 준수하지 않습니다.
- **장치를 장치 위협 수준 이하로 유지**: 최대 위협 수준을 선택하여 장치를 비준수로 표시합니다. 예를 들어, 위협 수준을 **보통**으로 설정하는 경우 보통, 낮음 또는 보안된 장치는 규정을 준수합니다. 높은 위협 수준의 장치는 비준수입니다.

## <a name="device-properties"></a>장치 속성

- **필요한 최소 OS**: 장치가 OS 최소 버전 요구 사항을 충족하지 못하면 비준수 장치로 보고됩니다. 업그레이드 방법에 대한 정보를 제공하는 링크가 표시됩니다. 사용자는 장치를 업그레이드하도록 선택할 수 있습니다. 그런 다음 회사 리소스에 액세스할 수 있습니다.
- **허용된 최대 OS 버전**: 장치가 규칙에 지정된 버전 이상의 OS 버전을 사용하는 경우 회사 리소스에 대한 액세스가 차단됩니다. 그런 다음, 사용자에게는 IT 관리자에게 문의하라는 메시지가 표시됩니다. OS 버전 허용 규칙이 변경될 때까지 이 장치는 회사 리소스에 액세스할 수 없습니다.

## <a name="system-security"></a>시스템 보안

### <a name="password"></a>암호

> [!NOTE]
> 준수 또는 구성 정책을 iOS 장치에 적용하면 사용자에게 15분마다 암호를 설정하라는 메시지가 표시됩니다. 사용자가 암호를 설정할 때까지 계속 메시지가 표시됩니다.

- **모바일 장치의 잠금을 해제하는 데 암호 필요**: 장치에 액세스하기 전에 사용자가 암호를 입력하도록 하려면 **예**로 설정합니다. 암호를 사용하는 iOS 장치는 암호화됩니다.
- **단순 암호**: 사용자가 **1234** 또는 **1111**과 같은 암호를 만들도록 하려면 **예**로 설정합니다.
- **최소 암호 길이**: 암호에 포함해야 하는 최소 자릿수 또는 문자 수를 입력합니다.
- **필수 암호 유형**: 사용자가 **영숫자** 암호 또는 **숫자** 암호를 만들어야 할지를 입력합니다.
- **영숫자가 아닌 암호의 문자 수**: 암호에 포함해야 하는 특수 문자의 최소 수(&, #, %, ! 등)를 입력합니다.

    더 큰 값을 설정하면 사용자는 더욱 복잡한 암호를 만들어야 합니다.

- **암호를 요구하기 전까지 최대 비활성 시간(분)**: 사용자가 해당 시간 내에 자신의 암호를 다시 입력해야 하는 유휴 시간을 입력합니다.
- **암호 만료(일)**: 암호가 만료된 후 새로 만들어야 하기 전까지의 일수를 선택합니다.
- **재사용을 방지하기 위한 이전 암호 수**: 사용할 수 없는 이전에 사용된 암호의 수를 입력합니다.

<!--- ## Next steps

[How to monitor device compliance](device-compliance-monitor.md)--->
