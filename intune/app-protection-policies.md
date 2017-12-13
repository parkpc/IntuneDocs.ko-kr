---
title: "앱 보호 정책 만들기 및 배포"
titleSuffix: Azure portal
description: "Intune 앱 보호 정책을 통해 관리하는 앱에서 사용되는 회사 데이터를 보호하는 방법을 알아봅니다.\""
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 04/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f31b2964-e932-4cee-95c4-8d5506966c85
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c282a98ecf357f650fbfa14499a206c4d283f81a
ms.sourcegitcommit: 67ec0606c5440cffa7734f4eefeb7121e9d4f94f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/08/2017
---
# <a name="how-to-create-and-assign-app-protection-policies"></a>앱 보호 정책을 만들고 할당하는 방법

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="before-you-begin"></a>시작하기 전에

Intune 클래식 포털 관련 지침을 확인하려면 [앱 보호 정책을 만드는 방법](https://docs.microsoft.com/intune-classic/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune)을 참조하세요.

앱 보호 정책은 Intune에서 관리하거나 관리하지 않을 수 있는 장치에서 실행되는 앱에 적용할 수 있습니다. 앱 보호 정책의 작동 방식 및 Intune 앱 보호 정책으로 지원되는 시나리오에 대한 자세한 설명은 [Microsoft Intune 앱 보호 정책이란](app-protection-policy.md)을 참조하세요.

MAM을 지원하는 앱 목록을 확인하려면 [MAM 앱 목록](https://www.microsoft.com/cloud-platform/microsoft-intune-apps)을 참조하세요.

##  <a name="create-an-app-protection-policy"></a>앱 보호 정책 만들기
1.  **Mobile Apps** 작업에서 **관리** > **앱 보호 정책**을 선택합니다.

2.  **앱 보호 정책** 블레이드가 열리며, 여기서 새 정책을 만들고 기존 정책을 편집할 수 있습니다. **정책 추가**를 선택합니다.

  ![정책 추가 블레이드의 스크린 샷](./media/app-protection-add-policy.png)

3.  정책의 이름을 입력하고, 간략한 설명을 추가한 다음 플랫폼 형식을 선택하여 iOS 또는 Android에 대한 정책을 만듭니다. 각 플랫폼에 대해 여러 개의 정책을 만들 수 있습니다.

4.  **앱**을 선택하여 **앱 블레이드**를 열면 사용할 수 있는 앱 목록이 표시됩니다. 만들고 있는 정책과 연결할 앱을 목록에서 하나 이상 선택합니다. 앱을 선택한 후 **앱** 블레이드 맨 아래에 있는 **선택** 단추를 선택하여 선택 내용을 저장합니다.

    > [!IMPORTANT]
    > 정책을 만들려면 앱을 하나 이상 선택해야 합니다.

5.  **정책 추가 블레이드**에서 **필요한 설정 구성** 을 선택하여 정책 설정 블레이드를 엽니다.

    **데이터 재배치** 및 **액세스**라는 두 범주의 정책 설정이 있습니다.  데이터 재배치 정책은 앱 내부 및 외부로 데이터 이동에 적용할 수 있는 반면, 액세스 정책은 최종 사용자가 회사 컨텍스트에서 앱에 액세스하는 방법을 결정합니다.
    정책 설정에는 기본값이 있습니다. 이 기본값이 요구 사항을 충족하는 경우에는 변경할 필요가 없습니다.

    > [!TIP]
    > 이러한 정책 설정은 회사 컨텍스트에서 앱을 사용하는 경우에만 적용됩니다.  최종 사용자가 앱을 사용하여 개인 작업을 수행하는 경우에는 이러한 정책의 영향을 받지 않습니다.



6.  **확인**을 선택하여 이 구성을 저장합니다. 이제 **정책 추가** 블레이드로 돌아왔습니다. **만들기**를 클릭하여 정책을 만들고 설정을 저장합니다.


이전 절차에서 설명한 대로 정책 만들기를 완료하면 사용자에게 배포되지 않습니다. 정책을 배포하려면 "사용자에게 정책 배포" 섹션을 참조하세요.

## <a name="deploy-a-policy-to-users"></a>사용자에게 정책 배포

1.  **정책** 블레이드에서  **사용자 그룹**을 선택하면 **사용자 그룹** 블레이드가 열립니다. **사용자 그룹** 블레이드에서 **사용자 그룹 추가**를 선택하여 **사용자 그룹 추가** 블레이드를 엽니다.

  ![사용자 그룹 추가 옵션을 강조 표시한 사용자 그룹 블레이드의 스크린 샷](./media/app-protection-policy-add-users.png)

2.  사용자 그룹 목록이 **사용자 그룹 추가** 블레이드에 표시됩니다. 이는 **Azure Active Directory**에 있는 모든 보안 그룹의 목록입니다. 이 정책을 적용할 사용자 그룹을 선택하고 **선택**을 선택합니다. **선택**을 선택하면 정책이 사용자에게 배포됩니다.
  ![Azure Active Directory 사용자 목록을 보여 주는 사용자 그룹 추가 블레이드의 스크린 샷](./media/azure-ad-user-group-list.png)

이제 정책을 만들고 사용자에게 배포했습니다.

Microsoft Intune 라이선스가 할당된 사용자만 정책에 의해 영향을 받습니다. 선택한 보안 그룹에서 Microsoft Intune 라이선스가 할당되지 않은 사용자는 영향을 받지 않습니다.

>[!IMPORTANT]
> Configuration Manager와 함께 Intune을 사용하여 iOS 및 Android 장치를 관리하는 경우 선택한 그룹에 바로 포함된 사용자에만 정책이 적용됩니다. 선택한 그룹 내에 중첩된 자식 그룹의 멤버는 영향을 받지 않습니다.

최종 사용자는 앱 스토어 또는 Google Play에서 앱을 다운로드할 수 있습니다. 자세한 내용은 다음을 참조하십시오.
* [Android 앱이 앱 보호 정책으로 관리될 때 예상되는 상황](app-protection-enabled-apps-android.md)
* [iOS 앱이 앱 보호 정책으로 관리될 때 예상되는 상황](app-protection-enabled-apps-ios.md)

##  <a name="change-existing-policies"></a>기존 정책 변경
기존 정책을 편집할 수 있으며 대상으로 지정된 사용자에게 적용할 수 있습니다. 그러나 기존 정책을 변경하는 경우 앱에 이미 로그인한 사용자에게는 8시간 동안 변경 내용이 표시되지 않습니다.

변경 사항의 결과를 즉시 확인하려면 최종 사용자가 앱에서 로그아웃하고 다시 로그인해야 합니다.

### <a name="to-change-the-list-of-apps-associated-with-the-policy"></a>정책과 연결된 앱 목록을 변경하려면

1.  **앱 정책** 블레이드에서 변경할 정책을 선택합니다. 방금 선택한 정책과 관련된 블레이드가 열립니다.

2.  정책 블레이드에서 **대상 앱**을 선택하여 앱 목록을 엽니다.

3.  목록에서 앱을 제거하거나 추가하고 **저장** 아이콘을 선택하여 변경 내용을 저장합니다.

### <a name="to-change-the-list-of-user-groups"></a>사용자 그룹 목록을 변경하려면

1.  **앱 정책** 블레이드에서 변경할 정책을 선택합니다. 선택한 정책과 관련된 블레이드가 열립니다.

2.  정책 블레이드에서 **사용자 그룹**을 선택하여 이 정책이 있는 현재 사용자 그룹 목록을 보여 주는 **사용자 그룹** 블레이드를 엽니다.

3.  정책에 새 사용자 그룹을 추가하려면 **사용자 그룹 추가**를 선택하고 사용자 그룹을 선택합니다. **선택**을 선택하여 선택한 그룹에 정책을 배포합니다.

4.  사용자 그룹을 삭제하려면 제거하려는 사용자 그룹을 강조 표시합니다. 그런 다음 줄임표(…)를 선택하고 **삭제**를 선택하여 사용자 그룹을 제거합니다.
  ![삭제 옵션을 보여 주는 스크린샷](./media/app-protection-policy-delete-user.png)

### <a name="to-change-policy-settings"></a>정책 설정을 변경하려면

1.  **앱 정책** 블레이드에서 변경할 정책을 선택합니다. 방금 선택한 정책과 관련된 블레이드가 열립니다.


2.  **정책 설정**을 선택하여 **정책 설정** 블레이드를 엽니다.

3.  설정을 변경하고 **저장** 아이콘을 선택하여 변경 내용을 저장합니다.

## <a name="policy-settings"></a>정책 설정
iOS 및 Android에 대한 정책 설정의 전체 목록을 보려면 다음 중 하나를 선택합니다.

- [iOS 정책](app-protection-policy-settings-ios.md)
- [Android 정책](app-protection-policy-settings-android.md)

## <a name="next-steps"></a>다음 단계
[규정 준수 및 사용자 상태 모니터링](app-protection-policies-monitor.md)

### <a name="see-also"></a>참고 항목
* [Android 앱이 앱 보호 정책으로 관리될 때 예상되는 상황](app-protection-enabled-apps-android.md)
* [iOS 앱이 앱 보호 정책으로 관리될 때 예상되는 상황](app-protection-enabled-apps-ios.md)
