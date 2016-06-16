---
# required metadata

title: Android 장치용 규정 준수 정책 설정 | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: e721c5c7-9678-4f3b-81d4-564da5efd337

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Microsoft Intune에서 Android 장치용 규정 준수 정책 설정

이 항목에서 설명하는 정책 설정은 Android 4.0 이상 또는 Samsung KNOX 4.0 이상을 실행하는 장치에 적용됩니다.

다른 플랫폼에 대한 정보를 찾는 경우 다음 중 하나를 선택합니다.
> [!div class="op_single_selector"]
- [iOS 장치용 규정 준수 정책 설정](ios-compliance-policy-settings-in-microsoft-intune.md)
- [Windows 장치용 규정 준수 정책 설정](windows-compliance-policy-settings-in-microsoft-intune.md)

## 시스템 보안 설정
### 암호
- **모바일 장치의 잠금을 해제하는 데 암호 필요:** 장치에 액세스하기 전에 사용자가 암호를 입력하도록 하려면 **예**로 
  설정합니다.

-  **최소 암호 길이:** 사용자의 암호에 포함해야 하는 최소 자릿수 또는 문자 수를 지정합니다.

- **암호 품질:** 이 설정을 사용하여 Android 장치에 대한 암호 요구 사항을 구성합니다. 다음 중에서 선택합니다.
  -   **낮은 보안 생체 인식**
  - **필수**
  -   **숫자 이상**
  -   **알파벳 이상**
  -   **최소 영숫자**
  -   **영숫자와 기호**

- **암호를 요구하기 전까지 비활성 시간(분):** 사용자가 해당 시간 내에 자신의 암호를 다시 입력해야 하는 유휴 시간을 지정합니다.

- **암호 만료(일):** 사용자의 암호가 만료된 후 
  새로 만들어야 하기 전까지의 일수를 선택합니다.

- **암호 기록 기억:** 이 설정을 **이전 암호 다시 사용 방지**와 함께 사용하여 사용자가 
  이전에 사용했던 암호를 만들지 못하게 제한할 수 있습니다.

- **이전 암호 다시 사용 방지:** **암호 기록 기억**을 선택한 경우 
  다시 사용할 수 없는 이전에 사용했던 암호 수를 지정합니다.

- **장치가 유휴 상태에서 되돌아오는 경우 암호 필요:**
  이 설정은 **암호를 요구하기 전까지 비활성 시간(분)** 설정과 함께 사용해야 합니다. The end-users are prompted to enter a password to access a device that has been inactive for the time specified in the
  암호를 요구하기 전까지 비활성 시간(분) 설정에 지정된 시간 동안 비활성화 상태인 장치에 최종 사용자가 액세스하려고 하면 암호를 입력하라는 메시지가 표시됩니다.

### Encryption
- **모바일 장치 암호화 필요:** **예**로 설정하여 리소스에 연결하기 위해 장치를 암호화하도록 
  해야 합니다. 장치는
   모바일 장치의 잠금을 해제하는 데
   암호 필요 설정을 구성하면 암호화됩니다..

## 장치 상태 설정

- **장치를 무단 해제하거나 루팅하면 안 됩니다.:** 이 설정을 사용하는 경우
  무단 해제된 장치는 호환이 불가능하다고 평가됩니다.

## 장치 속성 설정
- **필요한 최소 OS:** 장치가 OS 최소 
  버전 요구 사항을 충족하지 못하면 비규격으로 보고됩니다.
  업그레이드 방법에 대한 정보를 제공하는 링크가 표시됩니다. 최종 사용자는 회사 리소스에 액세스할 수 있으면 장치를 업그레이드하도록 선택할 수 있습니다.

- **허용된 최대 OS 버전:** 장치가 
  규칙에 지정된 버전 이후의 OS를 사용하는 경우 회사 리소스에 대한 액세스가 차단되고 사용자는 IT 관리자에게 문의하라는 메시지가 표시됩니다. OS 버전 허용 규칙이 변경될 때까지 회사 리소스에 액세스하는 데 이 장치를 사용할 수 없습니다.


<!--HONumber=May16_HO1-->

