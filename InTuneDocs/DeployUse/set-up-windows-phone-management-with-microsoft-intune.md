---
# required metadata

title: Microsoft Intune을 사용한 Windows 10 Mobile 및 Windows Phone 관리 설정 | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f5615051-2dd1-453b-9872-d3fdcefb2cb8

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Microsoft Intune을 사용한 Windows Phone 및 Windows 10 Mobile 관리 설정
Microsoft Intune을 사용하여 Windows 10 Mobile 또는 Windows Phone 장치를 관리할 수 있으려면 장치가 Intune과 통신할 수 있어야 합니다. 이를 간소화하기 위해 사용자가 서버 주소를 입력하지 않아도 되도록 DNS 레코드를 만들 수 있습니다. 아래 단계에서는 사용자 등록을 간소화하는 방법을 설명합니다.  

대부분의 시나리오에서 사용자는 Windows 스토어에서 회사 포털 앱을 설치할 수 있습니다. Windows Phone 8.0 장치를 관리하거나 회사 포털을 Windows Phone 장치로 배포해야 하는 경우 회사 포털 앱을 다운로드하고 서명해야 합니다. [Set up Windows Phone 8.0 management](set-up-windows-phone-8.0-management-with-microsoft-intune.md)(Windows Phone 8.0 관리 설정) 항목을 참조하세요.

1.  **Intune 설정** 모바일 장치 관리를 아직 준비하지 않은 경우 [모바일 장치 관리 기관](get-ready-to-enroll-devices-in-microsoft-intune.md#set-mobile-device-management-authority)을 **Microsoft Intune**으로 설정하고 MDM을 설정하여 관리를 준비합니다.

2.  **등록 서버 주소에 대한 DNS 별칭 설정** (선택 사항)

    DNS 별칭(CNAME 레코드 유형)을 만들면 사용자가 자신의 장치를 쉽게 등록할 수 있습니다. DNS 별칭을 만들지 않은 경우 사용자는

  1.  회사의 도메인에 대한 **CNAME** DNS 리소스 레코드를 만들어야 합니다. 예를 들어, 회사의 웹 사이트가 contoso.com인 경우 DNS에 EnterpriseEnrollment.contoso.com을 manage.microsoft.com으로 리디렉션하는 CNAME을 만들어야 합니다. 확인된 도메인이 둘 이상 있는 경우 각 도메인에 대해 CNAME 레코드를 만듭니다. CNAME 리소스 레코드에는 다음 정보가 포함되어야 합니다.

      |유형|호스트 이름|지시 대상|TTL|
      |--------|-------------|-------------|-------|
      |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1시간|
      |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1시간|

      DNS 레코드 변경 내용이 전파되는 데는 최대 72시간이 걸릴 수 있습니다. DNS 레코드가 전파될 때까지 Intune의 DNS 변경 내용을 확인할 수 없습니다.

      **EnterpriseEnrollment-s.manage.microsoft.com** – 메일의 도메인 이름에서 도메인을 인식하여 Intune 서비스로 리디렉션을 지원합니다.

      **EnterpriseRegistration.windows.net** – 회사 또는 학교 계정을 사용하여 Azure Active Directory에 등록하는 Windows 8.1 및 Windows 10 Mobile 장치를 지원합니다.

    2.  [Intune 관리 콘솔](http://manage.microsoft.com)에서 **관리** &gt; **모바일 장치 관리** &gt; **Windows Phone**을 클릭합니다.

      ![Windows 대화 상자에 대한 모바일 장치 관리 설정](../media/windows-device-enrollment.png)

    3.  회사 웹 사이트의 확인된 도메인 URL을 **확인된 도메인 이름 지정** 상자에 입력하고 **자동 검색 테스트**를 클릭합니다.



회사 포털을 장치에 배포하지 않는다면 추가 작업이 필요하지 않습니다.  관리 콘솔에서 2단계 및 3단계는 무시해도 됩니다.


<!--HONumber=May16_HO2-->


