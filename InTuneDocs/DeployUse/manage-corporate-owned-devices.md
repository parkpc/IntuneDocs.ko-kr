---
# required metadata

title: 회사 소유 장치 관리 | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 2b60bbff-25e6-489b-9621-c71b4275fa06

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune으로 회사 소유 장치 등록
조직이나 회사 소유 장치(COD)를 장치, 구입 방법 및 조직의 요구에 따라 다양한 방법으로 Intune에서 관리할 수 있습니다.

## 회사 소유 iOS 장치 관리
이 등록 방법은 조직이 사용자용 장치를 구입하지만 장치 관리를 유지하고자 하는 “고유 장치 선택”(CYOD) 시나리오에 유용합니다. 조직이 iOS 장치를 구입한 경우 사용자가 장치를 처음 켤 때부터 장치가 관리되도록 등록을 미리 구성할 수 있습니다. Intune은 [Apple의 장치 등록 프로그램(DEP)](ios-device-enrollment-program-in-microsoft-intune.md)을 통한, 또는 [직접](ios-direct-enrollment-in-microsoft-intune.md) 또는 [설정 길잡이](ios-setup-assistant-enrollment-in-microsoft-intune.md) 등록의 경우 Mac 컴퓨터에서 실행하는 Apple 구성기를 사용한 등록을 지원합니다.

[회사 소유의 iOS 장치 등록](enroll-corporate-owned-ios-devices-in-microsoft-intune.md)

## 장치 등록 관리자
조직에서는 Intune을 사용하여 장치 등록 관리자 계정이라는 단일 사용자 계정으로 많은 수의 모바일 장치를 관리할 수 있습니다. 장치 등록 관리자 계정을 만든 후 해당 계정을 사용하여 관리자가 일반 사용자에게 기본적으로 허용한 표준 장치 5개 이상을 등록할 수 있습니다. 장치 등록 관리자로 장치를 등록하는 방법은 특정 사용자가 사용하지 않는 장치에만 적용됩니다. 이러한 장치는 예를 들어 POS(Point-Of-Sale) 또는 유틸리티 앱에는 유용하지만 전자 메일 또는 회사 리소스에 액세스해야 하는 사용자에게는 불편합니다.

[장치 등록 관리자로 회사 소유 장치 등록](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)

## IMEI(International Mobile Equipment Identity)
고유 국제 모바일 장비 ID(IMEI) 번호는 많은 모바일 장치 제조업체에 대 한 일반적인 장치 속성입니다. Intune 관리자는 회사 소유 장치에 대 한 IMEI 번호를 가져올 수 있습니다. 장치가 Intune에서 관리하게 되면 회사 소유 장치로 태그를 지정하고 해당 정책의 대상으로 지정할 수 있습니다

[IMEI(International Mobile Equipment Identity) 번호로 회사 소유의 장치 지정](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

## 회사 소유 장치의 등록 방법 개요

다음 표에서는 회사 소유 장치의 등록 방법 및 그 이점에 대해 보여 줍니다.

**iOS 등록 방법**

| **메서드** |  **[재설정](#Reset)** |   **[선호도](#Affinity)**   |   **[Locked](#Locked)** |
|:---:|:---:|:---:|:---:|
|**[BYOD](#BYOD)** | 아니요|    예 |   아니요 |
|**[DEM](#DEM)**|   아니요 |아니요 |아니요  |
|**[DEP](#DEP)**|   예 |   옵션 |   옵션|
|**[USB-SA](#USB-SA)**| 예 |   옵션 |   아니요|
|**[USB-Direct](#USB-Direct)**| 아니요 |    아니요  | 아니요|

**Windows 및 Android 등록 방법**

| **메서드** |  **[초기화](#Wipe)** | **[사용자](#User)**   |   **[Locked](#Locked)** |
|:---:|:---:|:---:|:---:|
|**[BYOD](#BYOD)** | 아니요|    예 |   아니요 |
|**[DEM](#DEM)**|   아니요 |아니요 |아니요  |

**회사 소유 장치의 등록 방법**

### BYOD
“Bring Your Own Device.” 사용자가 회사 포털 앱을 설치하고 장치를 등록합니다. 회사 포털에 장치를 등록하면 장치가 작업 공간에 연결됩니다. 회사 포털에 iOS 장치를 등록하려면 Apple ID가 필요합니다. BYOD의 경우 회사 소유 장치의 추가 구성이 필요하지 않습니다. [장치 관리를 설정](get-ready-to-enroll-devices-in-microsoft-intune#set-up-device-management.md)하는 단계를 참조하세요.

### DEM
장치 등록 관리자입니다. 관리자가 DEM 계정을 만듭니다. 그러면 DEM이 회사 포털을 설치하고 사용자가 지정되지 않은 여러 장치를 등록할 수 있습니다. [DEM](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)에 대해 자세히 알아보세요. ([표로 돌아가기](#overview-of corporate-owned-device-enrollment-methods))

### DEP
Apple 장치 등록 프로그램입니다. 관리자가 정책을 만들고, DEP를 사용하여 구매하고 관리하는 iOS 장치에 이를 "무선으로" 배포합니다. 사용자가 iOS 설정 길잡이를 실행하는 경우 장치가 등록됩니다. 이 방법은 **iOS 감독** 모드를 지원하며, 이 모드에서는 다음을 사용할 수 있습니다.
  - 잠긴 등록
  - 조건부 액세스
  - 탈옥 검색
  - 모바일 응용 프로그램 관리

[DEP](ios-device-enrollment-program-in-microsoft-intune.md)에 대해 자세히 알아보세요. ([표로 돌아가기](#overview-of corporate-owned-device-enrollment-methods))

### USB-SA
USB 연결, 설치 도우미 등록입니다. 관리자가 Intune 정책을 만들어 Apple Configurator로 내보냅니다. USB로 연결된 장치는 Intune 정책을 사용하여 준비됩니다. 관리자가 각 장치를 직접 등록해야 합니다. 사용자가 장치를 받아 설치 도우미를 실행하여 해당 장치를 등록합니다. 이 방법은 **iOS 감독** 모드를 지원하며, 이 모드에서는 다음을 사용할 수 있습니다.
  - 잠긴 등록
  - 조건부 액세스
  - 탈옥 검색
  - 모바일 응용 프로그램 관리

[Apple Configurator를 사용하여 설치 도우미를 등록](ios-setup-assistant-enrollment-in-microsoft-intune.md)하는 방법에 대해 자세히 알아보세요. ([표로 돌아가기](#overview-of corporate-owned-device-enrollment-methods))

### USB-Direct
직접 등록입니다. 관리자가 Intune 정책을 만들어 Apple Configurator로 내보냅니다. USB로 연결된 장치를 초기화하지 않고 직접 등록합니다. 관리자가 각 장치를 직접 등록해야 합니다. 장치는 사용자가 지정되지 않은 장치로 관리됩니다. 장치는 잠기거나 감독되지 않으며, 조건부 액세스, 탈옥 검색, 모바일 응용 프로그램 관리를 지원할 수 없습니다. [Apple Configurator를 사용하여 직접 등록](ios-direct-enrollment-in-microsoft-intune.md)하는 방법에 대해 자세히 알아보세요. ([표로 돌아가기](#overview-of corporate-owned-device-enrollment-methods))

**회사 소유 모바일 장치의 동작**

### 재설정
장치를 등록할 때 초기화해야 하는지 여부를 지정하며, 장치에서 모든 데이터를 제거하고 원래 상태로 되돌립니다.
([표로 돌아가기](#overview-of corporate-owned-device-enrollment-methods))

### 선호도
등록 방법이 장치를 특정 사용자와 연결하는 "사용자 선호도"를 지원하는지 여부를 지정합니다. "옵션" 장치는 사용자 선호도를 사용하거나 사용하지 않고 등록할 수 있습니다. 사용자 선호도는 다음을 지원하는 데 필요합니다.
  - MAM(모바일 응용 프로그램 관리) 앱
  - 메일 및 회사 데이터에 대한 조건부 액세스
  - 회사 포털 앱

([표로 돌아가기](#overview-of corporate-owned-device-enrollment-methods)) ([표로 돌아가기](#overview-of corporate-owned-device-enrollment-methods))

### 잠금
사용자가 Intune 정책을 제거하는 것(사실상 관리에서 장치를 제거하는 동작)을 방지하기 위해 장치를 잠글 수 있는지 여부를 지정합니다. iOS 장치의 경우 장치를 잠그려면 감독 모드여야 합니다.
([표로 돌아가기](#overview-of corporate-owned-device-enrollment-methods)) ([표로 돌아가기](#overview-of corporate-owned-device-enrollment-methods))


<!--HONumber=Jun16_HO1-->


