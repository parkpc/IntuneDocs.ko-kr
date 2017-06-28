---
title: "Intune 테스트 및 유효성 검사"
description: "이 문서에는 사용자 환경에서 Intune 클라우드 전용 솔루션을 테스트하고 유효성 검사할 때 고려해야 하는 유용한 모든 세부 정보가 포함되어 있습니다."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4f82ee0c-4bd6-4623-9b10-9249d316ccf5
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: df3c42d8b52d1a01ddab82727e707639d5f77c16
ms.openlocfilehash: 4ea2974c4724564cd8f9972fdb238b06d1b100e6
ms.contentlocale: ko-kr
ms.lasthandoff: 06/08/2017


---

# <a name="intune-testing-and-validation"></a>Intune 테스트 및 유효성 검사

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

테스트 단계는 구현 단계 도중과 이후에 진행되어야 하며, 이전에 확인한 모든 필수 IT(관리자) 및 최종 사용자(사용 사례) 시나리오를 테스트하기 위한 테스트 계정, 그룹 및 장치가 있어야 합니다.

지원 설명서를 작성하도록 테스트 단계에 IT 지원/기술 지원팀 직원을 포함하는 것이 좋습니다. 그러면 IT 지원/기술 지원팀 직원의 제품 지원이 편리해집니다. 구성 요소 또는 시나리오가 사용 사례에 따라 작동하지 않을 경우 필요한 변경 내용을 문서화하고 변경을 수행한 이유를 포함해야 합니다.

## <a name="before-you-begin"></a>시작하기 전에

다음을 문서화하는 것이 좋습니다.

-   **테스트 기준:** 비교 측정할 벤치마크를 확인합니다.

-   **설계 구성 요소:** 하나 이상의 테스트 기준에 존재해야 합니다.

요구 사항 또는 시나리오에 맞는 설계 구성 요소가 하나 이상의 테스트 기준에 존재하지 않는 경우 설계 구성 요소가 필요한지 여부를 고려해야 합니다. 또한 다음 항목이 있는지 확인해야 합니다.

-   **계정:** 모든 사용 사례 시나리오를 테스트하려면 테스트에 사용되는 계정이 EMS 및 Office 365에 대한 라이선스가 있는 테스트 계정이어야 합니다.

-   **장치:** 이 시점에 사용되는 장치는 공장 기본값으로 재설정하거나 잠재적으로 초기화할 수 있는 테스트 장치여야 합니다.

-   **통합 구성 요소:** 필요한 경우 모든 통합 구성 요소(Certificate Connector, Hosted Exchange용 Intune Service To Service Connector 및 Intune On-Premises Exchange Connector)를 설치하고 구성해야 합니다.

예측하지 못한 문제를 해결하기 위해 설계를 변경해야 할 수 있습니다. 또한 모든 설계 변경 내용은 각 변경에 대한 이유와 함께 완벽하게 문서화해야 합니다. 다음은 어떤 변경이 일어날 수 있는지를 보여 주는 예입니다.

-   NDES(네트워크 장치 등록 서비스)의 요구 사항을 충족하지 못한다는 사실을 알게 될 수 있습니다. 그리고 NDES 구현 없이 동일한 요구 사항을 충족하는 루트 CA를 사용하여 VPN 및 Wi-Fi 프로필을 구성할 수도 있다는 것도 알게 됩니다.

테스트 및 유효성 검사 프로세스 중 기술 지침 또는 특수한 문제 해결이 필요한 과제 또는 문제에 직면할 수 있습니다. 이 경우 Microsoft 지원 채널을 통해 지원을 요청하는 것이 좋습니다.

-   [Microsoft Intune에 대한 관리 지원을 받는 방법](/intune-classic/troubleshoot/how-to-get-support-for-microsoft-intune)

-   [Microsoft Intune에 대한 일반적인 문제 해결 팁](/intune-classic/troubleshoot/general-troubleshooting-tips-for-microsoft-intune).

-   [Microsoft Intune에 대한 관리 지원을 받는 방법](/intune-classic/troubleshoot/how-to-get-support-for-microsoft-intune)

-   [Microsoft Intune의 담당자 전화 지원](/intune-classic/troubleshoot/contact-assisted-phone-support-for-microsoft-intune)

## <a name="functional-validation-testing"></a>기능 유효성 검사 테스트

기능 유효성 검사는 각 구성 요소 및 구성이 올바르게 작동하는지 확인하는 테스트로 구성됩니다. 유효성 검사 테스트의 예는 아래 표에 나와 있습니다.

![섹션 9 표 1](./media/section-9-image-1-table.PNG)

## <a name="use-case-validation-testing"></a>사용 사례 유효성 검사 테스트

시나리오가 완전하며 작동하는지 확인하려면 사용 사례 유효성 검사 테스트를 수행해야 합니다. 두 가지 유형 즉, IT 관리자 및 최종 사용자의 사용 사례 시나리오가 있습니다.

### <a name="it-admin"></a>IT 관리자

장치에서 수행되거나 사용자가 수행한 관리 작업이 올바르게 작동하는지 확인하려면 IT 관리자 유효성 검사 테스트를 수행해야 합니다. 다음은 IT 관리자 종단 간 유효성 검사 시나리오의 예입니다.

![섹션 9 표 2](./media/section-9-image-2-table.PNG)

### <a name="end-user"></a>최종 사용자

최종 사용자 환경이 예상대로 작동하며 모든 사용자 통신에 제대로 표시되는지 확인하려면 최종 사용자 유효성 검사 테스트를 수행해야 합니다. 유효성 검사에 실패하면 채택률이 낮아지고 기술 지원팀의 통화량이 높아질 수 있으므로 최종 사용자 환경이 올바른지 확인하는 것이 중요합니다.

![섹션 9 표 3](./media/section-9-image-3-table.PNG)

## <a name="next-steps"></a>다음 단계

Intune 기능 및 사용자 사례 시나리오를 테스트하고 그 유효성을 검사했으므로 이제 Intune 프로덕션 출시에 대한 준비가 되었습니다. 자세한 내용은 [추가 리소스](planning-guide-resources.md)를 참조하세요.

