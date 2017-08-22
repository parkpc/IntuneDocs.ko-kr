---
title: "Intune 데이터 웨어하우스 사용 | Microsoft 문서"
description: "Intune 데이터 웨어하우스를 사용하여 기업 모바일 환경에 대한 정보를 제공하는 보고서를 만듭니다."
keywords: "Intune 데이터 웨어하우스"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 57019B11-DF9B-4D8A-95FE-254C75398DDE
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: cb311429e0537709b3476154bdef24347cb99026
ms.sourcegitcommit: 294de4d4058de2c625abb8143e90880d27da9284
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2017
---
# <a name="use-the-intune-data-warehouse"></a>Intune 데이터 웨어하우스 사용

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune 데이터 웨어하우스를 사용하여 기업 모바일 환경에 대한 정보를 제공하는 보고서를 만듭니다. 예를 들어 일부 보고서는 다음과 같은 내용을 포함합니다.
-   라이선스 구매 최적화를 위한 Intune 등록 사용자 추세
-   모바일 장치 상태를 검토하기 위한 앱 및 OS 버전 분석
-   정책 업데이트를 원활하게 롤아웃하기 위한 등록 및 장치 규정 준수 추세

데이터 웨어하우스는 Azure 포털보다 모바일 환경에 대해 더 많은 정보를 제공합니다. Intune 데이터 웨어하우스를 통해 다음에 액세스할 수 있습니다.

  -  과거 Intune 데이터
  -  일 단위로 새로 고침되는 데이터
  -  OData 표준을 사용하는 데이터 모델

> [!Important]  
> 베타 버전을 사용하여 데이터 웨어하우스의 최신 기능을 체험해 볼 수 있습니다. 베타 버전을 사용하려면 URL이 쿼리 매개 변수 `api-version=beta`을(를) 포함해야 합니다. 베타 버전에서는 정식 지원되기 전의 기능을 먼저 사용해 볼 수 있습니다. Intune에서 새로운 기능을 추가하면서 베타 버전의 동작과 데이터 계약이 달라질 수 있습니다. 베타 버전의 사용자 지정 코드 또는 보고 도구는 지속적인 업데이트와 함께 중단될 수 있습니다. <!-- If you experience problems with the beta service, follow [link to feedback process]() to report the issue or provide feedback.-->

**다음 단계**

- 링크를 받고 Power BI를 사용하여 정보를 파악합니다. 자세한 내용은 [Power BI를 통해 Intune 데이터 웨어하우스에 연결](reports-proc-get-a-link-powerbi.md)을 참조하세요.
- Intune 데이터 웨어하우스 API, 데이터 모델, 엔터티 간 관계에 대해 자세히 알아보려면<!-- , and an example of creating a custom client to retrieve data,--> [Intune 데이터 웨어하우스 API](reports-nav-intune-data-warehouse.md)를 참조하세요.