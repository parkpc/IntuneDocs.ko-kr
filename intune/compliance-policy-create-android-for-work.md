---
title: "Android for Work에 대한 준수 정책 만들기"
titleSuffix: Intune Azure preview
description: "Intune Azure 미리 보기: Android for Work 장치에 대한 준수 정책을 만드는 방법을 알아봅니다."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9da89713-6306-4468-b211-57cfb4b51cc6
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: af5aa4f336df0f47695484b7dce1d7df29bea03d
ms.contentlocale: ko-kr
ms.lasthandoff: 05/23/2017


---

# <a name="how-to-create-a-device-compliance-policy-for-android-for-work-devices-in-intune-azure-preview"></a>Intune Azure 미리 보기에서 Android for Work 장치에 대한 장치 준수 정책을 만드는 방법


[!INCLUDE[azure_preview](./includes/azure_preview.md)]

준수 정책은 각 플랫폼에 대해 생성됩니다.  Azure Portal에서 준수 정책을 만들 수 있습니다. 준수 정책에 대한 정의는 [장치 준수란?](device-compliance.md) 항목을 참조하세요. 준수 정책을 만들기 전에 해결해야 하는 전제 조건을 자세히 알아보려면 [장치 준수 시작](device-compliance-get-started.md) 항목을 참조하세요.

아래 표에서는 준수 정책을 조건부 액세스 정책과 함께 사용할 경우 비준수 설정을 관리하는 방법을 설명합니다.

--------------------------

|**정책 설정**| **Android for Work** |
| --- | --- |
| **PIN 또는 암호 구성** |  격리됨 |
| **장치 암호화** |  격리됨 |
| **무단 해제 또는 루팅된 장치** | 격리됨(설정 아님) |
| **메일 프로필** | 해당 없음 |
| **최소 OS 버전** | 격리됨 |
| **최대 OS 버전** | 격리됨 |
| **Windows 상태 증명** |해당 없음 |

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
6. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **Ok** when you are finished creating all the actions.--->

## <a name="assign-user-groups"></a>사용자 그룹 할당

준수 정책을 사용자에게 할당하려면 구성한 정책을 선택합니다. 기존 정책은 **준수 – 정책** 블레이드에서 찾을 수 있습니다.

1. 사용자에게 할당할 정책을 선택한 다음 **할당**을 선택합니다. **Azure Active Directory 보안 그룹**을 선택하고 정책에 할당할 수 있는 블레이드가 열립니다.
2. **그룹 선택**을 선택하여 Azure AD 보안 그룹을 표시하는 블레이드를 엽니다.  **선택**을 선택하면 정책이 사용자에게 배포됩니다.

사용자에게 정책을 적용했습니다.  정책의 대상 사용자가 사용하는 장치에 대해 준수 여부가 평가됩니다.

<!--- ##  Compliance policy settings--->

## <a name="system-security-settings"></a>시스템 보안 설정

### <a name="password"></a>암호

- **모바일 장치의 잠금을 해제하는 데 암호 필요:** 장치에 액세스하기 전에 사용자가 암호를 입력하도록 하려면 **예**로 설정합니다.
- **최소 암호 길이:** 암호에 포함해야 하는 최소 자릿수 또는 문자 수를 지정합니다.
- **암호 품질:** 지정한 암호 요구 사항이 장치에 구성되었는지 검색합니다. 이 설정을 사용하여 사용자가 Android 장치에 대한 특정 암호 요구 사항을 구성하도록 요구합니다. 다음 중에서 선택합니다.
  - **낮은 보안 생체 인식**
  - **필수**
  - **숫자 이상**
  - **알파벳 이상**
  - **영숫자 이상**
  - **영숫자와 기호**
- **암호를 요구하기 전까지 비활성 시간(분):** 사용자가 해당 시간 내에 자신의 암호를 다시 입력해야 하는 유휴 시간을 지정합니다.
- **암호 만료(일):** 사용자의 암호가 만료된 후 새로 만들어야 하기 전까지의 일수를 선택합니다.
- **암호 기록 기억:** 이 설정을 **이전 암호 다시 사용 방지**와 함께 사용하여 사용자가 이전에 사용했던 암호를 만들지 못하게 제한할 수 있습니다.
- **이전 암호 다시 사용 방지:** **암호 기록 기억**을 선택한 경우 다시 사용할 수 없는 이전에 사용했던 암호 수를 지정합니다.
- **장치가 유휴 상태에서 되돌아오는 경우 암호 필요:** 이 설정은 **암호를 요구하기 전까지 비활성 시간(분)** 설정과 함께 사용해야 합니다. **암호를 요구하기 전까지 비활성 시간(분)** 설정에 지정된 시간 동안 비활성화 상태인 장치에 최종 사용자가 액세스하려고 하면 암호를 입력하라는 메시지가 표시됩니다.


### <a name="encryption"></a>암호화

- **모바일 장치 암호화 필요:** Android for Work 장치에는 암호화가 시행되므로 이 설정을 구성하지 않아도 됩니다.


## <a name="device-health-and-security-settings"></a>장치 상태 및 보안 설정

- **장치는 탈옥 또는 루팅되지 않아야 함:** 이 설정을 사용하도록 설정하는 경우 탈옥된 장치가 비규격 상태로 평가됩니다.
- **장치가 알 수 없는 소스의 앱 설치를 방지해야 함:** Android for Work 장치는 알 수 없는 소스를 통한 설치를 항상 제한하므로 이 설정을 구성하지 않아도 됩니다. .
- **USB 디버깅은 사용하지 않도록 설정되어야 함**: USB 디버깅은 Android for Work 장치에서 이미 사용하지 않도록 설정되었으므로 이 설정을 구성하지 않아도 됩니다.
- **최소 Android 보안 패치 수준**: 최소 Android 패치 수준을 지정하려면 이 설정을 사용합니다. 적어도 이 패치 수준에 없는 장치가 비규격 장치가 됩니다. 날짜는 YYYY-MM-DD 형식으로 지정해야 합니다.
- **장치 위협 보호를 사용하도록 설정해야 함**: Lookout MTP 솔루션에서 위험 평가를 규정 준수에 대한 조건으로 수행하려면 이 설정을 사용합니다. 허용되는 최대 위협 수준을 다음 중에서 선택합니다.
  - **없음(보안됨)**: 가장 안전합니다. 장치에 어떤 위협도 있어서는 안 된다는 의미입니다. 수준에 관계없이 위협이 발견된 장치는 규정 비준수로 평가됩니다.
  - **낮음**: 낮은 수준의 위협이 있는 경우에만 장치가 규정 준수로 평가됩니다. 더 높은 수준의 위협이 발생하면 장치는 규정 비준수 상태가 됩니다.
  - **보통**: 장치에 있는 위협이 낮거나 중간 수준인 경우 장치가 규정 준수로 평가됩니다. 높은 수준의 위협이 있는 것으로 감지되면 장치가 규정 비준수로 결정됩니다.
  - **높음**: 가장 보안이 낮습니다. 기본적으로 이 옵션은 모든 위협 수준을 허용하기 때문에 이 솔루션을 보고 목적으로 사용할 경우에만 유용합니다.

자세한 내용은 [규정 준수 정책에서 장치 위협 방지 규칙 활성화](https://docs.microsoft.com/intune-classic/deploy-use/enable-device-threat-protection-rule-in-compliance-policy)를 참조하세요.

## <a name="device-property-settings"></a>장치 속성 설정

- **필요한 최소 OS:** 장치가 OS 최소 버전 요구 사항을 충족하지 못하면 비규격 장치로 보고됩니다. 업그레이드 방법에 대한 정보를 제공하는 링크가 표시됩니다. 최종 사용자는 회사 리소스에 액세스할 수 있으면 장치를 업그레이드하도록 선택할 수 있습니다.
- **허용된 최대 OS 버전:** 장치가 규칙에 지정된 버전 이후의 OS를 사용하는 경우 회사 리소스에 대한 액세스가 차단되고 사용자는 IT 관리자에게 문의하라는 메시지가 표시됩니다. OS 버전 허용 규칙이 변경될 때까지 회사 리소스에 액세스하는 데 이 장치를 사용할 수 없습니다.

<!--- ## Next steps

[How to monitor device compliance](device-compliance-monitor.md)--->

