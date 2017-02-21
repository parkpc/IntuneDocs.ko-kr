---
title: "Intune에서 iOS 장치를 등록하는 방법 선택 | Intune Azure 미리 보기 | Microsoft 문서"
description: "Intune Azure 미리 보기: Microsoft Intune에서 iOS 장치 등록을 설정하는 방법을 알아봅니다."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 12/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e6c0a430-1851-4108-812a-87e0fc2623b5
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 990062ecf03a117dad74eb71e3f40abb79f22be6
ms.openlocfilehash: c228601451b33238d0f6929987dcdec3a5e56e8d


---

# <a name="choose-how-to-enroll-ios-devices"></a>iOS 장치를 등록하는 방법 선택

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

이 항목에서는 iOS 장치를 등록하는 데 사용할 수 있는 방법 및 등록을 위한 필수 구성 요소를 설명합니다.

다음 정보를 사용하여 iOS 장치를 등록하는 데 사용할 방법을 결정합니다. BYOD를 제외하고 다음 방법은 모두 회사 소유 장치를 등록하는 데 사용됩니다.

**:** [Apple Push Notification Service 인증서](get-an-apple-mdm-push-certificate.md)가 필요합니다.

## <a name="user-owned-ios-devices-byod"></a>사용자 소유 iOS 장치(BYOD)

사용자가 자신의 개인 BYOD(bring your own device) 장치를 등록하려는 경우 사용 가능한 등록 방법은 앱 스토어에서 iOS용 회사 포털 앱을 다운로드하고 앱의 등록 지침을 따르는 방법밖에 없습니다. 등록한 후에는 회사 네트워크에 연결하고, 도메인 또는 Azure Active Directory에 가입하고, 회사 리소스에 액세스할 수 있습니다.

## <a name="apple-configurator"></a>Apple Configurator

회사 등록 프로필을 내보낸 후 해당 모바일 장치를 [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017)를 실행하는 Mac에 연결하여 iOS 장치를 등록할 수 있습니다. Apple Configurator는 다음 두 가지 방식의 등록을 지원합니다.

- **설치 도우미 등록**: 장치를 공장 기본 설정으로 복원하고 장치의 새 사용자가 설치하도록 준비합니다. 이 방법을 사용하려면 관리자가 iOS 장치를 Apple Configurator를 실행하는 Mac 컴퓨터에 USB로 연결하여 등록을 미리 구성해야 합니다. 그러면 설치 도우미 프로세스를 실행하는 사용자에게 장치가 제공됩니다. 이 프로세스에서는 사용자의 회사 또는 학교 자격 증명을 사용하여 장치를 구성하고 등록 프로세스를 완료합니다. 자세한 내용은 [Apple Configurator 및 설정 도우미를 사용하여 iOS 장치 등록](enroll-ios-devices-with-apple-configurator-and-setup-assistant.md)을 참조하세요.

- **직접 등록**: 장치를 준비하는 동안 사용할 수 있도록 Apple Configurator 규격 파일을 만듭니다. 등록된 장치가 공장 기본 설정으로 복원되지 않았으며 사용자 정보가 없습니다. 장치를 등록하려면 관리자가 iOS 장치를 Apple Configurator를 실행하는 Mac 컴퓨터에 USB로 연결해야 합니다. 자세한 내용은 [Apple Configurator 직접 등록을 사용하여 iOS 장치 등록](enroll-ios-devices-with-apple-configurator-and-direct-enrollment.md)을 참조하세요.

## <a name="use-the-device-enrollment-program-dep"></a>DEP(장치 등록 프로그램) 사용

DEP는 DEP를 통해 구입한 장치에 등록 프로필을 "무선으로" 배포합니다. 사용자가 장치에서 설정 도우미를 실행하는 경우 장치는 Intune에 등록됩니다. DEP를 통해 등록된 장치는 사용자가 등록을 취소할 수 없습니다. 자세한 내용은 [장치 등록 프로그램을 사용하여 iOS 장치 등록](enroll-ios-devices-using-device-enrollment-program.md)을 참조하세요.

## <a name="use-the-device-enrollment-manager-dem"></a>DEM(장치 등록 관리자) 사용
장치 등록 관리자는 최대 1000개의 장치를 등록하고 관리할 수 있는 사용자 계정 유형입니다. DEM 계정에 기존 사용자를 추가하여 이들에게 이러한 기능을 제공합니다. DEM 사용자가 등록한 각 장치에서는 단일 Intune 라이선스를 사용합니다. 자세한 내용은 [장치 등록 관리자를 사용하여 장치 등록](enroll-devices-using-device-enrollment-manager.md)을 참조하세요.



<!--HONumber=Feb17_HO1-->


