---
title: "Intune에서 iOS 장치를 등록하는 방법 선택"
titleSuffix: Intune on Azure
description: "Microsoft Intune에서 iOS 장치 등록을 설정하는 방법을 알아봅니다.\""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e6c0a430-1851-4108-812a-87e0fc2623b5
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 092f582cf30210858bd8cdd3879edfa873523ccb
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2017
---
# <a name="choose-how-to-enroll-ios-and-macos-devices"></a>iOS 및 macOS 장치를 등록하는 방법 선택

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

이 항목에서는 IT 관리자가 Intune에서 iOS 장치 등록을 사용하도록 설정하는 데 사용할 수 있는 방법을 설명합니다.

다음 정보를 사용하여 iOS 장치를 등록하는 데 사용할 방법을 결정합니다. BYOD를 제외하고 다음 방법은 모두 회사 소유 장치를 등록하는 데 사용됩니다.

**:** [Apple Push Notification Service 인증서](apple-mdm-push-certificate-get.md)가 필요합니다.

## <a name="user-owned-ios-devices-byod"></a>사용자 소유 iOS 장치(BYOD)

자신의 개인 BYOD(Bring Your Own Device) 장치를 등록하려는 사용자는 앱 스토어에서 iOS용 회사 포털 앱을 다운로드하고 앱의 등록 지침을 따르면 됩니다. 등록한 후에는 회사 네트워크에 연결하고, 도메인 또는 Azure Active Directory에 가입하고, 회사 리소스에 액세스할 수 있습니다. BYOD를 사용하도록 설정하려는 경우 충족해야 하는 요구 사항은 [Apple Push Notification Service 인증서](apple-mdm-push-certificate-get.md)뿐입니다. 개인 소유 iOS 장치 등록을 차단할 수도 있습니다. 지침에 대해서는 [장치 유형 제한 설정](enrollment-restrictions-set.md)을 참조하세요.

## <a name="user-owned-macos-devices-byod"></a>사용자 소유 macOS 장치(BYOD)

macOS 장치 등록을 사용하도록 설정할 수 있습니다. macOS 등록을 사용하도록 설정하려는 경우 충족해야 하는 요구 사항은 [Apple Push Notification Service 인증서](apple-mdm-push-certificate-get.md)뿐입니다. 자세한 내용은 [macOS 장치 등록](./macos-enroll.md)을 참조하세요.

## <a name="enrollment-program-with-apple"></a>Apple의 등록 프로그램
Apple은 장치 등록 및 관리 인프라를 포함하는 장치 구매 프로그램을 제공합니다. 이러한 프로그램 중 하나를 통해 구매한 장치는 Intune 관리를 위해 장치 일련 번호를 할당하여 "무선"으로 대량 등록할 수 있습니다.

- **DEM(장비 등록 프로그램)** - Apple의 조직 및 기업용 장치 등록 프로그램입니다. 자세한 내용은 [장비 등록 프로그램을 사용하여 iOS 장치 등록](device-enrollment-program-enroll-ios.md)을 참조하세요.
- **Apple School Manager** - Apple의 학교용 장치 등록 프로그램입니다. 자세한 내용은 [Apple School Manager를 통해 iOS 장치 등록 기능 사용](apple-school-manager-set-up-ios.md)을 참조하세요.

## <a name="apple-configurator"></a>Apple Configurator

회사 등록 프로필을 내보낸 후 해당 모바일 장치를 Apple Configurator를 실행하는 Mac에 연결하여 iOS 장치를 등록할 수 있습니다. Apple Configurator는 다음 두 가지 방식의 등록을 지원합니다.

- **설치 도우미 등록**: 장치를 공장 기본 설정으로 복원하고 장치의 새 사용자가 설치하도록 준비합니다. 이 방법을 사용하려면 관리자가 iOS 장치를 Apple Configurator를 실행하는 Mac 컴퓨터에 USB로 연결하여 등록을 미리 구성해야 합니다. 그러면 장치를 처음 시작할 때 설정 도우미를 실행하는 사용자에게 장치가 제공됩니다. 이 프로세스에서는 사용자의 회사 또는 학교 자격 증명을 사용하여 장치를 구성하고 등록 프로세스를 완료합니다. 자세한 내용은 [Apple Configurator 및 설정 도우미를 사용하여 iOS 장치 등록](apple-configurator-setup-assistant-enroll-ios.md)을 참조하세요.

- **직접 등록**: 장치를 준비하는 동안 사용할 수 있도록 Apple Configurator 규격 파일을 만듭니다. 등록된 장치가 공장 기본 설정으로 복원되지 않았으며 사용자 정보가 없습니다. 장치를 등록하려면 관리자가 iOS 장치를 Apple Configurator를 실행하는 Mac 컴퓨터에 USB로 연결해야 합니다. 자세한 내용은 [Apple Configurator 직접 등록을 사용하여 iOS 장치 등록](apple-configurator-direct-enroll-ios.md)을 참조하세요.

## <a name="use-the-device-enrollment-program-dep"></a>DEP(장비 등록 프로그램) 사용

DEP는 DEP를 통해 구입한 장치에 등록 프로필을 "무선으로" 배포합니다. 사용자가 장치를 처음 시작할 때 장치에서 설정 도우미를 실행하는 경우 장치는 Intune에 등록됩니다. 자세한 내용은 [을 사용하여 iOS 장치 등록](device-enrollment-program-enroll-ios.md)을 참조하세요.

## <a name="use-the-device-enrollment-manager-dem"></a>DEM(장치 등록 관리자) 사용
장치 등록 관리자는 최대 1,000개의 장치를 등록하고 관리할 수 있는 일반 사용자 계정입니다. DEM 관리 장치는 사용자 선호도를 포함할 수 없으므로 장치에는 소유자가 없습니다. Intune 사용자에게 DEM 권한을 부여하여 이러한 기능을 제공할 수 있습니다. DEM 사용자가 등록한 각 장치에서는 Intune 라이선스를 사용합니다. 자세한 내용은 [장치 등록 관리자를 사용하여 장치 등록](device-enrollment-manager-enroll.md)을 참조하세요.
