---
title: Microsoft Intune에 웹앱을 추가하는 방법
titleSuffix: ''
description: Microsoft Intune에 웹앱을 추가하는 방법을 알아봅니다.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/08/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5f08752f-0e87-4ad9-a34c-4991b3150775
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 45253e061039198aee4aa49b2bf879a1b9929e35
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-web-apps-to-microsoft-intune"></a>Microsoft Intune에 웹앱을 추가하는 방법

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune은 웹앱을 포함하여 다양한 앱 유형을 지원합니다. 웹앱은 클라이언트-서버 응용 프로그램입니다. 서버는 UI, 콘텐츠 및 기능을 포함하는 웹앱을 제공합니다. 또한 플랫폼을 호스팅하는 현대식 웹은 일반적으로 보안, 부하 분산 및 기타 이점을 제공합니다. 웹 앱은 웹에서 별도로 유지 관리됩니다. Microsoft Intune을 사용하여 이 앱 유형을 가리킵니다. 또한 이 앱에 액세스할 수 있는 사용자 그룹을 할당합니다. 

사용자의 앱을 관리하고 할당하려면 먼저 Intune에 앱을 추가합니다. Intune이 사용자의 장치 홈 화면에 웹앱 바로 가기를 만듭니다.

> [!Note]
> Android for Work 및 macOS에서는 웹앱이 지원되지 않습니다.

Intune에 앱을 웹용 앱의 바로 가기로 추가하려면 다음 단계를 완료하세요.

1. 로그인은 [Azure 포털](https://portal.azure.com)합니다.
2. **모든 서비스** > **Intune**을 선택합니다. Intune은 **모니터링 + 관리** 섹션에 있습니다.
3. **Microsoft Intune** 창에서 **모바일 앱**을 선택합니다.
4. **모바일 앱** 창에서 **앱**을 선택합니다.
5. 앱 목록 위에서 **추가**를 선택합니다. **앱 추가** 창이 표시됩니다.
6. **앱 추가** 창의 **앱 유형** 드롭다운 목록에서 **웹 링크** 유형을 선택합니다.
7. **구성** 옵션을 선택하여 **앱 정보** 창을 표시합니다.
8. **앱 정보** 창에서 다음 정보를 추가합니다.
    - **이름** - 회사 포털에 표시되는 앱 이름을 입력합니다.
    - **설명** - 앱에 대한 설명을 입력합니다. 이 설명은 회사 포털에서 최종 사용자에게 표시됩니다.
    - **게시자** - 이 앱의 게시자 이름을 입력합니다.
    - **앱 URL** - 할당할 앱을 호스트하는 웹 사이트의 URL을 입력합니다.
    - **범주(선택 사항)** - 기본 제공 앱 범주 중 하나 이상 또는 사용자가 만든 범주를 선택합니다. 이러게 범주를 선택하면 사용자가 회사 포털을 찾아볼 때 앱을 더 쉽게 찾을 수 있습니다.
    - **회사 포털에서 이 항목을 추천 앱으로 표시** - 사용자가 앱을 찾을 때 회사 포털의 기본 페이지에서 앱이 눈에 띄게 표시됩니다.
    - **이 링크를 열려면 Managed Browser가 필요** - 웹 사이트 또는 웹앱 링크가 할당된 사용자는 Intune Managed Browser에서 링크를 열 수 있습니다. 이 브라우저는 장치에 설치되어 있어야 합니다.
    - **로고** - 앱과 연결된 로고를 업로드할 수 있습니다. 이 로고는 사용자가 회사 포털을 찾아볼 때 앱과 함께 표시되는 로고입니다.
9. 작업이 완료되면 **정보 추가** 창에서 **확인**을 선택합니다.
10. 그런 다음, **앱 추가** 창에서 **추가**를 선택합니다.

> [!Note]
> 사용자는 자신의 홈 화면에 Intune 위젯을 추가하여 Android 장치에 할당된 웹앱을 표시해야 합니다.

## <a name="next-steps"></a>다음 단계

- 만든 앱이 앱 목록에 표시되며, 여기서 이 앱을 선택한 그룹에 할당할 수 있습니다. 도움말은 [그룹에 앱을 할당하는 방법](apps-deploy.md)을 참조하세요.