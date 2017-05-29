---
title: "특별한 마이그레이션 고려 사항 | Microsoft 문서"
description: "이 문서의 목적은 고객이 마이그레이션 캠페인을 시작하기 전에 고객에게 특별한 마이그레이션 고려 사항을 제공하는 것입니다."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f29d2894-e98b-4f2c-b444-a8ccc1b7efdd
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 7e0adb862d8c60805b3b34406e193df5a93be381
ms.contentlocale: ko-kr
ms.lasthandoff: 05/23/2017


---

# <a name="phase-1-special-migration-considerations"></a>1단계: 특별한 마이그레이션 고려 사항

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

기존 MDM 공급자 환경에 따라 적용될 수 있는 특별한 마이그레이션 고려 사항이 있습니다.

## <a name="factory-reset-for-apples-device-enrollment-program-dep"></a>Apple DEP(장치 등록 프로그램)에 대한 초기화

Apple DEP(장치 등록 프로그램)는 최종 사용자가 제거할 수 없는 장치 구성을 설정합니다. DEP의 고급 관리 기능을 유지하려면 초기화를 통해 장치를 기본(신규) 상태로 되돌리고 Intune에 등록해야 합니다.

Intune에서 장치를 관리하는 데 DEP를 계속 사용하려면

1.  [Intune에 DEP](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune)를 등록합니다.

2.  Apple DEP 계정으로 이동하여 기존 MDM 공급자의 [DEP 장치 일련 번호를 Intune에 다시 할당](https://help.apple.com/deployment/business/#/tesf9562af26)합니다.

3.  DEP 계정을 Intune과 [동기화](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune)합니다.

4.  Intune에서 적절한 DEP 등록 프로필을 [만들어 일련 번호에 할당](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune)합니다.

5.  장치를 초기화합니다(현재 MDM 공급자를 통해 원격으로 또는 각 장치에서 수동으로).

6.  최종 사용자에게 장치를 배포합니다.

## <a name="next-steps"></a>다음 단계 

[2단계: 마이그레이션 캠페인](/intune-classic/plan-design/migration-phase2-migration-campaign)

