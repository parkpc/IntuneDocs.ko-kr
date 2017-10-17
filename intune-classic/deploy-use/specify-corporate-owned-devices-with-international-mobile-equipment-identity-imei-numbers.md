---
title: "IMEI 번호 지정"
description: "Microsoft Intune에서는 관리자가 회사 소유의 모바일 장치를 식별하는 데 도움이 되는 모바일 장치 플랫폼용 IMEI 번호를 가져올 수 있습니다."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/22/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1712bd39-562b-4409-9cec-155d5f4d8a39
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9038670a4c0b4bf52868ba739336dd35366eed2f
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/10/2017
---
# <a name="specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers"></a>IMEI(International Mobile Equipment Identity) 번호로 회사 소유의 장치 지정

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune에서는 관리자가 회사 소유의 모바일 장치를 식별하는 데 도움이 되는 IMEI 번호가 있는 모바일 장치 플랫폼에 대해 IMEI(International Mobile Equipment Identity) 번호를 가져올 수 있습니다. Intune에서 장치를 등록한 후에 **그룹** > **개요** > **모든 장치**에서 가져온 IMEI 번호를 갖는 장치가 표시될 수 있습니다. **장치 그룹** 목록에는 가져온 IMEI 번호를 가진 장치가 **소유권** 열에 **회사**로 표시됩니다.

1. [Microsoft Intune 관리 콘솔](https://manage.microsoft.com)에서 **그룹** &gt; **모든 장치** &gt; **회사에서 사전 등록한 모든 장치** &gt; **IMEI(모든 플랫폼) 기준**을 선택한 후 **장치 추가...**를 선택합니다. 두 가지 방법으로 장치를 추가할 수 있습니다.

    -   **일련 번호가 포함된 .csv 파일 업로드** – 머리글 없이 두 열로 이루어진 쉼표로 구분된 값(.csv) 목록을 만들고 목록을 .csv 파일당 장치 5,000대 또는 용량 5MB로 제한합니다. 이 세부 정보 필드는 128자로 제한됩니다. 

        |||
        |-|-|
        |&lt;IMEI #1&gt;|&lt;장치 #1 세부 정보&gt;|
        |&lt;IMEI #2&gt;|&lt;장치 #2 세부 정보&gt;|
        이.csv 파일을 텍스트 편집기에서 보면 다음과 같이 표시됩니다.

        ```
        01234567890123,device details
        02234567890123,device details
        ```

    -   **수동으로 장치 세부 정보 추가** - 최대 15개 장치에 대한 IMEI 번호와 장치 세부 정보를 입력합니다.

   *세부 정보* 필드는 관리 용도로 사용됩니다. 하드웨어 ID별로 나열된 회사 소유 장치 목록에서 장치를 식별하는 데 도움이 되는 세부 정보를 지정할 수 있습니다. 이 정보는 장치에 전송되지 않고 Intune 콘솔에 표시됩니다.

2.   **다음**을 선택합니다.
3.  **장치 검토** 창에서 가져온 장치 IMEI 번호를 확인할 수 있습니다. 가져오는 IMEI 번호에 대한 **세부 정보**를 덮어쓸지 여부를 결정할 수도 있습니다. 현재 세부 정보를 유지하려면 **덮어쓰기** 상자의 선택을 취소할 수 있습니다. **마침**을 선택하여 IMEI 번호를 가져옵니다.
4.  가져온 IMEI 번호 및 설명이 **By IMEI (All platforms)(IMEI 기준(모든 플랫폼))** 목록에 추가됩니다.

> [!IMPORTANT]
> Android 장치에 대한 IMEI 번호를 가져오는 경우 일부 Android 장치에는 여러 IMEI 번호가 있을 수 있다는 것에 유의하세요. IMEI 번호를 가져오지만 장치에서 Intune에 보고한 IMEI가 아닌 경우 장치는 회사 소유 장치가 아니라 개인 장치로 분류됩니다.

IMEI 번호가 있는 장치가 Intune에서 등록되면, 일반적으로 사용자가 회사 포털 앱을 설치하고 등록 프로세스를 완료할 때 장치에 회사 소유로 태그가 지정되며 **IMEI 장치** 그룹에 등록된 것으로 표시됩니다.

>[!NOTE]
> 곧 조직이 새 Azure 포털로 마이그레이션되면 이 기능이 변경됩니다. 기존 Intune 관리자 콘솔에서 관리자는 업로드된 CSV의 연결된 세부 정보를 수락하고 개별 하드웨어 식별자의 기존 세부 정보를 덮어쓸 수 있습니다. 새 Azure 포털에서는 모든 하드웨어 식별자의 세부 정보를 자동으로 덮어쓰거나 기존 식별자의 세부 정보를 모두 무시할 수 있습니다.

International Mobile Equipment Identifiers에 대한 자세한 사양은 [3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729)을 참조하세요.
