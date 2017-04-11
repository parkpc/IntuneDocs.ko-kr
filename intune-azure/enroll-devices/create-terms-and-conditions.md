---
title: "Microsoft Intune에서 사용 약관 설정"
titleSuffix: Intune Azure preview
description: "Intune Azure 미리 보기: Intune용 회사 포털에서 사용자에게 표시되는 사용 약관을 설정합니다. "
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a3a11a8-9c0c-4334-8c6b-6fea4d0a2efb
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 07a42cf8fa10d3223129fbb2932217ff90ac365b
ms.lasthandoff: 02/18/2017

---

# <a name="set-terms-and-conditions"></a>사용 약관 설정 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

사용자 그룹에 Intune 사용 약관을 배포하여 등록, 작업 리소스 액세스, 회사 포털 앱이 장치와 사용자에 미치는 영향을 설명할 수 있습니다. 사용자는 먼저 사용 약관에 동의해야 회사 포털을 사용하여 작업 등록 및 액세스를 수행할 수 있습니다.

각기 다른 사용 약관을 포함하는 여러 정책을 만들어 배포할 수 있습니다. 또한 같은 버전의 사용 약관을 여러 언어로 생성한 다음 적합한 그룹에 배포할 수도 있습니다.

**사용 약관을 만들려면**

1. Azure Portal에서 **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.

2. Intune 블레이드에서 **장치 등록**을 선택한 다음 **사용 약관**을 선택합니다.

3. **만들기**를 선택합니다.

4. **사용 약관 만들기** 블레이드에서 다음 정보를 지정합니다.

   - **표시 이름**: 약관에 사용할 이름입니다. 회사 포털 앱에 이 이름이 표시됩니다.

   - **설명**: Azure Portal에서 정책을 식별하는 데 도움이 되는 선택적 세부 정보입니다.

5. 사용 약관 정의 옆의 화살표를 선택하여 사용 약관 블레이드를 열고 다음 정보를 입력합니다.

   - **제목**: 회사 포털에 표시되는 제목입니다.

   - **사용 약관 요약**: 사용자가 약관에 동의하는 경우 의미를 설명하는 텍스트입니다.

   - **사용 약관**: 사용자가 보고 동의하거나 거부해야 하는 법적 레이블입니다(예: "사용 약관에 동의함").

6. **확인**을 선택합니다.

