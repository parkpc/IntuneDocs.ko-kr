<<<<<<< HEAD
---
title: "Android 장치용 규정 준수 정책 설정 | Microsoft Intune"
description: "이 항목에서는 Android 장치에 대한 장치 준수 정책 설정에 대해 설명합니다."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 07/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e721c5c7-9678-4f3b-81d4-564da5efd337
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 777c0ac6ea309db81b127fb254e0c5f88444e475
ms.openlocfilehash: cf1fde5b5ed55552e573c724b6165203033683da

||||||| merged common ancestors
---
title: "Android 장치용 규정 준수 정책 설정 | Microsoft Intune"
description: "이 항목에서는 Android 장치에 대한 장치 준수 정책 설정에 대해 설명합니다."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 07/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e721c5c7-9678-4f3b-81d4-564da5efd337
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: be1ebcdf2514e45d383dd49890e0e21acf6ede44
ms.openlocfilehash: f99158924b83254efedb8663b9d6175a6b6775b1

=======
---
title: "Android 장치용 규정 준수 정책 설정 | Microsoft Intune"
description: "이 항목에서는 Android 장치에 대한 장치 준수 정책 설정에 대해 설명합니다."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 07/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e721c5c7-9678-4f3b-81d4-564da5efd337
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e24de6814d9e01c64768f425e961a7822f4b27a1
ms.openlocfilehash: 5f02618da6fb3c538ad131fe8abaf35a6be6e177

>>>>>>> 359d4f486355df1be118d8fdb698694ae632df85

---


# Microsoft Intune에서 Android 장치용 규정 준수 정책 설정

이 항목에서 설명하는 정책 설정은 Android 4.0 이상 또는 Samsung KNOX 4.0 이상을 실행하는 장치에 적용됩니다.

다른 플랫폼에 대한 정보를 찾는 경우 다음 중 하나를 선택합니다.
> [!div class="op_single_selector"]
- [iOS 장치용 규정 준수 정책 설정](ios-compliance-policy-settings-in-microsoft-intune.md)
- [Windows 장치용 규정 준수 정책 설정](windows-compliance-policy-settings-in-microsoft-intune.md)

## 시스템 보안 설정
### 암호
- **모바일 장치의 잠금을 해제하는 데 암호 필요**: 장치에 액세스하기 전에 사용자가 암호를 입력하도록 하려면 **예**로 설정합니다.

-  **최소 암호 길이**: 사용자의 암호에 포함해야 하는 최소 자릿수 또는 문자 수를 지정합니다.

- **암호 품질**: 지정한 암호 요구 사항이 장치에 설정되었는지 검색합니다. 이 설정을 사용하여 사용자가 Android 장치에 대한 특정 암호 요구 사항을 충족하도록 요구합니다. 다음 중에서 선택합니다.

  -   **낮은 보안 생체 인식**
  -   **필수**
  -   **숫자 이상**
  -   **알파벳 이상**
  -   **최소 영숫자**
  -   **영숫자와 기호**

- **암호를 요구하기 전까지 비활성 시간(분)**: 사용자가 해당 시간 내에 자신의 암호를 다시 입력해야 하는 유휴 시간을 지정합니다.

- **암호 만료(일)**: 사용자의 암호가 만료된 후 새로 만들어야 하기 전까지의 일수를 선택합니다.

- **암호 기록 기억**: 이 설정을 **이전 암호 다시 사용 방지**와 함께 사용하여 사용자가 이전에 사용했던 암호를 만들지 못하게 제한할 수 있습니다.

- **이전 암호 다시 사용 방지** **암호 기록 기억**:을 선택한 경우 다시 사용할 수 없는 이전에 사용했던 암호 수를 지정합니다.

- **장치가 유휴 상태에서 되돌아오는 경우 암호 필요**: 이 설정은 **암호를 요구하기 전까지 비활성 시간(분)** 설정과 함께 사용해야 합니다. **암호를 요구하기 전까지 비활성 시간(분)** 설정에 지정된 시간 동안 비활성화 상태인 장치에 사용자가 액세스하려고 하면 암호를 입력하라는 메시지가 표시됩니다.

### 암호화
- **모바일 장치 암호화 필요**: **예**로 설정하여 리소스에 연결하기 위해 장치를 암호화하도록 해야 합니다. **모바일 장치의 잠금을 해제하는 데 암호 필요** 설정을 선택하면 장치가 암호화됩니다.

## 장치 상태 및 보안 설정

- **장치는 탈옥 또는 루팅되지 않아야 함**: 이 설정을 사용하도록 설정하는 경우 탈옥된 장치가 비규격 상태로 평가됩니다.
- **장치가 알 수 없는 소스의 앱 설치를 방지해야 함(Android 4.0 이상)**: **보안** > **알 수 없는 소스**를 사용하도록 설정한 장치를 차단하려면 이 설정을 사용하도록 설정하고 **예**로 설정합니다.  
>[!IMPORTANT]
>앱을 테스트용으로 로드하려면 **알 수 없는 소스**를 사용하도록 설정해야 합니다. 장치에서 Android 앱을 테스트용으로 로드하지 않는 경우에만 이 준수 정책을 적용합니다.

- **USB 디버깅을 사용하지 않도록 설정되어야 함(Android 4.2 이상)**: 이 설정은 장치에 USB 디버깅 옵션을 감지하는 기능이 사용하도록 설정되어 있는지 여부를 지정합니다.
- **장치의 보안 위협 검색을 사용하도록 장치가 설정되어 있어야 함(Android 4.2 4.4 이상)**: 이 설정은 장치에 **앱 확인** 기능이 사용하도록 설정되어 있는지 지정합니다.
<<<<<<< HEAD
- **최소 Android 보안 패치 수준(Android 6.0 이상)**: 최소 Android 패치 수준이 지정하려면 이 설정을 사용합니다.  적어도 이 패치 수준에 없는 장치가 비규격 장치가 됩니다. 날짜는 YYYY-MM-DD 형식으로 지정해야 합니다.
- **장치 위협 보호를 사용하도록 설정해야 함**: Lookout MTP 솔루션에서 위험 평가를 규정 준수에 대한 조건으로 수행하려면 이 설정을 사용합니다. 허용되는 최대 위협 수준을 다음 중에서 선택합니다.
||||||| merged common ancestors
- **최소 Android 보안 패치 수준(Android 6.0 이상)**: 최소 Android 패치 수준이 지정하려면 이 설정을 사용합니다.  적어도 이 패치 수준에 없는 장치가 비규격 장치가 됩니다. 날짜는 YYYY-MM-DD 형식으로 지정해야 합니다.
=======
- **최소 Android 보안 패치 수준(Android 6.0 이상)**: 최소 Android 패치 수준이 지정하려면 이 설정을 사용합니다. 적어도 이 패치 수준에 없는 장치가 비규격 장치가 됩니다. 날짜는 YYYY-MM-DD 형식으로 지정해야 합니다.
- **장치 위협 보호를 사용하도록 설정해야 함**: Lookout MTP 솔루션에서 위험 평가를 규정 준수에 대한 조건으로 수행하려면 이 설정을 사용합니다. 허용되는 최대 위협 수준을 다음 중에서 선택합니다.

  - **없음(보안됨)**: 가장 안전합니다. 장치에 어떤 위협도 있어서는 안 된다는 의미입니다. 수준에 관계없이 위협이 발견된 장치는 규정 비준수로 평가됩니다.
  - **낮음**: 낮은 수준의 위협만 있는 경우 장치가 규정 준수로 평가됩니다. 더 높은 수준의 위협이 발생하면 장치는 규정 비준수 상태가 됩니다.
  - **보통**: 장치에 있는 위협이 낮거나 중간 수준인 경우 장치가 규정 준수로 평가됩니다. 높은 수준의 위협이 있는 것으로 감지되면 장치가 규정 비준수로 결정됩니다.
  - **높음**: 가장 보안이 낮습니다. 기본적으로 모든 위협 수준이 허용됩니다. 이 수준은 이 솔루션을 보고 용도로만 사용하는 경우에 유용할 수 있습니다.
>>>>>>> 359d4f486355df1be118d8fdb698694ae632df85

<<<<<<< HEAD
  - **없음(보안됨)**: 가장 안전합니다. 장치에 어떤 위협도 있어서는 안 된다는 의미입니다. 수준에 관계없이 위협이 발견된 장치는 규정 비준수로 평가됩니다.
  - **낮음**: 낮은 수준의 위협이 있는 경우에만 장치가 규정 준수로 평가됩니다. 더 높은 수준의 위협이 발생하면 장치는 규정 비준수 상태가 됩니다.
  - **보통**: 장치에 있는 위협이 낮거나 중간 수준인 경우 장치가 규정 준수로 평가됩니다. 높은 수준의 위협이 있는 것으로 감지되면 장치가 규정 비준수로 결정됩니다.
  - **높음**: 가장 보안이 낮습니다. 기본적으로 이 옵션은 모든 위협 수준을 허용하기 때문에 이 솔루션을 보고 목적으로 사용할 경우에만 유용합니다.

  자세한 내용은 [규정 준수 정책에서 장치 위협 방지 규칙 활성화](enable-device-threat-protection-rule-in-compliance-policy.md)를 참조하세요.
||||||| merged common ancestors
=======
  자세한 내용은 [규정 준수 정책에서 장치 위협 방지 규칙 활성화](enable-device-threat-protection-rule-in-compliance-policy.md)를 참조하세요.
>>>>>>> 359d4f486355df1be118d8fdb698694ae632df85

## 장치 속성 설정
- **필요한 최소 OS**: 장치가 OS 최소 버전 요구 사항을 충족하지 못하면 비규격 장치로 보고됩니다.
  업그레이드 방법에 대한 정보를 제공하는 링크가 표시됩니다. 사용자는 회사 리소스에 액세스할 수 있으면 장치를 업그레이드하도록 선택할 수 있습니다.

<<<<<<< HEAD
- **허용된 최대 OS 버전:** 장치가 규칙에 지정된 버전 이후의 OS를 사용하는 경우 회사 리소스에 대한 액세스가 차단되고 사용자는 IT 관리자에게 문의하라는 메시지가 표시됩니다. OS 버전 허용 규칙이 변경될 때까지 회사 리소스에 액세스하는 데 이 장치를 사용할 수 없습니다.
||||||| merged common ancestors
- **허용된 최대 OS 버전:** 장치가 규칙에 지정된 버전 이후의 OS를 사용하는 경우 회사 리소스에 대한 액세스가 차단되고 사용자는 IT 관리자에게 문의하라는 메시지가 표시됩니다. OS 버전 허용 규칙이 변경될 때까지 회사 리소스에 액세스하는 데 이 장치를 사용할 수 없습니다.

=======
- **허용된 최대 OS 버전**: 장치가 규칙에 지정된 버전 이후의 OS를 사용하는 경우 회사 리소스에 대한 액세스가 차단되고 사용자는 IT 관리자에게 문의하라는 메시지가 표시됩니다. OS 버전 허용 규칙이 변경될 때까지 회사 리소스에 액세스하는 데 이 장치를 사용할 수 없습니다.

>>>>>>> 359d4f486355df1be118d8fdb698694ae632df85


<<<<<<< HEAD
||||||| merged common ancestors
<!--HONumber=Jul16_HO5-->
=======
<!--HONumber=Oct16_HO3-->
>>>>>>> 359d4f486355df1be118d8fdb698694ae632df85

<!--HONumber=Sep16_HO3-->


