---
title: "Microsoft Intune을 사용한 Windows 장치 관리 설정 | Microsoft 문서"
description: "Microsoft Intune으로 Windows 장치에 대한 MDM(모바일 장치 관리)을 사용하도록 설정합니다."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 02/26/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 255c3e47464ac7670a971881cf399e8e2bb17044
ms.openlocfilehash: 4acbae2aba4cff21286d45cb7cb1691864c281dc
ms.lasthandoff: 02/28/2017


---

# <a name="set-up-windows-device-management"></a>Windows 장치 관리 설정

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

다음 방법 중 하나를 사용하여 Windows 장치에 대한 등록을 설정할 수 있습니다.

- [**Azure Active Directory Premium에 Windows 10 및 Windows 10 Mobile 자동 등록**](#set-up-windows-10-and-windows-10-mobile-automatic-enrollment-with-azure-active-directory-premium)
 -  이 방법은 Windows 10 및 Windows 10 Mobile 장치에만 적용됩니다.
 -  이 방법을 사용하려면 Azure Active Directory Premium이 있어야 합니다. 그렇지 않은 경우 Windows 8.1 및 Windows Phone 8.1에 대한 등록 방법을 사용하세요.
 -  자동 등록을 사용하도록 설정하지 않은 경우 Windows 8.1 및 Windows Phone 8.1에 대한 등록 방법을 사용합니다.


- [**CNAME을 구성하여 Windows 8.1 및 Windows Phone 8.1 등록**](#set-up-windows-81-and-windows-phone-81-enrollment-by-configuring-cname)
 - Windows 8.1 및 Windows Phone 8.1 장치를 등록하려면 이 방법을 사용해야 합니다.

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="set-up-windows-81-and-windows-phone-81-enrollment-by-configuring-cname"></a>CNAME을 구성하여 Windows 8.1 및 Windows Phone 8.1 등록 설정
사용자가 Intune 회사 포털을 사용하여 장치를 설치하고 등록하도록 할 수 있습니다. DNS CNAME 리소스 레코드를 만들면 사용자가 서버 이름을 입력하지 않고도 Intune에서 연결 및 등록합니다.

### <a name="step-1-set-up-intune"></a>1단계: Intune 설정

MDM(모바일 장치 관리)을 아직 준비하지 않은 경우 [모바일 장치 관리 기관](prerequisites-for-enrollment.md#step-2-set-mdm-authority)을 **Microsoft Intune**으로 설정하고 MDM을 설정하여 관리를 준비합니다.

### <a name="step-2-create-cnames-optional"></a>2단계: CNAME 만들기(선택 사항)

회사의 도메인에 대한 **CNAME** DNS 리소스 레코드를 만들어야 합니다. 예를 들어, 회사의 웹 사이트가 contoso.com인 경우 DNS에 EnterpriseEnrollment.contoso.com을 enterpriseenrollment-s.manage.microsoft.com으로 리디렉션하는 CNAME을 만듭니다.


   CNAME DNS 항목을 만드는 것은 선택 사항이지만 CNAME 레코드를 사용하면 사용자가 보다 쉽게 등록할 수 있습니다. 등록 CNAME 레코드가 없으면 사용자에게 MDM 서버 이름인 enrollment.manage.microsoft.com을 수동으로 입력하라는 메시지가 표시됩니다.

   CNAME 리소스 레코드에는 다음 정보가 포함되어야 합니다.

  |유형|호스트 이름|지시 대상|TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1시간|
  |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1시간|

  `EnterpriseEnrollment-s.manage.microsoft.com` – 메일의 도메인 이름에서 도메인을 인식하여 Intune 서비스로 리디렉션을 지원합니다.

  `EnterpriseRegistration.windows.net` - 회사 또는 학교 계정을 사용하여 Azure Active Directory에 등록하는 Windows 8.1 및 Windows 10 Mobile 장치를 지원합니다.

  회사에서 사용자 자격 증명에 여러 도메인을 사용하는 경우 각 도메인용으로 CNAME 레코드를 만듭니다.

  예를 들어, 회사의 웹 사이트가 contoso.com인 경우 DNS에 EnterpriseEnrollment.contoso.com을 EnterpriseEnrollment-s.manage.microsoft.com으로 리디렉션하는 CNAME을 만듭니다. DNS 레코드 변경 내용이 전파되는 데는 최대 72시간이 걸릴 수 있습니다. DNS 레코드가 전파될 때까지 Intune의 DNS 변경 내용을 확인할 수 없습니다.

### <a name="step-3-verify-cname"></a>3단계: CNAME 확인

[Intune 관리 콘솔](http://manage.microsoft.com)에서 **관리** &gt; **모바일 장치 관리** &gt; **Windows**를 선택합니다. 회사 웹 사이트의 확인된 도메인 URL을 **확인된 도메인 이름 지정** 상자에 입력하고 **자동 검색 테스트**를 선택합니다.

### <a name="step-4-tell-your-users-how-to-enroll-their-devices-and-what-to-expect-after-theyre-brought-into-management"></a>4단계: 장치를 등록하는 방법과 장치가 관리될 때 발생하는 상황에 대한 정보를 사용자에게 제공

   최종 사용자 등록 지침은 [Intune에서 Windows 장치 등록](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-windows)을 참조하세요.

   최종 사용자 작업에 대한 자세한 내용은 [Microsoft Intune에 대한 최종 사용자 교육 방법](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune) 및 [Windows 장치에 대한 최종 사용자 지침](../enduser/using-your-windows-device-with-intune.md)을 참조하세요.

### <a name="see-also"></a>참고 항목
[Microsoft Intune에서 장치 등록을 위한 필수 구성 요소](prerequisites-for-enrollment.md)

