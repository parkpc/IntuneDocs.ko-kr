---
title: "Microsoft Intune을 사용하여 macOS 장치에 Office 365 설치"
titlesuffix: 
description: "Microsoft Intune을 사용하여 macOS 장치에 Office 365 앱을 설치하는 방법을 알아봅니다."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2372332a-7e3a-4a9c-91a9-86654e0fabe2
ms.reviewer: aiwang
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8de14184c4d23adc79d5b519fdcf272f0d7f6804
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/08/2018
---
# <a name="how-to-assign-office-365-to-macos-devices-with-microsoft-intune"></a>Microsoft Intune을 사용하여 macOS 장치에 Office 365를 할당하는 방법

이 **스토어 앱** 유형을 사용하면 macOS 장치에 Office 365 앱을 쉽게 할당할 수 있습니다. 이 앱 유형을 통해 Word, Excel, PowerPoint, Outlook 및 OneNote를 설치할 수 있습니다. 또한 이러한 앱은 MAU(Microsoft 자동 업데이트)와 함께 제공되므로 앱을 더 안전하게 최신 상태로 유지할 수 있습니다. 원하는 앱이 Intune 콘솔의 앱 목록에 하나의 앱으로 표시됩니다.


## <a name="before-you-start"></a>시작하기 전에

macOS 장치에 Office 365를 추가하기 전에 다음 세부 정보를 이해해야 합니다.

- 이 앱을 배포할 장치에서 macOS 10.10 이상을 실행하고 있어야 합니다.
- Intune은 Mac용 Office 2016 제품군에 포함된 Office 앱 추가를 지원합니다.
- Intune에서 앱 패키지를 설치할 때 Office 앱이 열려 있으면 최종 사용자가 저장하지 않은 파일의 데이터가 손실될 수 있습니다.

## <a name="create-and-configure-the-app-suite"></a>앱 패키지 만들기 및 구성

**앱** 블레이드를 사용하여 Office 365를 추가합니다.
1. 로그인은 [Azure 포털](https://portal.azure.com)합니다.
2. **모든 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
3. **Intune** 블레이드에서 **모바일 앱**을 선택합니다.
4. **모바일 앱** 워크로드의 **관리** 센션에서 **앱**을 선택합니다. 
5. **앱 추가** 블레이드를 표시하는 **추가**를 선택합니다.
6. **앱 유형** 목록의 **Office 365 패키지** 그룹에서 **macOS**를 선택합니다.
7. 앱 패키지에 대한 정보를 제공하려면 **앱 패키지 정보**를 선택합니다. 이 정보를 사용하여 Intune에서 앱 패키지을 식별하고 사용자가 회사 포털 앱에서 앱 패키지을 찾을 수도 있습니다.
8.  다음 정보를 지정합니다.
    - **패키지 이름** - 회사 포털에 표시되는 앱 패키지의 이름을 입력합니다. 사용하는 모든 패키지 이름이 고유한지 확인합니다. 같은 앱 패키지 이름이 두 번 나타나는 경우 앱 중 하나만 회사 포털에서 사용자에게 표시됩니다.
    - **패키지 설명** - 앱 패키지에 대한 설명을 입력합니다.
    - **게시자** - Microsoft가 게시자로 표시됩니다.
    - **카테고리** - 기본 제공 앱 범주 중 하나 이상 또는 사용자가 만든 범주를 선택합니다. 이 설정을 통해 사용자가 회사 포털을 찾아볼 때 앱 패키지를 더 쉽게 찾을 수 있습니다.
    - **회사 포털에서 이 항목을 추천 앱으로 표시** - 이 설정은 사용자가 앱을 찾아볼 때 회사 포털의 기본 페이지에 앱 패키지가 눈에 띄게 표시합니다.
    - **정보 URL** - (선택 사항) 이 앱에 대한 정보를 포함하는 웹 사이트의 URL을 입력합니다. URL은 회사 포털에서 사용자에게 표시됩니다.
    - **개인 정보 URL** - (선택 사항) 이 앱에 대한 개인 정보 관련 정보를 포함하는 웹 사이트의 URL을 입력합니다. URL은 회사 포털에서 사용자에게 표시됩니다.
    - **개발자** - Microsoft가 개발자로 표시됩니다.
    - **소유자** - Microsoft가 소유자로 표시됩니다.
    - **메모** - (선택 사항) 이 앱과 연결할 모든 메모를 입력합니다.
    - **로고** - Office 365 로고는 사용자가 회사 포털을 찾아볼 때 앱과 함께 표시되는 로고입니다.
9.  **앱 정보** 블레이드에서 **확인**을 클릭합니다.
10. **앱 추가** 블레이드에서 **추가**를 클릭합니다.
    패키지가 앱 목록에 단일 항목으로 표시됩니다.

## <a name="configure-app-assignments"></a>앱 할당 구성

이 단계에서는 앱 패키지에 대한 할당을 구성합니다. 

1. 앱 목록에서 **Office 365** 앱 패키지를 선택해 **Office 365** 개요 블레이드를 표시합니다.
2. **Office 365** 블레이드에서 **할당**을 클릭합니다.
3. 앱 패키지를 사용하여 그룹을 추가하려면 **그룹 추가**를 클릭합니다. **그룹 추가** 블레이드가 표시됩니다.
3. **배정 형식**을 **필요**에 따라 설정합니다.
4. 선택한 그룹에 패키지를 할당합니다. 자세한 내용은 [Microsoft intune을 사용하여 그룹에 앱을 할당하는 방법](apps-deploy.md)을 참조하세요.

    >[!Note]
    > Office 365 앱 패키지를 필요로 하는 모든 그룹은 Microsoft Intune을 통해 제거할 수 없습니다.

5. **할당** 블레이드에서 **확인**을 선택합니다.
6. **그룹 추가** 블레이드에서 **확인**을 선택합니다.
7. **저장**을 선택하여 할당을 커밋합니다.

## <a name="next-steps"></a>다음 단계

- Windows 10 장치에 Office 365 앱을 추가하는 방법은 [Microsoft Intune을 사용하여 Windows 10 장치에 Office 365 ProPlus 2016 앱을 할당하는 방법](apps-add-office365.md)을 참조하세요.
- 사용자 그룹에 앱 할당을 포함하고 제외하는 방법에 대한 자세한 내용은 [앱 할당 포함 및 제외](apps-inc-exl-assignments.md)를 참조합니다.
