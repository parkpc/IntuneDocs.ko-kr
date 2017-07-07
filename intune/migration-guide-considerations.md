---
title: "특별 마이그레이션 고려 사항"
description: "이 문서의 목적은 고객이 마이그레이션 캠페인을 시작하기 전에 고객에게 특별한 마이그레이션 고려 사항을 제공하는 것입니다."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f29d2894-e98b-4f2c-b444-a8ccc1b7efdd
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: bc39ffd3a4f11a4c2b32f75dc5befcd8ce42f43e
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2017
---
# <a name="special-migration-considerations"></a>특별 마이그레이션 고려 사항

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

기존 MDM 공급자 환경에 따라 적용될 수 있는 특별한 마이그레이션 고려 사항이 있습니다.

## <a name="factory-reset-for-apples-device-enrollment-program-dep"></a>Apple DEP(장치 등록 프로그램)에 대한 초기화

Apple DEP(장치 등록 프로그램)는 최종 사용자가 제거할 수 없는 장치 구성을 설정합니다. DEP의 고급 관리 기능을 유지하려면 초기화를 통해 장치를 기본(신규) 상태로 되돌리고 Intune에 등록해야 합니다.

계속해서 DEP를 사용하여 Intune에서 장치를 관리하려면 [장치 등록 프로그램을 사용하여 iOS 장치 등록을 설정](/intune/device-enrollment-program-enroll-ios)합니다.


## <a name="next-steps"></a>다음 단계 

[2단계: 마이그레이션 캠페인](migration-guide-campaign.md)
