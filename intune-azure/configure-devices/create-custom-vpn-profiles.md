---
title: "Microsoft Intune을 사용하여 사용자 지정 VPN 프로필을 만드는 방법 | Microsoft 문서"
description: "사용자 지정 구성을 사용하여 Intune에서 VPN 프로필을 만듭니다."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4c0bd439-3b58-420b-9a9a-282886986786
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: 968932c07d2c68003b61c0cc554b43b348385d1e
ms.lasthandoff: 02/16/2017


---

# <a name="how-to-create-custom-vpn-profiles-in-microsoft-intune"></a>Microsoft Intune에서 사용자 지정 VPN 프로필을 만드는 방법

## <a name="create-a-custom-configuration"></a>사용자 지정 구성 만들기
사용자 지정 구성 정책을 사용하여 다음에 대한 VPN 프로필을 만들 수 있습니다.

* Android 4 이상을 실행하는 장치
* Windows 8.1 이상을 실행하는 등록된 장치
* Windows Phone 8.1 이상을 실행하는 장치
* Windows 10 데스크톱 이상을 실행하는 등록된 장치 
* Windows 10 Mobile을 실행하는 장치

표준 Intune VPN 정책에 사용하려는 설정이 없는 경우 이 유형의 정책이 유용할 수 있습니다.

## <a name="to-create-a-custom-configuration-policy"></a>사용자 지정 구성 정책을 만들려면

1. Azure 포털에 로그인합니다.
2. **추가 서비스** > **기타** > **Intune**을 선택합니다.
3. **Intune** 블레이드에서 **장치 구성**을 선택합니다.
4. **장치 구성** 블레이드에서 **관리** > **프로필**을 선택합니다.
5. 프로필 블레이드에서 **프로필 만들기**를 선택합니다.
6. **프로필 만들기** 블레이드에서 VPN 프로필에 대한 **이름** 및 **설명**을 입력합니다.
7. **플랫폼** 드롭다운 목록에서 VPN 설정을 적용할 장치 플랫폼을 선택합니다. 현재 사용자 지정 장치 설정에 대해 다음 플랫폼 중 하나를 선택할 수 있습니다.
    - **OWA(Outlook Web Access)**
    - **iOS**(Apple Configurator에서 내보낸 파일을 사용하여 구성).
    - **macOS**(Apple Configurator에서 내보낸 파일을 사용하여 구성).
    - **Windows Phone 8.1**
    - **Windows 10 이상**
6. **프로필** 유형 드롭다운 목록에서 선택 **사용자 지정**을 선택합니다.
7. **사용자 지정 OMA-URI 설정** 블레이드에서 지정할 각 URI 설정에 대해 **추가**를 선택하고 요청된 정보를 제공한 다음 **확인**을 선택합니다. 아래 예를 살펴보세요.

   ![VPN 프로필 사용자 지정 구성 대화 상자](./media/Intune_Add_VPN_URI.png)

4.  필요한 URI 설정을 모두 입력한 후 **확인**을 선택하고 **프로필 만들기** 블레이드에서 **만들기**를 선택합니다.

프로필이 만들어지고 프로필 목록 블레이드에 표시됩니다.
계속해서 이 프로필을 그룹에 할당하려면 [장치 프로필을 할당하는 방법](how-to-assign-device-profiles.md)을 참조하세요.

## <a name="example-uri-settings"></a>URI 설정 예

이러한 설정은 Contoso라는 가상의 회사에서 VPN에 대한 사용자 지정 구성을 만드는 데 사용할 수 있습니다.
사용할 수 있는 모든 설정이 대한 자세한 내용은 [VPNv2 CSP](https://msdn.microsoft.com/en-us/library/windows/hardware/dn914776.aspx)를 참조하세요.

기본 Contoso VPN(IKEv2): ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Servers

vpn.contoso.com ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/NativeProtocolType

Ikev2 ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/RoutingPolicyType

SplitTunnel ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/UserMethod

Eap ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/Eap/Configuration &lt;EapHostConfig xmlns="http://www.microsoft.com/provisioning/EapHostConfig"&gt;&lt;EapMethod&gt;&lt;Type xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;13&lt;/Type&gt;&lt;VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;0&lt;/VendorId&gt;&lt;VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;0&lt;/VendorType&gt;&lt;AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;0&lt;/AuthorId&gt;&lt;/EapMethod&gt;&lt;Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig"&gt;&lt;Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1"&gt;&lt;Type&gt;13&lt;/Type&gt;&lt;EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1"&gt;&lt;CredentialsSource&gt;&lt;CertificateStore&gt;&lt;SimpleCertSelection&gt;true&lt;/SimpleCertSelection&gt;&lt;/CertificateStore&gt;&lt;/CredentialsSource&gt;&lt;ServerValidation&gt;&lt;DisableUserPromptForServerValidation&gt;false&lt;/DisableUserPromptForServerValidation&gt;&lt;ServerNames&gt;&lt;/ServerNames&gt;&lt;/ServerValidation&gt;&lt;DifferentUsername&gt;false&lt;/DifferentUsername&gt;&lt;PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2"&gt;false&lt;/PerformServerValidation&gt;&lt;AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2"&gt;false&lt;/AcceptServerName&gt;&lt;/EapType&gt;&lt;/Eap&gt;&lt;/Config&gt;&lt;/EapHostConfig&gt;

**./Vendor/MSFT/VPNv2/ContosoVPN/ByPassForLocal** True

**./Vendor/MSFT/VPNv2/ContosoVPN/RememberCredentials** 1

**./Vendor/MSFT/VPNv2/ContosoVPN/DomainNameInformationList/1/DomainName** Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/DnsSuffix** Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/TrustedNetworkDetection** Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/Address** 10.0.0.0

**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/PrefixSize** 8

**./Vendor/MSFT/VPNv2/ContosoVPN/AlwaysOn** true

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/0/App/Id** %PROGRAMFILES%\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/1/App/Id** %PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/2/App/Id** Microsoft.MicrosoftEdge_8wekyb3d8bbwe

**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/0/App/Id** %PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/1/App/Id** Microsoft.MicrosoftEdge_8wekyb3d8bbwe

이러한 설정을 어떻게 사용해야 할지에 대한 질문 또는 사용하는 내용에 대한 자세한 내용은 고객이 CSP(구성 서비스 공급자) 설명서(https://msdn.microsoft.com/en-us/library/windows/hardware/dn914776(v=vs.85).aspx)를 참조해야 합니다.

## <a name="uri-settings-for-android-per-app-vpn-on-pulsesecure"></a>PulseSecure에서 Android 앱별 VPN에 대한 URI 설정
### <a name="custom-uri-for-package-list"></a>패키지 목록에 대한 사용자 지정 URI
-  데이터 형식 = 문자열
-  OMA-URI = ./Vendor/MSFT/VPN/Profile/Name/PackageList
-  값 = 구분 기호로 구분된 패키지 목록.
   - 구분 기호: 세미콜론(;), 콜론(:), 쉼표(,), 파이프(|)

예:
- com.android.chrome
- com.android.chrome;com.android.browser

### <a name="custom-uri-for-mode-optional"></a>모드에 대한 사용자 지정 URI(선택 사항)
- 데이터 형식 = 문자열
- OMA-URI = ./Vendor/MSFT/VPN/Profile/NAME/Mode

> 참고
> - 사용자 지정 프로필에 할당한 동일한 *이름* 사용
> - 가능한 값: *전역*, *화이트 리스트*, *블랙 리스트*
> - PackageList를 제공하지 않는 경우 *전역*에 대한 기본값(시스템 차원의 프로필이 있는 이전 버전과 호환성)
> - PackageList에서 제공하는 경우 *화이트 리스트*에 대한 기본값




