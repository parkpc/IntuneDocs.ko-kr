---
# required metadata

title: Microsoft Intune에서 규정 준수 정책 배포 및 모니터링 | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: d8f246d4-0d86-4c8b-a1bf-9977985506d8

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: chrisgre
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune에서 장치 규정 준수 정책 배포 및 모니터링
## 준수 정책 배포
조직에서 하나 이상의 사용자 또는 장치 그룹에 [만든](create-a-device-compliance-policy-in-microsoft-intune.md) 준수 정책을 배포합니다.

1.  **정책** 작업 영역에서 배포할 정책을 선택한 다음 **배포 관리**를 선택합니다.
![맨 위에 있는 배포 관리 메뉴 옵션을 표시하는 규정 준수 정책 페이지의 스크린 샷](./media/intune-sa-3c-deploy-compliance-policy2.png)

2.  **배포 관리** 대화 상자에서 정책을 배포하려는 그룹을 하나 이상 선택하고 **추가 > 확인**을 선택합니다.
![관리 배포 대화 상자 스크린샷](./media/intune-sa-3d-deploy-compliance-policy3-Manage.png) 사용자 및/또는 장치에 규정 준수 정책을 배포할 수 있습니다. 이미 만들어 Intune에 동기화한 Active Directory 그룹을 사용하거나, Intune 콘솔에서 이러한 그룹을 수동으로 만듭니다. 정책을 배포하는 방법에 대해 자세히 알아보려면 [구성 정책 배포](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)를 참조하세요.

**정책** 작업 영역의 **개요** 페이지에 있는 상태 요약 및 경고는 주의가 필요한 정책 문제를 식별합니다. 또한 상태 요약은 **대시보드** 작업 영역에 표시됩니다.

> [!IMPORTANT]규정 준수 정책을 배포하지 않은 상태에서 Exchange 조건부 액세스 정책을 사용하도록 설정하면 대상으로 지정된 모든 장치에 액세스가 허용됩니다.

## Intune 정책 충돌을 해결하는 방법
정책 충돌은 장치에 여러 Intune 정책을 적용하는 동안 발생할 수 있습니다. 정책 설정이 겹치면 Intune에서는 다음 규칙을 사용하여 충돌을 해결합니다.

-   Intune 구성 정책과 규정 준수 정책에 충돌하는 설정이 있는 경우 규성 정책 설정이 더 안전하더라도 구성 정책 설정보다 규정 준수 정책 설정이 우선시됩니다.

-   여러 규정 준수 정책을 배포한 경우 정책 중 가장 안전한 정책이 사용됩니다.

## 규정 준수 정책 모니터링

#### 준수 정책을 준수하지 않는 장치를 보려면

1.  [Microsoft Intune 관리 콘솔](https://manage.microsoft.com)에서 **그룹 > 모든 장치**를 선택합니다.

2.  장치 목록에서 장치 이름을 두 번 클릭합니다.

3.  **정책** 탭을 선택하여 해당 장치에 대한 정책 목록을 표시합니다.

4.  **필터** 드롭다운 목록에서 **준수 정책을 준수하지 않음**을 선택합니다.
![필터 목록에서 옵션 목록을 보여 주는 스크린 샷](./media/intune-sa-3e-view-device-noncompliance.png)

#### 상태 증명 보고서를 보려면

1.  [Microsoft Intune 관리 콘솔](https://manage.microsoft.com)에서 **보고서**를 선택합니다.

2.  **상태 증명 보고서 - 새 보고서 만들기** 페이지에서는 Intune에서 수집한 모든 Windows 10 상태 증명 데이터가 포함된 보고서를 볼 수 있습니다. 필터를 사용하여 데이터 하위 집합으로 보고서를 만들 수도 있습니다. 필터는 장치 유형, 운영 체제 또는 데이터 요소 하위 집합만 기반으로 할 수 있습니다.


## 다음 단계
이제 사용자의 조직에서 서비스에 대 한 액세스를 제어하려면 조건부 액세스 정책과 함께 규정 준수 정책을 사용할 수 있습니다.

[전자 메일 및 O365 서비스에 대한 액세스 제한](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)


### 참고 항목
[Intune에서 장치 규정 준수 정책 소개](introduction-to-device-compliance-policies-in-microsoft-intune.md)


<!--HONumber=Jun16_HO2-->


