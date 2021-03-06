<<<<<<< HEAD
---
title: "Windows 장치용 규정 준수 정책 설정 | Microsoft Intune"
description: "이 항목에서는 Windows 장치의 준수 정책에 대해 구성할 수 있는 규칙 및 설정을 살펴보았습니다."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f996842c-e9a4-4819-acb4-ee66e8fb35b8
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9a442d9472159757333a9ebe081d86eac9907cdc
ms.openlocfilehash: 40c63094f37fbffa62ea0d3e5b52ef1f3988e7e1

||||||| merged common ancestors
---
title: "Windows 장치용 규정 준수 정책 설정 | Microsoft Intune"
description: "이 항목에서는 Windows 장치의 준수 정책에 대해 구성할 수 있는 규칙 및 설정을 살펴보았습니다."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f996842c-e9a4-4819-acb4-ee66e8fb35b8
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9a442d9472159757333a9ebe081d86eac9907cdc
ms.openlocfilehash: 40c63094f37fbffa62ea0d3e5b52ef1f3988e7e1

=======
---
title: "Windows 장치용 규정 준수 정책 설정 | Microsoft Intune"
description: "이 항목에서는 Windows 장치의 준수 정책에 대해 구성할 수 있는 규칙 및 설정을 살펴보았습니다."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f996842c-e9a4-4819-acb4-ee66e8fb35b8
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 8cde3ffb3be8656d5f256e16eb71ed4aaa7ceb5b
ms.openlocfilehash: c330f730b4eced38f9d0ee972063198ccafc0bcf

>>>>>>> cbfbf499eccf5c2397decf9af598d6cda806b377

---
<<<<<<< HEAD

# Microsoft Intune에서 Windows 장치용 규정 준수 정책 설정
||||||| merged common ancestors

# Microsoft Intune에서 Windows 장치용 규정 준수 정책 설정
=======

# <a name="compliance-policy-settings-for-windows-devices-in-microsoft-intune"></a>Microsoft Intune에서 Windows 장치용 규정 준수 정책 설정
>>>>>>> cbfbf499eccf5c2397decf9af598d6cda806b377

이 항목에서 설명하는 정책 설정은Windows 운영 체제에서 실행하는 장치에 적용됩니다. 지원되는 Windows 버전은 아래 섹션에 나와 있습니다.

다른 플랫폼에 대한 정보를 찾는 경우 다음 중 하나를 선택합니다.
> [!div class="op_single_selector"]
- [iOS 장치용 규정 준수 정책 설정](ios-compliance-policy-settings-in-microsoft-intune.md)
- [Android 장치용 규정 준수 정책 설정](android-compliance-policy-settings-in-microsoft-intune.md)
- [Android for Work용 규정 준수 정책 설정](afw-compliance-policy-settings-in-microsoft-intune)

## <a name="compliance-policy-settings-for-windows-phone-devices"></a>Windows Phone 장치용 규정 준수 정책 설정
이 항목에 나열된 설정은 Windows Phone 8.1 이상에서 지원됩니다.

## <a name="system-security-settings"></a>시스템 보안 설정
### <a name="password"></a>암호
- **모바일 장치의 잠금을 해제하는 데 암호 필요:** 장치에 액세스하기 전에 사용자가 암호를 입력하도록 하려면 **예**로 설정합니다.

- **단순 암호 허용:** 사용자가 ‘**1234**’ 또는 ‘**1111**’과 같은 간단한 암호를 만들도록 하려면 **예**로 설정합니다.

-  **최소 암호 길이:** 사용자의 암호에 포함해야 하는 최소 자릿수 또는 문자 수를 지정합니다.
- **필수 암호 유형:** 사용자가 **영숫자** 또는 **숫자** 암호를 만들어야 할지를 지정합니다.

  Windows를 실행하고 Microsoft 계정으로 보안이 유지되는 장치의 경우 최소 암호 길이가 8자보다 길거나 최소 문자 집합 수가 2보다 크면 준수 정책 평가가 올바르게 이루어지지 않습니다.

- **최소 문자 집합 수:** **필수 암호 유형**을 **영숫자**로 설정한 경우 이 설정은 암호에 포함해야 하는 최소 문자 집합 수를 지정합니다. 4가지 문자 집합은 다음과 같습니다.
  -   소문자
  -   대문자
  -   기호
  -   숫자

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
- **장치가 정상으로 보고되어야 함:** 기존 또는 새 준수 정책에서 **Windows 10 Mobile** 장치가 정상으로 보고되어야 하도록 요구하는 규칙을 설정할 수 있습니다.  이 설정을 사용하면 다음 데이터 요소에 대해 Windows 10 장치가 HAS(상태 증명 서비스)를 통해 평가됩니다.
  -  **BitLocker is enabled(BitLocker 사용):** BitLocker를 켜면 시스템이 꺼져 있거나 절전 모드로 전환될 때 장치가 드라이브에 저장된 데이터를 무단 액세스로부터 보호할 수 있습니다. Windows BitLocker 드라이브 암호화는 Windows 운영 체제 볼륨에 저장된 모든 데이터를 암호화합니다. BitLocker는 TPM을 사용하여 Windows 운영 체제 및 사용자 데이터를 보호하고, 사용자가 자리를 비우거나 컴퓨터가 분실 또는 도난당한 경우에도 변조되지 않도록 합니다. 컴퓨터에 호환되는 TPM이 장착되어 있으면 BitLocker는 TPM을 사용하여 데이터를 보호하는 암호화 키를 잠급니다. 결과적으로, TPM이 컴퓨터의 상태를 확인할 때까지 키를 액세스할 수 없습니다.
  -  **Code integrity is enabled(코드 무결성 사용):** 코드 무결성은 메모리에 로드될 때마다 드라이버 또는 시스템 파일의 무결성을 확인하는 기능입니다. 코드 무결성은 서명되지 않은 드라이버 또는 시스템 파일이 커널에 로드되는지 여부나 시스템 파일이 관리자 권한을 가진 사용자 계정에 의해 실행되는 악성 소프트웨어에 의해 수정되었는지 여부를 검색합니다.
  - **Secure Boot is enabled(보안 부팅 사용):** 보안 부팅을 사용하면 시스템이 신뢰할 수 있는 공장 기본 상태로 강제로 부팅됩니다. 또한 보안 부팅을 사용하면 컴퓨터를 부팅하는 데 사용되는 핵심 구성 요소에 장치를 제조한 조직에서 신뢰할 수 있는 올바른 암호화 서명이 있어야 합니다. UEFI 펌웨어는 컴퓨터가 시작되도록 허용하기 전에 이를 확인합니다. 파일이 변조되어 해당 서명이 손상된 경우에는 시스템이 부팅되지 않습니다.

  HAS 서비스의 작동 방식에 대한 자세한 내용은 [상태 증명 CSP](https://msdn.microsoft.com/library/dn934876.aspx)를 참조하세요.
##  <a name="device-property-settings"></a>장치 속성 설정
- **필요한 최소 OS:** 장치가 OS 최소 버전 요구 사항을 충족하지 못하면 비규격 장치로 보고됩니다.
    업그레이드 방법에 대한 정보를 제공하는 링크가 표시됩니다. 최종 사용자는 회사 리소스에 액세스할 수 있으면 장치를 업그레이드하도록 선택할 수 있습니다.

- **허용된 최대 OS 버전:** 장치가 규칙에 지정된 버전 이후의 OS를 사용하는 경우 회사 리소스에 대한 액세스가 차단되고 사용자는 IT 관리자에게 문의하라는 메시지가 표시됩니다. OS 버전 허용 규칙이 변경될 때까지 회사 리소스에 액세스하는 데 이 장치를 사용할 수 없습니다.


## <a name="compliance-policy-settings-for-windows-pcs"></a>Windows PC용 규정 준수 정책 설정
이 항목에 나열된 설정은 Windows PC에서 지원됩니다.
## <a name="system-security-settings"></a>시스템 보안 설정
### <a name="password"></a>암호
- **최소 암호 길이:** - Windows 8.1에서 지원됩니다.

  사용자의 암호에 포함해야 하는 최소 자릿수 또는 문자 수를 지정합니다.

  Microsoft 계정으로 액세스되는 장치의 경우 **최소 암호 길이**가 8자보다 길거나 **최소 문자 집합 수**가 2보다 크면 준수 정책 평가가 올바르게 이루어지지 않습니다.

- **필수 암호 유형:** - Windows RT, Windows RT 8.1, 및 Windows 8.1에서 지원됩니다.

  사용자가 **영숫자** 또는 **숫자** 암호를 만들어야 할지를 지정합니다.

- **최소 문자 집합 수:**  - Windows RT, Windows RT 8.1, 및 Windows 8.1에서 지원됩니다. **필수 암호 유형**을 **영숫자**로 설정한 경우 이 설정은 암호에 포함해야 하는 최소 문자 집합 수를 지정합니다. 4가지 문자 집합은 다음과 같습니다.
  -   소문자
  -   대문자
  -   기호
  -   숫자:     이 설정에 대해 더 큰 값을 설정하면 사용자는 더욱 복잡한 암호를 만들어야 합니다.

  Microsoft 계정으로 액세스되는 장치의 경우 **최소 암호 길이**가 8자보다 길거나 **최소 문자 집합 수**가 2보다 크면 준수 정책 평가가 올바르게 이루어지지 않습니다.
- **암호를 요구하기 전까지 비활성 시간(분):** - Windows RT, Windows RT 8.1, 및 Windows 8.1에서 지원됩니다.

  사용자가 해당 시간 내에 자신의 암호를 다시 입력해야 하는 유휴 시간을 지정합니다.

- **암호 만료(일):**  - Windows RT, Windows RT 8.1, 및 Windows 8.1에서 지원됩니다.

  사용자의 암호가 만료된 후 새로 만들어야 하기 전까지의 일수를 선택합니다.

- **암호 기록 기억:** - Windows RT, Windows RT, 및 Windows 8.1에서 지원됩니다.

  이 설정을 **이전 암호 다시 사용 방지**와 함께 사용하여 사용자가 이전에 사용했던 암호를 만들지 못하게 제한할 수 있습니다.
- **이전 암호 다시 사용 안 함:** - Windows RT, Windows RT 8.1, 및 Windows 8.1에서 지원됩니다.

  **암호 기록 기억**을 선택한 경우 다시 사용할 수 없는 이전에 사용했던 암호 수를 지정합니다.

## <a name="device-health-settings"></a>장치 상태 설정
- **장치가 정상으로 보고되어야 함:** - Windows 10 장치에서 지원됩니다.
기존 또는 새 준수 정책에서 Windows 10 장치가 정상으로 보고되어야 하도록 요구하는 규칙을 설정할 수 있습니다.  이 설정을 사용하면 다음 데이터 요소에 대해 Windows 10 장치가 HAS(상태 증명 서비스)를 통해 평가됩니다.
  -  **BitLocker is enabled(BitLocker 사용):** BitLocker를 켜면 시스템이 꺼져 있거나 절전 모드로 전환될 때 장치가 드라이브에 저장된 데이터를 무단 액세스로부터 보호할 수 있습니다. Windows BitLocker 드라이브 암호화는 Windows 운영 체제 볼륨에 저장된 모든 데이터를 암호화합니다. BitLocker는 TPM을 사용하여 Windows 운영 체제 및 사용자 데이터를 보호하고, 사용자가 자리를 비우거나 컴퓨터가 분실 또는 도난당한 경우에도 변조되지 않도록 합니다. 컴퓨터에 호환되는 TPM이 장착되어 있으면 BitLocker는 TPM을 사용하여 데이터를 보호하는 암호화 키를 잠급니다. 결과적으로, TPM이 컴퓨터의 상태를 확인할 때까지 키를 액세스할 수 없습니다.
  -  **Code integrity is enabled(코드 무결성 사용):** 코드 무결성은 메모리에 로드될 때마다 드라이버 또는 시스템 파일의 무결성을 확인하는 기능입니다. 코드 무결성은 서명되지 않은 드라이버 또는 시스템 파일이 커널에 로드되는지 여부나 시스템 파일이 관리자 권한을 가진 사용자 계정에 의해 실행되는 악성 소프트웨어에 의해 수정되었는지 여부를 검색합니다.
  - **Secure Boot is enabled(보안 부팅 사용):** 보안 부팅을 사용하면 시스템이 신뢰할 수 있는 공장 기본 상태로 강제로 부팅됩니다. 또한 보안 부팅을 사용하면 컴퓨터를 부팅하는 데 사용되는 핵심 구성 요소에 장치를 제조한 조직에서 신뢰할 수 있는 올바른 암호화 서명이 있어야 합니다. UEFI 펌웨어는 컴퓨터가 시작되도록 허용하기 전에 이를 확인합니다. 파일이 변조되어 해당 서명이 손상된 경우에는 시스템이 부팅되지 않습니다.
  - **Early-launch antimalware is enabled(맬웨어 방지 조기 실행 사용):** ELAM(맬웨어 방지 조기 실행)은 타사 드라이버가 초기화되기 전에 시작될 경우 네트워크의 컴퓨터를 보호합니다.

  HAS 서비스의 작동 방식에 대한 자세한 내용은 [상태 증명 CSP](https://msdn.microsoft.com/library/dn934876.aspx)를 참조하세요.

## <a name="device-property-settings"></a>장치 속성 설정
- **Minimum OS required(필요한 최소 OS):** - Windows 8.1 및 Windows 10에서 지원됩니다.

  여기에 major.minor.build 번호를 지정합니다. 버전 번호는 winver 명령에 의해 반환된 버전과 일치해야 합니다.

  지정된 OS 버전보다 이전 버전이 장치에 있으면 호환되지 않는 것으로 보고됩니다. 업그레이드 방법에 대한 정보를 제공하는 링크가 표시됩니다. 최종 사용자는 회사 리소스에 액세스할 수 있으면 장치를 업그레이드하도록 선택할 수 있습니다.

- **허용된 최대 OS 버전:** - Windows 8.1 및 Windows 10에서 지원됩니다.

  장치가 규칙에 지정된 버전 이후의 OS를 사용하는 경우 회사 리소스에 대한 액세스가 차단되고 사용자는 IT 관리자에게 문의하라는 메시지가 표시됩니다. OS 버전 허용 규칙이 변경될 때까지 회사 리소스에 액세스하는 데 이 장치를 사용할 수 없습니다.

**필요한 최소 OS** 및 **허용된 최대 OS 버전** 설정에 사용할 OS 버전을 찾으려면, 명령 프롬프트에서 **winver** 명령을 실행합니다. winver 명령은 보고된 운영 체제 버전을 반환합니다.
- Windows 8.1 PC는 **6.3** 버전을 반환합니다.    Windows에 대한 OS 버전 규칙이 Windows 8.1로 설정된 경우 장치에 Windows 8.1이 있어도 장치가 호환되지 않는 것으로 보고됩니다.
- Windows 10을 실행하는 PC의 버전은 "10.0"과 winver 명령에 의해 반환된 OS 빌드 번호로 설정되어야 합니다. 예를 들면 10.0.10586과 같이 설정해야 합니다.
> ![CA_Win10OSVersion](./media/ca_win10-os-version.png)



<!--HONumber=Nov16_HO2-->


