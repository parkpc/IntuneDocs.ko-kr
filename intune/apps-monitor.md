---
title: "앱 정보 및 할당을 모니터링하는 방법"
titlesuffix: Azure portal
description: "사용자 또는 장치에 앱을 할당한 후 이 정보를 사용하여 해당 상태를 모니터링할 수 있습니다."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 11/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 64e5133d-1e23-4ee6-b556-f5d32c0e95da
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0298fc255b3c11a12b5bf225968d6f2303192053
ms.sourcegitcommit: 520eb7712625e129b781e2f2b9fe16f9b9f3d08a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-monitor-app-information-and-assignments-with-microsoft-intune"></a>Microsoft Intune으로 앱 정보 및 할당을 모니터링 하는 방법

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune에서는 관리하는 앱 속성 및 해당 할당 상태를 모니터링할 수 있는 다양한 방법을 제공합니다.

1. Azure Portal에 로그인합니다.
2. **추가 서비스** > **모니터링 + 관리** + **Intune**을 선택합니다.
3. **모바일 앱** 워크로드에서 **관리** 그룹의 **앱**을 선택합니다.
5. 앱 블레이드 목록에서 앱을 선택합니다. <*앱 이름*> **장치 설치 상태** 블레이드가 표시됩니다.

## <a name="app-overview-blade"></a>앱 개요 블레이드

<*앱 이름*> **장치 설치 상태** 블레이드를 사용하여 환경 내 앱의 상태에 대한 세부 정보를 검토할 수 있습니다.

### <a name="essentials"></a>Essentials

**필수** 섹션은 앱에 대한 다음 정보를 포함합니다.

 - **게시자**  
앱의 게시자
 - **운영 체제**  
앱의 운영 체제(Windows, iOS, Android 등)
 - **만들기**  
해당 수정 버전을 만든 시간
 - **할당됨**  
앱이 할당되었는지에 대한 **예** 또는 **아니요**.

### <a name="status"></a>상태
각 그래프는 다음 상태에 대한 수를 보여줍니다.

 - **설치됨**  
설치된 앱의 수입니다.
 - **설치 안 됨**  
설치되지 않은 앱의 수입니다.
 - **설치 보류 중**  
설치 과정에 있는 앱의 수입니다.
 - **실패**  
실패한 설치의 수입니다.
 - **알 수 없음**  
상태를 알 수 없는 앱의 수입니다.

### <a name="device-status"></a>장치 상태

장치 상태입니다. 장치에 앱의 설치 상태를 표시하는 도넛형 차트입니다. 그래프를 클릭하여 장치 상태에 대한 세부 정보 목록을 엽니다. 세부 정보 테이블에는 다음 열이 포함되어 있습니다.

 - **장치 이름**  
장치 이름 지정을 허용하는 플랫폼에서 장치의 이름입니다. 다른 플랫폼에서 Intune은 다른 속성으로부터 이름을 만듭니다. 이 특성은 모든 장치에 대해 사용할 수 없습니다.
 - **사용자 이름**  
사용자의 이름입니다.
 - **플랫폼**  
장치의 운영 체제(Windows, iOS, Android 등)
 - **버전**  
앱의 버전 번호입니다. LOB(기간 업무) 앱의 경우 앱의 전체 버전 번호가 표시됩니다. 전체 버전 번호는 앱의 특정 릴리스를 식별합니다. 번호는 _버전_(_빌드_)으로 표시됩니다. 예: 2.2(2.2.17560800)
 - **상태**  
앱의 상태입니다.
 - **상태 정보**  
상태의 세부 정보입니다.
 - **마지막 체크 인**  
장치가 Intune과 마지막으로 동기화된 날짜입니다.


### <a name="user-status"></a>사용자 상태

사용자 상태입니다. 사용자에 대한 앱의 설치 상태를 표시하는 도넛형 차트입니다. 그래프를 클릭하여 장치 상태에 대한 세부 정보 목록을 엽니다. 세부 정보 테이블에는 다음 열이 포함되어 있습니다.
 - **Name**  
Azure AD의 사용자 이름입니다.
 - **사용자 이름**  
사용자의 고유한 이름입니다.
 - **설치**  
사용자가 사용한 앱 설치 수입니다.
 - **실패**  
사용자가 설치에 실패한 수입니다.
 - **설치 안 됨**  
사용자가 설치하지 않은 앱의 수입니다.


## <a name="next-steps"></a>다음 단계

Intune 데이터 작업에 대해 자세히 알아보려면 [Intune 데이터 웨어하우스 사용](reports-nav-create-intune-reports.md)을 참조하세요.