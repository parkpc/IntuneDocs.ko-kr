---
title: "Microsoft Intune-Azure에서 장치 보기 | Micrososft Docs"
description: "운영 체제, 저장 공간, 제조업체 및 모델을 비롯한 장치 세부 정보를 봅니다. Azure에서 Microsoft Intune을 사용하여 설치된 앱의 목록을 가져오고, 준수 정책을 확인하고, TeamViewer를 설정합니다. 관리하는 장치의 인벤토리 보기와 유사합니다."
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e71c6bdb-d75c-404f-8e38-24a663be81c2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 934ba0853f8bee851f7027580c276a9fff911b7f
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/08/2018
---
# <a name="see-device-details-in-intune"></a>Intune에서 장치 세부 정보 참조

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

**장치** 기능은 하드웨어 및 설치된 앱을 비롯하여 관리하는 장치에 추가 세부 정보를 제공합니다. 

이 문서는 Azure Portal에서 모든 장치 및 해당 속성을 보는 방법을 보여줍니다.

## <a name="view-your-device-details"></a>장치 세부 정보 보기

1. 로그인은 [Azure 포털](https://portal.azure.com)합니다.
2. **모든 서비스**를 선택하고 **Intune**에서 필터링하고 **Microsoft Intune**을 선택합니다.
3. **장치**를 선택합니다. 장치 내에서 다음과 같은 여러 가지 옵션을 사용할 수 있습니다.

  - **개요** - 등록한 장치 및 각 장치에서 실행하는 운영 체제에 대한 정보를 가져옵니다.
  - **관리** - 관리하는 모든 장치 목록을 보려면 **모든 장치** 또는 **Azure AD 장치**를 선택합니다.
    목록에서 장치 중 하나를 선택합니다. 이 단계에서는 <*장치 이름*> **개요**를 엽니다. 여기서 다음을 선택할 수 있습니다.
    - **개요** - 체크 인할 때 장치 이름, 소유자(BYOD(Bring-Your-Own-Device)인 경우) 및 자세한 정보를 표시합니다.
    - **하드웨어** -저장소 공간, 모델과 제조업체 등 장치에 대한 자세한 정보를 표시합니다.
    - **검색된 앱** - Intune이 장치에 설치한 모든 앱을 표시합니다.
    - **장치 준수** - 장치에 할당된 모든 준수 정책의 상태를 표시합니다.
    - **장치 구성** - 장치에 할당된 모든 장치 구성 정책의 준수 상태를 표시합니다.
- **모니터** - **장치 작업**을 선택하여 관리하는 장치에서 수행된 장치 작업 목록 및 현재 상태가 표시됩니다. **감사 로그**에서는 다양한 작업의 상태를 표시합니다.
- **설치 프로그램** > **TeamViewer 커넥터** - TeamViewer 소프트웨어를 사용하여 장치에서 원격 관리를 구성합니다. 자세한 내용은 [Intune 관리 Android 장치에 대해 원격 지원 제공](device-profile-android-teamviewer.md)을 참조하세요.

Intune은 회사 소유 장치에서만 앱 목록을 수집합니다. 앱이 개인 장치에서 확인되지 않습니다. Windows 10 PC의 경우 최신 앱만이 회사 소유 장치에서 나열됩니다. Intune은 장치에서 Win32 앱에 대한 정보는 수집하지 않습니다. 장치별 이동 통신 사업자에 따라 일부 앱을 수집하지 않을 수 있습니다.

## <a name="next-steps"></a>다음 단계
Intune을 사용하여 [장치를 관리](device-management.md)하기 위해 수행할 수 있는 작업을 참조하세요.
