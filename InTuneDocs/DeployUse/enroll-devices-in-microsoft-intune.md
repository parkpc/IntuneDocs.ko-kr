---
title: "장치 등록 | Microsoft Intune"
description: "MDM(모바일 장치 관리)에서는 등록을 사용하여 장치를 관리하고 리소스에 대한 액세스를 허용합니다."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8fc415f7-0053-4aa5-8d2b-03202eca4b87
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d8e524b267622f91ed0c2ed854f931299f316312
ms.openlocfilehash: 15f4af1f870d619f4fd51e88d1aef91b0b45e66d


---

# Intune에서 관리를 위해 장치 등록
Microsoft Intune MDM(모바일 장치 관리)에서는 등록을 사용하여 장치를 관리하고 리소스에 대한 액세스를 허용합니다. 장치를 등록하는 방법은 장치 유형, 소유권 및 필요한 관리 수준에 따라 다릅니다. "BYOD(Bring your own device)" 및 COD(회사 소유 장치) 시나리오는 등록 프로세스를 필요로 합니다. Exchange ActiveSync를 사용하거나 온-프레미스 또는 클라우드에서 호스트되는 조직에서는 등록 요구 사항 없이 가볍게 관리할 수 있습니다. Windows PC에서는 Intune 클라이언트 소프트웨어를 사용하여 관리할 수 있습니다.

###  지원되는 장치 플랫폼

Intune은 다음 장치 플랫폼을 관리할 수 있습니다.

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

## 장치 등록 방법 개요

다음 표에서는 회사 소유 장치의 등록 방법 및 그 이점에 대해 보여 줍니다.

**iOS 등록 방법**

| **메서드** |  **[초기화](#Wipe)** | **[선호도](#Affinity)**   |   **[Locked](#Lock)** |
|:---:|:---:|:---:|:---:|
|**[BYOD](#BYOD)** | 아니요|    예 |   아니요 |
|**[DEM](#DEM)**|   아니요 |아니요 |아니요  |
|**[DEP](#DEP)**|   예 |   옵션 |   옵션|
|**[USB-SA](#USB-SA)**| 예 |   옵션 |   아니요|
|**[USB-Direct](#USB-Direct)**| 아니요 |    아니요  | 아니요|

**Windows 및 Android 등록 방법**

| **메서드** |  **[초기화](#Wipe)** | **[선호도](#Affinity)**   |   **[Locked](#Lock)** |
|:---:|:---:|:---:|:---:|
|**[BYOD](#BYOD)** | 아니요|    예 |   아니요 |
|**[DEM](#DEM)**|   아니요 |아니요 |아니요  |

**회사 소유 장치의 등록 방법**

### BYOD
“Bring Your Own Device.” 사용자가 회사 포털 앱을 설치하고 장치를 등록합니다. 회사 포털에 장치를 등록하면 장치가 작업 공간에 연결됩니다. 회사 포털에 iOS 장치를 등록하려면 Apple ID가 필요합니다. BYOD의 경우 회사 소유 장치에 대한 추가 구성이 필요하지 않습니다. [장치 관리를 설정](get-ready-to-enroll-devices-in-microsoft-intune.md#set-up-device-management)하는 단계를 참조하세요. ([테이블로 돌아가기](#overview-of-device-enrollment-methods))

### DEM
장치 등록 관리자입니다. 관리자가 회사 소유의 장치를 관리하기 위한 DEM 계정을 만듭니다. 그러면 DEM이 회사 포털을 설치하고 사용자가 지정되지 않은 여러 장치를 등록할 수 있습니다. [DEM](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)에 대해 자세히 알아보세요. ([테이블로 돌아가기](#overview-of-device-enrollment-methods))

### DEP
Apple 장치 등록 프로그램입니다. 관리자가 정책을 만들고, DEP를 사용하여 구매하고 관리하는 회사 소유의 iOS 장치에 이를 "무선으로" 배포합니다. 사용자가 iOS 설치 도우미를 실행하는 경우 장치가 등록됩니다. 이 방법은 **iOS 감독** 모드를 지원하며, 이 모드에서는 다음을 사용할 수 있습니다.
  - 잠긴 등록
  - 조건부 액세스
  - 탈옥 검색
  - 모바일 응용 프로그램 관리

[DEP](ios-device-enrollment-program-in-microsoft-intune.md)에 대해 자세히 알아보세요. ([테이블로 돌아가기](#overview-of-device-enrollment-methods))

### USB-SA
USB로 연결된 설치 도우미 등록입니다. 관리자가 Intune 정책을 만들어 Apple Configurator로 내보냅니다. USB로 연결된 회사 소유의 장치는 Intune 정책을 사용하여 준비됩니다. 관리자가 각 장치를 직접 등록해야 합니다. 사용자가 장치를 받아 설치 도우미를 실행하여 해당 장치를 등록합니다. 이 방법은 **iOS 감독** 모드를 지원하며, 이 모드에서는 다음을 사용할 수 있습니다.
  - 조건부 액세스
  - 탈옥 검색
  - 모바일 응용 프로그램 관리

[Apple Configurator를 사용하여 설치 도우미를 등록](ios-setup-assistant-enrollment-in-microsoft-intune.md)하는 방법에 대해 자세히 알아보세요. ([테이블로 돌아가기](#overview-of-device-enrollment-methods))

### USB-Direct
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

## Exchange ActiveSync와 Intune을 사용한 모바일 장치 관리
EAS MDM 정책을 사용하여 등록되지는 않았지만 EAS(Exchange ActiveSync)에 연결된 모바일 장치를 Intune에서 관리할 수 있습니다. Intune에서는 Exchange 커넥터를 사용하여 EAS 및 클라우드 호스티드 온-프레미스와 통신합니다.

[Exchange ActiveSync와 Intune을 사용한 모바일 장치 관리](mobile-device-management-with-exchange-activesync-and-microsoft-intune.md)


## Intune을 사용하여 Windows PC 관리  
또한 Windows PC Intune 클라이언트 소프트웨어를 사용하여 Windows PC를 관리하기 위해 Microsoft Intune을 사용할 수 있습니다. Intune 클라이언트로 관리하는 PC에서는 다음과 같은 작업이 가능합니다.

 - 소프트웨어 및 하드웨어 인벤토리 보고
 - 데스크톱 응용 프로그램(예:.exe 및.msi 파일) 설치
 - 방화벽 설정

Intune 클라이언트 소프트웨어로 관리된 컴퓨터는 선택적으로 초기화되거나 폐기될 수 없고 조건부 액세스, VPN 및 Wi-Fi 설정 또는 인증서 및 전자 메일 구성의 배포와 같은 많은 Intune 관리 기능을 사용할 수 없습니다.

[Intune을 사용하여 Windows PC 관리](manage-windows-pcs-with-microsoft-intune.md)



<!--HONumber=Aug16_HO1-->


