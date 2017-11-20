---
title: "Intune 데이터 웨어하우스 변경 로그 | Microsoft Docs"
description: "Intune 데이터 웨어하우스 API의 변경 사항 목록입니다."
keywords: "Intune 데이터 웨어하우스"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: E85DBB2D-67BB-4E10-82D6-E43046B9C43C
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6d675a36cd5ea4c11d755174bf2b0bbc5d4b18ec
ms.sourcegitcommit: 5279a0bb8c5aef79aa57aa247ad95888ffe5a12b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2017
---
# <a name="change-log-for-the-intune-data-warehouse-api"></a>Intune 데이터 웨어하우스 API에 대한 변경 로그

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune 데이터 웨어하우스에 대한 업데이트를 최신 상태로 유지합니다.

## <a name="1710"></a>1710
_2017년 11월 출시_

### <a name="user-entity-contains-latest-user-data-in-data-warehouse-data-model----1544273---"></a>데이터 웨어하우스 데이터 모델의 마지막 사용자 데이터를 포함하는 사용자 엔터티<!-- 1544273 -->

Intune 데이터 웨어하우스 데이터 모델의 첫 번째 버전에는 최신 과거 Intune 데이터만 포함되어 있습니다. 보고서 결정권자는 사용자의 현재 상태를 캡처할 수 없습니다. 이 업데이트에서 [**사용자 엔터티**](reports-ref-user.md)는 i번째 최신 사용자 데이터로 채워집니다.

### <a name="new-entities-in-the-in-data-warehouse-data-model----1479526--------"></a>데이터 웨어하우스 데이터 모델의 새 엔터티 <!-- 1479526 --><!-- -->

 - 엔터티 [**UserDeviceAssociation**](reports-ref-user-device.md)이 추가되었습니다. **UserDeviceAssociation**에는 조직의 사용자 장치 연결이 포함되어 있습니다.
 - 엔터티 [**IntuneManagementExtension**](reports-ref-intunemanagementextension.md)이 추가되었습니다. **IntuneManagementExtension**은 버전 및 설치 상태와 같은 정보를 추적하는 모바일 장치에 대한 엔터티를 포함합니다.

## <a name="next-steps"></a>다음 단계
 - [매주 Intune에 추가되는 새로운 기능](whats-new.md)에 대해 알아봅니다. 예정된 변경, 서비스 관련 중요 공지 및 이전 릴리스 관련 정보에 대해서도 알아볼 수 있습니다. 
 - [Microsoft Intune 블로그](http://go.microsoft.com/fwlink/?LinkID=273882)를 읽어 보세요.