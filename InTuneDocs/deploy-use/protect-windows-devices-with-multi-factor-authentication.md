---
title: "Windows용 Multi-Factor Authentication | Microsoft Intune"
description: "Intune에서는 회사 리소스를 보호할 수 있는 MFA(Multi-Factor Authentication)를 통합합니다."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 09/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9b4f197d-bc10-4bee-91c9-19bcc8287d36
ms.reviewer: vinaybha
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 1bfd17f9fcc73049254bc77351eae48da874fb4c


---

# <a name="protect-windows-devices-with-multi-factor-authentication"></a>Protect Windows devices with multi-factor authentication
Microsoft Intune에서는 회사 리소스를 보호할 수 있는 MFA(Multi-Factor Authentication)를 통합합니다. MFA를 사용하려면 사용자 이름 및 암호 외에도 텍스트 인증과 같은 인증 요소가 필요합니다. Intune에서는 Windows 8.1 이상, Windows Phone 8.1 또는 Windows 10 Desktop 및 Mobile 장치의 등록 중에 MFA의 사용을 지원합니다.

## <a name="on-premises-infrastructure-requirements-for-adfs-mfa"></a>ADFS MFA에 대한 온-프레미스 인프라 요구 사항
다단계 인증을 설정하려면 다음이 필요합니다.

-   [Windows 장치 관리 설정](set-up-windows-device-management-with-microsoft-intune.md)에 설명된 자동 등록
-   **ADFS 서버가 가입되어 있는 Active Directory 도메인.**

-   **MFA용으로 구성된 ADFS(Active Directory Federation Services) 서버.** Windows Server 2012 R2를 실행 중이고 ADFS 서버로 설치된 서버. 자세한 내용은 [Windows Server 2012 R2 AD FS에서 Azure Multi-Factor Authentication 서버를 사용하여 클라우드 및 온-프레미스 리소스 보호](https://azure.microsoft.com/en-us/documentation/articles/multi-factor-authentication-get-started-adfs-w2k12/)를 참조하세요.

서버가 [시스템 요구 사항 및 Windows Server 2012 R2 설치 정보](http://technet.microsoft.com/library/dn303418.aspx)에 있는 시스템 요구 사항을 충족해야 합니다.

 


#### <a name="mfa-with-intune"></a>Intune이 있는 MFA
조직에 ADFS(Active Directory Federation Services)가 있는 Active Directory 도메인이 포함된 온-프레미스 IT 인프라가 있는 경우 페더레이션 서버에서 MFA를 설정한 다음 MFA를 Intune 등록에 사용하도록 설정할 수 있습니다. Intune에서 MFA를 구성하면 등록하는 동안 사용자를 한 번 인증하도록 설정한 후 MFA 프로세스를 매번 반복하지 않고 회사 리소스를 사용할 수 있습니다.

>[!NOTE]
>MFA는 ADFS 서버에서 사용자 또는 그룹 단위별로 필요할 수 있습니다.  

#### <a name="mfa-without-intune"></a>Intune이 없는 MFA
페더레이션 서버에서 MFA를 설정하지만 Intune에서 등록하는 데 MFA를 사용하지 않을 경우 사용자는 장치 등록뿐만 아니라 회사 리소스에 액세스할 때마다 MFA를 사용해야 합니다.

Azure AD(Azure Active Directory) MFA를 사용하여 사용자가 회사 리소스에 액세스할 때마다 사용자 기준으로 MFA를 요구할 수도 있습니다. Azure AD MFA는 온-프레미스 IT 기반이 필요하지 않은 클라우드 서비스입니다. Azure AD MFA를 설정하는 방법을 알아보려면 [클라우드에서 Azure Multi-Factor Authentication 시작](https://azure.microsoft.com/en-us/documentation/articles/multi-factor-authentication-get-started-cloud/)을 참조하세요.

## <a name="requiring-adfs-mfa-during-enrollment-of-windows-devices"></a>Windows 장치 등록 시 ADFS MFA 요구
ADFS에서 MFA를 사용하도록 설정하는 방법에 대한 자세한 내용은 [중요한 응용 프로그램에 대해 추가 다단계 인증을 사용하여 위험 관리](http://technet.microsoft.com/library/dn280949.aspx)를 참조하세요.

## <a name="set-up-device-enrollment-mfa-in-intune"></a>Intune에서 장치 등록 MFA 설정
>[!Important]  
>Windows 장치의 Intune 등록을 위해 MFA를 요구하려면 먼저 Azure AD 테넌트 또는 온-프레미스 환경에서 MFA를 사용하도록 설정하세요. 그렇지 않으면 사용자가 Windows 장치를 등록하려고 하거나 장치에 대해 Azure AD 조인을 시도할 때 Azure AD 조인 중에 자동 등록이 설정된 경우 오류 메시지가 표시됩니다.

1.  Intune 관리 콘솔에서 **관리** &gt; **모바일 장치 관리** &gt; **다단계 인증**을 선택합니다.

2.  **다단계 인증 구성**과 **다단계 인증 사용**을 차례로 선택합니다.



<!--HONumber=Nov16_HO1-->


