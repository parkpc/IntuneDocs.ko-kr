---
title: "Intune에 Windows LOB(기간 업무) 앱을 추가하는 방법 | Microsoft 문서"
titleSuffix: Intune Azure preview
description: "Intune Azure 미리 보기: Intune에 Windows LOB(기간 업무) 앱을 추가하는 방법을 알아봅니다."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f81c5f82-5cfa-4b97-9f73-d6cf77c06896
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 3758df744311392528be01c826527c2a9d879975
ms.openlocfilehash: deafb0a37609b957a0cd4fa0880eeb5ff40314bc
ms.contentlocale: ko-kr
ms.lasthandoff: 05/10/2017

---

# <a name="how-to-add-windows-line-of-business-lob-apps-to-microsoft-intune"></a>Microsoft Intune에 Windows LOB(기간 업무) 앱을 추가하는 방법

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


## <a name="step-1---specify-the-software-setup-file"></a>단계 1 - 소프트웨어 설치 파일 지정

1. Azure 포털에 로그인합니다.
2. **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
3. **Intune** 블레이드에서 **앱 관리**를 선택합니다.
4. **모바일 앱** 워크로드에서 **관리** > **앱**을 선택합니다.
5. 앱 목록 위에서 **추가**를 선택합니다.
6. **앱 추가** 블레이드에서 **LOB(기간 업무) 앱**을 선택합니다.

## <a name="step-2---configure-the-app-package-file"></a>2단계: 앱 패키지 파일 구성

1. **앱 추가** 블레이드에서 **앱 패키지** 파일을 선택합니다.
2. **앱 패키지** 파일 블레이드에서 [찾아보기] 단추를 선택하고 확장명이 **.msi**인 Windows 설치 파일을 선택합니다(기타 설치 파일 유형은 지원되지 않음).
3. 작업이 끝나면 **확인**을 선택합니다.


## <a name="step-3---configure-app-information"></a>3단계 - 앱 정보 구성

1. **앱 추가** 블레이드에서 **앱 패키지** 파일을 선택합니다.
2. **앱 정보** 블레이드에서 다음 정보를 구성합니다. 선택한 앱에 따라 이 블레이드의 일부 값이 자동으로 채워질 수 있습니다.
    - **이름** - 회사 포털에 표시되는 앱의 이름을 입력합니다. 사용하는 모든 앱 이름이 고유한지 확인합니다. 같은 앱 이름을 두 번 사용하는 경우에는 회사 포털에서 앱 중 하나만 사용자에게 표시됩니다.
    - **설명** - 앱에 대한 설명을 입력합니다. 이 설명은 회사 포털에서 사용자에게 표시됩니다.
    - **게시자** - 앱의 게시자 이름을 입력합니다.
    - **카테고리** - 기본 제공 앱 범주 중 하나 이상 또는 사용자가 만든 범주를 선택합니다. 이렇게 하면 사용자가 회사 포털을 찾아볼 때 앱을 더 쉽게 찾을 수 있습니다.
    - **회사 포털에서 이 항목을 추천 앱으로 표시** - 사용자가 앱을 찾을 때 회사 포털의 기본 페이지에서 앱이 눈에 띄게 표시됩니다.
    - **정보 URL** - 필요에 따라 이 앱에 대한 정보를 포함하는 웹 사이트의 URL을 입력합니다. URL은 회사 포털에서 사용자에게 표시됩니다.
    - **개인 정보 URL** - 필요에 따라 이 앱에 대한 개인 정보 관련 정보를 포함하는 웹 사이트의 URL을 입력합니다. URL은 회사 포털에서 사용자에게 표시됩니다.
    - **명령줄 인수** - 필요한 경우 실행될 때 .msi 파일에 적용할 명령줄 인수를 입력합니다(예: **/q**).
    - **개발자** - 필요에 따라 앱 개발자의 이름을 입력합니다.
    - **소유자** - 필요에 따라 이 앱의 소유자 이름을 입력합니다(예: **HR 부서**).
    - **메모** - 이 앱과 연결할 모든 메모를 입력합니다.
    - **로고** - 앱과 연결할 아이콘을 업로드합니다. 사용자가 회사 포털을 찾아볼 때 이 아이콘이 앱과 함께 표시됩니다.
3. 작업이 끝나면 **확인**을 선택합니다.

## <a name="step-4---finish-up"></a>4단계 - 끝내기

1. **앱 추가** 블레이드에서 구성 정보가 올바른지 확인합니다.
2. **추가**를 선택하여 Intune에 앱을 업로드합니다.

만든 앱이 앱 목록에 표시됩니다. 이 목록에서 선택한 그룹에 앱을 할당할 수 있습니다. 도움말은 [그룹에 앱을 할당하는 방법](deploy-apps.md)을 참조하세요.

