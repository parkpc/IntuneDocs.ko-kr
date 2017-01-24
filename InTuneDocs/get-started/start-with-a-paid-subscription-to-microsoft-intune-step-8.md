---
title: "장치 등록 사용 | Microsoft 문서"
description: "MDM 기관을 설정하고 iOS, Windows, Android 및 Mac 장치에 대한 등록을 사용하도록 설정합니다."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d3215e7-0a5c-44bd-afb0-aeafce98c43f
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 654c5b65a9fde6742f3682b1fd5ba6c056d0d45b


---

# <a name="enroll-mobile-devices-and-install-an-app"></a>모바일 장치 등록 및 앱 설치

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune을 사용하여 모바일 장치 관리를 설정하려면 먼저 *모바일 장치 관리 기관*을 설정하여 계정과 연결된 장치를 관리할 수 있는 서비스를 식별해야 합니다. 이 지침에서는 System Center Configuration Manager 대신 Intune 서비스를 사용한다고 가정합니다. MDM 기관이 설정되면 장치 플랫폼에 대한 관리를 사용하도록 설정하고 회사 포털 앱을 사용하여 장치를 등록할 수 있습니다.

## <a name="enable-device-enrollment"></a>장치 등록 사용

1. **Intune을 모바일 장치 관리 기관으로 만들기** 
    [Intune 관리 콘솔](https://manage.microsoft.com/)에서 **관리** > **모바일 장치 관리**를 클릭하고 **작업** 아래에서 **MDM 기관 설정**을 클릭합니다.  

2. MDM 기관 대화 상자에서 **예**를 선택합니다.

    ![관리 콘솔. Intune에 MDM 설정](./media/mdmAuthority.png)

## <a name="choose-how-to-enroll-devices"></a>장치를 등록하는 방법 선택

Intune에서는 회사의 요구 사항에 따라 다양한 방법으로 장치를 관리할 수 있습니다. “BYOD(Bring Your Own Device)”, 회사 소유 장치, “CYOD(Choose Your Own Device)”, 키오스크 모드 장치 등 다양한 등록 시나리오를 사용할 수 있습니다.

이러한 단계에 따라 [장치를 등록하는 방법을 선택](choose-how-to-enroll-devices1.md)합니다.

## <a name="enable-mdm-for-your-device-platform"></a>장치 플랫폼에 MDM을 사용하도록 설정
iOS, Mac 및 Android for Work 장치에 대해 등록을 사용하도록 설정하여 플랫폼 공급자와 Intune 테넌트 간의 관계를 설정해야 합니다. Windows 및 Android 장치에는 단계가 추가로 필요하지 않지만 Windows 장치의 경우 특수한 DNS 레지스트리 항목을 만들어 사용자의 장치 등록을 간소화할 수 있습니다.

관리하려는 장치 플랫폼에 대해 장치 등록을 사용하도록 설정합니다. 플랫폼에 따라 각기 다른 요구 사항을 충족해야 합니다.

-  [iOS 및 macOS](https://docs.microsoft.com/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune.md)
-  [Windows PC](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune)
-  [Windows 10 Mobile 및 Windows Phone](https://docs.microsoft.com/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune)
- [Android for Work](https://docs.microsoft.com/intune/deploy-use/set-up-android-for-work)

등록을 사용하도록 설정하면 사용자는 회사 포털 앱을 장치로 다운로드하고 장치 등록 프로세스를 완료할 수 있습니다.

### <a name="enable-company-owned-device-enrollment"></a>회사 소유 장치 등록 사용
다음을 비롯한 다양한 [회사 소유 장치 등록](https://docs.microsoft.com/intune/deploy-use/manage-corporate-owned-devices) 시나리오를 사용하도록 설정할 수도 있습니다.
- [Apple 장치 등록 프로그램](https://docs.microsoft.com/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune)
- [Apple Configurator 설치 도우미 등록](https://docs.microsoft.com/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune)
- [Apple Configurator 설치 도우미 등록](https://docs.microsoft.com/intune/deploy-use/ios-direct-enrollment-in-microsoft-intune)
- [장치 등록 관리자](https://docs.microsoft.com/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

### <a name="next-steps"></a>다음 단계
축하합니다. *Intune 빠른 시작 가이드*의 마지막 단계를 완료했습니다. 초기 구성을 완료했으니, 추가적인 MDM 기능 활성화를 고려할 수 있습니다.

>[!div class="step-by-step"]

>[&larr; **장치 등록**](.\start-with-a-paid-subscription-to-microsoft-intune-step-8.md)     [**구성 후 작업** &rarr;](.\post-configuration-tasks.md)  



<!--HONumber=Dec16_HO2-->


