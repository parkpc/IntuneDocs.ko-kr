---
title: "사용자 및 장치를 구성하는 그룹 만들기 | Microsoft Intune"
description: "Microsoft Intune 무료 30일 평가판을 등록할 때 장치 그룹 및 사용자 그룹을 만드는 방법"
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 11/28/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7162cad3-5c14-43f3-a760-833ffd7786b1
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: ab451a1213923ecd27dfc0b8ca353041e70435ed


---

# <a name="create-groups-to-organize-evaluation-subscription-users-and-devices"></a>평가판 구독 사용자 및 장치를 구성하는 그룹 만들기
Intune의 그룹을 통해 장치 및 사용자를 매우 유연하게 관리할 수 있습니다. 지리적 위치, 부서, 하드웨어 특성 등의 조직 요구 사항에 맞게 그룹을 설정한 후 사용자 집합에 대한 정책 설정, 장치 집합에 대한 응용 프로그램 배포 등의 다양한 관리 작업을 수행하는 데 사용할 수 있습니다.

## <a name="create-a-device-group"></a>장치 그룹 만들기
장치 그룹을 사용하여 소프트웨어와 업데이트를 배포하고, Microsoft Intune 에이전트 설정과 Windows 방화벽 설정 정책을 구성할 수 있습니다. 예를 들어 다음 단계를 수행하면 "내 평가판 장치" 그룹을 설정할 수 있습니다.

1.  [Intune 관리 콘솔](https://manage.microsoft.com/)에서 **그룹** &gt; **개요** &gt; **그룹 만들기**를 선택합니다.

2.  **그룹 이름**에 "내 평가판 장치"를 입력하고 상위 그룹 목록에서 **모든 장치**를 선택한 후 **다음**을 선택합니다.

3.  **회원 기준 정의** 페이지에서 **모든 장치**를 선택하여 그룹에 모바일 장치와 컴퓨터가 모두 포함되도록 합니다.

4.  **직접 회원 관리 정의** 페이지에서 **다음**을 선택합니다. 이전에 만든 그룹에 모든 장치가 포함되어 있지 않으며 특정 장치를 새 그룹에 추가하려는 경우 이 단계에서 추가할 수 있습니다.

5.  **요약** 페이지에서 수행할 작업을 검토한 후 **마침**을 선택합니다.

새로 만든 그룹은 **모든 장치** 의 **그룹** 작업 영역에 있는 **그룹**목록에서 찾아볼 수 있습니다. 여기에서 그룹을 편집하거나 삭제할 수도 있습니다.

## <a name="create-a-user-group"></a>사용자 그룹 만들기
사용자 그룹을 사용하여 소프트웨어 및 장치 정책을 배포합니다. 예를 들어 다음 단계를 수행하면 "내 평가판 사용자" 그룹을 설정할 수 있습니다.

1.  [Intune 관리 콘솔](https://manage.microsoft.com/)에서 **그룹** &gt; **개요** &gt; **그룹 만들기**를 선택합니다.

2.  **그룹 이름**에 "내 평가판 사용자"를 입력하고 상위 그룹 목록에서 **모든 사용자**를 선택한 후 **다음**을 선택합니다.

3.   **멤버 자격 기준 정의** 페이지에서 **다음으로 그룹 멤버 자격 시작** 을 **부모 그룹의 모든 사용자**로 설정합니다.

4.  **다음 보안 그룹의 구성원 제외** 옆에 있는 **찾아보기**를 선택한 다음 **회사 관리자**를 선택합니다. 이 예외를 통해 회사 관리자 계정(또는 테넌트 관리자)에 영향을 주지 않고 내 평가판 사용자 그룹을 관리할 수 있습니다.

5.  **직접 회원 관리 정의** 페이지에서 **다음**을 선택합니다. 내 평가판 사용자 그룹에 회사 관리자를 제외한 모든 사용자를 포함하려고 하기 때문에 여기서는 어떤 작업도 수행할 필요가 없습니다.

6.  **요약** 페이지에서 수행할 작업을 검토한 후 **마침**을 선택합니다.

새로 만든 그룹은 **모든 사용자** 의 **그룹** 작업 영역에 있는 **그룹**목록에서 찾아볼 수 있습니다. 여기에서 그룹을 편집하거나 삭제할 수도 있습니다.

그룹을 사용하는 방법에 대한 자세한 내용은 [Microsoft Intune에서 그룹을 사용하여 사용자 및 장치 관리](/Intune/Deploy-Use/use-groups-to-manage-users-and-devices-with-microsoft-intune)를 참조하세요.

## <a name="next-steps"></a>다음 단계
[정책 만들기](get-started-with-a-30-day-trial-of-microsoft-intune-step-4.md)  



<!--HONumber=Nov16_HO5-->


