---
title: "Windows Holographic for Business에 대한 Microsoft Intune 장치 제한 설정"
titleSuffix: 
description: "Windows Holographic for Business를 실행하는 장치에서 장치 설정 및 기능을 제어하는 데 사용할 수 있는 Intune 설정을 알아봅니다."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 3/6/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9acce571330a754de85b65caf8ec71912fd36a69
ms.sourcegitcommit: e30fb2375fb79f67e5c1e4ed7b2c21fb9ca80c59
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2018
---
# <a name="microsoft-intune-windows-holographic-for-business-device-restriction-settings"></a>Microsoft Intune Windows Holographic for Business 장치 제한 설정

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

다음과 같은 장치 제한 설정은 Microsoft Hololens와 같은 Windows Holographic for Business를 실행하는 장치에서 지원됩니다.

## <a name="general"></a>일반

- **수동 등록 취소** - 장치에서 회사 계정을 수동으로 삭제할 수 있습니다.
- **Cortana** - Cortana 음성 도우미를 사용하거나 사용하지 않도록 설정합니다.
- **지리적 위치** - 장치에서 위치 서비스 정보를 사용할 수 있는지 여부를 지정합니다.



## <a name="password"></a>암호
-   **암호** - 최종 사용자에게 장치에 액세스하려면 암호를 입력하도록 요구합니다.
    -   **장치가 유휴 상태에서 되돌아올 때 암호 요구** - 사용자가 장치 잠금을 해제하기 위해 암호를 입력해야 할지 여부를 지정합니다.



## <a name="app-store"></a>앱 스토어

-   **스토어에서 앱 자동 업데이트** - Microsoft 스토어에서 설치된 앱이 자동으로 업데이트되게 합니다.
-   **신뢰할 수 있는 앱 설치** - 신뢰할 수 있는 인증서로 서명된 앱을 테스트용으로 로드할 수 있습니다.
-   **개발자의 잠금 해제** - Windows 개발자 설정을 허용합니다(예: 테스트용으로 로드된 앱을 최종 사용자가 수정하도록 허용).

## <a name="edge-browser"></a>Microsoft Edge 브라우저

-   **Microsoft Edge 브라우저** - 장치에서 Edge 웹 브라우저 사용을 허용합니다.
-   **쿠키** - 브라우저에서 장치에 인터넷 쿠키를 저장할 수 있도록 합니다.
-   **팝업** - 브라우저에서 팝업 창을 차단합니다(Windows 10 Desktop에만 적용).
-   **검색 제안** - 검색 구문을 입력하면 검색 엔진에서 사이트를 제안할 수 있습니다.
-   **암호 관리자** - Edge 암호 관리자 기능을 사용하거나 사용하지 않습니다.
- **추적 방지 헤더 보내기** - 사용자가 방문하는 웹 사이트에 Do Not Track 헤더를 보내도록 Microsoft Edge 브라우저를 구성합니다

## <a name="windows-defender-smart-screen"></a>Windows Defender Smart Screen

- **Microsoft Edge용 SmartScreen** - 사이트 및 파일 다운로드에 액세스하는 데 Edge SmartScreen을 사용합니다.

## <a name="search"></a>검색
- **위치 검색** - 검색에서 위치를 사용할 수 있는지를 지정합니다. 정보


## <a name="cloud-and-storage"></a>클라우드 및 저장소
-   **Microsoft 계정** - 사용자가 Microsoft 계정을 장치와 연결하도록 허용합니다.

## <a name="cellular-and-connectivity"></a>셀룰러 및 연결

-   **Bluetooth** - 사용자가 장치에서 Bluetooth를 설정하고 구성할 수 있는지 여부를 제어합니다.
-   **Bluetooth 검색 기능** - Bluetooth를 사용하는 다른 장치에서 이 장치를 검색하도록 허용합니다.
-   **Bluetooth 광고** - 장치에서 Bluetooth를 통해 광고를 수신하도록 허용합니다.

## <a name="control-panel-and-settings"></a>제어판 및 설정

- **시스템 시간 수정** - 최종 사용자가 장치 날짜 및 시간을 변경할 수 없습니다.

## <a name="reporting-and-telemetry"></a>보고 및 원격 분석

- **사용 데이터 공유** - 진단 데이터 제출 수준을 선택합니다.