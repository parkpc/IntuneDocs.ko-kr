---
title: "Microsoft Intune 장치 등록이란?"
titlesuffix: Azure portal
description: "iOS, Android 및 Windows 장치에 대한 등록을 알아봅니다.\""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 05/29/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dda7108aedcc4d3878fe3743ee0b88b26fabbe6f
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/09/2017
---
# <a name="what-is-device-enrollment"></a>장치 등록이란?
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

이 항목에서는 등록에 대해 설명하고 Intune 관리에서 모바일 장치를 등록하는 다양한 방법을 열거합니다.

Intune에서는 장치를 등록하여 관리할 수 있습니다. Intune 설명서에서는 이 기능을 MDM(모바일 장치 관리)이라고 합니다. Intune에서 등록하는 장치에는 MDM 인증서가 발급됩니다. 그러면 장치는 이 인증서를 사용하여 Intune 서비스와 통신합니다.

장치를 등록하는 방법은 장치 유형, 소유권 및 필요한 관리 수준에 따라 다릅니다. BYOD("Bring Your Own Device") 등록을 사용하면 사용자가 개인 휴대폰, 태블릿 또는 PC를 등록할 수 있습니다. COD(회사 소유 장치) 등록을 사용하면 자동 등록, 공유 장치 또는 사전 승인된 등록 요구 사항과 같은 관리 시나리오를 사용할 수 있습니다.

Exchange ActiveSync를 클라우드에서 호스트하거나 온-프레미스로 사용하는 경우 등록하지 않고 간단한 Intune 관리를 사용할 수 있습니다(자세한 내용은 곧 제공 예정). Windows PC를 모바일 장치로 관리할 수 있습니다. 이는 아래 설명된 권장 방법입니다.


## <a name="overview-of-device-enrollment-methods"></a>장치 등록 방법 개요

다음 표에는 아래에서 설명하는 Intune 등록 방법과 해당 기능 및 요구 사항의 개요가 나와 있습니다.
**범례**

- **초기화 필요** - 장치가 등록 중에 초기화됩니다.
- **사용자 선호도** - 사용자와 장치를 연결합니다. 자세한 내용은 [사용자 선호도](device-enrollment-program-enroll-ios.md)를 참조하세요.
- **잠김** - 사용자가 장치를 등록할 수 없습니다.

**iOS 등록 방법**

| **방법** |  **초기화 필요** |    **사용자 선호도**   |   **잠김** | **세부 정보** |
|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | 아니요|    예 |   아니요 | [추가 정보](./apple-mdm-push-certificate-get.md)|
|**[DEM](#dem)**|   아니요 |아니요 |아니요  | [추가 정보](./device-enrollment-program-enroll-ios.md)|
|**[DEP](#dep)**|   예 |   선택 사항 |  선택 사항입니다.|[추가 정보](./device-enrollment-program-enroll-ios.md)|
|**[USB-SA](#usb-sa)**| 예 |   선택 사항 |  아니요| [추가 정보](./apple-configurator-setup-assistant-enroll-ios.md)|
|**[USB-Direct](#usb-direct)**| 아니요 |    아니요  | 아니요|[추가 정보](./apple-configurator-direct-enroll-ios.md)|

**Windows 등록 방법**

| **방법** |  **초기화 필요** |    **사용자 선호도**   |   **잠김** | **세부 정보**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | 아니요 |   예 |   아니요 | [추가 정보](windows-enroll.md)|
|**[DEM](#dem)**|   아니요 |아니요 |아니요  |[추가 정보](device-enrollment-manager-enroll.md)|
|**자동 등록** | 아니요 |예 |아니요 | [추가 정보](./windows-enroll.md#enable-windows-10-automatic-enrollment)|
|**대량 등록** |아니요 |아니요 |아니요 | [추가 정보](./windows-bulk-enroll.md) |

**Android 등록 방법**

| **방법** |  **초기화 필요** |    **사용자 선호도**   |   **잠김** | **세부 정보**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | 아니요|    예 |   아니요 | [추가 정보](./android-enroll.md)|
|**[DEM](#dem)**|   아니요 |아니요 |아니요  |[추가 정보](./device-enrollment-program-enroll-ios.md)|
|**Android for Work**| 아니요 | 예 | 아니요| [추가 정보](./android-enroll.md#enable-enrollment-of-android-for-work-devices) |


## <a name="byod"></a>BYOD
"Bring Your Own Device" 사용자는 회사 포털 앱을 설치 및 실행하여 장치를 등록합니다. 사용자는 이 프로그램을 통해 전자 메일 등의 회사 리소스에 액세스할 수 있습니다.

## <a name="corporate-owned-devices"></a>회사 소유 장치
COD(회사 소유 장치) 등록 시나리오는 다음과 같습니다. Apple에서 제공한 도구를 통해 iOS 장치를 직접 등록할 수 있습니다. 관리자 또는 관리자 장치 등록 관리자를 사용하여 모든 장치 유형을 등록할 수 있습니다. COD 시나리오를 사용할 수 있도록 IMEI 번호가 있는 장치도 식별하고 회사 소유로 태그를 지정할 수 있습니다.

### <a name="dem"></a>DEM
DEM(장치 등록 관리자)은 회사 소유 장치를 여러 개 등록하여 관리할 수 있는 특수 사용자 계정입니다. 관리자는 회사 포털을 설치하고 사용자가 없는 많은 장치를 등록할 수 있습니다. [DEM](./device-enrollment-manager-enroll.md)에 대해 자세히 알아보세요.

### <a name="dep"></a>DEP
Apple DEP(장치 등록 프로그램) 관리에서는 정책을 만든 후, 구입한 iOS 장치 중에서 DEP로 관리하는 장치에 "무선으로" 정책을 배포할 수 있습니다. 사용자가 처음으로 장치를 켜고 iOS 설치 도우미를 실행하면 장치가 등록됩니다. 이 방법은 **iOS 감독** 모드를 지원하며, 이 모드에서는 다음 기능을 사용할 수 있습니다.

  - 잠긴 등록
  - 키오스크 모드와 다른 고급 구성 및 제한 사항

iOS DEP 등록에 대한 자세한 내용은 다음을 참조하세요.

- [iOS 장치를 등록하는 방법 선택](enrollment-method-choose-ios.md)
- [장치 등록 프로그램을 사용하여 iOS 장치 등록](device-enrollment-program-enroll-ios.md)

### <a name="usb-sa"></a>USB-SA
IT 관리자는 USB를 통해 Apple Configurator를 사용하여 등록할 각 회사 소유 장치를 설정 도우미를 사용하여 수동으로 준비합니다. IT 관리자는 등록 프로필을 만들어 Apple Configurator로 내보냅니다. 사용자가 장치를 받으면 [설정 도우미]를 실행하여 장치를 등록하라는 메시지가 표시됩니다. 이 방법은 **iOS 감독** 모드를 지원하며, 이 모드에서는 다음 기능을 사용할 수 있습니다.
  - 잠긴 등록
  - 키오스크 모드와 다른 고급 구성 및 제한 사항

설정 도우미를 사용한 iOS Apple Configurator 등록에 대한 자세한 내용은 다음을 참조하세요.

- [iOS 장치를 등록하는 방법 결정](enrollment-method-choose-ios.md)
- [Configurator 및 설정 도우미를 사용하여 iOS 장치 등록](apple-configurator-setup-assistant-enroll-ios.md)

### <a name="usb-direct"></a>USB-Direct
직접 등록의 경우 관리자가 등록 정책을 만들고 Apple Configurator로 내보내어 각 장치를 수동으로 등록해야 합니다. USB로 연결된 회사 소유의 장치는 직접 등록되고 출하 시 설정으로 초기화할 필요가 없습니다. 장치는 사용자가 지정되지 않은 장치로 관리됩니다. 장치는 잠기거나 감독이 되지 않으며, 조건부 액세스, 탈옥 검색, 모바일 응용 프로그램 관리를 지원할 수 없습니다.

iOS 등록에 대한 자세한 내용은 다음을 참조하세요.

- [iOS 장치를 등록하는 방법 결정](enrollment-method-choose-ios.md)
- [Configurator 및 직접 등록을 사용하여 iOS 장치 등록](apple-configurator-direct-enroll-ios.md)

## <a name="mobile-device-management-with-exchange-activesync-and-intune"></a>Exchange ActiveSync와 Intune을 사용한 모바일 장치 관리
EAS MDM 정책을 사용하면 등록되지는 않았지만 EAS(Exchange ActiveSync)에 연결하는 모바일 장치를 Intune에서 관리할 수 있습니다. Intune에서는 Exchange 커넥터를 사용하여 EAS 및 클라우드 호스티드 온-프레미스와 통신합니다. 자세한 내용은 곧 제공 예정

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>MDM 인증서 만료 후 모바일 장치 정리

MDM 인증서는 모바일 장치가 Intune 서비스와 통신할 때 자동으로 갱신됩니다. 모바일 장치가 초기화되거나 일정 기간에 Intune 서비스와 통신하지 못한 경우에는 MDM 인증서가 갱신되지 않습니다. MDM 인증서가 만료되고 180일 후 Azure Portal에서 장치가 제거됩니다.
