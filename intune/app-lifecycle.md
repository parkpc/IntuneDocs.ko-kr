---
title: "Intune에 대한 앱 수명 주기 개요"
description: "Microsort Intune에서 관리되는 앱의 추가부터 최종 사용 중지까지 수명 주기에 대해 알아봅니다."
keywords: 
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 06/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 60347012-bc3f-4b9a-a4f4-6d3c5021a6e6
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 87bd0ceed846052444e4dac4366e3a0304b1452c
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2018
---
# <a name="overview-of-the-app-lifecycle"></a>앱 수명 주기 개요

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Intune 앱 수명 주기는 앱이 추가될 때 시작되어 앱을 제거할 때까지 추가 단계를 진행해 나갑니다.

![앱 수명 주기](./media/app-lifecycle.png "Intune 앱 수명 주기")

## <a name="add"></a>추가

앱 배포의 첫 단계는 관리 및 할당할 앱을 Intune에 추가하는 것입니다. 작업할 수 있는 앱 형식은 다양하지만, 기본 절차는 같습니다. Intune을 사용하여 [등록된 장치](apps-add.md)([클래식 포털](/intune-classic/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune)) 및 [Intune 클라이언트 소프트웨어를 사용하여 관리하는 Windows PC](/intune-classic/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune)에 대한 앱을 모두 추가할 수 있습니다.

## <a name="deploy"></a>배포

앱을 Intune에 추가한 후 [관리하는 사용자와 장치에 앱을 할당](apps-deploy.md)할 수 있습니다([클래식 포털](/intune-classic/deploy-use/deploy-apps)). Intune은 이 과정을 쉽게 수행할 수 있게 해주며 앱이 배포된 후 Intune 관리 콘솔에서 배포의 [성공 여부를 모니터링](apps-monitor.md)할 수 있습니다([클래식 포털](/intune-classic/deploy-use/monitor-apps-in-microsoft-intune)). 또한 [Apple](vpp-apps-ios.md)([클래식 포털](/intune-classic/deploy-use/manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune)) 및 [Windows](windows-store-for-business.md)([클래식 포털](/intune-classic/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune)) 앱 스토어와 같은 일부 앱 스토어에서 회사용 앱 라이선스를 대량으로 구매할 수 있습니다. Intune은 데이터를 이러한 스토어와 동기화하여 이러한 형식의 앱에 대한 라이선스 사용을 Intune 관리 콘솔에서 바로 배포 및 추적할 수 있습니다.

## <a name="configure"></a>구성

앱 수명 주기의 일부로 새 버전의 앱이 정기적으로 출시됩니다. Intune은 배포한 [앱을 쉽게 최신 버전으로 업데이트](apps-add.md)하는 도구를 제공합니다([클래식 포털](/intune-classic/deploy-use/update-apps-using-microsoft-intune)). 또한 일부 앱에 대한 추가 기능을 구성할 수 있으며, 예를 들면 다음과 같습니다.
- [iOS 앱 구성 정책](app-configuration-policies-use-ios.md)([클래식 포털](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune))은 앱이 실행될 때 사용되는 호환되는 iOS 앱에 대한 설정을 제공합니다. 예를 들어 앱이 특정 브랜드 설정 또는 연결할 서버의 이름을 요구할 수 있습니다.
- [Managed Browser 정책](app-configuration-managed-browser.md)([클래식 포털](/intune-classic/deploy-use/manage-internet-access-using-managed-browser-policies))은 기본 장치 브라우저를 바꾸는 Intune Managed Browser에 대한 설정을 구성하고 사용자가 방문할 수 있는 웹 사이트를 제한하는 데 도움이 됩니다.

## <a name="protect"></a>보호

Intune은 앱의 데이터를 보호하는 데 도움이 되는 많은 방법을 제공합니다. 주요 방법은 다음과 같습니다.
- [조건부 액세스](conditional-access.md)([클래식 포털](/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune))는 지정한 조건에 따라 메일 및 기타 서비스에 대한 액세스를 제어합니다. 조건에는 장치 유형 또는 배포한 [장치 준수 정책](device-compliance.md)([클래식 포털](/intune-classic/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune))에 대한 준수가 포함됩니다.
- [앱 보호 정책](app-protection-policy.md)([클래식 포털](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune))은 개별 앱에 대해 작동하여 이러한 앱에서 사용하는 회사 데이터를 보호하는 데 도움을 줍니다. 예를 들어 관리되지 않는 앱과 관리하는 앱 간의 데이터 복사를 제한하거나, 탈옥되거나 루팅된 장치에서 앱이 실행되지 않도록 할 수 있습니다.

## <a name="retire"></a>사용 중지

결국 배포한 앱이 만료되어 제거해야 할 가능성이 높습니다. Intune을 사용하면 [서비스에서 앱을 쉽게 사용 중지](device-management.md)할 수 있습니다([클래식 포털](/intune-classic/deploy-use/retire-apps-using-microsoft-intune)).
