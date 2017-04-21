---
title: "Intune 마이그레이션 중 앱 보호 정책 구성 | Microsoft 문서"
description: "이 문서의 목적은 Intune 마이그레이션 중 앱 보호 정책을 설정하는 데 필요한 단계를 제공하는 것입니다."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 93cda587-bf56-4d41-b123-9fe203fad788
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab6d9b6b296fb4e1fb0aaa9496fede28976728dc
ms.openlocfilehash: f30ab8799b2e049372139c7f9ee7213547736bb0
ms.lasthandoff: 04/14/2017


---

# <a name="phase-1-configure-app-protection-policies-optional"></a>1단계: 앱 보호 정책 구성(선택 사항)

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

앱 보호 정책을 통해 앱을 암호화하고, 앱에 액세스할 때 PIN을 정의하고, 탈옥 또는 루팅 상태의 장치에서 앱이 실행되는 것을 차단하고, 기타 여러 보호 기능을 사용할 수 있습니다. 사용자의 휴대폰을 잃어버리거나 도난당한 경우 모바일 앱 보호 정책을 적용하여 개인 데이터는 그대로 유지하면서 선택적으로 회사 데이터를 원격으로 초기화할 수 있습니다.

앱 보호 정책은 앱 수준에서 보안을 적용하며 장치 등록이 필요하지 않습니다. 이 정책은 Intune에 등록된 장치와 등록되지 않은 장치에서 모두 사용할 수 있습니다. 또한 타사 MDM 공급자에 등록된 장치에서도 사용할 수 있습니다.

## <a name="app-protection-policies-with-lob-apps"></a>LOB 앱의 앱 보호 정책

또한 [Microsoft Intune 앱 SDK](https://docs.microsoft.com/intune/deploy-use/use-the-sdk-to-enable-apps-for-mobile-application-management) 또는 [IOS](https://www.microsoft.com/download/details.aspx?id=45218&751be11f-ede8-5a0c-058c-2ee190a24fa6=True) 및 [Android](https://www.microsoft.com/download/details.aspx?id=47267) 플랫폼용 Microsoft Intune 앱 래핑 도구를 활용하여 LOB(기간 업무) 앱으로 모바일 앱 보호 정책을 확장할 수도 있습니다.

## <a name="how-do-app-protection-policies-help-during-migration"></a>앱 보호 정책이 마이그레이션하는 동안 어떻게 도움이 되나요?

마이그레이션하려면 장치를 이전 MDM 공급자에서 제거하여 Intune에 등록해야 합니다. 이런 과정을 계획하고, 최종 사용자가 이전 MDM 공급자에서 등록 취소하는 즉시 Intune에 등록하도록 권장해야 합니다. 그러나 마이그레이션하는 동안 등록 프로세스 완료를 미루는 사용자가 있을 수 있으며, 이런 경우 해당 장치가 MDM 공급자 중 하나에서 관리되지 않습니다.

이 기간에 회사 리소스 액세스가 계속 허용되는 경우 조직이 장치 도난 및 회사 데이터 손실에 더 취약해질 수 있으며 회사 리소스 액세스가 차단된 경우 사용자 생산성이 떨어질 수 있습니다.

Intune에서는 장치 수준 관리 방법이 없는 경우 회사 데이터 보안 기능을 계속 사용할 수 있도록 마이그레이션하는 동안에도 회사 데이터 보호 기능을 제공할 수 있습니다.

이전 MDM 공급자에서 조건부 액세스를 비활성화하므로, Intune에 등록하는 동안에도 사용자는 계속 생산성을 유지할 수 있습니다.

## <a name="task-list-for-app-protection-policies"></a>앱 보호 정책에 대한 작업 목록

-   작업 1: [모바일 앱 보호를 구성하는 방법](https://docs.microsoft.com/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune)에 대해 알아봅니다.

-   작업 2: [모바일 앱 보호 정책을 만들어 배포하는 방법](https://docs.microsoft.com/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune)에 대해 알아봅니다.

## <a name="next-steps"></a>다음 단계 

[1단계: 특별한 마이그레이션 고려 사항](https://docs.microsoft.com/intune/plan-design/migration-phase1-special-migration-considerations)

