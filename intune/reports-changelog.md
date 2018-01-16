---
title: "Intune 데이터 웨어하우스 변경 로그 | Microsoft Docs"
description: "Intune 데이터 웨어하우스 API의 변경 사항 목록입니다."
keywords: "Intune 데이터 웨어하우스"
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 12/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: E85DBB2D-67BB-4E10-82D6-E43046B9C43C
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d1078dfeebae22f0754502935c983db13de60a60
ms.sourcegitcommit: a3a744ea55f38a360ca9f788c77a5b3018d1add5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/30/2017
---
# <a name="change-log-for-the-intune-data-warehouse-api"></a>Intune 데이터 웨어하우스 API에 대한 변경 로그

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune 데이터 웨어하우스에 대한 업데이트를 최신 상태로 유지합니다.

## <a name="1710"></a>1710
_2017년 11월 출시됨_

### <a name="a-new-entity-collection-named-current-user-is-limited-to-currently-active-user-data----1544273---"></a>현재 사용자라는 새 엔터티 컬렉션은 현재 활성 사용자 데이터로 제한됨<!-- 1544273 -->

**사용자** 엔터티 컬렉션에는 엔터프라이즈에서 할당된 라이선스를 가진 모든 Azure AD(Azure Active Directory) 사용자가 포함됩니다. 이러한 레코드에는 사용자가 제거된 경우에도 데이터 컬렉션 기간의 사용자 상태가 포함됩니다. 예를 들어, 사용자가 Intune에 추가된 다음 지난달 중에 제거되었을 수 있습니다. 보고 시점에는 이 사용자가 없지만 데이터에는 사용자와 상태가 있습니다. 데이터에 있는 사용자의 현재 상태 기록에 대한 기간을 보여 주는 보고서를 만들 수 있습니다.

이와 달리 새 **현재 사용자** 엔터티 컬렉션에는 제거되지 않은 사용자만 포함됩니다. **현재 사용자** 엔터티 컬렉션에는 현재 활성 사용자만 포함됩니다. **현재 사용자** 엔터티 컬렉션에 대한 자세한 내용은 [현재 사용자 엔터티에 대한 참조](reports-ref-current-user.md)를 참조하세요.

## <a name="1709"></a>1709
_2017년 10월 출시됨_

### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>Intune 데이터 웨어하우스 데이터 모델에 추가된 사용자 장치 연결 엔터티 컬렉션 <!-- 1187917 -->

이제 사용자와 장치 엔터티 컬렉션을 연결하는 사용자 장치 연결 정보를 사용하여 보고서 및 데이터 시각화를 작성할 수 있습니다. 데이터 모델은 데이터 웨어하우스 Intune 페이지에서 검색한 Power BI 파일(PBIX)이나 OData 끝점을 통해 액세스하거나 사용자 지정 클라이언트를 개발하여 액세스할 수 있습니다. 자세한 내용은 [사용자 장치 연결](reports-ref-user-device.md)을 참조하세요.

### <a name="new-entities-in-the-in-data-warehouse-data-model----1479526--------"></a>데이터 웨어하우스 데이터 모델의 새 엔터티 <!-- 1479526 --><!-- -->

 - 엔터티 [**UserDeviceAssociation**](reports-ref-user-device.md)이 추가되었습니다. **UserDeviceAssociation**에는 조직의 사용자 장치 연결이 포함되어 있습니다. 이제 사용자와 장치 엔터티 컬렉션을 연결하는 사용자 장치 연결 정보를 사용하여 보고서 및 데이터 시각화를 작성할 수 있습니다.  
 - 엔터티 [**IntuneManagementExtension**](reports-ref-intunemanagementextension.md)이 추가되었습니다. **IntuneManagementExtension**은 버전 및 설치 상태와 같은 정보를 추적하는 모바일 장치에 대한 엔터티를 포함합니다.

## <a name="next-steps"></a>다음 단계
 - [매주 Intune에 추가되는 새로운 기능](whats-new.md)에 대해 알아봅니다. 예정된 변경, 서비스 관련 중요 공지 및 이전 릴리스 관련 정보에 대해서도 알아볼 수 있습니다.
 - [Microsoft Intune 블로그](http://go.microsoft.com/fwlink/?LinkID=273882)를 읽어 보세요.
