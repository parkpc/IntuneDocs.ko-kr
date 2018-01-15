---
title: "Intune을 사용하여 macOS 장치에 Office 365 설치"
titlesuffix: Azure portal
description: "Intune을 사용하여 macOS 장치에 Office 365 앱을 더 쉽게 설치하는 방법을 알아봅니다."
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 12/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2372332a-7e3a-4a9c-91a9-86654e0fabe2
ms.reviewer: aiwang
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5613997340867dda6def6a9a0a308b1ef0b618b5
ms.sourcegitcommit: 138df6f793d2dc718041346b90c367c0181990da
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/20/2017
---
# <a name="how-to-assign-office-365-to-macos-devices-with-microsoft-intune"></a>Microsoft Intune을 사용하여 macOS 장치에 Office 365를 할당하는 방법

>[!Note]
> 이 기능에 영향을 주는 알려진 문제가 있습니다. 자세한 내용은 [알려진 Microsoft Intune 문제](/intune/known-issues#apps)를 참조하세요.

이 앱 유형을 사용하면 macOS 장치에 Office 365 앱을 쉽게 할당할 수 있습니다. 이 새로운 앱 유형을 통해 Word, Excel, PowerPoint, Outlook 및 OneNote를 설치할 수 있습니다. 또한 이러한 앱은 MAU(Microsoft 자동 업데이트)와 함께 제공되므로 앱을 더 안전하게 최신 상태로 유지할 수 있습니다. 원하는 앱이 Intune 콘솔의 앱 목록에 하나의 앱으로 표시됩니다.


## <a name="before-you-start"></a>시작하기 전에

- 이 앱을 배포할 장치에서 macOS 10.10 이상을 실행하고 있어야 합니다.
- Intune은 Mac용 Office 2016 제품군에 포함된 Office 앱 추가를 지원합니다.
- Intune에서 앱 패키지를 설치할 때 Office 앱이 열려 있으면 최종 사용자가 저장하지 않은 파일의 데이터가 손실될 수 있습니다.


## <a name="get-started"></a>시작
**앱** 블레이드를 사용하여 Office 365를 추가합니다.
1.  Azure 포털에 로그인합니다.
2.  **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
3.  **Intune** 블레이드에서 **Mobile Apps**를 선택합니다.
4.  **모바일 앱** 워크로드의 **관리** 그룹에서 **앱**을 선택합니다. **추가**를 선택합니다.
5.  **앱 추가** 블레이드에서 **Office 365** > **macOS**를 선택합니다.
6.  **추가**를 선택합니다.

## <a name="configure-the-app-suite"></a>앱 패키지 구성

앱 패키지에 대한 정보를 제공합니다. 이 정보를 사용하여 Intune에서 앱 패키지를 식별하고 사용자가 회사 포털 앱에서 앱 패키지를 찾을 수도 있습니다.

1.  **앱 추가** 블레이드에서 **앱 패키지 정보**를 선택합니다.
2.  다음 정보를 지정합니다.
    - **패키지 이름** - 회사 포털에 표시되는 앱 패키지의 이름을 입력합니다. 사용하는 모든 패키지 이름이 고유한지 확인합니다. 같은 앱 패키지 이름이 두 번 나타나는 경우 앱 중 하나만 회사 포털에서 사용자에게 표시됩니다.
    - **패키지 설명** - 앱 패키지에 대한 설명을 입력합니다.
    - **게시자** - Microsoft가 게시자로 표시됩니다.
    - **범주** - 필요한 경우 기본 제공 앱 범주 중 하나 이상 또는 사용자가 만든 범주를 선택합니다. 이렇게 하면 사용자가 회사 포털을 찾아볼 때 앱 패키지를 더 쉽게 찾을 수 있습니다.
    - **회사 포털에서 이 항목을 추천 앱으로 표시** - 사용자가 앱을 찾아볼 때 회사 포털의 기본 페이지에 앱 패키지가 눈에 띄게 표시됩니다.
    - **정보 URL** - 필요에 따라 이 앱에 대한 정보를 포함하는 웹 사이트의 URL을 입력합니다. URL은 회사 포털에서 사용자에게 표시됩니다.
    - **개인 정보 URL** - 필요에 따라 이 앱에 대한 개인 정보 관련 정보를 포함하는 웹 사이트의 URL을 입력합니다. URL은 회사 포털에서 사용자에게 표시됩니다.
    - **개발자** - Microsoft가 개발자로 표시됩니다.
    - **소유자** - Microsoft가 소유자로 표시됩니다.
    - **메모** - 이 앱과 연결할 모든 메모를 입력합니다.
    - **아이콘 업로드** - 사용자가 회사 포털을 찾아볼 때 이 아이콘이 앱과 함께 표시됩니다.
3.  **확인**을 선택합니다. 패키지가 앱 목록에 단일 항목으로 표시됩니다.

## <a name="configure-app-assignments"></a>앱 할당 구성

이 단계에서는 앱 패키지에 대한 할당을 구성합니다. 사용 가능한 앱 유형이 곧 제공될 예정입니다.

1.  앱 목록에서 앱 패키지를 선택하고 **할당**을 선택합니다.
2.  **그룹 선택**을 선택합니다.
3.  선택한 그룹에 패키지를 할당합니다. 자세한 내용은 [Microsoft intune을 사용하여 그룹에 앱을 할당하는 방법](/intune/apps-deploy)을 참조하세요.
4.  각 그룹에 대해 **설치 필요**를 선택합니다.
        >[!Note]
        > You cannot uninstall Office 365 through Intune.

5. **저장**을 선택하여 할당을 커밋합니다.

## <a name="next-steps"></a>다음 단계

Windows 10 장치에 Office 365 앱을 추가하는 방법은 [Microsoft Intune을 사용하여 Windows 10 장치에 Office 365 ProPlus 2016 앱을 할당하는 방법](/intune/apps-add-office365)을 참조하세요.
