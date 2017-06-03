---
title: "Intune에 iOS 스토어 앱을 추가하는 방법 | Microsoft 문서"
titleSuffix: Intune Azure preview
description: "Intune Azure 미리 보기: Intune에 iOS 스토어 앱을 추가하는 방법을 알아봅니다."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c59514d7-1256-4576-9380-e7a0b85a0378
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 16d6da2bf1ebab609b8e9be4bec998d2f081600b
ms.contentlocale: ko-kr
ms.lasthandoff: 05/23/2017

---

# <a name="how-to-add-ios-store-apps-to-microsoft-intune"></a>Microsoft Intune에 iOS 스토어 앱을 추가하는 방법

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

## <a name="before-you-start"></a>시작하기 전에

앱 스토어에 무료 iOS 앱을 할당하려면 이 방법을 사용해야 합니다. Intune을 사용하여 유료 앱을 할당하려면 [iOS 대량 구매 프로그램](vpp-apps-ios.md)을 사용하는 것이 좋습니다.


## <a name="step-1---search-for-the-app-in-the-store"></a>1단계 - 스토어에서 앱 검색

1. Azure 포털에 로그인합니다.
2. **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
3. **Intune** 블레이드에서 **앱 관리**를 선택합니다.
4. **모바일 앱** 워크로드에서 **관리** > 앱을 선택합니다.
5. 앱 목록 위에서 **추가**를 선택합니다.
6. **앱 추가** 블레이드에서 **앱 스토어 검색**을 선택합니다.
7. **Apple 앱 스토어** 블레이드에서 검색 상자에 이름(또는 이름의 일부)을 입력합니다. Intune에서 스토어를 검색하여 관련 결과 목록을 반환합니다.
8. 목록에서 원하는 앱을 클릭한 다음 **확인**을 클릭합니다.

## <a name="step-2---configure-app-information"></a>2단계 - 앱 정보 구성

1. **앱 추가** 블레이드에서 **앱 정보**를 선택합니다.
2. **앱 편집** 블레이드에서 다음 정보를 구성합니다. 작업이 끝나면 **추가**를 클릭합니다. 선택한 앱에 따라 이 블레이드의 일부 값이 자동으로 채워질 수 있습니다.
- **앱 이름** - 회사 포털에 표시되는 앱의 이름을 입력합니다. 사용하는 모든 앱 이름이 고유한지 확인합니다. 같은 앱 이름을 두 번 사용하는 경우에는 회사 포털에서 앱 중 하나만 사용자에게 표시됩니다.
    - **앱 설명** - 앱에 대한 설명을 입력합니다. 이 설명은 회사 포털에서 사용자에게 표시됩니다.
- **게시자** - 앱의 게시자 이름을 입력합니다.
- **앱 스토어 URL** - 만들려는 앱의 앱 스토어 URL을 입력합니다.
- **최소 운영 체제** - 목록에서 앱을 설치할 수 있는 최소 운영 체제 버전을 선택합니다. 이전 버전의 운영 체제를 사용하는 장치에 앱을 할당할 경우 앱이 설치되지 않습니다.
- **범주**(선택 사항). 기본 제공 앱 범주 중 하나 이상 또는 사용자가 만든 범주를 선택합니다. 이렇게 하면 사용자가 회사 포털을 찾아볼 때 앱을 더 쉽게 찾을 수 있습니다.
- **회사 포털에서 이 항목을 추천 앱으로 표시** - 사용자가 앱을 찾을 때 회사 포털의 기본 페이지에서 앱이 눈에 띄게 표시됩니다.
- **정보 URL** - 필요에 따라 이 앱에 대한 정보를 포함하는 웹 사이트의 URL을 입력합니다. URL은 회사 포털에서 사용자에게 표시됩니다.
- **개인 정보 URL** - 필요에 따라 이 앱에 대한 개인 정보 관련 정보를 포함하는 웹 사이트의 URL을 입력합니다. URL은 회사 포털에서 사용자에게 표시됩니다.
- **개발자** - 필요에 따라 앱 개발자의 이름을 입력합니다.
- **소유자** - 필요에 따라 이 앱의 소유자 이름을 입력합니다(예: **HR 부서**).
- **메모** - 이 앱과 연결할 모든 메모를 입력합니다.
- **아이콘 업로드** - 앱과 연결할 아이콘을 업로드합니다. 사용자가 회사 포털을 찾아볼 때 이 아이콘이 앱과 함께 표시됩니다.
3. 작업을 마치면 **앱 추가** 블레이드에서 **저장**을 선택합니다.

만든 앱이 앱 목록에 표시됩니다. 이 목록에서 선택한 그룹에 앱을 할당할 수 있습니다. 도움말은 [그룹에 앱을 할당하는 방법](apps-deploy.md)을 참조하세요.
