---
title: "Windows 8.1에 대한 Intune 장치 제한 설정"
titleSuffix: Azure portal
description: "Windows 8.1 장치에서 장치 설정 및 기능을 제어하는 데 사용할 수 있는 Intune 설정을 알아봅니다.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fe5785e9-8d35-4ad7-95e8-d50f8d87154a
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d1b4745e1d05d2790de71b947eafc3e6cc1a7a43
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/09/2017
---
# <a name="windows-81-and-later-device-restriction-settings-in-microsoft-intune"></a>Microsoft Intune에서 Windows 8.1 이상 장치 제한 설정

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="general"></a>일반

-   **진단 데이터 제출** - 장치에서 Microsoft에 진단 정보를 제출할 수 있습니다.
-   **방화벽** - Windows 방화벽이 켜져 있어야 합니다.
-   **사용자 계정 컨트롤** - 장치에 UAC(사용자 계정 컨트롤)를 사용해야 합니다.

## <a name="password"></a>암호
-   **필수 암호 유형** - 최종 사용자에게 장치에 액세스하려면 암호를 입력하도록 요구합니다.
-   **최소 암호 길이** - 암호에 대한 최소 문자 길이를 구성합니다.
-   **장치를 초기화하기 전 로그인 오류 발생 횟수** - 이 횟수만큼 로그인에 실패하면 장치를 초기화합니다.
-   **화면이 잠기기 전까지 최대 비활성 시간(분)** - 잠금을 해제하기 위해 암호가 필요하게 되기까지 장치가 유휴 상태여야 하는 시간(분)을 지정합니다.
-   **암호 만료(일)** - 장치 암호를 변경해야 할 때까지의 기간(일)을 지정합니다.
-   **이전 암호 다시 사용 방지** - 사용자가 이전에 사용한 암호를 구성할 수 있을지 여부를 지정합니다.
-   **사진 암호 및 PIN** - 사진 암호 및 PIN을 사용하도록 설정합니다. 그림 암호를 허용하면, 그림에 제스처를 사용하여 로그인할 수 있습니다. PIN을 허용하면, 4자리 코드를 사용하여 빠르게 로그인할 수 있습니다.
-   **암호화** - 장치의 파일을 암호화해야 합니다.<br>Windows 8.1을 실행하는 장치에 암호화를 적용하려면 각 장치에 [Windows용 December 2014 MDM 클라이언트 업데이트](https://support.microsoft.com/kb/3013816) 를 설치해야 합니다.
Windows 8.1 장치에 대해 이 설정을 사용하려면 장치의 모든 사용자가 Microsoft 계정을 가지고 있어야 합니다.
암호화가 작동하려면 장치가 [Microsoft InstantGo](https://blogs.windows.com/windowsexperience/2014/06/19/instantgo-a-better-way-to-sleep/#IBHULcTfI4PokO8X.97) 하드웨어 인증 요구 사항을 만족해야 합니다.
장치에 암호화를 적용하는 경우, 복구 키는 자신의 OneDrive 계정에서 액세스한 Microsoft 계정에서만 액세스할 수 있습니다. 사용자를 대신하여 이 키를 복구할 수 없습니다.     



## <a name="browser"></a>브라우저
-   **자동 채우기** - 사용자가 브라우저에서 자동 완성 설정을 변경할 수 있습니다.
-   **사기 경고** - 사기성일 수 있는 웹 사이트 경고를 사용하거나 사용하지 않도록 설정합니다.
-   **SmartScreen** - 사기성일 수 있는 웹 사이트 경고를 사용하거나 사용하지 않도록 설정합니다.
-   **JavaScript** - 브라우저에서 Java 스크립트와 같은 스크립트를 실행할 수 있습니다.
-   **팝업** - 브라우저 팝업 차단을 사용하거나 사용하지 않도록 설정합니다.
-   **Do Not Track 헤더 보내기** - Internet Explorer에서 방문한 사이트에 Do Not Track 헤더를 보냅니다.
-   **플러그 인** - 사용자가 Internet Explorer에 플러그 인을 추가할 수 있습니다.
-   **인트라넷 사이트에서 한 단어 입력** - 한 단어를 사용하여 Internet Explorer를 ‘Bing’ 등과 같은 웹 사이트로 디렉션할 수 있습니다.
-   **인트라넷 사이트 자동 검색** - Internet Explorer에서 인트라넷 사이트의 보안을 구성하도록 돕습니다.
-   **인터넷 보안 수준** - 인터넷 사이트에 대한 Internet Explorer 보안 수준을 설정합니다.
-   **인트라넷 보안 수준** - 인트라넷 사이트에 대한 Internet Explorer 보안 수준을 설정합니다.
-   **신뢰할 수 있는 사이트 보안 수준** - 신뢰할 수 있는 사이트 영역에 대한 보안 수준을 구성합니다.
-   **제한된 사이트에 대한 높은 수준의 보안** - 제한된 사이트 영역에 대한 보안 수준을 구성합니다.
-   **엔터프라이즈 모드 메뉴 액세스** - 사용자가 Internet Explorer에서 엔터프라이즈 모드 메뉴에 액세스하도록 허용합니다.
이 설정을 선택하면 사용자가 엔터프라이즈 모드 액세스를 켜 놓은 웹 사이트를 보여주는 보고서에 대한 URL을 포함하는 **로깅 보고서 위치**를 지정할 수 있습니다.
-   **엔터프라이즈 모드 사이트 목록 위치** – 엔터프라이즈 모드가 활성화된 경우 이 모드를 사용할 웹 사이트 목록의 위치를 지정합니다.

## <a name="cellular"></a>셀룰러
-   **데이터 로밍** - 장치가 셀룰러 네트워크에 있을 때 데이터 로밍을 사용하도록 설정합니다.

## <a name="cloud-and-storage"></a>클라우드 및 저장소
-   **작업 폴더 URL** - 문서를 장치 간에 동기화될 수 있도록 작업 폴더의 URL을 설정합니다.
-   **Microsoft 계정이 없는 Windows Mail 앱 액세스** - Microsoft 계정 없이 Windows Mail 응용 프로그램에 대한 액세스를 사용하도록 설정합니다.    
