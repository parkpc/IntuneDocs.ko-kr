---
title: "장치 등록 | Microsoft Intune"
description: "MDM(모바일 장치 관리)에서는 등록을 사용하여 장치를 관리하고 리소스에 대한 액세스를 허용합니다."
keywords: 
author: staciebarker
ms.author: stabar
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
ms.sourcegitcommit: d51f34dea3463bec83ea39cdfb79c7bedf9e3926
ms.openlocfilehash: 0b60e7a7a921762e682185af273bb94f24441a0c


---

# <a name="enroll-devices-for-management-in-intune"></a>Intune에서 관리를 위해 장치 등록
Microsoft Intune으로 MDM(모바일 장치 관리)을 설정할 Windows PC 같은 장치를 등록할 수 있습니다. 이 항목에서는 Intune 관리에서 모바일 장치를 등록할 수 있는 다양한 방법을 설명합니다. 장치를 등록하는 방법은 장치 유형, 소유권 및 필요한 관리 수준에 따라 다릅니다. “BYOD”(Bring Your Own Device) 등록 방식에서는 개인 전화, 태블릿 또는 PC를 등록할 수 있습니다. COD(회사 소유의 장치) 등록 방식에서는 원격 초기화, 장치 공유, 장치에 대한 사용자 선호도 지정 같은 관리 시나리오가 가능합니다.

[Exchange ActiveSync](#mobile-device-management-with-exchange-activesync-and-intune)를 온-프레미스나 클라우드에서 호스트하여 사용하면 등록 과정 없이 간단하게 Intune을 관리할 수 있습니다. Windows PC에서는 [Intune 클라이언트 소프트웨어](#manage-windows-pcs-with-intune)를 사용하여 관리할 수 있습니다.

## <a name="overview-of-device-enrollment-methods"></a>장치 등록 방법 개요

다음 표에는 Intune의 등록 방법이 각 지원 기능과 함께 나와 있습니다. 이러한 기능은 다음과 같습니다.
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

**Windows 등록 방법**

| **방법** |  **초기화** |  **선호도**    |   **잠금** | **세부 정보**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | 예|   예 |   아니요 | [추가 정보](prerequisites-for-enrollment.md#set-up-device-management)|
|**[DEM](#dem)**|   아니요 |아니요 |아니요  |[추가 정보](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|

**Android 등록 방법**

| **방법** |  **초기화** |  **선호도**    |   **잠금** | **세부 정보**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | 아니요|    예 |   아니요 | [추가 정보](prerequisites-for-enrollment.md#set-up-device-management)|
|**[DEM](#dem)**|   아니요 |아니요 |아니요  |[추가 정보](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|

올바른 방법을 찾는 데 도움이 되는 질문은 [장치 등록 방법 선택](/intune/get-started/choose-how-to-enroll-devices1)를 참조하세요.

## <a name="byod"></a>BYOD
"Bring Your Own Device" 사용자가 회사 포털 앱을 설치하고 장치를 등록합니다. 이렇게 하면 사용자가 회사 네트워크에 연결되어 도메인 또는 Azure Active Directory에 가입할 수 있습니다. 대부분의 플랫폼에서는 많은 COD 시나리오를 위해 BYOD 등록을 사용하도록 설정해야 합니다. 자세한 내용은 [장치 등록을 위한 필수 조건](prerequisites-for-enrollment.md)을 참조하세요. ([표로 돌아가기](#overview-of-device-enrollment-methods))

## <a name="corporateowned-devices"></a>회사 소유 장치
Intune 콘솔을 사용하여 COD(회사 소유 장치)를 관리할 수 있습니다. Apple에서 제공한 도구를 통해 iOS 장치를 직접 등록할 수 있습니다. 관리자 또는 관리자 장치 등록 관리자를 사용하여 모든 장치 유형을 등록할 수 있습니다. IMEI 번호가 있는 장치도 회사 소유로 식별되고 태그가 지정되어 COD 시나리오를 사용할 수 있습니다.

자세한 내용은 [회사 소유 장치 등록](manage-corporate-owned-devices.md)을 참조하세요.

### <a name="dem"></a>DEM
장치 등록 관리자는 회사 소유 장치를 여러 개 등록하여 관리할 수 있는 특수 Intune 계정입니다. 관리자는 회사 포털을 설치하고 사용자 정보가 없는 장치를 여러 대 등록할 수 있습니다. [DEM](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)에 대해 자세히 알아보세요. ([표로 돌아가기](#overview-of-device-enrollment-methods))

### <a name="dep"></a>DEP
Apple DEP(장치 등록 프로그램) 관리에서는 정책을 만든 후, 구입한 iOS 장치 중에서 DEP로 관리하는 장치에 "무선으로" 정책을 배포할 수 있습니다. 사용자가 처음으로 장치를 켜고 iOS 설치 도우미를 실행하면 장치가 등록됩니다. 이 방법은 **iOS 감독** 모드를 지원하며, 이 모드에서는 다음을 사용할 수 있습니다.
  - 잠긴 등록
  - 조건부 액세스
  - 탈옥 검색
  - 모바일 응용 프로그램 관리

[DEP](ios-device-enrollment-program-in-microsoft-intune.md)에 대해 자세히 알아보세요. ([표로 돌아가기](#overview-of-device-enrollment-methods))

### <a name="usbsa"></a>USB-SA
USB로 연결된 회사 소유의 장치는 Intune 정책을 사용하여 준비됩니다. 설치 도우미 등록을 위해서는 관리자가 Intune 정책을 만들어 Apple Configurator로 내보냅니다. 관리자는 각 장치를 수동으로 등록해야 합니다. 사용자가 장치를 받아 설치 도우미를 실행하여 해당 장치를 등록합니다. 이 방법은 **iOS 감독** 모드를 지원하며, 이 모드에서는 다음을 사용할 수 있습니다.
  - 조건부 액세스
  - 탈옥 검색
  - 모바일 응용 프로그램 관리

[Apple Configurator를 사용하여 설치 도우미를 등록](ios-setup-assistant-enrollment-in-microsoft-intune.md)하는 방법에 대해 자세히 알아보세요. ([표로 돌아가기](#overview-of-device-enrollment-methods))

### <a name="usbdirect"></a>USB-Direct
직접 등록을 위해서는 관리자가 Intune 정책을 만들어 Apple Configurator로 내보냅니다. USB로 연결된 회사 소유의 장치는 직접 등록되고 출하 시 설정으로 초기화할 필요가 없습니다. 관리자는 각 장치를 수동으로 등록해야 합니다. 장치는 사용자가 지정되지 않은 장치로 관리됩니다. 장치는 잠기거나 감독이 되지 않으며, 조건부 액세스, 탈옥 검색, 모바일 응용 프로그램 관리를 지원할 수 없습니다. [Apple Configurator를 사용하여 직접 등록](ios-direct-enrollment-in-microsoft-intune.md)하는 방법에 대해 자세히 알아보세요. ([표로 돌아가기](#overview-of-device-enrollment-methods))

## <a name="mobile-device-management-with-exchange-activesync-and-intune"></a>Exchange ActiveSync와 Intune을 사용한 모바일 장치 관리
EAS MDM 정책을 사용하여 등록되지는 않았지만 EAS(Exchange ActiveSync)에 연결된 모바일 장치를 Intune에서 관리할 수 있습니다. Intune에서는 Exchange 커넥터를 사용하여 EAS 및 클라우드 호스티드 온-프레미스와 통신합니다.

자세한 내용은 [Exchange ActiveSync와 Intune을 사용한 모바일 장치 관리](mobile-device-management-with-exchange-activesync-and-microsoft-intune.md)를 참조하세요.


## <a name="windows-pc-management-with-intune"></a>Intune을 사용하여 Windows PC 관리  
또한 Intune 클라이언트 소프트웨어를 사용하여 Windows PC를 관리하기 위해 Microsoft Intune을 사용할 수 있습니다. Intune 클라이언트로 관리하는 PC에서는 다음과 같은 작업이 가능합니다.

 - 소프트웨어 및 하드웨어 인벤토리 보고
 - 데스크톱 응용 프로그램(예:.exe 및.msi 파일) 설치
 - 방화벽 설정 관리

선택적 초기화를 사용할 수 있으나 Intune 클라이언트 소프트웨어로 관리되는 PC를 완벽하게 초기화할 수는 없습니다. Intune 소프트웨어 클라이언트로 관리되는 PC는 조건부 액세스, VPN 및 Wi-Fi 설정 또는 인증서 및 메일 구성의 배포와 같은 많은 Intune 관리 기능을 사용할 수 없습니다.

자세한 내용은 [Intune을 사용하여 Windows PC 관리](manage-windows-pcs-with-microsoft-intune.md)를 참조하세요.

## <a name="supported-device-platforms"></a>지원되는 장치 플랫폼

Intune은 다음 장치 플랫폼을 관리할 수 있습니다.

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

## <a name="next-steps"></a>다음 단계
- [장치 등록을 위한 필수 조건](prerequisites-for-enrollment.md)
- [회사 소유 장치 관리](manage-corporate-owned-devices.md)
- [지원되는 모바일 장치 및 컴퓨터](../get-started/supported-mobile-devices-and-computers.md)



<!--HONumber=Nov16_HO2-->


