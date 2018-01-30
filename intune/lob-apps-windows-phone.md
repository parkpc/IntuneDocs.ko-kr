---
title: "Intune에 Windows Phone 기간 업무 앱을 추가하는 방법"
titlesuffix: Azure portal
description: "Intune에 Windows Phone 기간 업무 앱을 추가하는 방법을 알아봅니다.\""
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/3/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a097b7b2-d01d-454b-954c-da4f3cd0ae86
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6c20414c2df5616a2616d64f88718761be8a57b0
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2018
---
# <a name="how-to-add-windows-phone-line-of-business-lob-apps-to-microsoft-intune"></a>Microsoft Intune에 Windows Phone LOB(기간 업무) 앱을 추가하는 방법

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


## <a name="step-1---specify-the-software-setup-file"></a>단계 1 - 소프트웨어 설치 파일 지정

1. Azure Portal에 로그인합니다.
2. **추가 서비스** > **모니터링 + 관리** + **Intune**을 선택합니다.
3. **Intune** 블레이드에서 **앱 관리**를 선택합니다.
4. **모바일 앱** 워크로드에서 **관리** > **앱**을 선택합니다.
5. 앱 목록 위에서 **추가**를 선택합니다.
6. **앱 추가** 블레이드에서 **LOB(기간 업무) 앱**을 선택합니다.

## <a name="step-2---configure-the-app-package-file"></a>2단계: 앱 패키지 파일 구성

1. **앱 추가** 블레이드에서 **앱 패키지** 파일을 선택합니다.
2. **앱 패키지** 파일 블레이드에서 찾아보기 단추를 선택하고 확장명 **.xap**가 포함된 Windows Phone 설치 파일을 선택합니다.
3. 작업이 끝나면 **확인**을 선택합니다.


## <a name="step-3---configure-app-information"></a>3단계 - 앱 정보 구성

1. **앱 추가** 블레이드에서 **앱 패키지** 파일을 선택합니다.
2. **앱 정보** 블레이드에서 앱 정보를 구성합니다. 선택한 앱에 따라 이 블레이드의 일부 값이 자동으로 채워질 수 있습니다.
    - **이름** - 회사 포털에 표시되는 앱의 이름을 입력합니다. 사용하는 모든 앱 이름이 고유한지 확인합니다. 동일한 앱 이름을 두 번 사용하는 경우에는 회사 포털에서 앱 중 하나만 사용자에게 표시됩니다.
    - **설명** - 앱에 대한 설명을 입력합니다. 설명은 회사 포털에서 사용자에게 표시됩니다.
    - **게시자** - 앱의 게시자 이름을 입력합니다.
    - **카테고리** - 기본 제공 앱 범주 중 하나 이상 또는 사용자가 만든 범주를 선택합니다. 범주를 사용하면 사용자가 회사 포털을 찾아볼 때 앱을 더 쉽게 찾을 수 있습니다.
    - **회사 포털에서 이 항목을 추천 앱으로 표시** - 사용자가 앱을 찾을 때 회사 포털의 기본 페이지에서 앱이 눈에 띄게 표시됩니다.
    - **정보 URL** - 필요에 따라 이 앱에 대한 정보를 포함하는 웹 사이트의 URL을 입력합니다. URL은 회사 포털에서 사용자에게 표시됩니다.
    - **개인 정보 URL** - 필요에 따라 이 앱에 대한 개인 정보 관련 정보를 포함하는 웹 사이트의 URL을 입력합니다. URL은 회사 포털에서 사용자에게 표시됩니다.
    - **개발자** - 필요에 따라 앱 개발자의 이름을 입력합니다.
    - **소유자** - 필요에 따라 이 앱의 소유자 이름을 입력합니다(예: **HR 부서**).
    - **메모** - 이 앱과 연결할 모든 메모를 입력합니다.
    - **로고** - 앱과 연결된 아이콘을 업로드합니다. 사용자가 회사 포털을 찾아볼 때 이 아이콘이 앱과 함께 표시됩니다.
3. 작업이 끝나면 **확인**을 선택합니다.

## <a name="step-4---finish-up"></a>4단계 - 끝내기

1. **앱 추가** 블레이드에서 정보를 올바르게 구성했는지 확인합니다.
2. **추가**를 선택하여 Intune에 앱을 업로드합니다.

## <a name="next-steps"></a>다음 단계

만든 앱은 앱 목록에 표시됩니다. 이제 선택한 그룹에 앱을 할당할 수 있습니다. 도움말은 [그룹에 앱을 할당하는 방법](apps-deploy.md)을 참조하세요.

앱의 속성 및 할당을 모니터링할 수 있는 방법에 대해 자세히 알아봅니다. 자세한 내용은 [앱 정보 및 할당을 모니터링하는 방법](apps-monitor.md)을 참조하세요.

Intune에서 앱의 컨텍스트에 대해 자세히 알아봅니다. 자세한 내용은 [장치 및 앱 수명 주기 개요](introduction-device-app-lifecycles.md)를 참조하세요.
