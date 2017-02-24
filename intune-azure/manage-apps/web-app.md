---
title: "Intune에 웹앱을 추가하는 방법"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Intune에 웹앱을 추가하는 방법을 알아봅니다."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5f08752f-0e87-4ad9-a34c-4991b3150775
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: c2e54d3e57a4b02ba277b88cc672d5587c449281

---

# <a name="how-to-add-web-apps-to-microsoft-intune"></a>Microsoft Intune에 웹앱을 추가하는 방법

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

1. Azure 포털에 로그인합니다.
2. **More Services**(추가 서비스) > **모니터링 + 관리** > **Intune**을 선택합니다.
3. **Intune** 블레이드에서 **앱 관리**를 선택합니다.
4. **모바일 앱** 워크로드에서 **관리** > **앱**을 선택합니다.
5. 앱 목록 위에서 **추가**를 선택합니다.
6. **앱 추가** 블레이드에서 **App Information**(앱 정보)을 선택합니다.
7. **앱 편집** 블레이드에서 다음 정보를 구성합니다. 작업이 끝나면 **추가**를 클릭합니다.
    - **앱 URL** - 배포할 앱을 호스트하는 웹 사이트의 URL을 입력합니다.
    - **앱 이름** - 회사 포털에 표시되는 앱의 이름을 입력합니다.
    - **앱 설명** - 앱에 대한 설명을 입력합니다. 이 설명은 회사 포털에서 최종 사용자에게 표시됩니다.
    - **게시자** - 이 앱의 게시자 이름을 입력합니다.
    - **범주(선택 사항)** - 기본 제공 앱 범주 중 하나 이상 또는 사용자가 만든 범주를 선택합니다. 이렇게 하면 사용자가 회사 포털을 찾아볼 때 앱을 더 쉽게 찾을 수 있습니다.
    - **회사 포털에서 이 항목을 추천 앱으로 표시** - 사용자가 앱을 찾을 때 회사 포털의 기본 페이지에서 앱이 눈에 띄게 표시됩니다.
    - **이 링크를 열려면 Managed Browser가 필요** - 웹 사이트 또는 웹앱에 대한 링크를 사용자에게 배포할 경우 Intune Managed Browser에서만 링크를 열 수 있습니다. 이 브라우저는 장치에 설치되어 있어야 합니다.
    - **아이콘 업로드** - 앱과 연결할 아이콘을 업로드합니다. 사용자가 회사 포털을 찾아볼 때 이 아이콘이 앱과 함께 표시됩니다.
8. 작업을 마치면 **앱 추가** 블레이드에서 **저장**을 선택합니다.

만든 앱이 앱 목록에 표시됩니다. 이 목록에서 선택한 그룹에 앱을 할당할 수 있습니다. 도움말은 [그룹에 앱을 할당하는 방법](/intune-azure/manage-apps/deploy-apps)을 참조하세요.


<!--HONumber=Feb17_HO3-->


