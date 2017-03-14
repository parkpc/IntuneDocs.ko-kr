---
title: "Windows 10 장치에 대한 Intune 메일 설정"
titleSuffix: Intune Azure preview
description: "Intune Azure 미리 보기: Windows 10 장치에서 메일 연결을 구성하는 데 사용할 수 있는 Intune 설정을 알아봅니다."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2ffafbd0-4b5d-4c86-a46b-611f9b7a58e5
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 9a052f26d87fbfdc5794cf97033b409846db6a73
ms.lasthandoff: 02/18/2017


---

# <a name="email-profile-settings-for-windows-10-devices-in-microsoft-intune"></a>Microsoft Intune의 Windows 10 장치에 대한 메일 프로필 설정

[!INCLUDE[azure_preview](../includes/azure_preview.md)]



- **메일 서버** - Exchange Server의 호스트 이름입니다.
- **계정 이름** - 장치에서 사용자에게 표시될 메일 계정의 표시 이름입니다.
- **AAD의 사용자 이름 특성** - 이것은 이 메일 프로필에 대한 사용자 이름을 생성하는 데 사용되는 Active Directory(AD) 또는 Azure AD의 특성입니다. **user1@contoso.com**와 같은 **기본 SMTP 주소** 또는 **user1**, **user1@contoso.com**와 같은 **사용자 계정 이름**을 선택합니다.
- **AAD의 메일 주소 특성** - 각 장치에서 사용자의 메일 주소가 생성되는 방식을 선택합니다. **기본 SMTP 주소**를 선택하여 Exchange에 로그인하는 기본 SMTP 주소를 사용하거나 **사용자 계정 이름**을 사용하여 메일 주소와 전체 사용자 이름을 사용합니다.


## <a name="security-settings"></a>보안 설정

- **SSL** - 메일을 전송하거나 수신할 때와 Exchange Server와 통신할 때 SSL(Secure Sockets Layer) 통신을 사용합니다.



## <a name="synchronization-settings"></a>동기화 설정

- **동기화할 메일 양** - 동기화할 메일의 일 수를 선택하거나, **무제한**을 선택하여 사용 가능한 모든 메일을 동기화합니다.
- **동기화 일정** - 장치가 Exchange 서버의 데이터를 동기화할 일정을 선택합니다. 데이터가 도착하는 즉시 동기화하는 **메시지가 도착할 때**를 선택하거나 또는 장치의 사용자가 동기화를 시작해야 하는 **수동**을 선택할 수도 있습니다.

## <a name="content-sync-settings"></a>콘텐츠 동기화 설정

- **동기화할 콘텐츠 형식** - 장치에 동기화할 콘텐츠 형식을 선택합니다.
    - **연락처**
    - **일정**
    - **태스크**

