---
# required metadata

title: IMEI(International Mobile Equipment Identity) 번호로 회사 소유의 장치 지정 | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 1712bd39-562b-4409-9cec-155d5f4d8a39

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# IMEI(International Mobile Equipment Identity) 번호로 회사 소유의 장치 지정
Microsoft Intune에서는 관리자가 회사 소유의 모바일 장치를 식별하는 데 도움이 되는 IMEI 번호가 있는 모바일 장치 플랫폼에 대해 IMEI(International Mobile Equipment Identity) 번호를 가져올 수 있습니다. Intune에 등록되었으며 가져온 IMEI 번호가 있는 장치는 **그룹** > **개요** > **모든 장치** > **회사에서 사전 등록한 장치** > **IMEI(모든 플랫폼) 기준** 아래에서 볼 수 있습니다.

1. [Microsoft Intune 관리 콘솔](http://manage.microsoft.com)에서 **그룹** &gt; **모든 장치** &gt; **회사에서 사전 등록한 모든 장치** &gt; **IMEI(모든 플랫폼) 기준**을 선택한 후 **장치 추가...**를 선택합니다. 두 가지 방법으로 장치를 추가할 수 있습니다.

    -   **일련 번호가 포함된 CSV 파일 업로드** – 머리글 없이 두 열로 이루어진 쉼표로 구분된 값 목록을 만듭니다. csv 파일당 장치 5,000대 또는 용량 5MB로 제한됩니다.

        |||
        |-|-|
        |&lt;IMEI #1&gt;|&lt;장치 #1 세부 정보&gt;|
        |&lt;IMEI #2&gt;|&lt;장치 #2 세부 정보&gt;|
        이.csv 파일을 텍스트 편집기에서 보면 다음과 같이 표시됩니다.

        ```
        AA-BBBBBB-CCCCCC-D,PO 1234
        AA-BBBBBB-CCCCCC-E,PO 1234
        ```

    -   **수동으로 장치 세부 정보 추가** - 최대 5개 장치에 대한 IMEI 번호와 장치 세부 정보를 입력합니다.

   *세부 정보*는 장치와 연결된 IMEI 번호를 식별할 수 있도록 관리 용도로 사용됩니다. 이 정보는 장치에 전송되지 않고 Intune 콘솔에 표시됩니다.

2.   **다음**을 선택합니다.
3.  **장치 검토** 창에서 가져오는 장치 IMEI 번호를 확인할 수 있습니다. 가져오는 IMEI 번호에 대한 **세부 정보**를 덮어쓸지 여부를 결정할 수도 있습니다. 현재 세부 정보를 유지하려면 **덮어쓰기** 확인란의 선택을 취소할 수 있습니다. **마침**을 선택하여 IMEI 번호를 가져옵니다.
4.  추가한 IMEI 번호 및 설명이 **By IMEI (All platforms)(IMEI 기준(모든 플랫폼))** 목록에 추가됩니다.

IMEI 번호가 있는 장치가 등록되면, 일반적으로 사용자가 회사 포털 앱을 설치하고 등록 프로세스를 완료할 때 장치에 회사 소유로 태그가 지정되며 **IMEI 장치** 그룹에 등록된 것으로 표시됩니다.


<!--HONumber=May16_HO5-->


