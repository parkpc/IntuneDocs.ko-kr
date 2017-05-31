---
title: "앱 수명 주기 개요 | Microsoft 문서"
description: "Microsort Intune에서 관리되는 앱의 추가부터 최종 사용 중지까지 수명 주기에 대해 알아봅니다."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 60347012-bc3f-4b9a-a4f4-6d3c5021a6e6
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 2c1b4876e92e64912f237560b346aedceb0771c5
ms.contentlocale: ko-kr
ms.lasthandoff: 05/23/2017


---

# <a name="overview-of-the-app-lifecycle"></a>앱 수명 주기 개요

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune 앱 수명 주기는 앱이 추가될 때 시작되어 앱을 제거할 때까지 추가 단계를 진행해 나갑니다.

![앱 수명 주기](./media/app-lifecycle.png "Intune 앱 수명 주기")

## <a name="add"></a>추가

앱 배포의 첫 단계는 관리 및 배포할 앱을 Intune에 추가하는 것입니다. 작업할 수 있는 앱 형식은 다양하지만, 기본 절차는 같습니다. Intune을 사용하여 [등록된 장치](add-apps-for-mobile-devices-in-microsoft-intune.md) 및 [Intune 클라이언트 소프트웨어를 사용하여 관리하는 Windows PC](add-apps-for-windows-pcs-in-microsoft-intune.md)에 대한 앱을 모두 추가할 수 있습니다.

## <a name="deploy"></a>배포:

앱을 Intune에 추가한 후 [관리하는 장치에 앱을 배포](deploy-apps.md)할 수 있습니다. Intune은 이 과정을 쉽게 수행할 수 있게 해주며 앱이 배포된 후 Intune 관리 콘솔에서 배포의 [성공 여부를 모니터링](monitor-apps-in-microsoft-intune.md)할 수 있습니다. 또한 [Apple](manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune.md) 및 [Windows](manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune.md) 앱 스토어와 같은 일부 앱 스토어에서 회사용 앱 라이선스를 대량으로 구매할 수 있습니다. Intune은 데이터를 이러한 스토어와 동기화하여 이러한 형식의 앱에 대한 라이선스 사용을 Intune 관리 콘솔에서 바로 배포 및 추적할 수 있습니다.

## <a name="configure"></a>구성

앱 수명 주기의 일부로 새 버전의 앱이 정기적으로 출시됩니다. Intune은 배포한 [앱을 쉽게 최신 버전으로 업데이트](update-apps-using-microsoft-intune.md)하는 도구를 제공합니다. 또한 일부 앱에 대한 추가 기능을 구성할 수 있으며, 예를 들면 다음과 같습니다.
- [iOS 앱 구성 정책](configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune.md)은 앱이 실행될 때 사용되는 호환되는 iOS 앱에 대한 설정을 제공합니다. 예를 들어 앱이 특정 브랜드 설정 또는 연결할 서버의 이름을 요구할 수 있습니다.
- [관리되는 브라우저 정책](manage-internet-access-using-managed-browser-policies.md)은 기본 장치 브라우저를 바꾸는 Intune Managed Browser에 대한 설정을 구성하고 사용자가 방문할 수 있는 웹 사이트를 제한하는 데 도움이 됩니다.

## <a name="protect"></a>보호

Intune은 앱의 데이터를 보호하는 데 도움이 되는 많은 방법을 제공합니다. 주요 방법은 다음과 같습니다.
- [조건부 액세스](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)는 지정한 조건에 따라 메일 및 기타 서비스에 대한 액세스를 제어합니다. 조건에는 장치 유형 또는 배포한 [장치 준수 정책](introduction-to-device-compliance-policies-in-microsoft-intune.md)에 대한 준수가 포함됩니다.
- [MAM(모바일 응용 프로그램 관리)](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)은 개별 앱에 대해 작동하여, 사용하는 회사 데이터를 보호하는 데 도움을 줍니다. 예를 들어 관리되지 않는 앱과 관리하는 앱 간의 데이터 복사를 제한하거나, 탈옥되거나 루팅된 장치에서 앱이 실행되지 않도록 할 수 있습니다.

## <a name="retire"></a>사용 중지

결국 배포한 앱이 만료되어 제거해야 할 가능성이 높습니다. Intune을 사용하면 [서비스에서 앱을 쉽게 사용 중지](retire-apps-using-microsoft-intune.md)할 수 있습니다.

