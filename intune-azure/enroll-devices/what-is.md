---
title: "Microsoft Intune 장치 등록이란 | Intune Azure 미리 보기 | Microsoft Docs"
description: "Intune Azure 미리 보기: 장치 iOS, Android 및 Windows 장치에 대한 등록을 알아봅니다."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 01/26/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 10cf9980468eff912557747c31994747c17a3ab4
ms.openlocfilehash: 01bf32ef874385019ea4b0fb0ce278554459287d


---

# <a name="what-is-device-enrollment"></a>장치 등록이란?
[!INCLUDE[azure_preview](../includes/azure_preview.md)]

이 항목에서는 등록에 대해 설명하고 Intune 관리에서 모바일 장치를 등록하는 다양한 방법을 열거합니다.

Intune에서 Windows PC를 비롯한 장치를 등록하여 이러한 장치를 관리할 수 있습니다. Intune 설명서에서는 이 기능을 MDM(모바일 장치 관리)이라고 합니다. 장치가 PC가 아니라 모바일 장치로 등록된 경우 Intune 서비스와 통신하는 사용하는 MDM 인증서를 발급합니다. 

장치를 등록하는 방법은 장치 유형, 소유권 및 필요한 관리 수준에 따라 다릅니다. BYOD("Bring Your Own Device") 등록을 사용하면 사용자가 개인 휴대폰, 태블릿 또는 PC를 등록할 수 있습니다. COD(회사 소유 장치) 등록을 사용하면 자동 등록, 공유 장치 또는 사전 승인된 등록 요구 사항과 같은 관리 시나리오를 사용할 수 있습니다.

Exchange ActiveSync를 클라우드에서 호스트하거나 온-프레미스로 사용하는 경우 등록하지 않고 간단한 Intune 관리를 사용할 수 있습니다(자세한 내용은 곧 제공 예정). Windows PC를 모바일 장치로 관리할 수 있습니다. 이는 아래 설명된 권장 방법입니다. 또한 [Intune 클라이언트 소프트웨어](https://docs.microsoft.com/intune/deploy-use/manage-windows-pcs-with-microsoft-intune)를 사용하여 Windows PC를 PC로 관리할 수 있습니다.


## <a name="overview-of-device-enrollment-methods"></a>장치 등록 방법 개요

다음 표는 Intune 등록 방법 및 각 방법에 지원되는 기능과 요구 사항을 보여 줍니다. 기능 및 요구 사항은 아래에 설명되어 있습니다. 표에 사용된 용어는 다음과 같습니다.

- **초기화** -장치를 등록하려면 먼저 초기화를 해야 하는지 여부를 나타냅니다. "초기화"라는 용어는 모든 데이터를 제거하는 장치의 공장 기본 설정을 의미합니다. 자세한 내용은 [장치에서 전체 또는 선택적 초기화 사용](/intune-azure/manage-devices/use-full-or-selective-wipe-on-devices-using-microsoft-intune)을 참조하세요.
- **선호도** - 장치를 사용자에 연결합니다. MAM(모바일 응용 프로그램 관리)과 회사 데이터에 대한 조건부 액세스에는 필수입니다. 자세한 내용은 [사용자 선호도](enroll-ios-devices-using-device-enrollment-program.md)를 참조하세요.
- **잠금** - 사용자가 관리에서 장치 등록을 취소할 수 없는지를 나타냅니다. 사용자는 회사 포털 앱을 사용하여 모든 플랫폼에서 장치 등록을 취소할 수 있습니다. 등록을 취소하기 위해 네이티브 운영 체제 메뉴를 사용할 수 없습니다.


**iOS 등록 방법**

| **방법** |  **초기화가 필요하세요?** |    **선호도**    |   **잠금** | **세부 정보** |
|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | 아니요|    예 |   아니요 | 자세한 내용은 곧 제공 예정|
|**[DEM](#dem)**|   아니요 |아니요 |아니요  | [추가 정보](enroll-ios-devices-using-device-enrollment-program.md)|
|**[DEP](#dep)**|   예 |   선택 사항 |  선택 사항입니다.|[추가 정보](enroll-ios-devices-using-device-enrollment-program.md)|
|**[USB-SA](#usb-sa)**| 예 |   선택 사항 |  아니요| [추가 정보](enroll-ios-devices-with-apple-configurator-and-setup-assistant.md)|
|**[USB-Direct](#usb-direct)**| 아니요 |    아니요  | 아니요|[추가 정보](enroll-ios-devices-with-apple-configurator-and-direct-enrollment.md)|



**Windows 등록 방법**

| **방법** |  **초기화가 필요하세요?** |    **선호도**    |   **잠금** | **세부 정보**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | 예|   예 |   아니요 | 자세한 내용은 곧 제공 예정|
|**[DEM](#dem)**|   아니요 |아니요 |아니요  |[추가 정보](enroll-devices-using-device-enrollment-manager.md)|

**Android 등록 방법**

| **방법** |  **초기화가 필요하세요?** |    **선호도**    |   **잠금** | **세부 정보**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | 아니요|    예 |   아니요 | 자세한 내용은 곧 제공 예정|
|**[DEM](#dem)**|   아니요 |아니요 |아니요  |[추가 정보](enroll-ios-devices-using-device-enrollment-program.md)|


## <a name="byod"></a>BYOD
"Bring Your Own Device" 사용자가 회사 포털 앱을 설치하고 장치를 등록합니다. 이렇게 하면 사용자가 회사 네트워크에 연결되어 도메인 또는 Azure Active Directory에 가입할 수 있습니다. 대부분의 플랫폼에서는 많은 COD 시나리오를 위해 BYOD 등록을 사용하도록 설정해야 합니다.

## <a name="corporate-owned-devices"></a>회사 소유 장치
Azure Portal을 사용하여 COD(회사 소유 장치)를 관리할 수 있습니다. Apple에서 제공한 도구를 통해 iOS 장치를 직접 등록할 수 있습니다. 관리자 또는 관리자 장치 등록 관리자를 사용하여 모든 장치 유형을 등록할 수 있습니다. COD 시나리오를 사용할 수 있도록 IMEI 번호가 있는 장치도 식별하고 회사 소유로 태그를 지정할 수 있습니다.

### <a name="dem"></a>DEM
장치 등록 관리자는 회사 소유 장치를 여러 개 등록하여 관리할 수 있는 특수 사용자 계정입니다. 관리자는 회사 포털을 설치하고 사용자가 없는 많은 장치를 등록할 수 있습니다. [DEM](enroll-devices-using-device-enrollment-manager.md)에 대해 자세히 알아보세요. ([표로 돌아가기](#overview-of-device-enrollment-methods))

### <a name="dep"></a>DEP
Apple DEP(장치 등록 프로그램) 관리에서는 정책을 만든 후, 구입한 iOS 장치 중에서 DEP로 관리하는 장치에 "무선으로" 정책을 배포할 수 있습니다. 사용자가 처음으로 장치를 켜고 iOS 설치 도우미를 실행하면 장치가 등록됩니다. 이 방법은 **iOS 감독** 모드를 지원하며, 이 모드에서는 다음을 사용할 수 있습니다.

  - 잠긴 등록
  - 키오스크 모드와 다른 고급 구성 및 제한 사항

iOS 등록에 대한 자세한 내용은 다음을 참조하세요.

- [iOS 장치를 등록하는 방법 선택](choose-ios-enrollment-method.md)
- [장치 등록 프로그램을 사용하여 iOS 장치 등록](enroll-ios-devices-using-device-enrollment-program.md) 
- [위의 표로 돌아가기](#overview-of-device-enrollment-methods)

### <a name="usb-sa"></a>USB-SA
설정 도우미 및 Apple Configurator IT 관리자는 USB 통해 Apple Configurator를 사용하여 등록할 각 회사 소유 장치를 [설정 도우미]를 통해 수동으로 준비합니다. IT 관리자는 등록 프로필을 만들어 Apple Configurator로 내보냅니다. 사용자가 장치를 받으면 [설정 도우미]를 실행하여 장치를 등록하라는 메시지가 표시됩니다. 이 방법은 **iOS 감독** 모드를 지원하며, 이 모드에서는 다음을 사용할 수 있습니다.
  - 잠긴 등록
  - 키오스크 모드와 다른 고급 구성 및 제한 사항

iOS 등록에 대한 자세한 내용은 다음을 참조하세요.

- [iOS 장치를 등록하는 방법 결정](choose-ios-enrollment-method.md)
- [Configurator 및 설정 도우미를 사용하여 iOS 장치 등록](enroll-ios-devices-with-apple-configurator-and-setup-assistant.md) 

### <a name="usb-direct"></a>USB-Direct
직접 등록의 경우 관리자가 등록 정책을 만들고 Apple Configurator로 내보내어 각 장치를 수동으로 등록해야 합니다. USB로 연결된 회사 소유의 장치는 직접 등록되고 출하 시 설정으로 초기화할 필요가 없습니다. 장치는 사용자가 지정되지 않은 장치로 관리됩니다. 장치는 잠기거나 감독이 되지 않으며, 조건부 액세스, 탈옥 검색, 모바일 응용 프로그램 관리를 지원할 수 없습니다. 

iOS 등록에 대한 자세한 내용은 다음을 참조하세요.

- [iOS 장치를 등록하는 방법 결정](choose-ios-enrollment-method.md)
- [Configurator 및 직접 등록을 사용하여 iOS 장치 등록](enroll-ios-devices-with-apple-configurator-and-direct-enrollment.md)

## <a name="mobile-device-management-with-exchange-activesync-and-intune"></a>Exchange ActiveSync와 Intune을 사용한 모바일 장치 관리
EAS MDM 정책을 사용하여 등록되지는 않았지만 EAS(Exchange ActiveSync)에 연결된 모바일 장치를 Intune에서 관리할 수 있습니다. Intune에서는 Exchange 커넥터를 사용하여 EAS 및 클라우드 호스티드 온-프레미스와 통신합니다. 자세한 내용은 곧 제공 예정


## <a name="windows-pc-management-with-intune"></a>Intune을 사용하여 Windows PC 관리  
또한 Intune 클라이언트 소프트웨어를 사용하여 Windows PC를 관리하기 위해 Microsoft Intune을 사용할 수 있습니다. Intune 클라이언트로 관리하는 PC에서는 다음과 같은 작업이 가능합니다.

 - 소프트웨어 및 하드웨어 인벤토리 보고
 - 데스크톱 응용 프로그램(예:.exe 및.msi 파일) 설치
 - 방화벽 설정 관리

선택적 초기화를 사용할 수 있으나 Intune 클라이언트 소프트웨어로 관리되는 PC를 완벽하게 초기화할 수는 없습니다. Intune 소프트웨어 클라이언트로 관리되는 PC는 조건부 액세스, VPN 및 Wi-Fi 설정 또는 인증서 및 메일 구성의 배포와 같은 많은 Intune 관리 기능을 사용할 수 없습니다. 자세한 내용은 곧 제공 예정

## <a name="supported-device-platforms-and-browsers"></a>지원되는 장치 플랫폼 및 브라우저

[Intune 지원 장치 및 브라우저](https://docs.microsoft.com/intune/get-started/supported-mobile-devices-and-computers) 참조

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>MDM 인증서 만료 후 모바일 장치 정리

MDM 인증서는 모바일 장치가 Intune 서비스와 통신할 때 자동으로 갱신됩니다. 모바일 장치(PC가 아님)가 초기화된 경우 또는 일정 기간 동안 Intune 서비스와 통신하지 못한 경우에는 MDM 인증서가 갱신되지 않습니다. MDM 인증서가 만료되고 180일 후 Azure Portal에서 장치가 제거됩니다.



<!--HONumber=Feb17_HO1-->


