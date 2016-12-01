---
title: "VPN 프로필에 대한 사용자 지정 구성 | Microsoft Intune"
description: "사용자 지정 구성을 사용하여 Intune에서 VPN 프로필을 만듭니다."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 11/06/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4c0bd439-3b58-420b-9a9a-282886986786
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: fb3b6cccaa3e62be3a7271ae6a67e76f8cf8d858
ms.openlocfilehash: a1c7648a4ee4ab91e00f5305a8124a07570824fc


---

# <a name="custom-configurations-for-vpn-profiles"></a>VPN 프로필에 대한 사용자 지정 구성

## <a name="create-a-custom-configuration"></a>사용자 지정 구성 만들기
사용자 지정 구성을 사용하여 Intune에서 다음에 대한 VPN 프로필을 만들 수 있습니다.

* Android 4 이상을 실행하는 장치
* Android for Work 장치
* Windows 8.1 이상을 실행하는 등록된 장치
* Windows Phone 8.1 이상을 실행하는 장치
* Windows 10 Desktop 및 Mobile을 실행하는 장치

사용자 지정 구성을 만들려면:

   1. Intune 관리 콘솔에서 **정책** > **정책 추가** > *플랫폼 확장* > **사용자 지정 구성** > **정책 만들기**를 선택합니다.
   2. 정책의 이름을 제공합니다.
   3. 각 URI 설정에서 **추가**를 선택하고 요청된 정보를 제공합니다. 아래 예를 살펴보세요.

   ![VPN 프로필 사용자 지정 구성 대화 상자](./media/Intune_Add_VPN_URI.png)

   4.  URI 설정을 모두 입력한 후에 **정책 저장**을 선택한 다음 정책을 배포합니다.

## <a name="deploy-a-configuration-policy"></a>구성 정책 배포

1.  **정책** 작업 영역에서 배포할 정책을 선택한 다음 **배포 관리**를 클릭합니다.

2.   **배포 관리** 대화 상자에서

    -   **정책을 배포하려면** 정책을 배포하려는 그룹을 하나 이상 선택하고 **추가** &gt;**확인**을 클릭합니다.

    -   **정책을 배포하지 않고 대화 상자를 닫으려면** - **취소**를 선택합니다.

배포한 정책을 선택하면 정책 목록 아래쪽에서 배포에 대한 추가 정보를 볼 수 있습니다.

##<a name="example-of-uri-settings-for-a-custom-vpn-profile-configuration"></a>사용자 지정 VPN 프로필 구성에 대한 URI 설정의 예
다음은 Contoso라는 가상의 회사에서 VPN에 대한 사용자 지정 구성을 만드는한 URI 값에 대한 예제 항목입니다. 각 항목에 대한 데이터 형식과 같은 자세한 정보는 [VPNv2 CSP](https://msdn.microsoft.com/en-us/library/windows/hardware/dn914776.aspx)를 참조하세요.

네이티브 Contoso VPN(IKEv2): ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Servers

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

## <a name="uri-settings-for-android-perapp-vpn-on-pulsesecure"></a>PulseSecure에서 Android 앱별 VPN에 대한 URI 설정
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


### <a name="see-also"></a>참고 항목
(Microsoft Intune에서 VPN 연결)[vpn-connections-in-microsoft-intune.md]



<!--HONumber=Nov16_HO1-->


