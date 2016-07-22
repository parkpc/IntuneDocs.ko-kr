---
title: "Windows 팀 구성 정책 설정 | Microsoft Intune"
description: 
keywords: 
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 38194ef3-e26e-4682-958d-14b395fccba1
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 42e21b802fb605c98f688485c3b77703b3950e94
ms.openlocfilehash: b08d52289b94429b1328a7470469a7efdf4d46a7


---

# Microsoft Intune의 Windows 팀 구성 정책 설정
Microsoft Intune **Windows 10 Team 일반 구성 정책**을 사용하여 Microsoft Surface Hub와 같은 등록된 Windows 10 Team 장치에 대한 설정을 구성합니다.

|설정 이름|세부 정보|
|----------------|-----------|
|**방에 사람이 들어오면 화면이 자동으로 켜지도록 허용**|센서가 방에서 사람을 감지하면 장치가 자동으로 켜지도록 합니다.|
|**무선 프로젝션용 PIN 필요**|장치의 무선 프로젝션 기능을 사용하려면 PIN을 입력해야 하는지 여부를 지정합니다.|
|**장치 업데이트에 대한 유지 관리 기간 설정**|장치를 업데이트할 수 있는 기간을 구성합니다. 시작 시간 및 지속 기간(1-5시간)을 구성할 수 있습니다.|
|**Azure Operational Insights 사용**|Microsoft Operations Manager 제품군의 일부인 Azure Operational Insights는 Windows 10 Team 장치에서 로그 파일 데이터를 수집, 저장 및 분석합니다.<br /><br />Azure Operational Insights에 연결하려면 **작업 영역 ID** 및 **작업 영역 키**를 지정해야 합니다.|
|**Miracast 무선 프로젝션 사용**|Windows 10 Team 장치가 Miracast 사용 장치를 통해 프로젝션할 수 있게 하려면 이 옵션을 사용하도록 설정합니다.<br /><br />이 옵션을 사용하도록 설정할 경우 **Miracast 채널 선택**에서 콘텐츠 프로젝션에 사용할 Miracast 채널을 선택합니다.|
|**시작 화면에 표시되는 모임 정보를 선택합니다.**|이 옵션을 사용하도록 설정할 경우 **시작** 화면의 **모임** 타일에 표시되는 정보를 선택할 수 있습니다. 다음과 같습니다.<br /><br />-   **구성 도우미 및 시간만 표시**<br />-   **구성 도우미, 시간 및 제목 표시(비공개 모임의 경우 제목 숨김)**|
|**잠금 화면 배경 이미지 URL**|지정한 URL에서 Windows 10 Team 장치의 **시작** 화면에 사용자 지정 배경을 표시하려면 이 설정을 사용하도록 설정합니다.<br /><br />이미지는 PNG 형식이어야 하며 URL은 **https://**로 시작해야 합니다.|


### 참고 항목
[Microsoft Intune 정책을 사용하여 장치의 설정 및 기능 관리](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)




<!--HONumber=Jun16_HO4-->


