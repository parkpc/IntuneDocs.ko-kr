---
title: "Windows에 대한 준수 정책을 만드는 방법"
titleSuffix: Azure portal
description: "Windows 장치에 대한 준수 정책을 만드는 방법을 알아봅니다.\""
keywords: 
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 2/13/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: fe5a66ca91181d0cebdaea846f0ee08f9252d76b
ms.sourcegitcommit: 754fcc31155b28d6910bba45419c6be745f8793e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="how-to-create-a-device-compliance-policy-for-windows-devices-in-intune"></a>Intune에서 Windows 장치에 대한 장치 준수 정책을 만드는 방법


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

준수 정책은 각 플랫폼에 대해 생성됩니다. Azure Portal에서 준수 정책을 만들 수 있습니다. 준수 정책에 대한 정의는 [장치 준수란?](device-compliance.md) 항목을 참조하세요. 준수 정책을 만들기 전에 해결해야 하는 전제 조건을 자세히 알아보려면 [장치 준수 시작](device-compliance-get-started.md) 항목을 참조하세요.

다음 표에서는 준수 정책을 조건부 액세스 정책과 함께 사용할 경우 비준수 설정을 관리하는 방법을 설명합니다.

---------------------------

| **정책 설정** | **Windows 8.1 이상** | **Windows Phone 8.1 이상** |
|----| ----| --- |
| **PIN 또는 암호 구성** | 재구성됨 | 재구성됨 |   
| **장치 암호화** | 해당 없음 | 재구성됨 |   
| **무단 해제 또는 루팅된 장치** | 해당 없음 | 해당 없음 |  
| **전자 메일 프로필** | 해당 없음 | 해당 없음 |   
| **최소 OS 버전** | 격리됨 | 격리됨 |   
| **최대 OS 버전** | 격리됨 | 격리됨 |   
| **Windows 상태 증명** | 격리됨: Windows 10 및 Windows 10 Mobile|해당 없음: Windows 8.1 |

-------------------------------

**재구성됨** = 장치 운영 체제에서 준수를 적용하도록 요구합니다. (예를 들어 사용자에게 PIN을 설정하도록 강제합니다.)

**격리됨** = 장치 운영 체제에서 준수를 적용하도록 요구하지 않습니다. (예를 들어, Android 장치에서 사용자에게 장치를 암호화하도록 강제하지 않습니다.) 장치가 호환되지 않으면 다음 작업이 수행됩니다.

- 조건부 액세스 정책이 사용자에게 적용될 경우 장치가 차단됩니다.
- 회사 포털은 모든 준수 문제에 대해 사용자에게 알립니다.

## <a name="create-a-compliance-policy-in-the-azure-portal"></a>Azure Portal에서 준수 정책 만들기

1. **Intune** 블레이드에서 **장치 준수 설정**을 선택합니다. **관리** 아래에서 **모든 장치 준수 정책**을 선택한 다음 **만들기**를 선택합니다.
2. 이름 및 설명을 입력하고 이 정책을 적용할 플랫폼을 선택합니다.
3. **준수 요구 사항**을 선택하여 준수 요구 사항 블레이드를 엽니다.  **보안**, **장치 상태** 및 **장치 속성** 설정을 지정할 수 있습니다. 작업이 끝나면 **확인**을 선택합니다.

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

사용자에게 정책을 적용했습니다. 정책의 대상 사용자가 사용하는 장치에 대해 준수 여부가 평가됩니다.

<!---## Compliance policy settings--->

## <a name="system-security-settings"></a>시스템 보안 설정

### <a name="password"></a>암호

- **모바일 장치의 잠금을 해제하는 데 암호 필요:** 장치에 액세스하기 전에 사용자가 암호를 입력하도록 하려면 **예**로 설정합니다.
- **단순 암호 허용:** 사용자가 ‘**1234**’ 또는 ‘**1111**’과 같은 #39; 간단한 암호를 만들도록 하려면 **예**로 설정합니다.
- **최소 암호 길이:** 사용자의 암호에 포함해야 하는 최소 자릿수 또는 문자 수를 지정합니다.
- **필수 암호 유형:** 사용자가 **영숫자** 또는 **숫자** 암호를 만들어야 할지를 지정합니다.

Windows를 실행하고 Microsoft 계정으로 보안이 유지되는 장치의 경우 최소 암호 길이가 8자보다 길거나 최소 문자 집합 수가 2보다 크면 준수 정책 평가가 올바르게 이루어지지 않습니다.

- **최소 문자 집합 수:** **필수 암호 유형**을 **영숫자**로 설정한 경우 이 설정은 암호에 포함해야 하는 최소 문자 집합 수를 지정합니다. 4가지 문자 집합은 다음과 같습니다.
  - 소문자
  - 대문자
  - 기호
  - 숫자

이 설정에 대해 더 큰 값을 설정하면 사용자는 더욱 복잡한 암호를 만들어야 합니다. Windows를 실행하고 Microsoft 계정으로 보안이 유지되는 장치의 경우 최소 암호 길이가 8자보다 길거나 최소 문자 집합 수가 2보다 크면 준수 정책 평가가 올바르게 이루어지지 않습니다.

- **암호를 요구하기 전까지 비활성 시간(분):** 사용자가 해당 시간 내에 자신의 암호를 다시 입력해야 하는 유휴 시간을 지정합니다.
- **암호 만료(일):** 사용자의 암호가 만료된 후 새로 만들어야 하기 전까지의 일수를 선택합니다.
- **암호 기록 기억:** 이 설정을 **이전 암호 다시 사용 방지**와 함께 사용하여 사용자가 이전에 사용했던 암호를 만들지 못하게 제한할 수 있습니다.
- **이전 암호 다시 사용 방지:** **암호 기록 기억**을 선택한 경우 다시 사용할 수 없는 이전에 사용했던 암호 수를 지정합니다.
- **장치가 유휴 상태에서 되돌아오는 경우 암호 필요:** 이 설정은 **암호를 요구하기 전까지 비활성 시간(분)** 설정과 함께 사용해야 합니다. **암호를 요구하기 전까지 비활성 시간(분)** 설정에 지정된 시간 동안 비활성화 상태인 장치에 최종 사용자가 액세스하려고 하면 암호를 입력하라는 메시지가 표시됩니다.

**이 설정은 Windows 10 Mobile 장치에만 적용됩니다.**

### <a name="encryption"></a>암호화

- **모바일 장치 암호화 필요:** **예**로 설정하여 리소스에 연결하기 위해 장치를 암호화하도록 해야 합니다.



## <a name="device-health-settings"></a>장치 상태 설정

- **장치가 정상으로 보고되어야 함:** 기존 또는 새 준수 정책에서 **Windows 10 Mobile** 장치가 정상으로 보고되어야 하도록 요구하는 규칙을 설정할 수 있습니다. 이 설정을 사용하면 다음 데이터 요소에 대해 Windows 10 장치가 HAS(상태 증명 서비스)를 통해 평가됩니다.
  - **BitLocker is enabled(BitLocker 사용):** BitLocker를 켜면 시스템이 꺼져 있거나 절전 모드로 전환될 때 장치가 드라이브에 저장된 데이터를 무단 액세스로부터 보호할 수 있습니다. Windows BitLocker 드라이브 암호화는 Windows 운영 체제 볼륨에 저장된 모든 데이터를 암호화합니다. BitLocker는 TPM을 사용하여 Windows 운영 체제 및 사용자 데이터를 보호하고, 컴퓨터를 관리하는 사람 없이 두거나 컴퓨터를 잃어버리거나 도난당한 경우에도 컴퓨터가 변조되지 않도록 합니다. 컴퓨터에 호환되는 TPM이 장착되어 있으면 BitLocker는 TPM을 사용하여 데이터를 보호하는 암호화 키를 잠급니다. 결과적으로, TPM이 컴퓨터의 상태를 확인할 때까지 키를 액세스할 수 없습니다.
  - **Code integrity is enabled(코드 무결성 사용):** 코드 무결성은 메모리에 로드될 때마다 드라이버 또는 시스템 파일의 무결성을 확인하는 기능입니다. 코드 무결성은 서명되지 않은 드라이버 또는 시스템 파일이 커널에 로드되는지 여부나 시스템 파일이 관리자 권한을 가진 사용자 계정에 의해 실행되는 악성 소프트웨어에 의해 수정되었는지 여부를 검색합니다.
  - **Secure Boot is enabled(보안 부팅 사용):** 보안 부팅을 사용하면 시스템이 신뢰할 수 있는 공장 기본 상태로 강제로 부팅됩니다. 또한 보안 부팅을 사용하면 컴퓨터를 부팅하는 데 사용되는 핵심 구성 요소에 장치를 제조한 조직에서 신뢰할 수 있는 올바른 암호화 서명이 있어야 합니다. UEFI 펌웨어에서 컴퓨터를 시작하도록 허용하기 전에 이를 확인합니다. 파일이 변조되어 해당 서명이 손상된 경우에는 시스템이 부팅되지 않습니다.

HAS 서비스의 작동 방식에 대한 자세한 내용은 [상태 증명 CSP](https://msdn.microsoft.com/library/dn934876.aspx)를 참조하세요.

## <a name="device-property-settings"></a>장치 속성 설정

- **필요한 최소 OS:** 장치가 OS 최소 버전 요구 사항을 충족하지 못하면 비규격 장치로 보고됩니다. 업그레이드 방법에 대한 정보를 제공하는 링크가 표시됩니다. 최종 사용자는 회사 리소스에 액세스할 수 있으면 장치를 업그레이드하도록 선택할 수 있습니다.
- **허용된 최대 OS 버전:** 장치가 규칙에 지정된 버전 이후의 OS를 사용하는 경우 회사 리소스에 대한 액세스가 차단되고 사용자는 IT 관리자에게 문의하라는 메시지가 표시됩니다. OS 버전 허용 규칙이 변경될 때까지 회사 리소스에 액세스하는 데 이 장치를 사용할 수 없습니다.

<!---## Compliance policy settings for Windows PCs--->

## <a name="system-security-settings"></a>시스템 보안 설정

### <a name="password"></a>암호

- **최소 암호 길이:** - Windows 8.1에서 지원됩니다.

사용자의 암호에 포함해야 하는 최소 자릿수 또는 문자 수를 지정합니다.

Microsoft 계정으로 액세스되는 장치의 경우 **최소 암호 길이**가 8자보다 길거나 **최소 문자 집합 수**가 2보다 크면 준수 정책 평가가 올바르게 이루어지지 않습니다.

- **필수 암호 유형** - Windows RT, Windows RT 8.1, 및 Windows 8.1에서 지원됩니다.

사용자가 **영숫자** 또는 **숫자** 암호를 만들어야 할지를 지정합니다.

- **최소 문자 집합 수** - Windows RT, Windows RT 8.1, 및 Windows 8.1에서 지원됩니다. **필수 암호 유형**을 **영숫자**로 설정한 경우 이 설정은 암호에 포함해야 하는 최소 문자 집합 수를 지정합니다. 4가지 문자 집합은 다음과 같습니다.
  - 소문자
  - 대문자
  - 기호
  - 숫자: 이 설정에 대해 더 큰 값을 설정하면 사용자는 더욱 복잡한 암호를 만들어야 합니다.

Microsoft 계정으로 액세스되는 장치의 경우 **최소 암호 길이**가 8자보다 길거나 **최소 문자 집합 수**가 2보다 크면 준수 정책 평가가 올바르게 이루어지지 않습니다.

- **암호를 요구하기 전까지 비활성 시간(분):** - Windows RT, Windows RT 8.1, 및 Windows 8.1에서 지원됩니다.

사용자가 해당 시간 내에 자신의 암호를 다시 입력해야 하는 유휴 시간을 지정합니다.

- **암호 만료(일)** - Windows RT, Windows RT 8.1, 및 Windows 8.1에서 지원됩니다.

사용자의 암호가 만료된 후 새로 만들어야 하기 전까지의 일수를 선택합니다.

- **암호 기록 기억:** - Windows RT, Windows RT, 및 Windows 8.1에서 지원됩니다.

이 설정을 **이전 암호 다시 사용 방지**와 함께 사용하여 사용자가 이전에 사용했던 암호를 만들지 못하게 제한할 수 있습니다.

- **이전 암호 다시 사용 안 함:** - Windows RT, Windows RT 8.1, 및 Windows 8.1에서 지원됩니다.

**암호 기록 기억**을 선택한 경우 다시 사용할 수 없는 이전에 사용했던 암호 수를 지정합니다.


## <a name="device-health-settings"></a>장치 상태 설정

- **장치가 정상으로 보고되어야 함:** - Windows 10 장치에서 지원됩니다. 기존 또는 새 규정 준수 정책에서 Windows 10 장치를 보고하도록 요구하기 위해 규칙을 정상으로 설정할 수 있습니다. 이 설정을 사용하면 다음 데이터 요소에 대해 Windows 10 장치가 HAS(상태 증명 서비스)를 통해 평가됩니다.
  - **BitLocker is enabled(BitLocker 사용):** BitLocker를 켜면 시스템이 꺼져 있거나 절전 모드로 전환될 때 장치가 드라이브에 저장된 데이터를 무단 액세스로부터 보호할 수 있습니다. Windows BitLocker 드라이브 암호화는 Windows 운영 체제 볼륨에 저장된 모든 데이터를 암호화합니다. BitLocker는 TPM을 사용하여 Windows 운영 체제 및 사용자 데이터를 보호하고, 컴퓨터를 관리하는 사람 없이 두거나 컴퓨터를 잃어버리거나 도난당한 경우에도 컴퓨터가 변조되지 않도록 합니다. 컴퓨터에 호환되는 TPM이 장착되어 있으면 BitLocker는 TPM을 사용하여 데이터를 보호하는 암호화 키를 잠급니다. 결과적으로, TPM이 컴퓨터의 상태를 확인할 때까지 키를 액세스할 수 없습니다.
  - **Code integrity is enabled(코드 무결성 사용):** 코드 무결성은 메모리에 로드될 때마다 드라이버 또는 시스템 파일의 무결성을 확인하는 기능입니다. 코드 무결성은 서명되지 않은 드라이버 또는 시스템 파일이 커널에 로드되는지 여부나 시스템 파일이 관리자 권한을 가진 사용자 계정에 의해 실행되는 악성 소프트웨어에 의해 수정되었는지 여부를 검색합니다.
  - **Secure Boot is enabled(보안 부팅 사용):** 보안 부팅을 사용하면 시스템이 신뢰할 수 있는 공장 기본 상태로 강제로 부팅됩니다. 또한 보안 부팅을 사용하면 컴퓨터를 부팅하는 데 사용되는 핵심 구성 요소에 장치를 제조한 조직에서 신뢰할 수 있는 올바른 암호화 서명이 있어야 합니다. UEFI 펌웨어에서 컴퓨터를 시작하도록 허용하기 전에 이를 확인합니다. 파일이 변조되어 해당 서명이 손상된 경우에는 시스템이 부팅되지 않습니다.
  - **Early-launch antimalware is enabled(맬웨어 방지 조기 실행 사용):** ELAM(맬웨어 방지 조기 실행)은 타사 드라이버가 초기화되기 전에 시작될 경우 네트워크의 컴퓨터를 보호합니다.

HAS 서비스의 작동 방식에 대한 자세한 내용은 [상태 증명 CSP](https://msdn.microsoft.com/library/dn934876.aspx)를 참조하세요.

## <a name="device-property-settings"></a>장치 속성 설정

- **Minimum OS required(필요한 최소 OS):** - Windows 8.1 및 Windows 10에서 지원됩니다.

여기에 major.minor.build 번호를 지정합니다. 버전 번호는 ```winver``` 명령에 의해 반환된 버전과 일치해야 합니다.

지정된 OS 버전보다 이전 버전이 장치에 있으면 호환되지 않는 것으로 보고됩니다. 업그레이드 방법에 대한 정보를 제공하는 링크가 표시됩니다. 최종 사용자는 회사 리소스에 액세스할 수 있으면 장치를 업그레이드하도록 선택할 수 있습니다.

- **허용된 최대 OS 버전:** - Windows 8.1 및 Windows 10에서 지원됩니다.

장치가 규칙에 지정된 버전 이후의 OS를 사용하는 경우 회사 리소스에 대한 액세스가 차단되고 사용자는 IT 관리자에게 문의하라는 메시지가 표시됩니다. OS 버전 허용 규칙이 변경될 때까지 회사 리소스에 액세스하는 데 이 장치를 사용할 수 없습니다.

**필요한 최소 OS** 및 **허용된 최대 OS 버전** 설정에 사용할 OS 버전을 찾으려면, 명령 프롬프트에서 **winver** 명령을 실행합니다. winver 명령은 보고된 운영 체제 버전을 반환합니다.

- Windows 8.1 PC는 **3** 버전을 반환합니다. Windows에 대한 OS 버전 규칙이 Windows 8.1로 설정된 경우 장치에 Windows 8.1이 있어도 장치가 호환되지 않는 것으로 보고됩니다.
- Windows 10을 실행하는 PC의 버전은 &quot;10.0&quot;과 winver 명령에 의해 반환된 OS 빌드 번호로 설정되어야 합니다.

## <a name="windows-holographic-for-business-support"></a>Windows Holographic for Business 지원

Windows Holographic for Business는 다음과 같은 설정을 지원합니다.

- 시스템 보안/암호화

  **장치에 있는 데이터 저장소의 암호화**

Microsoft HoloLens에서 장치 암호화를 확인하려면 [장치 암호화 확인](https://docs.microsoft.com/hololens/hololens-encryption#verify-device-encryption)을 참조하세요.

## <a name="next-steps"></a>다음 단계

장치 규정 준수를 모니터링하는 방법에 대해 알아보려면 다음 항목을 참조하세요.

- [장치 준수를 모니터링하는 방법](device-compliance-monitor.md)
