---
title: "Android 장치에 대한 Intune 사용자 지정 설정 | Intune Azure 미리 보기 | Microsoft Docs"
description: "Intune Azure 미리 보기: Android 사용자 지정 프로필에서 사용할 수 있는 설정을 알아봅니다."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 494b3892-916e-4b40-9b67-61adec889bdf
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5ab494a3dd1e1bdea9703ab314574b192c5208ee
ms.openlocfilehash: 3a80a69a27b540b66fb96e098c0b0f66a0854297


---

# <a name="custom-settings-for-android-devices-in-intune-azure-preview"></a>Intune Azure 미리 보기의 Android 장치에 대한 사용자 지정 설정

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Microsoft Intune Android **사용자 지정** 프로필을 사용하여 Android 장치에서 기능을 제어하는 데 사용할 수 있는 OMA-URI 설정을 배포합니다. 이는 많은 모바일 장치 제조업체가 장치 기능을 제어하는 데 사용하는 표준 설정입니다.

이 기능은 Intune 정책을 사용하여 구성할 수 없는 Android 설정을 배포할 수 있도록 하기 위한 것입니다.

## <a name="custom-profile-settings-for-android-devices"></a>Android 장치에 대한 사용자 지정 프로필 설정

1. [Microsoft Intune에서 사용자 지정 장치 설정을 구성하는 방법](how-to-configure-custom-settings.md)의 지침을 사용하여 시작합니다.
2. **프로필 만들기** 블레이드에서 **설정**을 선택하여 하나 이상의 OMA-URI 설정을 추가합니다.
3. **행 편집** 블레이드에서 각 설정에 대해 다음 값을 구성합니다.
    - **이름** - 설정 목록에서 쉽게 식별할 수 있도록 OMA-URI 설정에 대한 고유한 이름을 입력합니다.
    - **설명** - 설정의 개요에 대한 설명과 찾을 때 도움이 되는 기타 관련 정보를 제공합니다.
    - **데이터 형식** - 이 OMA-URI 설정을 지정할 데이터 형식을 선택합니다. **문자열**, **문자열(XML)**, **날짜 및 시간**, **정수**, **부동 소수점** 또는 **부울** 중에서 선택합니다.
    - **OMA-URI** - 설정을 제공하려는 OMA-URI를 지정합니다.
    - **값** - 입력한 OMA-URI와 연결할 값을 입력합니다.
4. 완료되면 **확인**을 클릭한 다음 필요에 따라 설정을 계속 추가합니다.



<!--HONumber=Feb17_HO1-->


