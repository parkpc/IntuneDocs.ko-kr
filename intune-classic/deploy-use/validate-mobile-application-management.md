---
title: "MAM 설정 유효성 검사"
description: "이 항목에서는 MAM 정책이 올바르게 설정되어 있으며 정상적으로 작동하는지를 테스트하고 유효성을 검사하는 방법을 설명합니다."
keywords: 
author: andredm7
ms.author: andredm
manager: angerobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 41d82597-e13e-4c3e-9151-e71392236ca0
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: joglocke
ms.custom: intune-classic
ms.openlocfilehash: e0cb44177f830236865dce0ab68bb1084fcebc2d
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/10/2017
---
# <a name="validating-your-mobile-application-management-setup"></a>모바일 응용 프로그램 관리 설정 유효성 검사

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

이 항목에서는 MAM(모바일 응용 프로그램 관리)을 설정한 후에 문제를 확인하는 방법에 대한 정보를 제공합니다. 이 지침은 Azure Portal의 MAM 정책에 적용됩니다.

### <a name="checking-for-symptoms"></a>증상 확인
MAM은 데이터 보호 도구이므로 사용자가 문제를 보고할 가능성은 거의 없습니다. MAM 구성에 문제가 있더라도 MAM을 사용하지 않을 때와 마찬가지로, 제한 없이 MAM 기능에 액세스할 수 있으므로 사용자는 문제가 있음을 알 수 없습니다. 따라서 MAM 제한을 의도적으로 테스트할 수 있는 소규모 사용자 그룹에 대해 MAM 정책을 파일럿 적용해 MAM 구성의 유효성을 검사하는 것이 좋습니다.


### <a name="what-to-check"></a>확인할 사항

테스트 결과 MAM 정책 동작이 예상과 다른 경우에는 다음 사항을 확인하는 것이 좋습니다.

- 사용자에게 MAM 사용이 허가되었는지 여부
- 사용자에게 O365 사용이 허가되었는지 여부
- 각 사용자의 MAM 앱 상태. 앱의 가능한 상태는 **체크 인됨** 및 **체크 인되지 않음**입니다.

#### <a name="user-mam-status"></a>사용자 MAM 상태
1. Azure Portal에서 **Intune 모바일 응용 프로그램 관리** > **설정** > **앱 관리** > **모든 설정** > **사용자의 앱 보고** > **사용자**를 선택합니다.

2. 목록에서 사용자를 선택하거나 사용자를 검색하여 선택한 다음 **사용자 선택**을 선택합니다. **앱 보고** 열 맨 위에 사용자에게 MAM 사용이 허가되었는지 여부가 표시됩니다. 그 아래에는 사용자에게 O365 사용이 허가되었는지 여부와 해당 사용자의 모든 장치에 대한 앱 상태가 표시됩니다.

![MAM용 앱 상태](..\media\ts-mam-user-apps.png)

### <a name="what-to-do"></a>알아두어야 할 사항
사용자 상태에 따라 수행할 작업은 다음과 같습니다.

- 사용자에게 MAM 사용이 허가되지 않은 경우 [Intune 라이선스 관리](/intune/setup-steps)의 설명에 따라 사용자에게 Intune 라이선스를 할당합니다.
- 사용자에게 O365 사용이 허가되지 않은 경우 사용자용 라이선스를 받습니다.
- 사용자의 앱이 목록에서 **체크 인되지 않음**으로 표시되는 경우 해당 앱에 대해 MAM 정책을 올바르게 구성했는지 확인합니다.
- MAM 정책을 적용할 모든 사용자에게 이러한 조건이 적용되는지 확인합니다.

### <a name="see-also"></a>참고 항목
[Microsoft Intune을 사용하여 모바일 앱 관리 정책 구성 준비](..\deploy-use\get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)

[Microsoft Intune에서 모바일 앱 관리 정책을 사용하여 앱 데이터 보호](..\deploy-use\protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)
