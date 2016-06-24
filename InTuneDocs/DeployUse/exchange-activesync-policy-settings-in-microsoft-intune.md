---
# required metadata

title: Microsoft Intune의 Exchange ActiveSync 정책 설정 | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: e9cbb826-b155-4df6-abf3-60c6f05b2783

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune의 Exchange ActiveSync 정책 설정
Microsoft Intune **Exchange ActiveSync** 정책을 사용하여 Exchange ActiveSync에 의해 관리되는 장치에서 다양한 특징과 기능을 제어할 수 있도록 해주는 설정을 구성할 수 있습니다.


## 암호 설정

|설정 이름|세부 정보
|----------------|
|**모바일 장치의 잠금을 해제하는 데 암호 필요**|암호를 사용하여 장치를 잠가야 하는지 여부를 지정합니다.<br>(Windows RT를 실행하는 장치에는 적용되지 않음)|
|**필수 암호 유형**|영숫자만 또는 숫자와 같이 필요한 암호의 유형을 지정합니다.|
|**최소 암호 길이**|장치 암호에 필요한 최소 문자 수를 지정합니다.|
|**단순 암호 허용**|단순한 암호에는 '0000' 및 '1234'가 있습니다.|
|**장치를 초기화하기 전까지 허용되는 로그인 반복 오류 횟수**|장치가 초기화되기 전에 올바른 암호 입력에 많은 시도를 허용합니다.|
|**암호 만료(일)**|장치 암호를 변경해야 할 때까지의 기간(일)을 지정합니다.
|**암호 기록 기억**|이전에 사용한 암호의 사용을 허용하지 않을지 여부를 지정합니다.|
|**암호 기록 기억** – **이전 암호 다시 사용 안 함**|다시 사용할 수 없는 이전에 사용한 암호의 수를 지정합니다.|
|**암호를 요구하기 전까지 비활성 시간(분)**|화면이 잠기기 전에 장치가 유휴 상태여야 하는 시간을 지정합니다.

## 암호화 설정

|설정 이름|세부 정보|
|----------------|
|**모바일 장치 암호화 필요**<sup>1</sup>|지원되는 경우 암호화해야 하는 장치의 데이터가 필요합니다.<br>Windows Phone 8 장치의 경우 이 옵션을 **예**로 설정해야 합니다..<br /><br />iOS 장치에서 암호화를 사용하도록 설정하려면 **모바일 장치를 잠금 해제하기 위해 암호 필요**설정을 사용하도록 설정합니다..|
|**메모리 카드 암호화 필요**|(지원되는 장치에서) 암호화될 SD 카드와 같은 외부 저장소에 저장된 데이터가 필요합니다.
<sup>1</sup> Windows 8.1을 실행하는 장치에 대한 추가 정보

-   Windows 8.1을 실행하는 장치에 암호화를 적용하려면 각 장치에 [Windows용 December 2014 MDM 클라이언트 업데이트](http://support.microsoft.com/kb/3013816)를 설치해야 합니다.

-   Windows 8.1 장치에 대해 이 설정을 사용하도록 설정하려면 장치의 모든 사용자가 Microsoft 계정을 가지고 있어야 합니다.

-   암호화가 작동하려면 장치가 Microsoft [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) 하드웨어 인증 요구 사항을 만족해야 합니다.

-   장치에 암호화를 적용하는 경우, 복구 키는 자신의 OneDrive 계정에서 액세스한 Microsoft 계정에서만 액세스할 수 있습니다. 사용자를 대신하여 이 키를 복구할 수 없습니다.

## 전자 메일 설정

|설정 이름|세부 정보
|----------------|
|**사용자가 전자 메일 첨부 파일을 다운로드하도록 허용**|전자 메일 첨부 파일을 장치로 다운로드할 수 있는지 여부를 지정합니다.|
|**전자 메일 동기화 기간**|장치로 동기화될 받은 전자 메일의 일 수를 선택합니다.
|**Exchange ActiveSync를 완전하게 지원하지 않는 모바일 장치가 Exchange와 동기화할 수 있도록 허용**|하나 이상의 Exchange ActiveSync 설정을 지원하지 않는 장치에서 Exchange 액세스를 허용할 것인지 여부를 지정합니다.

## 브라우저 설정

|설정 이름|세부 정보
|----------------|-
|**웹 브라우저 허용**|장치에서 웹 브라우저를 사용할 수 있는지 여부를 지정합니다.<br>(Windows RT 또는 Windows Phone에 대해 사용할 수 없습니다.)

## 하드웨어 설정

|설정 이름|세부 정보
|----------------|
|**카메라 허용**|장치에서 카메라를 사용할 수 있는지 여부를 지정합니다.<br>(Windows RT 또는 Windows Phone에 대해 사용할 수 없습니다.)



### 참고 항목
[Microsoft Intune 정책을 사용하여 장치의 설정 및 기능 관리](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=May16_HO1-->


