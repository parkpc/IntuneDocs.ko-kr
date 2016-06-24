---
# required metadata

title: 앱 업데이트 | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: beee6933-876a-4be0-b395-4c24cfbd519b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune을 사용하여 앱 업데이트
Microsoft Intune은 앱 업데이트를 관리하는 데 유용합니다. 이 항목의 정보를 토대로 새 버전이 필요할 때 앱을 업데이트할 수 있는 방법을 파악할 수 있습니다.

## 앱을 업데이트하는 방법
배포한 새 앱 버전이 출시되면 Intune에서 최신 버전의 앱을 업데이트하고 배포할 수 있습니다. 배포를 최신 버전의 동일한 앱으로 바꿀 수 있습니다(동일한 식별자 사용). 앱 업데이트를 사용하여 다른 앱 패키지로 배포를 업데이트할 수 없습니다.

> [!IMPORTANT]
> **필수 설치** 배포 작업을 수행하여 앱을 배포했다가 나중에 배포 작업을 **사용 가능한 설치**로 변경하면 배포를 변경하기 전에 앱을 설치했던 장치에 앱의 업데이트가 자동으로 설치되지 않습니다. 이 문제를 해결하려면 다음을 수행할 수 있습니다.
> 
> -   장치 사용자에게 회사 포털로 이동하여 설치된 앱을 선택한 다음 **설치**를 클릭하도록 합니다.
> -   배포 작업을 **제거**로 변경하고 앱이 제거된 후 **사용 가능한 설치**배포 작업을 통해 앱을 다시 배포합니다.

### 앱을 업데이트하려면

1.  [Microsoft Intune 관리자 콘솔](https://manage.microsoft.com)에서 **앱** &gt; **앱**을 클릭합니다.

2.  **관리 소프트웨어** 목록에서 업데이트할 앱을 선택하고 **편집**을 클릭합니다.

3.  **소프트웨어 편집** 마법사에서 앱 패키지에 대한 새로운 세부 정보를 제공합니다.

4.  작업이 끝나면 **업데이트**를 클릭합니다.

다음에 장치가 사용 가능한 앱을 확인하면 앱이 최신 버전으로 자동 업데이트됩니다.





<!--HONumber=May16_HO2-->


