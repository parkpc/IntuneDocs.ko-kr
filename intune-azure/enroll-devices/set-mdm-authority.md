---
title: "모바일 장치 관리 기관 설정"
titleSuffix: Intune Azure preview
description: "Intune Azure 미리 보기: Intune에서 모바일 장치 관리 기관을 설정하는 방법을 알아봅니다. "
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 01/06/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8deff871-5dff-4767-9484-647428998d82
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 9d7a1a934188f0a40553d3c6b8b567ba8f6af034
ms.lasthandoff: 02/18/2017

---

# <a name="set-the-mobile-device-management-authority"></a>모바일 장치 관리 기관 설정 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

모바일 장치 관리 기관 설정에 따라 장치를 관리하는 방법이 결정됩니다. 가능한 구성은 다음과 같습니다.

- **Intune 독립 실행형** - Azure Portal을 사용하여 구성하는 클라우드 전용 관리입니다. Intune에서 제공하는 모든 기능 집합을 포함합니다.

- **Intune 하이브리드** - Intune 클라우드 솔루션과 System Center Configuration Manager의 통합입니다. Configuration Manager 콘솔을 사용하여 Intune을 구성합니다.

- **Office 365용 모바일 장치 관리 ** - Office 365와 Intune 클라우드 솔루션의 통합입니다. Office 365 관리 센터에서 Intune을 구성합니다. Intune 독립 실행형에서 제공되는 기능 중 일부를 포함합니다.

>[!IMPORTANT]
>모바일 장치 관리 기관을 설정한 후 이를 변경하려면 [Microsoft 지원](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune)에 문의해야 하므로 신중하게 선택해야 합니다.

**모바일 장치 관리 기관을 설정하려면:**

1. Azure Portal에서 **More Services**(추가 서비스) > **모니터링 + 관리** > **Intune**을 선택합니다.

2. Intune 블레이드에서 **장치 등록**을 선택한 다음 **개요**를 선택합니다.

3. **장치 관리 시작** 블레이드에서 **MDM 기관을 Intune으로 설정**을 선택합니다. MDM 기관을 Intune으로 설정했음을 나타내는 메시지가 표시됩니다.

