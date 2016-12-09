---
title: "iOS 장치용 규정 준수 정책 설정 | Microsoft Intune"
description: "이 항목에서는 iOS 장치에 대한 준수 정책에 설정할 수 있는 규칙 및 설정에 대해 설명합니다."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a59d24f-ed58-49b1-b874-b2d4aea3ec76
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d6ff74f0b46baf384dbdedf13ad75538dd33a089
ms.openlocfilehash: 0ee697472a7cb553d78aef9977381197149c3177


---


# <a name="compliance-policy-settings-for-ios-devices-in-microsoft-intune"></a>Microsoft Intune에서 iOS 장치용 규정 준수 정책 설정

이 항목에서 설명하는 정책 설정은 iOS 8.0 이상을 실행하는 장치에 적용됩니다.

다른 플랫폼에 대한 정보를 찾는 경우 다음 중 하나를 선택합니다.
> [!div class="op_single_selector"]
- [Android 장치용 규정 준수 정책 설정](android-compliance-policy-settings-in-microsoft-intune.md)
- [Android for Work용 규정 준수 정책 설정](afw-compliance-policy-settings-in-microsoft-intune.md)
- [Windows 장치용 준수 정책 설정](windows-compliance-policy-settings-in-microsoft-intune.md)

## <a name="system-security-settings"></a>시스템 보안 설정
### <a name="password"></a>암호
- **모바일 장치의 잠금을 해제하는 데 암호 필요:** 장치에 액세스하기 전에 사용자가 암호를 입력하도록 하려면 **예**로 설정합니다. 암호를 사용하는 iOS 장치는 암호화됩니다.

- **단순 암호 허용**: 사용자가 **1234** 또는 **1111**과 같은 간단한 암호를 만들도록 하려면 **예**로 설정합니다.

-  **최소 암호 길이**: 사용자의 암호에 포함해야 하는 최소 자릿수 또는 문자 수를 지정합니다.

- **필수 암호 유형**: 사용자가 **영숫자** 암호 또는 **숫자** 암호를 만들어야 할지를 지정합니다.

- **최소 문자 집합 수**: **필수 암호 유형**을 **영숫자**로 설정한 경우 이 설정을 사용하여 암호에 포함해야 하는 최소 문자 집합 수를 지정합니다. 4가지 문자 집합은 다음과 같습니다.
  -   소문자
  -   대문자
  -   기호
  -   숫자

  더 큰 값을 설정하면 사용자는 더욱 복잡한 암호를 만들어야 합니다.

  iOS 장치의 경우 이 설정은 암호에 포함해야 하는 특수 문자(예: **!**, **#**, **&amp;**) 수를 나타냅니다.

- **암호를 요구하기 전까지 비활성 시간(분)**: 사용자가 해당 시간 내에 자신의 암호를 다시 입력해야 하는 유휴 시간을 지정합니다.

- **암호 만료(일)**: 사용자의 암호가 만료된 후 새로 만들어야 하기 전까지의 일수를 선택합니다.

- **암호 기록 기억:** 이 설정을 **이전 암호 다시 사용 방지**와 함께 사용하여 사용자가 이전에 사용했던 암호를 만들지 못하게 제한할 수 있습니다.

- **이전 암호 다시 사용 방지** **암호 기록 기억**:을 선택한 경우 다시 사용할 수 없는 이전에 사용했던 암호 수를 지정합니다.

- **장치가 유휴 상태에서 되돌아오는 경우 암호 필요**: 이 설정은 **암호를 요구하기 전까지 비활성 시간(분)** 설정과 함께 사용해야 합니다. **암호를 요구하기 전까지 비활성 시간(분)** 설정에 지정된 시간 동안 비활성화 상태인 장치에 사용자가 액세스하려고 하면 암호를 입력하라는 메시지가 표시됩니다.

### <a name="email-profile"></a>전자 메일 프로필
- **메일 계정은 Intune을 통해 관리해야 함:** 이 옵션이 **예**로 설정된 경우 장치는 장치에 배포된 메일 프로필을 사용해야 합니다. 장치는 다음과 같은 상황에서 비규격으로 간주됩니다.
  - 메일 프로필은 준수 정책의 대상으로 지정된 사용자 그룹 이외의 사용자 그룹에 배포됩니다.
  - 사용자가 장치에 배포된 Intune 메일 프로필과 일치하는 메일 계정을 이미 장치에서 설정했습니다. Intune은 사용자가 프로비전한 프로필을 덮어쓸 수 없으므로 이러한 프로필을 관리할 수 없습니다. 장치의 준수 상태를 유지하려면 사용자는 기존 메일 설정을 제거해야 합니다. 그런 다음 Intune이 관리되는 메일 프로필을 설치할 수 있습니다.

- **Intune에서 관리해야 하는 메일 프로필 선택**: **Intune에서 메일 계정을 관리해야 함** 설정을 선택할 경우 **선택**을 선택하여 Intune 메일 프로필을 지정합니다. 장치에 전자 메일 프로필이 있어야 합니다.

     메일 프로필에 대한 자세한 내용은 [Microsoft Intune에서 메일 프로필을 사용하여 회사 메일에 대한 액세스 구성](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md)을 참조하세요.

## <a name="device-health-settings"></a>장치 상태 설정

- **장치는 탈옥 또는 루팅되지 않아야 함**: 이 설정을 사용하도록 설정하는 경우 탈옥된 장치는 비준수 상태가 됩니다.

##  <a name="device-properties"></a>장치 속성
- **필요한 최소 OS**: 장치가 OS 최소 버전 요구 사항을 충족하지 못하면 비준수 장치로 보고됩니다.
업그레이드 방법에 대한 정보를 제공하는 링크가 표시됩니다. 사용자는 장치를 업그레이드하도록 선택할 수 있습니다. 그런 다음 회사 리소스에 액세스할 수 있습니다.

- **허용된 최대 OS 버전**: 장치가 규칙에 지정된 버전 이후의 OS를 사용하는 경우 회사 리소스에 대한 액세스가 차단되고 사용자는 IT 관리자에게 문의하라는 메시지가 표시됩니다. OS 버전 허용 규칙이 변경될 때까지 회사 리소스에 액세스하는 데 이 장치를 사용할 수 없습니다.



<!--HONumber=Dec16_HO2-->


