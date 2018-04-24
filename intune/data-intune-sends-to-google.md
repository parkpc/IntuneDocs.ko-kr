---
title: Intune이 Google에 보내는 데이터
titleSuffix: Microsoft Intune
description: Intune이 Google에 보내는 데이터 목록입니다.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a5c3bec4-18ed-11e8-accf-0ed5f89f718b
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 78fef57849b8742bb10ece1717234af5cce3f4ba
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="data-intune-sends-to-google"></a>Intune이 Google에 보내는 데이터

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Android 장치 관리가 장치에서 사용되는 경우 Microsoft Intune이 Google과 연결되고 Google과 사용자 및 장치 정보를 공유합니다. Microsoft Intune이 연결을 설정하기 전에 Google 계정을 만들어야 합니다.

다음 표는 장치에서 장치 관리를 사용하는 경우 Microsoft Intune이 Google에 보내는 데이터를 보여 줍니다.


| Google에 보낸 데이터 | 세부 정보 | 사용 목적 | 예제 |
|:---:|:---:|:---:|:---:|
| EnterpriseId | Intune에 Gmail 계정 바인딩 시 Google에서 발생합니다. | Intune과 Google 간 통신에 사용되는 기본 식별자입니다.  이 통신에는 정책 설정, 관리 장치, Intune과 Android Enterprise 간의 바인딩/바인딩 해제가 포함됩니다. | 고유 식별자, 형식 예: LC04eik8a6 |
| 정책 본문 | 새 응용 프로그램 또는 구성 정책을 저장하는 경우 Intune에서 발생합니다. | 장치에 정책을 적용합니다. | 응용 프로그램 또는 구성 정책을 위해 구성된 모든 설정의 컬렉션입니다. 이 컬렉션에는 네트워크 이름, 응용 프로그램 이름, 응용 프로그램별 설정 같은 정책의 일부로서 제공되는 경우 고객 정보를 포함할 수 있습니다. |
| 장치 데이터 | 작업 프로필 시나리오를 위해 장치는 Intune에 등록을 시작합니다. 관리 장치 시나리오를 위해 장치는 Google에 등록을 시작합니다. | 장치 데이터 정보는 정책 적용, 장치 관리 및 일반적인 보고 같은 다양한 작업을 위해 Intune과 Google 간에 전송됩니다. | **장치 이름을 나타내는 고유 식별자입니다.** 예: enterprises/LC04ebru7b/devices/3592d971168f9ae4<br>**사용자 이름을 나타내는 고유 식별자입니다.** 예: Enterprises/LC04ebru7b/users/116838519924207449711<br>**장치 상태입니다.** 예제: 활성, 사용하지 않음, 프로비전.<br>**준수 상태입니다.** 예제: 설정 지원되지 않음, 누락된 필수 응용 프로그램<br>**소프트웨어 정보입니다.** 예제: 소프트웨어 버전 및 패치 수준.<br>**네트워크 정보입니다.** 예제: IMEI, MEID, WifiMacAddress<br>**장치 설정입니다.** 예제: 암호화 수준에 대한 정보 및 장치가 알려지지 않은 응용 프로그램을 허용하는지 여부.<br> JSON 메시지의 예제는 아래를 참조하십시오. |
| newPassword | Intune에서 발생합니다. | 장치 암호를 재설정합니다. | 새 암호를 나타내는 문자열입니다. |
| Google 사용자 | Google | 작업 프로필(BYOD) 시나리오에 대한 작업 프로필을 관리합니다. | 연결된 Gmail 계정을 나타내는 고유 식별자입니다. 예: 114223373813435875042 |
| 응용 프로그램 데이터 | 응용 프로그램 정책을 저장하는 경우 Intune에서 발생 합니다. |  | 응용 프로그램 이름 문자열입니다. 예: app:com.microsoft.windowsintune.companyportal |
| Enterprise 서비스 계정 | Intune 요청 시 Google에서 발생합니다. | 해당 고객 관련 트랜잭션을 위해 Intune과 Google 간 인증에 사용됩니다. | 몇 가지 파트가 있습니다.<br> **Enterprise Id**: 이전에 문서화됐습니다.<br>**UPN**: 고객 대신 인증에 사용된 UPN을 생성 했습니다.<br>예: w49d77900526190e26708c31c9e8a0@pfwp-commicrosoftonedfmdm2.google.com.iam.gserviceaccount.com<br>**키**: 해당 서비스에 암호화되어 저장되고 인증 요청에 사용되는 Base64로 인코딩된 blob입니다. 그러나 이것이 blob의 모습입니다.<br> 고객 키를 나타내는 고유 식별자<br>예: a70d4d53eefbd781ce7ad6a6495c65eb15e74f1f |

**장치 데이터 예**

다음은 Google에서 온 JSON 장치 메시지의 예입니다.



```
'{
  "name": "enterprises/LC02dhxx1r/devices/3195483be017acdc",
  "userId": "114223373813435875042",
  "adminType": "DEVICE_OWNER",
  "state": "ACTIVE",
  "appliedState": "ACTIVE",
  "policyCompliant": true,
  "enrollmentTime": "2017-10-06T15:17:41.702Z",
  "lastStatusReportTime": "2017-10-06T15:18:10.325Z",
  "lastPolicyComplianceReportTime": "2017-10-06T15:18:11.665Z",
  "lastPolicySyncTime": "2017-10-06T15:18:07.852Z",
  "appliedPolicyVersion": "2",
  "apiLevel": 26,
  "enrollmentTokenData": "brew 30 day token",
  "enrollmentTokenId": "yXdtW0_0L7c7Yo9DtRhEfPi3PcMqTorF3V1bTAw_eRs",
  "softwareInfo": {
    "androidVersion": "8.0.0",
    "cloudDpcVersionCode": 55314,
    "cloudDpcVersionName": "bv00553-rc14",
    "androidBuildNumber": "OPR4.170623.009",
    "deviceKernelVersion": "3.10.73-ga51b1600b7f8",
    "bootloaderVersion": "BHZ21c",
    "androidBuildTime": "2017-08-28T18:57:48Z",
    "securityPatchLevel": "2017-10-05",
    "androidBuildType": "user",
    "buildUser": "android-build"
  },
  "hardwareInfo": {
    "brand": "google",
    "hardware": "bullhead",
    "deviceBasebandVersion": "M8994F-2.6.39.3.03",
    "manufacturer": "LGE",
    "serialNumber": "01ed07873b3c20cd",
    "model": "Nexus 5X",
    "batteryShutdownTemperatures": [60.0],
    "batteryThrottlingTemperatures": [-3.4028235E38],
    "cpuShutdownTemperatures": [115.0, 115.0, 115.0, 115.0, 115.0, 115.0],
    "cpuThrottlingTemperatures": [60.0, 60.0, 60.0, 60.0, 60.0, 60.0],
    "gpuShutdownTemperatures": [-3.4028235E38],
    "gpuThrottlingTemperatures": [-3.4028235E38],
    "skinShutdownTemperatures": [-3.4028235E38],
    "skinThrottlingTemperatures": [37.0]
  },
  "displays": [{
    "name": "Built-in Screen",
    "refreshRate": 60,
    "state": "ON",
    "width": 1080,
    "height": 1920,
    "density": 420
  }],
  "appliedPolicyName": "enterprises/LC02dhxx1r/policies/default",
  "networkInfo": {
    "imei": "353626070676775",
    "wifiMacAddress": "02:00:00:00:00:00"
  },
  "memoryInfo": {
    "totalRam": "1902936064",
    "totalInternalStorage": "3169611776"
  },
  "memoryEvents": [{
    "eventType": "EXTERNAL_STORAGE_DETECTED",
    "createTime": "2017-10-06T15:18:09.959Z",
    "byteCount": "26720919552"
  }],
  "powerManagementEvents": [{
    "eventType": "BATTERY_LEVEL_COLLECTED",
    "createTime": "2017-10-06T15:18:09.939Z",
    "batteryLevel": 95.0
  }],
  "userName": "enterprises/LC02dhxx1r/users/114223373813435875042",
  "enrollmentTokenName": "enterprises/LC02dhxx1r/enrollmentTokens/yXdtW0_0L7c7Yo9DtRhEfPi3PcMqTorF3V1bTAw_eRs"
}'
```

Microsoft Intune으로 Android 장치 관리의 사용을 중단하고 데이터를 삭제하려면 Microsoft Intune Android 장치 관리를 사용하지 않을 뿐 아니라 Google 계정도 삭제해야 합니다. 계정 관리를 수행하는 방법은 Google 계정을 참조하세요.


