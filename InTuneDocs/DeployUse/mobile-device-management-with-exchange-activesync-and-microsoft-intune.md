---
title: "Exchange ActiveSync와 Microsoft Intune을 사용한 모바일 장치 관리 | Microsoft Intune"
description: 
keywords: 
author: nathbarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 14f5cf53-6764-4e22-a18b-fa750b3acd41
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 779127bfd39145010f0d9b6609286aaf4dedfdc8
ms.openlocfilehash: d24395786daa7aec103ec754895868a75983e099


---

# Exchange ActiveSync와 Microsoft Intune을 사용한 모바일 장치 관리
Microsoft Intune에서 모바일 장치를 직접 관리하려면 사용자가 Intune에 장치를 등록해야 합니다. 사용자가 등록하지 않은 모바일 장치에 대해 Exchange 커넥터를 사용하여 EAS(Exchange ActiveSync) 관리를 사용하도록 설정할 수 있습니다. 장치는 온-프레미스 Exchange 서버 또는 Microsoft Office 365에서 클라우드 방식으로 호스트하는 Exchange를 사용하여 관리할 수 있습니다.

## 모바일 장치의 Exchange 액세스 규칙 ##

Exchange를 사용하려면 모바일 장치가 EAS에 연결을 시도할 때 일어나는 일을 정의하는 규칙 집합이 필요합니다. 이러한 규칙은 Intune 관리 콘솔에서 관리됩니다.

[모바일 장치의 Exchange 액세스 규칙](exchange-access-rules-for-mobile-devices.md)

## Exchange Connector 설치
Exchange Connector를 사용하면 Intune 콘솔에서 Exchange 배포를 관리할 수 있습니다. 먼저 적절한 Intune과 Exchange 간 커넥터를 설치하고 구성해야 합니다. Exchange Server가 온-프레미스인지 또는 클라우드에서 서비스로 호스트되는지에 따라 적절한 옵션을 선택합니다.

-   [온-프레미스 Exchange용 Intune 커넥터 설치](intune-on-premises-exchange-connector.md)
-   [호스트된 Exchange용 Intune 서비스 간 커넥터 구성](intune-service-to-service-exchange-connector.md)

## Exchange에서 관리하는 모바일 장치에 대한 정책 적용
Intune 콘솔을 통해 정책 설정을 적용할 수 있습니다. [Microsoft Intune 정책을 사용하여 장치의 설정 및 기능 관리](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)를 참조하세요. 특정 모바일 장치별로 지원되는 Exchange ActiveSync 정책 설정 및 기능의 목록은 [Exchange ActiveSync Client Comparison Table(Exchange ActiveSync 클라이언트 비교 표)](http://go.microsoft.com/fwlink/?LinkId=247270)을 참조하세요.

> [!NOTE]
> Intune 내에 더 구체적인 정책이 정의되어 있지 않은 경우, Intune을 Microsoft Exchange 환경에 연결하면 Intune을 통해 관리되는 모든 사용자에 대한 Microsoft Exchange Server 정책이 Microsoft Exchange 서버의 현재 기본 정책으로 다시 설정됩니다.

## 모바일 장치에서 회사 데이터 초기화
마지막으로 더 이상 사용하지 않거나 장치가 분실 또는 도난당한 경우 [EAS 관리 모바일 장치에서 회사 데이터를 초기화](wipe-for-exchange-managed-mobile-devices.md)할 수 있습니다.



<!--HONumber=Jun16_HO4-->


