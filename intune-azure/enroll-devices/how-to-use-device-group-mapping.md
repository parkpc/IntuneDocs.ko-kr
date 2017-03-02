---
title: "Intune에서 장치 범주를 사용하는 방법 | Intune Azure 미리 보기 | Microsoft 문서"
description: "Intune Azure 미리 보기: Intune에서 장치를 등록할 때 사용자가 선택할 수 장치 범주를 사용하는 방법을 알아봅니다."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7b668c37-40b9-4c69-8334-5d8344e78c24
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 08dad848a48adad7d9c6f0b5b3286f6550a266bd
ms.openlocfilehash: 57dce5b23b9c8cd878a9ce746e6459a69f1270ff
ms.lasthandoff: 02/15/2017


---

# <a name="map-device-groups"></a>장치 그룹 매핑


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

이러한 장치를 쉽게 관리하기 위해 Microsoft Intune 장치 범주를 사용하여 정의하는 범주를 기반으로 하는 그룹에 장치를 자동으로 추가합니다.

장치 범주에는 다음 워크플로가 사용됩니다.
1.    사용자가 자신의 장치를 등록할 때 선택할 범주 만들기
4.    최종 사용자가 해당 장치를 등록할 경우 구성한 범주 목록에서 범주를 선택해야 합니다. 장치를 이미 등록한 경우 최종 사용자에게 다음번에 회사 포털 앱에 액세스할 때 범주를 선택할지 묻는 메시지가 표시됩니다.


원하는 모든 장치 범주를 만들 수 있습니다. 예를 들면 다음과 같습니다.
- POS(Point of Sale) 장치
- 데모 장치
- 판매
- 계정
- Manager

## <a name="how-to-configure-device-categories"></a>장치 범주를 구성하는 방법

### <a name="step-1---create-device-categories-in-the-intune-blade-of-the-azure-portal"></a>1단계 - Azure Portal의 Intune 블레이드에서 장치 범주 만들기
1. Azure Portal에서 **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
2. **추가 서비스** > **기타** > **Intune**을 선택합니다.
3. **Intune** 블레이드에서 **장치 등록**을 선택합니다.
3. **등록** 블레이드에서 **장치 범주**를 선택합니다.
4. **장치 범주** 페이지에서 **만들기**를 선택하여 새 범주를 추가합니다.
5. 다음 블레이드에서 새 범주의 **이름** 및 선택적 **설명**을 입력합니다.
6. 완료되면 **만들기**를 클릭합니다. 범주 목록에서 방금 만든 범주를 볼 수 있습니다.

2단계에서 Azure Active Directory 보안 그룹을 만들 때 장치 범주 이름을 사용합니다.

### <a name="step-2---create-azure-active-directory-security-groups"></a>2단계 - Azure Active Directory 보안 그룹 만들기
이 단계에서는 장치 범주 및 장치 범주 이름에 따라 Azure Portal에서 동적 그룹을 만듭니다.

계속하려면 Azure Active Directory 설명서에서 [특성을 사용하여 고급 규칙 만들기](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/#using-attributes-to-create-rules-for-device-objects) 항목을 참조하세요. 

이 섹션의 정보를 통해 **deviceCategory** 특성을 사용하는 고급 규칙이 있는 장치 그룹을 만듭니다. 예(**device.deviceCategory-eq** "*<the device category name you got from the Intune portal>*")

장치 그룹을 구성하고 사용자가 해당 장치를 등록한 후에는 구성한 범주의 목록으로 표시됩니다. 범주를 선택하고 등록을 완료한 후에 이 장치는 선택한 범주에 해당하는 Active Directory 보안 그룹에 추가됩니다.

### <a name="how-to-view-the-categories-of-devices-you-manage"></a>관리하는 장치의 범주를 확인하는 방법

1.    Azure Portal에서 **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.

2. Azure Portal의 Intune 블레이드에서 **장치 및 그룹**을 선택합니다.

3.    **관리** 아래에서 **모든 장치**를 클릭합니다.

4.    장치 목록에서 **범주** 열을 확인합니다.

**범주** 열이 표시되지 않으면 **열**을 클릭하고 목록에서 **범주**를 선택한 다음 **적용**을 클릭합니다.

### <a name="to-change-the-category-of-a-device"></a>장치의 범주를 변경하려면

1. Azure Portal에서 **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
2. **추가 서비스** > **기타** > **Intune**을 선택합니다.
3. **Intune** 블레이드에서 **장치 및 그룹**을 선택합니다.
4. **장치 및 그룹** 블레이드에서 **관리** > **모든 장치**를 선택합니다.
5. 장치 목록에서 원하는 장치를 선택하고 장치 속성 블레이드에서 **관리** > **속성**을 선택합니다.
6. 다음 블레이드에서 선택한 장치의 **장치 범주**를 이전에 구성한 범주 이름으로 변경할 수 있습니다.



## <a name="further-information"></a>추가 정보
- Azure Portal에서 장치 범주를 편집할 수 있지만 이 경우 해당 범주를 참조하는 모든 Azure Active Directory 보안 그룹을 수동으로 업데이트해야 합니다.

- 범주를 삭제하면 해당 범주에 할당된 모든 장치의 범주 이름이 **할당되지 않음**으로 표시됩니다.



