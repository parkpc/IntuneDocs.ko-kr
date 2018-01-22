---
title: "장치 등록 사용"
description: "MDM 기관을 설정하고 iOS, Windows, Android 및 Mac 장치에 대한 등록을 사용하도록 설정합니다."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d3215e7-0a5c-44bd-afb0-aeafce98c43f
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ab0dfd5abc1cf2f1a0d8576e9072509ba51b4e57
ms.sourcegitcommit: 22ab1c6a6bfeb4fef9850d12b29829c3fecbbeed
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2018
---
# <a name="enable-enrollment-for-mobile-devices"></a>모바일 장치에 대한 등록 사용

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

이 항목에서는 Intune 관리자가 모바일 장치 등록을 사용하도록 설정하는 방법을 설명합니다. 휴대폰에서 Intune을 사용하는 방법에 대한 도움말은 [using managed devices to get work done](https://docs.microsoft.com/intune-user-help/company-portal-frequently-asked-questions)(관리되는 장치를 사용하여 작업 완료)을 참조하세요.

Intune을 사용하여 모바일 장치 관리를 설정하려면 먼저 *모바일 장치 관리 기관*을 설정하여 계정과 연결된 장치를 관리할 수 있는 서비스를 식별해야 합니다. 이 지침에서는 System Center Configuration Manager 대신 Intune 서비스를 사용한다고 가정합니다. MDM 기관이 설정되면 장치 플랫폼에 대한 관리를 사용하도록 설정하고 회사 포털 앱을 사용하여 장치를 등록할 수 있습니다.

## <a name="enable-device-enrollment"></a>장치 등록 사용

1. **Intune을 모바일 장치 관리 기관으로 만들기** [Intune 관리 콘솔](https://manage.microsoft.com/)에서 **관리** > **모바일 장치 관리**를 클릭하고 **작업** 아래에서 **MDM 기관 설정**을 클릭합니다.  

2. MDM 기관 대화 상자에서 **예**를 선택합니다.

    ![관리 콘솔. Intune에 MDM 설정](../media/intune-mdm-authority.png)

## <a name="choose-how-to-enroll-devices"></a>장치를 등록하는 방법 선택

Intune에서는 회사의 요구 사항에 따라 다양한 방법으로 장치를 관리할 수 있습니다. “BYOD(Bring Your Own Device)”, 회사 소유 장치, “CYOD(Choose Your Own Device)”, 키오스크 모드 장치 등 다양한 등록 시나리오를 사용할 수 있습니다.

이러한 단계에 따라 [장치를 등록하는 방법을 선택](choose-how-to-enroll-devices1.md)합니다.

## <a name="enable-mdm-for-your-device-platform"></a>장치 플랫폼에 MDM을 사용하도록 설정
iOS, Mac 및 Android for Work 장치에 대해 등록을 사용하도록 설정하여 플랫폼 공급자와 Intune 테넌트 간의 관계를 설정해야 합니다. Windows 및 Android 장치에는 단계가 추가로 필요하지 않지만 Windows 장치의 경우 특수한 DNS 레지스트리 항목을 만들어 사용자의 장치 등록을 간소화할 수 있습니다.

관리하려는 장치 플랫폼에 대해 장치 등록을 사용하도록 설정합니다. 플랫폼에 따라 각기 다른 요구 사항을 충족해야 합니다.

- [iOS 및 macOS](/intune-classic/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune)
- [Window 10 및 Windows Phone](/intune-classic/deploy-use/set-up-windows-device-management-with-microsoft-intune)
- [Window PC](/intune-classic/deploy-use/manage-windows-pcs-with-microsoft-intune)(Intune 소프트웨어 클라이언트)
- [Android for Work](/intune-classic/deploy-use/set-up-android-for-work)

등록을 사용하도록 설정하면 사용자는 회사 포털 앱을 장치로 다운로드하고 장치 등록 프로세스를 완료할 수 있습니다.

### <a name="enable-company-owned-device-enrollment"></a>회사 소유 장치 등록 사용
다음을 비롯한 다양한 [회사 소유 장치 등록](/intune-classic/deploy-use/manage-corporate-owned-devices) 시나리오를 사용하도록 설정할 수도 있습니다.
- [Apple 장비 등록 프로그램](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune)
- [Apple Configurator 설치 도우미 등록](/intune-classic/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune)
- [Apple Configurator 직접 등록](/intune-classic/deploy-use/ios-direct-enrollment-in-microsoft-intune)
- [장치 등록 관리자](/intune-classic/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

### <a name="next-steps"></a>다음 단계
축하합니다. *Intune 빠른 시작 가이드*의 마지막 단계를 완료했습니다. 초기 구성을 완료했으니, 추가적인 MDM 기능 활성화를 고려할 수 있습니다.

>[!div class="step-by-step"]
>[&larr; **장치 등록**](.\start-with-a-paid-subscription-to-microsoft-intune-step-8.md)     [**구성 후 작업** &rarr;](.\post-configuration-tasks.md)  
