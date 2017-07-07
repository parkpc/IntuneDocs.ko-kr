---
title: "Intune을 사용하여 장치에서 회사 데이터 제거"
titleSuffix: Intune on Azure
description: "Intune으로 관리하는 장치에서 회사 데이터만 제거하는 방법을 알아봅니다.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/27/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f021e95f-157f-4e8a-9253-1cff03d6ee3e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 39acd12333e9685f94d23416fb1a61ce93f45476
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2017
---
# <a name="remove-company-data-from-intune-managed-devices"></a>Intune으로 관리하는 장치에서 회사 데이터 제거


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

**회사 데이터 제거** 기능은 Intune으로 관리하는 장치에서 회사 데이터만 제거합니다. 장치에서 개인 데이터를 제거하지 않습니다. 장치가 더 이상 Intune에서 관리되지 않으며 더 이상 회사 리소스에 액세스할 수 없습니다(Azure Active Directory에 가입된 Windows 장치에 대해 지원되지 않음).

1. Azure 포털에 로그인합니다.
2. **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
3. **Intune** 블레이드에서 **장치**를 선택합니다.
4. **장치 및 그룹** 블레이드에서 **모든 장치**를 선택합니다.
5. 관리하는 장치 목록에서 장치를 선택한 다음 **회사 데이터 제거** 장치 원격 작업을 선택합니다.

방금 수행한 작업의 상태를 확인하려면 **장치 및 그룹** 블레이드에서 **장치 작업**을 선택합니다.
