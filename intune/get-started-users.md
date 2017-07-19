---
title: "사용자 시작"
titleSuffix: Intune on Azure
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 06/27/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 22a232de-ab93-44ab-b0b5-d2b3ccb007fe
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: fc1c4f6d18fd78f455be8e333bb765080184c908
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2017
---
# <a name="get-started-with-users"></a>사용자 시작

![Azure의 일반 사용자](/intune/media/generic-intune-user.png)

Azure AD는 장치, 앱 등의 조직 개체 그룹과 사용자 그룹을 관리합니다. 각 장치를 개별적으로 관리할 필요 없이 사용자 또는 장치를 그룹화할 수 있습니다. 이렇게 하면 다수의 사용자 및 장치에 앱과 설정을 쉽게 할당할 수 있습니다.

## <a name="how-do-i-create-a-user"></a>사용자를 만들려면 어떻게 하나요?

1. [Azure 포털](https://portal.azure.com)에 로그인합니다.
2. **리소스 검색**를 사용하여 **사용자 및 그룹**을 검색합니다.
3. **사용자 및 그룹** 블레이드를 연 후 **모든 사용자**를 선택한 다음 **+ 새 사용자**를 선택합니다.
4. **이름** 및 **사용자 이름**과 같은 사용자 정보를 입력합니다. 사용자 이름의 도메인 이름 부분은 초기 기본 도메인 이름인 "contoso.onmicrosoft.com" 도메인 이름 또는 "contoso.com"과 같은 페더레이션되지 않은 확인된 도메인 이름이어야 합니다.
5. **그룹**에서 사용자를 추가할 테스트 그룹을 선택합니다.
6. 테스트 장치에 로그인하는 데 사용할 수 있도록 자동으로 생성된 사용자 암호를 저장합니다. 기억할 수 있는 일반적인 암호로 변경할 수 있도록 이 암호를 사용자에게 제공해야 합니다.
7. **사용자** 블레이드에서 **만들기**를 선택합니다.

## <a name="assigning-licenses-to-users"></a>사용자에게 라이선스 할당

사용자를 만든 후 [Office 365 포털](http://go.microsoft.com/fwlink/p/?LinkId=698854)을 사용하여 해당 사용자에게 Intune 라이선스를 할당해야 합니다. 라이선스를 할당하지 않으면 해당 장치를 관리에 등록할 수 없습니다.

1. Intune에 로그인하는 데 사용한 것과 동일한 자격 증명으로 [Office 365 포털](http://go.microsoft.com/fwlink/p/?LinkId=698854)에 로그인합니다.
2. **사용자** > **활성 사용자**를 선택한 다음 이전에 만든 사용자를 선택합니다.
3. 사용자 정보가 모두 로드될 때까지 잠시 기다려야 할 수도 있습니다. 로드되고 나면 사용자의 **제품 라이선스**에 대해 **편집**을 선택합니다.
4. 사용자에게 **위치**를 할당한 다음 Intune을 **켜기**로 전환합니다.

 > [!NOTE]
 > 그러면 라이선스 중 하나가 이 사용자에 사용됩니다. 라이브 환경을 사용하는 경우 나중에 실제 사용자에게 다시 할당하기 위해 이 라이선스 사용을 해제할 수 있습니다.

5. **저장**을 선택합니다.
