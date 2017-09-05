---
title: "Intune을 사용하여 장치에서 회사 데이터 제거"
titleSuffix: Intune on Azure
description: "Intune으로 관리하는 장치에서 회사 데이터만 제거하는 방법을 알아봅니다.\""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f021e95f-157f-4e8a-9253-1cff03d6ee3e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8074d6e7cc0a061a6708f8c8bfae1a4dfcb6daa3
ms.sourcegitcommit: 10e3ab2aeb79a1fb2243bef2748ccc003fdd4cc7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/02/2017
---
# <a name="remove-company-data-from-intune-managed-devices"></a>Intune으로 관리하는 장치에서 회사 데이터 제거


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

**회사 데이터 제거** 장치 작업을 통해 Intune으로 관리하는 장치에서 회사 데이터만 제거합니다. 이 작업에서는 장치에서 개인 데이터를 제거하지 않습니다. 제거하고 나면 Intune에서 더 이상 장치를 관리하지 않으므로 더 이상 회사 리소스에 액세스할 수 없습니다.

## <a name="supported-platforms"></a>지원되는 플랫폼

- Windows - 지원됨(Azure Active Directory에 연결된 Windows 장치에는 지원되지 않음)
- Windows Phone - 지원됨
- iOS - 지원됨
- macOS - 지원됨
- Android - 지원됨

## <a name="how-to-remove-company-data"></a>회사 데이터 제거 방법

1. Azure 포털에 로그인합니다.
2. **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
3. **Intune** 블레이드에서 **장치**를 선택합니다.
4. **장치 및 그룹** 블레이드에서 **모든 장치**를 선택합니다.
5. 관리하는 장치 목록에서 장치를 선택한 다음 **회사 데이터 제거** 장치 원격 작업을 선택합니다.

## <a name="next-steps"></a>다음 단계

방금 수행한 작업의 상태를 확인하려면 **장치 및 그룹** 블레이드에서 **장치 작업**을 선택합니다.
