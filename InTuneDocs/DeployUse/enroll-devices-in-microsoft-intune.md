---
title: "장치 등록 | Microsoft Intune"
description: "MDM(모바일 장치 관리)에서는 등록을 사용하여 장치를 관리하고 리소스에 대한 액세스를 허용합니다."
keywords: 
<<<<<<< HEAD
author: NathBarn
||||||| merged common ancestors
author: NathBarn
ms.author: nathbarn
=======
author: staciebarker
ms.author: stabar
>>>>>>> 3cc2bcb16b2aaae00d16317c1b818ba25738a455
manager: angrobe
ms.date: 09/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8fc415f7-0053-4aa5-8d2b-03202eca4b87
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
<<<<<<< HEAD
||||||| merged common ancestors
<<<<<<<<< Temporary merge branch 1
=======
<<<<<<< HEAD
<<<<<<< HEAD
>>>>>>> 3cc2bcb16b2aaae00d16317c1b818ba25738a455
ms.sourcegitcommit: e6b182ebab1691c62e69cabaf4689ac7395ab31a
ms.openlocfilehash: 0995d3ced978f5213fdb0e9905f508b64a1e5c09
<<<<<<< HEAD
||||||| merged common ancestors
||||||||| merged common ancestors
ms.sourcegitcommit: a7a0f834df939432910e32e6e635a70f021b37a9
ms.openlocfilehash: 63405b43609eda515656ad397c5c7ff4253a8167
=========
ms.sourcegitcommit: 92e40930c0ccbeb3d98bef43b115fd92f24beaef
ms.openlocfilehash: 136f91e26a367ab107a80673930e735c85008ac7
>>>>>>>>> Temporary merge branch 2
=======
||||||| merged common ancestors
ms.sourcegitcommit: a7a0f834df939432910e32e6e635a70f021b37a9
ms.openlocfilehash: 63405b43609eda515656ad397c5c7ff4253a8167
=======
ms.sourcegitcommit: 92e40930c0ccbeb3d98bef43b115fd92f24beaef
ms.openlocfilehash: 136f91e26a367ab107a80673930e735c85008ac7
>>>>>>> 359d4f486355df1be118d8fdb698694ae632df85
||||||| merged common ancestors
ms.sourcegitcommit: 92e40930c0ccbeb3d98bef43b115fd92f24beaef
ms.openlocfilehash: 136f91e26a367ab107a80673930e735c85008ac7
=======
ms.sourcegitcommit: d51f34dea3463bec83ea39cdfb79c7bedf9e3926
ms.openlocfilehash: 0b60e7a7a921762e682185af273bb94f24441a0c
>>>>>>> 12550744143a4804819a881aa25136cdf07f4bcb
>>>>>>> 3cc2bcb16b2aaae00d16317c1b818ba25738a455


---

# <a name="enroll-devices-for-management-in-intune"></a>Intune에서 관리를 위해 장치 등록
Microsoft Intune으로 MDM(모바일 장치 관리)을 설정할 Windows PC 같은 장치를 등록할 수 있습니다. 이 항목에서는 Intune 관리에서 모바일 장치를 등록할 수 있는 다양한 방법을 설명합니다. 장치를 등록하는 방법은 장치 유형, 소유권 및 필요한 관리 수준에 따라 다릅니다. “BYOD”(Bring Your Own Device) 등록 방식에서는 개인 전화, 태블릿 또는 PC를 등록할 수 있습니다. COD(회사 소유의 장치) 등록 방식에서는 원격 초기화, 장치 공유, 장치에 대한 사용자 선호도 지정 같은 관리 시나리오가 가능합니다.

<<<<<<< HEAD
||||||| merged common ancestors
<<<<<<<<< Temporary merge branch 1
[Exchange ActiveSync](#mobile-device-management-with-exchange-activesync-and-intune)를 온-프레미스나 클라우드에서 호스트하여 사용하면 등록 과정 없이 간단하게 Intune을 관리할 수 있습니다. Windows PC에서는 [Intune 클라이언트 소프트웨어](#manage-windows-pcs-with-intune)를 사용하여 관리할 수 있습니다.
||||||||| merged common ancestors
도움을 받으려면 [장치를 등록하는 방법 선택](/intune/get-started/choose-how-to-enroll-devices1)을 참조하세요.

###  지원되는 장치 플랫폼

Intune은 다음 장치 플랫폼을 관리할 수 있습니다.

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

## 모바일 장치 관리 기관 설정
MDM 기관은 일련의 장치를 관리할 권한을 가진 관리 서비스를 정의합니다. MDM 기관에 대한 옵션에는 Intune 자체 및 Intune을 사용하는 Configuration Manager가 포함됩니다. Configuration Manager를 관리 기관으로 설정한 경우 모바일 장치 관리에 다른 서비스를 사용할 수 없습니다.

>[!IMPORTANT]
> Intune만 사용(온라인 서비스)하여 모바일 장치를 관리할지, 아니면 Intune으로 System Center Configuration Manager(온-프레미스 소프트웨어 솔루션 및 온라인 서비스 결합)를 사용하여 모바일 장치를 관리할지를 신중히 고려해야 합니다. 이런 항목을 설정한 후에는 모바일 장치 관리 기관을 변경할 수 없습니다.

1.  [Microsoft Intune 관리 콘솔](http://manage.microsoft.com)에서 **관리** &gt; **모바일 장치 관리**를 선택합니다.

2.  **작업** 목록에서 **모바일 장치 관리 기관 설정**을 클릭합니다. **MDM 기관 설정** 대화 상자가 열립니다.

    ![MDM 기관 설정 대화 상자](../media/intune-mdm-authority.png)

3.  Intune을 MDM 기관으로 지정할 것임을 확인하라는 요청 메시지가 표시됩니다. 이 확인란을 선택한 후 **예**를 선택하여 모바일 장치를 관리하는 데 Microsoft Intune을 사용합니다.

## Intune 회사 포털 구성

Intune 회사 포털에서 사용자는 회사 데이터에 액세스하고 장치 등록, 앱 설치, IT 부서 지원 정보 찾기 등의 일반적인 작업을 수행할 수 있습니다.

> [!TIP]
> 회사 포털을 사용자 지정할 때는 구성이 회사 포털 웹 사이트 및 회사 포털 앱에 모두 적용됩니다.

회사 포털을 사용자 지정하면 최종 사용자에게 친숙하고 유용한 환경을 제공하는 데 도움이 됩니다. 이렇게 하려면 [Microsoft Intune 관리자 콘솔](https://manage.microsoft.com)에 테넌트 또는 서비스 관리자로 로그인하고, **관리** &gt; **회사 포털**을 선택하여 회사 포털 설정을 구성합니다.

![admin-console-admin-workspace-comp-portal-settings](../media/cp_sa_cpsetup.PNG)
=========
=======
<<<<<<< HEAD
[Exchange ActiveSync](#mobile-device-management-with-exchange-activesync-and-intune)를 온-프레미스나 클라우드에서 호스트하여 사용하면 등록 과정 없이 간단하게 Intune을 관리할 수 있습니다. Windows PC에서는 [Intune 클라이언트 소프트웨어](#manage-windows-pcs-with-intune)를 사용하여 관리할 수 있습니다.
||||||| merged common ancestors
도움을 받으려면 [장치를 등록하는 방법 선택](/intune/get-started/choose-how-to-enroll-devices1)을 참조하세요.

###  지원되는 장치 플랫폼

Intune은 다음 장치 플랫폼을 관리할 수 있습니다.

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

## 모바일 장치 관리 기관 설정
MDM 기관은 일련의 장치를 관리할 권한을 가진 관리 서비스를 정의합니다. MDM 기관에 대한 옵션에는 Intune 자체 및 Intune을 사용하는 Configuration Manager가 포함됩니다. Configuration Manager를 관리 기관으로 설정한 경우 모바일 장치 관리에 다른 서비스를 사용할 수 없습니다.

>[!IMPORTANT]
> Intune만 사용(온라인 서비스)하여 모바일 장치를 관리할지, 아니면 Intune으로 System Center Configuration Manager(온-프레미스 소프트웨어 솔루션 및 온라인 서비스 결합)를 사용하여 모바일 장치를 관리할지를 신중히 고려해야 합니다. 이런 항목을 설정한 후에는 모바일 장치 관리 기관을 변경할 수 없습니다.

1.  [Microsoft Intune 관리 콘솔](http://manage.microsoft.com)에서 **관리** &gt; **모바일 장치 관리**를 선택합니다.

2.  **작업** 목록에서 **모바일 장치 관리 기관 설정**을 클릭합니다. **MDM 기관 설정** 대화 상자가 열립니다.

    ![MDM 기관 설정 대화 상자](../media/intune-mdm-authority.png)

3.  Intune을 MDM 기관으로 지정할 것임을 확인하라는 요청 메시지가 표시됩니다. 이 확인란을 선택한 후 **예**를 선택하여 모바일 장치를 관리하는 데 Microsoft Intune을 사용합니다.

## Intune 회사 포털 구성

Intune 회사 포털에서 사용자는 회사 데이터에 액세스하고 장치 등록, 앱 설치, IT 부서 지원 정보 찾기 등의 일반적인 작업을 수행할 수 있습니다.

> [!TIP]
> 회사 포털을 사용자 지정할 때는 구성이 회사 포털 웹 사이트 및 회사 포털 앱에 모두 적용됩니다.

회사 포털을 사용자 지정하면 최종 사용자에게 친숙하고 유용한 환경을 제공하는 데 도움이 됩니다. 이렇게 하려면 [Microsoft Intune 관리자 콘솔](https://manage.microsoft.com)에 테넌트 또는 서비스 관리자로 로그인하고, **관리** &gt; **회사 포털**을 선택하여 회사 포털 설정을 구성합니다.

![admin-console-admin-workspace-comp-portal-settings](../media/cp_sa_cpsetup.PNG)
=======
>>>>>>> 3cc2bcb16b2aaae00d16317c1b818ba25738a455
[Exchange ActiveSync](#mobile-device-management-with-exchange-activesync-and-intune)를 온-프레미스나 클라우드에서 호스트하여 사용하면 등록 과정 없이 간단하게 Intune을 관리할 수 있습니다. Windows PC에서는 [Intune 클라이언트 소프트웨어](#manage-windows-pcs-with-intune)를 사용하여 관리할 수 있습니다.

## <a name="overview-of-device-enrollment-methods"></a>장치 등록 방법 개요

다음 표에는 Intune의 등록 방법이 각 지원 기능과 함께 나와 있습니다. 이러한 기능은 다음과 같습니다.
<<<<<<< HEAD
||||||| merged common ancestors
- **초기화** - 장치를 공장 재설정하는 것으로 모든 데이터를 제거합니다. 자세한 내용은 [장치 사용 중지](retire-devices-from-microsoft-intune-management.md).
- **선호도** - 사용자와 장치를 연결합니다. MAM(모바일 응용 프로그램 관리)과 회사 데이터에 대한 조건부 액세스에는 필수입니다. 자세한 내용은 [사용자 선호도](enroll-corporate-owned-ios-devices-in-microsoft-intune.md#using-company-portal-on-dep-or-apple-configurator-enrolled-devices)를 참조하세요.
- **잠금** - 사용자가 관리에서 장치를 제거하지 못하도록 합니다. iOS 장치를 잠그려면 감독 모드로 설정해야 합니다. 자세한 내용은 [원격 잠금](retire-devices-from-microsoft-intune-management.md#block-access-a-device)을 참조하세요.

**iOS 등록 방법**

| **메서드** |  **초기화** |  **선호도**    |   **잠금** | **세부 정보** |
|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | 아니요|    예 |   아니요 | [추가 정보](prerequisites-for-enrollment.md#set-up-device-management)|
|**[DEM](#dem)**|   아니요 |아니요 |아니요  | [추가 정보](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|
|**[DEP](#dep)**|   예 |   선택 사항입니다. |  선택 사항입니다.|[추가 정보](ios-device-enrollment-program-in-microsoft-intune.md)|
|**[USB-SA](#usb-sa)**| 예 |   선택 사항입니다. |  아니요| [추가 정보](ios-setup-assistant-enrollment-in-microsoft-intune.md)|
|**[USB-Direct](#usb-direct)**| 아니요 |    아니요  | 아니요|[추가 정보](ios-direct-enrollment-in-microsoft-intune.md)|
>>>>>>>>> Temporary merge branch 2

**Windows 등록 방법**

<<<<<<<<< Temporary merge branch 1
다음 표에는 Intune의 등록 방법이 각 지원 기능과 함께 나와 있습니다. 이러한 기능은 다음과 같습니다.
=======
- **초기화** - 장치를 공장 재설정하는 것으로 모든 데이터를 제거합니다. 자세한 내용은 [장치 사용 중지](retire-devices-from-microsoft-intune-management.md).
- **선호도** - 사용자와 장치를 연결합니다. MAM(모바일 응용 프로그램 관리)과 회사 데이터에 대한 조건부 액세스에는 필수입니다. 자세한 내용은 [사용자 선호도](enroll-corporate-owned-ios-devices-in-microsoft-intune.md#using-company-portal-on-dep-or-apple-configurator-enrolled-devices)를 참조하세요.
- **잠금** - 사용자가 관리에서 장치를 제거하지 못하도록 합니다. iOS 장치를 잠그려면 감독 모드로 설정해야 합니다. 자세한 내용은 [원격 잠금](retire-devices-from-microsoft-intune-management.md#block-access-a-device)을 참조하세요.

**iOS 등록 방법**

| **방법** |  **초기화** |  **선호도**    |   **잠금** | **세부 정보** |
|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | 아니요|    예 |   아니요 | [추가 정보](prerequisites-for-enrollment.md#set-up-device-management)|
|**[DEM](#dem)**|   아니요 |아니요 |아니요  | [추가 정보](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|
|**[DEP](#dep)**|   예 |   선택 사항입니다. |  선택 사항입니다.|[추가 정보](ios-device-enrollment-program-in-microsoft-intune.md)|
|**[USB-SA](#usb-sa)**| 예 |   선택 사항입니다. |  아니요| [추가 정보](ios-setup-assistant-enrollment-in-microsoft-intune.md)|
|**[USB-Direct](#usb-direct)**| 아니요 |    아니요  | 아니요|[추가 정보](ios-direct-enrollment-in-microsoft-intune.md)|
>>>>>>> 359d4f486355df1be118d8fdb698694ae632df85

**Windows 등록 방법**

<<<<<<< HEAD
<<<<<<< HEAD
다음 표에는 Intune의 등록 방법이 각 지원 기능과 함께 나와 있습니다. 이러한 기능은 다음과 같습니다.
>>>>>>> 3cc2bcb16b2aaae00d16317c1b818ba25738a455
- **초기화** - 장치를 공장 재설정하는 것으로 모든 데이터를 제거합니다. [장치 사용 중지](retire-devices-from-microsoft-intune-management.md)
- **선호도** - 사용자와 장치를 연결합니다. MAM(모바일 응용 프로그램 관리)과 회사 데이터에 대한 조건부 액세스에는 필수입니다. [사용자 선호도](enroll-corporate-owned-ios-devices-in-microsoft-intune.md#using-company-portal-on-dep-or-apple-configurator-enrolled-devices)
- **잠금** 사용자가 관리에서 장치를 제거하지 못하도록 합니다. iOS 장치를 잠그려면 감독 모드로 설정해야 합니다. [원격 잠금](retire-devices-from-microsoft-intune-management.md#block-access-a-device)
<<<<<<< HEAD
||||||| merged common ancestors
||||||||| merged common ancestors
다음 표에서는 회사 소유 장치의 등록 방법 및 그 이점에 대해 보여 줍니다.
=========
| **메서드** |  **초기화** |  **선호도**    |   **잠금** | **세부 정보**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | 예|   예 |   아니요 | [추가 정보](prerequisites-for-enrollment.md#set-up-device-management)|
|**[DEM](#dem)**|   아니요 |아니요 |아니요  |[추가 정보](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|
>>>>>>>>> Temporary merge branch 2
=======
||||||| merged common ancestors
다음 표에서는 회사 소유 장치의 등록 방법 및 그 이점에 대해 보여 줍니다.
=======
| **메서드** |  **초기화** |  **선호도**    |   **잠금** | **세부 정보**|
||||||| merged common ancestors
| **메서드** |  **초기화** |  **선호도**    |   **잠금** | **세부 정보**|
=======
| **방법** |  **초기화** |  **선호도**    |   **잠금** | **세부 정보**|
>>>>>>> 12550744143a4804819a881aa25136cdf07f4bcb
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | 예|   예 |   아니요 | [추가 정보](prerequisites-for-enrollment.md#set-up-device-management)|
|**[DEM](#dem)**|   아니요 |아니요 |아니요  |[추가 정보](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|
>>>>>>> 359d4f486355df1be118d8fdb698694ae632df85
>>>>>>> 3cc2bcb16b2aaae00d16317c1b818ba25738a455

**iOS 등록 방법**

<<<<<<< HEAD
||||||| merged common ancestors
<<<<<<<<< Temporary merge branch 1
=======
<<<<<<< HEAD
<<<<<<< HEAD
>>>>>>> 3cc2bcb16b2aaae00d16317c1b818ba25738a455
| **메서드** |  **초기화** |  **선호도**    |   **잠금** | **세부 정보** |
|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | 아니요|    예 |   아니요 | [정보](get-ready-to-enroll-devices-in-microsoft-intune.md#set-up-device-management)|
|**[DEM](#dem)**|   아니요 |아니요 |아니요  | [정보](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|
|**[DEP](#dep)**|   예 |   선택 사항입니다. |  선택 사항입니다.|[정보](ios-device-enrollment-program-in-microsoft-intune.md)|
|**[USB-SA](#usb-sa)**| 예 |   선택 사항입니다. |  아니요| [정보](ios-setup-assistant-enrollment-in-microsoft-intune.md)|
|**[USB-Direct](#usb-direct)**| 아니요 |    아니요  | 아니요|[정보](ios-direct-enrollment-in-microsoft-intune.md)|
<<<<<<< HEAD
||||||| merged common ancestors
||||||||| merged common ancestors
| **메서드** |  **[초기화](#Wipe)** | **[선호도](#Affinity)**   |   **[Locked](#Lock)** |
|:---:|:---:|:---:|:---:|
|**[BYOD](#BYOD)** | 아니요|    예 |   아니요 |
|**[DEM](#DEM)**|   아니요 |아니요 |아니요  |
|**[DEP](#DEP)**|   예 |   옵션 |   옵션|
|**[USB-SA](#USB-SA)**| 예 |   옵션 |   아니요|
|**[USB-Direct](#USB-Direct)**| 아니요 |    아니요  | 아니요|
=========
| **메서드** |  **초기화** |  **선호도**    |   **잠금** | **세부 정보**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | 아니요|    예 |   아니요 | [추가 정보](prerequisites-for-enrollment.md#set-up-device-management)|
|**[DEM](#dem)**|   아니요 |아니요 |아니요  |[추가 정보](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|
>>>>>>>>> Temporary merge branch 2
=======
||||||| merged common ancestors
| **메서드** |  **[초기화](#Wipe)** | **[선호도](#Affinity)**   |   **[Locked](#Lock)** |
|:---:|:---:|:---:|:---:|
|**[BYOD](#BYOD)** | 아니요|    예 |   아니요 |
|**[DEM](#DEM)**|   아니요 |아니요 |아니요  |
|**[DEP](#DEP)**|   예 |   옵션 |   옵션|
|**[USB-SA](#USB-SA)**| 예 |   옵션 |   아니요|
|**[USB-Direct](#USB-Direct)**| 아니요 |    아니요  | 아니요|
=======
| **메서드** |  **초기화** |  **선호도**    |   **잠금** | **세부 정보**|
||||||| merged common ancestors
| **메서드** |  **초기화** |  **선호도**    |   **잠금** | **세부 정보**|
=======
| **방법** |  **초기화** |  **선호도**    |   **잠금** | **세부 정보**|
>>>>>>> 12550744143a4804819a881aa25136cdf07f4bcb
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | 아니요|    예 |   아니요 | [추가 정보](prerequisites-for-enrollment.md#set-up-device-management)|
|**[DEM](#dem)**|   아니요 |아니요 |아니요  |[추가 정보](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|
>>>>>>> 359d4f486355df1be118d8fdb698694ae632df85
>>>>>>> 3cc2bcb16b2aaae00d16317c1b818ba25738a455

**Windows 및 Android 등록 방법**

<<<<<<< HEAD
||||||| merged common ancestors
<<<<<<<<< Temporary merge branch 1
=======
<<<<<<< HEAD
<<<<<<< HEAD
>>>>>>> 3cc2bcb16b2aaae00d16317c1b818ba25738a455
| **메서드** |  **초기화** |  **선호도**    |   **잠금** | **세부 정보**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | 아니요|    예 |   아니요 | [정보](get-ready-to-enroll-devices-in-microsoft-intune.md#set-up-device-management)|
|**[DEM](#dem)**|   아니요 |아니요 |아니요  |[정보](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|

올바른 방법을 찾는 데 도움이 되는 질문은 [Choose how to enroll devices](/intune/get-started/choose-how-to-enroll-devices1)(장치 등록 방법 선택)를 참조하세요.
<<<<<<< HEAD
||||||| merged common ancestors
||||||||| merged common ancestors
| **메서드** |  **[초기화](#Wipe)** | **[선호도](#Affinity)**   |   **[Locked](#Lock)** |
|:---:|:---:|:---:|:---:|
|**[BYOD](#BYOD)** | 아니요|    예 |   아니요 |
|**[DEM](#DEM)**|   아니요 |아니요 |아니요  |
=========
## BYOD
"Bring Your Own Device" 사용자가 회사 포털 앱을 설치하고 장치를 등록합니다. 이렇게 하면 사용자가 회사 네트워크에 연결되어 도메인 또는 Azure Active Directory에 가입할 수 있습니다. 대부분의 플랫폼에서는 많은 COD 시나리오를 위해 BYOD 등록을 사용하도록 설정해야 합니다. 자세한 내용은 [장치 등록을 위한 필수 조건](prerequisites-for-enrollment.md)을 참조하세요. ([표로 돌아가기](#overview-of-device-enrollment-methods))
>>>>>>>>> Temporary merge branch 2
=======
||||||| merged common ancestors
| **메서드** |  **[초기화](#Wipe)** | **[선호도](#Affinity)**   |   **[Locked](#Lock)** |
|:---:|:---:|:---:|:---:|
|**[BYOD](#BYOD)** | 아니요|    예 |   아니요 |
|**[DEM](#DEM)**|   아니요 |아니요 |아니요  |
=======
## BYOD
||||||| merged common ancestors
## BYOD
=======
## <a name="byod"></a>BYOD
>>>>>>> 12550744143a4804819a881aa25136cdf07f4bcb
"Bring Your Own Device" 사용자가 회사 포털 앱을 설치하고 장치를 등록합니다. 이렇게 하면 사용자가 회사 네트워크에 연결되어 도메인 또는 Azure Active Directory에 가입할 수 있습니다. 대부분의 플랫폼에서는 많은 COD 시나리오를 위해 BYOD 등록을 사용하도록 설정해야 합니다. 자세한 내용은 [장치 등록을 위한 필수 조건](prerequisites-for-enrollment.md)을 참조하세요. ([표로 돌아가기](#overview-of-device-enrollment-methods))
>>>>>>> 359d4f486355df1be118d8fdb698694ae632df85
>>>>>>> 3cc2bcb16b2aaae00d16317c1b818ba25738a455

<<<<<<< HEAD
||||||| merged common ancestors
<<<<<<<<< Temporary merge branch 1
=======
<<<<<<< HEAD
<<<<<<< HEAD
>>>>>>> 3cc2bcb16b2aaae00d16317c1b818ba25738a455
## BYOD
"Bring Your Own Device" 사용자가 회사 포털 앱을 설치하고 장치를 등록합니다. 이렇게 하면 사용자가 회사 네트워크에 연결되어 도메인 또는 Azure Active Directory에 연결할 수 있습니다. BYOD 등록 설정은 대다수 플랫폼에서 다양한 COD 시나리오를 가능하게 하는데 반드시 필요합니다. [장치 등록을 위한 필수 조건](prerequisites-for-enrollment.md)을 참조하세요. ([테이블로 돌아가기](#overview-of-device-enrollment-methods))
<<<<<<< HEAD
||||||| merged common ancestors
||||||||| merged common ancestors
**장치 등록 방법**
=========
## 회사 소유 장치
Intune 콘솔을 사용하여 COD(회사 소유 장치)를 관리할 수 있습니다. Apple에서 제공한 도구를 통해 iOS 장치를 직접 등록할 수 있습니다. 관리자 또는 관리자 장치 등록 관리자를 사용하여 모든 장치 유형을 등록할 수 있습니다. IMEI 번호가 있는 장치도 회사 소유로 식별되고 태그가 지정되어 COD 시나리오를 사용할 수 있습니다.
>>>>>>>>> Temporary merge branch 2
=======
||||||| merged common ancestors
**장치 등록 방법**
=======
## 회사 소유 장치
||||||| merged common ancestors
## 회사 소유 장치
=======
## <a name="corporateowned-devices"></a>회사 소유 장치
>>>>>>> 12550744143a4804819a881aa25136cdf07f4bcb
Intune 콘솔을 사용하여 COD(회사 소유 장치)를 관리할 수 있습니다. Apple에서 제공한 도구를 통해 iOS 장치를 직접 등록할 수 있습니다. 관리자 또는 관리자 장치 등록 관리자를 사용하여 모든 장치 유형을 등록할 수 있습니다. IMEI 번호가 있는 장치도 회사 소유로 식별되고 태그가 지정되어 COD 시나리오를 사용할 수 있습니다.
>>>>>>> 359d4f486355df1be118d8fdb698694ae632df85
>>>>>>> 3cc2bcb16b2aaae00d16317c1b818ba25738a455

<<<<<<< HEAD
||||||| merged common ancestors
<<<<<<<<< Temporary merge branch 1
=======
<<<<<<< HEAD
>>>>>>> 3cc2bcb16b2aaae00d16317c1b818ba25738a455
## 회사 소유 장치
Intune 콘솔로 COD(회사 소유 장치)를 관리할 수 있습니다. Apple에서 제공한 도구를 통해 iOS 장치를 등록할 수 있습니다. 관리자 또는 관리자 장치 등록 관리자를 사용하여 모든 장치 유형을 등록할 수 있습니다. IMEI 번호가 있는 장치도 회사 소유로 식별되고 태그가 지정되어 COD 시나리오를 사용할 수 있습니다.

[회사 소유 장치 등록](manage-corporate-owned-devices.md)
<<<<<<< HEAD
||||||| merged common ancestors
||||||||| merged common ancestors
### BYOD
“Bring Your Own Device.” 사용자가 회사 포털 앱을 설치하고 장치를 등록합니다. 회사 포털에 장치를 등록하면 장치가 작업 공간에 연결됩니다. 회사 포털에 iOS 장치를 등록하려면 Apple ID가 필요합니다. BYOD의 경우 회사 소유 장치에 대한 추가 구성이 필요하지 않습니다. [장치 관리를 설정](get-ready-to-enroll-devices-in-microsoft-intune.md#set-up-device-management)하는 단계를 참조하세요. ([테이블로 돌아가기](#overview-of-device-enrollment-methods))
=========
자세한 내용은 [회사 소유 장치 등록](manage-corporate-owned-devices.md)을 참조하세요.
>>>>>>>>> Temporary merge branch 2
=======
||||||| merged common ancestors
### BYOD
“Bring Your Own Device.” 사용자가 회사 포털 앱을 설치하고 장치를 등록합니다. 회사 포털에 장치를 등록하면 장치가 작업 공간에 연결됩니다. 회사 포털에 iOS 장치를 등록하려면 Apple ID가 필요합니다. BYOD의 경우 회사 소유 장치에 대한 추가 구성이 필요하지 않습니다. [장치 관리를 설정](get-ready-to-enroll-devices-in-microsoft-intune.md#set-up-device-management)하는 단계를 참조하세요. ([테이블로 돌아가기](#overview-of-device-enrollment-methods))
=======
자세한 내용은 [회사 소유 장치 등록](manage-corporate-owned-devices.md)을 참조하세요.
>>>>>>> 359d4f486355df1be118d8fdb698694ae632df85
>>>>>>> 3cc2bcb16b2aaae00d16317c1b818ba25738a455

<<<<<<< HEAD
### DEM
<<<<<<< HEAD
||||||| merged common ancestors
<<<<<<<<< Temporary merge branch 1
=======
<<<<<<< HEAD
>>>>>>> 3cc2bcb16b2aaae00d16317c1b818ba25738a455
장치 등록 관리자는 회사 소유 장치를 여러 개 등록하여 관리할 수 있는 특수 Intune 계정입니다. 관리자는 회사 포털을 설치하고 사용자 정보가 없는 장치를 여러 대 등록할 수 있습니다. [DEM](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)에 대해 자세히 알아보세요. ([테이블로 돌아가기](#overview-of-device-enrollment-methods))
<<<<<<< HEAD
||||||| merged common ancestors
||||||||| merged common ancestors
장치 등록 관리자입니다. 관리자가 회사 소유의 장치를 관리하기 위한 DEM 계정을 만듭니다. 그러면 DEM이 회사 포털을 설치하고 사용자가 지정되지 않은 여러 장치를 등록할 수 있습니다. [DEM](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)에 대해 자세히 알아보세요. ([테이블로 돌아가기](#overview-of-device-enrollment-methods))
=========
장치 등록 관리자는 회사 소유 장치를 여러 개 등록하여 관리할 수 있는 특수 Intune 계정입니다. 관리자는 회사 포털을 설치하고 사용자 정보가 없는 장치를 여러 대 등록할 수 있습니다. [DEM](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)에 대해 자세히 알아보세요. ([표로 돌아가기](#overview-of-device-enrollment-methods))
>>>>>>>>> Temporary merge branch 2
=======
||||||| merged common ancestors
장치 등록 관리자입니다. 관리자가 회사 소유의 장치를 관리하기 위한 DEM 계정을 만듭니다. 그러면 DEM이 회사 포털을 설치하고 사용자가 지정되지 않은 여러 장치를 등록할 수 있습니다. [DEM](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)에 대해 자세히 알아보세요. ([테이블로 돌아가기](#overview-of-device-enrollment-methods))
=======
||||||| merged common ancestors
### DEM
=======
### <a name="dem"></a>DEM
>>>>>>> 12550744143a4804819a881aa25136cdf07f4bcb
장치 등록 관리자는 회사 소유 장치를 여러 개 등록하여 관리할 수 있는 특수 Intune 계정입니다. 관리자는 회사 포털을 설치하고 사용자 정보가 없는 장치를 여러 대 등록할 수 있습니다. [DEM](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)에 대해 자세히 알아보세요. ([표로 돌아가기](#overview-of-device-enrollment-methods))
>>>>>>> 359d4f486355df1be118d8fdb698694ae632df85
>>>>>>> 3cc2bcb16b2aaae00d16317c1b818ba25738a455

### <a name="dep"></a>DEP
Apple DEP(장치 등록 프로그램) 관리에서는 정책을 만든 후, 구입한 iOS 장치 중에서 DEP로 관리하는 장치에 "무선으로" 정책을 배포할 수 있습니다. 사용자가 처음으로 장치를 켜고 iOS 설치 도우미를 실행하면 장치가 등록됩니다. 이 방법은 **iOS 감독** 모드를 지원하며, 이 모드에서는 다음을 사용할 수 있습니다.
  - 잠긴 등록
  - 조건부 액세스
  - 탈옥 검색
  - 모바일 응용 프로그램 관리

[DEP](ios-device-enrollment-program-in-microsoft-intune.md)에 대해 자세히 알아보세요. ([테이블로 돌아가기](#overview-of-device-enrollment-methods))

<<<<<<< HEAD
### USB-SA
USB로 연결된 설치 도우미 등록입니다. 관리자가 Intune 정책을 만들어 Apple Configurator로 내보냅니다. USB로 연결된 회사 소유의 장치는 Intune 정책을 사용하여 준비됩니다. 관리자가 각 장치를 직접 등록해야 합니다. 사용자가 장치를 받아 설치 도우미를 실행하여 해당 장치를 등록합니다. 이 방법은 **iOS 감독** 모드를 지원하며, 이 모드에서는 다음을 사용할 수 있습니다.
||||||| merged common ancestors
### USB-SA
USB로 연결된 회사 소유의 장치는 Intune 정책을 사용하여 준비됩니다. 설치 도우미 등록을 위해서는 관리자가 Intune 정책을 만들어 Apple Configurator로 내보냅니다. 관리자는 각 장치를 수동으로 등록해야 합니다. 사용자가 장치를 받아 설치 도우미를 실행하여 해당 장치를 등록합니다. 이 방법은 **iOS 감독** 모드를 지원하며, 이 모드에서는 다음을 사용할 수 있습니다.
=======
### <a name="usbsa"></a>USB-SA
USB로 연결된 회사 소유의 장치는 Intune 정책을 사용하여 준비됩니다. 설치 도우미 등록을 위해서는 관리자가 Intune 정책을 만들어 Apple Configurator로 내보냅니다. 관리자는 각 장치를 수동으로 등록해야 합니다. 사용자가 장치를 받아 설치 도우미를 실행하여 해당 장치를 등록합니다. 이 방법은 **iOS 감독** 모드를 지원하며, 이 모드에서는 다음을 사용할 수 있습니다.
>>>>>>> 3cc2bcb16b2aaae00d16317c1b818ba25738a455
  - 조건부 액세스
  - 탈옥 검색
  - 모바일 응용 프로그램 관리

[Apple Configurator를 사용하여 설치 도우미를 등록](ios-setup-assistant-enrollment-in-microsoft-intune.md)하는 방법에 대해 자세히 알아보세요. ([테이블로 돌아가기](#overview-of-device-enrollment-methods))

<<<<<<< HEAD
### USB-Direct
<<<<<<< HEAD
||||||| merged common ancestors
<<<<<<<<< Temporary merge branch 1
=======
<<<<<<< HEAD
>>>>>>> 3cc2bcb16b2aaae00d16317c1b818ba25738a455
직접 등록입니다. 관리자가 Intune 정책을 만들어 Apple Configurator로 내보냅니다. USB로 연결된 회사 소유의 장치를 초기화하지 않고 직접 등록합니다. 관리자가 각 장치를 직접 등록해야 합니다. 장치는 사용자가 지정되지 않은 장치로 관리됩니다. 장치는 잠기거나 감독되지 않으며, 조건부 액세스, 탈옥 검색, 모바일 응용 프로그램 관리를 지원할 수 없습니다. [Apple Configurator를 사용하여 직접 등록](ios-direct-enrollment-in-microsoft-intune.md)하는 방법에 대해 자세히 알아보세요. ([테이블로 돌아가기](#overview-of-device-enrollment-methods))

<<<<<<< HEAD
||||||| merged common ancestors
||||||||| merged common ancestors
직접 등록입니다. 관리자가 Intune 정책을 만들어 Apple Configurator로 내보냅니다. USB로 연결된 회사 소유의 장치를 초기화하지 않고 직접 등록합니다. 관리자가 각 장치를 직접 등록해야 합니다. 장치는 사용자가 지정되지 않은 장치로 관리됩니다. 장치는 잠기거나 감독되지 않으며, 조건부 액세스, 탈옥 검색, 모바일 응용 프로그램 관리를 지원할 수 없습니다. [Apple Configurator를 사용하여 직접 등록](ios-direct-enrollment-in-microsoft-intune.md)하는 방법에 대해 자세히 알아보세요. ([테이블로 돌아가기](#overview-of-device-enrollment-methods))

**회사 소유 모바일 장치의 동작**

### 초기화
장치를 등록할 때 초기화해야 하는지 여부를 지정하며, 장치에서 모든 데이터를 제거하고 원래 상태로 되돌립니다.
[장치 사용 중지](retire-devices-from-microsoft-intune-management.md)([테이블로 돌아가기](#overview-of-device-enrollment-methods))

### 선호도
등록 방법이 장치를 특정 사용자와 연결하는 "사용자 선호도"를 지원하는지 여부를 지정합니다. "옵션" 장치는 사용자 선호도를 사용하거나 사용하지 않고 등록할 수 있습니다. 사용자 선호도는 다음을 지원하는 데 필요합니다.
  - MAM(모바일 응용 프로그램 관리) 앱
  - 메일 및 회사 데이터에 대한 조건부 액세스
  - 회사 포털 앱

[사용자 선호도](enroll-corporate-owned-ios-devices-in-microsoft-intune.md#using-company-portal-on-dep-or-apple-configurator-enrolled-devices)([테이블로 돌아가기](#overview-of-device-enrollment-methods))

### 잠금
사용자가 Intune 정책을 제거하는 것(사실상 관리에서 장치를 제거하는 동작)을 방지하기 위해 장치를 잠글 수 있는지 여부를 지정합니다. iOS 장치의 경우 장치를 잠그려면 감독 모드여야 합니다.
([테이블로 돌아가기](#overview-of-device-enrollment-methods))

## 장치 등록 사용  
 등록을 통해 사용자는 개인 장치에서 회사 리소스에 액세스할 수 있고 관리자는 해당 장치가 회사 리소스를 보호하는 정책을 준수하는지 확인할 수 있습니다. Intune으로 "BYOD(Bring your own device)" 시나리오를 사용하는 가장 좋은 방법입니다. 관리자는 Intune 콘솔에서 등록을 사용해야 하며 이 때 장치와 트러스트 관계를 만들고 사용자에게 라이선스를 할당해야 합니다. 그런 다음 일반적으로 사용자가 회사 또는 학교 자격 증명을 입력하여 장치를 등록합니다. 그런 다음 장치는 Intune에서 정책을 가져오고 리소스에 대한 액세스 권한을 얻습니다.

[Intune에서 장치 등록 준비](get-ready-to-enroll-devices-in-microsoft-intune.md)

## 회사 소유 장치 등록
Intune 콘솔로 COD(회사 소유 장치)를 관리할 수 있습니다. Apple에서 제공한 도구를 통해 iOS 장치를 등록할 수 있습니다. 관리자 또는 관리자 장치 등록 관리자를 사용하여 모든 장치 유형을 등록할 수 있습니다. IMEI 번호가 있는 장치도 회사 소유로 식별되고 태그가 지정되어 COD 시나리오를 사용할 수 있습니다.

[회사 소유 장치 등록](manage-corporate-owned-devices.md)

=========
직접 등록을 위해서는 관리자가 Intune 정책을 만들어 Apple Configurator로 내보냅니다. USB로 연결된 회사 소유의 장치는 직접 등록되고 출하 시 설정으로 초기화할 필요가 없습니다. 관리자는 각 장치를 수동으로 등록해야 합니다. 장치는 사용자가 지정되지 않은 장치로 관리됩니다. 장치는 잠기거나 감독이 되지 않으며, 조건부 액세스, 탈옥 검색, 모바일 응용 프로그램 관리를 지원할 수 없습니다. [Apple Configurator를 사용하여 직접 등록](ios-direct-enrollment-in-microsoft-intune.md)하는 방법에 대해 자세히 알아보세요. ([표로 돌아가기](#overview-of-device-enrollment-methods))

>>>>>>>>> Temporary merge branch 2
=======
||||||| merged common ancestors
직접 등록입니다. 관리자가 Intune 정책을 만들어 Apple Configurator로 내보냅니다. USB로 연결된 회사 소유의 장치를 초기화하지 않고 직접 등록합니다. 관리자가 각 장치를 직접 등록해야 합니다. 장치는 사용자가 지정되지 않은 장치로 관리됩니다. 장치는 잠기거나 감독되지 않으며, 조건부 액세스, 탈옥 검색, 모바일 응용 프로그램 관리를 지원할 수 없습니다. [Apple Configurator를 사용하여 직접 등록](ios-direct-enrollment-in-microsoft-intune.md)하는 방법에 대해 자세히 알아보세요. ([테이블로 돌아가기](#overview-of-device-enrollment-methods))

**회사 소유 모바일 장치의 동작**

### 초기화
장치를 등록할 때 초기화해야 하는지 여부를 지정하며, 장치에서 모든 데이터를 제거하고 원래 상태로 되돌립니다.
[장치 사용 중지](retire-devices-from-microsoft-intune-management.md)([테이블로 돌아가기](#overview-of-device-enrollment-methods))

### 선호도
등록 방법이 장치를 특정 사용자와 연결하는 "사용자 선호도"를 지원하는지 여부를 지정합니다. "옵션" 장치는 사용자 선호도를 사용하거나 사용하지 않고 등록할 수 있습니다. 사용자 선호도는 다음을 지원하는 데 필요합니다.
  - MAM(모바일 응용 프로그램 관리) 앱
  - 메일 및 회사 데이터에 대한 조건부 액세스
  - 회사 포털 앱

[사용자 선호도](enroll-corporate-owned-ios-devices-in-microsoft-intune.md#using-company-portal-on-dep-or-apple-configurator-enrolled-devices)([테이블로 돌아가기](#overview-of-device-enrollment-methods))

### 잠금
사용자가 Intune 정책을 제거하는 것(사실상 관리에서 장치를 제거하는 동작)을 방지하기 위해 장치를 잠글 수 있는지 여부를 지정합니다. iOS 장치의 경우 장치를 잠그려면 감독 모드여야 합니다.
([테이블로 돌아가기](#overview-of-device-enrollment-methods))

## 장치 등록 사용  
 등록을 통해 사용자는 개인 장치에서 회사 리소스에 액세스할 수 있고 관리자는 해당 장치가 회사 리소스를 보호하는 정책을 준수하는지 확인할 수 있습니다. Intune으로 "BYOD(Bring your own device)" 시나리오를 사용하는 가장 좋은 방법입니다. 관리자는 Intune 콘솔에서 등록을 사용해야 하며 이 때 장치와 트러스트 관계를 만들고 사용자에게 라이선스를 할당해야 합니다. 그런 다음 일반적으로 사용자가 회사 또는 학교 자격 증명을 입력하여 장치를 등록합니다. 그런 다음 장치는 Intune에서 정책을 가져오고 리소스에 대한 액세스 권한을 얻습니다.

[Intune에서 장치 등록 준비](get-ready-to-enroll-devices-in-microsoft-intune.md)

## 회사 소유 장치 등록
Intune 콘솔로 COD(회사 소유 장치)를 관리할 수 있습니다. Apple에서 제공한 도구를 통해 iOS 장치를 등록할 수 있습니다. 관리자 또는 관리자 장치 등록 관리자를 사용하여 모든 장치 유형을 등록할 수 있습니다. IMEI 번호가 있는 장치도 회사 소유로 식별되고 태그가 지정되어 COD 시나리오를 사용할 수 있습니다.

[회사 소유 장치 등록](manage-corporate-owned-devices.md)

=======
||||||| merged common ancestors
### USB-Direct
=======
### <a name="usbdirect"></a>USB-Direct
>>>>>>> 12550744143a4804819a881aa25136cdf07f4bcb
직접 등록을 위해서는 관리자가 Intune 정책을 만들어 Apple Configurator로 내보냅니다. USB로 연결된 회사 소유의 장치는 직접 등록되고 출하 시 설정으로 초기화할 필요가 없습니다. 관리자는 각 장치를 수동으로 등록해야 합니다. 장치는 사용자가 지정되지 않은 장치로 관리됩니다. 장치는 잠기거나 감독이 되지 않으며, 조건부 액세스, 탈옥 검색, 모바일 응용 프로그램 관리를 지원할 수 없습니다. [Apple Configurator를 사용하여 직접 등록](ios-direct-enrollment-in-microsoft-intune.md)하는 방법에 대해 자세히 알아보세요. ([표로 돌아가기](#overview-of-device-enrollment-methods))

<<<<<<< HEAD
>>>>>>> 359d4f486355df1be118d8fdb698694ae632df85
>>>>>>> 3cc2bcb16b2aaae00d16317c1b818ba25738a455
## Exchange ActiveSync와 Intune을 사용한 모바일 장치 관리
||||||| merged common ancestors
## Exchange ActiveSync와 Intune을 사용한 모바일 장치 관리
=======
## <a name="mobile-device-management-with-exchange-activesync-and-intune"></a>Exchange ActiveSync와 Intune을 사용한 모바일 장치 관리
>>>>>>> 12550744143a4804819a881aa25136cdf07f4bcb
EAS MDM 정책을 사용하여 등록되지는 않았지만 EAS(Exchange ActiveSync)에 연결된 모바일 장치를 Intune에서 관리할 수 있습니다. Intune에서는 Exchange 커넥터를 사용하여 EAS 및 클라우드 호스티드 온-프레미스와 통신합니다.

[Exchange ActiveSync와 Intune을 사용한 모바일 장치 관리](mobile-device-management-with-exchange-activesync-and-microsoft-intune.md)


## <a name="windows-pc-management-with-intune"></a>Intune을 사용하여 Windows PC 관리  
또한 Intune 클라이언트 소프트웨어를 사용하여 Windows PC를 관리하기 위해 Microsoft Intune을 사용할 수 있습니다. Intune 클라이언트로 관리하는 PC에서는 다음과 같은 작업이 가능합니다.

 - 소프트웨어 및 하드웨어 인벤토리 보고
 - 데스크톱 응용 프로그램(예:.exe 및.msi 파일) 설치
 - 방화벽 설정 관리

<<<<<<< HEAD
||||||| merged common ancestors
<<<<<<<<< Temporary merge branch 1
=======
<<<<<<< HEAD
>>>>>>> 3cc2bcb16b2aaae00d16317c1b818ba25738a455
Intune 클라이언트 소프트웨어로 관리된 PC는 초기화하거나 폐기할 수 없고 조건부 액세스, VPN 및 Wi-Fi 설정 또는 인증서 및 메일 구성의 배포와 같은 많은 Intune 관리 기능을 사용할 수 없습니다.
<<<<<<< HEAD
||||||| merged common ancestors
||||||||| merged common ancestors
Intune 클라이언트 소프트웨어로 관리된 컴퓨터는 선택적으로 초기화되거나 폐기될 수 없고 조건부 액세스, VPN 및 Wi-Fi 설정 또는 인증서 및 전자 메일 구성의 배포와 같은 많은 Intune 관리 기능을 사용할 수 없습니다.
=========
선택적 초기화를 사용할 수 있으나 Intune 클라이언트 소프트웨어로 관리되는 PC를 완벽하게 초기화할 수는 없습니다. Intune 소프트웨어 클라이언트로 관리되는 PC는 조건부 액세스, VPN 및 Wi-Fi 설정 또는 인증서 및 메일 구성의 배포와 같은 많은 Intune 관리 기능을 사용할 수 없습니다.

자세한 내용은 [Intune을 사용하여 Windows PC 관리](manage-windows-pcs-with-microsoft-intune.md)를 참조하세요.

## 지원되는 장치 플랫폼

Intune은 다음 장치 플랫폼을 관리할 수 있습니다.
=======
||||||| merged common ancestors
Intune 클라이언트 소프트웨어로 관리된 컴퓨터는 선택적으로 초기화되거나 폐기될 수 없고 조건부 액세스, VPN 및 Wi-Fi 설정 또는 인증서 및 전자 메일 구성의 배포와 같은 많은 Intune 관리 기능을 사용할 수 없습니다.
=======
선택적 초기화를 사용할 수 있으나 Intune 클라이언트 소프트웨어로 관리되는 PC를 완벽하게 초기화할 수는 없습니다. Intune 소프트웨어 클라이언트로 관리되는 PC는 조건부 액세스, VPN 및 Wi-Fi 설정 또는 인증서 및 메일 구성의 배포와 같은 많은 Intune 관리 기능을 사용할 수 없습니다.

자세한 내용은 [Intune을 사용하여 Windows PC 관리](manage-windows-pcs-with-microsoft-intune.md)를 참조하세요.

## <a name="supported-device-platforms"></a>지원되는 장치 플랫폼

Intune은 다음 장치 플랫폼을 관리할 수 있습니다.
>>>>>>> 3cc2bcb16b2aaae00d16317c1b818ba25738a455

<<<<<<< HEAD
||||||| merged common ancestors
[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]
>>>>>>>>> Temporary merge branch 2

<<<<<<<<< Temporary merge branch 1
=======
[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]
>>>>>>> 359d4f486355df1be118d8fdb698694ae632df85

<<<<<<< HEAD
>>>>>>> 3cc2bcb16b2aaae00d16317c1b818ba25738a455
[Intune을 사용하여 Windows PC 관리](manage-windows-pcs-with-microsoft-intune.md)

##  지원되는 장치 플랫폼

<<<<<<< HEAD
Intune은 다음 장치 플랫폼을 관리할 수 있습니다.

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

## 다음 단계
- [장치 등록을 위한 필수 조건](prerequisites-for-enrollment.md)
- [회사 소유 장치 관리](manage-corporate-owned-devices.md)
- [지원되는 모바일 장치 및 컴퓨터](../get-started/supported-mobile-devices-and-computers.md)
<<<<<<< HEAD
||||||| merged common ancestors
||||||||| merged common ancestors
[Intune을 사용하여 Windows PC 관리](manage-windows-pcs-with-microsoft-intune.md)
=========
## 다음 단계
- [장치 등록을 위한 필수 조건](prerequisites-for-enrollment.md)
- [회사 소유 장치 관리](manage-corporate-owned-devices.md)
- [지원되는 모바일 장치 및 컴퓨터](../get-started/supported-mobile-devices-and-computers.md)
>>>>>>>>> Temporary merge branch 2
=======
||||||| merged common ancestors
[Intune을 사용하여 Windows PC 관리](manage-windows-pcs-with-microsoft-intune.md)
=======
## 다음 단계
||||||| merged common ancestors
## 다음 단계
=======
## <a name="next-steps"></a>다음 단계
>>>>>>> 12550744143a4804819a881aa25136cdf07f4bcb
- [장치 등록을 위한 필수 조건](prerequisites-for-enrollment.md)
- [회사 소유 장치 관리](manage-corporate-owned-devices.md)
- [지원되는 모바일 장치 및 컴퓨터](../get-started/supported-mobile-devices-and-computers.md)
>>>>>>> 359d4f486355df1be118d8fdb698694ae632df85
>>>>>>> 3cc2bcb16b2aaae00d16317c1b818ba25738a455



<<<<<<< HEAD
||||||| merged common ancestors
<<<<<<<<< Temporary merge branch 1
=======
<<<<<<< HEAD
<<<<<<< HEAD
>>>>>>> 3cc2bcb16b2aaae00d16317c1b818ba25738a455
<!--HONumber=Sep16_HO3-->
<<<<<<< HEAD
||||||| merged common ancestors
||||||||| merged common ancestors
<!--HONumber=Aug16_HO4-->
=========
<!--HONumber=Oct16_HO3-->
>>>>>>>>> Temporary merge branch 2
=======
||||||| merged common ancestors
<!--HONumber=Aug16_HO4-->
=======
<!--HONumber=Oct16_HO3-->
>>>>>>> 359d4f486355df1be118d8fdb698694ae632df85
||||||| merged common ancestors
<!--HONumber=Oct16_HO3-->
=======
<!--HONumber=Nov16_HO2-->
>>>>>>> 12550744143a4804819a881aa25136cdf07f4bcb
>>>>>>> 3cc2bcb16b2aaae00d16317c1b818ba25738a455


