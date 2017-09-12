---
title: "Intune에서 Windows 장치를 등록하는 방법 선택"
titlesuffix: Azure portal
description: "Microsoft Intune에서 Windows 장치 등록을 설정하는 방법을 알아봅니다.\""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 09/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 439c33a6-e80c-4da9-ba09-a51fc36f62ad
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 72b30ceed928ed2d3768441a5b5c2fbd8ffdeea4
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/09/2017
---
# <a name="enroll-ios-devices-in-intune"></a>Intune에 iOS 장치 등록

Intune은 iPad 및 iPhone의 MDM(모바일 장치 관리)을 가능하게 하고, 사용자가 회사 메일 및 앱에 액세스할 수 있게 해줍니다.

Intune 관리자는 iOS 장치에 대한 등록을 사용하도록 설정할 수 있습니다. 사용자가 개인적으로 소유한 장치를 등록(BYOD("Bring Your Own Device") 등록이라고 함)하도록 허용할 수 있습니다. 회사 소유 장치 등록을 사용하도록 설정할 수도 있습니다.

## <a name="prerequisites-for-ios-enrollment"></a>iOS 등록을 위한 필수 구성 요소
iOS 장치를 사용하도록 설정하기 전에 다음 단계를 완료해야 합니다.
- [Intune 설정](setup-steps.md) - 이러한 단계에서는 Intune 인프라를 설정합니다. 특히 장치를 등록하려면 [MDM 기관을 설정](mdm-authority-set.md)해야 합니다.
- [Apple MDM 푸시 인증서 가져오기](apple-mdm-push-certificate-get.md) - Apple의 경우 iOS 및 macOS 장치 관리를 사용하려면 인증서가 필요합니다.

## <a name="user-owned-ios-devices-byod"></a>사용자 소유 iOS 장치(BYOD)

사용자가 Intune 관리에 대해 개인 장치를 등록하도록 할 수 있습니다. 이를 "Bring Your Own Device" 또는 BYOD라고 합니다. 필수 구성 요소를 완료하고 사용자 라이선스를 할당하면 앱 스토어에서 iOS 회사 포털 앱을 다운로드하고 앱에서 등록 지침을 수행할 수 있습니다.

## <a name="company-owned-ios-devices"></a>회사 소유 iOS 장치
사용자를 위해 장치를 구입하는 조직의 경우, Intune은 다음과 같은 iOS 회사 소유 장치 등록 방법을 지원합니다.

- Apple의 DEP(장치 등록 프로그램)
- Apple School Manager
- Apple Configurator 설치 도우미 등록
- Apple Configurator 직접 등록

[장치 등록 관리자](device-enrollment-manager-enroll.md) 계정을 사용하여 회사 소유 iOS 장치를 등록할 수도 있습니다.

## <a name="device-enrollment-program"></a>장치 등록 프로그램
조직은 Apple의 DEP(장치 등록 프로그램)를 통해 iOS 장치를 구매할 수 있습니다. DEP를 통해 등록 프로필을 "무선"으로 배포하여 장치를 관리할 수 있습니다. [장치 등록 프로그램](device-enrollment-program-enroll-ios.md)에 대해 자세히 알아보세요.

## <a name="apple-school-manager"></a>Apple School Manager
Apple School Manager는 학교용 장치 구매 및 등록 프로그램입니다. DEP처럼 프로필을 배포하여 장치를 관리에 등록할 수 있습니다. [Apple School Manager](apple-school-manager-set-up-ios.md)에 대해 자세히 알아보세요.

## <a name="apple-configurator"></a>Apple Configurator
Mac 컴퓨터에서 실행되는 Apple Configurator를 사용하여 iOS 장치를 등록할 수 있습니다. 장치를 준비하려면 장치를 USB로 연결하고 등록 프로필을 설치합니다. Apple Configurator를 사용하여 다음 두 가지 방법으로 장치를 등록할 수 있습니다.
- 설정 도우미 등록 - 장치를 초기화하고 설정 도우미를 실행할 수 있도록 준비하여 장치의 새 사용자용으로 회사 정책을 설치합니다.
- 직접 등록 - 장치를 초기화하지 않고 미리 정의된 정책을 사용하여 장치를 등록합니다. 이 방법은 사용자 선호도가 없는 장치용입니다.

[Apple Configurator 등록](apple-configurator-setup-assistant-enroll-ios.md)에 대해 자세히 알아보세요.
