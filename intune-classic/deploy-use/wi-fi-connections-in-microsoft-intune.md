---
title: "Wi-Fi 연결"
description: "Wi-Fi 프로필을 통해 사용자의 Wi-Fi 네트워크 연결을 지원하는 방법을 설명합니다."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 02/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0b1b86ed-2e80-474d-8437-17dd4bc07b55
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 99ac426d2210aa22a7c0151aea59e14b848bbe1f
ms.sourcegitcommit: 3b397b1dcb780e2f82a3d8fba693773f1a9fcde1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2017
---
# <a name="configure-devices-to-connect-to-your-corporate-wi-fi-networks"></a>회사 Wi-Fi 네트워크에 연결하도록 장치 구성

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune Wi-Fi 프로필을 사용하여 무선 네트워크 설정을 조직의 사용자와 장치에 배포합니다. Wi-Fi 프로필을 배포하면 사용자가 Wi-Fi를 직접 구성하지 않고도 회사 Wi-Fi에 액세스할 수 있습니다.

예를 들어, **Contoso Wi-Fi**라는 이름의 새 Wi-Fi 네트워크를 설치하고 모든 iOS 장치를 이 네트워크에 연결하도록 설정하려고 합니다. 프로세스는 다음과 같습니다.

![Wi-Fi 프로필 프로세스 요약](..\media\wi-fi-process-diagram.png)

1.   **Contoso Wi-Fi** 무선 네트워크에 연결하는 데 필요한 설정이 포함된 Wi-Fi 프로필을 만듭니다.

2.   프로필을 iOS 장치 사용자 그룹에 배포합니다.

3.   사용자는 무선 네트워크 목록에서 새 **Contoso Wi-Fi** 네트워크를 찾아서 해당 네트워크에 쉽게 연결할 수 있습니다.


## <a name="create-a-wi-fi-profile"></a>Wi-Fi 프로필 만들기

다음 플랫폼에 Wi-Fi 프로필을 배포할 수 있습니다.

-   Android 4.0 이상

-   Android for Work   

-   iOS 8.0 이상

-   Mac OS X 10.9 이상

Windows 8.1 또는 Windows 10 데스크톱이나 모바일 운영 체제를 실행하는 장치의 경우에는 이전에 파일로 내보낸 Wi-Fi 구성 프로필을 가져올 수 있습니다. 자세한 내용은 [Windows 장치용 Wi-Fi 구성 프로필 내보내기 또는 가져오기](#export-or-import-a-wi-fi-configuration-profile-for-windows-devices)를 참조하세요.

1.  [Microsoft Intune 관리 콘솔](https://manage.microsoft.com)에서 **정책** &gt; **정책 추가**를 선택합니다.

2.  다음 정책 유형 중 하나를 선택하고 **정책 만들기**를 선택합니다.

    -   Wi-Fi 프로필(Android 4 이상)

    -   Wi-Fi 프로필(Android for Work)

    -   Wi-Fi 프로필(iOS 8.0 이상)

    -   Wi-Fi 프로필(Mac OS X 10.9 이상)


이 정책 유형에 대한 권장 설정은 없습니다. 사용자 지정 정책을 만들어야 합니다.

3.  프로필의 이름과 설명을 제공합니다.

4. **네트워크 연결** 값을 지정합니다.
 - **SSID(서비스 집합 ID)**: 사용자에게 SSID가 아니라 네트워크 이름을 표시하려면 이 옵션을 선택합니다.
 - **네트워크가 해당 이름(SSID)을 브로드캐스트하지 않을 때 연결**: 네트워크가 숨겨져 있고 네트워크 이름이 브로드캐스트되지 않아서 네트워크 목록에 네트워크가 표시되지 않을 때 장치가 네트워크에 연결할 수 있도록 하려면 이 옵션을 선택합니다.

5. 선택한 플랫폼의 **보안 설정** 을 구성합니다. 사용 가능한 설정은 선택한 보안 유형에 따라 달라집니다. 보안 유형에 대한 설명은 [보안 설정](#security-settings)에 있습니다.

6. **프록시 설정**을 구성합니다(iOS 및 MAC OS X만 해당).

    |설정 이름|추가 정보|사용 시기|
    |----------------|-------------------|-------------|
    |**이 Wi-Fi 연결에 대한 프록시 설정**|프록시 설정 유형을 선택합니다.<br /><br />-   **없음**(기본값)<br />-   **수동** - 프록시 서버의 URL 및 포트 번호를 수동으로 지정합니다.<br />-   **자동** – 구성 파일을 사용하여 프록시 서버를 구성합니다.|항상|
    |**프록시 서버 주소** 및 **포트 번호**|프록시 서버의 URL과 포트 번호를 지정합니다.|**이 Wi-Fi 연결에 대한 프록시 설정**을 **수동**으로 설정한 경우|
    |**프록시 서버 URL**|프록시 서버 설정을 포함하는 파일의 URL을 지정합니다.|**이 Wi-Fi 연결에 대한 프록시 설정**을 **자동**으로 설정한 경우|

7.  Wi-Fi 프로필 저장

새 정책이 **정책** 작업 영역의 **구성 정책** 노드에 표시됩니다. 프로필 배포에 대한 자세한 내용은 **다음 단계**를 참조하세요.

## <a name="export-or-import-a-wi-fi-configuration-profile-for-windows-devices"></a>Windows 장치용 Wi-Fi 구성 프로필 내보내기 또는 가져오기

Windows 8.1 또는 Windows 10 데스크톱이나 모바일 운영 체제를 실행하는 장치의 경우에는 이전에 파일로 내보낸 Wi-Fi 구성 프로필을 가져올 수 있습니다.

### <a name="export-a-wi-fi-profile"></a>Wi-Fi 프로필 내보내기
Windows에서는 **netsh wlan** 유틸리티를 사용하여 기존 Wi-Fi 프로필을 Intune에서 읽을 수 있는 XML 파일로 내보낼 수 있습니다. 필요한 Wi-Fi 프로필이 이미 설치되어 있는 Windows 컴퓨터에서는 다음 단계를 수행합니다.

1.  내보낸 Wi-Fi 프로필에 대한 로컬 폴더를 만듭니다. 예를 들어 **c:\WiFi**라는 폴더를 만듭니다.

2.  관리자 권한으로 명령 프롬프트를 엽니다.

3.  `netsh wlan show profiles` 명령을 실행하고 내보내려는 프로필의 이름을 적어 둡니다.  이 예제에서 프로필 이름은 **WiFiName**입니다.

4.  다음 명령을 실행합니다. `netsh wlan export profile name="ProfileName" folder=c:\Wifi`. 이렇게 하면 **Wi-Fi-WiFiName.xml**이라는 Wi-Fi 프로필 파일이 대상 폴더에 생성됩니다.

### <a name="import-a-wi-fi-profile"></a>Wi-Fi 프로필 가져오기
**Windows Wi-Fi 가져오기 정책**을 사용하여 Wi-Fi 설정 집합을 가져온 다음 필요한 사용자 또는 정책 그룹에 배포할 수 있습니다.


1.  [Microsoft Intune 관리 콘솔](https://manage.microsoft.com)에서 **정책** &gt; **정책 추가**를 클릭합니다.

2.  **Windows** &gt; **Wi-Fi 가져오기(Windows 8.1 이상)** 유형의 정책을 구성합니다.

    이 정책은 Windows 8.1 및 Windows 10 데스크톱 및 모바일 운영 체제를 실행하는 장치에 적용할 수 있습니다.

    *사용자 지정* Windows Wi-Fi 가져오기 정책만 만들고 배포할 수 있습니다. 권장 설정은 사용할 수 없습니다.

3.  Windows Wi-Fi 가져오기 정책에 대해 다음과 같은 일반 값을 지정합니다.

    |설정 이름|추가 정보|
    |----------------|--------------------|
    |**Name**|Intune 콘솔에서 쉽게 식별할 수 있도록 Wi-Fi 프로필에 대한 고유한 이름을 입력합니다.|
    |**설명**|Wi-Fi 프로필을 쉽게 찾을 수 있도록 Wi-Fi 프로필 설명과 기타 관련 정보를 입력합니다.|

4.  **사용자 지정 Wi-Fi 프로필** 제목 아래에 다음 값을 지정합니다.

    |설정 이름|추가 정보|
    |----------------|--------------------|
    |**구성 프로필 파일**|**가져오기**를 선택하여 Intune으로 가져오려는 Wi-Fi 프로필 설정이 포함된 XML 파일을 선택합니다.|
    |**사용자 지정 구성 프로필 이름(사용자에게 표시됨)**|장치에서 사용자에게 Wi-Fi 구성 프로필의 이름을 표시할 방법을 선택합니다.|
    |**구성 프로필 세부 정보**|선택한 구성 프로필에 대한 XML 코드를 표시할 방법을 선택합니다.|

5.  작업이 끝나면 **정책 저장**을 선택합니다.

6.  새 정책이 **정책** 작업 영역의 **구성 정책** 노드에 표시됩니다.

## <a name="deploy-the-profile"></a>프로필 배포

프로필은 정책의 일종이므로 **정책** 작업 영역을 사용하여 배포합니다.

1.  **정책** 작업 영역에서 배포할 정책을 선택한 다음 **배포 관리**를 선택합니다.

2.  **배포 관리** 대화 상자에서

    -   **정책을 배포하려면**: 정책을 배포하려는 그룹을 하나 이상 선택합니다. **추가** &gt; **확인**을 선택합니다.

    -   **정책을 배포하지 않고 대화 상자를 닫으려면**: **취소**를 클릭합니다.


**정책** 작업 영역의 **개요** 페이지에 주의해야 하는 정책 문제가 표시됩니다. 또한 상태 요약은 대시보드 작업 영역에 표시됩니다.

## <a name="security-settings"></a>보안 설정
이러한 테이블에는 Android, iOS 및 Mac OS X Wi-Fi 프로필에 사용 가능한 보안 설정의 세부 정보가 있습니다.

### <a name="security-settings-for-android-devices"></a>Android 장치용 보안 설정

  |설정 이름|추가 정보|사용 시기|
|----------------|--------------------|-------------|
|**보안 유형**|무선 네트워크의 보안 프로토콜을 선택합니다.<br /><br />-   **WPA-엔터프라이즈/WPA2-엔터프라이즈**<br />-   **인증 안 함(열림)** - 비보안 네트워크인 경우|항상|
|**EAP 종류**|보안 무선 연결을 인증하는 데 사용되는 EAP(확장할 수 있는 인증 프로토콜) 유형을 선택합니다.<br /><br />-   **EAP-TLS**<br />-   **PEAP**<br />-   **EAP-TTLS**|**WPA-엔터프라이즈/WPA2-엔터프라이즈** 보안 유형을 선택한 경우|
|**서버 유효성 검사를 위한 루트 인증서 선택**|**선택**을 선택한 다음 연결을 인증하는 데 사용되는 신뢰할 수 있는 루트 인증서 프로필을 선택합니다. 신뢰할 수 있는 루트 인증서 프로필을 만드는 방법에 대한 자세한 내용은 [인증서 프로필을 통해 리소스 액세스 보안](secure-resource-access-with-certificate-profiles.md)을 참조하세요.|**EAP 유형**을 선택한 경우|
|**인증 방법**|연결에 사용되는 인증 방법을 선택합니다.<br /><br />-   **인증서** - 클라이언트 인증서를 지정하려는 경우<br />-   **사용자 이름 및 암호** - 다른 인증 방법을 지정하려는 경우|-   **EAP 종류**가 **PEAP** 또는 **EAP-TTLS**인 경우|
|**인증을 위해 EAP 이외의 방법 선택(내부 ID)**|연결을 인증할 방법을 선택합니다.<br /><br />-   **없음**<br />-   **암호화되지 않은 암호(PAP)**<br />-   **CHAP(Challenge Handshake 인증 프로토콜)**<br />-   **MS-CHAP(Microsoft CHAP)**<br />-   **MS-CHAP v2(Microsoft CHAP 버전 2)**<br /><br />사용 가능한 옵션은 선택한 EAP 유형에 따라 달라집니다.|**인증 방법** 이 **사용자 이름 및 암호**인 경우|
|**ID 개인 정보 사용(외부 ID)**|EAP ID 요청에 대한 응답으로 전송되는 텍스트를 지정합니다. 이 텍스트에는 원하는 값을 사용할 수 있습니다. 인증하는 동안 이 익명 ID가 처음에 전송됩니다. 그런 다음 실제 ID가 보안 터널에서 전송 됩니다.|**EAP 유형**이 **PEAP** 또는 **EAP-TTLS**인 경우|
|**클라이언트 인증을 위해 클라이언트 인증서 선택(ID 인증서)**|**선택**을 선택한 다음 연결을 인증하는 데 사용되는 SCEP 인증서 프로필을 선택합니다. SCEP 인증서 프로필을 만드는 방법에 대한 자세한 내용은 [인증서 프로필을 통해 리소스 액세스 보안](secure-resource-access-with-certificate-profiles.md)을 참조하세요.|보안 유형이 **WPA-엔터프라이즈/WPA2-엔터프라이즈**이며 임의의 **EAP 유형**을 선택한 경우|

### <a name="security-settings-for-ios-and-mac-os-x-devices"></a>iOS 및 Mac OS X 장치용 보안 설정

  |설정 이름|추가 정보|사용 시기|
|----------------|--------------------|-------------|
|**보안 유형**|무선 네트워크 보안 프로토콜을 선택합니다.<br /><br />-   **WPA-개인/WPA2-개인**<br />-   **WPA-엔터프라이즈/WPA2-엔터프라이즈**<br />-   **WEP**<br />-   **인증 안 함(열림)** - 비보안 네트워크인 경우|항상|
|**EAP 종류**|보안 무선 연결을 인증하는 데 사용되는 EAP(확장할 수 있는 인증 프로토콜) 유형을 선택합니다.<br /><br />-   **EAP-TLS**<br />-   **PEAP**<br />-   **EAP-TLS**<br />-   **EAP-AST**<br />-   **LEAP**<br />-   **EAP-SIM**|**WPA-엔터프라이즈/WPA2-엔터프라이즈** 보안 유형을 선택한 경우|
|**신뢰할 수 있는 서버 인증서 이름**|연결을 인증하는 데 사용되는 신뢰할 수 있는 루트 인증서 프로필을 선택합니다. 신뢰할 수 있는 루트 인증서 프로필을 만드는 방법에 대한 자세한 내용은 [인증서 프로필을 통해 리소스 액세스 보안](secure-resource-access-with-certificate-profiles.md)을 참조하세요.|EAP 유형 **EAP-TLS**, **PEAP**, **EAP-TTLS** 또는 **EAP-FAST**를 선택한 경우|
|**PAC(보호된 액세스 자격 증명) 사용**|인증 서버와 클라이언트 간의 인증된 터널을 설정하기 위해 보호된 액세스 자격 증명을 사용하려는 경우 선택합니다. 기존 PAC 파일에 있는 경우 사용됩니다.|**EAP 유형**이 **EAP-FAST**인 경우|
|**PAC 프로 비전**|장치에서 PAC 파일을 설정합니다.<br /><br />이 설정을 사용하는 경우에는 서버를 인증하지 않아도 PAC 파일이 설정되도록 **익명으로 PAC 프로비전**을 선택할 수도 있습니다.|**PAC(보호된 액세스 자격 증명) 사용**을 선택한 경우|
|**인증 방법**|연결에 사용되는 인증 방법을 선택합니다.<br /><br /><ul><li>**인증서** - 클라이언트 인증서를 지정하려는 경우</li><li>**사용자 이름 및 암호** - 인증에 대해 다음과 같은 EAP 이외의 방법(내부 ID라고도 함) 중 하나를 지정하려는 경우<br /><br /><ul><li>**없음**</li><li>**암호화되지 않은 암호(PAP)**</li><li>**CHAP(Challenge Handshake 인증 프로토콜)**</li><li>**MS-CHAP(Microsoft CHAP)**</li><li>**MS-CHAP v2(Microsoft CHAP 버전 2)**</li><li>**EAP-TLS**</li></ul></li></ul>|**EAP 유형**이 **PEAP** 또는 **EAP-TTLS**인 경우|
|**클라이언트 인증을 위해 클라이언트 인증서 선택(ID 인증서)**|연결을 인증하는 데 사용되는 SCEP 인증서 프로필을 선택합니다. SCEP 인증서 프로필을 만드는 방법에 대한 자세한 내용은 [인증서 프로필을 통해 리소스 액세스 보안](secure-resource-access-with-certificate-profiles.md)을 참조하세요.|보안 유형이 **WPA-엔터프라이즈/WPA2-엔터프라이즈**이고 **EAP 유형**이 **EAP-TLS**, **PEAP** 또는 **EAP-TTLS**인 경우|
|**ID 개인 정보 사용(외부 ID)**|EAP ID 요청에 대한 응답으로 전송되는 텍스트를 지정합니다. 이 텍스트에는 원하는 값을 사용할 수 있습니다.<br /><br />인증하는 동안 이 익명 ID가 처음에 전송됩니다. 그런 다음 실제 ID가 보안 터널에서 전송 됩니다.|**EAP 유형**이 **PEAP**, **EAP-TTLS** 또는 **EAP-FAST**로 설정된 경우|


### <a name="see-also"></a>참고 항목
[미리 공유한 키 Wi-Fi 프로필](pre-shared-key-wi-fi-profile.md)에서 미리 공유한 키를 사용하여 Wi-Fi 프로필을 만드는 방법을 알아보세요.
