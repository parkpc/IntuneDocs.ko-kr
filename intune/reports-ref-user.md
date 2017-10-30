---
title: "사용자 | Microsoft 문서"
description: "Intune 데이터 웨어하우스 API에서 엔터티 컬렉션의 사용자 범주에 대한 항목을 참조하세요."
keywords: "Intune 데이터 웨어하우스"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: C29A6EEA-72B7-427E-9601-E05B408F3BB0
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: be8b7041882539c4e379074cffea385f582f686e
ms.sourcegitcommit: bb2c181fd6de929cf1e5d3856e048d617eb72063
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/20/2017
---
# <a name="reference-for-user-entity"></a>사용자 엔터티에 대한 참조

**사용자** 범주는 데이터 모델의 사용자와 에이전트 속성을 정의하는 **사용자** 엔터티를 포함합니다.

**사용자**

**사용자** 엔터티는 회사 내 할당된 라이선스가 있는 모든 Azure Active Directory(Azure AD) 사용자를 나열합니다.

| 속성  | 설명 | 예 |
|---------|------------|--------|
| UserKey |데이터 웨어하우스의 사용자에 대한 고유 식별자 - 서로게이트 키 |123 |
| UserId |사용자에 대한 고유 식별자 - UserKey와 비슷하지만 자연 키입니다. |b66bc706-ffff-7437-0340-032819502773 |
| UserEmail |사용자의 이메일 주소 |John@constoso.com |
| DisplayName |사용자의 표시 이름 |John |
| IntuneLicensed |이 사용자의 Intune 라이선스 여부를 나타냅니다. |True/False |
| IsDeleted |이 사용자 레코드가 업데이트되었는지 나타냅니다.  True-이 사용자는 이 테이블에서 필드가 업데이트된 새 레코드를 가집니다. False-이 사용자의 최신 레코드입니다. |True/False |
| StartDateInclusiveUTC |데이터 웨어하우스에서 해당 사용자를 만든 UTC 날짜 및 시간 |11/23/2016 12:00:00 AM |
| EndDateExclusiveUTC |IsDeleted를 True로 변경한 UTC 날짜 및 시간 |11/23/2016 12:00:00 AM |
| IsCurrent |해당 사용자 레코드가 데이터 웨어하우스에 있는지 여부를 나타냅니다. |True/False |
| RowLastModifiedDateTimeUTC |데이터 웨어하우스에서 해당 사용자를 마지막으로 수정한 UTC 날짜 및 시간 |11/23/2016 12:00:00 AM |

