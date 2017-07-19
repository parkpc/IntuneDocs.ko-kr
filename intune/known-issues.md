---
title: "Azure의 Microsoft Intune에서 알려진 문제"
titleSuffix: Intune on Azure
description: "Intune의 알려진 문제에 대해 알아봅니다.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/27/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33a6645-a57e-4424-a1e9-0ce932ea83c5
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4fda224613d8b69be82ef7f9681ba9165be33e52
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2017
---
# <a name="known-issues-in-microsoft-intune"></a>Microsoft Intune의 알려진 문제


[!INCLUDE[azure_portal](./includes/azure_portal.md)]


이 항목을 사용하여 Microsoft Intune의 알려진 문제를 파악할 수 있습니다.

여기에 나열되지 않은 버그를 보고하려면 [지원 요청을 시작](get-support.md)하세요.

Intune의 새로운 기능을 요청하려면 [Uservoice](https://microsoftintune.uservoice.com/forums/291681-ideas/category/189016-azure-admin-console) 사이트에서 보고서를 제출하는 것이 좋습니다.

## <a name="migration"></a>마이그레이션

### <a name="groups-created-by-intune-during-migration-might-affect-functionality-of-other-microsoft-products"></a>마이그레이션 도중 Intune이 만든 그룹은 다른 Microsoft 제품의 기능에 영향을 줄 수 있습니다.

클래식 Intune에서 Azure로 마이그레이션할 때 **All Users - b0b08746-4dbe-4a37-9adf-9e7652c0b421**이라는 이름의 새 그룹이 보일 수 있습니다. 이 그룹에는 Intune의 사용이 허가된 사용자뿐만 아니라 Azure Active Directory의 모든 사용자도 포함됩니다. 이러한 사용 방식으로 인해 일부 기존 또는 새로운 사용자가 어떤 그룹의 멤버도 아니라면 다른 Microsoft 제품에서 문제가 발생할 수 있습니다.

### <a name="secondary-migration-required-for-select-capabilities"></a>일부 기능에 필요한 보조 마이그레이션

2017년 1월 이전에 만든 Intune 계정의 경우 마이그레이션해야 Azure Portal에서 다음 기능을 사용할 수 있습니다.

- 회사 장치 등록 프로필
- Apple 장비 등록 프로그램
- iOS 일련 번호 그룹을 통해 회사에서 사전 등록한 장치
- 장치 등록 관리자
- Apple Volume Purchase Program

이러한 기능은 클래식 Silverlight 및 Azure 콘솔에서 관리할 수 없으므로 마이그레이션에서는 다음 작업이 수행됩니다.
- 클래식 콘솔에서 이러한 기능이 사용하지 않도록 설정됩니다.
- Azure 콘솔에서 이러한 기능이 사용하도록 설정됩니다.  

이제 Azure Portal에서 이러한 Intune 기능을 관리하는 경우 다음 사항에 유의하세요.

#### <a name="removes-default-corporate-device-enrollment-profiles-in-apple-dep"></a>Apple DEP에서 기본 회사 장치 등록 프로필 제거
Azure Portal에서는 Apple DEP(장비 등록 프로그램) 장치에 대한 기본 회사 장치 등록 프로필을 지원하지 않습니다. 클래식 Silverlight Intune 콘솔에서 사용할 수 있는 이 기능은 의도치 않은 프로필 할당을 방지하기 위해 중단됩니다. Azure Portal에서 DEP 일련 번호를 동기화할 때는 회사 장치 등록 프로필이 할당되지 않습니다. 등록 프로필은 장치를 사용하기 전에 할당해야 합니다.

#### <a name="apple-dep-token-restored-with-migration"></a>Apple DEP 토큰이 마이그레이션 시 복원됨

Intune 클래식(Silverlight) 포털에서 Apple 장비 등록 프로그램 토큰을 삭제했으며 Azure Portal에 새 토큰을 업로드하지 않으면 마이그레이션 시 원래 토큰이 Azure Portal에서 복원됩니다. 이 토큰을 제거하고 DEP 등록을 방지하려면 Azure Portal에서 토큰을 삭제하세요.

### <a name="status-blades-for-migrated-policies-do-not-work"></a>마이그레이션한 정책에 대한 상태 블레이드가 작동하지 않음

클래식 포털에서 마이그레이션한 정책의 상태 정보는 Azure Portal에서 확인할 수 없습니다. 그러나 클래식 포털에서는 이러한 정책에 대한 보고서를 계속 확인할 수 있습니다.
마이그레이션한 구성 정책에 대한 상태 정보를 확인하려면 Azure Portal에서 정책을 다시 만드세요.

## <a name="apps"></a>앱

### <a name="ios-volume-purchased-apps-only-available-in-default-intune-tenant-language"></a>기본 Intune 테넌트 언어에서만 iOS 대량 구매 앱을 사용할 수 있음
iOS 대량 구매 앱은 Intune 계정과 동일한 국가 코드에 대해서만 표시되며 할당할 수 있습니다. Intune은 Intune 테넌트 계정 국가 코드와 동일한 iTunes 로캘의 앱만 동기화합니다. 예를 들어 미국 스토어에서만 사용할 수 있는 앱을 구매했는데 Intune 계정이 독일어라면 Intune에 해당 앱이 표시되지 않습니다.

### <a name="multiple-copies-of-the-same-ios-volume-purchase-program-are-uploaded"></a>동일한 iOS 대량 구매 프로그램의 여러 복사본이 업로드됨
동일한 VPP 토큰에 대해 **업로드** 단추를 여러 번 클릭하지 마세요. 여러 번 클릭하면 중복 VPP 토큰이 업로드되고, 동일한 VPP 토큰에 대해 앱이 여러 번 동기화됩니다. 

<!-- ## Groups -->

## <a name="device-configuration"></a>장치 구성

### <a name="you-cannot-save-a-windows-information-protection-policy-for-some-devices"></a>일부 장치에 대해 Windows Information Protection 정책을 저장할 수 없음

Intune에 등록되지 않은 장치의 경우 Windows Information Protection 정책에 대한 설정의 **회사 ID** 필드에서 주 도메인만 지정할 수 있습니다.
**고급 설정** > **네트워크 경계** > **보호된 도메인 추가**를 사용하여 도메인을 더 추가하는 경우 정책을 저장할 수 없습니다. 표시되는 오류 메시지는 조만간 보다 정확하게 변경될 예정입니다.

### <a name="cisco-anyconnect-vpn-client-support"></a>Cisco AnyConnect VPN 클라이언트 지원
 
Cisco AnyConnect VPN 클라이언트(4.0.07072)의 최신 릴리스는 현재 Intune과 호환되지 않습니다. 향후 Intune 업데이트에는 이 VPN 클라이언트 버전과의 호환성이 포함됩니다. 그때까지 Cisco AnyConnect VPN 클라이언트를 업데이트하지 말고 기존 버전을 계속 사용하는 것이 좋습니다.

### <a name="using-the-numeric-password-type-with-macos-sierra-devices"></a>macOS Sierra 장치에서 숫자 암호 유형 사용

현재는 macOS Sierra 장치에 대한 장치 제한 프로필에서 **숫자** **필수 암호 유형**을 선택하면 암호가 **영숫자**로 적용됩니다. 이러한 장치에 숫자 암호를 사용하려는 경우 이 설정을 구성하지 마세요.
이 문제는 향후 macOS 버전에서 해결될 수도 있습니다.

이러한 설정에 대한 자세한 내용은 [Microsoft Intune의 macOS 장치 제한 설정](device-restrictions-macos.md)을 참조하세요.

## <a name="compliance"></a>준수

### <a name="compliance-policies-from-intune-do-not-show-up-in-new-console"></a>Intune의 준수 정책이 새 콘솔에 표시되지 않음

클래식 포털에서 만든 준수 정책은 마이그레이션되기는 하지만 Azure Portal의 디자인 변경으로 인해 Azure Portal에 표시되지는 않습니다. 클래식 Intune 포털에서 만든 준수 정책은 계속 적용되기는 하지만, 클래식 Intune 포털에서 이러한 정책을 보고 편집해야 합니다.
또한 Azure Portal에서 만든 새 준수 정책은 클래식 Intune 포털에서는 보이지 않습니다.

자세한 내용은 [장치 준수](device-compliance.md)를 참조하세요.

<!-- ## Enrollment -->


<!-- ## Data protection -->


## <a name="administration-and-accounts"></a>관리 및 계정

전역 관리자(테넌트 관리자라고도 함)는 별도의 Intune 또는 EMS(Enterprise Mobility Suite) 라이선스 없이 일상적인 관리 작업을 계속 수행할 수 있습니다. 그러나 자신의 장치나 회사 장치 등록 또는 Intune 회사 포털 사용 등의 서비스를 사용하려는 전역 관리자에게는 Intune 또는 EMS 라이선스가 필요합니다.

<!-- ## Additional items -->












 
