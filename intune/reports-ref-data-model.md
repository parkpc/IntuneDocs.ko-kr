---
title: "데이터 웨어하우스 데이터 모델 | Microsoft 문서"
description: "Intune 데이터 웨어하우스 샘플 데이터는 항상 변화하는 모바일 환경에 대한 과거 보기를 제공합니다."
keywords: "Intune 데이터 웨어하우스"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4D04D3D9-4B6C-41CD-AAF8-466AF8FA6032
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d52e240763263ac4f761a8635ee6694a45168354
ms.sourcegitcommit: bb2c181fd6de929cf1e5d3856e048d617eb72063
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/20/2017
---
# <a name="data-warehouse-data-model"></a>데이터 웨어하우스 데이터 모델

Intune 데이터 웨어하우스 샘플 데이터는 항상 변화하는 모바일 환경에 대한 과거 보기를 제공합니다.

테넌트에서 가져온 데이터는 데이터 웨어하우스에 추가됩니다. 웨어하우스는 하려는 질문의 유형에 의미 있는 엔터티와 관계의 집합입니다. 예를 들어 지난주 동안 하루에 사내에서 개발된 Android 응용 프로그램의 설치 수를 검토하여 설치가 증가하는 추세인지 평가할 수 있습니다. 데이터 웨어하우스 구조를 통해 모바일 환경에 대한 정보를 얻을 수 있습니다. 결과적으로 Microsoft Power BI와 같은 분석 도구는 데이터 웨어하우스 데이터 모델을 사용하여 시각화 및 동적 대시보드를 만들 수 있습니다.

Intune 데이터 웨어하우스 구조는 별모양 스키마 모델을 사용합니다. 별모양 스키마에서는 시간 차원에 대해 팩트를 구성합니다. 모델 컨텍스트에서 *팩트*는 장치 수, 앱, 개수 또는 등록 시간 같은 정량 측정값을 나타냅니다. 모델 컨텍스트에서 *차원*은 범주와 그 계층 관계의 집합입니다. 예를 들어 일은 달로, 달은 년으로 그룹화됩니다. 별모양 스키마 모델은 유연성과 데이터 분석을 위해 최적화되므로 진화하는 모바일 환경을 이해하는 데 필요한 보고서를 생성할 수 있습니다.

웨어하우스는 다음과 같은 개략적인 범주로 데이터를 노출합니다.
  -  앱 보호가 설정된 앱 및 사용량
  -  등록된 장치, 속성 및 인벤토리
  -  앱 및 소프트웨어 인벤토리
  -  장치 구성 및 규정 준수 정책

**데이터 모델 엔터티 집합**

엔터티 집합은 데이터 모델의 이름이 있는 엔터티 컬렉션입니다. 이 집합에는 모델에서 수집된 데이터를 정의하는 엔터티가 포함됩니다. 각 엔터티 집합은 데이터 웨어하우스 데이터 모델에 대한 액세스 포인트를 제공합니다. 다음 범주의 엔터티에 대한 정보를 찾을 수 있습니다.

  -  [날짜](reports-ref-date.md)
  -  [사용자](reports-ref-user.md)
  -  [모바일 앱 관리(MAM)](reports-ref-mobile-app-management.md)
  -  [장치](reports-ref-devices.md)
  -  [응용 프로그램](reports-ref-application.md)
  -  [정책](reports-ref-policy.md)
  -  [사용자 장치 연결](reports-ref-userdeviceassociations.md)

<!-- ## Data Model relationships

For more information on the relationships in the data model, see [Relationships of Entities](reports-api-entity-relationships.md). -->