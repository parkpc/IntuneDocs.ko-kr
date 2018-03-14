---
title: "Microsoft Intune에서 앱 시작"
titlesuffix: 
description: "앱을 찾고 장치에 추가하여 직원이 작업을 수행할 수 있게 합니다."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 3/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1542fc3-672e-47c1-a21f-82826a2f8ac4
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0185eebbe436da73e1920d7cd834f0897a143894
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2018
---
# <a name="get-started-with-adding-apps-in-microsoft-intune"></a>Microsoft Intune에서 앱 추가 시작

앱을 할당, 모니터링, 구성 또는 보호하려면 앱을 Intune에 추가해야 합니다. Intune은 여러 앱 유형을 지원합니다. 또한 사용 가능한 옵션은 앱 유형마다 다릅니다.

Intune을 사용하여 기업 장치에 다음 앱 유형을 추가하고 할당할 수 있습니다.
- **스토어 앱**: 앱 스토어에서 제공되는 앱에 추가 모바일 응용 프로그램 관리가 적용되어야 하는 장치의 경우.
- **사내에서 작성한 앱(기간 업무)**: 사용자 장치에 다운로드되는 파일을 업로드하는 경우.
- **기본 제공되는 앱** - Office 365 앱과 같이 엄격히 관리되는 앱을 iOS 및 Android 장치에 할당하는 경우. 
- **웹앱** - Intune이 장치 홈 화면에 웹앱의 바로 가기를 만드는 경우.

## <a name="how-do-i-assign-a-public-store-app"></a>공용 저장소 앱을 할당하려면 어떻게 하나요?

다음 예제에서는 Microsoft Intune에서 iOS 앱을 추가 하는 방법을 단계별로 안내합니다.

1. 로그인은 [Azure 포털](https://portal.azure.com)합니다.
2. **모든 서비스** > **Intune**을 선택합니다. Intune은 **모니터링 + 관리** 섹션에 있습니다.
3. **Intune** 블레이드에서 **Mobile Apps**를 선택합니다.
4. **모바일 앱** 워크로드의 **관리** 섹션에서 **앱**을 선택합니다.
5. **앱** 창의 오른쪽에 있는 **추가**를 선택합니다.
6. **앱 유형** 목록에서 사용할 수 있는 **스토어 앱** 형식 아래에서 **iOS**를 선택합니다.
6. **앱 스토어 검색**을 선택합니다.
7. **앱 스토어 검색** 블레이드에서 먼저 앱 스토어 국가별 로캘을 선택합니다.
8. 검색 상자에서 이름(또는 이름의 일부)을 입력합니다. Intune에서 스토어를 검색하고 관련 결과의 목록을 반환합니다.
9. 목록에서 원하는 앱을 선택한 다음, **선택**을 클릭합니다.
10. **앱 정보**를 선택해 앱 정보를 구성합니다.
11. **소유자**, **메모**, **개발자**, **개인 정보 보호 URL**(회사의 개인 정보 취급 방침에 대한) 등 이 앱을 구성하는 데 유용한 세부 정보를 추가할 수 있습니다(선택 사항).
12. **회사 포털에서 이 항목을 추천 앱으로 표시**에 대해 **예**를 선택했습니다. 
13. 필요한 모든 앱 정보를 추가한 뒤 **확인**을 클릭합니다.
14. **앱 추가** 블레이드에서 **추가**를 클릭하면 해당 앱의 **개요**로 이동합니다. 

## <a name="next-steps"></a>다음 단계

Intune에 앱을 추가한 만큼 직원 그룹이 자신들의 장치에 앱을 포함시킬 수 있도록 할당할 수 있습니다.

- [그룹에 앱을 할당하는 방법](apps-deploy.md)
- 
## <a name="learn-more"></a>자세한 정보

* [Intune을 사용한 앱 관리란?](app-management.md)
* [앱 수명 주기 개요](app-lifecycle.md)
* [앱 보호 정책이란?](app-protection-policy.md)
