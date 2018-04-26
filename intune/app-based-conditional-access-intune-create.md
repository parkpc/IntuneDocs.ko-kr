---
title: Intune을 사용한 앱 기반 조건부 액세스 정책 설정
description: Intune을 사용한 앱 기반 조건부 액세스 정책 설정을 만드는 방법을 알아봅니다.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d1693515-de18-4553-91ef-801976cd3ec7
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: da6f351f4ce5cf6b0aeae977ffbef56dab5bd2df
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="set-up-app-based-conditional-access-policies-with-intune"></a>Intune을 사용한 앱 기반 조건부 액세스 정책 설정

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

이 아티클에서는 승인된 앱 목록에 포함된 앱에 대해 앱 기반 조건부 액세스 정책을 설정하는 방법을 설명합니다. 승인된 앱 목록은 Microsoft에서 테스트한 앱으로 구성됩니다.

> [!IMPORTANT]
> 이 아티클에서는 Exchange Online을 사용하여 앱 기반 조건부 액세스 정책을 추가하는 단계를 안내하지만, 승인된 앱 목록에서 SharePoint Online, Microsoft Teams 등의 다른 앱을 추가할 때도 동일한 단계를 사용할 수 있습니다.

## <a name="to-create-an-app-based-conditional-access-policy"></a>앱 기반 조건부 액세스 정책을 만들려면
1.  [Azure Portal](https://portal.azure.com)로 이동한 다음 자격 증명을 사용하여 로그인합니다.

2.  **모든 서비스**를 선택하고 "Intune"을 입력합니다.

3.  **Intune 앱 보호**를 선택합니다.

4.  **조건부 액세스** 섹션 아래 **Intune 앱 보호**에서 **Exchange Online**을 선택합니다.

    ![Exchange Online 옵션이 강조 표시된 조건부 액세스 섹션을 보여 주는 설정 창의 스크린샷](./media/MAM-conditional-access-1.png)

6. **허용된 앱** 창에서 **Allow apps that support Intune app policies**(Intune 앱 정책을 지원하는 앱 허용) 옵션을 선택하여 앱 보호 정책에서 지원하는 앱만 Exchange Online에 액세스할 수 있도록 합니다. 이 옵션을 선택하는 경우 지원되는 앱 목록이 표시됩니다.

    > [!NOTE]
    > iOS 및 Android에서 Exchange Online에 연결하는 기본 제공 메일 클라이언트를 비롯하여 모든 Exchange Active Sync 메일 클라이언트에서 이메일을 주고받지 못하게 됩니다. 사용자는 대신 Outlook 메일 앱을 사용해야 한다고 알리는 단일 메일을 받습니다.

7. 사용자에게 이 정책을 적용하려면 **제한된 사용자 그룹** 창을 열고 **사용자 그룹 추가**를 선택합니다. 이 정책을 받아야 하는 사용자 그룹을 하나 이상 선택하세요.

    ![사용자 그룹 추가 옵션이 강조 표시된 제한된 사용자 그룹 창의 스크린샷](./media/mam-ca-add-user-group.png)

8. 이전 단계에서 선택한 사용자 그룹에 있는 사용자 중 일부를 이 정책에 의해 영향을 받지 않도록 할 수 있습니다. 이 경우 제외된 사용자 그룹 목록에 사용자 그룹을 추가합니다. **Exchange Online** 창에서 **제외된 사용자 그룹**을 선택합니다. **사용자 그룹 추가**를 선택하여 사용자 그룹 목록을 엽니다. 이 정책에서 제외할 그룹을 선택합니다.

## <a name="to-modify-or-delete-user-groups-from-an-existing-app-based-ca-policy"></a>기존 앱 기반 CA 정책에서 사용자 그룹을 수정하거나 삭제하려면

1. **제한된 사용자 그룹** 창을 열고 삭제할 사용자 그룹을 강조 표시합니다.
2. 삭제 옵션을 보려면 타원을 클릭합니다.
3. **삭제**를 선택하여 목록에서 사용자 그룹을 제거합니다.

## <a name="create-app-based-conditional-access-policies-in-azure-ad-workload"></a>Azure AD 워크로드에서 앱 기반 조건부 액세스 정책 만들기

Intune 1708 릴리스부터 IT 관리자는 Azure AD 워크로드에서 앱 기반 조건부 액세스 정책을 만들 수 있습니다. 그러면 Azure와 Intune 워크로드 간을 전환할 필요가 없으므로 편리합니다.

> [!IMPORTANT]
> Intune Azure Portal에서 Azure AD 조건부 액세스 정책을 만들려면 Azure AD Premium 라이선스가 있어야 합니다.

### <a name="to-create-an-app-based-conditional-access-policy"></a>앱 기반 조건부 액세스 정책을 만들려면

> [!IMPORTANT]
> 앱 기반 조건부 액세스 정책을 사용하기 전에 [Intune 앱 보호 정책](app-protection-policies.md)을 앱에 적용해야 합니다.

1. **Intune 대시보드**에서 **조건부 액세스**를 선택합니다.

2. **정책** 창에서 **새 정책**을 선택하여 새 앱 기반 조건부 액세스 정책을 만듭니다.

4. 정책 이름을 입력하고 **할당** 섹션에서 사용 가능한 설정을 구성한 다음 **Access controls**(액세스 제어) 섹션에서 **Grant**(권한 부여)를 선택합니다.

5. **Require approved client app**(승인된 클라이언트 앱 필요)을 선택하고 **선택**을 선택한 다음, **만들기**를 선택하여 새 정책을 저장합니다.

## <a name="next-steps"></a>다음 단계
[최신 인증이 없는 앱 차단](app-modern-authentication-block.md)

### <a name="see-also"></a>참고 항목

[앱 보호 정책을 사용하여 앱 데이터 보호](app-protection-policies.md)
[Azure Active Directory의 조건부 액세스](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)
