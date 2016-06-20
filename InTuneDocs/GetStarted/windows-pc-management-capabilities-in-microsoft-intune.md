---
# required metadata

title: Windows PC 관리 기능 | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 77fa5c66-a87c-47df-964c-800eea509b33

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: owenyen
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Windows PC 관리 기능(Microsoft Intune PC 클라이언트를 사용한)
대부분의 시나리오에서, Microsoft Intune을 통해 장치를 등록하며, 이렇게 하면 Intune PC 클라이언트보다 훨씬 더 많은 기능이 제공됩니다. 하지만, Intune PC 클라이언트를 사용하여 PC를 관리할 수도 있으며, 다음과 같은 기능이 제공됩니다.

-   **소프트웨어 업데이트 관리** - PC를 최신 상태로 유지하고 업데이트 적용 시기를 관리할 수 있습니다.

-   **Windows 방화벽 정책** - 이 정책을 통해 회사에서 사용하는 PC 중에 Windows 방화벽이 비활성화되거나 부적절하게 구성된 PC가 없는지를 확인할 수 있습니다.

-   **맬웨어 방지 보호** - Intune에 포함된 Endpoint Protection을 사용하면 PC를 맬웨어로부터 보호할 수 있습니다.

-   **원격 지원** - Intune을 통해 IT 지원 직원에게 문의하면 해당 직원이 Intune에 포함된 원격 데스크톱 기능을 사용하여 도움을 줄 수 있습니다<!--- (requires TeamViewer software)--->.

-   **소프트웨어 라이선스 관리** - 사용 가능한 소프트웨어 라이선스 수와 사용 가능한 라이선스 중 현재 사용 중인 라이선스 수를 추적합니다.
-   **앱 배포** - 관리하는 PC에 소프트웨어를 배포합니다. 일부 앱 관리 기능은 클라이언트 소프트웨어를 사용하여 PC를 관리하면 사용할 수 없습니다.


## 운영 체제 요구 사항
Intune은 다음 Windows 버전(x86 및 x64)을 실행하는 PC를 관리할 수 있습니다.


-   **Windows Vista** - Business, Enterprise 및 Ultimate 버전

-   **Windows 7** - Pro, Enterprise 및 Ultimate 버전(서비스 팩 미포함 또는 SP1)

-   **Windows 8** - Pro 및 Enterprise 버전

-   **Windows 8.1** - Pro 및 Enterprise 버전

- **Windows 10** - Home, Pro, Education 및 Enterprise 버전


## 최소 하드웨어 요구 사항
다음은 Intune PC 클라이언트를 설치하기 위한 최소 하드웨어 요구 사항입니다.

|요구 사항|세부 정보|
|---------------|--------------------|
|네트워크|클라이언트를 설치하려면 PC가 인터넷에 연결되어 있어야 합니다.|
|프로세서 및 메모리|PC 운영 체제의 프로세서 및 RAM 요구 사항을 참조하세요.|
|디스크 공간|클라이언트 소프트웨어를 설치하려면 먼저 200MB의 사용 가능한 디스크 공간이 필요합니다.|

## 자세한 요구 사항
다음은 Intune PC 클라이언트를 설치하기 위한 소프트웨어 요구 사항입니다.

|요구 사항|세부 정보|
|---------------|--------------------|
|관리자 권한|클라이언트 소프트웨어를 설치하는 계정에는 해당 PC에 대한 로컬 관리자 권한이 있어야 합니다.|
|Windows Installer 3.1|PC에 최소 Windows Installer 3.1이 설치되어 있어야 합니다.|
|호환되지 않는 클라이언트 소프트웨어를 제거합니다.|Intune PC 클라이언트 소프트웨어를 설치하려면 먼저 해당 PC에서 다음 클라이언트 소프트웨어를 제거해야 합니다.<br /><br />-   Configuration Manager의 모든 버전<br />-   Microsoft SMS(Systems Management Server)의 모든 버전|

### 참고 항목
[Microsoft Intune의 모바일 장치 관리 기능](./mobile-device-management-capabilities-in-microsoft-intune.md)


<!--HONumber=Jun16_HO2-->


