---
title: "Intune에서 등록 제한 설정"
titlesuffix: Azure portal
description: "Intune에서 플랫폼별로 등록을 제한하고 장치 등록 제한을 설정합니다. \""
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f0a2b858-a824-4598-ab81-bdd8e62ac3b3
ms.reviewer: amyros
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5e55a96ee1bee5b1f25a4ddf3366f3e7dc94122a
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2018
---
# <a name="add-groups-in-intune"></a>Intune에서 그룹 추가
Intune은 Azure AD(Active Directory) 그룹을 사용하여 장치 및 사용자를 관리합니다. Intune 관리자의 경우 조직의 요구에 맞게 그룹을 설정할 수 있습니다. 그룹을 만들어 지리적 위치, 부서 또는 하드웨어 특성별로 사용자 또는 장치를 구성합니다. 그룹을 사용하여 대규모 작업을 관리합니다. 예를 들어 많은 사용자에 대해 정책을 설정하거나 장치 집합에 앱을 배포할 수 있습니다.

이 항목에서는 Intune에서 사용할 그룹을 추가하는 방법을 설명합니다.

다음 유형의 그룹을 추가할 수 있습니다.
- **할당된 그룹** - 수동으로 정적 그룹에 사용자 또는 장치를 추가합니다.
- **동적 그룹** - (Azure Active Directory Premium 사용) 단순 또는 고급 규칙을 사용하여 정의된 사용자 또는 장치 그룹을 동적으로 작성할 수 있습니다.

## <a name="add-a-new-group"></a>새 그룹 추가

새 그룹을 만들려면 다음 단계를 따르세요.
1. Azure Portal에서 **그룹**으로 이동한 다음 **모든 그룹** 블레이드에서 **새 그룹**을 선택합니다.
  ![새 그룹이 선택된 Azure Portal의 스크린샷](./media/groups-add-new.png)
2. 새 그룹의 **이름**과 **설명**을 지정합니다. 이러한 속성은 관리 포털에만 나타나고 사용자에게 표시되지 않습니다.

3. **멤버 자격 유형**을 선택합니다.
  - **할당됨** - 수동으로 할당된 구성원으로 그룹을 만듭니다. [Azure AD 할당된 그룹](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal)에 대해 자세히 알아봅니다.
  - **동적 사용자** - **동적 쿼리**로 정의된 사용자 그룹을 만듭니다.
  - **동적 장치** - **동적 쿼리**로 정의된 장치 그룹을 만듭니다.

  ![이름, 설명, 멤버 자격 유형, Office 기능 사용, 구성원이 포함된 Intune 그룹 속성 스크린샷](./media/groups-add-properties.png)

  Azure AD를 통해 멤버 자격을 정의하는 규칙에 따라 동적 그룹을 만들 수 있습니다. [특성 기반 동적 그룹을 만드는 방법](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal)을 알아봅니다.

4. **Office 기능 사용**을 선택하여 사용자 그룹 구성원에게 공유 Office 365 앱에 대한 액세스 권한을 부여할 수 있습니다. [Office 365 그룹](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)에 대해 자세히 알아보세요.
5. 새 그룹을 추가하려면 **만들기**를 선택합니다.

## <a name="see-also"></a>참고 항목
- [Azure Active Directory 그룹을 사용하여 리소스에 대한 액세스 관리](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups)
- [Azure Portal의 Intune 클래식 그룹](groups-get-started.md)
