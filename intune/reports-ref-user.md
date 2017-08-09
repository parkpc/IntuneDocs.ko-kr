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
ms.openlocfilehash: 2b9739299c52c668117116f54c08715f1218d130
ms.sourcegitcommit: addf6a40caa22c22adfd2e2eff7d666cd1877e3c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/04/2017
---
# <a name="reference-for-user-entity"></a>사용자 엔터티에 대한 참조

**사용자** 범주는 데이터 모델의 사용자와 에이전트 속성을 정의하는 **사용자** 엔터티를 포함합니다.

**사용자**

**사용자** 엔터티는 회사 내 할당된 라이선스가 있는 모든 Azure Active Directory(Azure AD) 사용자를 나열합니다.

| 속성  | 설명 | 예 |
|---------|------------|--------|
| UserKey |데이터 웨어하우스에서 사용자의 고유 식별자 - 대리 키 |123 |
| UserId |사용자의 고유 식별자 - UserKey와 비슷하나 자연 키 |b66bc706-ffff-7437-0340-032819502773 |
| UserEmail |사용자의 메일 주소 |John@constoso.com |
| DisplayName |사용자의 표시 이름 |John |
| IntuneLicensed |이 사용자의 Intune 라이선스 여부를 나타냅니다. |True/False |
| IsDeleted |이 사용자 레코드가 업데이트되었는지 나타냅니다.  True-이 사용자는 이 테이블에서 필드가 업데이트된 새 레코드를 가집니다. False-이 사용자의 최신 레코드입니다. |True/False |
| StartDateInclusiveUTC |이 사용자가 데이터 웨어하우스에서 생성된 UTC 날짜 및 시간 |11/23/2016 12:00:00 AM |
| EndDateExclusiveUTC |IsDeleted가 True로 변경된 UTC 날짜 및 시간 |11/23/2016 12:00:00 AM |
| IsCurrent |이 사용자 레코드가 최신인지 또는 데이터 웨어하우스에 없는지 표시 |True/False |
| RowLastModifiedDateTimeUTC |데이터 웨어하우스에서 사용자가 마지막으로 수정된 UTC 날짜 및 시간 |11/23/2016 12:00:00 AM |

