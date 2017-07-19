---
title: "기술 지원팀의 문제 해결 포털"
titleSuffix: Intune on Azure
description: "기술 지원팀 직원은 문제 해결 포털을 사용하여 사용자의 기술 문제를 해결합니다."
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1f39c02a-8d8a-4911-b4e1-e8d014dbce95
ms.reviewer: sumitp
ms.custom: intune-azure
ms.openlocfilehash: 7a61c3703cd1016ef63c8baa371c3a21dca127fc
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2017
---
# <a name="help-users-with-the-troubleshooting-portal-in-microsoft-intune"></a>Microsoft Intune의 문제 해결 포털을 통해 사용자 지원

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

문제 해결 포털에서는 지원 센터 운영자 및 Intune 관리자가 사용자 정보를 보고 사용자 도움 요청을 해결할 수 있습니다. 해당 직원에 지원 센터 운영자를 포함하는 조직에서는 **지원 센터 운영자**를 사용자 그룹에 할당할 수 있으며, 해당 그룹은 문제 해결 블레이드를 사용하여 사용자를 지원할 수 있습니다.

예를 들어 사용자가 Intune과 관련된 기술 문제를 지원 센터에 문의하면 지원 센터 운영자가 사용자 이름을 입력합니다. Intune에서는 사용자 상태, 앱 설치 실패, 준수 문제 등 많은 계층 1 문제를 해결하는 데 도움이 되는 관련 정보를 표시합니다. 다음과 같은 문제를 다룹니다.
- 장치가 응답하지 않음
-   장치가 Wi-Fi 또는 VPN 설정을 가져오지 않음
-   앱 설치 실패


## <a name="add-help-desk-operators"></a>지원 센터 운영자 추가
Intune 관리자는 사용자에게 다음 두 가지 방법으로 지원 센터 운영자 권한을 할당할 수 있습니다.
- 기본 제공 **지원 센터 운영자** 역할 할당
- 사용자 지정 역할 만들기 및 할당

## <a name="assign-help-desk-operator-role"></a>지원 센터 운영자 역할 할당
Intune 관리자의 경우 사용자 그룹에 지원 센터 운영자 역할을 할당할 수 있습니다. 해당 그룹의 구성원은 관리 포털을 사용할 수 있습니다. 각 지원 센터 운영자가 Intune 포털에 액세스하려면 Intune 라이선스가 있어야 합니다. [Intune 라이선스를 할당](licenses-assign.md)하는 방법을 알아봅니다.

1. Intune 관리자로 Intune 포털에 로그인한 다음 **Intune 역할**을 선택합니다.
2. **Intune 역할** 워크로드에서 **지원 센터 운영자** > **할당**를 선택한 다음 **할당**을 선택합니다.
  ![Intune 역할이 강조 표시되고 지원 센터 운영자를 비롯한 기본 제공 역할 목록(할당이 강조 표시되고 할당 주위에 빨간색 상자가 있음)을 표시하는 Intune 포털 스크린샷](./media/help-desk-user-assign.png)
3. **할당 이름**(필수), **할당 설명**(선택 사항)을 입력한 다음 **구성원(그룹)** 및 **범위(그룹)**을 할당합니다.
4. 이제 지원 데스크 운영자 역할이 있는 구성원이 문제 해결 포털을 사용할 수 있습니다.

Intune 역할에 대한 자세한 내용은 [Intune 역할](role-based-access-control.md)을 참조하세요.

## <a name="create-a-custom-role-for-troubleshooting"></a>문제 해결을 위한 사용자 지정 역할 만들기
Intune 관리자의 경우 사용자가 조직의 요구에 맞는 사용 권한으로 문제 해결 포털을 사용할 수 있도록 사용자 지정 역할을 만들 수 있습니다. Intune 역할에 대한 자세한 내용은 [Intune 역할](role-based-access-control.md)을 참조하세요.

![Intune 역할이 강조 표시되고 지원 센터 운영자를 비롯한 기본 제공 역할 목록을 표시하는 Intune 포털 스크린샷](./media/help-desk-user-add.png)

지원 센터 보기에 Intune 콘솔을 사용하려면 사용자 지정 지원 센터 역할에 다음과 같은 사용 권한이 있어야 합니다.
- MobileApps: 읽기
- ManagedApps: 읽기
- ManagedDevices: 읽기
- Organization: 읽기

## <a name="access-the-troubleshooting-portal"></a>문제 해결 포털 액세스

지원 센터 직원 및 Intune 관리자는 다음 두 가지 방법으로 문제 해결 포털에 액세스할 수 있습니다.
- 웹 브라우저에서 [http://aka.ms/intunetroubleshooting](http://aka.ms/intunetroubleshooting)을 엽니다.
- Intune 포털에서 **도움말 및 지원** > **문제 해결**로 이동합니다.

![사용자 선택 링크가 포함된 Intune 문제 해결 워크로드 스크린샷](media/help-desk-user.png)

## <a name="use-the-troubleshooting-portal"></a>문제 해결 포털 사용

문제 해결 포털에서 **사용자 선택**을 선택하여 사용자의 정보를 볼 수 있습니다. 사용자 정보는 사용자와 장치의 현재 상태를 이해하는 데 유용합니다. 문제 해결 포털에는 다음과 같은 문제 해결 세부 정보가 표시됩니다.
- **테넌트 상태**
- **사용자 상태**
- **장치** 및 장치 작업
- **그룹 등록**
- **앱 보호 상태**
