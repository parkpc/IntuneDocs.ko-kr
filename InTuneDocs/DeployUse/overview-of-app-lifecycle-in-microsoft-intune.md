---
# required metadata

title: 앱 수명 주기 개요 | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 60347012-bc3f-4b9a-a4f4-6d3c5021a6e6

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# 앱 수명 주기 개요

Intune 앱의 수명 주기는 앱이 추가될 때 시작하며 제거할 때까지 추가 단계를 진행해 나갑니다.

![앱 수명 주기](./media/applifecycle_nobg.png "the Intune app lifecycle")

## 추가

앱 배포의 첫 단계는 관리할 앱을 추가하고 Intune에 배포하는 것입니다. 작업할 수 있는 다양한 앱이 있지만 기본 절차는 동일합니다. Intune을 사용하여 [등록된 장치](add-apps-for-mobile-devices-in-microsoft-intune.md) 및 [Intune 클라이언트 소프트웨어를 사용하여 관리하는 Windows PC](add-apps-for-windows-pcs-in-microsoft-intune.md)에 대한 앱을 모두 추가할 수 있습니다..

## 배포:

앱을 Intune에 추가한 후 [관리하는 장치에 배포](deploy-apps.md)합니다. Intune은 이 과정을 쉽게 해 주며 앱이 배포된 후 Intune 관리 콘솔에서 배포의 [성공 여부를 모니터링](monitor-apps-in-microsoft-intune.md)할 수 있습니다. 또한 [Apple](manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune.md) 및 [Windows](manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune.md) 앱 서비스와 같은 일부 앱 스토어에서 회사용 앱 라이선스를 대량으로 구입할 수 있습니다. Intune은 데이터를 이러한 스토어와 동기화하여 이러한 유형의 앱에 대한 라이선스 사용을 Intune 관리 콘솔에서 바로 배포 및 추적할 수 있습니다.

## 구성

앱 수명 주기의 일부로 새 버전의 앱이 정기적으로 출시됩니다. Intune은 배포한 [앱을 쉽게 업데이트](update-apps-using-microsoft-intune.md)하기 위한 도구를 제공합니다. 또한 일부 앱을 사용하여 예를 들어 추가 기능을 구성할 수 있습니다.
- [iOS 앱 구성 정책](configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune.md)을 사용하여 앱이 실행될 때 사용되는 호환 iOS 앱에 대한 설정을 제공할 수 있습니다. 예를 들어 앱이 특정 브랜드 설정 또는 연결할 서버의 이름을 요구할 수 있습니다.
- [관리되는 브라우저 정책](manage-internet-access-using-managed-browser-policies.md)은 기본 장치 브라우저를 바꾸는 Intune 관리되는 브라우저에 대한 설정을 구성하고 사용자가 방문할 수 있는 웹 사이트를 제한하는 데 도움이 됩니다.

## 보호

Intune은 앱의 데이터를 보호하는 데 도움이 되는 많은 방법을 제공합니다. 주요 방법은 다음과 같습니다.
- [조건부 액세스](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)를 사용하여 장치 유형과 같은 지정하는 조건을 기반으로 전자 메일 및 기타 서비스 또는 배포한 [장치 준수 정책](introduction-to-device-compliance-policies-in-microsoft-intune.md) 준수에 대한 액세스를 제어할 수 있습니다.
- [모바일 응용 프로그램 관리(MAM)](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)는 개별 앱과 함께 작동하여 사용하는 회사 데이터를 보호하도록 도와 줍니다. 예를 들어 관리되지 않는 앱과 관리하는 앱 간의 데이터 복사를 제한하거나, 또는 무단 해제되거나 루팅된 장치에서의 앱 실행을 금지할 수 있습니다.

## 사용 중지

결국 배포한 앱이 만료되어 제거해야 할 가능성이 높습니다. Intune으로 쉽게 [앱 서비스 사용 중지](retire-apps-using-microsoft-intune.md).


<!--HONumber=May16_HO1-->


