---
title: "앱 정보 및 할당을 모니터링하는 방법"
titlesuffix: Azure portal
description: "사용자 또는 장치에 앱을 할당한 후 이 정보를 사용하여 해당 상태를 모니터링할 수 있습니다.\""
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 05/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 64e5133d-1e23-4ee6-b556-f5d32c0e95da
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: fbb1d3e11f8ba3e508a261981e461f35c99ca110
ms.sourcegitcommit: f8672ff73066c2d8bcb78c30f84fda8aa3057a1c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/11/2017
---
# <a name="how-to-monitor-app-information-and-assignments-with-microsoft-intune"></a>Microsoft Intune으로 앱 정보 및 할당을 모니터링 하는 방법

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune에서는 관리하는 앱 속성 및 해당 할당 상태를 모니터링할 수 있는 다양한 방법을 제공합니다.

1. **모바일 앱** 워크로드에서 **관리** > **앱**을 선택합니다.
2. 앱 블레이드 목록에서 정보를 볼 앱을 선택합니다. <*앱 이름*> **장치 설치 상태** 블레이드가 표시됩니다. ![앱 설치 상태 블레이드.](./media/monitor-apps.png)

다음 작업 중 하나를 수행하여 앱 및 해당 할당에 대해 자세히 알아봅니다.

## <a name="general"></a>일반

- **개요** - 앱에 대한 기본적인 개요와 해당 앱의 할당 상태에 대한 정보를 제공합니다. 차트 중 하나를 선택하여 **장치 설치 상태** 또는 **사용자 설치 상태** 블레이드를 열고 더 자세한 정보를 알아볼 수 있습니다.

## <a name="manage"></a>관리

- **속성** - 선택한 앱에 대한 정보를 보고 변경할 수 있습니다. 앱 속성에 대한 자세한 내용은 [Microsoft Intune에 앱을 추가하는 방법](apps-add.md)을 참조하세요.
- **할당** - 이 앱의 할당에 대한 정보를 제공합니다. 자세한 내용은 [Microsoft intune을 사용하여 그룹에 앱을 할당하는 방법](apps-deploy.md)을 참조하세요.

## <a name="monitor"></a>모니터

- **장치 설치 상태** - 장치 이름, 운영 체제, 장치가 Intune에 마지막으로 체크인된 시기, 앱 설치 상태 등 선택한 앱을 할당한 각 장치에 대한 자세한 정보를 제공합니다.
- **사용자 설치 상태** - 모든 장치의 사용자 앱 설치 수, 설치 오류에 대한 정보 등 선택한 앱을 할당한 사용자에 대한 자세한 정보를 제공합니다.