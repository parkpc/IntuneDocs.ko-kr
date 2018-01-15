---
title: "장치 등록 관리자를 사용하여 등록"
description: "DEM(장치 등록 관리자) 계정이라는 단일 사용자 계정으로 많은 수의 공유되는 회사 소유의 모바일 장치를 관리할 수 있습니다."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 01/03/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a23abc61-69ed-44f1-9b71-b86aefc6ba03
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b55c5d588eb366487a9e1594a46f88551e0b6ee2
ms.sourcegitcommit: 5fd17a57989c6da3d325ed2e0018ce16fe20bb79
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/04/2018
---
# <a name="enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune"></a>Microsoft Intune에서 장치 등록 관리자를 사용하여 회사 소유 장치 등록

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

조직에서는 Intune을 사용하여 단일 사용자 계정으로 많은 수의 모바일 장치를 관리할 수 있습니다. *DEM(장치 등록 관리자)* 계정은 1000개까지 장치를 등록할 수 있는 특수한 사용자 계정입니다. 기존 사용자를 DEM 계정에 추가하여 특수 DEM 기능을 제공합니다. 등록된 각 장치는 단일 라이선스를 사용합니다. 이 계정을 통해 등록한 장치는 개인("BYOD") 장치가 아닌, 사용자 선호도가 없는 공유 장치로 사용하는 것이 좋습니다.  

장치 등록 관리자로 추가하려면 Azure 포털에 사용자가 존재해야 합니다. 보안 최적화를 위해 DEM 사용자는 Intune 관리자여서도 안 됩니다.

>[!NOTE]
>DEM 등록 방법을 [Apple Configurator 설정 도우미](ios-setup-assistant-enrollment-in-microsoft-intune.md), [직접 등록](ios-direct-enrollment-in-microsoft-intune.md), macOS 등록 및 [DEP 등록 방법](ios-device-enrollment-program-in-microsoft-intune.md)과 함께 사용할 수 없습니다.

## <a name="example-of-a-device-enrollment-manager-scenario"></a>장치 등록 관리자 시나리오의 예

식당에는 서빙 직원을 위한 50대의 POS 태블릿과 주방 직원을 위한 주문 모니터를 공급하기를 원합니다. 직원은 회사 데이터에 액세스하거나 사용자로 로그인할 필요가 없습니다. Intune 관리자는 장치 등록 관리자 계정을 만들고 DEM 계정에 식당 감독자를 추가하여 해당 감독자에게 DEM 기능을 제공합니다. 이제 감독자는 DEM 자격 증명을 사용하여 50대의 태블릿 장치를 등록할 수 있습니다.

Intune 콘솔의 사용자만 장치 등록 관리자가 될 수 있습니다. 장치 등록 관리자 사용자는 Intune 관리자일 수 없습니다.

DEM 사용자는 다음 작업을 수행할 수 있습니다.

-   Intune에서 최대 1,000개의 장치 등록
-   회사 포털 앱을 사용하여 회사 앱 가져오기
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

1.  DEM 계정에 추가할 사용자가 이미 있는지 확인하세요. 사용자를 추가해야하는 경우 [Office 365 포털](https://go.microsoft.com/fwlink/p/?LinkId=698854)에 로그인하여 [Office 365 포털에 사용자를 개별적으로 또는 일괄적으로 추가](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)의 단계를 따르세요.

2.  관리자 자격 증명을 사용하여 [Microsoft Intune 관리 콘솔](https://manage.microsoft.com)에 로그인합니다.

3.  탐색 창에서 **관리**를 선택하고 **관리자 관리**를 선택한 후 **장치 등록 관리자**를 선택합니다. **장치 등록 관리자** 페이지가 열립니다.

4.  **추가...**를 선택합니다. **장치 등록 관리자 추가** 대화 상자가 열립니다.

5.  Intune 계정의 **사용자 ID**를 입력하고 **확인**을 선택합니다.

    이제 DEM 사용자는 최종 사용자가 회사 포털에서 BYOD 시나리오에 이용하는 동일한 절차를 사용하여 모바일 장치를 등록할 수 있습니다. 관리자 최종 사용자는 회사 포털 앱을 설치하고 최대 1000대의 장치에 DEM 자격 증명을 사용하여 장치를 등록할 수 있습니다. 각 플랫폼에 대한 최종 사용자 등록 단계는 다음을 참조하세요.

  - [Intune에서 iOS 장치 등록](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios)
  - [Intune에서 macOS 장치 등록](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos)
  - [Intune에서 Android 장치 등록](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android)
  - [Intune에서 Windows 장치 등록](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows)

## <a name="delete-a-device-enrollment-manager-from-intune"></a>Intune에서 장치 등록 관리자 삭제

1.  관리자 자격 증명을 사용하여 [Microsoft Intune 관리 포털](https://manage.microsoft.com)에 로그온합니다.

2.  탐색 창에서 **관리**를 선택하고 **관리자 관리**를 선택한 후 **장치 등록 관리자**를 선택합니다. **장치 등록 관리자** 페이지가 열립니다.

3.  삭제하려는 장치 등록 관리자 **사용자**를 선택하고 **삭제**를 선택합니다. 이 사용자는 Intune에서 삭제되지 않으며, 이 사용자가 관리하는 장치는 Intune에서 등록된 상태를 유지합니다. 장치 등록 관리자를 삭제하면 해당 사용자가 추가 장치를 Intune에서 등록할 수 없게 됩니다.

4.  **예**를 선택하여 장치 등록 관리자를 삭제할 것임을 확인합니다.

장치 등록 관리자를 삭제해도 등록된 장치에는 영향을 주지 않습니다. 장치 등록 관리자를 삭제하는 경우:

-   등록된 장치는 영향을 받지 않습니다.

-   등록된 장치는 계속 완벽하게 관리됩니다.

-   삭제된 장치 등록 관리자 계정의 자격 증명은 계속 유효하여 회사 포털에 로그인해 앱에 액세스할 수 있습니다.

-   삭제된 장치 등록 관리자 계정 자격 증명으로는 여전히 장치를 초기화하거나 사용 중지할 수 없습니다.

-   등록된 장치에 대한 삭제된 장치 등록 관리자 계정의 관계는 유지되지만 추가 장치를 등록할 수는 없습니다.
