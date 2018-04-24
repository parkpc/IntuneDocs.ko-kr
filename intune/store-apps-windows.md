---
title: Microsoft Intune에 Microsoft Store 앱을 추가하는 방법
titleSuffix: ''
description: Microsoft Intune에 Microsoft Store(Windows 스토어) 앱을 추가하는 방법을 알아봅니다.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 07241b6d-86d8-4abb-83a2-3fc5feae5788
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 511cf2e01a2f5db93f0e0db9dbe2a32326c17723
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="add-microsoft-store-apps-to-microsoft-intune"></a>Microsoft Intune에 Microsoft Store 앱 추가

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

앱을 할당, 모니터링, 구성 또는 보호하려면 앱을 Intune에 추가해야 합니다. 다음 단계를 사용하면 Microsoft Intune에 Microsoft Store 앱을 추가할 수 있습니다.

1. 로그인은 [Azure 포털](https://portal.azure.com)합니다.
2. **모든 서비스** > **Intune**을 선택합니다. Intune은 **모니터링 + 관리** 섹션에 있습니다.
3. **Intune** 창에서 **모바일 앱**을 선택합니다.
4. **모바일 앱** 워크로드에서 **관리** > **앱**을 선택합니다.
5. 앱 목록 위에서 **추가**를 선택합니다.
6. **앱 추가** 창에서 **Windows**의 **앱 형식**을 선택하고 **앱 정보**를 선택합니다.
7. **앱 정보** 창에서 다음 정보를 구성합니다. 작업이 끝나면 **확인**을 클릭합니다. 선택한 앱에 따라 이 창의 일부 값이 자동으로 채워질 수 있습니다.
    - **이름** - 회사 포털에 표시되는 앱의 이름을 입력합니다. 사용하는 모든 앱 이름이 고유한지 확인합니다. 같은 앱 이름을 두 번 사용하는 경우에는 회사 포털에서 앱 중 하나만 사용자에게 표시됩니다.
    - **설명** - 회사 포털에서 사용자에게 표시될 앱의 설명을 입력합니다.
    - **게시자** - 앱의 게시자 이름을 입력합니다.
    - **앱 스토어 URL** - 만들려는 앱의 앱 스토어 URL을 입력합니다.
    - **범주(선택 사항)** - 하나 이상의 기본 제공 앱 범주 또는 만든 범주를 선택합니다. 그러면 사용자가 회사 포털을 찾아볼 때 더 쉽게 앱을 찾을 수 있습니다.
    - **회사 포털에서 이 항목을 추천 앱으로 표시** - 사용자가 앱을 찾을 때 회사 포털의 기본 페이지에서 앱이 눈에 띄게 표시됩니다.
    - **정보 URL** - 필요에 따라 이 앱에 대한 정보를 포함하는 웹 사이트의 URL을 입력합니다. URL은 회사 포털에서 사용자에게 표시됩니다.
    - **개인 정보 URL** - 필요에 따라 이 앱에 대한 개인 정보 관련 정보를 포함하는 웹 사이트의 URL을 입력합니다. URL은 회사 포털에서 사용자에게 표시됩니다.
    - **개발자** - 필요에 따라 앱 개발자의 이름을 입력합니다.
    - **소유자** - 필요에 따라 이 앱의 소유자 이름을 입력합니다(예: **HR 부서**).
    - **메모** - 이 앱과 연결할 모든 메모를 입력합니다.
    - **로고** - 앱과 연결된 아이콘을 업로드합니다. 사용자가 회사 포털을 찾아볼 때 이 아이콘이 앱과 함께 표시됩니다.
8. 작업이 완료되면 **앱 추가** 창에서 **추가**를 선택합니다.

만든 앱이 앱 목록에 표시됩니다. 이 목록에서 선택한 그룹에 앱을 할당할 수 있습니다. 

## <a name="next-steps"></a>다음 단계
- [그룹에 앱을 할당하는 방법](apps-deploy.md)