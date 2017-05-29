---
title: "Intune에tj 등록 제한 설정"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: 플랫폼별로 등록을 제한하고 Intune에서 장치 등록 제한을 설정합니다. "
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: d99f7ca5b5e96a7ab113a14d36f0fef474411836
ms.contentlocale: ko-kr
ms.lasthandoff: 05/23/2017

---

# <a name="set-enrollment-restrictions"></a>등록 제한 설정 

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

등록할 수 있는 장치의 유형 및 최대 수를 설정할 수 있습니다. [등록 제한] 블레이드에서 다음을 설정할 수 있습니다.

- 등록할 수 있는 플랫폼 및 개인적으로 소유한 Android 및 iOS용 장치의 등록을 차단할지 여부

- 사용자가 등록할 수 있는 최대 장치 수

## <a name="set-device-type-restrictions"></a>장치 유형 제한 설정

1. Azure Portal에서 **More Services**(추가 서비스) > **모니터링 + 관리** > **Intune**을 선택합니다.

2. [Intune] 블레이드에서 **장치 등록**을 선택한 다음 **등록 제한**을 선택합니다.

3. **장치 유형 제한**에서 **기본값**을 선택합니다.

4. **모든 사용자** 블레이드에서 **플랫폼**을 선택합니다.

5. Intune에 등록을 허용할 플랫폼에 대해 **허용**을 선택합니다. 등록을 차단하려는 플랫폼에 대해 **차단**을 선택합니다. 플랫폼은 기본적으로 **허용**으로 설정되어 있습니다. 

    >[!NOTE]
    >이러한 설정은 Intune 소프트웨어 클라이언트를 사용하는 Windows 등록에는 적용되지 않거나 이 등록을 차단합니다. 이러한 설정은 모바일 장치 관리를 사용한 등록에만 적용됩니다. 

6. **저장**을 선택합니다.

7. **플랫폼 구성**을 선택합니다.

8. 개인적으로 소유한 iOS 장치의 등록을 **허용**할지 또는 **차단**할지 선택합니다.

9. **저장**을 선택합니다.

## <a name="set-device-limit-restrictions"></a>장치 개수 제한

1. Azure Portal에서 **More Services**(추가 서비스) > **모니터링 + 관리** > **Intune**을 선택합니다.

2. [Intune] 블레이드에서 **장치 등록**을 선택한 다음 **등록 제한**을 선택합니다.

3. **장치 제한 한도**에서 **기본값**을 선택합니다.

4. **모든 사용자** 블레이드에서 **장치 제한**을 선택합니다.

5. 그런 다음 사용자가 등록할 수 있는 최대 장치 수를 선택하고 **저장**을 선택합니다.

