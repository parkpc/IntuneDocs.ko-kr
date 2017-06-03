---
title: "Windows Phone 8.1에 대한 Intune 장치 제한 설정"
titleSuffix: Intune Azure preview
description: "Intune Azure 미리 보기: Windows Phone 8.1 장치에서 장치 설정 및 기능을 제어하는 데 사용할 수 있는 Intune 설정을 알아봅니다."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c2d42714-49ca-43b3-b080-2e67a4268198
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 754833026331868efebcbcd157e8ce76e3ae35bb
ms.contentlocale: ko-kr
ms.lasthandoff: 05/23/2017


---

# <a name="windows-phone-81-device-restriction-settings-in-microsoft-intune"></a>Microsoft Intune에서 Windows Phone 8.1 장치 제한 설정

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

## <a name="general"></a>일반
-     **Windows Phone 8.1에만 모든 설정 적용** - 클래식 Intune 포털에서 구성할 수 있는 설정입니다. Azure Portal에서는 이 설정을 변경할 수 없습니다. **구성됨**으로 설정된 경우 모든 설정이 Windows Phone 8.1 장치에만 적용됩니다. **구성되지 않음**으로 설정한 경우 Windows 10 Mobile 장치에도 이러한 설정이 적용됩니다.
-     **카메라** - 장치 카메라를 사용하도록 설정하거나 차단합니다.
-     **복사 및 붙여넣기** - 장치에서 복사 및 붙여넣기 기능을 사용하도록 설정하거나 차단합니다.
-     **이동식 저장소** - 장치에서 SD 카드와 같은 이동식 저장소를 사용하도록 허용합니다.
-     **지리적 위치** - 장치에서 위치 정보를 활용할 수 있습니다.
-     **Microsoft 계정** - 사용자가 Microsoft 계정을 장치에 연결하도록 설정하거나 차단합니다.
-     **화면 캡처** - 사용자가 화면의 내용을 이미지 파일로 캡처하도록 허용합니다.
-     **진단 데이터 제출** - 장치에서 Microsoft에 진단 정보를 제출할 수 있습니다.
-     **사용자 지정 메일 계정 동기화** - 장치가 타사 메일 계정에 연결할 수 있습니다.

## <a name="password"></a>암호
-     **Windows Phone 8.1에만 모든 설정 적용** - 클래식 Intune 포털에서 구성할 수 있는 설정입니다. Azure Portal에서는 이 설정을 변경할 수 없습니다. **구성됨**으로 설정된 경우 모든 설정이 Windows Phone 8.1 장치에만 적용됩니다. **구성되지 않음**으로 설정한 경우 Windows 10 Mobile 장치에도 이러한 설정이 적용됩니다.
-     **암호 필요** - 최종 사용자에게 장치에 액세스하려면 암호를 입력하도록 요구합니다.
    -     **필수 암호 유형** - 숫자만 또는 영숫자와 같이 필요한 암호의 유형을 지정합니다.
    -     **최소 암호 길이** - 암호에 필요한 최소 문자 수를 지정합니다.
    -     **단순 암호** - '0000' 및 '1234'와 같은 단순한 암호를 사용할 수 있도록 지정합니다.
    -     **장치를 초기화하기 전 로그인 오류 발생 횟수** - 장치를 초기화하기 전까지 잘못된 암호 입력이 허용되는 횟수를 지정합니다.
    -     **화면이 잠기기 전까지 최대 비활성 시간(분)** - 화면이 자동으로 잠기기 전에 장치가 유휴 상태로 유지되어야 할 시간을 지정합니다.
    -     **암호 만료(일)** - 장치 암호를 변경해야 할 때까지의 기간(일)을 지정합니다.
    -     **이전 암호 다시 사용 방지** - 기억할 이전에 사용한 암호의 수를 지정합니다.
-     **암호화** - 지원되는 모바일 장치의 데이터를 암호화해야 합니다.

## <a name="app-store"></a>앱 스토어
-     **Windows Phone 8.1에만 모든 설정 적용** - 클래식 Intune 포털에서 구성할 수 있는 설정입니다. Azure Portal에서는 이 설정을 변경할 수 없습니다. **구성됨**으로 설정된 경우 모든 설정이 Windows Phone 8.1 장치에만 적용됩니다. **구성되지 않음**으로 설정한 경우 Windows 10 Mobile 장치에도 이러한 설정이 적용됩니다.
-     **앱 스토어** - 사용자가 장치에서 앱 스토어에 연결하도록 허용합니다.

## <a name="restricted-apps"></a>제한된 앱

-     **Windows Phone 8.1에만 모든 설정 적용** - 클래식 Intune 포털에서 구성할 수 있는 설정입니다. Azure Portal에서는 이 설정을 변경할 수 없습니다. **구성됨**으로 설정된 경우 모든 설정이 Windows Phone 8.1 장치에만 적용됩니다. **구성되지 않음**으로 설정한 경우 Windows 10 Mobile 장치에도 이러한 설정이 적용됩니다.

제한된 앱 목록에서 다음 목록 중 하나를 구성할 수 있습니다.

**차단된 앱** 목록 - 사용자가 설치하거나 실행할 수 없고 Intune에서 관리되지 않는 앱을 나열합니다.
**허용된 앱** 목록 - 사용자가 설치할 수 있는 앱을 나열합니다. Intune에서 관리되는 앱은 자동으로 허용됩니다.

목록을 구성하려면 **추가**를 클릭한 다음 원하는 이름, 앱 게시자(선택 사항) 및 앱 스토어의 앱 URL을 지정합니다.

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a>스토어의 앱에 대한 URL을 지정하는 방법

허용 및 차단된 앱 목록에 앱 URL을 지정하려면 다음 형식을 사용합니다.

[Windows Phone 스토어](https://www.microsoft.com/store/apps/windows-phone) 페이지에서 사용하려는 앱을 검색합니다.

앱 페이지를 열고 클립보드에 URL을 복사합니다. 이제 이 URL을 허용되는 앱 또는 차단되는 앱 목록에서 URL로 사용할 수 있습니다.

예: 스토어에서 Skype 앱을 검색합니다. 사용하는 URL이 **http://www.windowsphone.com/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51**이 됩니다.



### <a name="additional-options"></a>추가 옵션

**가져오기**를 클릭하여 <*앱 URL*>, <*앱 이름*>, <*앱 게시자*> 형식으로 csv 파일에서 목록을 채우거나 **내보내기**를 클릭하여 같은 형식으로 제한된 앱 목록 내용이 포함된 csv 파일을 만들 수도 있습니다.


## <a name="browser"></a>브라우저
-     **Windows Phone 8.1에만 모든 설정 적용** - 클래식 Intune 포털에서 구성할 수 있는 설정입니다. Azure Portal에서는 이 설정을 변경할 수 없습니다. **구성됨**으로 설정된 경우 모든 설정이 Windows Phone 8.1 장치에만 적용됩니다. **구성되지 않음**으로 설정한 경우 Windows 10 Mobile 장치에도 이러한 설정이 적용됩니다.
-     **웹 브라우저** - 장치의 기본 제공되는 웹 브라우저를 사용하도록 설정하거나 차단합니다.

## <a name="cellular-and-connectivity"></a>셀룰러 및 연결
-     **Windows Phone 8.1에만 모든 설정 적용** - 클래식 Intune 포털에서 구성할 수 있는 설정입니다. Azure Portal에서는 이 설정을 변경할 수 없습니다. **구성됨**으로 설정된 경우 모든 설정이 Windows Phone 8.1 장치에만 적용됩니다. **구성되지 않음**으로 설정한 경우 Windows 10 Mobile 장치에도 이러한 설정이 적용됩니다.
-     **Wi-Fi** - 장치의 Wi-Fi 기능을 사용하거나 사용하지 않도록 설정합니다.
-     **Wi-Fi 테더링** - 장치의 Wi-Fi 테더링을 사용할 수 있습니다.
-     **자동으로 Wi-Fi 핫스팟에 연결** - 장치가 무료 Wi-Fi 핫스폿에 자동으로 연결하고 사용 약관을 자동으로 수락할 수 있습니다.
-     **Wi-Fi 핫스팟 보고** - 사용자가 부근의 연결을 쉽게 검색할 수 있도록 Wi-Fi 연결에 관한 정보를 보냅니다.
-     **NFC** - 지원하는 장치에서 근거리 통신을 사용하는 작업을 사용하거나 사용하지 않도록 설정합니다.
-     **Bluetooth** - 장치의 Bluetooth 기능을 사용하거나 사용하지 않도록 설정합니다.
