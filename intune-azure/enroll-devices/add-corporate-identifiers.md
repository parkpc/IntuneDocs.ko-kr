---
title: "Intune에 IMEI 식별자 추가"
titleSuffix: Intune Azure preview
description: "Intune Azure 미리 보기: Microsoft Intune에 회사 식별자(IMEI 번호)을 추가하는 방법을 알아봅니다. "
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/22/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 15415f9f31d520d66257df3a7e134e4b1de8467c
ms.openlocfilehash: 8c9e6b39ee01697d993e5738ec35e8a64fc8e236
ms.lasthandoff: 04/07/2017

---

# <a name="add-corporate-identifiers"></a>회사 식별자 추가

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

IT 관리자 역할로, IMEI(International Mobile Equipment Identity) 번호가 나열된 쉼표로 구분된 값(.csv) 파일을 만든 후 가져와서 회사 소유의 장치를 식별할 수 있습니다. 각 IMEI 번호에는 관리 용도로 목록에 지정된 세부 정보를 포함할 수 있습니다.

<!-- When you upload serial numbers for company-owned iOS devices, they must be paired with a corporate enrollment profile. Devices must then be enrolled using either Apple’s device enrollment program (DEP) or Apple Configurator to have them appear as company-owned. -->

## <a name="add-corporate-identifiers"></a>회사 식별자 추가
목록을 만들려면 헤더 없이 2열로 구성된 쉼표로 구분된 값(.csv) 목록을 만듭니다. 왼쪽 열에 IMEI 식별자를 추가하고 오른쪽 열에 세부 정보를 추가합니다. 세부 정보는 128자로 제한되며 관리 용도로만 사용됩니다. 세부 정보는 장치에 표시되지 않습니다. 현재는 .csv 파일당 500개의 행으로 제한됩니다.

**일련 번호가 포함된 .csv 파일 업로드** – 머리글 없이 두 열로 이루어진 쉼표로 구분된 값(.csv) 목록을 만들고 목록을 .csv 파일당 장치 5,000대 또는 용량 5MB로 제한합니다. 

|||
|-|-|
|&lt;IMEI #1&gt;|&lt;장치 #1 세부 정보&gt;|
|&lt;IMEI #2&gt;|&lt;장치 #2 세부 정보&gt;|

이.csv 파일을 텍스트 편집기에서 보면 다음과 같이 표시됩니다.

```
01234567890123,device details
02234567890123,device details
```


> [!IMPORTANT]
> 일부 Android 장치는 IMEI 번호가 여러 개 있습니다. Intune에서는 장치당 IMEI 번호 하나를 인벤토리에 배정합니다. IMEI 번호를 가져오지만 Intune에서 인벤토리에 배정한 IMEI가 아닌 경우 장치는 회사 소유 장치가 아니라 개인 장치로 분류됩니다. 한 장치에 대해 여러 IMEI 번호를 가져오면 인벤토리에 배정되지 않은 번호는 등록 상태가 **알 수 없음**으로 표시됩니다.

**회사 식별자의 .csv 목록을 추가하려면**

1. Azure Portal에서 **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.

2. Intune 블레이드에서 **장치 등록** > **등록 제한**을 선택하고 **회사 장치 식별자**를 선택한 다음 **추가**를 클릭합니다.

3. **식별자 추가** 블레이드에서 식별자 형식 **IMEI**를 지정합니다. 이전에 가져온 숫자가 **기존 식별자 세부 정보를 덮어쓸지**를 지정할 수 있습니다.  

4. 폴더 아이콘을 클릭하고 가져오려는 목록의 경로를 지정하세요. IMEI CSV 파일로 이동하여 **추가**를 선택합니다.

번호를 가져오면 이러한 장치는 등록되거나 등록되지 않을 수도 있으며, 상태가 **등록됨** 또는 **연결되지 않음**으로 지정될 수 있습니다. **연결되지 않음**은 장치가 Intune 서비스와 통신된 적이 없음을 의미합니다.

## <a name="delete--corporate-identifiers"></a>회사 식별자 삭제

1. Azure Portal에서 **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.

2. Intune 블레이드에서 **장치 등록** > **등록 제한**을 선택하고 **회사 장치 식별자**를 선택한 다음 **삭제**를 선택합니다.

3. **식별자 삭제**에서 삭제할 장치 ID의 .csv 파일을 찾은 다음 **삭제**를 클릭합니다.

## <a name="imei-specifications"></a>IMEI 사양
International Mobile Equipment Identifiers에 대한 자세한 사양은 [3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729)을 참조하세요.

