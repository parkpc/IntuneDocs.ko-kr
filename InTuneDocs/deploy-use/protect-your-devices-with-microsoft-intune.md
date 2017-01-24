---
title: "장치 보호 | Microsoft 문서"
description: "Intune이 무단 액세스 및 기타 위협으로부터 장치를 보호하는 데 어떤 도움을 줄 수 있는지 알아봅니다."
keywords: 
author: Robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 71e0cbf3-2bfb-412e-8a12-8503df08b4cf
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e7d1760a10e63233fe7cc7f6fd57a68c5283647c
ms.openlocfilehash: 47263a7b0e4255cfa3fe830c969ce6116447ae9f


---

# <a name="protect-devices-with-microsoft-intune"></a>Microsoft Intune으로 장치 보호

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune에서는 관리하는 장치와 해당 장치에 저장된 데이터를 보호하는 데 사용 가능한 모든 기능 집합을 제공합니다. 이 항목에서 이러한 기능과 관련된 기본 사항을 파악하고 자세한 정보를 확인하는 방법을 알아보세요.

## <a name="general-ways-to-protect-all-devices"></a>모든 장치를 보호하는 일반적인 방법

### <a name="device-configuration"></a>장치 구성
Intune [구성 정책](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)을 사용하면 폭넓은 설정 및 기능을 제어하여 장치를 쉽게 보호하고 구성할 수 있습니다. 예를 들면 다음과 같습니다.
- 카메라, Bluetooth 등의 장치에서 하드웨어 기능 사용을 제한할 수 있습니다.
- 규격 및 비규격 앱을 구성할 수 있습니다. 비규격 앱 설치 시 경고가 표시되며 플랫폼에 따라서는 설치가 실제로 차단될 수도 있습니다.

### <a name="reset-passcodes-when-users-are-locked-out-of-their-devices"></a>사용자가 자신의 장치를 잠글 때 암호 재설정
모바일 장치의 회사 데이터를 보호하는 첫 번째 단계는 장치를 사용할 때 암호를 입력하도록 하는 것입니다. 때로는 암호를 제거하거나 원격으로 임시 암호를 설정하여 [암호를 재설정](use-remote-lock-and-passcode-reset-in-microsoft-intune.md)하거나 직원이 그렇게 하도록 해야 합니다. 장치를 분실하거나 도난당한 경우 [원격으로 장치를 잠글](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) 수도 있습니다.

### <a name="retire-devices-and-remove-data"></a>장치 사용 중지 및 데이터 제거
사용자가 퇴사하거나 장치를 분실/도난당한 경우 등 장치를 [Intune 관리 대상에서 제거](retire-devices-from-microsoft-intune-management.md)해야 할 때는 해당 장치에서 데이터도 제거해야 하는 경우가 많습니다. Intune에서는 회사 데이터의 보안을 유지할 수 있는 폭넓은 방법을 제공합니다.

### <a name="require-devices-to-be-compliant"></a>장치가 규칙을 준수해야 하도록 지정
Intune에서는 지정한 규칙을 준수하지 않는 장치를 평가하고 경우에 따라 수정하는 데 사용할 수 있는 [장치 준수 정책](introduction-to-device-compliance-policies-in-microsoft-intune.md)을 제공합니다. 예를 들어 탈옥 상태의 iOS 장치, 장치 암호화 여부 또는 상태 증명 서비스에서 Windows 10 장치를 정상으로 보고하는지 여부 등에 대한 정보를 보고할 수 있습니다.

### <a name="protect-apps-and-the-data-they-use"></a>앱 및 앱에서 사용하는 데이터 보호
Intune에서는 앱과 해당 데이터를 보호하는 데 사용할 수 있는 다양한 기능을 제공합니다. 예를 들어 MAM(모바일 응용 프로그램 관리) 정책을 적용하면 보호된 앱에서 데이터 백업을 차단하고, 다른 앱으로의 복사/붙여넣기를 제한하고, 앱 액세스 시 PIN을 요구하는 등의 기능을 설정할 수 있습니다. 앱 보호에 대한 자세한 내용은 [Microsoft Intune으로 앱 및 데이터 보호](protect-apps-and-data-with-microsoft-intune.md)를 참조하세요.

## <a name="further-capabilities-for-windows-devices"></a>Windows 장치용 추가 기능

### <a name="add-an-additional-layer-of-protection-to-windows-devices"></a>Windows 장치에 대한 추가 보호 계층 추가
[MFA(다단계 인증)](protect-windows-devices-with-multi-factor-authentication.md)는 네트워크에서 Windows 및 Windows Phone 장치의 사용자를 인증하는 더욱 안전한 방식입니다.  MFA를 사용하는 경우에는 사용자가 사용자 이름과 암호 외에 전화 통화나 문자 메시지를 통해 신원을 확인해야 합니다.

### <a name="control-windows-hello-for-business-settings-on-windows-devices"></a>Windows 장치에서 비즈니스용 Windows Hello 설정 제어
Active Directory를 사용하는 Windows 10 이상 버전 또는 Azure Active Directory 계정에서 암호, 스마트 카드 또는 가상 스마트 카드를 대신하는 로그인 방법인 [비즈니스용 Windows Hello](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md)(이전 명칭 Microsoft Passport)와 Intune을 통합할 수 있습니다.

## <a name="further-capabilities-for-ios-devices"></a>iOS 장치용 추가 기능

### <a name="bypass-activation-lock-on-ios-devices"></a>iOS 장치에서 활성화 잠금 무시
활성화 잠금은 장치를 지우거나 다시 활성화하려는 경우 먼저 Apple ID 및 암호를 입력하도록 하여 사용자 장치를 보호하는 기능입니다. 그러나 사용자가 잠금을 제거하지 않고 회사를 떠나는 경우 등에 문제가 발생할 수 있습니다. [iOS 활성화 잠금 무시](help-protect-ios-devices-with-activation-lock-bypass-for-microsoft-intune.md)는 감독 되는 iOS 장치에서 잠금을 제거하여 장치를 다시 할당하거나 지울 수 있도록 합니다.



## <a name="protect-windows-pcs-managed-with-the-intune-client"></a>Intune 클라이언트로 관리하는 Windows PC 보호
Intune에서는 등록하지 않았지만 Intune 컴퓨터 클라이언트 소프트웨어로 관리되는 Windows PC에 대한 보안 정책을 계속해서 지원합니다. 이러한 정책을 사용하여 어떻게 Windows PC를 보호할 수 있는지 알아보려면 [Use policies to help protect Windows PCs that run the Intune client software](policies-to-protect-windows-pcs-in-microsoft-intune.md)(Intune 클라이언트 소프트웨어를 실행하는 Windows PC를 보호하는 데 도움이 되는 정책 사용)를 참조하세요.



<!--HONumber=Dec16_HO5-->


