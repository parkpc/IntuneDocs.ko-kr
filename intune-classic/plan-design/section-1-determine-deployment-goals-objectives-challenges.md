---
title: "Intune 배포 목적, 목표 및 과제 확인 | Microsoft 문서"
description: "이 문서의 정보를 활용하여 Microsoft Intune 클라우드 전용 구현을 위한 배포 목적, 목표 및 과제를 확인할 수 있습니다."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 24cf9d97-db39-4b95-a664-4aa2e33edb87
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: d10906ee3fb69458738b31bb1d4252d632a9a0cf
ms.openlocfilehash: 6014527422ea3dae4d1333965ccd9e48e8216afb
ms.lasthandoff: 04/08/2017


---

# <a name="determine-intune-deployment-goals-objectives-and-challenges"></a>Intune 배포 목적, 목표 및 과제 확인

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

적절한 배포 계획을 갖춘 경우 먼저 조직의 배포 목적 및 목표와 함께 잠재적인 과제를 파악합니다. 각 조직은 고유하며, 각 조직에는 자체의 배포 목적, 목표 및 과제가 있습니다. 각 영역을 더 자세하게 살펴보겠습니다.

## <a name="deployment-goals"></a>배포 목적

배포 목적은 조직에서 Microsoft Intune을 구현함으로써 달성하려는 장기적 성과입니다. 조직의 Intune 배포 목적과 함께 각각에 대한 설명 및 비즈니스 가치의 몇 가지 예가 아래에 나열되어 있습니다.

-   **Office 365와의 통합 및 Office 모바일 앱의 사용 지원**

    -   **설명:** Office 365와의 긴밀한 통합을 제공하고, 응용 프로그램 보호 기능이 포함된 Office 모바일 응용 프로그램의 사용을 지원합니다.

    -   **비즈니스 가치:** 사용자가 익숙하고 선호하는 앱을 사용할 수 있게 하여 안전하고 향상된 사용자 환경을 구현합니다.

-   **모바일 장치에서 회사 내부 서비스에 대한 액세스 지원**

    -   **설명:** 직원이 근무하는 위치와 사용 중인 장치에 관계없이 생산성을 발휘하도록 하는 것이 조직의 전략적 방향입니다. 이 프로젝트는 모바일 생산성을 실현하고 안전하게 회사 데이터에 액세스하는 방법을 고려해야 합니다.

    -   **비즈니스 가치:** 직원이 필요한 곳에서 민첩하게 작업할 수 있으며, 기업은 경쟁력을 유지하고 더욱 생산적인 업무 환경을 제공할 수 있습니다.

-   **모바일 장치에서 데이터 보호 제공**

    -   **설명:** 데이터가 모바일 장치에 저장된 경우 악의적 행위나 실수로 데이터가 손실 또는 공유되지 않도록 보호해야 합니다.

    -   **비즈니스 가치:** 데이터 보호는 경쟁력을 유지하고 극도로 성실하게 고객을 대하고 데이터를 처리하는 데 매우 중요합니다.

-   **비용 절감**

    -   **설명:** 가능한 경우 프로젝트에서 배포 및 운영 비용을 절감합니다.

    -    **비즈니스 가치:** 기업이 리소스의 효율적인 사용으로 다른 영역에 투자할 수 있도록 하며 더 효과적으로 경쟁하고 고객에게 더 나은 서비스를 제공할 수 있습니다.

## <a name="deployment-objectives"></a>배포 목표

배포 목표는 조직이 Microsoft Intune 배포 목적에 도달하기 위해 취할 수 있는 조치입니다. 조직의 배포 목표와 각 목표를 달성하는 방식의 몇 가지 예가 아래에 나열되어 있습니다.

-   **장치 관리 솔루션의 수 축소**
<br>
    -   **실행:** 앱 및 장치의 회사 데이터 보호를 위해 하나의 모바일 장치 관리 솔루션인 Microsoft Intune으로 통합합니다.
<br></br>
-   **Exchange Online 및 SharePoint Online에 대한 보안 액세스 제공**
<br>
    -   **실행:** Exchange Online 및 SharePoint Online에 대해 Microsoft Intune 조건부 액세스를 구현합니다.
<br></br>
-   **모바일 장치에서 회사 데이터가 회사 외부 서비스에 저장되거나 전달되지 않도록 방지**
<br>
    -   **실행:** Microsoft Office 및 LOB 앱에 대해 Microsoft Intune 앱 보호 정책을 구현합니다.
<br></br>
-   **장치에서 회사 데이터를 초기화하는 기능 제공**
<br>
    -   **실행:** Microsoft Intune으로 장치를 등록 및 관리하고, 해당하는 경우 회사 데이터 및 리소스에 대해 원격 초기화를 수행하는 기능을 제공합니다.

## <a name="deployment-challenges"></a>배포 과제

배포 과제는 조직의 최우선 고려사항이 되는 문제로, 배포에 부정적인 영향을 줄 수 있습니다. 때로 배포 과제는 이전 프로젝트에서 경험했으며 방지하고 싶은 과거의 문제 또는 현재 배포 작업과 관련된 새로운 문제와 관계가 있을 수 있습니다. 조직의 Microsoft Intune 배포 과제와 함께 잠재적인 완화의 몇 가지 예가 아래에 나와 있습니다.

-   지원 준비 및 최종 사용자 환경이 초기 프로젝트 범위에 포함되지 않습니다.  이로 인해 부적절한 최종 사용자 채택이 초래되고 솔루션을 지원하는 과제가 제기됩니다.
<br>
    -   **완화:** 배포 계획에 지원 교육 및 성공 메트릭을 사용한 최종 사용자 환경의 유효성 검사를 포함합니다.
<br></br>
-   명확하게 정의된 목적 및 성공 메트릭이 부족하여 문제가 발생한 후 반응 모드와 파악할 수 없는 결과가 발생합니다.
<br>
    -   **완화:** 프로젝트 범위에서 목적 및 성공 메트릭을 초기에 정의하고 이러한 데이터 요소를 사용하여 다른 출시 단계를 구체화합니다. 목표가 SMART(Specific(구체적), Measurable(측정 가능), Attainable(도달 가능), Realistic(현실적), Timely(시기 적절))한지 확인하고 각 단계에서 목표에 대해 측정하고 출시 프로젝트의 진행 상태를 확인하도록 계획합니다.
<br></br>
-   조직이 적절히 받아들일 수 있는 명확한 가치 제안을 만들고 유효성을 검사하며 적극적으로 공유하는 것을 무시할 경우 보통 제한된 채택 및 ROI(투자 수익률) 부족으로 이어집니다.
<br>
    -   **완화:** 프로젝트를 시작할 동기 부여를 위해서는 명확하게 정의된 목적 및 목표가 있어야 합니다. 모든 인식 및 교육 활동에 이러한 목적 및 목표를 포함하면 사용자가 조직에서 Intune을 선택한 이유를 이해할 수 있습니다.

## <a name="next-steps"></a>다음 단계

배포 목적, 목표 및 잠재적인 과제를 확인했으므로 이제, 다음 섹션: [사용 사례 시나리오 확인](section-2-identify-use-case-scenarios.md)을 살펴보겠습니다.

