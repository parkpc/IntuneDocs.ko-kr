---
title: "Android에 대한 Intune 장치 제한 설정 | Intune Azure 미리 보기 | Microsoft Docs"
description: "Intune Azure 미리 보기: Android 장치에서 장치 설정 및 기능을 제어하는 데 사용할 수 있는 Intune 설정을 알아봅니다."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/23/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6bdf714a-5d93-485c-8b52-513635c60cb6
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 74023866802eb4c13e7e9ff97e8048afe7d62409
ms.openlocfilehash: 40e04f1f8e7972bcd72cceae272d8295a496df7a


---

# <a name="android-and-samsung-knox-standard-device-restriction-settings-in-intune-azure-preview"></a>Intune Azure 미리 보기의 Android 및 Samsung KNOX Standard 장치 제한 설정

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="general"></a>일반
-   **카메라** - 장치 카메라를 사용할 수 있습니다.
-   **복사 및 붙여넣기** - 장치의 복사 및 붙여넣기 기능을 사용할 수 있습니다.
-   **앱 간의 클립보드 공유** - 클립보드를 사용하여 앱 간에 복사하여 붙여넣을 수 있습니다(Samsung KNOX Standard에만 해당).
-   **진단 데이터 제출** - 사용자가 장치에서 진단 데이터를 제출하는 것을 중지합니다.    
-   **초기화** - 사용자가 장치를 공장 기본 설정으로 복원할 수 있습니다.
-   **지리적 위치** - 장치에서 위치 정보를 활용할 수 있습니다(Samsung KNOX Standard에만 해당).
-   **전원 끄기** - 사용자가 장치의 전원을 끌 수 있습니다.<br>이 설정을 사용하지 않도록 설정하면 Samsung KNOX Standard 장치에 대한 **장치를 초기화하기 전까지 허용되는 로그인 오류 횟수** 설정이 작동하지 않습니다.
-   **화면 캡처** - 사용자가 화면 콘텐츠를 이미지로 캡처할 수 있습니다.
-   **음성 도우미** - 장치에서 음성 도우미 소프트웨어를 사용할 수 있습니다(Samsung KNOX Standard에만 해당).
-   **YouTube** - 장치에서 YouTube 앱을 사용할 수 있습니다(Samsung KNOX Standard에만 해당).

## <a name="password"></a>암호
-   **암호 필요** - 최종 사용자에게 장치에 액세스하려면 암호를 입력하도록 요구합니다.
-   **최소 암호 길이** - 사용자가 구성해야 하는 암호의 최소 길이(4~16자)를 입력합니다.
-   **화면이 잠기기 전까지 최대 비활성 시간(분)** - 장치가 자동으로 잠길 때까지 비활성 상태로 유지되는 시간(분)을 지정합니다.
-   **장치를 초기화하기 전 로그인 오류 발생 횟수** - 장치를 초기화하기 전까지 허용되는 로그인 오류 횟수를 지정합니다.
-   **암호 만료(일)** - 장치 암호를 변경해야 할 때까지의 기간(일)을 지정합니다.
-   **필수 암호 유형** - 필요한 암호 복잡도 수준과 생체 인식 장치 사용 가능 여부를 지정합니다.
-   **이전 암호 다시 사용 방지** - 최종 사용자가 이전에 사용한 암호를 만드는 것을 중지합니다.
-   **지문 잠금 해제** - 지문을 사용하여 지원되는 장치의 잠금을 해제할 수 있습니다.
-   **Smart Lock 및 기타 신뢰 에이전트** - 호환되는 Android 장치(Samsung KNOX Standard 5.0 이상)에서 Smart Lock 기능을 제어할 수 있습니다. 신뢰 에이전트라고도 하는 이 전화 기능을 통해 장치가 특정 Bluetooth 장치에 연결된 경우 또는 NFC 태그에 가까이 있는 경우와 같이 신뢰할 수 있는 위치에 있는 경우 장치 잠금 화면 암호를 사용하지 않도록 설정하거나 무시할 수 있습니다. 이 설정을 사용하면 최종 사용자가 스마트 잠금을 구성하지 않도록 방지할 수 있습니다.
-   **암호화** - 장치의 파일을 암호화해야 합니다.

## <a name="google-play-store"></a>Google Play 스토어

-   **Google Play 스토어** - 사용자가 장치에서 Google Play 스토어에 액세스할 수 있습니다(Samsung KNOX Standard에만 해당).

## <a name="restricted-apps"></a>제한된 앱

제한된 앱 목록에서 다음 목록 중 하나를 구성할 수 있습니다.

**금지된 앱** 목록 - 사용자가 설치하거나 실행할 수 없고 Intune에서 관리되지 않는 앱을 나열합니다.
**승인된 앱** 목록 - 사용자가 설치할 수 있는 앱을 나열합니다. 호환성을 유지하려면 사용자가 나열되지 않은 앱을 설치하지 않아야 합니다. Intune에서 관리되는 앱은 자동으로 허용됩니다.
제한된 앱 설정이 포함된 장치 프로필을 사용자 그룹에 배포해야 합니다.

목록을 구성하려면 **추가**를 클릭한 다음 원하는 이름, 앱 게시자(선택 사항) 및 앱 스토어의 앱 URL을 지정합니다.

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a>스토어의 앱에 대한 URL을 지정하는 방법

규격 및 비규격 앱 목록에 앱 URL을 지정하려면 다음 단계를 수행합니다.

[Google Play의 앱 섹션](https://play.google.com/store/apps)에서 사용하려는 앱을 검색합니다.

앱 설치 페이지를 열고 클립보드에 URL을 복사합니다. 이제 규격 또는 비규격 앱 목록의 URL로 사용할 수 있습니다.

예: Google Play에서 Microsoft Office Mobile을 검색합니다. 사용하는 URL이 **https://play.google.com/store/apps/details?id=com.microsoft.office.officehub**가 됩니다.

### <a name="additional-options"></a>추가 옵션

**가져오기**를 클릭하여 <*앱 URL*>, <*앱 이름*>, <*앱 게시자*> 형식으로 csv 파일에서 목록을 채우거나 **내보내기**를 클릭하여 같은 형식으로 제한된 앱 목록 내용이 포함된 csv 파일을 만들 수도 있습니다.      

## <a name="browser"></a>브라우저
-   **웹 브라우저** - 장치의 기본 웹 브라우저 사용 가능 여부를 지정합니다.
-   **자동 채우기** - 웹 브라우저의 자동 채우기 기능을 사용할 수 있습니다.
-   **쿠키** - 장치 웹 브라우저가 쿠키를 사용할 수 있습니다.
-   **Javascript** - 장치 웹 브라우저에서 Java 스크립트를 실행할 수 있습니다.
-   **팝업** - 웹 브라우저에서 팝업 차단을 사용할 수 있습니다.

## <a name="cloud-and-storage"></a>클라우드 및 저장소
-   **Google 백업** - Google 백업을 사용할 수 있습니다.
-   **Google 계정 자동 동기화** - Google 계정 설정을 자동으로 동기화할 수 있습니다.
-   **이동식 저장소** - 장치에서 SD 카드와 같은 이동식 저장소를 사용할 수 있습니다(Samsung KNOX Standard에만 해당).
-   **저장소 카드의 암호화** - 장치 저장소 카드를 암호화해야 하는지 여부를 지정합니다.

## <a name="cellular-and-connectivity"></a>셀룰러 및 연결
-   **데이터 로밍** - 장치가 셀룰러 네트워크에 있을 때 데이터 로밍을 사용할 수 있습니다(Samsung KNOX Standard에만 해당).
-   **SMS/MMS 메시징** - 장치에서 SMS 및 MMS 메시징을 사용할 수 있습니다(Samsung KNOX Standard에만 해당).
-   **음성 전화 걸기** - 장치에서 음성 전화 걸기 기능을 사용하거나 사용하지 않도록 설정합니다(Samsung KNOX Standard에만 해당).
-   **음성 로밍** - 장치가 셀룰러 네트워크에 있을 때 음성 로밍을 사용할 수 있습니다(Samsung KNOX Standard에만 해당).
-   **Bluetooth** - 장치에서 Bluetooth를 사용할 수 있습니다(Samsung KNOX Standard에만 해당).
-   **NFC** - 장치에서 지원하는 경우 근거리 통신을 사용하는 작업을 수행할 수 있습니다(Samsung KNOX Standard에만 해당).
-   **Wi-Fi** - 장치에서 Wi-Fi 기능을 사용할 수 있습니다(Samsung KNOX Standard에만 해당).
-   **Wi-Fi 테더링** - 장치에서 Wi-Fi 테더링을 사용할 수 있습니다(Samsung KNOX Standard에만 해당).

## <a name="kiosk"></a>키오스크
-   **관리되는 앱 선택** - 장치가 키오스크 모드에 있을 때 실행할 수 있는 관리 앱을 찾아서 선택합니다(스토어로 연결되는 링크 형태로 지정된 앱은 현재 지원되지 않음). 다른 앱은 장치에서 실행할 수 없습니다.
-   **화면 절전 모드 단추** - 장치에서 화면 절전 모드 해제 단추를 사용하거나 사용하지 않도록 설정합니다.
-   **볼륨 단추** - 장치에서 볼륨 단추를 사용하거나 사용하지 않도록 설정합니다.



<!--HONumber=Feb17_HO1-->


