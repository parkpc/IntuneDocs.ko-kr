---
title: "사용자 장치 연결 | Microsoft Docs"
description: "Intune 데이터 웨어하우스 API의 엔터티 컬렉션에 대한 사용자 장치 연결 범주에 대한 참조 항목입니다."
keywords: "Intune 데이터 웨어하우스"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 09/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: BCDBABCB-A7B1-42F2-BDD1-D055E33F2239
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 490e29f87c65875a385472e6abe9400363383f9b
ms.sourcegitcommit: bb2c181fd6de929cf1e5d3856e048d617eb72063
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/20/2017
---
# <a name="reference-for-user-device-association-entity"></a>사용자 장치 연결 엔터티에 대한 참조

**사용자 장치 연결** 범주에는 조직의 장치 연결을 정의하는 데 사용되는 **사용자 장치 연결** 엔터티가 포함됩니다.

**사용자 장치 연결**

**사용자 장치 연결** 엔터티는 조직의 장치 연결 정의를 나타냅니다.

| Name               | 설명                                                                                      | 예                |
|--------------------|--------------------------------------------------------------------------------------------------|------------------------|
| UserKey            | 데이터 웨어하우스의 사용자에 대한 고유 식별자 - 서로게이트 키                             | 123                    |
| DeviceKey          | 데이터 웨어하우스의 장치에 대한 고유 식별자                                           | 123                    |
| CreatedDateTimeUTC | 사용자 장치 연결을 만든 UTC 날짜 및 시간                               | 11/23/2016 12:00:00 AM |
| IsDeleted          | 사용자가 해당 장치를 등록 취소했으며 연결이 현재 더 이상 존재하지 않음을 나타냅니다. | True                   |
| EndedDateTimeUTC   | IsDeleted를 **True**로 변경한 UTC 날짜 및 시간                                         | 06/23/2017 12:00:00 AM |