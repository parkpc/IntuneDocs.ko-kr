---
title: "Intune PC 소프트웨어 클라이언트 기능 | Microsoft Intune"
description: "Intune 소프트웨어 클라이언트로 Windows PC를 관리하는 경우 Intune의 기능에 대해 알아봅니다."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 08/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 77fa5c66-a87c-47df-964c-800eea509b33
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 12d75bc67fd61a2e807eed2543f21b756a65a900
ms.openlocfilehash: 3066ef98c0a1df6fc0ae455860635e7c12f82c4f


---

# Intune 소프트웨어 클라이언트를 사용하는 경우 Windows PC 관리 기능)
대부분의 시나리오에서 Microsoft Intune에 장치를 등록하면 훨씬 더 많은 기능이 제공됩니다. 그러나 Intune 소프트웨어 클라이언트를 사용하여 PC를 관리할 수도 있으며, 이 경우 다음과 같은 기능이 제공됩니다.

-   **소프트웨어 업데이트 관리** - PC를 최신 상태로 유지하고 업데이트 적용 시기를 결정할 수 있습니다.

-   **Windows 방화벽 정책** - 이 정책을 통해 회사에서 사용하는 PC 중에 Windows 방화벽이 비활성화되거나 부적절하게 구성된 PC가 없는지를 확인할 수 있습니다.

-   **맬웨어 방지 보호** - Intune에 포함된 Endpoint Protection을 사용하면 PC를 맬웨어로부터 보호할 수 있습니다.

-   **원격 지원** - Intune을 통해 IT 지원 직원에게 문의하면 해당 직원이 Intune에 포함된 원격 데스크톱 기능을 사용하여 도움을 줄 수 있습니다(TeamViewer 소프트웨어 필요).

-   **소프트웨어 라이선스 관리** - 사용 가능한 소프트웨어 라이선스 수와 사용 가능한 라이선스 중 현재 사용 중인 라이선스 수를 추적합니다.
-   **앱 배포** - 관리하는 PC에 소프트웨어를 배포합니다. 소프트웨어 클라이언트를 사용하여 PC를 관리하는 경우 일부 앱 관리 기능은 사용할 수 없습니다.


Intune에서는 소프트웨어 클라이언트를 최대 7,000대의 Windows 장치에 설치할 수 있도록 지원합니다.

## 운영 체제 요구 사항
Intune은 다음 Windows 버전(32비트 및 64비트)을 실행하는 PC를 관리할 수 있습니다.


-   **Windows Vista** - Business, Enterprise 및 Ultimate 버전

-   **Windows 7** - Pro, Enterprise 및 Ultimate 버전(서비스 팩 미포함 또는 SP1)

-   **Windows 8** - Pro 및 Enterprise 버전

-   **Windows 8.1** - Pro 및 Enterprise 버전

- **Windows 10** - Pro, Education 및 Enterprise 버전


## 최소 하드웨어 요구 사항
다음은 Intune 소프트웨어 클라이언트를 설치하기 위한 하드웨어 최소 요구 사항입니다.

|요구 사항|세부 정보|
|---------------|--------------------|
|네트워크|클라이언트를 설치하려면 PC가 인터넷에 연결되어 있어야 합니다.|
|프로세서 및 메모리|PC 운영 체제의 프로세서 및 RAM 요구 사항을 참조하세요.|
|디스크 공간|클라이언트 소프트웨어를 설치하려면 먼저 200MB의 사용 가능한 디스크 공간이 필요합니다.|

## 자세한 요구 사항
다음은 Intune 소프트웨어 클라이언트를 설치하기 위한 소프트웨어 요구 사항입니다.

|요구 사항|세부 정보|
|---------------|--------------------|
|관리자 권한|클라이언트 소프트웨어를 설치하는 계정에는 해당 PC에 대한 로컬 관리자 권한이 있어야 합니다.|
|Windows Installer 3.1|PC에 최소 Windows Installer 3.1이 설치되어 있어야 합니다.|
|호환되지 않는 클라이언트 소프트웨어를 제거합니다.|Intune PC 클라이언트 소프트웨어를 설치하려면 먼저 해당 PC에서 다음 클라이언트 소프트웨어를 제거해야 합니다.<br /><br />-   Configuration Manager의 모든 버전<br />-   Microsoft SMS(Systems Management Server)의 모든 버전|

### 참고 항목
[Microsoft Intune의 등록된 장치 관리 기능](./mobile-device-management-capabilities-in-microsoft-intune.md)



<!--HONumber=Aug16_HO4-->

