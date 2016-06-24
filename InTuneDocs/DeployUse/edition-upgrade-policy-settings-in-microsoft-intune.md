---
# required metadata

title: Microsoft Intune에서 Windows 버전 업그레이드 정책 설정 | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8589866a-3f13-489b-a5cd-cee017d16d54

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune에서 Windows 버전 업그레이드 정책 설정
Microsoft Intune **버전 업그레이드 정책**을 사용하면 다음 Windows 10 버전 중 하나를 실행하는 장치를 최신 버전으로 자동으로 업그레이드할 수 있습니다.
* Windows 10 Desktop
* Windows 10 Holographic

## 시작하기 전에
장치를 최신 버전으로 업그레이드하기 전에 다음 중 하나가 있어야 합니다.
* Windows 10 Desktop 버전용 정책에서 대상으로 지정하는 모든 장치에 새 버전의 Windows를 설치하는 데 유효한 제품 키
* Windows 10 Mobile 및 Windows 10 Holographic 버전용 정책에서 대상으로 지정하는 모든 장치에 새 버전의 Windows를 설치하기 위한 라이선스 정보가 포함된 Microsoft 라이선스 파일
* 대상으로 지정한 Windows 10 장치를 Microsoft Intune에 등록해야 합니다.

## 버전 업그레이드 정책 설정

|설정 이름|세부 정보|
|-|-|
|**Name**|버전 업그레이드 정책의 이름을 입력합니다.|
|**설명**|필요에 따라 Intune 콘솔에서 식별하는 데 도움이 되는 정책 설명을 입력합니다.
|**업그레이드할 버전**|드롭다운 목록에서 대상 장치를 업그레이드할 Windows 10 Desktop, Windows 10 Holographic 또는 Windows 10 Mobile 버전을 선택합니다.
|**제품 키**|대상으로 지정된 모든 Windows 10 Desktop 장치를 업그레이드하는 데 사용할 수 있는 Microsoft에서 가져온 제품 키를 지정합니다.<br>제품 키가 포함된 정책을 만든 후에는 나중에 제품 키를 편집할 수 없습니다. 보안상 키가 가려지기 때문입니다. 제품 키를 변경하려면 전체 키를 다시 입력해야 합니다.
|**라이선스 파일**|**찾아보기**를 클릭하여 대상으로 지정된 장치를 업그레이드하려는 Windows Holographic 버전에 대한 라이선스 정보를 포함하는 Microsoft에서 가져온 라이선스 파일을 선택합니다.

### 참고 항목
[Microsoft Intune 정책을 사용하여 장치의 설정 및 기능 관리](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)

<!--HONumber=May16_HO1-->


