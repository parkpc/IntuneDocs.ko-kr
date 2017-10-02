---
title: "Windows Phone 8.1 정책 설정"
description: "Intune은 Windows Phone 8.1 장치에서 구성할 수 있는 기본 제공 일반 설정의 범위를 제공합니다. 또한, Intune에서 사용할 수 없는 사용자 지정 설정을 만들기 위해 OMA-URI 값을 지정할 수 있습니다."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 10/11/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 83f7469c-272e-43f2-8139-b0d7bc34f43f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 95de34806ebd9faed761b0e64df8c4dc596083c8
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2017
---
# <a name="windows-phone-81-policy-settings-in-microsoft-intune"></a>Microsoft Intune의 Windows Phone 8.1 정책 설정

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune은 Windows Phone 8.1 장치에서 구성할 수 있는 기본 제공 일반 설정의 범위를 제공합니다. 또한, Intune에서 사용할 수 없는 사용자 지정 설정을 만들기 위해 OMA-URI(Open Mobile Alliance Uniform Resource Identifier) 값을 지정할 수 있습니다.

## <a name="general-configuration-settings"></a>일반 구성 설정

Microsoft Intune **Windows Phone 일반 구성 정책(Windows Phone 8.1 이상)**을 사용하여 Windows Phone 8.1 장치에 대해 다음과 같은 설정을 구성할 수 있습니다.

-   **모바일 장치 보안 설정** – 다양한 기능을 제어할 수 있는 미리 정의된 설정 목록에서 선택합니다.

-   **규격 및 비규격 앱** - 회사에서 준수 또는 미준수 앱 목록을 지정합니다. Windows Phone 장치는 이 앱의 설치를 차단하거나 허용할 수 있습니다.

### <a name="applicability-settings"></a>적용 가능성 설정

|설정 이름|세부 정보|
|----------------|----------------------------------|
|**Windows 10에 모든 구성 적용**|이 정책의 설정을 Windows Phone 8.1 장치 외에 Windows 10 Mobile 장치에도 적용할 수 있습니다.|

### <a name="password-settings"></a>암호 설정

|설정 이름|세부 정보|
|----------------|------|
|**모바일 장치의 잠금을 해제하는 데 암호 필요**|사용자가 자신의 장치 액세스하기 위해 암호를 입력해야 하는지 여부를 지정합니다.|
|**필수 암호 유형**|숫자만 또는 영숫자와 같이 필요한 암호의 유형을 지정합니다.|
|**필수 암호 유형 - 최소 문자 집합 개수**|암호에 포함되어야 하는 다양한 문자 집합 수를 지정합니다. 소문자, 대문자, 숫자, 기호에 해당하는 4가지 문자 집합을 사용할 수 있습니다. 그러나 iOS 장치의 경우에는 암호에 포함되어야 할 기호 문자의 수를 지정합니다.|
|**최소 암호 길이**|암호에 필요한 최소 문자 수를 지정합니다.|
|**단순 암호 허용**|'0000' 및 '1234'와 같은 단순한 암호를 사용할 수 있도록 지정합니다.|
|**장치를 초기화하기 전까지 허용되는 로그인 반복 오류 횟수**|장치를 초기화하기 전까지 잘못된 암호 입력이 허용되는 횟수를 지정합니다.|
|**화면이 잠기기 전까지 비활성 시간(분)**|화면이 자동으로 잠기기 전까지 장치가 유휴 상태를 유지해야 하는 시간의 길이를 지정합니다.|
|**암호 만료(일)**|장치 암호를 변경해야 할 때까지의 기간(일)을 지정합니다.|예|예|
|**암호 기록 기억**|사용자가 이전에 사용한 암호를 다시 사용하는 것을 막기 위해 이전에 사용된 암호를 기억할지 여부를 지정합니다.|
|**암호 기록 기억** – **이전 암호 다시 사용 안 함**|기억할 이전에 사용한 암호의 수를 지정합니다.|

### <a name="encryption-settings"></a>암호화 설정

|설정 이름|세부 정보|
|----------------|------|
|**모바일 장치 암호화 필요**|지원되는 모바일 장치의 데이터를 암호화해야 합니다.|

### <a name="system-settings"></a>시스템 설정

|설정 이름|세부 정보|
|----------------|-----|
|**화면 캡처 허용**|사용자가 화면의 내용을 이미지 파일로 캡처하도록 허용합니다.|
|**진단 데이터 제출 허용**|장치에서 Microsoft에 진단 정보를 제출할 수 있습니다.|

### <a name="cloud-settings--accounts-and-synchronization"></a>클라우드 설정 – 계정 및 동기화

|설정 이름|세부 정보|
|----------------|------|
|**Microsoft 계정 허용**|Microsoft 계정이 장치에 연결될 수 있습니다.|

### <a name="email-settings"></a>전자 메일 설정

|설정 이름|세부 정보|
|----------------|-----|
|**사용자 지정 메일 계정 허용**|장치가 타사 전자 메일 계정에 연결할 수 있습니다.|

### <a name="application-settings---browser"></a>응용 프로그램 설정 - 브라우저

|설정 이름|세부 정보|
|----------------|-----|
|**웹 브라우저 허용**|장치의 기본 제공되는 웹 브라우저를 사용하도록 설정하거나 차단합니다.|

### <a name="application-settings---apps"></a>응용 프로그램 설정 - 앱

|설정 이름|세부 정보|
|----------------|-----|
|**앱 스토어 허용**|사용자가 장치에서 앱 스토어에 연결하도록 허용합니다.|

### <a name="device-capabilities-settings---hardware"></a>장치 기능 설정 - 하드웨어

|설정 이름|세부 정보|
|----------------|-----|
|**카메라 허용**|장치 카메라를 사용하도록 설정하거나 차단합니다.|
|**이동식 저장소 허용**|장치에서 SD 카드와 같은 이동식 저장소를 사용하도록 허용합니다.|
|**Wi-Fi 허용**|장치의 Wi-Fi 기능을 사용하거나 사용하지 않도록 설정합니다.|
|**Wi-Fi 테더링 허용**|장치의 Wi-Fi 테더링을 사용할 수 있습니다.|
|**무료 Wi-Fi 핫스팟에 자동 연결 허용**|장치가 무료 Wi-Fi 핫스폿에 자동으로 연결하고 사용 약관을 자동으로 수락할 수 있습니다.|
|**Wi-Fi 핫스팟 보고 허용**|사용자가 부근의 연결을 쉽게 검색할 수 있도록 Wi-Fi 연결에 관한 정보를 보냅니다.|
|**지리적 위치 허용**|장치에서 위치 정보를 활용할 수 있습니다.|
|**NFC 허용**|NFC(근거리 통신)를 사용하는 작업을 사용하도록 설정합니다.|
|**Bluetooth 허용**|장치의 Bluetooth 기능을 사용하거나 사용하지 않도록 설정합니다.|

### <a name="device-capabilities-settings---features"></a>장치 기능 설정 - 기능

|설정 이름|세부 정보|
|----------------|----|
|**복사 및 붙여넣기 허용**|장치에서 복사 및 붙여넣기 기능을 사용하도록 설정합니다.|

### <a name="settings-for-allowed-and-blocked-apps"></a>허용 및 차단된 앱에 대한 설정
**허용된 앱 및 차단된 앱** 목록 페이지에서 다음 정보를 사용하여 허용하거나 차단할 앱 목록을 지정합니다.

> [!NOTE]
> 단일 정책에는 허용되거나 차단된 앱 목록만 포함될 수 있습니다. 동일한 정책에 둘 다 지정할 수는 없습니다.

|설정 이름|세부 정보|
|----------------|--------------------|
|**나열된 앱을 열 수 없도록 장치 차단**|사용자가 설치하거나 실행할 수 없는, Intune에서 관리되지 않는 앱을 나열합니다.|
|**나열된 앱만 장치에 설치하도록 허용**|사용자가 설치할 수 있는 앱을 나열합니다. 사용자는 다른 앱을 설치할 수 없습니다. Intune에서 관리되는 앱은 자동으로 허용됩니다.|
|**추가**|앱을 선택한 목록에 추가합니다. 원하는 이름, 앱 스토어의 앱 URL 및 앱 게시자(선택 사항)를 지정합니다. 도움말은 이 항목의 뒷부분에 나오는 앱 스토어에 URL을 지정하는 방법을 참조하세요.
|**앱 가져오기**|지정한 앱 목록을 쉼표로 구분된 값 파일로 가져옵니다. 파일의 형식, 응용 프로그램 이름, 게시자, 앱 URL을 사용합니다.|
|**편집**|선택한 앱의 이름, 게시자 및 URL을 편집할 수 있습니다.|
|**삭제**|목록에서 선택한 앱을 삭제합니다.|
> [!IMPORTANT]
> Windows Phone 8.1 장치용으로 사용 가능한 앱 목록을 지정하는 경우 회사 포털 앱을 이 목록에 추가해야 합니다. 그렇지 않으면 앱이 차단됩니다.


### <a name="reference-information-for-allowed-and-blocked-apps"></a>허용 및 차단된 앱에 대한 참조 정보

#### <a name="how-to-specify-urls-to-app-stores"></a>앱 스토어 URL을 지정하는 방법
허용 및 차단된 앱 목록에 앱 URL을 지정하려면 다음 형식을 사용합니다.

[Windows Phone 앱+게임 페이지](http://www.windowsphone.com/store/overview) 에서 사용하려는 앱을 검색합니다.

앱 페이지를 열고 클립보드에 URL을 복사합니다. 이제 이 URL을 허용되는 앱 또는 차단되는 앱 목록에서 URL로 사용할 수 있습니다.

**예:** Skype 앱의 저장소를 검색합니다. 사용하는 URL이 **http://www.windowsphone.com/ko-kr/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51**이 됩니다.

## <a name="custom-policy-settings"></a>사용자 지정 정책 설정
Microsoft Intune **Windows Phone 사용자 지정 구성 정책**을 사용하여 **Windows Phone 8.1 장치**에서 기능을 제어하는 데 사용할 수 있는 OMA-URI 설정을 배포할 수 있습니다. 이는 많은 모바일 장치 제조업체가 장치 기능을 제어하는 데 사용하는 표준 설정입니다.

이 기능을 통해 Intune 일반 구성 정책으로는 구성할 수 없는 Windows Phone 설정을 배포할 수 있습니다. 이러한 정책을 사용하여 구성할 수 있는 설정에 대한 자세한 내용은 [Microsoft Intune 정책을 사용하여 장치의 설정 및 기능 관리](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) 항목을 참조하세요.

Windows Phone 장치에 대한 OMA-URI 설정 만들기에 대한 도움이 필요하면 [Windows Phone 8.1 MDM 프로토콜 설명서](http://technet.microsoft.com/library/dn499787.aspx)를 참조하세요.

### <a name="general-settings"></a>일반 설정

|설정 이름|세부 정보|
|----------------|--------------------|
|**Name**|Intune 콘솔에서 쉽게 식별할 수 있도록 정책에 대한 고유한 이름을 입력합니다.|
|**설명**|정책의 개요에 대한 설명과 찾을 때 도움이 되는 기타 관련 정보를 제공합니다.|

### <a name="oma-uri-settings"></a>OMA-URI 설정

**OMA URI 설정** 섹션에서 **추가**를 클릭하여 설정을 추가합니다. 기존 설정을 편집하거나 삭제할 수도 있습니다.

**OMA URI 설정 추가 또는 편집** 대화 상자에서 다음 정보를 지정합니다.

|설정 이름|세부 정보|
    |--------|--------------------|
    |**설정 이름**|설정 목록에서 쉽게 식별할 수 있도록 OMA-URI 설정에 대한 고유한 이름을 입력합니다.|
    |**설정 설명**|설정의 개요에 대한 설명과 찾을 때 도움이 되는 기타 관련 정보를 제공합니다.|
    |**데이터 형식**|이 OMA-URI 설정을 지정할 데이터 형식을 선택합니다. 다음 중에서 선택합니다.<br /><br />-   **문자열**<br />-   **문자열(XML)**<br />-   **날짜 및 시간**<br />-   **정수**<br />-   **부동 소수점**<br />-   **부울**|
    |**OMA-URI(대/소문자 구분)**|설정을 제공하려는 OMA-URI를 지정합니다.|
    |**값**|이전에 지정한 OMA-URI와 연결할 값을 지정합니다.|

### <a name="see-also"></a>참고 항목
[Microsoft Intune 정책을 사용하여 장치의 설정 및 기능 관리](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
