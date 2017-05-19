---
title: "회사 소유 장치 관리 | Microsoft 문서"
description: "회사 소유의 장치는 장치 유형, 장치 구매 방법, 조직의 요구 사항에 따라 다양한 방법으로 등록합니다."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 01/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2b60bbff-25e6-489b-9621-c71b4275fa06
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 8b2bd3ecba0b597bc742ea08872ffe8fc58155cf
ms.openlocfilehash: 8ef5f26eced99dac547be727fc96e41c11d3a0e7
ms.lasthandoff: 04/24/2017


---

# <a name="enroll-corporate-owned-devices-by-using-intune"></a>Intune을 사용하여 회사 소유 장치 등록

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

장치 유형, 장치 구매 방법, 조직의 요구 사항에 따라 다양한 방법으로 Intune을 통해 관리할 조직 소유 또는 회사 소유 장치를 등록할 수 있습니다. 회사 포털 앱을 설치하여 BYOD(Bring Your Own Device) 시나리오의 경우처럼 회사 소유 장치를 등록하고 관리할 수도 있습니다.

기본적으로 모든 플랫폼의 장치를 Intune에서 등록할 수 있습니다. 장치 등록을 차단하려면 관리자 자격 증명을 사용하여 [Microsoft Intune 관리 포털](https://manage.microsoft.com)에 로그인합니다. **관리** > **모바일 장치 관리** > **등록 규칙**을 선택한 다음 차단할 플랫폼의 확인란을 선택 취소합니다.

## <a name="enroll-corporate-owned-ios-devices"></a>회사 소유의 iOS 장치 등록

회사 소유 장치 등록 방법은 CYOD(Choose Your Own Device) 시나리오에 적합합니다. CYOD 환경에서 조직은 사용자가 선택하는 장치에 대한 비용을 지불하고 장치를 관리합니다.

사용자에게 선택할 iOS 장치를 제공하면 사용자가 장치를 처음 켤 때부터 Intune을 통해 장치가 관리되도록 등록을 미리 구성할 수 있습니다. Intune은 [Apple의 DEP(장치 등록 프로그램)](ios-device-enrollment-program-in-microsoft-intune.md)를 통한 등록을 지원하거나, [직접](ios-direct-enrollment-in-microsoft-intune.md) 또는 [설정 도우미](ios-setup-assistant-enrollment-in-microsoft-intune.md) 등록의 경우 Mac 컴퓨터의 Apple Configurator를 사용한 등록을 지원합니다.

[회사 소유의 iOS 장치를 등록](enroll-corporate-owned-ios-devices-in-microsoft-intune.md)하는 방법을 알아봅니다.

## <a name="create-a-device-enrollment-manager-account"></a>장치 등록 관리자 계정 만들기

Intune에서 단일 사용자 DEM(장치 등록 관리자) 계정을 만들어 많은 조직용 모바일 장치를 관리할 수 있습니다. DEM 계정을 만든 후 지정된 계정 관리자는 표준 사용자가 등록할 수 있는 16대 이상의 장치를 등록할 수 있습니다.

DEM 계정을 사용하여 한 명의 특정 사용자가 사용하지 않는 장치만 등록할 수 있습니다. 해당 장치 유형은 예를 들어 POS(Point-Of-Sale) 또는 유틸리티 앱에는 유용하지만 메일 또는 회사 리소스에 액세스해야 하는 사용자에게는 유용하지 않습니다.

[DEM 계정을 사용하여 회사 소유 장치를 등록](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)하는 방법을 알아봅니다.

## <a name="enroll-corporate-owned-windows-10-enterprise-devices"></a>회사 소유 Windows 10 Enterprise 장치 등록

조직에서 Azure Active Directory Premium 또는 Microsoft Enterprise Mobility Suite를 사용할 경우 [Windows 10 Enterprise 장치를 등록](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview)할 수 있습니다. 사용자가 장치에서 회사 또는 학교 계정을 추가하면 장치에는 자동으로 “회사 소유”라는 태그가 지정됩니다.

## <a name="import-imei-numbers"></a>IMEI 번호 가져오기

대부분 모바일 장치 제조업체는 장치에서 IMEI(International Mobile Equipment Identity)라는 고유 번호를 사용합니다. 조직이 소유한 장치에 대한 IMEI 번호를 가져올 수 있습니다. 장치가 Intune에서 관리되면 회사 소유 장치로 태그가 지정됩니다.

[IMEI 번호를 사용하여 회사 소유 장치에 태그를 지정](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md)하는 방법을 알아봅니다.

## <a name="identify-a-device-as-corporate-owned"></a>장치를 회사 소유로 식별

Intune은 다음 조건 중 하나가 충족되면 장치를 "회사"로 인식합니다.

 - 장치가 [DEM 계정을 사용하여 등록](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)되었습니다.
 - 장치가 [Apple DEP](ios-device-enrollment-program-in-microsoft-intune.md) 또는 [Apple Configurator](ios-setup-assistant-enrollment-in-microsoft-intune.md)를 사용하여 등록되었습니다(iOS만 해당).
 - 장치 제조업체가 [IMEI 번호를 사용하여 장치를 미리 선언](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md)했습니다(IMEI 번호를 가진 모든 플랫폼).
 - 장치가 [Azure Active Directory 또는 Enterprise Mobility Suite에 Windows 10 Enterprise 장치](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview)로 등록되어 있습니다(Windows 10만 해당).

장치가 회사로 태그 지정되면 관리자 콘솔의 해당 장치 레코드에서 **소유권** 열에 **회사**로 표시됩니다. 

