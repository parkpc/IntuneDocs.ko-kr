---
title: "SharePoint Online에 대한 앱 기반 조건부 액세스 정책 만들기"
description: 
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 05/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 531b09bb-ddfd-498f-8ee3-6675d2466208
ms.reviewer: chrisgre
ms.suite: ems
ms.openlocfilehash: 2d9065281436d4c44e6af7d7a4401786a2a01965
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2017
---
# <a name="set-up-app-based-conditional-access-ca-policies-for-sharepoint-online"></a>SharePoint Online에 대한 앱 기반 CA(조건부 액세스) 정책 설정

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

이 항목에서는 SharePoint Online에 대한 앱 기반 조건부 액세스 정책을 설정하는 방법을 안내합니다. 앱 기반 CA는 Intune 앱 보호 정책이 적용되는 모바일 앱에만 사용할 수 있도록 관리자를 지원합니다.

## <a name="to-create-the-app-based-ca-policy-for-sharepoint-online"></a>SharePoint Online에 대한 앱 기반 CA 정책을 만들려면

1. [Azure Portal](https://portal.azure.com)로 이동한 다음 자격 증명을 사용하여 로그인합니다.

    > [!NOTE]
    > Azure Portal 환경을 처음 사용하는 경우 [앱 보호 정책용 Azure Portal](azure-portal-for-microsoft-intune-mam-policies.md) 항목을 읽어보세요.

2. 왼쪽 메뉴에서 **More services**(추가 서비스)를 선택한 다음 텍스트 상자 필터에 **Intune**을 입력합니다.

3. **Intune App Protection**(Intune 앱 보호) > **Intune 모바일 응용 프로그램 관리** > **모든 설정**을 선택합니다.

4. Intune 모바일 응용 프로그램 관리 블레이드에서 SharePoint Online 타일을 선택합니다.

5. **허용된 앱** 블레이드에서 **Allow apps that support Intune app policies**(Intune 앱 정책을 지원하는 앱 허용) 옵션을 선택하여 Intune 앱 보호 정책에서 지원하는 앱만 허용합니다.

    > [!NOTE] 
    > Intune 앱 보호 정책에서 지원되는 앱만 허용하는 옵션을 선택하면 지원되는 앱**만** 포함된 목록이 표시됩니다.

    ![앱의 목록을 보여 주는 허용된 앱 블레이드의 스크린샷](../media/mam-ca-spo-allowed-apps.png)

## <a name="to-assign-app-based-ca-policies-to-your-users"></a>사용자에게 앱 기반 CA 정책을 할당하려면

1. **제한된 사용자 그룹** 블레이드를 열고 **사용자 그룹 추가**를 선택합니다.

2. 이 정책을 받아야 하는 사용자 그룹을 하나 이상 선택하세요.

    ![사용자 그룹 추가 옵션이 강조 표시된 제한된 사용자 그룹 블레이드의 스크린샷](../media/mam-ca-spo-restricted-groups.png)

    > [!IMPORTANT] 
    > 이전 단계에서 선택한 사용자 그룹에 있는 사용자 중 일부를 이 정책에 의해 영향을 받지 않도록 할 수 있습니다. 이 경우 제외된 사용자 그룹 목록에 사용자 그룹을 추가합니다. 

3. **SharePoint Online** 블레이드에서 **예외 사용자 그룹**을 선택하고 **사용자 그룹 추가**를 선택하여 사용자 그룹 목록을 엽니다.

4. 이 정책에서 제외할 그룹을 선택합니다.  

## <a name="to-modify-or-delete-user-groups-from-an-existing-app-based-ca-policy"></a>기존 앱 기반 CA 정책에서 사용자 그룹을 수정하거나 삭제하려면

1. **제한된 사용자 그룹** 블레이드를 열고 삭제할 사용자 그룹을 강조 표시합니다.
2. 삭제 옵션을 보려면 타원을 클릭합니다.
3. **삭제**를 선택하여 목록에서 사용자 그룹을 제거합니다.

> [!NOTE] 
> 단계 절차를 사용하여 **예외 사용자 그룹** 목록에서 사용자 그룹을 제거할 수 있습니다.

## <a name="next-steps"></a>다음 단계

[최신 인증을 사용하지 않는 앱 차단](block-apps-with-no-modern-authentication.md)

## <a name="see-also"></a>참고 항목

[앱 보호 정책을 사용하여 앱 데이터 보호](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)

[Exchange Online에 대한 앱 기반 CA 구성](mam-ca-for-exchange-online.md)
