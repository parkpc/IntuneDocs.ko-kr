---
title: "장치 등록 - 장치 등록 관리자 | Intune Azure 미리 보기 | Microsoft Docs"
description: "Intune Azure 미리 보기: 장치 등록 관리자 계정을 사용하여 Intune에서 장치를 등록합니다. "
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7196b33e-d303-4415-ad0b-2ecdb14230fd
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 08dad848a48adad7d9c6f0b5b3286f6550a266bd
ms.openlocfilehash: 78eca605a277c1e0fc750900ece028d8f2c7c5b2
ms.lasthandoff: 02/15/2017

---

# <a name="enroll-devices-using-device-enrollment-manager"></a>장치 등록 관리자를 사용하여 장치 등록

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

조직에서는 Intune을 사용하여 단일 사용자 계정으로 많은 수의 모바일 장치를 관리할 수 있습니다. *DEM(장치 등록 관리자)* 계정은 1000개까지 장치를 등록할 수 있는 특수한 사용자 계정입니다. 특수 DEM 기능을 부여할 DEM 계정에 기존 사용자를 추가합니다. 등록된 각 장치는 단일 라이선스를 사용합니다. 이 계정을 통해 등록한 장치는 개인("BYOD") 장치가 아닌 공유 장치로 사용하는 것이 좋습니다.  

장치 등록 관리자로 추가하려면 Azure 포털에 사용자가 존재해야 합니다. 보안 최적화를 위해 DEM 사용자는 Intune 관리자여서도 안 됩니다.

>[!NOTE]
>DEM 등록 방법은 [Apple Configurator에서 설정 도우미 사용](enroll-ios-devices-with-apple-configurator-and-setup-assistant.md), [Apple Configurator에서 직접 등록](enroll-ios-devices-with-apple-configurator-and-direct-enrollment.md), [장치 등록 프로그램](enroll-ios-devices-using-device-enrollment-program.md) 등의 다른 등록 방법과 함께 사용할 수 없습니다. 

## <a name="example-of-a-device-enrollment-manager-scenario"></a>장치 등록 관리자 시나리오의 예

식당에는 서빙 직원을 위한 50대의 POS 태블릿과 주방 직원을 위한 주문 모니터를 공급하기를 원합니다. 직원은 회사 데이터에 액세스하거나 사용자로 로그인할 필요가 없습니다. Intune 관리자는 장치 등록 관리자 계정을 만들고 DEM 계정에 식당 감독자를 추가하여 해당 감독자에게 DEM 기능을 제공합니다. 이제 감독자는 DEM 자격 증명을 사용하여 50대의 태블릿 장치를 등록할 수 있습니다.

Intune 콘솔의 사용자만 장치 등록 관리자가 될 수 있습니다. 장치 등록 관리자 사용자는 Intune 관리자일 수 없습니다.

DEM 사용자는 다음 작업을 수행할 수 있습니다.

-   Intune에서 최대 1000개의 장치 등록
-   회사 포털에 로그인하여 회사 앱 가져오기
-   태블릿에 역할별 앱을 배포하여 회사 데이터에 대한 액세스 구성

## <a name="limitations-of-devices-that-are-enrolled-with-a-dem-account"></a>DEM 계정을 사용하여 등록된 장치의 제한 사항

장치 등록 관리자 계정을 사용하여 등록한 장치에는 다음과 같은 제한 사항이 적용됩니다.

  - 특정 장치 "사용자"가 없습니다. 따라서 메일 또는 회사 데이터 액세스 권한이 없습니다. 그러나 예를 들어 데이터에 대한 액세스 권한이 있는 장치 앱을 제공하는 데 VPN이 계속 사용될 수 있습니다.

  - 이러한 시나리오는 사용자 기준 시나리오이므로 조건부 액세스가 없습니다.

  - DEM 사용자는 회사 포털을 사용하여 장치 자체에서 DEM에 등록된 장치 등록을 해제할 수 없습니다. Intune 관리자에게는 이 기능이 있으나 DEM 사용자에게는 없습니다.

  - 회사 포털 앱 또는 웹 사이트에 로컬 장치만 표시됩니다.
 
  - 앱 관리에 대한 사용자별 Apple ID 요구 사항으로 인해 Apple VPP(Volume Purchase Program) 앱을 사용할 수 없습니다.
 
  - (iOS에만 해당)DEM을 사용하여 iOS 장치를 등록하는 경우 Apple Configurator 또는 Apple DEP(장치 등록 프로그램)를 사용하여 장치를 등록할 수 없습니다.


> [!NOTE]
> 장치 등록 관리자로 관리되는 장치에 회사 앱을 배포하려면 회사 포털 앱을 장치 등록 관리자의 사용자 계정에 **필수 설치**로 배포합니다.
> 성능 향상을 위해 DEM 장치에서 회사 포털 앱을 보면 로컬 장치만 표시됩니다. 다른 DEM 장치의 원격 관리는 Intune 관리 콘솔에서만 수행할 수 있습니다.


## <a name="add-a-device-enrollment-manager"></a>장치 등록 관리자 추가

1.  Azure Portal에서 **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.

2.  Intune 블레이드에서 **장치 등록**을 선택한 다음 **장치 등록 관리자**를 선택합니다.

3.  **추가**를 선택합니다.

4.  **사용자 추가** 블레이드에서 DEM 사용자의 사용자 계정 이름을 입력하고 **추가**를 선택합니다. DEM 사용자가 DEM 사용자 목록에 추가됩니다.

## <a name="remove-a-device-enrollment-manager"></a>장치 등록 관리자 제거

장치 등록 관리자를 제거해도 등록된 장치에는 영향을 주지 않습니다. 장치 등록 관리자를 제거하는 경우:

-   DEM 사용자 목록에서 사용자를 제거해도 등록된 장치에는 영향을 주지 않으며 등록된 장치는 계속 완벽하게 관리됩니다.

-   제거된 장치 등록 관리자 계정 자격 증명은 계속 유효합니다.

-   제거된 장치 등록 관리자는 여전히 장치를 초기화하거나 사용 중지할 수 없습니다.

-   제거된 장치 등록 관리자는 Intune 관리자가 구성한 장치별 한도에 도달하지 않는 한 추가 장치를 등록할 수 없습니다.

**장치 등록 관리자를 제거하려면**

1. Azure Portal에서 **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.

2. Intune 블레이드에서 **장치 등록**을 선택한 다음 **장치 등록 관리자**를 선택합니다.

3. **장치 등록 관리자** 블레이드에서 DEM 사용자를 마우스 오른쪽 단추로 클릭하고 **제거**를 선택합니다.

## <a name="view-the-properties-of-a-device-enrollment-manager"></a>장치 등록 관리자의 속성 보기

1. Azure Portal에서 **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.

2. Intune 블레이드에서 **장치 등록**을 선택한 다음 **장치 등록 관리자**를 선택합니다.

3. **장치 등록 관리자** 블레이드에서 DEM 사용자를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.

