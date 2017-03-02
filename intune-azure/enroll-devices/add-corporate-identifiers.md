---
title: "Intune에 IMEI 식별자 추가 | Intune Azure 미리 보기 | Microsoft Docs"
description: "Intune Azure 미리 보기: Microsoft Intune에 회사 식별자(IMEI 번호)을 추가하는 방법을 알아봅니다. "
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 08dad848a48adad7d9c6f0b5b3286f6550a266bd
ms.openlocfilehash: 8667f063de65fd5fa86149ac124b236a432eecef
ms.lasthandoff: 02/15/2017

---

# <a name="add-corporate-identifiers"></a>회사 식별자 추가

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

회사 장치를 식별하는 IMEI(International Mobile Equipment Identity) 번호 목록을 만들 수 있습니다. 이러한 장치는 등록되거나 등록되지 않을 수 있으며, 상태가 "등록됨" 또는 "연결되지 않음"으로 지정됩니다. "연결되지 않음"은 장치가 Intune 서비스에 체크 인되어 있지 않음을 의미합니다.

목록을 만들려면 헤더 없이&2;열로 구성된 쉼표로 구분된 값(.csv) 목록을 만듭니다. 왼쪽 열에 IMEI 식별자를 추가하고 오른쪽 열에 세부 정보를 추가합니다. 현재 목록의 최대값은 500개 행입니다.

텍스트 편집기에 .csv 목록이 다음과 같이 표시됩니다.

01 234567 890123,장치 세부 정보</br>
02 234567 890123,장치 세부 정보

**회사 식별자의 .csv 목록을 추가하려면**

1. Azure Portal에서 **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.

2. Intune 블레이드에서 **장치 등록**을 선택한 다음 **회사 장치 식별자**를 선택합니다.

3. 기존 세부 정보를 덮어쓰는 새로운 세부 정보가 포함된 파일을 가져오려면 **기존 식별자에 대한 세부 정보를 덮어씁니다**를 선택하여 기존 세부 정보를 새로운 세부 정보로 바꿉니다.

4. IMEI CSV 파일로 이동하여 **추가**를 선택합니다.

**회사 식별자의 .csv 목록을 삭제하려면**

1. Azure Portal에서 **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.

2. Intune 블레이드에서 **장치 등록**을 선택한 다음 **회사 장치 식별자**를 선택합니다.

3. **삭제**를 선택합니다.

