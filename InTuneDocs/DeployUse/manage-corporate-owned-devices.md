---
title: "회사 소유 장치 관리 | Microsoft Intune"
description: "회사 소유 장치(COD)를 장치, 구입 방법 및 조직의 필요에 따라 다양한 방법으로 관리할 수 있습니다."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2b60bbff-25e6-489b-9621-c71b4275fa06
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ecfeb73efed4a47256275120c52de232c556adfe
ms.openlocfilehash: 58efadf2f9fc34a31070aff93e86083583630caa


---

# Microsoft Intune으로 회사 소유 장치 등록
조직 또는 회사 소유 장치(COD)를 장치, 구입 방법 및 조직의 요구에 따라 다양한 방법으로 Intune에서 관리할 수 있습니다. 회사 소유 장치는 “BYOD(Bring your own device)” 시나리오에서와 같이 회사 포털 앱을 설치하여 등록하고 관리할 수 있습니다.

## 회사 소유 iOS 장치 관리
이 등록 방법은 조직이 사용자용 장치를 구입하지만 장치 관리를 유지하고자 하는 “고유 장치 선택”(CYOD) 시나리오에 유용합니다. 조직이 iOS 장치를 구입한 경우 사용자가 장치를 처음 켤 때부터 장치가 관리되도록 등록을 미리 구성할 수 있습니다. Intune은 [Apple의 장치 등록 프로그램(DEP)](ios-device-enrollment-program-in-microsoft-intune.md)을 통한, 또는 [직접](ios-direct-enrollment-in-microsoft-intune.md) 또는 [설정 길잡이](ios-setup-assistant-enrollment-in-microsoft-intune.md) 등록의 경우 Mac 컴퓨터에서 실행하는 Apple 구성기를 사용한 등록을 지원합니다.

[회사 소유의 iOS 장치 등록](enroll-corporate-owned-ios-devices-in-microsoft-intune.md)

## 장치 등록 관리자
조직에서는 Intune을 사용하여 장치 등록 관리자 계정이라는 단일 사용자 계정으로 많은 수의 모바일 장치를 관리할 수 있습니다. 장치 등록 관리자 계정을 만든 후 해당 계정을 사용하여 관리자가 일반 사용자에게 기본적으로 허용한 표준 장치 5개 이상을 등록할 수 있습니다. 장치 등록 관리자로 장치를 등록하는 방법은 특정 사용자가 사용하지 않는 장치에만 적용됩니다. 이러한 장치는 예를 들어 POS(Point-Of-Sale) 또는 유틸리티 앱에는 유용하지만 전자 메일 또는 회사 리소스에 액세스해야 하는 사용자에게는 불편합니다.

[장치 등록 관리자로 회사 소유 장치 등록](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)

## 회사 소유 Windows 10 데스크톱 등록

조직에 AADP(Azure Active Directory Premium) 또는 EMS(Enterprise ManaActivegement Suite)가 있는 경우 [엔터프라이즈용 Windows 10을 등록](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview)할 수 있습니다. 그러면 사용자가 회사 또는 학교 계정을 추가할 때 "회사 소유"로 자동 태깅됩니다.

## 회사 소유의 장치 식별

회사 소유의 장치 목록의 **소유권** 아래에 **회사**로 나열됩니다. 다음과 같은 방법으로 장치를 회사 소유로 식별할 수 있습니다.

 - [DEM(장치 등록 관리자)를 사용하여 등록](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)
 - Apple의 [DEP(장치 등록 프로그램)](ios-device-enrollment-program-in-microsoft-intune.md) 또는 [Apple Configurator](ios-setup-assistant-enrollment-in-microsoft-intune.md)로 등록
 - [IMEI 번호를 사용하여 장치 미리 선언](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md)
 - [Windows 10 장치의 Azure Active Directory/Enterprise Management Suite 등록](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview)

### IMEI(International Mobile Equipment Identity)

고유 국제 모바일 장비 ID(IMEI) 번호는 많은 모바일 장치 제조업체에 대 한 일반적인 장치 속성입니다. Intune 관리자는 회사 소유 장치에 대 한 IMEI 번호를 가져올 수 있습니다. 장치가 Intune에서 관리되면 회사 소유 장치로 태그가 지정됩니다.

[IMEI(International Mobile Equipment Identity) 번호로 회사 소유의 장치 지정](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md)



<!--HONumber=Jul16_HO4-->


