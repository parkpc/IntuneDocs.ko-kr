---
title: "Microsoft Intune으로 BYOD를 사용하도록 설정"
description: "조직에서 BYOD(Bring Your Own Device) 솔루션을 사용할 수 있도록 Intune을 설정하는 작업에 대한 개략적인 워크플로."
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 07/26/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: vlpetros
ms.suite: ems
ms.openlocfilehash: 8684ea31420edd836038dc9337bd8bdf56e78ba6
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/03/2017
---
# <a name="enable-byod-with-intune"></a>Intune으로 BYOD를 사용하도록 설정

이 항목은 조직에서 BYOD(Bring Your Own Device) 솔루션을 사용할 수 있도록 Intune을 설정하는 작업에 대한 개략적인 워크플로를 제공합니다. 3개의 프로세스와 지원 방법 도움말 항목에 대한 링크로 작업이 구성되어 있습니다.

워크플로는 다음 3개의 프로세스로 구분됩니다. 조직의 요구 사항에 맞게 각 프로세스의 여러 측면을 조정할 수 있습니다.

-   **[장치 등록 및 준수 확인](#enroll-devices-and-check-for-compliance)**에서는 사용자가 개인 장치를 Intune의 관리 기능에 등록하는 방법을 설명합니다. Intune은 iOS, macOS, Android 및 Windows 장치를 관리합니다. 이 섹션에서는 장치에 정책을 배포하고 기본 보안 요구 사항을 충족하는 방법도 설명합니다.

- **[회사 리소스에 대한 액세스 권한 제공](#provide-access-to-company-resources)**에서는 사용자가 쉽고 안전하게 회사 리소스에 액세스할 수 있도록 지원하는 방법을 보여 줍니다. 이를 위해 관리되는 장치에 액세스 프로필을 배포하는 방식을 사용합니다. 이 섹션에서는 Intune을 통해 대량 구매 앱 배포를 관리하는 방법도 설명합니다.

-   **[회사 데이터 보호](#protect-company-data)**에서는 회사 리소스에 대한 조건부 액세스를 제공하고, 데이터 손실을 방지하며, 더 이상 업무에 필요하지 않거나 분실 또는 도난된 장치에서 회사 앱 및 데이터를 제거하는 방법을 알아볼 수 있습니다.

[![Microsoft Intune을 통해 BYOD를 사용하도록 설정하는 작업에 대한 개략적인 워크플로 다이어그램](./media/workflow-diagram-for-byod.png)](./media/workflow-diagram-for-byod.png)

<!--- > <sup>You can download this infographic at https://gallery.technet.microsoft.com/Infographic-Management-3644ae41.</sup> --->

## <a name="before-you-begin"></a>시작하기 전에
사용자가 장치를 등록하려면 먼저 Intune 서비스를 준비해야 합니다. 이를 위해 [사용자에게 라이선스를 할당](licenses-assign.md)하고 [모바일 장치 관리 기관을 설정](mdm-authority-set.md)하세요.

이때 [회사 포털도 사용자 지정](company-portal-customize.md)해야 합니다. 회사 브랜딩을 추가하고 사용자에게 지원 정보를 제공하세요. 이렇게 하면 사용자가 신뢰할 수 있는 등록 및 지원 환경이 만들어집니다. 사용자가 등록하기 전에 동의해야 하는 [사용 약관](terms-and-conditions-create.md) 또는 지원하는 플랫폼을 지정하기 위한 [장치 제한](enrollment-restrictions-set.md)도 만들어야 합니다.

## <a name="enroll-devices-and-check-for-compliance"></a>장치 등록 및 준수 확인

Intune 서비스를 준비한 후 관리하려는 다양한 장치 유형의 다양한 등록 요구 사항을 충족해야 합니다. 관리에 장치를 등록하는 과정은 간단하지만 장치 유형에 따라 약간씩 달라집니다.

-   **iOS 및 Mac 장치** iPads, iPhones 또는 MacOS 장치를 등록하려면 [Apple MDM 푸시 인증서 가져오기](apple-mdm-push-certificate-get.md)를 수행해야 합니다. Intune에 MDM 푸시 인증서를 업로드한 후에는 사용자가 회사 포털 앱을 사용하여 [iOS 장치를 등록](/intune-user-help/enroll-your-device-in-intune-ios)하고 회사 포털 웹 사이트를 사용하여 [MacOS 장치를 등록](/intune-user-help/enroll-your-device-in-intune-macos)할 수 있습니다.

-   **Android 장치** Android 장치를 등록하기 위해 Intune 서비스를 준비하는 데 필요한 작업은 없습니다. 사용자는 Google Play에서 제공되는 회사 포털 앱을 사용하여 관리 기능에 [Android 장치를 등록](/intune-user-help/enroll-your-device-in-intune-android)하기만 하면 됩니다.

-   **Windows Phones 및 PC** 추가 구성을 사용하여 Windows 장치를 등록할 수 있습니다. 사용자 경험을 간소화하기 위해 Azure AD(Active Directory) Premium에서 Windows 10 PC 및 Windows 10 모바일 장치의 자동 등록을 사용할 수 있습니다. Azure AD Premium이 없거나 Windows 8.1을 지원해야 하는 경우 쉽게 등록할 수 있도록 [등록 서버의 DNS 별칭](windows-enroll.md#enable-windows-enrollment-without-azure-ad-premium)을 만들 수 있습니다.


### <a name="make-sure-that-managed-devices-meet-basic-security-requirements"></a>관리되는 장치가 기본 보안 요구 사항을 충족하는지 확인

사용자가 장치를 관리 기능에 등록하면 IT는 회사 앱 및 데이터에 액세스하는 데 사용되는 장치가 기본 보안 요구 사항을 충족하는지 확인해야 합니다. 이러한 규칙에는 장치에 액세스하는 데 PIN을 사용하고 장치에 저장된 데이터를 암호화하는 규칙이 포함됩니다. 이러한 규칙의 집합을 [준수 정책](device-compliance.md)이라고 합니다.

사용자에게 [준수 정책을 배포](device-compliance-get-started.md)하면 Intune은 해당 사용자가 Intune을 통해 관리하는 모든 장치에서 BYOD 정책의 일부로 정의한 기본 보안 요구 사항을 충족하는지 확인합니다. 장치가 정책을 준수하는 것으로 평가되면 해당 상태를 다시 Intune에 보고합니다. 사용자에게 PIN 또는 장치 암호화 같은 설정을 수정하도록 요청하는 경우도 있습니다. 또는 간단히 회사 포털 앱에서 정책에 맞지 않는 설정에 대해 사용자에게 알립니다.

## <a name="provide-access-to-company-resources"></a>회사 리소스에 대한 액세스 권한 제공

대부분 직원들이 모바일 장치에서 원하는 첫 번째 기능은 회사 메일 및 문서에 대한 액세스입니다. 또한 복잡한 단계를 거치거나 지원 센터에 문의하지 않고 설정을 진행할 수 있기 바랍니다. Intune을 사용하면 모바일 장치에 사전 설치되는 기본 메일 앱에 대한 [메일 설정을 쉽게 만들고 배포](email-settings-configure.md)할 수 있습니다.


> [!NOTE]
> Intune에서는 Google Play 스토어에 있는 Gmail 및 Nine Work 메일 앱에 대해 Android for Work 메일 프로필 구성을 지원합니다.

Intune은 사용자가 오프사이트에서 작업하는 경우 온-프레미스 회사 데이터에 대한 액세스를 제어하고 보호하는 데에도 도움이 됩니다. Intune [Wi-Fi](wi-fi-settings-configure.md), [VPN](vpn-settings-configure.md) 및 메일 프로필은 함께 작동하여 사용자가 어디에 있든지 상관없이 정상적인 작업 수행에 필요한 파일 및 리소스에 쉽게 액세스하게 해 줍니다. 온-프레미스에 호스트된 회사의 웹 응용 프로그램 및 서비스도 Azure Active Directory 응용 프로그램 프록시 및 조건부 액세스를 사용하여 안전하게 액세스하고 보호할 수 있습니다.

### <a name="manage-volume-purchased-apps"></a>대량 구매 앱 관리
Intune을 사용하면 다음 작업을 쉽게 수행할 수 있습니다.
* 앱 스토어에서 볼륨 라이선스 정보 가져오기
* 사용한 라이선스 수 추적
* 사용자가 소유한 것보다 많은 앱 복사본을 설치하지 않도록 방지
* [관리되는 장치에 스토어 앱 제공](apps-deploy.md)
* 회사 포털 웹 사이트를 사용하여 관리되지 않는 장치에 앱 제공

Intune을 사용하여 iOS 앱 스토어 및 비즈니스용 Windows 스토어에서 대량으로 구매한 앱도 관리하고 배포할 수 있습니다. 이 덕분에 대량으로 구입한 앱을 추적하는 관리 오버헤드를 줄일 수 있습니다.

> [!TIP]
> [Azure AD Connect를 통해 SSO(Single Sign On)를 구성](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)할 수 있습니다. SSO를 사용하면 사용자가 온-프레미스에서 사용하는 도메인 사용자 이름과 암호로 앱에 로그인할 수 있습니다. 또한 Azure Active Directory 응용 프로그램 프록시를 사용하여 [온-프레미스에 호스트된 웹앱에 대한 인터넷 기반 액세스를 제공](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started)할 수 있습니다.

-   [iOS 장치용 대량 구매 앱 관리](vpp-apps-ios.md). [Apple 비즈니스용 VPP(Volume Purchase Program)](http://www.apple.com/business/vpp/)를 통해 iOS 앱의 라이선스를 여러 개 구매합니다. Apple 웹 사이트에서 Apple VPP 계정을 설정하고 Apple VPP 토큰을 Intune에 업로드해야 합니다. 그런 다음 대량 구매 정보를 Intune과 동기화하고 대량 구매 앱 사용을 추적할 수 있습니다.

-   [비즈니스용 Windows 스토어에서 구매한 앱 관리](windows-store-for-business.md). [비즈니스용 Windows 스토어](https://www.microsoft.com/business-store)는 개별적으로 또는 대량으로 조직에 대한 앱을 찾고 구입할 수 있는 위치를 제공합니다. 스토어를 Intune에 연결하여 Intune 포털에서 대용량 구입 앱을 관리할 수 있습니다.

## <a name="protect-company-data"></a>회사 데이터 보호

Intune은 여러 기술 계층을 통해 회사 데이터를 보호합니다. ID 계층에서 조건부 액세스를 통해 서비스에 대한 액세스를 보호합니다. 조건부 액세스는 관리되는 장치 및 규격 장치만 회사 리소스에 액세스하도록 허용합니다. 클라이언트 응용 프로그램 계층에서는 MAM(모바일 응용 프로그램 관리)이 데이터 손실을 방지합니다.  앱 보호 정책은 보호되지 않는 앱 또는 저장소 위치로 데이터가 이동하는 것을 방지합니다. 이러한 정책을 사용하면 장치를 분실하거나 도난당한 경우 회사 데이터를 초기화할 수도 있습니다.

### <a name="enforce-conditional-access-to-company-resources"></a>회사 리소스에 대한 조건부 액세스 적용

준수 정책을 [조건부 액세스 정책](device-compliance.md)과 결합하여 장치가 BYOD 정책에서 요구하는 기본 보안 요구 사항을 충족하는지 확인할 수 있습니다. 장치가 요구 사항을 충족하지 않는 경우 규칙이 적용되어 장치가 정책 요구 사항을 충족할 때까지 액세스가 거부됩니다. 이 경우 관리되는 준수 장치만 Exchange([Exchange 온-프레미스](exchange-connector-install.md) 또는 [Exchange Online](conditional-access-exchange-create.md)), SharePoint Online, 비즈니스용 Skype Online 등과 같은 서비스에서 회사 데이터에 액세스할 수 있습니다.
<!---first link was (https://docs.microsoft.com/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)
third link was (https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune). check with Andre--->

> [!IMPORTANT]
> 규정 준수 유효성을 검사하기 위한 준수 정책이 없으면 조건부 액세스 정책이 작동되지 않습니다.

### <a name="prevent-data-loss-of-company-data-with-application-protection-policies"></a>응용 프로그램 보호 정책으로 회사 데이터 손실 방지

Intune 응용 프로그램 보호 정책을 사용하면 장치 등록 여부와 관계없이 데이터에 액세스하는 방법을 선택할 수 있습니다. 이러한 유연성을 통해 회사 데이터를 보호할 수 있으므로 사용자가 Intune에 장치를 등록하지 않는 경우에도 안전하게 회사 데이터에 액세스할 수 있습니다.

[Intune 앱 보호 정책](app-protection-policies.md)을 사용하여 사용자의 iOS 및 Android 장치를 통해 액세스되는 회사 데이터를 보호할 수 있습니다. 이러한 앱 수준 정책을 사용하면 장치 자체를 Intune에서 관리하지 않더라도 직원들이 회사 데이터를 사용하고 공유하는 방법을 제어할 수 있습니다.

관리되는 Windows 10 장치의 경우 [WIP(Windows Information Protection) 정책](app-protection-policies-configure-windows-10.md)을 사용하여 동일한 기능을 수행할 수 있습니다. 이러한 정책은 직원 환경을 방해하지 않으면서 작동합니다. 네트워크 환경 또는 다른 앱을 변경할 필요가 없습니다.

### <a name="wipe-company-data-while-leaving-personal-data-intact"></a>개인 데이터를 그대로 두고 회사 데이터 초기화

장치가 더 이상 작업에 필요하지 않거나, 용도 변경 중이거나, 유실된 경우 장치에서 회사 앱과 데이터를 제거할 수 있어야 합니다. 이를 위해, Intune의 선택적 초기화 및 전체 초기화 기능을 사용할 수 있습니다. 사용자의 개인 소유 장치가 Intune에 등록된 경우 사용자가 원격으로 Intune 회사 포털에서 해당 장치를 초기화할 수도 있습니다.

[전체 초기화](devices-wipe.md)는 장치가 출하 시 기본 설정으로 복원되고 사용자 데이터와 설정이 제거됩니다. [선택적 초기화](devices-wipe.md#selective-wipe)는 장치에서 회사 데이터는 제거하지만 사용자의 개인 데이터는 그대로 둡니다.

초기화되면 장치가 즉시 선택적 초기화 프로세스를 시작하여 관리 기능에서 제거됩니다. 프로세스가 완료되면 모든 회사 데이터가 삭제되고 장치 이름이 Intune 포털에서 제거됩니다. 장치 관리 수명 주기가 종료됩니다.
