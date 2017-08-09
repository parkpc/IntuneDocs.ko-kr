---
title: "Intune 데이터 웨어하우스 API  | Microsoft 문서"
description: "API를 사용하여 회사의 모바일 환경에 대한 정보를 제공하는 보고서를 작성할 수 있습니다."
keywords: "Intune 데이터 웨어하우스"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 701D6CE9-43F6-4A29-8E84-E2B59931C635
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 5f03fd3a1557ef5d013fe695016ed0e3b119ee62
ms.sourcegitcommit: addf6a40caa22c22adfd2e2eff7d666cd1877e3c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/04/2017
---
#  <a name="intune-data-warehouse-api"></a>Intune 데이터 웨어하우스 API

Intune 데이터 웨어하우스 API를 사용하면 임의의 분석 도구에서 사용할 수 있도록 컴퓨터가 읽을 수 있는 형식으로 Intune 데이터에 액세스할 수 있습니다. API를 사용하여 회사의 모바일 환경에 대한 정보를 제공하는 보고서를 작성할 수 있습니다. API는 다음을 위한 표준 패턴을 따르는 OData 프로토콜을 사용합니다.

  -   요청 및 응답 헤더
  -   상태 코드
  -   HTTP 메서드
  -   URL 규칙
  -   미디어 유형
  -   페이로드 형식
  -   쿼리 옵션

OData(개방형 데이터 프로토콜)는 RESTful API 빌드 및 사용을 위한 모범 사례를 정의하는 OASIS(Advancement of Structured Information Standards)를 위한 조직입니다. Intune 데이터 웨어하우스는 OData 버전 4.0을 사용합니다.

이 참조 섹션은 끝점, 지원되는 HTTP 메서드, 반환 페이로드 형식 및 Intune 데이터 웨어하우스 데이터 모델의 설명서에 대한 개요를 제공합니다.

> [!Important]  
> 베타 버전을 사용하여 데이터 웨어하우스의 최신 기능을 체험해 볼 수 있습니다. 베타 버전을 사용하려면 URL이 쿼리 매개 변수 `api-version=beta`을(를) 포함해야 합니다. 베타 버전에서는 정식 지원되기 전의 기능을 먼저 사용해 볼 수 있습니다. Intune에서 새로운 기능을 추가하면서 베타 버전의 동작과 데이터 계약이 달라질 수 있습니다. 베타 버전의 사용자 지정 코드 또는 보고 도구는 지속적인 업데이트와 함께 중단될 수 있습니다. <!--If you experience problems with the beta service, follow [link to feedback process]() to report the issue or provide feedback.-->

<!-- ## OData custom client

You can access the Intune Data Warehouse data model through RESTful endpoints. To gain access to your data, your client must authorize with Microsoft Azure Active Directory (Azure AD) using OAuth 2.0. You first set up a web app and a client app in Azure, grant permissions to the client. Your local client will get authorization, can then communicate with the Data Warehouse endpoints.

For more information, see [Get data from the Data Warehouse API with a REST client](Get-data-REST.md) -->

## <a name="interacting-with-the-api"></a>API 상호 작용

API는 Azure AD를 통한 권한 부여가 필요합니다. Azure AD는 OAuth 2.0을 사용합니다. 인증을 받으면 HTTP GET 동사를 사용하고 노출된 엔터티 컬렉션에 접촉하여 API에서 데이터를 가져올 수 있습니다. 자세한 내용은 다음을 참조하십시오.

 -  [권한 부여](reports-api-url.md)
 -  [API URL 구조](reports-api-url.md)

## <a name="intune-data-warehouse-data-model"></a>Intune 데이터 웨어하우스 데이터 모델

OData는 모든 클라이언트가 데이터 소스에서 노출된 정보에 액세스할 수 있게 하는 추상 데이터 모델과 프로토콜을 정의합니다. 데이터 모델 설명서 항목은 네임 스페이스, 엔터티 및 Intune 데이터 웨어하우스 데이터 모델의 반환 개체에 대해 설명합니다. 자세한 내용은 [데이터 웨어하우스 데이터 모델](reports-ref-data-model.md)을 참조하세요.

## <a name="for-more-information"></a>추가 정보

[Azure AD의 인증 시나리오](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-scenarios)  
[odata.org](http://www.odata.org)  
[OData 버전 4.0](http://docs.oasis-open.org/odata/odata/v4.0/odata-v4.0-part1-protocol.html)  
