---
title: "Microsoft Intune을 사용한 Windows 장치 관리 설정 | Microsoft 문서"
description: "Microsoft Intune으로 Windows 장치에 대한 MDM(모바일 장치 관리)을 사용하도록 설정합니다."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 03/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 771aed4e1c57171183b9a9ea7d9e0f702dc1859c
ms.openlocfilehash: f6014c5500b05762d123b2285ef859d67382e402
ms.lasthandoff: 04/06/2017


---

# <a name="set-up-windows-device-management"></a>Windows 장치 관리 설정

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

다음 방법 중 하나를 사용하여 Windows 장치에 대한 등록을 설정할 수 있습니다.

- [**Azure Active Directory Premium에 Windows 10 자동 등록**](#set-up-windows-10-and-windows-10-mobile-automatic-enrollment-with-azure-active-directory-premium)
 -  이 방법은 Windows 10 장치에서만 사용할 수 있습니다.
 -  이 방법을 사용하려면 Azure Active Directory Premium이 있어야 합니다.
 -  자동 등록을 사용하도록 설정하지 않은 경우 Windows 8.1 및 Windows Phone 8.1에 대한 등록 방법을 사용합니다.

- [**Azure AD Premium 자동 등록을 사용하지 않고 등록**](#enable-windows-enrollment-without-azure-ad-premium)
 - Windows 8.1 및 Windows Phone 8.1 장치를 등록하려면 이 방법을 사용해야 합니다.
 - Azure AD(Active Directory) Premium을 사용하지 않는 경우에는 Windows 8.1 이상 장치에 대해 이 방법을 사용할 수 있습니다.

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="enable-windows-enrollment-without-automatic-enrollment"></a>자동 등록을 사용하지 않고 Windows 등록 사용
사용자가 Azure AD Premium 자동 등록 없이도 장치를 설치 및 등록하도록 할 수 있습니다. 사용자의 계정에 라이선스를 할당하면 사용자는 Windows 장치에 해당 계정을 추가하고 장치를 관리에 등록하는 데 동의할 수 있습니다. DNS CNAME 리소스 레코드를 만들면 사용자가 서버 이름을 입력하지 않고도 Intune에서 연결 및 등록합니다.

**1단계: CNAME 만들기**(선택 사항)<br>
회사의 도메인에 대한 CNAME DNS 리소스 레코드를 만듭니다. 예를 들어, 회사의 웹 사이트가 contoso.com인 경우 DNS에 EnterpriseEnrollment.contoso.com을 enterpriseenrollment-s.manage.microsoft.com으로 리디렉션하는 CNAME을 만듭니다.

CNAME DNS 항목을 만드는 것은 선택 사항이지만 CNAME 레코드를 사용하면 사용자가 보다 쉽게 등록할 수 있습니다. 등록 CNAME 레코드가 없으면 사용자에게 MDM 서버 이름인 enrollment.manage.microsoft.com을 수동으로 입력하라는 메시지가 표시됩니다.

확인된 도메인이 둘 이상 있는 경우 각 도메인에 대해 CNAME 레코드를 만듭니다. CNAME 리소스 레코드에는 다음 정보가 포함되어야 합니다.

CNAME 리소스 레코드에는 다음 정보가 포함되어야 합니다.

|유형|호스트 이름|지시 대상|TTL|
|--------|-------------|-------------|-------|
|CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1시간|
|CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1시간|

`EnterpriseEnrollment-s.manage.microsoft.com` – 메일의 도메인 이름에서 도메인을 인식하여 Intune 서비스로 리디렉션을 지원합니다.

회사에서 사용자 자격 증명에 여러 도메인을 사용하는 경우 각 도메인용으로 CNAME 레코드를 만듭니다.

예를 들어, 회사의 웹 사이트가 contoso.com인 경우 DNS에 EnterpriseEnrollment.contoso.com을 EnterpriseEnrollment-s.manage.microsoft.com으로 리디렉션하는 CNAME을 만듭니다. DNS 레코드 변경 내용이 전파되는 데는 최대 72시간이 걸릴 수 있습니다. DNS 레코드가 전파될 때까지 Intune의 DNS 변경 내용을 확인할 수 없습니다.

**2단계: CNAME 확인**(선택 사항)<br>
[Intune 관리 콘솔](http://manage.microsoft.com)에서 **관리** &gt; **모바일 장치 관리** &gt; **Windows**를 선택합니다. 회사 웹 사이트의 확인된 도메인 URL을 **확인된 도메인 이름 지정** 상자에 입력하고 **자동 검색 테스트**를 선택합니다.

## <a name="tell-users-how-to-enroll-windows-devices"></a>사용자에게 Windows 장치를 등록하는 방법 안내
사용자에게 Windows 장치를 등록하는 방법과 장치가 관리될 때 발생할 수 있는 상황에 대해 알려주어야 합니다.
최종 사용자 등록 지침은 [Intune에서 Windows 장치 등록](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-windows)을 참조하세요. [IT 관리자가 장치에 대해 볼 수 있는 정보](https://docs.microsoft.com/intune/enduser/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows)로 사용자를 보낼 수도 있습니다.

최종 사용자 작업에 대한 자세한 내용은 [Microsoft Intune에서 최종 사용자 환경 관련 리소스](https://docs.microsoft.com/intune/deploy-use/how-to-educate-your-end-users-about-microsoft-intune)를 참조하세요.

### <a name="see-also"></a>참고 항목
[Microsoft Intune에서 장치 등록을 위한 필수 구성 요소](prerequisites-for-enrollment.md)

