﻿---
title: "모바일 장치의 Exchange 액세스 규칙"
description: "EAS를 통한 장치 연결을 허용하거나 차단할 Exchange ActiveSync 액세스 규칙"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 208b9f45-02d9-413a-b86a-8bad9b5008fa
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 097d6ee8a7ad6752d48f554ee0bc9b3729311fe2
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/10/2017
---
# <a name="exchange-access-rules-for-mobile-devices"></a>모바일 장치의 Exchange 액세스 규칙

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

모바일 장치에 대한 Exchange 액세스 규칙은 해당 장치가 Exchange ActiveSync에 대해 가져야 하는 액세스 수준을 결정합니다. 이러한 설정은 Microsoft Intune에 등록되지 않은 모바일 장치를 포함하는 모든 모바일 장치에 적용됩니다. 먼저 **기본 규칙**을 정의할 수 있습니다. 기본 규칙은 사용자 지정 규칙이 적용되지 않은 모든 모바일 장치에 적용됩니다.

다음 표에는 Exchange ActiveSync에서 관리하는 액세스 수준이 정리되어 있습니다.

|액세스 수준|설명|
|----------------|---------------|
|**장치에서 Exchange에 액세스하도록 허용**|*액세스 허용* 상태에서 모바일 장치는 Exchange ActiveSync를 통해 동기화할 수 있으며 Exchange 서버에 연결하여 메일을 검색하고 일정, 연락처, 작업 및 메모를 관리할 수 있습니다. Exchange 관리자가 사용자나 특정 모바일 장치를 차단하지 않은 상태에서 Exchange에서 구성된 Exchange ActiveSync 사서함 정책을 준수하는 한 장치는 이 상태로 계속 유지됩니다.|
|**장치에서 Exchange에 액세스하지 못하도록 차단**|*액세스 차단* 상태에서 모바일 장치는 차단되고 Exchange 서버에 연결할 수 없습니다. 장치는 HTTP 403 사용할 수 없음 오류를 받습니다. 사용자는 Exchange 서버로부터 모바일 장치에서 해당 사서함에 대한 액세스가 차단되었다는 내용의 메일 메시지를 받습니다. 이 메시지는 차단된 모바일 장치에 있을 수 없습니다. **사용자 알림 설정** 작업으로 이 메시지에 사용자 지정 텍스트를 추가하여 장치가 차단된 사용자에게 지침을 제공할 수 있습니다. |
|**나중에 허용하거나 차단할 수 있도록 장치 격리**|모바일 장치가 격리된 경우 모바일 장치에서 Exchange 서버에 연결할 수 있습니다. 하지만 데이터에 제한적으로만 액세스할 수 있습니다. 사용자가 일정, 연락처, 작업 및 메모 폴더에 콘텐츠를 추가할 수 있지만 서버가 해당 장치에서는 사용자 사서함의 모든 콘텐츠를 검색할 수 없도록 합니다. 사용자는 모바일 장치가 격리되었다는 내용의 단일 메일 메시지를 받습니다. 이 메시지는 장치 및 사용자의 사서함에 전송됩니다. **사용자 알림 설정** 작업을 통해 이 메시지에 사용자 지정 텍스트를 추가하여 장치가 격리된 사용자에게 지침을 제공할 수 있습니다.|

액세스 전략은 **기본 규칙**과 **플랫폼 예외**를 조합하는 것이며, 이러한 규칙은 Exchange에 연결된 모든 모바일 장치에 적용됩니다. 다음 표에 몇 가지 예제 액세스 전략이 정리되어 있습니다.

|액세스 전략|설명|
|-------------------|---------------|
|허용 목록|*허용 목록*을 사용하면 알려진 장치 목록에 액세스 권한을 부여하고 다른 모든 장치에서의 액세스를 제한할 수 있습니다. 이렇게 하려면 사용자 사서함에 액세스할 수 있도록 허용된 장치 플랫폼용 사용자 지정 규칙을 만들어야 합니다. 이러한 규칙을 만든 후 다른 모든 장치를 차단 또는 격리하는 기본 액세스 규칙을 설정해야 합니다. 허용 목록에 새 장치를 추가하려면 새 사용자 지정 규칙을 만듭니다.|
|차단 목록|*차단 목록*을 사용하면 기본적으로 모든 장치에 액세스 권한을 부여하면서 원치 않는 일련의 장치가 조직에 액세스하지 못하도록 차단할 수 있습니다. 원치 않는 장치 플랫폼이 조직의 사서함과 동기화하지 못하도록 차단하는 사용자 지정 규칙을 만들어 차단 목록을 만듭니다. 기본 규칙은 기존 규칙에서 명시적으로 차단되지 않은 모든 장치에 액세스를 허용하도록 설정하는 것이 좋습니다. 차단 목록에 새 장치나 일련의 장치를 추가하려면 새 사용자 지정 규칙을 만듭니다.|
|허용 및 차단 혼합|허용 목록과 차단 목록을 만드는 것 외에도, 새 모바일 장치가 조직에 액세스할 때 이 모바일 장치를 평가하는 동안 격리시킬 수 있습니다. 예를 들어 조직에서 허용되지 않는 모바일 장치에 대한 차단 목록과 조직에서 허용되는 모바일 장치에 대한 허용 목록이 있는 경우 기본 규칙을 격리로 설정할 수 있습니다. 다른 모든 장치가 자동으로 격리됩니다. 조직에 액세스하는 새 장치를 찾아 허용 또는 차단 목록에 추가할지 여부를 결정할 수 있습니다.|
다음 절차에서는 사용자 지정 규칙을 만드는 방법에 대해 설명합니다.

## <a name="create-a-default-access-rule"></a>기본 액세스 규칙 만들기

1.  [Microsoft Intune 관리 콘솔](https://manage.microsoft.com)에서 **정책** &gt; **Exchange ActiveSync**를 선택합니다.

2.  **기본 규칙** 목록에서, 규칙 또는 개인 예외에 포함되지 않는 모든 모바일 장치에 적용할 액세스 규칙을 선택합니다. **저장**을 선택합니다.

다음 절차에서는 사용자 지정 규칙을 만드는 방법에 대해 설명합니다.

## <a name="create-a-custom-access-rule"></a>사용자 지정 액세스 규칙 만들기

1. [Microsoft Intune 관리 콘솔](https://manage.microsoft.com)에서 **정책** &gt; **Exchange ActiveSync**를 선택합니다.

2.  **플랫폼 예외** 목록에서 **규칙 추가**를 선택하고 사용자 지정 규칙을 만듭니다. **저장**을 선택합니다.
