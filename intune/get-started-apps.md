---
title: "앱 시작"
titlesuffix: Azure portal
description: "앱을 찾고 장치에 추가하여 직원이 작업을 수행할 수 있게 합니다."
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 12/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1542fc3-672e-47c1-a21f-82826a2f8ac4
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: bb02c362f056c454f4d141ce7ae20b9c3ca8035d
ms.sourcegitcommit: a7c1e10e615e5c975bb5d52eca986c5cf5287687
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/07/2017
---
# <a name="get-started-with-adding-apps"></a>앱 추가 시작

Intune은 회사 장치에 앱을 배포하는 몇 가지 방법을 지원합니다.

* **소프트웨어 설치 관리자**: 사용자 장치에 다운로드되는 파일을 업로드하는 위치
* __외부 링크__: 공용 앱 스토어의 앱 또는 웹앱이 있는 경우의 링크
* **관리되는 앱**: 앱 스토어에서 제공되는 앱에 추가 모바일 응용 프로그램 관리가 적용되어야 하는 iOS 장치용 앱

공용 저장소 앱을 할당하여 더 빠른 응용 프로그램 배포 방법 중 하나를 수행하려고 합니다.

## <a name="how-do-i-assign-a-public-store-app"></a>공용 저장소 앱을 할당하려면 어떻게 하나요?

1. [Azure 포털](https://portal.azure.com)에 로그인합니다.
2. **리소스 검색**을 사용하여 **Intune**을 검색합니다.
3. **Mobile Apps**를 선택한 다음 **앱**을 선택합니다.
4. **추가**를 선택한 다음, **스토어 앱** 아래에서 **iOS**를 **앱 유형**으로 선택합니다.
5. **앱 선택**을 선택하여 **앱 스토어 검색** 블레이드를 표시합니다.
6. 텍스트 상자에서 장치에 할당할 앱을 검색합니다. 앱을 선택하고 **선택**을 클릭합니다.
7. **앱 추가** 블레이드에서 **앱 정보**를 선택한 다음 앱 정보가 모두 채워졌는지 확인합니다. **소유자**, **메모**, **개발자**, 회사의 개인 정보 취급 방침에 대한 **개인 정보 보호 URL** 등 이 앱을 구성하는 데 유용한 다른 선택적 세부 정보를 추가할 수 있습니다.
8. **회사 포털에서 이 항목을 추천 앱으로 표시**에 대해 **예**를 선택했는지 확인하고 **확인**을 선택합니다.
9. **앱 추가** 블레이드에서 **추가**를 선택하여 앱을 추가합니다. 그러면 해당 앱의 **개요**로 이동됩니다. **할당**을 선택하고 **그룹 선택**을 클릭하여 테스트 그룹에 할당합니다. 앱을 다운로드에 **사용 가능**하도록 설정합니다. 앱이 테스트 장치에서 **추천 앱**으로 표시됩니다.

## <a name="learn-more"></a>자세한 정보

* [Intune을 사용한 앱 관리란?](app-management.md)
* [앱 수명 주기 개요](app-lifecycle.md)
* [앱 보호 정책이란?](app-protection-policy.md)
