---
title: "장치 그룹 매핑을 사용하여 장치 분류 | Microsoft 문서"
description: "이러한 장치를 쉽게 관리하기 위해 Microsoft Intune 장치 그룹 매핑을 사용하여 장치를 정의하는 범주에 그룹화할 수 있습니다."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/26/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8b8c06a3-6b6c-4cf1-8646-b24fa9b1a39e
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 28af253b0a0fe174478961810a26b45d8ac3d959

---

# <a name="categorize-devices-with-device-group-mapping-in-microsoft-intune"></a>Microsoft Intune에서 장치 그룹 매핑을 사용하여 장치 분류

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

이러한 장치를 쉽게 관리하기 위해 Microsoft Intune **장치 그룹 매핑**을 사용하여 정의하는 범주를 기반으로 하는 그룹에 장치를 자동으로 추가합니다. 

장치 그룹 매핑에서는 다음 워크플로를 사용합니다.
1. 사용자가 자신의 장치를 등록할 때 선택할 범주 만들기
2. 그룹을 만들거나, 사용할 각 범주에 대한 기존 그룹을 사용합니다. 사용 중인 Intune 버전에 따라 Intune 그룹 또는 Azure Active Directory 보안 그룹이 될 수 있습니다.
2. 선택한 범주를 만든 장치 그룹에 매핑하는 규칙을 구성합니다.
3. 최종 사용자가 해당 장치를 등록할 경우 구성한 범주 목록에서 범주를 선택해야 합니다. 선택한 후에 자동으로 만든 해당 그룹에 장치가 추가됩니다. 장치를 이미 등록한 경우 최종 사용자에게 다음번에 회사 포털 앱에 액세스할 때 범주를 선택할지 묻는 메시지가 표시됩니다.
4. 그런 다음 이러한 그룹에 정책 및 앱을 배포할 수 있습니다.

원하는 모든 장치 범주를 만들 수 있습니다. 예를 들면 다음과 같습니다.
* POS(Point of Sale) 장치
* 데모 장치
* 판매
* 계정
* Manager

## <a name="important-information-about-a-change-in-group-management-for-intune"></a>Intune에 대한 그룹 관리의 변경에 대한 중요한 정보

여러분의 피드백에 따라 Enterprise Mobility + Security 전체에서 그룹화 및 대상 지정 환경을 단일화하고 있습니다. 이로 인해 Intune 그룹을 곧 Azure Active Directory 기반의 보안 그룹으로 변환할 예정입니다. 변경되고 나면 더 이상 Intune을 사용하여 그룹을 만들 수 없게 됩니다. 대신 Azure Portal에서 만들 수 있습니다. 이 변경은 점진적으로 수행되며, 변경에 대한 전체 세부 정보와 타임라인은 [이 항목](use-groups-to-manage-users-and-devices-with-microsoft-intune.md)에서 참조할 수 있습니다.

### <a name="which-procedure-in-this-topic-should-you-use-to-configure-device-group-mapping"></a>장치 그룹 매핑을 구성하려면 이 항목에서 어떤 절차를 사용해야 하나요?

Azure Active Directory 기반 보안 그룹은 단계적으로 구현되므로 [Intune 관리 콘솔](https://manage.microsoft.com)에서 **그룹** 작업 영역을 열어 사용할 절차를 파악해야 합니다.

-  Azure Portal에 대한 링크가 표시되면 Intune 그룹을 더 이상 사용하지 않는 것입니다. 아래 [Azure Active Directory 그룹에 대한 장치 그룹 매핑을 구성하는 방법](/intune/deploy-use/categorize-devices-with-device-group-mapping-in-microsoft-intune#how-to-configure-device-group-mapping-for-azure-active-directory-groups) 절차를 따릅니다.
-  Azure Portal에 대한 링크가 표시되지 않으면 계속 Intune 그룹을 사용하는 것입니다. 아래 [Intune 그룹에 대한 장치 그룹 매핑을 구성하는 방법](/intune/deploy-use/categorize-devices-with-device-group-mapping-in-microsoft-intune#how-to-configure-device-group-mapping-for-intune-groups) 절차를 따릅니다.

## <a name="how-to-configure-device-group-mapping-for-intune-groups"></a>Intune 그룹에 대한 장치 그룹 매핑을 구성하는 방법
1. 사용할 각 장치 범주에 대해 Intune 장치 그룹을 만들거나 기존 그룹을 파악합니다. 그룹을 만드는 방법에 대한 자세한 내용은 [Microsoft Intune에서 그룹을 사용하여 사용자 및 장치 관리](use-groups-to-manage-users-and-devices-with-microsoft-intune.md)를 참조하세요.
2. [Microsoft Intune 관리 콘솔](https://manage.microsoft.com)에서 **관리자**를 선택합니다.
3. **관리** 작업 영역에서 **모바일 장치 관리**를 확장한 후 **장치 그룹 매핑**을 선택합니다.
4. **장치 그룹 매핑** 페이지에서 장치 그룹 매핑을 사용합니다.
5. **추가**를 선택하여 새 매핑 규칙을 만듭니다.
6. **추가 장치 그룹 매핑 규칙** 대화 상자에서 만들려는 범주의 이름을 입력하고 드롭다운 목록에서 이 범주를 매핑할 장치 컬렉션을 선택합니다. 작업을 마치면 **추가**를 선택합니다.
7. 범주 및 그룹 추가를 완료하면 **저장**을 선택합니다.



## <a name="how-to-configure-device-group-mapping-for-azure-active-directory-groups"></a>Azure Active Directory 그룹에 대한 장치 그룹 매핑을 구성하는 방법

### <a name="step-1---create-device-categories-in-the-intune-administration-console"></a>1단계 - Intune 관리 콘솔에서 장치 범주 만들기
1. [Microsoft Intune 관리 콘솔](https://manage.microsoft.com)에서 **관리자**를 선택합니다.
3. **관리** 작업 영역에서 **모바일 장치 관리**를 확장한 후 **장치 범주**를 선택합니다.
4. **장치 범주** 페이지에 장치 범주를 구성할 수 있는 목록이 표시됩니다. 
- 이름을 입력한 다음 **추가**를 클릭하고 새 장치 범주로 추가할 수 있습니다.
- 또한 범주를 선택한 다음 **삭제**할 수 있습니다.

2단계에서 Azure Active Directory 보안 그룹을 만들 때 장치 범주 이름을 사용합니다.

### <a name="step-2---create-azure-active-directory-security-groups"></a>2단계 - Azure Active Directory 보안 그룹 만들기

이 단계에서는 장치 범주 및 장치 범주 이름에 따라 Azure Portal에서 동적 그룹을 만듭니다.

계속하려면 Azure Active Directory 설명서에서 [특성을 사용하여 고급 규칙 만들기](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/#using-attributes-to-create-rules-for-device-objects) 항목을 참조하세요.
이 항목의 정보를 통해 **deviceCategory** 특성을 사용하는 고급 규칙이 있는 장치 그룹을 만듭니다.
예를 들면 **device.deviceCategory-eq** "<*Intune 관리 콘솔에서 가져온 장치 범주 이름*>"입니다.


## <a name="after-you-configure-device-groups"></a>장치 그룹 구성 후

사용자가 해당 장치를 등록할 경우 구성한 범주의 목록으로 표시됩니다. 범주를 선택하고 등록을 완료한 후에 이 장치는 선택한 범주에 해당하는 Intune 장치 그룹 또는 Active Directory 보안 그룹에 추가됩니다.

### <a name="see-also"></a>참고 항목
[Microsoft Intune에서 그룹을 사용하여 사용자 및 장치 관리](use-groups-to-manage-users-and-devices-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


