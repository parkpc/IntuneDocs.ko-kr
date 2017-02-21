---
title: "Intune에 iOS LOB(기간 업무) 앱을 추가하는 방법 | Intune Azure 미리 보기 | Microsoft Docs"
description: "Intune Azure 미리 보기: Intune에 iOS LOB(기간 업무) 앱을 추가하는 방법을 알아봅니다."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 099101e8-4b22-40ac-ba19-82ba5c71944c
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 424fae862592c1ab5b4221fb5ad40a52c39f6760
ms.openlocfilehash: d8615611eb715da66b1cf0972b885fbccb12fe6a

---

# <a name="how-to-add-ios-line-of-business-lob-apps-to-intune"></a>Intune에 iOS LOB(기간 업무) 앱을 추가하는 방법

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


## <a name="step-1---specify-the-software-setup-file"></a>단계 1 - 소프트웨어 설치 파일 지정

1. Azure 포털에 로그인합니다.
2. **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
3. Intune 블레이드에서 **앱 관리**를 선택합니다.
4. **모바일 앱** 워크로드에서 관리 > **앱**을 선택합니다.
5. 앱 목록 위에서 **추가**를 선택합니다.
6. **앱 추가** 블레이드에서 **소프트웨어 설치 파일**을 선택합니다.
7. **설치 파일 선택** 블레이드에서 찾아보기 단추를 클릭하여 iOS 앱 설치 파일(확장명 .ipa)을 찾은 후 **확인**을 클릭합니다.

## <a name="step-2---configure-app-information"></a>2단계 - 앱 정보 구성

1. **앱 편집** 블레이드에서 다음 정보를 구성합니다. 작업이 끝나면 **추가**를 클릭합니다. 선택한 앱에 따라 이 블레이드의 일부 값이 자동으로 채워질 수 있습니다.
    - **앱 이름** - 회사 포털에 표시되는 앱의 이름을 입력합니다. 사용하는 모든 앱 이름이 고유한지 확인합니다. 같은 앱 이름을 두 번 사용하는 경우에는 회사 포털에서 앱 중 하나만 사용자에게 표시됩니다.
    - **앱 설명** - 앱에 대한 설명을 입력합니다. 이 설명은 회사 포털에서 사용자에게 표시됩니다.
    - **게시자** - 앱의 게시자 이름을 입력합니다.
    - **적용할 수 있는 장치 유형** - iPad, iPhone 또는 호환 iPod에 이 앱을 설치할 수 있는지 여부를 선택합니다.
    - **최소 운영 체제** - 목록에서 앱을 설치할 수 있는 최소 운영 체제 버전을 선택합니다. 이전 버전의 운영 체제를 사용하는 장치에 앱을 할당할 경우 앱이 설치되지 않습니다.
    - **범주(선택 사항)** - 기본 제공 앱 범주 중 하나 이상 또는 사용자가 만든 범주를 선택합니다. 이렇게 하면 사용자가 회사 포털을 찾아볼 때 앱을 더 쉽게 찾을 수 있습니다.
    - **회사 포털에서 이 항목을 추천 앱으로 표시** - 사용자가 앱을 찾을 때 회사 포털의 기본 페이지에서 앱이 눈에 띄게 표시됩니다.
    - **정보 URL** - 필요에 따라 이 앱에 대한 정보를 포함하는 웹 사이트의 URL을 입력합니다. URL은 회사 포털에서 사용자에게 표시됩니다.
    - **개인 정보 URL** - 필요에 따라 이 앱에 대한 개인 정보 관련 정보를 포함하는 웹 사이트의 URL을 입력합니다. URL은 회사 포털에서 사용자에게 표시됩니다.
    - **개발자** - 필요에 따라 앱 개발자의 이름을 입력합니다.
    - **소유자** - 필요에 따라 이 앱의 소유자 이름을 입력합니다(예: **HR 부서**).
    - **메모** - 이 앱과 연결할 모든 메모를 입력합니다.
    - **아이콘 업로드** - 앱과 연결할 아이콘을 업로드합니다. 사용자가 회사 포털을 찾아볼 때 이 아이콘이 앱과 함께 표시됩니다.
2. 작업을 마치면 **앱 추가** 블레이드에서 **저장**을 선택합니다.

만든 앱이 앱 목록에 표시됩니다. 이 목록에서 선택한 그룹에 앱을 할당할 수 있습니다. 도움말은 [그룹에 앱을 할당하는 방법](/intune-azure/manage-apps/deploy-apps)을 참조하세요.


<!--HONumber=Feb17_HO1-->


