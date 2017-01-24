---
title: "Windows 팀 구성 정책 설정 | Microsoft 문서"
description: "Microsoft Intune **Windows 10 Team 일반 구성 정책**을 사용하여 Microsoft Surface Hub와 같은 등록된 Windows 10 Team 장치에 대한 설정을 구성합니다."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 38194ef3-e26e-4682-958d-14b395fccba1
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e7d1760a10e63233fe7cc7f6fd57a68c5283647c
ms.openlocfilehash: 136f83a7340424b420e4a487a0758992a802ece3


---

# <a name="windows-team-configuration-policy-settings-in-microsoft-intune"></a>Microsoft Intune의 Windows 팀 구성 정책 설정

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune **Windows 10 Team 일반 구성 정책**을 사용하여 Microsoft Surface Hub와 같은 등록된 Windows 10 Team 장치에 대한 설정을 구성합니다.

|설정 이름|세부 정보|
|----------------|-----------|
|**방에 사람이 들어오면 화면이 자동으로 켜지도록 허용**|센서가 방에서 사람을 감지하면 장치가 자동으로 켜지도록 합니다.|
|**무선 프로젝션용 PIN 필요**|장치의 무선 프로젝션 기능을 사용하려면 PIN을 입력해야 하는지 여부를 지정합니다.|
|**장치 업데이트에 대한 유지 관리 기간 설정**|장치를 업데이트할 수 있는 기간을 구성합니다. 시작 시간 및 지속 기간(1-5시간)을 구성할 수 있습니다.|
|**Azure Operational Insights 사용**|Microsoft Operations Manager 제품군에 포함되어 있는 Azure Operational Insights는 Windows 10 Team 장치에서 로그 파일 데이터를 수집, 저장 및 분석합니다.<br /><br />Azure Operational insights에 연결하려면 **작업 영역 ID** 및 **작업 영역 키**를 지정해야 합니다.|
|**Miracast 무선 프로젝션 사용**|Windows 10 Team 장치에서 Miracast 지원 장치를 프로젝션에 사용할 수 있도록 하려면 이 옵션을 사용합니다.<br /><br />이 옵션을 사용하도록 설정하는 경우 **Miracast 채널 선택**에서 콘텐츠 프로젝션에 사용할 Miracast 채널을 선택합니다.|
|**시작 화면에 표시되는 모임 정보 선택**|이 옵션을 사용하도록 설정할 경우 **시작** 화면의 **모임** 타일에 표시되는 정보를 선택할 수 있습니다. 다음과 같습니다.<br /><br />-   **이끌이 및 시간만 표시**<br />-   **이끌이, 시간 및 제목 표시(비공개 모임의 경우 제목이 숨겨짐)**|
|**잠금 화면 배경 이미지 URL**|지정한 URL에서 Windows 10 Team 장치의 **시작** 화면에 사용자 지정 배경을 표시하려면 이 설정을 사용하도록 설정합니다.<br /><br />이미지는 PNG 형식이어야 하며 URL은 **https://**로 시작해야 합니다.|


### <a name="see-also"></a>참고 항목
[Microsoft Intune 정책을 사용하여 장치의 설정 및 기능 관리](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)




<!--HONumber=Dec16_HO5-->


