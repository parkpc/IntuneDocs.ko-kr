---
title: "앱 업데이트"
description: "이 항목의 정보를 토대로 새 버전이 필요할 때 앱을 업데이트할 수 있는 방법을 파악할 수 있습니다."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: beee6933-876a-4be0-b395-4c24cfbd519b
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: c643ea0e75a3376a30d43fc0c5ac4ef421c65bea
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2017
---
# <a name="update-apps-using-microsoft-intune"></a>Microsoft Intune을 사용하여 앱 업데이트

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune은 앱 업데이트를 관리하는 데 유용합니다. 이 항목의 정보를 토대로 새 버전이 필요할 때 앱을 업데이트할 수 있는 방법을 파악할 수 있습니다.

## <a name="how-to-update-apps"></a>앱을 업데이트하는 방법
배포한 새 앱 버전이 출시되면 Intune에서 최신 버전의 앱을 업데이트하고 배포할 수 있습니다. 배포를 최신 버전의 동일한 앱(식별자가 동일)으로 바꿀 수 있습니다. 앱 업데이트를 사용하여 다른 앱 패키지로 배포를 업데이트할 수 없습니다.

### <a name="app-identifiers"></a>앱 식별자
앱 식별자는 앱을 고유하게 식별하는 속성입니다. 동일한 식별자를 가진 앱의 여러 복사본을 설치할 수 없습니다. 식별자에 대한 몇 가지 예는 다음과 같습니다.

- **iOS** - 번들 ID(예: com.microsoft.excel)
- **Android** - 패키지 ID(예: com.microsoft.excel)
- **Windows Phone** - (xap 설치 관리자) 제품 ID(GUID) 사용
- **Windows** - (appx/appxbundle) 패키지의 전체 이름 사용



> [!IMPORTANT]
> **필수 설치** 배포 작업을 수행하여 앱을 배포했다가 나중에 배포 작업을 **사용 가능한 설치**로 변경하면 배포를 변경하기 전에 앱을 설치했던 장치에 앱의 업데이트가 자동으로 설치되지 않습니다. 이 문제를 해결하려면 다음을 수행할 수 있습니다.
>
> -   장치 사용자에게 회사 포털로 이동하여 설치된 앱을 선택한 다음 **설치**를 선택합니다.
> -   배포 작업을 **제거**로 변경하고 앱이 제거된 후 **사용 가능한 설치**배포 작업을 통해 앱을 다시 배포합니다.

### <a name="to-update-an-app"></a>앱을 업데이트하려면

1.  [Microsoft Intune 관리 콘솔](https://manage.microsoft.com)에서 **앱** &gt; **앱**을 선택합니다.

2.  **관리 소프트웨어** 목록에서 업데이트할 앱을 선택하고 **편집**을 선택합니다.

3.  **소프트웨어 편집** 마법사에서 앱 패키지에 대한 새로운 세부 정보를 제공합니다.

4.  작업이 끝나면 **업데이트**를 선택합니다.

다음에 장치가 사용 가능한 앱을 확인하면 앱이 최신 버전으로 자동 업데이트됩니다.
앱 패키지(기간 업무 앱)에서 설치된 앱의 경우 필수 및 사용 가능한 배포 둘 다에 대해 앱이 업그레이드되며 동일한 식별자를 갖습니다.

스토어에 링크로 배포된 앱의 경우 앱이 시작된 스토어에서 업데이트가 관리됩니다.
