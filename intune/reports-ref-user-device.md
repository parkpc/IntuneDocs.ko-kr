---
title: "사용자 장치 연결 - Intune 데이터 웨어하우스 | Microsoft Docs"
description: "Intune 데이터 웨어하우스 API의 변경 사항 목록입니다."
keywords: "Intune 데이터 웨어하우스"
author: Erikre
ms.author: erikre
manager: angrobe
ms.date: 10/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 777484A7-09CE-4409-987F-76B3F87DFE93
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 095395be4c86780ad65ba1e24b856f6eef8d41ae
ms.sourcegitcommit: d44c32aad3e84f6c0b296bdb010981d3a818befb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2018
---
# <a name="user-device-association"></a>사용자 장치 연결

**UserDeviceAssociation** 엔터티에는 조직의 사용자 장치 연결이 포함되어 있습니다.

| 이름               | 설명                                                                                      | 예제                |
|--------------------|--------------------------------------------------------------------------------------------------|------------------------|
| UserKey            | 데이터 웨어하우스에서 사용자의 고유 식별자입니다. (서로게이트 키입니다.)                              | 123                    |
| DeviceKey          | 데이터 웨어하우스의 장치에 대한 고유 식별자                                            | 123                    |
| CreatedDateTimeUTC | 사용자 장치 연결을 만든 날짜 및 시간. UTC 형식을 사용합니다.                                | 11/23/2016 12:00:00 AM |
| IsDeleted          | 사용자가 해당 장치를 등록 취소했으며 연결이 현재 더 이상 존재하지 않음을 나타냅니다. | True/False             |
| EndedDateTimeUTC   | IsDeleted를 **True**로 변경한 UTC 날짜 및 시간                                              | 06/23/2017 12:00:00 AM |
