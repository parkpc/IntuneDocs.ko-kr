---
title: "Windows 정책 설정"
description: "Intune Windows 일반 구성 정책(Windows 8.1 이상)을 사용하여 등록된 Windows 8.1 및 Windows 8 장치에 대한 설정을 구성합니다."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 10/11/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6982a2bc-aafa-475a-9236-4840b709e5a1
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9fa8d8454e9d22b2d3c36cd6449805d709c34ffa
ms.sourcegitcommit: 3b397b1dcb780e2f82a3d8fba693773f1a9fcde1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2017
---
# <a name="windows-policy-settings-in-microsoft-intune"></a>Microsoft Intune의 Windows 정책 설정

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune **Windows 일반 구성 정책(Windows 8.1 이상)**을 사용하여 등록된 Windows 8, Windows 8.1 및 Windows RT 8.1 장치에 대한 다음 설정을 구성합니다.

## <a name="applicability-settings"></a>적용 가능성 설정

|설정 이름|세부 정보|
|----------------|----------------------------------|
|**Windows 10에 모든 구성 적용**|이 정책의 설정을 Windows 8 및 Windows 8.1 장치 외에도 Windows 10 장치에 적용할 수 있습니다.|

## <a name="security-settings"></a>보안 설정

|설정 이름|세부 정보|
|----------------|------|
|**필수 암호 유형**|숫자만 또는 영숫자와 같이 필요한 암호의 유형을 지정합니다.|
|**필수 암호 유형 - 최소 문자 집합 개수**|암호에 포함되어야 하는 다양한 문자 집합 수를 지정합니다. 소문자, 대문자, 숫자, 기호에 해당하는 4가지 문자 집합을 사용할 수 있습니다. 그러나 이 설정에서는 iOS 장치의 경우에는 암호에 포함되어야 할 기호의 수를 지정합니다.|
|**최소 암호 길이**|암호에 대한 최소 문자 길이를 구성합니다.|
|**장치를 초기화하기 전까지 허용되는 로그인 반복 오류 횟수**|이 횟수만큼 로그인에 실패하면 장치를 초기화합니다.|
|**화면이 잠기기 전까지 비활성 시간(분)**|잠금을 해제하기 위해 암호가 필요하게 되기까지 장치가 유휴 상태여야 하는 시간(분)을 지정합니다.|
|**암호 만료(일)**|장치 암호를 변경해야 할 때까지의 기간(일)을 지정합니다.|
|**암호 기록 기억**|사용자가 이전에 사용한 암호를 구성할 수 있을지 여부를 지정합니다.|
|**암호 기록 기억** – **이전 암호 다시 사용 안 함**|장치에 기억될 이전에 사용된 암호의 수를 지정합니다.|
|**사진 암호 및 PIN 허용**|그림 암호 및 PIN을 사용하도록 설정합니다. 그림 암호를 허용하면, 그림에 제스처를 사용하여 로그인할 수 있습니다. PIN을 허용하면, 4자리 코드를 사용하여 빠르게 로그인할 수 있습니다.|

## <a name="encryption-settings"></a>암호화 설정

|설정 이름|세부 정보|
|----------------|-----|
|**모바일 장치 암호화 필요**<sup>1</sup>|장치의 파일을 암호화해야 합니다.|
<sup>1</sup> Windows 8.1을 실행하는 장치에 대한 추가 정보

-   Windows 8.1을 실행하는 장치에 암호화를 적용하려면 각 장치에 [Windows용 December 2014 MDM 클라이언트 업데이트](http://support.microsoft.com/kb/3013816) 를 설치해야 합니다.

-   Windows 8.1 장치에 대해 이 설정을 사용하려면 장치의 모든 사용자가 Microsoft 계정을 가지고 있어야 합니다.

-   암호화가 작동하려면 장치가 Microsoft [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) 하드웨어 인증 요구 사항을 만족해야 합니다.

-   장치에 암호화를 적용하는 경우, 복구 키는 자신의 OneDrive 계정에서 액세스한 Microsoft 계정에서만 액세스할 수 있습니다. 사용자를 대신하여 이 키를 복구할 수 없습니다.

## <a name="malware-settings"></a>맬웨어 설정

|설정 이름|세부 정보|
|----------------|-----|
|**네트워크 방화벽 필요**|Windows 방화벽이 켜져 있어야 합니다.|
|**SmartScreen 사용**|Windows SmartScreen을 사용해야 합니다.|

## <a name="system-settings"></a>시스템 설정

|설정 이름|세부 정보|
|----------------|-------|
|**자동 업데이트 필요**|장치에 자동 업데이트 설정을 켭니다.|
|**자동 업데이트 필요 - 자동으로 설치하기 위한 업데이트의 최소 분류**|자동으로 설치될 업데이트의 분류를 선택합니다.<br /><br />-   **중요** - 중요로 분류된 모든 업데이트를 설치합니다.<br />-   **권장** – 중요 또는 권장으로 분류된 모든 업데이트를 설치합니다.|
|**사용자 계정 컨트롤**|장치에 UAC(사용자 계정 컨트롤)를 사용해야 합니다.|
|**진단 데이터 제출 허용**|장치에서 Microsoft에 진단 정보를 제출할 수 있습니다.|


## <a name="cloud-settings--documents-and-data"></a>클라우드 설정 – 문서 및 데이터

|설정 이름|세부 정보|
|----------------|------|
|**작업 폴더 URL**|문서를 장치 간에 동기화될 수 있도록 작업 폴더의 URL을 설정합니다.|

## <a name="email-settings"></a>전자 메일 설정

|설정 이름|세부 정보|
|----------------|-----|
|**Windows Mail 응용 프로그램에서 Microsoft 계정을 옵션으로 설정**|Microsoft 계정 없이 Windows Mail 응용 프로그램에 대한 액세스를 사용하도록 설정합니다.|

## <a name="application-settings---browser"></a>응용 프로그램 설정 - 브라우저

|설정 이름|세부 정보|
|----------------|-----|
|**자동 채우기 허용**|사용자가 브라우저에서 자동 완성 설정을 변경할 수 있습니다.|
|**팝업 차단 허용**|브라우저 팝업 차단을 사용하거나 사용하지 않도록 설정합니다.|
|**플러그 인 허용**|사용자가 Internet Explorer에 플러그 인을 추가할 수 있습니다.|
|**액티브 스크립팅 허용**|브라우저에서 ActiveX 스크립트와 같은 스크립트를 실행할 수 있습니다.|
|**사기 경고 허용**|사기성일 수 있는 웹 사이트 경고를 사용하거나 사용하지 않도록 설정합니다.|
|**한 단어 입력으로 인트라넷 사이트 허용**|한 단어를 사용하여 Internet Explorer를 ‘Bing’ 등과 같은 웹 사이트로 디렉션할 수 있습니다.|
|**인트라넷 네트워크의 자동 검색 허용**|Internet Explorer에서 인트라넷 사이트의 보안을 구성하도록 돕습니다.|
|**인터넷의 보안 수준**|인터넷 사이트에 대한 Internet Explorer 보안 수준을 설정합니다.|
|**인트라넷의 보안 수준**|인트라넷 사이트에 대한 Internet Explorer 보안 수준을 설정합니다.|
|**신뢰할 수 있는 사이트의 보안 수준**|신뢰할 수 있는 사이트 영역에 대한 보안 수준을 구성합니다.|
|**제한된 사이트의 보안 수준**|제한된 사이트 영역에 대한 보안 수준을 구성합니다.|
|**Do Not Track 헤더 보내기**|Internet Explorer에서 방문한 사이트에 Do Not Track 헤더를 보냅니다.|
|**엔터프라이즈 모드 메뉴 액세스 허용**|사용자가 Internet Explorer에서 엔터프라이즈 모드 메뉴에 액세스하도록 허용합니다.<br>이 설정을 선택하면 사용자가 엔터프라이즈 모드 액세스를 켜 놓은 웹 사이트를 보여주는 보고서에 대한 URL을 포함하는 **로깅 보고서 위치**를 지정할 수 있습니다.|
|**엔터프라이즈 모드 사이트 목록 위치**|엔터프라이즈 모드가 활성화된 경우 이 모드를 사용할 웹 사이트 목록의 위치를 지정합니다.|

## <a name="device-capabilities-settings---cellular"></a>장치 기능 설정 - 셀룰러

|설정 이름|세부 정보|
|----------------|----|
|**데이터 로밍 허용**|장치가 셀룰러 네트워크에 있을 때 데이터 로밍을 사용하도록 설정합니다.|



### <a name="see-also"></a>참고 항목
[Microsoft Intune 정책을 사용하여 장치의 설정 및 기능 관리](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
