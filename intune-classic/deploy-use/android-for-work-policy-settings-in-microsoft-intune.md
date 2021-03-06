﻿---
title: "Android for Work 정책 설정"
description: "Intune으로 관리하는 Android for Work 장치에서 설정 및 기능을 제어하는 정책을 만듭니다."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 02/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 35a53076-74d6-486d-b201-e0da2e170008
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0938e4b788ef11a773854531f570e63809389fad
ms.sourcegitcommit: 3b397b1dcb780e2f82a3d8fba693773f1a9fcde1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2017
---
# <a name="android-for-work-policy-settings-in-microsoft-intune"></a>Microsoft Intune에서 Android for Work 정책 설정

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune은 [Android for Work 장치](android-for-work.md)에서 구성할 수 있는 기본 제공 일반 설정의 범위를 제공합니다.

## <a name="general-configuration-policy"></a>일반 구성 정책

Intune **Android for Work 일반 구성 정책**을 사용하여 Android for Work 장치에 대한 보안 및 업무용 프로필 설정을 구성합니다.

이 항목에 표시되지 않은 설정을 찾는 경우, OMA-URI 설정을 사용하여 장치를 제어할 수 있는 Android 사용자 지정 정책을 사용하여 만들 수 있습니다. 자세한 내용은 나중에 이 항목에서 [사용자 지정 정책 설정](#custom-policy-settings)으로 이동하세요.

> [!TIP]
> 업무용 프로필을 프로비전할 경우 장치는 자동으로 암호화됩니다. 이 설정을 변경할 수 없습니다.

### <a name="password-settings"></a>암호 설정

|설정 이름|세부 정보|
|----------------|-|
|**모바일 장치의 잠금을 해제하는 데 암호 필요**|관리되는 장치에 암호 필요 여부를 지정합니다. 다음 중에서 선택합니다.<br><br>- **복합** – 문자, 숫자, 기호가 하나 이상 필요합니다.<br>- **영숫자** - 숫자 하나 이상, 영문자가 하나 필요합니다.<br>- **알파벳** – 적어도 문자와 기호가 필요합니다.<br>- **복합 숫자** – 반복되거나 연속되지 않는 숫자와 문자가 필요합니다.<br>- **숫자**<br><br>이 설정을 사용하도록 설정하지 않으면 복잡성 요구 사항이 없습니다.|
|**최소 암호 길이**|암호에 최소 문자 또는 숫자 수를 지정합니다.|
|**장치가 잠기기 전까지 비활성 상태인 시간(분)**|장치가 자동으로 잠기기 전까지의 사용자 활동이 없는 시간(분)을 지정합니다.|
|**스마트 잠금 및 기타 신뢰 에이전트 허용**<br>(Android 6 이상)|호환되는 Android 장치의 스마트 잠금 기능을 제어하도록 허용합니다. 신뢰 에이전트라고도 하는 이 전화 기능을 통해 장치가 특정 Bluetooth 장치에 연결된 경우 또는 NFC 태그에 가까이 있는 경우와 같이 신뢰할 수 있는 위치에 있는 경우 장치 잠금 화면 암호를 사용하지 않도록 설정하거나 무시할 수 있습니다. 이 설정을 사용하면 사용자가 스마트 잠금 기능을 구성하는 것을 방지할 수 있습니다.|
|**회사 프로필을 삭제하기 전까지 허용되는 로그인 반복 오류 횟수**|장치의 업무용 프로필을 제거하기 전까지 허용되는 로그인 오류 횟수를 지정합니다. 전체 장치 초기화는 수행되지 않습니다.|
|**암호 기록 기억**|이전에 사용한 암호를 다시 사용할 수 없습니다.|
|**암호 기록 기억** - **이전 암호 다시 사용 안 함**|이전에 사용했으며 기억해야 할 암호의 수를 지정합니다.|
|**암호 만료(일)**|장치 암호를 변경해야 할 때까지의 기간(일)을 지정합니다.|
|**지문 잠금 해제 허용**<br>(Android 6 이상)|지문을 사용하여 이 기능을 사용하는 장치를 잠글 수 있습니다.|


### <a name="work-profile-settings"></a>업무용 프로필 설정

|설정 이름|세부 정보|
|----------------|-|
|**회사 및 개인 프로필 간의 데이터 공유 허용**|업무용 프로필에 있는 앱에서 사용자 개인 프로필의 앱과 데이터를 공유할 수 있습니다. 다음 중에서 선택합니다.<br><br>- **경계를 넘는 공유 금지**<br>- **회사 프로필의 앱에서 개인 프로필의 공유 요청을 처리할 수 있음**<br>- **공유 시 제한 없음**|
|**장치가 잠겼을 때 회사 프로필 알림 숨김**<br>(Android 6 이상)|장치가 잠겨 있는 경우 업무용 프로필에서 알림을 표시할지 여부를 제어합니다.|
|**기본 앱 사용 권한 정책 설정**<br>(Android 6 이상)|업무용 프로필에 있는 모든 앱에 대한 기본 사용 권한 정책을 설정합니다. Android 6부터 앱에서 요구하는 일부 권한이 런타임 시 최종 사용자에게 표시됩니다.  이 정책 설정을 통해 IT 담당자는 회사 프로필에서 사용자에게 앱에 대한 권한을 부여하라는 메시지를 표시할지 여부 및 표시 방법을 결정할 수 있습니다. <br/><br/>예를 들어 IT 담당자는 위치 액세스가 필요한 앱을 회사 프로필에 푸시할 수 있습니다.  일반적으로 사용자에게 앱에 위치 액세스 권한을 부여할지 묻는 대화 상자가 표시되며, 사용자는 이를 승인하거나 거부할 수 있습니다.  이 정책을 통해 IT 담당자는 모든 권한을 메시지 없이 자동으로 부여할지, 메시지 없이 자동으로 거부할지 또는 최종 사용자가 결정하도록 할지 결정할 수 있습니다.|


## <a name="custom-policy-settings"></a>사용자 지정 정책 설정
Microsoft Intune **Android for Work 사용자 지정 구성 정책**을 사용하여 Android for Work 장치에서 기능을 제어하는 데 사용할 수 있는 OMA-URI 설정을 배포합니다. 이는 많은 모바일 장치 제조업체가 장치 기능을 제어하는 데 사용하는 표준 설정입니다.

이 기능은 Intune 정책을 사용하여 구성할 수 없는 Android 설정을 배포할 수 있도록 하기 위한 것입니다.
Intune은 현재 제한된 수의 Android 사용자 지정 정책을 지원합니다. 이 항목의 예제를 참조하여 구성할 수 있는 정책이 무엇인지 알아보세요.

### <a name="general-settings"></a>일반 설정

|설정 이름|세부 정보|
    |----------------|--------------------|
    |**Name**|Intune 콘솔에서 쉽게 식별할 수 있도록 Android 사용자 지정 정책에 대한 고유한 이름을 입력합니다.|
    |**설명**|Android 사용자 지정 정책의 개요에 대한 설명과 찾을 때 도움이 되는 기타 관련 정보를 제공합니다.|

### <a name="oma-uri-settings"></a>OMA URI 설정

   |설정 이름|세부 정보|
    |--------|--------------------|
    |**설정 이름**|설정 목록에서 쉽게 식별할 수 있도록 OMA-URI 설정에 대한 고유한 이름을 입력합니다.|
    |**설정 설명**|설정의 개요에 대한 설명과 찾을 때 도움이 되는 기타 관련 정보를 제공합니다.|
    |**데이터 형식**|이 OMA-URI 설정을 지정할 데이터 형식을 선택합니다. **문자열, 문자열(XML), 날짜 및 시간, 정수, 부동 소수점** 또는 **부울** 중에서 선택합니다.|
    |**OMA-URI(대/소문자 구분)**|설정을 제공하려는 OMA-URI를 지정합니다.|
    |**값**|이전에 지정한 OMA-URI와 연결할 값을 지정합니다.|

### <a name="examples"></a>예

- [미리 공유한 키를 사용하여 Wi-Fi 프로필 만들기](pre-shared-key-wi-fi-profile.md)
- [사용자 지정 정책을 사용하여 Android 장치용 앱별 VPN 프로필 만들기](per-app-vpn-for-android-pulse-secure.md)

### <a name="see-also"></a>참고 항목
[Microsoft Intune 정책을 사용하여 장치의 설정 및 기능 관리](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
