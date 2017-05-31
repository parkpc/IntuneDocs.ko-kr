---
title: "iOS 장치에 대한 Intune AirPlay 설정"
titleSuffix: Intune Azure preview
description: "Intune을 사용하여 AirPlay 호환 장치에 iOS 장치를 자동으로 연결하는 방법을 알아봅니다."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 712a79fb-14ef-4f6b-aba5-1dfca900afd2
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: ad2f20603261ec0eac4156facd3fd23b2982f517
ms.contentlocale: ko-kr
ms.lasthandoff: 05/23/2017


---

# <a name="intune-airplay-settings-for-ios-devices"></a>iOS 장치에 대한 Intune AirPlay 설정

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

이러한 설정을 사용하여 네트워크에서 AirPlay 호환 장치(예: Apple TV)를 관리하는 iOS 장치를 연결할 수 있습니다.
이 기능을 사용하여 다음을 수행할 수 있습니다.

- **장치 및 암호 목록 구성** - AirPlay 장치의 이름과 암호로 장치를 프로비전하여 장치가 범위 내에 있을 때 자동으로 연결되도록 합니다. 암호를 제공하는 경우에는 최종 사용자가 연결할 때 해당 암호를 입력할 필요가 없습니다.
- **허용된 대상 구성** - AirPlay 장치 목록을 장치 ID를 기준으로 구성합니다. 최종 사용자는 나열한 장치만 보고 연결할 수 있게 됩니다(감독 모드 장치에만 해당).

## <a name="get-started"></a>시작

1. **장치 기능** 블레이드에서 **AirPlay**를 선택합니다.
2. **AirPlay** 블레이드에서 다음 작업 중 하나 또는 모두를 선택합니다.

## <a name="configure-a-device-and-password-list"></a>장치 및 암호 목록 구성

1. **암호** 블레이드에서 Airlpay 장치의 **장치 이름** 및 **암호**를 입력합니다(예: **Contoso Apple TV**).
2. 장치 세부 정보를 입력한 후 **추가**를 클릭합니다. **장치 이름** 목록에 해당 장치가 표시됩니다.
3. 장치를 계속 추가합니다. 작업이 끝나면 **확인**을 선택합니다.


## <a name="configure-allowed-destinations"></a>허용된 대상 구성

1. **허용된 대상(감독 모드에서만 해당)* 블레이드에서 Airlpay 장치의 **장치 ID**를 입력합니다(예: 52:46:CD:51:83:4C).
2. 장치 ID를 입력한 후 **추가**를 클릭합니다. **장치 ID** 목록에 해당 ID가 표시됩니다.
3. 장치를 계속 추가합니다. 작업이 끝나면 **확인**을 선택합니다.

장치 및 암호, 그리고 허용된 대상을 쉼표로 구분된 값(csv) 파일로 가져올 수도 있습니다.



