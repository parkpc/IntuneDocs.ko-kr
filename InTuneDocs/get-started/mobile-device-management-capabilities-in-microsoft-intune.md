---
title: "등록된 장치 관리 기능 | Microsoft 문서"
description: "등록된 장치를 관리하는 데 Microsoft Intune이 도움을 주는 방법을 확인하려면 이 항목을 읽어보세요."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/12/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f23b3ee7-78da-4e53-9fc2-78e58401bcf9
ms.reviewer: angrobe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: f268cf29461447306d0f5c3ca06d541d9a03a49d
ms.openlocfilehash: 898975338edcd3267fd47d62d23b35e295f0d99b


---
# <a name="enrolled-device-management-capabilities-of-microsoft-intune"></a>Microsoft Intune의 등록된 장치 관리 기능

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune에서 다양한 장치를 서비스에 *등록*하여 관리할 수 있습니다. 일부 장치 유형은 사용자가 직접 등록하거나, *회사 포털* 앱을 사용하여 등록할 수 있습니다. 회사 포털에서는 앱을 검색하여 설치하고, 해당 장치가 회사 정책을 준수하는지 확인하고, IT 지원에 문의하는 등 다양한 작업을 수행할 수 있습니다.

이 항목에서는 장치 등록 후 제공되는 기능에 대한 전체 목록을 제공합니다.

관리, 재고, 앱 배포, 프로비저닝 및 만료는 모두 Intune 관리 콘솔을 통해 처리됩니다. 사용자가 앱을 설치하고, 장치를 등록 및 제거하고, 해당 IT 부서 또는 기술 지원팀에 문의할 수 있는 회사 포털에 액세스할 수 있습니다.



## <a name="device-security-and-configuration"></a>장치 보안 및 구성

|기능|세부 정보|추가 정보|
|--------------|-----------|--------------------|
|구성 정책<br><br>사용자 지정 정책| 조직의 모바일 장치에서 많은 설정과 기능을 관리할 수 있습니다. 예를 들어 암호를 요구하고, 실패한 시도 횟수를 제한하고, 화면 잠금 전 시간을 제한하고, 암호 만료 시간을 설정하고, 이전에 사용한 암호의 사용을 금지할 수 있습니다. 장치 카메라 또는 웹 브라우저와 같은 하드웨어 및 소프트웨어 기능의 사용을 제어할 수도 있습니다.<br><br>구성 정책에 필요한 설정이 포함되어 있지 않은 경우 사용자 지정 정책을 사용합니다. iOS 장치의 경우 Apple 구성기 도구에서 내보낸 설정을 가져올 수 있습니다. 다른 장치의 경우 OMA-URI(Open Mobile Alliance Uniform Resource Identifier) 설정을 사용하여 장치에서 설정 및 기능을 구성할 수 있습니다.|[Microsoft Intune 정책을 사용하여 장치의 설정 및 기능 관리](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies)<br />|
|원격 초기화, 원격 잠금 및 암호 재설정|장치를 분실하거나 도난당하는 경우 중요한 데이터를 지웁니다. 예를 들어, 원격으로 장치를 잠그거나, 공장 설정으로 복원하거나, 회사 데이터만 삭제할 수 있습니다.<br><br>장치에 액세스하는 방법을 잊어버리거나 분실 또는 도난당한 장치를 잠그거나 분실 또는 도난당한 장치의 데이터를 초기화할 경우 암호를 재설정할 수 있습니다.|[원격 잠금 및 암호 다시 설정으로 장치 보호 지원](/intune/deploy-use/use-remote-lock-and-passcode-reset-in-microsoft-intune) 및 [Intune 관리에서 장치 사용 중지](/intune/deploy-use/retire-devices-from-microsoft-intune-management)|
|키오스크 모드|화면 캡처 및 전원 스위치와 같은 모바일 장치의 특정 기능을 잠글 수 있습니다. 또한 지정한 단일 앱을 실행하도록 장치를 제한할 수 있습니다.|[Microsoft Intune의 iOS 구성 정책 설정](/intune/deploy-use/ios-policy-settings-in-microsoft-intune)|

## <a name="app-management"></a>앱 관리

|기능|세부 정보|추가 정보|
|--------------|-----------|--------------------|
|앱 배포 및 관리|설치 파일 및 앱 스토어를 통한 앱 배포, 자세한 앱 상태 모니터링, 앱 제거 등 수명 주기 동안 모바일 앱을 관리할 수 있는 다양한 도구를 제공합니다.|[Microsoft Intune에서 앱 배포](/intune/deploy-use/deploy-apps)|
|규격 및 비규격 앱|규격 앱(사용자가 설치 가능) 및 비규격 앱(사용자가 설치 불가능) 목록을 지정할 수 있습니다.|[Microsoft Intune의 iOS 정책 설정](/intune/deploy-use/ios-policy-settings-in-microsoft-intune)|
|모바일 응용 프로그램 관리|Intune을 사용하여 관리되거나, Intune으로 관리되지 않는 장치 모두에 대해 모바일 응용 프로그램 관리를 사용하여 앱에 대한 제한을 구성합니다. 이렇게 하면 복사 및 붙여넣기, 데이터의 외부 백업, 앱 간 데이터 전송과 같은 작업을 제한하여 회사 데이터 보안을 강화할 수 있습니다.|[Microsoft Intune 콘솔에서 모바일 응용 프로그램 관리 정책 구성 및 배포](/intune/deploy-use/configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console)<br><br>[Microsoft Intune으로 모바일 앱 관리 정책 만들기 및 배포](/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune)<br /><br />[Microsoft Intune 앱 래핑 도구를 사용하여 모바일 응용 프로그램 관리를 위해 iOS 앱 준비](/intune/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)<br /><br />[Microsoft Intune 앱 래핑 도구를 사용하여 모바일 응용 프로그램 관리용 Android 앱 준비](/intune/deploy-use/prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)|
|iOS 모바일 앱 구성|모바일 앱 구성 정책을 사용하여 사용자가 앱을 실행할 때 필요할 수 있는 iOS 앱에 대한 설정을 제공할 수 있습니다. 예를 들어 앱에서 사용자가 포트 번호 또는 로그온 정보를 지정하도록 요구할 수 있습니다. 이렇게 하면 앱 구성을 능률화하고 지원 요청 횟수를 줄이는 데 도움이 될 수 있습니다.|[Microsoft Intune에서 모바일 앱 구성 정책을 사용하여 iOS 앱 구성](/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)|
|iOS 모바일 앱 프로비전 프로필|곧 만료되는 iOS 앱에 프로비전 프로필을 배포하는 데 도움이 됩니다. |[iOS 모바일 프로비전 프로필 정책을 사용하여 모바일 앱이 만료되지 않도록 방지](/intune/deploy-use/ios-mobile-app-provisioning-profiles)|
|관리되는 브라우저|장치 사용자가 방문할 수 있는 웹 사이트를 제어하도록 관리되는 브라우저 정책을 구성합니다. 또한 관리되는 브라우저에 모바일 응용 프로그램 관리 정책을 적용할 수도 있습니다.|[Microsoft Intune에서 Managed Browser 정책을 사용하여 인터넷 액세스 관리](/intune/deploy-use/manage-internet-access-using-managed-browser-policies)|
|비즈니스용 Windows Hello|온-프레미스 Active Directory를 사용하는 Windows 10 또는 Azure Active Directory에서 암호, 스마트 카드 또는 가상 스마트 카드를 대신하는 로그인 방법인 비즈니스용 Windows Hello를 통합할 수 있습니다.|[Microsoft Intune을 사용하는 장치에서 비즈니스용 Windows Hello 설정 제어](/intune/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune)|
|대량 구매 앱|앱 스토어에서 라이선스 정보를 가져오고, 사용한 라이선스 수를 추적하고, 소유한 라이선스보다 많은 앱을 설치하지 못하도록 차단하는 방식으로 대량 구매 프로그램을 통해 구매한 앱을 관리할 수 있습니다.|[Microsoft Intune을 사용하여 대량 구매 앱 관리](/intune/deploy-use/manage-volume-purchased-apps-in-microsoft-intune)|

## <a name="company-resource-access"></a>회사 리소스 액세스

|기능|세부 정보|추가 정보|
|--------------|-----------|--------------------|
|인증서 프로필|Wi-Fi, VPN 및 전자 메일 프로필을 보호하고 인증하는 데 사용할 수 있는 SCEP(단순 인증서 등록 프로토콜) 인증서와 신뢰할 수 있는 인증서 프로필을 만들고 배포합니다.|[Microsoft Intune에서 인증서 프로필을 통해 리소스 액세스 보안](/intune/deploy-use/secure-resource-access-with-certificate-profiles)|
|Wi-Fi 프로필|사용자에게 무선 네트워크 설정을 배포합니다. 이러한 설정을 배포하여 사용자가 기업 네트워크에 연결하는 데 필요한 노력을 최소화할 수 있습니다.|[Microsoft Intune에서 Wi-Fi 연결](/intune/deploy-use/wi-fi-connections-in-microsoft-intune)|
|전자 메일 프로필|전자 메일 설정을 만들고 장치에 배포합니다. 그러면 사용자가 설정할 필요 없이 개인 장치에서 회사 전자 메일에 액세스할 수 있습니다.|[Microsoft Intune에서 메일 프로필을 사용하여 회사 메일에 대한 액세스 구성](/intune/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune)|
|VPN 프로필|사용자와 조직의 장치에 VPN 설정을 배포합니다. 이러한 설정을 배포하여 사용자가 회사 네트워크에 있는 리소스에 연결하는 데 필요한 노력을 최소화할 수 있습니다.|[Microsoft Intune에서 VPN 연결](/intune/deploy-use/vpn-connections-in-microsoft-intune)|
|조건부 액세스 정책|Intune에서 관리하지 않는 장치의 Microsoft Exchange 전자 메일 및 SharePoint Online에 대한 액세스를 관리합니다.|[Microsoft Intune을 사용한 메일 및 SharePoint 액세스 제한](/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)|

## <a name="inventory-and-reporting"></a>인벤토리 및 보고

|기능|세부 정보|추가 정보|
|--------------|-----------|--------------------|
|인벤토리 및 보고|관리하는 장치와, 장치에서 사용 중인 소프트웨어에 대한 정보를 확인합니다.|[Microsoft Intune에서 인벤토리를 사용하는 장치 이해](/intune/deploy-use/understand-your-devices-with-inventory-in-microsoft-intune)|


### <a name="see-also"></a>참고 항목
[Microsoft Intune의 Windows PC 관리 기능](windows-pc-management-capabilities-in-microsoft-intune.md)



<!--HONumber=Dec16_HO3-->


