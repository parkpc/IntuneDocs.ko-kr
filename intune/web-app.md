---
title: "Intune에 웹앱을 추가하는 방법"
titleSuffix: Azure portal
description: "Intune에 웹앱을 추가하는 방법을 알아봅니다.\""
keywords: 
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 12/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5f08752f-0e87-4ad9-a34c-4991b3150775
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: cfa70879a460826d22eb6fab2e0d08603e567d6e
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2018
---
# <a name="how-to-add-web-apps-to-microsoft-intune"></a>Microsoft Intune에 웹앱을 추가하는 방법

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

사용자의 앱을 관리하고 할당하려면 먼저 Intune에 앱을 추가합니다. Intune은 웹앱을 포함하여 다양한 앱 유형을 지원합니다.

> [!Note]
> Android for Work 장치에서는 웹앱이 지원되지 않습니다.

Intune에 앱을 웹용 앱의 바로 가기로 추가하려면 다음 단계를 완료하세요.

1. Azure 포털에 로그인합니다.
2. **추가 리소스**를 사용하여 **Intune**을 검색하고 선택합니다.
3. **Microsoft Intune** 블레이드에서 **모바일 앱**을 선택합니다.
4. **모바일 앱** 블레이드에서 **앱**을 선택합니다.
5. 앱 목록 위에서 **추가**를 선택합니다. **앱 추가** 블레이드가 표시됩니다.
6. **앱 추가** 블레이드의 **앱 유형** 드롭다운 목록에서 **웹앱** 유형을 선택합니다.
7. **구성** 옵션을 선택하여 **앱 정보** 블레이드를 표시합니다.
8. **앱 정보** 블레이드에서 다음 정보를 추가합니다.
    - **이름** - 회사 포털에 표시되는 앱 이름을 입력합니다.
    - **설명** - 앱에 대한 설명을 입력합니다. 이 설명은 회사 포털에서 최종 사용자에게 표시됩니다.
    - **게시자** - 이 앱의 게시자 이름을 입력합니다.
    - **앱 URL** - 할당할 앱을 호스트하는 웹 사이트의 URL을 입력합니다.
    - **범주(선택 사항)** - 기본 제공 앱 범주 중 하나 이상 또는 사용자가 만든 범주를 선택합니다. 이러게 범주를 선택하면 사용자가 회사 포털을 찾아볼 때 앱을 더 쉽게 찾을 수 있습니다.
    - **회사 포털에서 이 항목을 추천 앱으로 표시** - 사용자가 앱을 찾을 때 회사 포털의 기본 페이지에서 앱이 눈에 띄게 표시됩니다.
    - **이 링크를 열려면 Managed Browser가 필요** - 웹 사이트 또는 웹앱 링크가 할당된 사용자는 Intune Managed Browser에서 링크를 열 수 있습니다. 이 브라우저는 장치에 설치되어 있어야 합니다.
    - **로고** - 앱과 연결된 로고를 업로드할 수 있습니다. 이 로고는 사용자가 회사 포털을 찾아볼 때 앱과 함께 표시되는 로고입니다.
9. 작업이 완료되면 **정보 추가** 블레이드에서 **확인**을 선택합니다.
10. 그런 다음 **앱 추가** 블레이드에서 **추가**를 선택합니다.

만든 앱이 앱 목록에 표시되며, 여기서 이 앱을 선택한 그룹에 할당할 수 있습니다. 도움말은 [그룹에 앱을 할당하는 방법](apps-deploy.md)을 참조하세요.