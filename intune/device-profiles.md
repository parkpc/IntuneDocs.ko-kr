---
title: "Microsoft Intune에서 장치 프로필이란?"
titlesuffix: Azure portal
description: "Intune 장치 프로필과 이를 통해 회사에서 장치를 관리 및 보호하는 방법을 알아봅니다.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/23/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1053ddf4195e8481cf383c441664e07c02dacdec
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/09/2017
---
# <a name="what-are-microsoft-intune-device-profiles"></a>Microsoft Intune 장치 프로필이란?

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Microsoft Intune **장치 구성** 워크로드를 사용하여 관리하는 모든 장치의 설정 및 기능을 관리할 수 있습니다. 대부분 이 워크로드를 사용하여 장치 프로필을 만들 수 있습니다. 장치 프로필을 통해 장치에서 광범위한 기능을 관리하고 제어할 수 있습니다.

이 워크로드를 열면 다음 옵션이 표시됩니다.

- **개요** - 이 페이지에는 사용자 및 장치에 할당한 장치 구성을 모니터링하는 데 도움이 되는 보고서 및 상태가 표시됩니다.
- **프로필 관리** - 이 섹션에서는 장치 구성 프로필을 만들 수 있습니다. 만들 수 있는 모든 프로필 유형 목록은 이 항목의 뒷부분에서 확인할 수 있습니다.
- **인증 기관 설정** - 이 워크플로는 Intune 인증서 프로필을 구성하는 데 필요한 단계를 안내합니다.

## <a name="getting-started"></a>시작하기

장치 프로필을 만드는 워크플로는 모든 프로필에 대해 유사합니다. 자세한 내용은 [Microsoft Intune 장치 구성 프로필을 만드는 방법](device-profile-create.md)을 참조하세요. 그런 다음 각 프로필 유형의 설정을 만드는 방법에 대한 구체적인 정보를 계속 읽어보세요.

장치에서 다음과 같은 기능을 관리할 수 있습니다.

## <a name="device-features"></a>장치 기능

장치 기능을 통해 IOS 및 macOS 장치에서 AirPrint, 알림 및 공유 장치 구성과 같은 기능을 제어할 수 있습니다.
자세한 내용은 [장치 기능 설정을 구성하는 방법](device-features-configure.md)을 참조하세요. 지원: iOS 및 macOS

## <a name="device-restrictions"></a>장치 제한 사항
장치 제한을 사용하면 보안, 하드웨어 및 데이터 공유 설정을 포함하여 여러 범주에 걸쳐 관리하는 장치의 많은 설정을 제어할 수 있습니다. 예를 들어 iOS 장치의 사용자가 장치 카메라에 액세스하지 못하도록 하는 장치 제한 프로필을 만들 수 있습니다.
자세한 내용은 [장치 제한 설정을 구성하는 방법](device-restrictions-configure.md)을 참조하세요. 지원: Android, iOS, macOS, Windows 10 및 Windows 10 Team

## <a name="email"></a>메일
관리하는 장치에서 메일 프로필을 사용하여 Exchange ActiveSync 메일 설정을 만들고, 할당하고, 모니터링할 수 있습니다. 메일 프로필을 사용하면 일관성이 보장되고, 지원 요청이 감소하며, 최종 사용자가 필요한 설정 없이 자신의 개인 장치에서 회사 메일에 액세스하도록 할 수 있습니다.
자세한 내용은 [메일 설정을 구성하는 방법](email-settings-configure.md)을 참조하세요. 지원: Android, iOS, Windows Phone 8.1 및 Windows 10

## <a name="wi-fi"></a>Wi-Fi
Wi-Fi 프로필을 사용하여 무선 네트워크 설정을 조직의 사용자와 장치에 할당합니다. Wi-Fi 프로필을 할당하면 사용자가 Wi-Fi를 직접 구성하지 않고도 회사 Wi-Fi에 액세스할 수 있습니다.
자세한 내용은 [Wi-Fi 설정을 구성하는 방법](wi-fi-settings-configure.md)을 참조하세요. 지원: Android, iOS, macOS 및 Windows 8.1(가져오기만)

## <a name="vpn"></a>VPN
VPN(가상 사설망)을 사용하면 사용자가 회사 네트워크에 안전하게 원격으로 액세스할 수 있습니다. 장치는 VPN 연결 프로필을 사용하여 VPN 서버와의 연결을 시작합니다. 조직의 사용자 및 장치에 VPN 프로필을 할당하면 네트워크에 쉽고 안전하게 연결할 수 있습니다.
자세한 내용은 [VPN 설정을 구성하는 방법](vpn-settings-configure.md)을 참조하세요.
지원: Android, iOS, macOS, Windows Phone 8.1, Windows 8.1 및 Windows 10

## <a name="education"></a>교육
Windows 시험 응시(Windows Take a Test) 앱에 대한 옵션을 구성할 수 있습니다. 이 설정을 구성할 경우 테스트가 완료될 때까지 장치에서 다른 앱을 실행할 수 없습니다.
자세한 내용은 [교육 설정을 구성하는 방법](education-settings-configure.md)을 참조하세요.

## <a name="certificates"></a>인증서
이 프로필 유형을 사용하여 장치에 할당하고 Wi-Fi, VPN 및 메일 프로필을 인증하는 데 사용할 수 있는 신뢰할 수 있는 SCEP 및 PKCS 인증서를 구성할 수 있습니다.
자세한 내용은 [인증서를 구성하는 방법](certificates-configure.md)을 참조하세요. 지원: Android, iOS, Windows Phone 8.1, Windows 8.1 및 Windows 10

## <a name="edition-upgrade"></a>버전 업그레이드
이 프로필 유형을 사용하면 일부 버전의 Windows 10을 실행하는 장치를 최신 버전으로 자동으로 업그레이드할 수 있습니다.
자세한 내용은 [Windows 10 버전 업그레이드를 구성하는 방법](edition-upgrade-configure-windows-10.md) 지원: Windows 10만 해당을 참조하세요.

## <a name="endpoint-protection"></a>Endpoint Protection
이 프로필 유형을 사용하면 Windows 10 장치에 대한 BitLocker 및 Windows Defender 설정을 구성할 수 있습니다.
자세한 내용은 [Windows 10에 대한 Endpoint Protection 설정](endpoint-protection-windows-10.md) 지원: Windows 10만 해당을 참조하세요.

## <a name="windows-information-protection"></a>Windows Information Protection
Windows 정보 보호는 직원 환경을 방해하지 않으면서 데이터 유출로부터 보호하는 데 도움이 됩니다. 또한 작업 환경이나 기타 앱을 변경하지 않고도 엔터프라이즈 앱 및 데이터가 회사 소유 장치 및 직원이 회사에 가져오는 개인 장치에서 실수로 누출되지 않도록 보호하는 데도 유용합니다.
자세한 내용은 [Windows Information Protection을 구성하는 방법](windows-information-protection-configure.md)을 참조하세요. 지원: Windows 10만 해당

## <a name="custom"></a>사용자 지정
사용자 지정 설정을 사용하면 Intune에 기본 제공되지 않는 장치 설정을 할당할 수 있습니다. 예를 들어 Android 장치에서 해당 장치를 구성하는 OMA-URI 값을 지정할 수 있습니다. IOS 장치의 경우 Apple Configurator에서 만든 구성 파일을 가져올 수 있습니다.
자세한 내용은 [사용자 지정 설정을 구성하는 방법](custom-settings-configure.md)을 참조하세요. 지원: Android, iOS, macOS 및 Windows Phone 8.1

## <a name="next-steps"></a>다음 단계
장치 구성을 시작하려면 목록에서 프로필 유형 중 하나를 선택합니다.
