---
# required metadata

title: Microsoft Intune에서 장치 그룹 매핑을 사용하여 장치 분류 | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8b8c06a3-6b6c-4cf1-8646-b24fa9b1a39e

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune에서 장치 그룹 매핑을 사용하여 장치 분류
이러한 장치를 쉽게 관리하기 위해 Microsoft Intune **장치 그룹 매핑**을 사용하여 장치를 정의하는 범주에 그룹화할 수 있습니다. 

장치 그룹 매핑에서는 다음 워크플로를 사용합니다.
1. 사용하려는 각 범주에 Intune 장치 그룹을 만듭니다.
2. 선택한 범주를 만든 장치 그룹에 매핑하는 장치 그룹 매핑 규칙을 구성합니다.
3. 최종 사용자가 해당 장치를 등록할 경우 구성한 범주에서 범주를 선택해야 합니다. 선택한 후에 자동으로 만든 해당 장치 그룹에 장치가 추가됩니다.
4. 그런 다음 정책 및 앱을 배포할 때 이러한 장치 그룹을 사용할 수 있습니다.

항목의 예는 다음과 같습니다.
* 개인
* POS(Point of Sale) 장치
* 데모 장치
* 판매
* 계정
* Manager

그러나 원하는 범주를 구성할 수 있습니다.

## 장치 그룹 매핑을 구성하는 방법
1. 사용하려는 각 장치 범주에 Intune 장치 그룹을 만듭니다. 그룹을 만드는 방법에 대한 자세한 내용은 [Microsoft Intune에서 그룹을 사용하여 사용자 및 장치 관리](use-groups-to-manage-users-and-devices-with-microsoft-intune.md)를 참조하세요..
2. [Microsoft Intune 관리 콘솔](https://manage.microsoft.com)에서 **관리**를 클릭합니다..
3. **관리** 작업 영역에서 **모바일 장치 관리**를 확장한 후 **장치 그룹 매핑**을 클릭합니다..
4. **장치 그룹 매핑** 페이지에서 장치 그룹 매핑을 사용합니다.
5. **추가**를 클릭하여 새 매핑 규칙을 만듭니다.
6. **추가 장치 그룹 매핑 규칙** 대화 상자에서 만들려는 범주의 이름을 입력하고 드롭다운 목록에서 이 범주를 매핑할 장치 컬렉션을 선택합니다. 작업을 마치면 **추가**를 클릭합니다.
7. 범주 및 그룹 추가를 완료하면 **저장**을 클릭합니다..

이제 사용자가 해당 장치를 등록할 경우 구성한 범주의 목록으로 표시됩니다. 범주를 선택하고 등록을 완료한 후에 이 장치는 선택한 범주에 해당하는 장치 그룹에 추가됩니다.

### 참고 항목
[Microsoft Intune에서 그룹을 사용하여 사용자 및 장치 관리](use-groups-to-manage-users-and-devices-with-microsoft-intune.md)

<!--HONumber=May16_HO1-->


