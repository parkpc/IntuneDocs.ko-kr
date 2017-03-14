---
title: "Windows Phone 8.1 장치에 대한 Intune 사용자 지정 설정"
titleSuffix: Intune Azure preview
description: "Intune Azure 미리 보기: Windows Phone 8.1 사용자 지정 프로필에서 사용할 수 있는 설정을 알아봅니다."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 21c55041-3821-4a62-9f85-855b97dba269
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 652eca69f3e53365b75fd8590fce299209e2a12f
ms.lasthandoff: 02/18/2017


---

# <a name="custom-settings-for-windows-phone-81-devices-in-microsoft-intune"></a>Microsoft Intune의 Windows Phone 8.1 장치에 대한 사용자 지정 설정

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Microsoft Intune Windows Phone 8.1 **사용자 지정** 프로필을 사용하여 Windows Phone 8.1 장치에서 기능을 제어하는 데 사용할 수 있는 OMA-URI 설정을 배포할 수 있습니다. 이는 많은 모바일 장치 제조업체가 장치 기능을 제어하는 데 사용하는 표준 설정입니다.

이 기능은 다른 Intune 정책을 사용하여 구성할 수 없는 설정을 배포할 수 있도록 하기 위한 것입니다.

## <a name="custom-policy-settings-for-windows-phone-81-devices"></a>Windows Phone 8.1 장치에 대한 사용자 지정 정책 설정

1. [Microsoft Intune에서 사용자 지정 장치 설정을 구성하는 방법](how-to-configure-custom-settings.md)의 지침을 사용하여 시작합니다.
2. **프로필 만들기** 블레이드에서 **설정**을 선택하여 하나 이상의 OMA-URI 설정을 추가합니다.
3. **행 추가** 블레이드에서 각 설정에 대해 다음 값을 구성합니다.
    - **이름** - 설정 목록에서 쉽게 식별할 수 있도록 OMA-URI 설정에 대한 고유한 이름을 입력합니다.
    - **설명** - 설정의 개요에 대한 설명과 찾을 때 도움이 되는 기타 관련 정보를 제공합니다.
    - **OMA-URI** - 설정을 제공하려는 OMA-URI를 지정합니다.
    - **데이터 형식** - 이 OMA-URI 설정을 지정할 데이터 형식을 선택합니다. **문자열**, **날짜 및 시간**, **정수**, **부동 소수점** 또는 **부울** 중에서 선택합니다.
    - **값** - 입력한 OMA-URI와 연결할 값을 입력합니다.

4. 완료되면 **확인**을 클릭한 다음 필요에 따라 설정을 계속 추가합니다.

