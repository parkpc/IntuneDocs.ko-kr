---
# required metadata

title: Microsoft Intune 정책 참조 | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: d27f2739-9791-4aae-a9db-01a4e59ccfe5

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune 정책 참조

장치를 관리하는 데 사용해야 하는 Microsoft Intune 정책을 결정할 수 있도록 이 항목의 정보를 사용합니다.

> [!TIP]
> 정책을 사용하는 방법에 대한 자세한 내용은 [Microsoft Intune 정책을 사용하여 장치의 설정 및 기능 관리](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) 항목을 참조하세요..


## Android 구성 정책

|정책 이름|다음을 수행하려는 경우에 사용|
|---------------|------------------------|
|**사용자 지정 구성(Android 4 이상, Samsung KNOX Standard 4.0 이상)**|장치 기능을 제어하는 데 사용할 수 있는 Wi-Fi 설정과 같은 OMA URI 설정을 배포합니다. 필요한 설정을 구성 정책에서 사용할 수 없는 경우에 유용합니다.<br /><br />자세한 내용은 [Microsoft Intune의 Android 정책 설정](android-policy-settings-in-microsoft-intune.md)을 참조하세요..|
|**메일 프로필(Samsung KNOX Standard 4.0 이상)**|관리되는 장치에서 Exchange ActiveSync 메일 설정을 만들고 배포하고 모니터링합니다. 그러면 사용자가 설정할 필요 없이 개인 장치에서 회사 메일에 액세스할 수 있습니다.<br /><br />자세한 내용은 [Microsoft Intune에서 메일 프로필을 사용하여 회사 메일에 대한 액세스 구성](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md)을 참조하세요..|
|**일반 구성(Android 4 이상, Samsung KNOX Standard 4.0 이상)**|모바일 장치 보안 및 기능 설정을 구성합니다.<br />호환 또는 호환되지 않는 앱을 지정하고 사용되는 경우를 보고합니다.<br />장치를 잠가 특정 기능만 작동하도록 하는(예: 장치에서 하나의 앱만 실행되도록 하거나 볼륨 단추를 사용할 수 없도록 설정함) 키오스크 모드를 구성합니다.<br /><br />자세한 내용은 [Microsoft Intune의 Android 정책 설정](android-policy-settings-in-microsoft-intune.md)을 참조하세요..|
|**PKCS #12(.PFX) 인증서 프로필(Android 4 이상)**|장치 인증서 요청용으로 PFX 설정을 만들어 배포하려면 이 프로필을 사용합니다.<br /><br />자세한 내용은 [Microsoft Intune에서 인증서 프로필을 통해 리소스 액세스 보안](secure-resource-access-with-certificate-profiles.md)을 참조하세요..|
|**SCEP 인증서 프로필(Android 4 이상)**|모바일 장치 인증에 사용하는 신뢰할 수 있는 모바일 장치 인증서와 함께 사용할 수 있는 단순 인증서 등록 프로토콜 인증서를 구성하여 Wi-Fi 및 VPN 프로필을 통해 구성된 네트워크 리소스에 대한 액세스를 허용합니다.<br /><br />자세한 내용은 [Microsoft Intune에서 인증서 프로필을 통해 리소스 액세스 보안](secure-resource-access-with-certificate-profiles.md)을 참조하세요..|
|**신뢰할 수 있는 인증서 프로필(Android 4 이상)**|모바일 장치 인증에 사용할 수 있는 신뢰할 수 있는 모바일 장치 인증서를 구성하여 Wi-Fi 및 VPN 프로필을 통해 구성된 네트워크 리소스에 대한 액세스를 허용합니다.<br /><br />자세한 내용은 [Microsoft Intune에서 인증서 프로필을 통해 리소스 액세스 보안](secure-resource-access-with-certificate-profiles.md)을 참조하세요..|
|**VPN 프로필(Android 4 이상)**|사용자가 모바일 장치에서 회사 네트워크에 안전하게 액세스할 수 있도록 해주는 설정을 구성하고 배포합니다. 이러한 설정을 배포하여 최종 사용자가 회사에 연결하는 데 필요한 노력을 최소화할 수 있습니다.<br /><br />자세한 내용은 [Microsoft Intune.md에서 VPN 연결](vpn-connections-in-microsoft-intune.md)를 참조하세요..|
|**Wi-Fi 프로필(Android 4 이상)**|무선 네트워크 설정을 구성하고 조직의 사용자에게 배포합니다. 이러한 설정을 배포하여 최종 사용자가 무선 네트워크에 연결하는 데 필요한 노력을 최소화할 수 있습니다.<br /><br />자세한 내용은 [Microsoft Intune에서 Wi-Fi 연결](wi-fi-connections-in-microsoft-intune.md)를 참조하세요..|

## iOS 구성 정책

|정책 이름|다음을 수행하려는 경우에 사용|
|---------------|------------------------|
|**사용자 지정 구성(iOS 7.1 이상)**|Apple Configurator 도구를 사용하여 만든 구성 프로필을 iOS 장치에 배포합니다. 필요한 설정을 구성 정책에서 사용할 수 없는 경우에 유용합니다.<br /><br />자세한 내용은 [Microsoft Intune의 iOS 정책 설정](ios-policy-settings-in-microsoft-intune.md)을 참조하세요..|
|**메일 프로필(iOS 7.1 이상)**|관리되는 장치에서 Exchange ActiveSync 메일 설정을 만들고 배포하고 모니터링합니다. 그러면 사용자가 설정할 필요 없이 개인 장치에서 회사 메일에 액세스할 수 있습니다.<br /><br />자세한 내용은 [Microsoft Intune에서 메일 프로필을 사용하여 회사 메일에 대한 액세스 구성](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md)을 참조하세요..|
|**일반 구성(iOS 7.1 이상)**|모바일 장치 보안 및 기능 설정을 구성합니다.<br />-   호환 또는 호환되지 않는 앱을 지정하고 사용되는 경우를 보고합니다.<br />장치를 잠가 특정 기능만 작동하도록 하는(예: 장치에서 하나의 앱만 실행되도록 하거나 볼륨 단추를 사용할 수 없도록 설정함) 키오스크 모드를 구성합니다.<br /><br />자세한 내용은 [Microsoft Intune의 iOS 정책 설정](ios-policy-settings-in-microsoft-intune.md)을 참조하세요..|
|**SCEP 인증서 프로필(iOS 7.1 이상)**|모바일 장치 인증에 사용하는 신뢰할 수 있는 모바일 장치 인증서와 함께 사용할 수 있는 단순 인증서 등록 프로토콜 인증서를 구성하여 Wi-Fi 및 VPN 프로필을 통해 구성된 네트워크 리소스에 대한 액세스를 허용합니다.<br /><br />자세한 내용은 [Microsoft Intune에서 인증서 프로필을 통해 리소스 액세스 보안](secure-resource-access-with-certificate-profiles.md)을 참조하세요..|
|**신뢰할 수 있는 인증서 프로필(iOS 7.1 이상)**|모바일 장치 인증에 사용할 수 있는 신뢰할 수 있는 모바일 장치 인증서를 구성하여 Wi-Fi 및 VPN 프로필을 통해 구성된 네트워크 리소스에 대한 액세스를 허용합니다.<br /><br />자세한 내용은 [Microsoft Intune에서 인증서 프로필을 통해 리소스 액세스 보안](secure-resource-access-with-certificate-profiles.md)을 참조하세요..|
|**VPN 프로필(iOS 7.1 이상)**|사용자가 모바일 장치에서 회사 네트워크에 안전하게 액세스할 수 있도록 해주는 설정을 구성하고 배포합니다. 이러한 설정을 배포하여 최종 사용자가 회사에 연결하는 데 필요한 노력을 최소화할 수 있습니다.<br /><br />자세한 내용은 [Microsoft Intune.md에서 VPN 연결](vpn-connections-in-microsoft-intune.md)를 참조하세요..|
|**Wi-Fi 프로필(iOS 7.1 이상)**|무선 네트워크 설정을 구성하고 조직의 사용자에게 배포합니다. 이러한 설정을 배포하여 최종 사용자가 무선 네트워크에 연결하는 데 필요한 노력을 최소화할 수 있습니다.<br /><br />자세한 내용은 [Microsoft Intune에서 Wi-Fi 연결](wi-fi-connections-in-microsoft-intune.md)를 참조하세요..|
|**모바일 앱 구성 정책(iOS 7.1 이상)**|모바일 앱 구성 정책을 사용하여 사용자가 iOS 앱을 실행할 때 필요할 수 있는 설정을 자동으로 제공할 수 있습니다.<br /><br />자세한 내용은 [Microsoft Intune에서 모바일 앱 구성 정책을 사용하여 iOS 앱 구성](configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune.md)을 참조하세요..|

## Mac OS X 구성 정책

|정책 이름|다음을 수행하려는 경우에 사용|
|---------------|------------------------|
|**사용자 지정 구성(Mac OS X 10.9 이상)**|Apple Configurator 도구를 사용하여 만든 구성 프로필을 Mac 컴퓨터에 배포합니다. 필요한 설정을 구성 정책에서 사용할 수 없는 경우에 유용합니다.<br /><br />자세한 내용은 [Microsoft Intune의 Mac OS X 정책 설정](mac-os-x-policy-settings-in-microsoft-intune.md)을 참조하세요..|
|**일반 구성(Mac OS X 10.9 이상)**|모바일 장치 보안 및 기능 설정을 구성합니다.<br />호환 또는 호환되지 않는 앱을 지정하고 사용되는 경우를 보고합니다.<br /><br />자세한 내용은 [Microsoft Intune의 Mac OS X 정책 설정](mac-os-x-policy-settings-in-microsoft-intune.md)을 참조하세요..|
|**SCEP 인증서 프로필(Mac OS X 10.9 이상)**|모바일 장치 인증에 사용하는 신뢰할 수 있는 모바일 장치 인증서와 함께 사용할 수 있는 단순 인증서 등록 프로토콜 인증서를 구성하여 Wi-Fi 및 VPN 프로필을 통해 구성된 네트워크 리소스에 대한 액세스를 허용합니다.<br /><br />자세한 내용은 [Microsoft Intune에서 인증서 프로필을 통해 리소스 액세스 보안](secure-resource-access-with-certificate-profiles.md)을 참조하세요..|
|**신뢰할 수 있는 인증서 프로필(Mac OS X 10.9 이상)**|모바일 장치 인증에 사용할 수 있는 신뢰할 수 있는 모바일 장치 인증서를 구성하여 Wi-Fi 및 VPN 프로필을 통해 구성된 네트워크 리소스에 대한 액세스를 허용합니다.<br /><br />자세한 내용은 [Microsoft Intune에서 인증서 프로필을 통해 리소스 액세스 보안](secure-resource-access-with-certificate-profiles.md)을 참조하세요..|
|**VPN 프로필(Mac OS X 10.9 이상)**|사용자가 모바일 장치에서 회사 네트워크에 안전하게 액세스할 수 있도록 해주는 설정을 구성하고 배포합니다. 이러한 설정을 배포하여 최종 사용자가 회사에 연결하는 데 필요한 노력을 최소화할 수 있습니다.<br /><br />자세한 내용은 [Microsoft Intune.md에서 VPN 연결](vpn-connections-in-microsoft-intune.md)를 참조하세요..|
|**Wi-Fi 프로필(Mac OS X 10.9 이상)**|무선 네트워크 설정을 구성하고 조직의 사용자에게 배포합니다. 이러한 설정을 배포하여 최종 사용자가 무선 네트워크에 연결하는 데 필요한 노력을 최소화할 수 있습니다.<br /><br />자세한 내용은 [Microsoft Intune에서 Wi-Fi 연결](wi-fi-connections-in-microsoft-intune.md)를 참조하세요..|

## Windows 구성 정책
Windows Phone 및 등록된 Windows 장치에만 적용됩니다.

|정책 이름|다음을 수행하려는 경우에 사용|
|---------------|------------------------|
|**사용자 지정 구성(Windows 10 Desktop 및 Mobile 이상)**|장치 기능을 제어하는데 사용할 수 있는 OMA-URI 설정을 배포합니다. 필요한 설정을 구성 정책에서 사용할 수 없는 경우에 유용합니다.<br />    자세한 내용은 [Microsoft Intune의 Windows 10 정책 설정](windows-10-policy-settings-in-microsoft-intune.md)을 참조하세요..|
|**사용자 지정 구성(Windows Phone 8.1 이상)**|장치 기능을 제어하는데 사용할 수 있는 OMA-URI 설정을 배포합니다. 필요한 설정을 구성 정책에서 사용할 수 없는 경우에 유용합니다.<br /><br />자세한 내용은 [Microsoft Intune의 Windows Phone 8.1 설정](windows-phone-8-1-policy-settings-in-microsoft-intune.md)을 참조하세요..|
|**버전 업그레이드 정책(Windows 10 Desktop 이상)**<br><br>**버전 업그레이드 정책(Windows 10 Holographic 이상)**|Windows 10 장치를 최신 버전으로 업데이트하는 데 사용되는 라이선스 또는 제품 키 정보가 포함된 정책을 구성 및 배포합니다.<br><br>자세한 내용은 [Microsoft Intune의 버전 업그레이드 정책 설정](edition-upgrade-policy-settings-in-microsoft-intune.md)을 참조하세요..|  
|**메일 프로필(Windows Phone 8 이상)**<br /><br />**메일 프로필(Windows 10 Desktop 및 Mobile 이상)**|관리되는 장치에서 Exchange ActiveSync 메일 설정을 만들고 배포하고 모니터링합니다. 그러면 사용자가 설정할 필요 없이 개인 장치에서 회사 메일에 액세스할 수 있습니다.<br /><br />자세한 내용은 [Microsoft Intune에서 메일 프로필을 사용하여 회사 메일에 대한 액세스 구성](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md)을 참조하세요..|
|**일반 구성(Windows 10 Desktop 및 Mobile 이상)**|등록된 Windows 10 Desktop 및 Mobile 장치에 대한 모바일 장치 보안 및 기능 설정을 구성합니다.<br /><br />자세한 내용은 [Microsoft Intune의 Windows 10 정책 설정](windows-10-policy-settings-in-microsoft-intune.md)을 참조하세요..|
|**일반 구성(Windows 10 Team 이상)**|등록된 Windows 10 Team 장치(예: Surface Hub 장치)에 대한 장치 보안 및 기능 설정을 구성합니다.<br /><br />자세한 내용은 [Microsoft Intune의 Windows 팀 구성 정책 설정](windows-team-configuration-policy-settings-in-microsoft-intune.md)을 참조하세요..|
|**일반 구성(Windows 8.1 이상)**|모바일 장치 보안 및 등록된 Windows 장치의 기능 설정을 구성합니다.<br /><br />자세한 내용은 [Microsoft Intune의 Windows 정책 설정](windows-configuration-policy-settings-in-microsoft-intune.md)을 참조하세요..|
|**일반 구성(Windows Phone 8.1 이상)**|모바일 장치 보안 및 기능 설정을 구성합니다.<br />사용자가 사용할 수 있거나 사용할 수 없는 앱을 지정하고, 비규격 앱을 설치하거나 사용하지 않도록 차단합니다.<br /><br />자세한 내용은 [Microsoft Intune의 Windows Phone 8.1 설정](windows-phone-8-1-policy-settings-in-microsoft-intune.md)을 참조하세요..|
|**PKCS #12(.PFX) 인증서 프로필(Windows 10 Desktop 및 Mobile 이상)**|장치 인증서 요청용으로 PFX 설정을 만들어 배포하려면 이 프로필을 사용합니다.<br /><br />자세한 내용은 [Microsoft Intune에서 인증서 프로필을 통해 리소스 액세스 보안](secure-resource-access-with-certificate-profiles.md)을 참조하세요..|
|**SCEP 인증서 프로필(Windows 8.1 이상)**<br /><br />**SCEP 인증서 프로필(Windows Phone 8.1 이상)**|모바일 장치 인증에 사용하는 신뢰할 수 있는 모바일 장치 인증서와 함께 사용할 수 있는 단순 인증서 등록 프로토콜 인증서를 구성하여 Wi-Fi 및 VPN 프로필을 통해 구성된 네트워크 리소스에 대한 액세스를 허용합니다.<br /><br />자세한 내용은 [Microsoft Intune에서 인증서 프로필을 통해 리소스 액세스 보안](secure-resource-access-with-certificate-profiles.md)을 참조하세요..|
|**신뢰할 수 있는 인증서 프로필(Windows 8.1 이상)**<br /><br />**신뢰할 수 있는 인증서 프로필(Windows Phone 8.1 이상)**|모바일 장치 인증에 사용할 수 있는 신뢰할 수 있는 모바일 장치 인증서를 구성하여 Wi-Fi 및 VPN 프로필을 통해 구성된 네트워크 리소스에 대한 액세스를 허용합니다.<br /><br />자세한 내용은 [Microsoft Intune에서 인증서 프로필을 통해 리소스 액세스 보안](secure-resource-access-with-certificate-profiles.md)을 참조하세요.).|
|**VPN 프로필(Windows 10 Desktop 및 Mobile 이상)**<br /><br />**VPN 프로필(Windows 8.1 이상)**<br /><br />**VPN 프로필(Windows Phone 8.1 이상)**|사용자가 모바일 장치에서 회사 네트워크에 안전하게 액세스할 수 있도록 해주는 설정을 구성하고 배포합니다. 이러한 설정을 배포하여 최종 사용자가 회사에 연결하는 데 필요한 노력을 최소화할 수 있습니다.<br /><br />자세한 내용은 [Microsoft Intune.md에서 VPN 연결](vpn-connections-in-microsoft-intune.md)를 참조하세요..|
|**Wi-Fi 가져오기**|이전에 파일로 내보낸 Windows Wi-Fi 구성을 가져와서 배포합니다.<br /><br />자세한 내용은 [Microsoft Intune에서 Wi-Fi 연결](wi-fi-connections-in-microsoft-intune.md)를 참조하세요..|

## 소프트웨어 정책

|정책 이름|다음을 수행하려는 경우에 사용|
|---------------|------------------------|
|**관리되는 브라우저 정책(Android 4 이상)**<br /><br />**Managed Browser 정책(iOS 7.1 이상)**|사용자가 관리되는 브라우저 앱을 사용할 때 액세스할 수 있는 웹 사이트 및 액세스할 수 없는 웹 사이트를 지정합니다.<br /><br />자세한 내용은 [Microsoft Intune에서 Managed Browser 정책을 사용하여 인터넷 액세스 관리](manage-internet-access-using-managed-browser-policies.md)를 참조하세요..|
|**모바일 응용 프로그램 관리 정책(Android 4 이상)**<br /><br />**모바일 응용 프로그램 관리 정책(iOS 7.1 이상)**|회사 규정 준수 및 보안 정책에 맞도록 배포하는 앱의 기능을 수정합니다. 예를 들어, 제한된 앱으로 잘라내기, 복사 및 붙여넣기 작업을 제한하거나, 관리되는 브라우저 내에서 모든 웹 링크를 열도록 앱을 구성할 수 있습니다.<br /><br />자세한 내용은 [Microsoft Intune 콘솔에서 모바일 응용 프로그램 관리 정책 구성 및 배포](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md)를 참조하세요.|

## 공용 모바일 장치 설정

|정책 이름|다음을 수행하려는 경우에 사용|
|---------------|------------------------|
|**Exchange ActiveSync 정책**|모바일 장치 보안 및 Exchange ActiveSync에서 관리되는 장치에 대한 기능 설정을 구성합니다.<br /><br />자세한 내용은 [Microsoft Intune의 Exchange ActiveSync 정책 설정](exchange-activesync-policy-settings-in-microsoft-intune.md)을 참조하세요..|
|**모바일 장치 보안 정책**|<ul><li>다음을 포함한 모바일 장치(모든 플랫폼)에 대한 설정을 구성합니다.<br /><br /><ul><li>보안</li><li>암호화</li><li>시스템</li><li>메일</li><li>응용 프로그램</li></ul></li></ul> **중요:** 이제 Microsoft Intune에서는 각 장치 플랫폼에 대해 개별 **구성 정책**을 사용하며 이러한 정책에는 사용할 수 있는 가장 최신 설정이 포함되어 있습니다. 모바일 장치 보안 정책을 계속해서 사용할 수 있으며 기존 배포가 계속 작동하지만, 새 구성 정책으로 최대한 빨리 마이그레이션하는 계획을 세워야 합니다.<br />자세한 내용은 [Microsoft Intune의 모바일 장치 보안 정책 설정](mobile-device-security-policy-settings-in-microsoft-intune.md)을 참조하세요..|

## 조건부 액세스 및 규정 준수 정책

### 조건부 액세스

|정책 이름|다음을 수행하려는 경우에 사용|
|---------------|------------------------|
|**Exchange Online 정책**<br /><br />**Exchange 온-프레미스 정책**|Intune을 통해 관리되지 않거나 사용자가 만든 준수 정책을 준수하지 않는 장치의 Microsoft Exchange 메일 액세스를 관리합니다.<br /><br />자세한 내용은 [Intune을 사용하여 Exchange Online 및 새 Exchange Online Dedicated 환경에 대한 메일 액세스 제한](restrict-access-to-exchange-online-with-microsoft-intune.md)을 참조하세요..|
|**SharePoint Online 정책**|Intune에서 관리하지 않거나 사용자가 만든 준수 정책을 준수하지 않는 장치의 SharePoint Online 액세스를 관리합니다.<br /><br />자세한 내용은 [Microsoft Intune을 사용하여 SharePoint Online에 대한 액세스 제한](restrict-access-to-sharepoint-online-with-microsoft-intune.md)을 참조하세요..|
|**비즈니스용 Skype**|Intune에서 관리하지 않거나 사용자가 만든 준수 정책을 준수하지 않는 장치의 비즈니스용 Skype 액세스를 관리합니다.<br /><br />자세한 내용은 [Microsoft Intune을 사용하여 비즈니스용 Skype에 대한 액세스 제한](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)을 참조하세요..|
> [!NOTE]
> 사용자 및 장치에는 조건부 액세스 정책을 배포하지 마세요. 대신, 필요한 정책을 구성하면 정책의 대상인 모든 그룹에 적용됩니다.

### 규정 준수 정책

|정책 이름|다음을 수행하려는 경우에 사용|
|---------------|------------------------|
|**규정 준수 정책**|장치의 준수 수준을 정의한 다음 준수하지 않는 장치에 대해 보고합니다. 이러한 정책은 서비스에서 차단해야 하는 장치를 평가할 수 있도록 조건부 액세스와 함께 사용됩니다.<br /><br />자세한 내용은 [Microsoft Intune의 장치 준수 정책](introduction-to-device-compliance-policies-in-microsoft-intune.md)을 참조하세요..|

## Windows PC 관리

|정책 이름|다음을 수행하려는 경우에 사용|
|---------------|------------------------|
|**Microsoft Intune 에이전트 설정**|다음에 대한 설정을 포함하여 컴퓨터에서 Intune PC 클라이언트를 구성합니다.<br /><br />-   Endpoint Protection<br />-   소프트웨어 업데이트<br />-   정책 확인 일정<br /><br />이 유형의 정책은 장치 그룹에만 배포할 수 있습니다.<br /><br />Intune 클라이언트는 **업데이트 및 응용 프로그램 검색 주기** 설정(기본값은 8시간으로 설정)에 따라 새로운 정책 및 업데이트된 정책을 다운로드합니다. 그러나 언제든지 컴퓨터에서 정책을 강제로 새로 고칠 수 있습니다.<br /><br />자세한 내용은 [Microsoft Intune에서 소프트웨어 업데이트를 사용하여 Windows PC를 최신 상태로 유지](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md)를 참조하세요..|
|**Microsoft Intune Center 설정**|관리되는 컴퓨터의 Microsoft Intune 센터에 표시되는 세부 정보를 구성합니다.<br /><br />이 유형의 정책은 장치 그룹에만 배포할 수 있습니다.<br /><br />자세한 내용은 [Microsoft Intune 컴퓨터 클라이언트를 사용한 일반 Windows PC 관리 작업](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)을 참조하세요..|
|**Windows 방화벽 설정**|컴퓨터에서 다음을 포함한 공용 네트워크 통신에 대해 Windows 방화벽 정책 및 예외를 구성합니다.<br /><br />-   BranchCache<br />-   원격 지원<br />-   미디어 공유<br /><br />이 유형의 정책은 장치 그룹에만 배포할 수 있습니다.<br /><br />자세한 내용은 [Microsoft Intune용 Endpoint Protection을 사용한 Windows PC의 보안 유지 방법](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md)을 참조하세요..|

### 참고 항목

[Microsoft Intune 정책을 사용하여 장치의 설정 및 기능 관리](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=May16_HO1-->


