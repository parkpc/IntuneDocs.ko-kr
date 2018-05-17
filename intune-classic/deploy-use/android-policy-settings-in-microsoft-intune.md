---
title: Android 및 Samsung KNOX 정책 설정
description: Intune으로 관리하는 Android 장치에서 설정 및 기능을 제어하는 정책을 만듭니다.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 10/20/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 71cc39cf-e726-40fd-8d08-78776e099a4b
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 8d1e20ecd5c6cc1f7bef4541d08a1571a99ac35e
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="android-and-samsung-knox-standard-policy-settings-in-microsoft-intune"></a>Microsoft Intune의 Android 및 Samsung KNOX Standard 정책 설정

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Intune은 Android 장치에서 구성할 수 있는 기본 제공 일반 설정의 범위를 제공합니다. 또한, Intune에서 사용할 수 없는 사용자 지정 설정을 만들기 위해 OMA-URI(Open Mobile Alliance Uniform Resource Identifier) 값을 지정할 수 있습니다.

## <a name="general-configuration-policy"></a>일반 구성 정책

Intune **Android 일반 구성 정책**을 사용하여 다음 설정을 구성할 수 있습니다.

-   **모바일 장치 보안 설정** – 다양한 기능을 제어할 수 있는 미리 정의된 설정 목록에서 선택합니다.

-   **키오스크 모드**(Samsung KNOX Standard 장치만 해당) - 특정 기능만 작동하도록 장치를 잠글 수 있습니다. 예를 들어, 장치에서 지정된 관리되는 앱만 실행할 수 있게 하거나 장치에서 볼륨 단추를 사용되지 않도록 설정할 수 있습니다. 이러한 설정은 POS 장치와 같이 한 가지 기능만 수행하도록 지정된 장치 또는 장치의 데모 모델에 사용할 수 있습니다.

-   **규격 및 비규격 앱** - 회사에서 규격 또는 비규격 앱 목록을 지정합니다. Android 및 iOS 장치에서 **비규격 앱 보고서** 를 사용하여 사용자가 설치한 앱과 목록에 지정한 앱 규격을 비교해서 확인할 수 있습니다. 그렇지만 실제로 앱의 설치를 차단할 수는 없습니다.

> [!TIP]
> 사용자가 개인 앱을 비롯하여 장치에 있는 모든 앱이 평가되고, 비규격 앱이 차단되거나 비규격으로 보고되는 것을 알 수 있도록 사용 약관을 구성할 수 있습니다. 사용자가 각자의 장치를 등록하고 회사 포털을 사용하여 앱을 받으려면 먼저 이러한 사용 약관에 동의해야 합니다. 사용 약관 사용에 대한 자세한 내용은 [Microsoft Intune에서 사용 약관 정책 설정](terms-and-condition-policy-settings-in-microsoft-intune.md)을 참조하세요.

이 항목에 표시되지 않은 설정을 찾는 경우, OMA-URI 설정을 사용하여 장치를 제어할 수 있는 Android 사용자 지정 정책을 사용하여 만들 수 있습니다. 자세한 내용은 나중에 이 항목에서 [사용자 지정 정책 설정](#custom-policy-settings)으로 이동하세요.

### <a name="password-settings"></a>암호 설정

|설정 이름|세부 정보|Android 4.0+|Samsung KNOX Standard|
|----------------|-|----------------|----------------|
|**모바일 장치의 잠금을 해제하는 데 암호 필요**|지원되는 장치에 암호가 필요할지 여부를 지정합니다.|예|예|
|**최소 암호 길이**|암호의 최소 길이를 지정합니다.|예|예|
|**장치를 초기화하기 전까지 허용되는 로그인 반복 오류 횟수**|장치를 초기화하기 전까지 허용되는 로그인 오류 횟수를 지정합니다.|예|예|
|**화면이 잠기기 전까지 비활성 시간(분)**|장치가 자동으로 잠기기 전까지의 비활성 시간(분)을 지정합니다.|예|예|
|**암호 만료(일)**|암호를 변경해야 할 때까지의 기간(일)을 지정합니다.|예|예|
|**암호 기록 기억**|이전에 사용했으며 기억해야 할 암호의 수를 지정합니다.|예|예|
|**암호 기록 기억** - **이전 암호 다시 사용 안 함**|이전 암호 다시 사용을 방지합니다.|예|예|
|**암호 품질**|필요한 암호 복잡도 수준과 생체 인식 장치 사용 가능 여부를 지정합니다.|예|예|
|**지문 잠금 해제 허용**|지문을 사용하여 장치 잠금을 해제할 수 있습니다.|아니요|예|
|**스마트 잠금 및 기타 신뢰 에이전트 허용**<br>(Android 5 이상)|호환되는 Android 장치의 스마트 잠금 기능을 제어하도록 허용합니다. 신뢰 에이전트라고도 하는 이 전화 기능을 통해 장치가 특정 Bluetooth 장치에 연결된 경우 또는 NFC 태그에 가까이 있는 경우와 같이 신뢰할 수 있는 위치에 있는 경우 장치 잠금 화면 암호를 사용하지 않도록 설정하거나 무시할 수 있습니다. 이 설정을 사용하면 사용자가 스마트 잠금 기능을 구성하는 것을 방지할 수 있습니다.|예|아니요|

### <a name="encryption-settings"></a>암호화 설정

|설정 이름|세부 정보|Android 4.0+|Samsung KNOX Standard|
|----------------|---|-------------|----------------|
|**모바일 장치 암호화 필요**|모바일 장치의 파일을 암호화해야 합니다.|예|예|
|**메모리 카드 암호화 필요**|장치 메모리 카드를 암호화해야 하는지 여부를 지정합니다.|아니요|예|

### <a name="system-settings"></a>시스템 설정

|설정 이름|세부 정보|Android 4.0+|Samsung KNOX Standard|
|----------------|---|-------------|----------------|
|**화면 캡처 허용**|사용자가 화면 콘텐츠를 이미지로 캡처하도록 허용합니다.|아니요|예|
|**진단 데이터 제출 허용**|장치에서 Google에 진단 정보를 제출하할 수 있습니다.|아니요|예|
|**초기화 허용**|사용자가 장치를 출하 시 설정으로 초기화할 수 있습니다.|아니요|예|

### <a name="cloud-settings---documents-and-data"></a>클라우드 설정 – 문서 및 데이터

|설정 이름|세부 정보|Android 4.0+|Samsung KNOX Standard|
|----------------|----|------------------------|----------------|
|**Google 백업 허용**|Google 백업을 사용할 수 있습니다.|아니요|예|

### <a name="cloud-settings---accounts-and-synchronization"></a>클라우드 설정 – 계정 및 동기화

|설정 이름|세부 정보|Android 4.0+|Samsung KNOX Standard|
|----------------|-----|-----------|----------------|
|**Google 계정 자동 동기화 허용**|Google 계정 설정을 자동으로 동기화할 수 있습니다.|아니요|예|

### <a name="application-settings---browser"></a>응용 프로그램 설정 - 브라우저

|설정 이름|세부 정보|Android 4.0+|Samsung KNOX Standard|
|----------------|-----|-----------|----------------|
|**웹 브라우저 허용**|장치의 기본 웹 브라우저를 사용할 수 있는지 여부를 지정합니다.|아니요|예|
|**자동 채우기 허용**|웹 브라우저의 자동 채우기 함수를 사용할 수 있습니다.|아니요|예|
|**팝업 차단 허용**|웹 브라우저에서 팝업 차단을 사용할 수 있습니다.|아니요|예|
|**쿠키 허용**|장치 웹 브라우저가 쿠키를 사용할 수 있습니다.|아니요|예|
|**액티브 스크립팅 허용**|장치 웹 브라우저에서 액티브 스크립팅을 사용할 수 있습니다.|아니요|예|

### <a name="application-settings---apps"></a>응용 프로그램 설정 - 앱

|설정 이름|세부 정보|Android 4.0+|Samsung KNOX Standard|
|----------------|----|------------|----------------|
|**Google Play 스토어 허용**|사용자가 장치에서 Google Play 스토어에 액세스할 수 있습니다.|아니요|예|

### <a name="device-capabilities-settings---hardware"></a>장치 기능 설정 - 하드웨어

|설정 이름|세부 정보|Android 4.0+|Samsung KNOX Standard|
|----------------|-----|-----------|----------------|
|**카메라 허용**|장치 카메라를 사용할 수 있습니다.|예|예|
|**이동식 저장소 허용**|장치에서 SD 카드와 같은 이동식 저장소를 사용할 수 있습니다.|아니요|예|
|**Wi-Fi 허용**|장치의 Wi-Fi 기능을 사용할 수 있습니다.|아니요|예|
|**Wi-Fi 테더링 허용**|장치의 Wi-Fi 테더링을 사용할 수 있습니다.|아니요|예|
|**지리적 위치 허용**|장치에서 위치 정보를 활용하도록 허용합니다.|아니요|예|
|**NFC 허용**|장치가 지원하는 경우 작업에서 근거리 통신을 사용할 수 있습니다.|아니요|예|
|**Bluetooth 허용**|장치에서 Bluetooth를 사용할 수 있습니다.|아니요|예|
|**전원 끄기 허용**|사용자가 장치의 전원을 끌 수 있습니다.<br /><br />이 설정을 사용하지 않도록 설정하면 Samsung KNOX Standard 장치에 대한 **장치를 초기화하기 전까지 허용되는 로그인 반복 오류 횟수** 설정이 작동하지 않습니다.|아니요|예|

### <a name="device-capabilities-settings---cellular"></a>장치 기능 설정 - 셀룰러

|설정 이름|세부 정보|Android 4.0+|Samsung KNOX Standard|
|----------------|---|-------------|----------------|
|**음성 로밍 허용**|장치가 셀룰러 네트워크에 있을 때 음성 로밍을 허용합니다.|아니요|예|
|**데이터 로밍 허용**|장치가 셀룰러 네트워크에 있을 때 데이터 로밍을 허용합니다.|아니요|예|
|**SMS/MMS 메시징 허용**|장치에서 SMS 및 MMS 메시지를 허용합니다.|아니요|예|

### <a name="device-capabilities-settings---features"></a>장치 기능 설정 - 기능

|설정 이름|세부 정보|Android 4.0+|Samsung KNOX Standard|
|----------------|----|------------|----------------|
|**음성 지원 허용**|장치에서 음성 도우미 소프트웨어를 사용할 수 있습니다.|아니요|예|
|**음성 전화 걸기 허용**|장치에서 음성 전화 걸기 기능을 활성화하거나 비활성화할 수 있습니다.|아니요|예|
|**복사 및 붙여넣기 허용**|장치에서 복사 및 붙여넣기 기능을 허용합니다.|아니요|예|
|**응용 프로그램 간에 클립보드 공유 허용**|앱 간에 복사 및 붙여넣을 수 있도록 클립보드 사용을 허용합니다.|아니요|예|
|**YouTube 허용**|장치에서 YouTube 사용을 허용합니다.|아니요|예|

### <a name="settings-for-compliant-and-noncompliant-apps"></a>규격 및 비규격 앱에 대한 설정
**규격 &amp; 비규격 앱** 목록에서 다음 정보를 사용하는 규격 또는 비규격 앱 목록을 지정합니다.

> [!NOTE]
> 단일 정책에는 규격 앱 목록이나 비규격 앱 목록만 포함될 수 있습니다. 동일한 정책에 둘 다 지정할 수는 없습니다.

|설정 이름|세부 정보|
|----------------|--------------------|
|**사용자가 나열된 앱을 설치할 때 비호환성 보고**|Intune에서 관리하지 않고, 사용자가 설치하여 실행할 수 없도록 할 앱을 나열합니다. 사용자가 이러한 앱 중 하나를 설치하면 비규격 앱 보고서에 해당 앱이 나타납니다.|
|**사용자가 나열된 앱을 설치할 때 비호환성 보고 안 함**|허용할 앱을 나열합니다. 규격을 유지하려면 사용자는 나열되지 않은 앱을 설치해서는 안 됩니다. Intune에서 관리되는 앱은 자동으로 허용됩니다.|
|**추가**|앱을 선택한 목록에 추가합니다. 앱 이름, 앱 게시자(선택 사항) 및 앱 스토어의 앱 URL을 지정합니다.<br /><br />자세한 내용은 이 항목의 뒷부분에 나오는 [앱 스토어에 URL 지정](#specify-urls-to-app-stores)을 참조하세요.|
|**앱 가져오기**|지정한 앱 목록을 쉼표로 구분된 값 파일로 가져옵니다. 파일의 형식, 응용 프로그램 이름, 게시자, 앱 URL을 사용합니다.|
|**편집**|선택한 앱의 이름, 게시자 및 URL을 편집할 수 있습니다.|
|**삭제**|목록에서 선택한 앱을 삭제합니다.|

규격 및 비규격 앱 설정이 포함된 정책을 사용자 그룹에 배포해야 합니다.

### <a name="kiosk-mode-settings"></a>키오스크 모드 설정
다음과 같이 **Samsung KNOX Standard 장치** 설정을 지정합니다.

|설정 이름|세부 정보|
|----------------|--------------------|
|**장치가 키오스크 모드일 때 실행할 수 있는 관리되는 앱 선택**|**찾아보기**를 선택한 다음, 장치가 키오스크 모드에 있을 때 실행할 수 있는 관리 앱을 선택합니다(스토어로 연결되는 링크 형태로 지정된 앱은 현재 지원되지 않음). 다른 앱은 장치에서 실행할 수 없습니다.|
|**볼륨 단추 허용**|장치에서 볼륨 단추를 사용하거나 사용하지 않도록 설정합니다.|
|**화면 절전 모드 해제 단추 허용**|장치에서 화면 절전 모드 해제 단추를 사용하거나 사용하지 않도록 설정합니다.|

### <a name="reference-information-for-compliant-and-noncompliant-apps"></a>규격 및 비규격 앱에 대한 참조 정보

#### <a name="monitor-compliant-and-noncompliant-apps"></a>규격 및 비규격 앱 모니터링
**비규격 앱 보고서** 를 사용하여 허용 및 차단된 앱의 규정 준수 여부를 확인할 수 있습니다.

###### <a name="to-run-the-noncompliant-apps-report"></a>비규격 앱 보고서를 실행하려면

1.  [Microsoft Intune 관리 콘솔](https://manage.microsoft.com)에서 **보고서** &gt; **비규격 앱 보고서**를 선택합니다.

2.  확인할 장치 그룹을 선택합니다. 그런 다음 규격 앱이나 비규격 앱을 확인할지 또는 둘 다 확인할지를 선택합니다. 마지막으로 **보고서 보기**를 선택합니다.

#### <a name="specify-urls-to-app-stores"></a>앱 스토어 URL 지정
규격 및 비규격 앱 목록에 앱 URL을 지정하려면 다음 단계를 수행합니다.

[Google Play의 앱 섹션](https://play.google.com/store/apps)에서 사용하려는 앱을 검색합니다.

앱 설치 페이지를 열고 클립보드에 URL을 복사합니다. 이제 규격 또는 비규격 앱 목록의 URL로 사용할 수 있습니다.

예: Google Play에서 Microsoft Office Mobile을 검색합니다. 사용할 URL은 **https://play.google.com/store/apps/details?id=com.microsoft.office.officehub** 입니다.

## <a name="custom-policy-settings"></a>사용자 지정 정책 설정
Microsoft Intune **Android 사용자 지정 구성 정책**을 사용하여 Android 장치에서 기능을 제어하는 데 사용할 수 있는 OMA-URI 설정을 배포합니다. 이는 많은 모바일 장치 제조업체가 장치 기능을 제어하는 데 사용하는 표준 설정입니다.

이 기능은 Intune 정책을 사용하여 구성할 수 없는 Android 설정을 배포할 수 있도록 하기 위한 것입니다.
Intune은 현재 제한된 수의 Android 사용자 지정 정책을 지원합니다. 이 항목의 예제를 참조하여 구성할 수 있는 정책이 무엇인지 알아보세요.

### <a name="general-settings"></a>일반 설정

|설정 이름|세부 정보|
    |----------------|--------------------|
    | **Name** |Intune 콘솔에서 쉽게 식별할 수 있도록 Android 사용자 지정 정책에 대한 고유한 이름을 입력합니다.|
    | **설명** |Android 사용자 지정 정책의 개요에 대한 설명과 찾을 때 도움이 되는 기타 관련 정보를 제공합니다.|

### <a name="oma-uri-settings"></a>OMA URI 설정

   |설정 이름|세부 정보|
    |--------|--------------------|
    | **설정 이름** |설정 목록에서 쉽게 식별할 수 있도록 OMA-URI 설정에 대한 고유한 이름을 입력합니다.|
    | **설정 설명** |설정의 개요에 대한 설명과 찾을 때 도움이 되는 기타 관련 정보를 제공합니다.|
    | **데이터 형식** |이 OMA-URI 설정을 지정할 데이터 형식을 선택합니다. **문자열, 문자열(XML), 날짜 및 시간, 정수, 부동 소수점** 또는 **부울** 중에서 선택합니다.|
    | **OMA-URI(대/소문자 구분)** |설정을 제공하려는 OMA-URI를 지정합니다.|
    | **값** |이전에 지정한 OMA-URI와 연결할 값을 지정합니다.|

### <a name="examples"></a>예

- [미리 공유한 키를 사용하여 Wi-Fi 프로필 만들기](pre-shared-key-wi-fi-profile.md)
- [사용자 지정 정책을 사용하여 Android 장치용 앱별 VPN 프로필 만들기](per-app-vpn-for-android-pulse-secure.md)
- [사용자 지정 정책을 사용하여 Samsung KNOX 장치에 대해 앱을 허용하거나 차단](custom-policy-to-allow-and-block-samsung-knox-apps.md)

## <a name="supported-samsung-knox-standard-devices"></a>지원되는 Samsung KNOX Standard 장치

회사 포털 앱이 장치가 [지원 KNOX 장치의 목록](https://www.samsungknox.com/knox-supported-devices/knox-workspace)에 표시되는 경우에만 MDM 등록 중에 삼성 KNOX 정품 인증을 시도합니다. 그러면 KNOX 정품 인증 오류로 인해 MDM 등록을 방해하지 않도록 방지할 수 있습니다. Samsung KNOX 정품 인증을 지원하지 않는 장치는 표준 Android 장치로 등록합니다. Samsung 장치 중 일부에만 KNOX를 지원하는 모델 번호가 있을 수 있습니다. Samsung 장치를 구매하고 배포하기 전에 장치 재판매인과 함께 KNOX 호환성을 검사합니다.

[Intune 지원 장치](/intune/supported-devices-browsers.md#intune-supported-devices) 목록과 함께 지원되는 Samsung KNOX 장치 목록을 찾을 수 있습니다.

### <a name="see-also"></a>참고 항목
[Microsoft Intune 정책을 사용하여 장치의 설정 및 기능 관리](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
