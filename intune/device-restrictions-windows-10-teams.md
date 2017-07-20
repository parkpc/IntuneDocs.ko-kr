---
title: "Windows 10 Team에 대한 Intune 장치 제한"
titleSuffix: Intune on Azure
description: "Windows 10 Team 장치에 사용할 수 있는 장치 제한을 알아봅니다.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 677c41a2-5344-4c52-85f0-809dce3a5d5b
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6e7e6e5093b09d7a221083cd36a8d3e5ecbbb8c2
ms.sourcegitcommit: f100c943a635f5a08254ba7cf30f1aaebb7e810e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/13/2017
---
# <a name="windows-10-team-device-restriction-settings-in-microsoft-intune"></a>Microsoft Intune의 Windows 10 Team 장치 제한 설정

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

- **방에 사람이 들어오면 화면 켜기** - 센서가 방에서 사람을 감지하면 장치가 자동으로 켜지도록 합니다.
- **무선 프로젝션용 PIN** - 장치의 무선 프로젝션 기능을 사용하려면 PIN을 입력해야 하는지 여부를 지정합니다.
- **Miracast 무선 프로젝션** - Windows 10 Team 장치에서 Miracast 지원 장치를 프로젝트에 사용할 수 있도록 하려면 이 옵션을 선택합니다.
- **시작 화면에 표시되는 모임 정보** - 시작 화면의 모임 타일에 표시되는 정보를 선택하려면 이 옵션을 사용합니다. 다음과 같습니다.
    - **이끌이 및 시간만 표시**
    - **이끌이, 시간 및 제목 표시(비공개 모임의 경우 제목이 숨겨짐)**
- **시작 화면 배경 이미지 URL** - 지정한 URL에서 Windows 10 Team 장치의 **시작** 화면에 사용자 지정 배경을 표시하려면 이 설정을 사용하도록 설정합니다.<br>이미지는 PNG 형식이어야 하며 URL은 **https://**로 시작되어야 합니다.
- **업데이트 유지 관리 창** - 장치를 업데이트할 수 있는 기간을 구성합니다. 시작 시간 및 지속 기간(1-5시간)을 구성할 수 있습니다.
- **Azure Operational Insights** - Microsoft Operations Manager 제품군에 포함되어 있는 Azure Operational Insights는 Windows 10 Team 장치에서 로그 파일 데이터를 수집, 저장 및 분석합니다.<br>Azure Operational insights에 연결하려면 **작업 영역 ID** 및 **작업 영역 키**를 지정해야 합니다.

## <a name="next-steps"></a>다음 단계

[장치 제한 설정 구성 방법](device-restrictions-configure.md) 정보를 사용하여 사용자 및 장치에 프로필을 저장하고 할당하세요.
