---
# required metadata

title: 컴퓨터가 이미 등록되어 있음 | Microsoft Intune
description:
keywords:
author: staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8d3a40f5-99e9-48dc-9706-f7a3a23e5704

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# 컴퓨터가 이미 등록되어 있음
Intune 클라이언트 소프트웨어의 설치 프로그램을 실행했으므로 이 페이지가 표시됩니다. 그러나 소프트웨어는 컴퓨터에 이미 설치되어 있으므로 설치를 계속할 수 없습니다.

그 이유는 다음 중 하나일 수 있습니다.

-   클라이언트 소프트웨어가 이전에 설치되었는데 설치 프로그램이 다시 실행되었습니다.

-   IT 관리자가 Intune에서 장치 사용을 중지한 후에 컴퓨터에서 설치 프로그램이 실행되었습니다. 장치 사용이 중지된 후 컴퓨터에서 클라이언트 소프트웨어를 제거하는 데 몇 시간 정도 걸릴 수 있습니다.

-   설치 프로그램이 최근에 있었던 클라이언트 소프트웨어의 설치 또는 제거 실패를 감지했습니다.

## 설치 프로그램이 컴퓨터에 설치하는 프로그램
설치 프로그램은 Intune 클라이언트를 설치합니다. 설치 프로그램이 완료되면, 클라이언트 소프트웨어는 백그라운드에서 계속 실행되며 Intune에서 사용할 컴퓨터를 계속 구성합니다. 이 프로세스는 완료하는 데 다소 시간이 걸릴 수 있으며 다음이 포함됩니다.

-   Intune에 컴퓨터 등록

-   컴퓨터 하드웨어 및 설치된 소프트웨어에 대한 인벤토리 제출

-   Endpoint Protection 설치를 포함하여 Intune 정책 구성(구성된 경우)

-   Intune Center 설치

Intune Center가 설치되면, 이를 사용하여 컴퓨터를 회사 계정에 연결할 수 있는 회사 포털에 액세스할 수 있습니다.

## Microsoft Intune Center
Intune Center는 컴퓨터에서 클라이언트 소프트웨어를 성공적으로 설치하고 컴퓨터를 Intune에 등록한 후 컴퓨터에 앱으로 설치합니다. Intune Center를 사용하여 다음을 수행할 수 있습니다.

-   **회사 포털에서 응용 프로그램 가져오기** - IT 관리자가 배포한 앱을 찾아서 설치합니다. 새로 등록된 컴퓨터에서 회사 포털에 처음 로그인하는 경우 해당 컴퓨터를 회사 계정과 연결하는 옵션이 제공됩니다.

-   **소프트웨어 업데이트 확인** – Intune 관리자가 배포한 소프트웨어 업데이트를 찾습니다.

-   **컴퓨터의 Endpoint Protection 검색 시작** – 컴퓨터에서 악성 소프트웨어 검색을 시작할 수 있습니다.

-   **원격 지원 요청** – 이 옵션은 컴퓨터 운영 체제에서 원격 지원을 지원할 때만 사용할 수 있습니다.

## 클라이언트 소프트웨어가 설치 또는 제거되었는지 확인
**클라이언트가 설치되었는지 확인:**
컴퓨터에서 다음 앱을 사용할 수 있으면 Intune 클라이언트 설치가 완료된 것입니다.

-   **Intune Center**

-   **Intune Endpoint Protection**(IT 관리자가 Endpoint Protection을 사용하도록 설정한 경우)

작업 관리자 사용에 익숙한 경우 실행 중인 Intune 클라이언트 서비스를 검색할 수 있습니다.

-   **OmcSvc**

**클라이언트가 제거되었는지 확인:**
Intune 클라이언트가 컴퓨터에서 제거되면 Intune Center를 비롯하여 클라이언트가 설치되었을 때 설치된 앱이 제거됩니다.

Intune 클라이언트 서비스 **OmcSvc**가 제거됩니다.

## 컴퓨터에서 클라이언트 소프트웨어를 제거하는 방법
기본적으로 IT 관리자가 Intune 관리 콘솔에서 컴퓨터의 사용을 중지하고 몇 시간 후에 Intune 클라이언트 소프트웨어가 제거됩니다.

컴퓨터에서 Intune 클라이언트 소프트웨어를 수동으로 제거하려면 다음 단계를 사용하여 강제로 제거할 수 있습니다.

1.  컴퓨터의 관리자 모드에서 명령 프롬프트를 엽니다.

2.  **%programfiles%\Microsoft\OnlineManagement\Common** 폴더로 이동합니다.

3.  **ProvisioningUtil.exe /UninstallAgents /MicrosoftIntune** 명령을 실행합니다.

이 명령은 클라이언트 소프트웨어의 제거를 예약합니다.



<!--HONumber=May16_HO1-->


