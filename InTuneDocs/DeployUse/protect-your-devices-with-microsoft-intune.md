---
title: "장치 보호 | Microsoft Intune"
description: "Intune이 무단 액세스 및 기타 위협으로부터 장치를 보호하는 데 어떤 도움을 줄 수 있는지 알아봅니다."
keywords: 
author: Robstackmsft
manager: arob98
ms.date: 07/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 71e0cbf3-2bfb-412e-8a12-8503df08b4cf
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a409d36c1c5fcfd3d81ce0cbdf1f69af4747157a
ms.openlocfilehash: 53201c36e7a210c1c62d3ed3183093ed8e63dc53


---

# Microsoft Intune으로 장치 보호
Intune에서 장치를 관리하도록 한 후에는 무단 액세스 및 기타 위협에 대해 보호되도록 해야 합니다. 다음은 이러한 목표를 달성하는 데 도움이 되는 Intune의 기능 중 일부입니다.

> [!TIP]
> 이 항목에는 Intune에서 장치를 보호하는 데 도움이 될 수 있는 일부 방법만 포함합니다. 예를 들어, 암호 구성, 암호화 설정 및 하드웨어 기능(예: Bluetooth 및 장치 카메라) 등 장치에 대해 많은 보안 설정을 구성하도록 Intune 정책을 사용할 수 있습니다. 이러한 설정에 대해 자세히 알아보려면 [Microsoft Intune을 사용하여 장치의 설정 및 기능 관리](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)를 참조하세요.

## 사용자가 자신의 장치를 잠글 때 암호 재설정
모바일 장치의 회사 데이터를 보호하는 첫 번째 단계는 장치를 사용할 때 암호를 입력하도록 하는 것입니다. 때로는 암호를 제거하거나 원격으로 임시 암호를 설정하여 [암호를 재설정](use-remote-lock-and-passcode-reset-in-microsoft-intune.md)하거나 직원이 그렇게 하도록 해야 합니다. 장치를 분실하거나 도난당한 경우 [원격으로 장치를 잠글](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) 수도 있습니다.

## Windows 장치에 대한 추가 보호 계층 추가
[MFA(다단계 인증)](protect-windows-devices-with-multi-factor-authentication.md)는 네트워크에서 Windows 및 Windows Phone 장치의 사용자를 인증하는 더욱 안전한 방식입니다.  MFA를 사용하는 경우에는 사용자가 사용자 이름과 암호 외에 전화 통화나 문자 메시지를 통해 신원을 확인해야 합니다.

## Windows 장치에서 Microsoft Passport 설정 제어
Intune에서는 Active Directory 또는 Azure Active Directory 계정을 사용하여 암호, 스마트 카드 또는 가상 스마트 카드를 대신하는 Windows 10 이상의 대체 로그인 방법인 [Microsoft Passport for Work와 통합](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md)할 수 있습니다.

## iOS 장치에서 활성화 잠금 무시
활성화 잠금은 장치를 지우거나 다시 활성화하려면 먼저 Apple ID 및 암호를 입력하도록 하여 사용자 장치를 보호하는 기능입니다. 그러나 사용자가 잠금을 제거하지 않고 회사를 떠나는 경우 등에 문제가 발생할 수 있습니다. [iOS 활성화 잠금 무시](help-protect-ios-devices-with-activation-lock-bypass-for-microsoft-intune.md)는 감독 되는 iOS 장치에서 잠금을 제거하여 장치를 다시 할당하거나 지울 수 있도록 합니다.

## Intune 클라이언트로 관리하는 Windows PC 보호
Intune에서는 등록하지 않았지만 Intune 컴퓨터 클라이언트 소프트웨어로 관리되는 Windows PC에 대한 보안 정책을 계속해서 지원합니다. 이러한 정책을 사용하여 어떻게 Windows PC를 보호할 수 있는지 알아보려면 [Use policies to help protect Windows PCs that run the Intune client software](policies-to-protect-windows-pcs-in-microsoft-intune.md)(Intune 클라이언트 소프트웨어를 실행하는 Windows PC를 보호하는 데 도움이 되는 정책 사용)를 참조하세요.



<!--HONumber=Jul16_HO3-->


