---
title: "모바일 장치 관리 기관 설정"
titleSuffix: Intune on Azure
description: "Intune에서 모바일 장치 관리 기관을 설정하는 방법을 알아봅니다. \""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 05/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8deff871-5dff-4767-9484-647428998d82
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 449c45e0edcc0d0a33352ba154ad68fa6c4725c0
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2017
---
# <a name="set-the-mobile-device-management-authority"></a>모바일 장치 관리 기관 설정

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

MDM(모바일 장치 관리) 기관 설정에 따라 장치를 관리하는 방법이 결정됩니다. IT 관리자가 MDM 기관을 설정해야 사용자가 관리를 위해 장치를 등록할 수 있습니다.

가능한 구성은 다음과 같습니다.

- **Intune 독립 실행형** - Azure Portal을 사용하여 구성하는 클라우드 전용 관리입니다. Intune에서 제공하는 모든 기능 집합을 포함합니다. [Intune 콘솔에서 MDM 기관을 설정합니다](#mdm-authority-set-to-intune).

- **Intune 하이브리드** - Intune 클라우드 솔루션과 System Center Configuration Manager의 통합입니다. Configuration Manager 콘솔을 사용하여 Intune을 구성합니다. [Configuration Manager에서 MDM 기관을 설정합니다](https://docs.microsoft.com/sccm/mdm/deploy-use/configure-intune-subscription).

- **Office 365용 모바일 장치 관리**  - Office 365와 Intune 클라우드 솔루션의 통합입니다. Office 365 관리 센터에서 Intune을 구성합니다. Intune 독립 실행형에서 제공되는 기능 중 일부를 포함합니다. Office 365 관리 센터에서 MDM 기관을 설정합니다.

>[!IMPORTANT]    
Configuration Manager 버전 1610 이상과 Microsoft Intune 버전 1705에서는 Microsoft 지원에 문의하여 기존의 관리 장치를 등록 취소했다가 다시 등록할 필요 없이 MDM 기관을 변경할 수 있습니다. 자세한 내용은 [잘못된 MDM 기관 설정을 선택한 경우 수행할 작업](/intune-classic/deploy-use/prerequisites-for-enrollment#what-to-do-if-you-choose-the-wrong-mdm-authority-setting)을 참조하세요.

## <a name="set-mdm-authority-to-intune"></a>MDM 기관을 Intune으로 설정

1. Azure Portal에서 **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
  ![사용자 선택 링크가 포함된 Intune 문제 해결 작업 스크린샷](media/set-mdm-auth.png)
2. Intune 블레이드에서 **장치 등록**을 선택한 다음 **개요**를 선택합니다.

3. **장치 관리 시작** 블레이드에서 **MDM 기관을 Intune으로 설정**을 선택합니다. MDM 기관을 Intune으로 설정했음을 나타내는 메시지가 표시됩니다.

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>MDM 인증서 만료 후 모바일 장치 정리

MDM 인증서는 모바일 장치가 Intune 서비스와 통신할 때 자동으로 갱신됩니다. 모바일 장치가 초기화되거나 일정 기간에 Intune 서비스와 통신하지 못한 경우에는 MDM 인증서가 갱신되지 않습니다. MDM 인증서가 만료되고 180일 후 Azure Portal에서 장치가 제거됩니다.
