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
ms.openlocfilehash: 7aad054f0861522174faa01b979083a818c106af
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/03/2017
---
# <a name="help-users-with-the-troubleshooting-portal-in-microsoft-intune"></a>Microsoft Intune의 문제 해결 포털을 통해 사용자 지원

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

문제 해결 포털에서는 지원 센터 운영자 및 Intune 관리자가 사용자 정보를 보고 사용자 도움 요청을 해결할 수 있습니다. 해당 직원에 지원 센터 운영자를 포함하는 조직에서는 **지원 센터 운영자**를 사용자 그룹에 할당할 수 있으며, 해당 그룹은 문제 해결 블레이드를 사용하여 사용자를 지원할 수 있습니다.

예를 들어 사용자가 Intune과 관련된 기술 문제를 지원 센터에 문의하면 지원 센터 운영자가 사용자 이름을 입력합니다. Intune에서는 다음과 같은 여러 계층 1 문제를 해결하는 데 사용할 수 있는 유용한 데이터를 표시합니다.
- 사용자 상태
- 할당
- 앱 설치 오류
- 규정 준수 문제
- 장치가 응답하지 않음
-   장치가 Wi-Fi 또는 VPN 설정을 가져오지 않음
-   앱 설치 실패


## <a name="add-help-desk-operators"></a>지원 센터 운영자 추가
Intune 관리자의 경우 사용자 그룹에 지원 센터 운영자 역할을 할당할 수 있습니다. 해당 그룹의 구성원은 관리 포털을 사용하여 사용자의 문제점을 해결할 수 있습니다. 각 지원 센터 운영자가 Intune 포털에 액세스하려면 Intune 라이선스가 있어야 합니다. [Intune 라이선스를 할당](licenses-assign.md)하는 방법을 알아봅니다.

지원 센터 사용자를 추가하려면 다음을 수행하세요.
1. 필요한 경우 [Intune에 사용자 추가](users-add.md)
2. [지원 센터 그룹 만들기](groups-add.md) 및 그룹에 사용자 추가
3. 다음 권한이 있는 [RBAC 지원 센터 운영자 역할 할당](role-based-access-control.md#built-in-roles) 또는 [사용자 지정 역할 만들기](role-based-access-control.md#custom-roles):
  - MobileApps: 읽기
  - ManagedApps: 읽기
  - ManagedDevices: 읽기
  - Organization: 읽기
  - DeviceCompliancePolices: 읽기
  - DeviceConfigurations: 읽기

  ![Intune 역할이 강조 표시되고 지원 센터 운영자를 비롯한 기본 제공 역할 목록을 표시하는 Intune 포털 스크린샷](./media/help-desk-user-add.png)

4. 지원 센터 운영자에게 Intune의 서비스 상태를 보고 지원 티켓을 여는 권한을 제공하려면, **서비스 관리자**로서 [사용자에게 관리자 권한 부여](https://docs.microsoft.com/azure/active-directory/active-directory-users-assign-role-azure-portal)를 수행합니다. 이 디렉터리 역할에는 지원 센터 운영자에 필요한 권한보다 많은 권한이 있으므로 **Intune 서비스 관리자** 권한을 부여하지 마세요.

## <a name="access-the-troubleshooting-portal"></a>문제 해결 포털 액세스

지원 센터 직원 및 Intune 관리자는 다음 두 가지 방법으로 문제 해결 포털에 액세스할 수 있습니다.
- 웹 브라우저에서 [http://aka.ms/intunetroubleshooting](http://aka.ms/intunetroubleshooting)을 열어 문제 해결 포털만 보세요.
  ![문제 해결 콘솔의 스크린샷](./media/help-desk-console.png)
- Azure 포털에 로그인하고 **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택한 다음 **도움말 및 지원** > **문제 해결**로 이동합니다.

**사용자 선택**을 클릭하여 사용자와 해당 사용자의 세부 정보를 봅니다.

![사용자 선택 링크가 포함된 Intune 문제 해결 워크로드 스크린샷](media/help-desk-user.png)

## <a name="use-the-troubleshooting-portal"></a>문제 해결 포털 사용

문제 해결 포털에서 **사용자 선택**을 선택하여 사용자의 정보를 볼 수 있습니다. 사용자 정보는 사용자와 장치의 현재 상태를 이해하는 데 유용합니다. 문제 해결 포털에는 다음과 같은 문제 해결 세부 정보가 표시됩니다.
- **계정 상태**
- **사용자 상태**
- 장치 작업이 있는 **장치**
- **그룹 등록**
- **앱 보호 상태**
