---
title: "Windows 10 정책 설정 | Microsoft Intune"
description: 
keywords: 
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00a602d9-b339-4fd8-ab70-defbf6686855
ms.reviewer: heenamac
ms.suite: ems
ms.sourcegitcommit: 1cccafa5f740bad50779ae36c899fd23ee7dc5f3
ms.openlocfilehash: 70347776f72a3534a4c384957aef01a909767b99


---

# Microsoft Intune의 Windows 10 정책 설정

이 항목에 나열된 정책 설정을 사용하면 등록된 Windows 10 Desktop 및 Windows 10 Mobile 장치의 설정을 구성하는 데 도움이 됩니다.

## 일반 구성 정책 설정

Windows 10용 Microsoft Intune **일반 구성 정책**을 사용하여, 등록된 Windows 10 Desktop 및 Windows 10 Mobile 장치에 대한 일반 설정을 구성합니다. 이 정책은 Intune 클라이언트 소프트웨어로 Windows 10 PC를 관리하는 경우에는 사용할 수 없습니다.


### 암호

|설정 이름|세부 정보|
|----------------|----------------------|
|**장치의 잠금을 해제하는 데 암호 필요**|지원되는 장치에는 암호가 필요합니다.|
|**필수 암호 유형**|영숫자만 또는 숫자와 같이 필요한 암호의 유형을 지정합니다.|
|**필수 암호 유형** - **최소 문자 집합 개수**|소문자, 대문자, 숫자, 기호에 해당하는 4가지 문자 집합을 사용할 수 있습니다. 이 설정은 암호에 포함되어야 하는 다양한 문자 집합 수를 지정합니다.|
|**최소 암호 길이**|장치 암호에 포함해야 하는 최소 문자 수를 지정합니다.<br>(Windows 10 Mobile에만 해당)|
|**장치를 초기화하기 전까지 허용되는 로그인 반복 오류 횟수**|이 횟수만큼 로그인에 실패하면 장치를 초기화합니다.|
|**화면이 잠기기 전까지 비활성 시간(분)**|화면이 잠기기 전에 장치가 유휴 상태여야 하는 기간을 지정합니다.|
|**암호 만료(일)**|장치 암호를 변경해야 하는 간격을 지정합니다.|
|**암호 기록 기억**|최종 사용자가 이전에 사용했던 암호를 만들지 못하도록 제한할지 여부를 지정합니다.|
|**암호 기록 기억** - **이전 암호 다시 사용 안 함**|장치에 기억될 이전에 사용된 암호의 수를 지정합니다.|
|**그림 암호 및 PIN 허용**|그림의 간단한 제스처 또는 간단한 PIN을 사용하여 로그인할 수 있습니다.<br>(Windows 10 Desktop에만 해당)|
|**장치가 유휴 상태에서 되돌아오는 경우 암호 필요**|사용하도록 설정된 경우, 사용자는 유휴 상태에서 장치 잠금을 해제하기 위해 암호를 입력해야 합니다.<br>(Windows 10 Mobile에만 해당)|

### 암호화

|설정 이름|세부 정보|
|----------------|----------------------|
|**모바일 장치 암호화 필요**|대상 장치에서 암호화를 사용하도록 설정<br>(Windows 10 Mobile에만 해당)|

### System (시스템)

|설정 이름|세부 정보|
|----------------|----------------------|
|**화면 캡처 허용**|장치 화면을 이미지로 캡처하도록 허용합니다.<br>(Windows 10 Mobile에만 해당)|
|**수동 등록 취소 허용**|장치에서 회사 계정을 수동으로 삭제할 수 있습니다.|
|**루트 인증서 수동 설치 허용**|사용자가 루트 인증서를 수동으로 설치할 수 있는지 여부를 지정합니다.<br>(Windows 10 Mobile에만 해당)|
|**진단 및 사용 현황 데이터를 Microsoft에 보내도록 허용**|장치에서 Microsoft로 보내는 진단 및 사용 현황 데이터의 양을 결정합니다.<br><br>**없음** - Microsoft로 데이터가 전송되는 데이터가 없습니다.<br>**기본** - 장치에서 제한된 정보만 Microsoft에 전송합니다.<br>**확장됨** - 확장된 진단 데이터를 Microsoft에 전송합니다.<br>**전체(권장됨)** - **확장됨**과 동일한 데이터 외에, 장치 상태에 대한 추가적인 데이터를 전송합니다.|


### 계정 및 동기화

|설정 이름|세부 정보|
|----------------|----------------------|---------------------|
|**Microsoft 계정 허용**|사용자가 Microsoft 계정을 장치와 연결하도록 허용합니다.|
|**Microsoft가 아닌 타사 계정 수동 추가 허용**|사용자가 Microsoft 계정과 연결되지 않은 장치에 전자 메일 계정을 추가하도록 허용합니다.|
|**Microsoft 계정에 대한 설정 동기화 허용**|Microsoft 계정과 연결된 장치 및 앱 설정이 장치 간이 동기화되도록 허용합니다.|

### 전자 메일 설정

|설정 이름|세부 정보|
|----------------|----------------------|---------------------|
|**Windows Mail 응용 프로그램에서 Microsoft 계정을 옵션으로 설정**|Windows Mail의 Microsoft 계정에 대한 요구 사항을 제거하려면 이 옵션을 구성합니다.<br>Windows 10 Desktop에만 해당|



### Microsoft Edge

|설정 이름|세부 정보|
|----------------|----------------------|
|**웹 브라우저 허용**|장치에서 Edge 웹 브라우저 사용을 허용합니다.<br>(Windows 10 Mobile에만 해당)|
|**주소 표시줄에서 검색 제안 허용**|검색 구를 입력할 때 검색 엔진이 사이트를 제안하도록 허용합니다.|
|**인트라넷 트래픽을 Internet Explorer에 전송 허용**|사용자가 Internet Explorer에서 인트라넷 웹 사이트를 열도록 허용합니다.<br>(Windows 10 Desktop에만 해당)|
|**Do Not Track 허용**|사용자가 방문하는 웹 사이트에 Do Not Track 헤더를 보내도록 Edge 브라우저를 구성합니다|
|**SmartScreen 사용**|장치에 SmartScreen 브라우저 설정을 사용합니다.|
|**액티브 스크립팅 허용**|Edge 브라우저에서 JavaScript 같은 스크립트가 실행되도록 허용합니다.|
|**팝업 허용**|브라우저 팝업 차단을 사용하거나 사용하지 않도록 설정합니다.<br>(Windows 10 Desktop에만 해당)|
|**쿠키 허용**|쿠키를 허용하거나 사용하지 않습니다.|
|**자동 채우기 허용**|사용자가 브라우저에서 자동 완성 설정을 변경하도록 허용합니다.<br>(Windows 10 Desktop에만 해당)|
|**암호 관리자 허용**|Edge 암호 관리자 기능을 사용하거나 사용하지 않습니다.|
|**엔터프라이즈 모드 사이트 목록 위치**|엔터프라이즈 모드에서 열 웹 사이트 목록을 찾을 위치를 지정합니다. 사용자는 이 목록을 편집할 수 없습니다.<br>(Windows 10 Desktop에만 해당)|

### 앱

|설정 이름|세부 정보|
|----------------|----------------------|---------------------|
|**앱 스토어 허용**|사용자가 장치에서 앱 스토어에 액세스하도록 허용합니다.<br>(Windows 10 Mobile에만 해당)|



### 셀룰러

|설정 이름|세부 정보|
|----------------|----------------------|---------------------|
|**데이터 로밍 허용**|데이터 액세스 시 네트워크 간 로밍이 가능합니다.|
|**셀룰러에서 VPN 허용**|셀룰러 네트워크에 연결 시 장치가 VPN 연결에 액세스할 수 있을지 여부를 제어합니다.|
|**셀룰러에서 VPN 로밍 허용**|셀룰러 네트워크에 로밍 시 장치가 VPN 연결에 액세스할 수 있을지 여부를 제어합니다.|

### 하드웨어

|설정 이름|세부 정보|
|----------------|----------------------|
|**카메라 허용**|장치 카메라 사용 여부를 지정합니다.|
|**이동식 저장소 허용**|장치에 SD 카드와 같은 외부 저장 장치 사용 여부를 지정합니다.|
|**Wi-Fi 허용**|장치 Wi-Fi 기능을 사용하도록 허용합니다.<br>(Windows 10 Mobile에만 해당)|
|**인터넷 공유 허용**|장치에서 인터넷 연결 공유를 사용하도록 허용합니다.|
|**Wi-Fi 수동 구성 허용**|사용자가 스스로 Wi-Fi 연결을 구성할 수 있을지 또는 Wi-Fi 프로필에 의해 구성되는 연결만 사용할 수 있을지를 제어합니다.<br>(Windows 10 Mobile에만 해당)|
|**무료 Wi-Fi 핫스팟에 자동 연결 허용**|장치가 무료 Wi-Fi 핫스폿에 자동으로 연결되고 연결에 대한 사용 약관을 자동으로 수락하도록 허용합니다.|
|**지리적 위치 허용**|장치에서 위치 서비스 정보를 사용할 수 있는지 여부를 지정합니다.|
|**NFC 허용**|장치가 NFC(근거리 통신) 기능을 사용하도록 허용합니다.|
|**Bluetooth 허용**|장치에서 Bluetooth 기능을 사용할 수 있도록 합니다.|
|**Bluetooth 검색 가능 모드 허용**|Bluetooth를 사용하는 다른 장치에서 이 장치를 검색하도록 허용합니다.|
|**Bluetooth 광고 허용**|장치에서 Bluetooth를 통해 광고를 수신할 수 있도록 허용합니다.|
|**Bluetooth 연결 가능 모드 허용**|**중요:** 이 설정은 Windows 10에서 더 이상 지원되지 않으며 나중에 제거될 예정입니다.|
|**휴대폰 초기화 허용**|사용자가 장치를 출하 시로 초기화할 수 있는지 여부를 제어합니다.|
|**USB 연결 허용**|장치의 USB 연결을 통한 외부 저장 장치 액세스 가능 여부를 제어합니다.|
|**AntiTheft 모드 허용**|Windows Antitheft 모드 사용 여부를 구성합니다.|

### 기능

|설정 이름|세부 정보|
|----------------|----------------------|---------------------|
|**복사 및 붙여넣기 허용**|장치에서 복사 및 붙여넣기 사용을 허용하거나 허용하지 않습니다.<br>(Windows 10 Mobile에만 해당)|
|**음성 녹음 허용**|장치에서 음성 녹음 기능을 허용하거나 허용하지 않습니다.<br>(Windows 10 Mobile에만 해당)|
|**Cortana 허용**|Cortana 음성 지원을 허용하거나 허용하지 않습니다.|
|**알림 센터 알림 허용**|장치 잠금 화면에서 알림 센터 알림을 허용하거나 허용하지 않습니다.<br>(Windows 10 Mobile에만 해당)|

### Defender

모든 설정이 Windows 10 Desktop에만 해당됩니다.

|설정 이름|세부 정보|
|-|-|
|**실시간 모니터링 허용**|맬웨어, 스파이웨어 및 기타 사용자 동의 없이 설치되는 소프트웨어에 대한 실시간 모니터링을 허용합니다.|
|**동작 모니터링 허용**|Defender가 장치에서 특정한 알려진 패턴의 의심스러운 활동을 확인하도록 허용합니다.|
|**네트워크 검사 시스템 사용**|NIS(네트워크 검사 시스템)는 Microsoft Endpoint Protection Center의 알려진 취약한 부분에 대한 서명을 사용하여 네트워크 기반의 익스플로잇으로부터 장치를 보호하고 악의적인 트래픽을 차단하는 데 도움을 줍니다.|
|**모든 다운로드 검색**|Defender가 인터넷에서 다운로드한 모든 파일을 검사할지 여부를 제어합니다.|
|**스크립트 검색 허용**|Defender가 Internet Explorer에 사용되는 스크립트를 검색하도록 허용합니다.|
|**파일 및 프로그램 활동 모니터링**|Defender가 장치의 파일 및 프로그램 활동을 모니터링하도록 허용하려면 이 설정을 사용합니다.|
|**해결된 맬웨어를 추적하는 일 수**|이전에 영향을 받은 장치를 수동으로 확인할 수 있도록 Defender가 지정한 일 수 동안 해결된 맬웨어를 추적하도록 허용합니다. 일 수를 **0**으로 설정하면, 맬웨어가 격리 폴더에 유지되며 자동으로 제거되지 않습니다. |
|**클라이언트 UI 액세스 허용**|Windows Defender 사용자 인터페이스를 최종 사용자에게 숨길지 여부를 제어합니다.<br>이 설정이 변경되면, 다음 번 최종 사용자 PC를 다시 시작할 때 적용됩니다.|
|**매일 빠른 검색 예약**|매일 발생하는 빠른 검색을 사용자가 선택한 시간으로 예약하도록 허용합니다.|
|**시스템 검색 예약**|정기적으로 발생하는 전체 또는 빠른 시스템 검색을 사용자가 선택한 날짜와 시간으로 예약하도록 허용합니다.|
|**검색하는 동안 CPU 사용 제한**|검색에 사용하도록 허용하는 CPU 양을 제한하도록 허용합니다(**1**에서 **100**까지).|
|**보관 파일 검색**|Defender가 Zip 또는 Cab 파일로 보관된 파일을 검색하도록 허용합니다.|
|**전자 메일 메시지 검색**|Defender가 전자 메일 메시지가 장치에 도착하면 검색하도록 허용합니다.|
|**이동식 드라이브 검색**|Defender가 USB 스틱 같은 이동식 드라이브를 검색하도록 허용합니다.|
|**매핑된 네트워크 드라이브 검색**|Defender가 매핑된 네트워크 드라이브의 파일을 검색하도록 허용합니다.<br>드라이브의 파일이 읽기 전용이면, Defender가 그 안에서 발견한 맬웨어를 제거할 수 없습니다.|
|**네트워크 공유 폴더의 열린 파일 검색**|Defender가 공유 네트워크 드라이브의 파일을(예: UNC 경로를 통해 액세스하는) 검색하도록 허용합니다.<br>드라이브의 파일이 읽기 전용이면, Defender가 그 안에서 발견한 맬웨어를 제거할 수 없습니다.|
|**서명 업데이트 간격**|Defender가 새로운 서명 파일을 확인하는 간격을 지정합니다.|
|**클라우드 보호 허용**|사용자가 관리하는 장치의 맬웨어 활동에 대한 정보를 Microsoft Active Protection Service가 수신하도록 허용하거나 차단합니다. 이 정보는 향후 서비스를 개선하는 데 사용됩니다.|
|**사용자에게 샘플 제출 확인**|파일이 악성 파일인지 판단하기 위해 Microsoft의 자세한 분석이 필요할 수 있는 파일을 Microsoft에 자동으로 보낼지를 제어합니다.|
|**사용자 동의 없이 설치된 응용 프로그램 검색**|이 설정을 사용하여 Windows Defender에서 사용자 동의 없이 설치된 소프트웨어로 분류된 프로그램에 대해 등록된 Windows 데스크톱 컴퓨터를 보호할 수 있습니다. 실행 중인 이러한 응용 프로그램으로부터 보호하거나 감사 모드를 사용하여 사용자 동의 없이 응용 프로그램이 설치될 때 보고할 수 있습니다.|
|**검색을 실행하거나 실시간 보호를 사용할 때 제외할 파일 및 폴더**|제외 목록에 **C:\Path** 또는 **%ProgramFiles%\Path\filename.exe** 같은 파일과 폴더를 하나 이상 추가합니다. 이러한 파일과 폴더는 실시간 또는 예약된 검색에 포함되지 않습니다.|
|**검색을 실행하거나 실시간 보호를 사용할 때 제외할 파일 확장명**|제외 목록에 **jpg** 또는 **txt** 같은 파일과 확장명을 하나 이상 추가합니다. 이러한 확장명의 파일은 실시간 또는 예약된 검색에 포함되지 않습니다.|
|**검색을 실행하거나 실시간 보호를 사용할 때 제외할 프로세스**|제외 목록에 **.exe**, **.com**, 또는 **.scr** 같은 유형의 프로세스를 하나 이상 추가합니다. 이러한 프로세스는 실시간 또는 예약된 검색에 포함되지 않습니다.| 


### 업데이트 설정

|설정 이름|세부 정보|
|----------------|---------------|
|**자동 업데이트 허용**|자동 업데이트를 허용하려면 이 설정을 사용하도록 설정합니다. 그런 후에 다음 설정 중 하나를 구성하여 업데이트 동작을 제어합니다.<br /><br />**다운로드 알림**<br /><br />**유지 관리 시 자동 설치**<br /><br />**유지 관리 시 자동 설치 및 다시 부팅**<br /><br />**예약 시간에 자동 설치 및 다시 부팅** **참고:** 이 옵션을 선택하면 다음 설정을 구성할 수 있습니다. **최종 사용자에게 알림 표시 안 함** 및 **예약된 업데이트의 설치 날짜 지정**<br>(Windows 10 Desktop에만 해당)|

## 사용자 지정 정책 설정
Windows 10 및 Windows 10 Mobile용 Microsoft Intune **사용자 지정 구성 정책**을 사용하여 Windows 10 및 Windows 10 Mobile 장치에서 기능을 제어하는 데 사용할 수 있는 OMA-URI(Open Mobile Alliance Uniform Resource Identifier) 설정을 배포할 수 있습니다. 이는 많은 모바일 장치 제조업체가 장치 기능을 제어하는 데 사용하는 표준 설정입니다.

이 기능은 Intune 일반 구성 정책으로는 구성할 수 없는 Windows 10 설정을 배포하도록 허용하는 데 사용됩니다.



### 사용자 지정 정책 일반 설정

|설정 이름|세부 정보|
    |----------------|--------------------|
    |**Name**|Intune 콘솔에서 쉽게 식별할 수 있도록 정책에 대한 고유한 이름을 입력합니다.|
    |**설명**|정책의 개요에 대한 설명과 찾을 때 도움이 되는 기타 관련 정보를 제공합니다.|

### 사용자 지정 정책 OMA-URI 설정

|설정 이름|세부 정보|
    |--------|--------------------|
    |**설정 이름**|설정 목록에서 쉽게 식별할 수 있도록 OMA-URI 설정에 대한 고유한 이름을 입력합니다.|
    |**설정 설명**|설정의 개요에 대한 설명과 찾을 때 도움이 되는 기타 관련 정보를 제공합니다.|
    |**데이터 형식**|이 OMA-URI 설정을 지정할 날짜 유형을 선택합니다. 다음 중에서 선택합니다.<br /><br />-   **문자열**<br />-   **문자열(XML)**<br />-   **날짜 및 시간**<br />-   **정수**<br />-   **부동 소수점**<br />-   **부울**|
    |**OMA-URI(대/소문자 구분)**|설정을 제공하려는 OMA-URI를 지정합니다.|
    |**값**|이전에 지정한 OMA-URI와 연결할 값을 지정합니다.|


## Windows 10 장치에 대한 사용자 지정 URI 설정
이 항목에서는 Microsoft Intune **Windows 10 사용자 지정 정책**에서 Windows 10 및 Windows 10 Mobile 장치에 대해 구성할 수 있는 설정을 나열합니다.

Windows 사용자 지정 URI 정책을 사용하려면 모든 장치를 Intune에 등록해야 합니다.

### 정책 URI 설정

|정책 이름|세부 정보|
|---------------|------------|-----------|
|**​자동 업데이트 허용**<br>(데스크톱에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Device/Update/AllowAutoUpdate<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** - **5**(기본값: **1**)|
|**설치 날짜 예약**<br>(모바일에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Device/Update/ScheduledInstallDay<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** - 매일(기본값)<br>**1** - 일요일<br>**2** - 월요일<br>**3** - 화요일<br>**4** - 수요일<br>**5** - 목요일<br>**6** - 금요일<br>**7** - 토요일|
|**설치 시간 예약**<br>(데스크톱 및 모바일)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Update/ScheduledInstallTime<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** - **23**시간(**0**은 자정)(기본값: **3**)|
|**DeviceLock/AllowIdleReturnWithoutPassword**<br>(모바일에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/DeviceLock/AllowIdleReturnWithoutPassword<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** - 사용자는 암호 유예 기간 타이머를 설정할 수 없으며, 값은 “매번”으로 설정됩니다.<br>**1** - 사용자가 암호 유예 기간 타이머를 설정할 수 있습니다(기본값).|
|**WiFi/AllowWiFi**<br>(모바일에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/WiFi/AllowWiFi<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – **Wi-Fi 연결 사용**을 허용하지 않습니다.<br>**1** - **Wi-Fi 연결 사용을 허용합니다**(기본값).|
|**WiFi/AllowInternetSharing**<br>(데스크톱 및 모바일)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/WiFi/AllowInternetSharing<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 인터넷 공유를 허용하지 않습니다.<br>**1** - 인터넷 공유를 허용합니다(기본값).|
|**WiFi/AllowAutoConnectToWiFiSenseHotspots**<br>(데스크톱 및 모바일)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/WiFi/AllowAutoConnectToWiFiSenseHotspots<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용되지 않음<br>**1** - 허용됨(기본값)|
|**WiFi/AllowManualWiFiConfiguration**<br>(모바일에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/WiFi/AllowManualWiFiConfiguration<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 프로비전된 MDM 외부의 Wi-Fi 연결이 허용되지 않습니다.<br>**1** – 이미 프로비전된 MDM을 초과하는 새 네트워크 SSID의 추가를 허용합니다(기본값).|
|**System/AllowLocation**<br>(데스크톱 및 모바일)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/System/AllowLocation<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용되지 않음<br>**1** - 허용됨(기본값)|
|**System/AllowTelemetry**<br>(데스크톱 및 모바일)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/System/AllowTelemetry<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용되지 않음(기업 전용 설정)<br>**1** – 제한됨<br>**2** - 전체(기본값)<br>**3** - 전체 및 진단 정보|
|**System/AllowExperimentation**<br>(데스크톱 및 모바일)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/System/AllowExperimentation<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용되지 않음<br>**1** - 설정만(기본값)<br>**2** - 설정 및 실험|
|**Security/AntiTheftMode**<br>(모바일에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Security/AntiTheftMode<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** - 도난 방지 모드를 허용하지 않음<br>**1** - 사용자 기본 설정(기본값)|
|**Connectivity/AllowUSBConnection**<br>(모바일에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowUSBConnection<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용되지 않음<br>**1** - 허용됨(기본값)|
|**System/AllowUserToResetPhone**<br>(모바일에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/System/AllowUserToResetPhone<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용되지 않음<br>**1** - 허용됨(기본값)|
|**Connectivity/AllowCellularDataRoaming**<br>(데스크톱 및 모바일)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowCellularDataRoaming<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용되지 않음<br>**1** - 허용됨(기본값)|
|**Connectivity/AllowVPNOverCellular**<br>(데스크톱 및 모바일)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNOverCellular<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** - 휴대폰을 통한 VPN이 허용되지 않음<br>**1** - VPN이 휴대폰을 포함한 모든 연결을 사용할 수 있음(기본값)|
|**Connectivity/AllowVPNRoamingOverCellular**<br>(모바일에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용되지 않음<br>**1** - 허용됨(기본값)|
|**Connectivity/AllowVPNRoamingOverCellular**<br>(모바일에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용되지 않음<br>**1** - 허용됨(기본값)|
|**Connectivity/AllowBluetooth**<br>(데스크톱 및 모바일)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowBluetooth<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 사용자가 Bluetooth를 켜도록 허용하지 않습니다.<br>**1** – 예약됨. 사용자가 Bluetooth를 켜고 구성할 수 있습니다(Windows 10 Mobile 또는 MDM, EAS, Windows 10 Desktop용 Windows Phone 8.1에는 지원되지 않음).<br>**2** - 허용됨. 사용자가 Bluetooth를 켜고 구성할 수 있습니다(기본값).|
|**Experience/AllowScreenCapture**<br>(모바일에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Experience/AllowScreenCapture<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용되지 않음<br>**1** - 허용됨(기본값)|
|**Experience/AllowTaskSwitcher**<br>(모바일에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Experience/AllowTaskSwitcher<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용되지 않음<br>**1** - 허용됨(기본값)|
|**Experience/AllowVoiceRecording**<br>(모바일에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Experience/AllowVoiceRecording<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용되지 않음<br>**1** - 허용됨(기본값)|
|**Experience/AllowSyncMySettings**<br>(모바일에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Experience/AllowSyncMySettings<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 로밍을 허용하지 않음<br>**1** – 로밍 허용(기본값)|
|**Experience/AllowManualMDMUnenrollment**<br>(데스크톱 및 모바일)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Experience/AllowManualMDMUnenrollment<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용되지 않음<br>**1** - 허용됨(기본값)|
|**Accounts/AllowMicrosoftAccountConnection**<br>(데스크톱 및 모바일)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Accounts/AllowMicrosoftAccountConnection<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용되지 않음<br>**1** - 허용됨(기본값)|
|**Accounts/AllowAddingNonMicrosoftAccountsManually**<br>(데스크톱 및 모바일)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Accounts/AllowAddingNonMicrosoftAccountsManually<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용되지 않음<br>**1** - 허용됨(기본값)|
|**Security/AllowManualRootCertificateInstallation**<br>(모바일에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Security/AllowManualRootCertificateInstallation<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용되지 않음<br>**1** - 허용됨(기본값)|
|**Security/AllowAddProvisioningPackages**<br>(데스크톱 및 모바일)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Security/AllowAddProvisioningPackages<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용되지 않음<br>**1** - 허용됨(기본값)|
|**Search/DisableBackoff**<br>(데스크톱 및 모바일)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Search/DisableBackoff<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0**(기본값)<br>**1**|
|**Search/PreventRemoteQueries**<br>(데스크톱 및 모바일)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Search/PreventRemoteQueries<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0**<br>**1**(기본값)|
|**Search/AllowUsingDiacritics**<br>(데스크톱 및 모바일)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Search/AllowUsingDiacritics<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br> **0**(기본값)<br>**1**|
|**Search/AlwaysUseAutoLangDetection**<br>(데스크톱 및 모바일)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Search/AlwaysUseAutoLangDetection<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0**(기본값)<br>**1**|
|**Search/DisableRemovableDriveIndexing**<br>(데스크톱 및 모바일)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Search/DisableRemovableDriveIndexing<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0**(기본값)<br>**1**|
|**Search/PreventIndexingLowDiskSpaceMB**<br>(데스크톱 및 모바일)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Search/PreventIndexingLowDiskSpaceMB<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0**<br>**1**(기본값)|
|**Search/AllowIndexingEncryptedStoresOrItems**<br>(데스크톱 및 모바일)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Search/AllowIndexingEncryptedStoresOrItems<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0**(기본값)<br>**1**|
|**Security/AllowRemoveProvisioningPackage**<br>(데스크톱 및 모바일)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Security/AllowRemoveProvisioningPackage<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용되지 않음<br>**1** - 허용됨(기본값)|
|**Security/RequireProvisioningPackageSignature**<br>(데스크톱 및 모바일)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Security/RequireProvisioningPackageSignature<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0**(기본값)<br>**1**|
|**AboveLock/AllowActionCenterNotifications**<br>(데스크톱 및 모바일)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/AboveLock/AllowActionCenterNotifications<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용되지 않음<br>**1** - 허용됨(기본값)|
|**TextInput/AllowIMENetworkAccess**<br>(데스크톱에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/TextInput/AllowIMENetworkAccess<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용하지 않음<br>개방형 확장 사전이 꺼집니다.<br>사용자는 다음 작업을 수행할 수 없습니다.<br>새 개방형 확장 사전 추가<br /><br />새 검색 통합 구성 파일 추가<br>클라우드 후보 기능 사용<br>사용자 등록 단어 보내기<br>추가 필수 구성 요소:<br>이 정책 설정을 사용하도록 설정하기 전에 추가된 개방형 확장 사전은 변환을 위해 사용되지 않습니다.<br>이 정책 설정을 사용하도록 설정하기 전에 설치된 검색 통합 구성 파일은 사용되지 않습니다.<br>**1** - 허용<br>개방형 확장 사전을 기본적으로 추가하고 사용할 수 있습니다. 또한 검색 통합 기능을 기본적으로 사용할 수 있습니다.<br>사용자는 다음 작업을 수행할 수 있습니다.<br>클라우드 후보 기능 사용<br>사용자 등록 단어 보내기|
|**TextInput/AllowIMELogging**<br>(데스크톱에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/TextInput/AllowIMELogging<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** - 변환 오류 로깅이 꺼집니다. 자동으로 조정되는 데이터 및 입력 기록 데이터가 파일에 저장되지 않습니다.<br>**1** - 변환 오류 로깅이 켜집니다. 자동으로 조정되는 데이터 및 입력 기록 데이터가 파일에 저장됩니다(기본값).|
|**TextInput/AllowJapaneseNonPublishingStandardGlyph**<br>(데스크톱에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseNonPublishingStandardGlyph<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용되지 않음<br>**1** - 허용됨(기본값)|
|**TextInput/AllowJapaneseIVSCharacters**<br>(데스크톱에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIVSCharacters<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용되지 않음<br>**1** - 허용됨(기본값)|
|**TextInput/AllowJapaneseUserDictionary**<br>(데스크톱에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseUserDictionary<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용되지 않음<br>**1** - 허용됨(기본값)|
|**TextInput/AllowJapaneseIMESurrogatePairCharacters**<br>(데스크톱에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIMESurrogatePairCharacters<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용되지 않음<br>**1** - 허용됨(기본값)|
|**TextInput/ExcludeJapaneseIMEExceptShiftJIS**<br>(데스크톱에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptShiftJIS<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** - 문자가 필터링되지 않음(기본값)<br>**1** - Shift JIS 문자를 제외한 모든 내용이 필터링됨|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208**<br>(데스크톱에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br /><br />**0** - 문자가 필터링되지 않음(기본값)<br>**1** - JIS0208 문자를 제외한 모든 내용이 필터링됨|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC**<br>(데스크톱에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** - 문자가 필터링되지 않음(기본값)<br>**1** - JIS0208 문자 또는 EUDC 문자를 제외한 모든 내용이 필터링됨|
|**TextInput/AllowInputPanel**<br>(데스크톱에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/TextInput/AllowInputPanel<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용되지 않음<br>**1** - 허용됨(기본값)|
|**Bluetooth/AllowDiscoverableMode**<br>(데스크톱 및 모바일)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Bluetooth/AllowDiscoverableMode<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용되지 않음<br>**1** - 허용됨(기본값)|
|**Bluetooth/AllowAdvertising**<br>(데스크톱 및 모바일)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Bluetooth/AllowAdvertising<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용되지 않음<br>**1** - 허용됨(기본값)|
|**Settings/AllowDataSense**<br>(데스크톱 및 모바일)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Settings/AllowDataSense<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용되지 않음<br>**1** - 허용됨(기본값)|
|**Settings/AllowVPN**<br>(데스크톱 및 모바일)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Settings/AllowVPN<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용되지 않음<br>**1** - 허용됨(기본값)|
|**Settings/AllowWorkplace**<br>(데스크톱에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Settings/AllowWorkplace<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용되지 않음<br>**1** - 허용됨(기본값)|
|**Settings/AllowDateTime**<br>(데스크톱 및 모바일)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Settings/AllowDateTime<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용되지 않음<br>**1** - 허용됨(기본값)|
|**Settings/AllowLanguage**<br>(데스크톱에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Settings/AllowLanguage<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용되지 않음<br>**1** - 허용됨(기본값)|
|**Settings/AllowRegion**<br>(데스크톱에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Settings/AllowRegion<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용되지 않음<br>**1** - 허용됨(기본값)|
|**Settings/AllowSignInOptions**<br>(데스크톱에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Settings/AllowSignInOptions<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용되지 않음<br>**1** - 허용됨(기본값)|
|**Settings/AllowYourAccount**<br>(데스크톱 및 모바일)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Settings/AllowYourAccount<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용되지 않음<br>**1** - 허용됨(기본값)|
|**Settings/AllowPowerSleep**<br>(데스크톱에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Settings/AllowPowerSleep<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용되지 않음<br>**1** - 허용됨(기본값)|
|**Settings/AllowAutoPlay**<br>(데스크톱에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Settings/AllowAutoPlay<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용되지 않음<br>**1** - 허용됨(기본값)|
|**Experience/AllowCortana**<br>(데스크톱 및 모바일)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Experience/AllowCortana<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용되지 않음<br>**1** - 허용됨(기본값)|
|**Search/SafeSearchPermissions**<br>(모바일에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Search/SafeSearchPermissions<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 엄격, 성인용 콘텐츠에 대한 최고의 필터링<br>**1** – 보통, 성인용 콘텐츠에 대한 보통 필터링(유효한 검색 결과는 필터링되지 않음 - 기본값)|
|**Experience/AllowCopyPaste**<br>(데스크톱에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Experience/AllowCopyPaste<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용되지 않음<br>**1** - 허용됨(기본값)|
|**시작 크기 적용**<br>(모바일에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Start/ForceStartSize<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** - 사용자가 크기 변경 가능(기본값)<br>**1** - 전체 화면이 아닌 화면 적용<br>**2** - 전체 화면 적용|
|**Update/RequireDeferUpgrade**<br>(데스크톱 및 모바일)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Update/RequireDeferUpgrade<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0**: 업그레이드를 연기하지 않음(CB(Current Branch) 유지 - 기본값)<br>**1**: 업데이트 및 업그레이드 연기 허용(장치가 CBB(Current Branch for Business) 규칙을 따름)<br /><br />자세한 내용은 다음을 참조하십시오.<br>[Windows 10 서비스 소개](https://technet.microsoft.com/library/mt598226.aspx)<br>[Windows 10 배포에 대한 계획](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpdatePeriod**<br>(데스크톱 및 모바일)|**설명:** 최대 4주 동안 소프트웨어 업데이트를 연기하는 정책<br /><br />**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Update/DeferUpdatePeriod<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br> **0**: 즉시 업데이트 적용(기본값)<br>**1**-**4**: 소프트웨어 업데이트를 연기할 주 수<br /><br />자세한 내용은 다음을 참조하십시오.<br>[Windows 10 서비스 소개](https://technet.microsoft.com/library/mt598226.aspx)<br>[Windows 10 배포에 대한 계획](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpgradePeriod**<br>(데스크톱 및 모바일)|**설명:** 최대 8개월 동안 기능 업그레이드를 연기하는 정책<br /><br />**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Update/DeferUpgradePeriod<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0**: 즉시 업데이트 적용(기본값)<br>**1**-**8**: 기능 업그레이드를 연기할 개월 수<br /><br />자세한 내용은 다음을 참조하십시오.<br>[Windows 10 서비스 소개](https://technet.microsoft.com/library/mt598226.aspx)<br>[Windows 10 배포에 대한 계획](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/PauseDeferrals**<br>(데스크톱 및 모바일)|**설명:** CBB 컴퓨터에서 5주 동안 업데이트 및 업그레이드 수신을 중지하도록 허용합니다. 업데이트에 문제가 있는 경우에 사용해야 합니다.<br /><br />**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Update/PauseDeferrals<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0**: 즉시 업데이트 적용(기본값)<br>**1**: 업데이트 및 업그레이드 일시 중지(5주 후에 만료)|

### Windows Defender URI 설정

|정책 이름|세부 정보|
|---------------|-----------|
|**AllowRealtimeMonitoring**<br>(데스크톱에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Defender/AllowRealtimeMonitoring<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용되지 않음<br>**1** - 허용됨(기본값)|
|**AllowBehaviorMonitoring**<br>(데스크톱에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Defender/AllowBehaviorMonitoring<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용되지 않음<br>**1** - 허용됨(기본값)|
|**AllowIntrusionPreventionSystem**<br>(데스크톱에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Defender/AllowIntrusionPreventionSystem<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용되지 않음<br>**1** - 허용됨(기본값)|
|**AllowIOAVProtection**<br>(데스크톱에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Defender/AllowIOAVProtection<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용되지 않음<br>**1** - 허용됨(기본값)|
|**AllowScriptScanning**<br>(데스크톱에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Defender/AllowScriptScanning<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용되지 않음<br>**1** - 허용됨(기본값)|
|**AllowOnAccessProtection**<br>(데스크톱에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Defender/AllowOnAccessProtection<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용되지 않음<br>**1** - 허용됨(기본값)|
|**RealTimeScanDirection**<br>(데스크톱에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Defender/RealTimeScanDirection<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 모든 파일 모니터링(양방향 - 기본값)<br>**1** – 들어오는 파일 모니터링<br>**2** – 나가는 파일 모니터링|
|**DaysToRetainCleanedMalware**<br>(데스크톱에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Defender/DaysToRetainCleanedMalware<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** - **90** – 맬웨어가 유지되는 길이를 나타냄<br>**기본값:** **0** – 격리 폴더에 영원히 유지하고 자동으로 제거하지 않음|
|**AllowUserUIAccess**<br>(데스크톱에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Defender/AllowUserUIAccess<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용되지 않음<br>**1** - 허용됨(기본값)|
|**ScanParameter**<br>(데스크톱에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Defender/ScanParameter<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**1** - 빠른 검색(기본값)<br>**2** - 전체 검색|
|**ScheduleScanDay**<br>(데스크톱에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Defender/ScheduleScanDay<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** - 매일(기본값)<br>**1** - 월요일<br>**2** - 화요일<br>**3** - 수요일<br>**4** - 목요일<br>**5** - 금요일<br>**6** - 토요일<br>**7** - 일요일<br>**8** – 예약된 검색 없음|
|**ScheduleScanTime**<br>(데스크톱에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Defender/ScheduleScanTime<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** - 12:00 am<br>**60** ~ 1:00 am<br>**120** – 2:00 am(기본값)<br>**180** ~ 3:00 am<br>**240** ~ 4:00 am<br>**300** ~ 5:00 am<br>**360** ~ 6:00 am<br>**420** ~ 7:00 am<br>**480** ~ 8:00 am<br>**540** ~ 9:00 am<br>**600** ~ 10:00 am<br>**660** ~ 11:00 am<br>**720** ~ 12:00 pm<br>**780** ~ 1:00 pm<br>**840** ~ 2:00 pm<br>**900** ~ 3:00 pm<br>**960** ~ 4:00 pm<br>**1020** ~ 5:00 pm<br>**1080** ~ 6:00 pm<br>**1140** ~ 7:00 pm<br>**1200** ~ 8:00 pm<br>**1260** ~ 9:00 pm<br>**1320** ~ 10:00 pm<br>**1381** – 유지 관리 기간|
|**ScheduleQuickScanTime**<br>(데스크톱에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Defender/ScheduleQuickScanTime<br>**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** - 12:00 am<br>**60** ~ 1:00 am<br>**120** – 2:00 am(기본값)<br>**180** ~ 3:00 am<br>**240** ~ 4:00 am<br>**300** ~ 5:00 am<br>**360** ~ 6:00 am<br>**420** ~ 7:00 am<br>**480** ~ 8:00 am<br>**540** ~ 9:00 am<br>**600** ~ 10:00 am<br>**660** ~ 11:00 am<br>**720** ~ 12:00 pm<br>**780** ~ 1:00 pm<br>**840** ~ 2:00 pm<br>**900** ~ 3:00 pm<br>**960** ~ 4:00 pm<br>**1020** ~ 5:00 pm<br>**1080** ~ 6:00 pm<br>**1140** ~ 7:00 pm<br>**1200** ~ 8:00 pm<br>**1260** ~ 9:00 pm<br>**1320** ~ 10:00 pm<br>**1380** ~ 11:00 pm|
|**AVGCPULoadFactor**<br>(데스크톱에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Defender/AVGCPULoadFactor<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:0** - **100**(기본값: **50**)|
|**AllowArchiveScanning**<br>(데스크톱에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Defender/AllowArchiveScanning<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용되지 않음<br>**1** - 허용됨(기본값)|
|**AllowEmailScanning**<br>(데스크톱에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Defender/AllowEmailScanning<br /><br />**데이터 형식:** 정수<br>**허용되는 값:**<br>**0** – 허용되지 않음(기본값)<br>**1** – 허용됨|
|**AllowFullScanRemovableDriveScanning**<br>(데스크톱에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Defender/AllowFullScanRemovableDriveScanning<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용되지 않음(기본값)<br>**1** – 허용됨|
|**AllowFullScanOnMappedNetworkDrives**<br>(데스크톱에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Defender/AllowFullScanOnMappedNetworkDrives<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용되지 않음<br>**1** - 허용됨(기본값)|
|**AllowScanningNetworkFiles**<br>(데스크톱에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Defender/AllowScanningNetworkFiles<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용되지 않음<br>**1** – 허용됨(기본값), 허용됨으로 설정되어 있는 경우 RTP가 켜져 있을 때에도 실행됨|
|**SignatureUpdateInterval**<br>(데스크톱에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Defender/SignatureUpdateInterval<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 일정 간격으로 서명을 검사하지 않음<br>**1** - 매 시간마다 서명 검사<br>**2** – 매 2시간마다 서명 검사 등등<br>**24** – 매일 서명 검사<br>**기본값:** 8 – 8시간 마다 서명 확인|
|**AllowCloudProtection**<br>(데스크톱에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Defender/AllowCloudProtection<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용되지 않음<br>**1** - 허용됨(기본값)|
|**SubmitSamplesConsent**<br>(데스크톱에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Defender/SubmitSamplesConsent<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 항상 메시지 표시(기본값)<br>**1** – 자동으로 안전 샘플 보내기<br>**2** – 보내지 않음<br>**3** – 자동으로 모든 샘플 보내기|
|**ExcludedExtensions**<br>(데스크톱에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Defender/ExcludedExtensions<br /><br />**데이터 형식:** 문자열<br /><br />**허용되는 값:**<br>*&lt;세미콜론으로 구분된 확장자 목록&gt;* 예: **obj;lib**<br>**기본값:** 제외되는 확장 없음|
|**ExcludedPaths**<br>(데스크톱에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Defender/ExcludedPaths<br /><br />**데이터 형식:** 문자열<br /><br />**허용되는 값:**<br /><br />*&lt;세미콜론으로 구분된 경로 목록&gt;*<br /><br />예: **c:\test;c:\test1.exe**<br /><br />**기본값:** 제외되는 경로 없음|
|**ExcludedProcesses**<br>(데스크톱에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Defender/ExcludedProcesses<br /><br />**데이터 형식:** 문자열<br /><br />**허용되는 값:**<br>*&lt;세미콜론으로 구분된 경로 목록&gt;*<br>예: **c:\test.exe;c:\test1.exe**<br>**기본값:** 제외되는 프로세스 없음|

### Edge 브라우저 URI 설정

|정책 이름|세부 정보|
|---------------|------------|-----------|
|**브라우저 허용**<br>(모바일에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Browser/AllowBrowser<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0**: 검색 해제<br>**1**: 검색 설정(기본값)|
|**AllowSearchSuggestionsinAddressBar**<br>(데스크톱 및 모바일)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Browser/AllowSearchSuggestionsinAddressBar<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0**: 검색 제안 표시 안 함<br>**1**: 검색 제안 표시(기본값)|
|**SendIntranetTraffictoInternetExplorer**<br>(데스크톱에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Browser/SendIntranetTraffictoInternetExplorer<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0**: 사용 안 함(Edge 브라우저에서 인트라넷 사이트 열기 - 기본값)<br>**1** - 사용(Internet Explorer에서 인트라넷 사이트 열기)|
|**Do Not Track 허용**<br>(데스크톱 및 모바일)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Browser/AllowDoNotTrack<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 사용 안 함(DNT가 전송되지 않음 - 기본값)<br>**1** – 사용(DNT 전송)|
|**SmartScreen 구성**<br>(데스크톱 및 모바일)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Browser/AllowSmartScreen<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 허용 안 함<br>**1** – 허용(기본값)|
|**팝업 허용**<br>(데스크톱에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Browser/AllowPopups<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 팝업 차단(기본값)<br>**1** – 팝업 허용|
|**쿠키 허용**<br>(데스크톱 및 모바일)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Browser/AllowCookies<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 차단하지 않음. 모든 웹 사이트의 쿠키 허용(기본값)<br>**1** – 타사 쿠키만 차단<br>**2** – 모든 쿠키 차단|
|**암호 저장 허용**<br>(데스크톱 및 모바일)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Browser/AllowPasswordManager<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 암호 관리자 사용 안 함 <br>**1** – 암호 관리자 사용(기본값)|
|**자동 채우기 허용**<br>(데스크톱에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Settings/AllowAutofill<br /><br />**데이터 형식:** 정수<br /><br />**허용되는 값:**<br>**0** – 사용 안 함(기본값)<br>**1** – 사용|
|**엔터프라이즈 사이트 목록 구성**<br>(데스크톱에만 해당)|**URI 전체 경로:** ./Vendor/MSFT/Policy/Config/Browser/EnterpriseModeSiteList<br /><br />**데이터 형식:** 문자열<br /><br />**허용되는 값:<br>0** – 구성되지 않음<br>**1** – 구성하는 경우 IE의 엔터프라이즈 모드 사이트 목록 사용(기본값)<br>**2** – 엔터프라이즈 사이트 목록의 위치 지정|

### 참고 항목
[Microsoft Intune 정책을 사용하여 장치의 설정 및 기능 관리](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)




<!--HONumber=Jun16_HO3-->


