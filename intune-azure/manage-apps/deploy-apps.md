---
title: "그룹에 앱을 할당하는 방법 | Intune Azure 미리 보기 | Microsoft Docs"
description: "Intune Azure 미리 보기: Intune에 앱을 추가한 후 사용자 또는 장치 그룹에 할당할 수 있습니다."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dc349e22-9e1c-42ba-9e70-fb2ef980ef7a
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: 638ad0d87c19c9e40e96b42d18e5c4342f40a156
ms.lasthandoff: 02/16/2017

---

# <a name="how-to-assign-apps-to-groups-with-microsoft-intune"></a>Microsoft intune을 사용하여 그룹에 앱을 할당하는 방법

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Intune에 앱을 추가한 후 사용자 및 장치로 가져올 수 있습니다. 해당 앱을 할당하면 됩니다.

Intune에서 관리되는지 여부에 상관없이 장치에 앱을 할당할 수 있습니다. 다음 표를 사용하면 사용자 및 장치에 앱을 할당하는 다양한 옵션을 쉽게 이해할 수 있습니다.

||||
|-|-|-|-|
|&nbsp;|Intune에 등록된 장치|Intune에 등록되지 않은 장치|
|사용자에게 할당|예|예|
|장치에 할당|예|아니요|
|래핑된 앱 또는 Intune SDK 통합 앱(앱 보호 정책용) 할당|예|예|
|사용 가능으로 앱 할당|예|예|
|필수로 앱 할당|예|아니요|
|앱 제거|예|예|
|최종 사용자가 회사 포털 앱에서 사용 가능한 앱 설치|예|아니요|
|최종 사용자가 웹 기반 회사 포털에서 사용 가능한 앱 설치|예|예|

> [!NOTE]
> 현재 Intune에 등록되지 않은 장치에 iOS 및 Android 앱(기간 업무 및 스토어 구매 모두)을 할당할 수 있습니다.

## <a name="how-to-assign-an-app"></a>앱을 할당하는 방법

1. Azure 포털에 로그인합니다.
2. **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
3. **Intune** 블레이드에서 **앱 관리**를 선택합니다.
1. **앱 관리** 워크로드에서 **관리** > **앱**을 선택합니다.
2. 앱 목록 블레이드에서 할당할 앱을 클릭합니다.
3. <*앱 이름*> - **개요** 블레이드에서 **관리** > **할당**을 선택합니다.
4. **그룹 선택**을 선택하고 **그룹 선택** 블레이드에서 앱을 할당할 Azure AD 그룹을 선택합니다.
5. 선택한 각 앱에 대해 **할당 유형**을 선택합니다.
    - **사용 가능** - 사용자가 회사 포털 앱 또는 웹 사이트에서 앱을 설치합니다.
    - **해당 사항 없음** - 앱이 설치되거나 회사 포털에 표시되지 않습니다.
    - **필수** - 앱이 선택한 그룹의 장치에 설치됩니다.
    - **제거** - 앱이 선택한 그룹의 장치에서 제거됩니다.
    - **등록없이 사용 가능** - 이 앱을 Intune에 등록되지 않은 장치의 사용자 그룹에 할당합니다. 도움말은 위 표를 참조하세요.
6. 작업이 끝나면 **저장**을 선택합니다.

이제 선택한 그룹에 앱이 할당됩니다.

앱 할당을 모니터링하는 데 유용한 정보는 [앱을 모니터링하는 방법](monitor-apps.md)을 참조하세요.

