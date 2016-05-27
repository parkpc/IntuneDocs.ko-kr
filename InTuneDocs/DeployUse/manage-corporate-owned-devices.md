---
# required metadata

title: Microsoft Intune으로 회사 소유 장치 관리 | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 2b60bbff-25e6-489b-9621-c71b4275fa06

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune으로 회사 소유 장치 등록
조직이나 회사 소유 장치(COD)를 장치 및 구입 방법에 따라 다양한 방법으로 관리할 수 있습니다.

## 회사 소유 iOS 장치 관리
이 등록 방법은 조직이 사용자용 장치를 구입하지만 장치 관리를 유지하고자 하는 “고유 장치 선택”(CYOD) 시나리오에 유용합니다. 조직이 iOS 장치를 구입한 경우 사용자가 장치를 처음 켤 때부터 장치가 관리되도록 등록을 미리 구성할 수 있습니다. Intune은 [Apple의 장치 등록 프로그램(DEP)](ios-device-enrollment-program-in-microsoft-intune.md)을 통한, 또는 [직접](ios-direct-enrollment-in-microsoft-intune.md) 또는 [설정 길잡이](ios-setup-assistant-enrollment-in-microsoft-intune.md) 등록의 경우 Mac 컴퓨터에서 실행하는 Apple 구성기를 사용한 등록을 지원합니다.

[회사 소유의 iOS 장치 등록](enroll-corporate-owned-ios-devices-in-microsoft-intune.md)

## 장치 등록 관리자
조직에서는 Intune을 사용하여 장치 등록 관리자 계정이라는 단일 사용자 계정으로 많은 수의 모바일 장치를 관리할 수 있습니다. 장치 등록 관리자 계정을 만든 후 해당 계정을 사용하여 관리자가 일반 사용자에게 기본적으로 허용한 표준 장치 5개 이상을 등록할 수 있습니다. 장치 등록 관리자로 장치를 등록하는 방법은 특정 사용자가 사용하지 않는 장치에만 적용됩니다. 이러한 장치는 예를 들어 POS(Point-Of-Sale) 또는 유틸리티 앱에는 유용하지만 전자 메일 또는 회사 리소스에 액세스해야 하는 사용자에게는 불편합니다.

[장치 등록 관리자로 회사 소유 장치 등록](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)

## IMEI(International Mobile Equipment Identity)로 회사 소유의 장치 지정
고유 국제 모바일 장비 ID(IMEI) 번호는 많은 모바일 장치 제조업체에 대 한 일반적인 장치 속성입니다. Intune 관리자는 회사 소유 장치에 대 한 IMEI 번호를 가져올 수 있습니다. 장치가 Intune에서 관리하게 되면 회사 소유 장치로 태그를 지정하고 해당 정책의 대상으로 지정할 수 있습니다

[IMEI(International Mobile Equipment Identity) 번호로 회사 소유의 장치 지정](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md)


<!--HONumber=May16_HO1-->


