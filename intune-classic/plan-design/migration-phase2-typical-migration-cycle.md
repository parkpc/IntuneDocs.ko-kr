---
title: "일반적인 Intune 마이그레이션 주기 작동 방식 | Microsoft 문서"
description: "이 문서의 목적은 Intune 마이그레이션 주기 작동 방식에 대해 설명하고 고객이 마이그레이션 주기를 처리하는 방법에 대한 예를 제공하는 것입니다."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3688b724-9521-4210-bf4d-bcf47d8d4ca0
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 7130d09d7340aba94f3f9ac72743a281e0aa45ca
ms.contentlocale: ko-kr
ms.lasthandoff: 05/23/2017


---

# <a name="phase-2-typical-migration-cycle"></a>2단계: 일반적인 마이그레이션 주기

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

조직에서는 일반적으로 IT 부서의 사용자 하위 집합을 대상으로, 소규모 파일럿을 통해 Intune 마이그레이션을 시작합니다. 또한 조직은 변경에 대한 그룹의 열의, 사용자 수, 복잡성, 요구 사항, 위치 및 비즈니스 위험 등의 요인에 대해 논의하여 마이그레이션 기간 결정 과정을 지원해야 할 수 있습니다.

다음은 대상 그룹을 예약하는 방법에 대한 예입니다.

  | **마이그레이션 대상 그룹** | **기간 1** | **기간 2** | **기간 3** | **기간 4** | **...**
|:---:|:---:|:---:|:---:|:---:|:---:|
| 제한된 파일럿 IT 조직(사용자 50명) | 계획 발표 | 등록 지시 | 마감일 지정 | 조건부 액세스 적용 |  |                                                        
| 확장된 파일럿 IT 조직(사용자 200명) |  | 계획 발표 | 등록 지시 | 마감일 지정 | 조건부 액세스 적용 | 
| 마이그레이션 1단계 기술에 정통한 사용자(2,000명) |  |  | 계획 발표 | 등록 지시 | 마감일 지정 | 
| 마이그레이션 2단계 미국 동부 |  |  |  | 계획 발표 | 등록 지시 | 
| 모든 지역 |  |  |  |  | 계획 발표 | 

## <a name="customer-migration-case-study"></a>고객 마이그레이션 사례 연구

### <a name="adatum-corporation"></a>Adatum Corporation

- [how Adatum Corporation went through the process of migration from a third-party MDM provider to Intune](https://gallery.technet.microsoft.com/Intune-migration-guide-893a95e3?redir=0)(Adatum Corporation이 타사 MDM 공급자에서 Intune으로 마이그레이션 프로세스를 수행한 방법)을 확인해 보세요.

## <a name="monitoring-migration"></a>마이그레이션 모니터링

Microsoft Intune에서는 마이그레이션을 모니터링할 수 있는 여러 방법을 제공합니다.

1.  Intune 사용자 그룹 뷰

2.  기본 제공 보고서 집합

3.  콘솔 내 경고

다음을 수행할 수 있도록 각 단계 후 얼마나 많은 사용자가 장치를 등록했는지 추적해야 합니다.

-   통신 계획의 효율성 평가

-   조건부 액세스 적용의 영향 예측

[Intune 마이그레이션을 모니터링하는 방법](/intune-classic/deploy-use/understand-microsoft-intune-operations-by-using-reports)에 대해 알아보세요.

## <a name="post-migration"></a>마이그레이션 후

Intune으로 마이그레이션한 후 이전 MDM 공급자를 사용 중지 및/또는 서비스 구독을 취소해야 합니다. 또한 MDM 공급자의 지침에 따라 불필요한 인프라 요구 사항을 제거해야 합니다.

