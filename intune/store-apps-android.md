---
title: "Intune에 Android 스토어 앱을 추가하는 방법"
titleSuffix: Azure portal
description: "Intune에 Android 스토어 앱을 추가하는 방법을 알아봅니다.\""
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/13/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4433000a-23e9-4cad-a818-48c28eedc1f5
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: cdf00d8adc5a854f90b59c6066d6f0ab7c6ae94a
ms.sourcegitcommit: 754fcc31155b28d6910bba45419c6be745f8793e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="how-to-add-android-store-apps-to-microsoft-intune"></a>Microsoft Intune에 Android 스토어 앱을 추가하는 방법

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

앱은 장치 또는 사용자 그룹에 할당하기 전에 먼저 앱을 Microsoft Intune에 추가해야 합니다. 다음 단계를 사용하면 Azure 포털에서 Android 스토어 앱을 Intune에 추가할 수 있습니다.

1. 로그인은 [Azure 포털](https://portal.azure.com)합니다.
2. **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
3. **Microsoft Intune** 블레이드에서 **Mobile Apps**를 선택합니다.
4. **모바일 앱** 워크로드의 **관리** 섹션에서 **앱**을 선택합니다.
5. 앱 목록 위에서 **추가**를 선택합니다.
6. **앱 추가** 블레이드의 **스토어 앱** 형식 아래에서 **Android**를 선택합니다.
7. 다음 정보에 따라 앱 정보를 구성하려면 **구성**을 선택합니다.  이 설명은 회사 포털에서 사용자에게 표시됩니다.
    - **이름** - 회사 포털에 표시되는 앱의 이름을 입력합니다. 사용하는 모든 앱 이름이 고유한지 확인합니다. 같은 앱 이름을 두 번 사용하는 경우에는 회사 포털에서 앱 중 하나만 사용자에게 표시됩니다.
    - **설명** - 앱에 대한 설명을 입력합니다. 이 설명은 회사 포털에서 사용자에게 표시됩니다.
    - **게시자** - 앱의 게시자 이름을 입력합니다.
    - **앱 스토어 URL** - 만들려는 앱의 앱 스토어 URL을 입력합니다.
    - **최소 운영 체제** - 목록에서 앱을 설치할 수 있는 최소 운영 체제 버전을 선택합니다. 이전 버전의 운영 체제를 사용하는 장치에 앱을 할당할 경우 앱이 설치되지 않습니다.
    - **범주(선택 사항)** - 기본 제공 앱 범주 중 하나 이상 또는 사용자가 만든 범주를 선택합니다. 이렇게 하면 사용자가 회사 포털을 찾아볼 때 앱을 더 쉽게 찾을 수 있습니다.
    - **회사 포털에서 이 항목을 추천 앱으로 표시** - 사용자가 앱을 찾을 때 회사 포털의 기본 페이지에서 앱이 눈에 띄게 표시됩니다.
    - **정보 URL** - (선택 사항) 이 앱에 대한 정보를 포함하는 웹 사이트의 URL을 입력합니다. URL은 회사 포털에서 사용자에게 표시됩니다.
    - **개인 정보 URL** - (선택 사항) 이 앱에 대한 개인 정보 관련 정보를 포함하는 웹 사이트의 URL을 입력합니다. URL은 회사 포털에서 사용자에게 표시됩니다.
    - **개발자** - (선택 사항) 앱 개발자의 이름을 입력합니다.
    - **소유자** - (선택 사항) 이 앱의 소유자 이름을 입력합니다(예: **HR 부서**).
    - **메모** - (선택 사항) 이 앱과 연결할 모든 메모를 입력합니다.
    - **아이콘** - (선택 사항) 앱과 연결할 아이콘을 업로드합니다. 사용자가 회사 포털을 찾아볼 때 이 아이콘이 앱과 함께 표시됩니다.
8. 앱 정보 설정을 마쳤을 때 **확인**을 클릭합니다.
9. **추가**를 클릭하여 앱을 추가합니다.

만든 앱이 앱 목록에 표시되며, 여기서 이 앱을 선택한 그룹에 할당할 수 있습니다. 

##<a name="next-steps"></a>다음 단계

- [그룹에 앱을 할당하는 방법](apps-deploy.md)