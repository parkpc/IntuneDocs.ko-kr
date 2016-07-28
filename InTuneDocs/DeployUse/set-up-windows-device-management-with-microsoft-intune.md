---
title: "Microsoft Intune을 사용한 Windows 장치 관리 설정 | Microsoft Intune"
description: "Microsoft Intune으로 Windows 10 장치를 비롯한 Windows Phone PC에 대한 MDM(모바일 장치 관리)을 사용하도록 설정합니다."
keywords: 
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5f336cf52cbecd93cb7b2850560327e6024302e0
ms.openlocfilehash: 710e34f8f97377bf57a398f74773788df3794654


---

# Windows 장치 관리 설정
Intune을 사용하면 회사 메일 및 앱에 액세스할 수 있도록 Windows PC 장치 등록에 대해 BYOD("Bring Your Own Device")를 사용하도록 설정할 수 있습니다. Azure Active Directory와 함께 사용되어 새 Windows 10 장치를 관리로 이동하는 신속하고 자동화된 방법을 제공하며 컴퓨터에 이미지로 다시 설치할 필요 없이 회사 리소스에 액세스할 수 있습니다. 사용자가 등록된 후에는 로그인할 수 있으며 Intune 관리 콘솔을 사용하여 정책, 앱 및 설정으로 대상 장치를 지정할 수 있습니다. Intune 클라이언트를 사용하여 [Microsoft Intune을 사용한 Windows Phone 관리 설정](set-up-windows-phone-management-with-microsoft-intune.md) 또는 [Intune 클라이언트 소프트웨어로 컴퓨터 관리](manage-windows-pcs-with-microsoft-intune.md)를 수행하려고 할 수도 있습니다.

DNS CNAME을 만들면 사용자가 서버 이름을 입력하지 않고도 Intune에서 연결 및 등록할 수 있습니다.

### Windows 장치 관리 설정

  1.  회사의 도메인에 대한 **CNAME** DNS 리소스 레코드를 만듭니다. 예를 들어, 회사의 웹 사이트가 contoso.com인 경우 DNS에 EnterpriseEnrollment.contoso.com을 EnterpriseEnrollment-s.manage.microsoft.com으로 리디렉션하는 CNAME을 만듭니다. CNAME DNS 항목은 Windows 장치 등록에서 선택 사항이지만 Windows 장치 등록 프로세스 동안 작업을 더욱 쉽게 수행하기 위해서는 필요할 때 레코드를 하나 이상 만드는 것이 좋습니다. CNAME 레코드가 없는 경우 MDM 서버 이름을 수동으로 입력하라는 메시지가 나타납니다.

  확인된 도메인이 둘 이상 있는 경우 각 도메인에 대해 CNAME 레코드를 만듭니다. CNAME 리소스 레코드에는 다음 정보가 포함되어야 합니다.

  |유형|호스트 이름|지시 대상|TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1시간|
  |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1시간|

  DNS 레코드 변경 내용이 전파되는 데는 최대 72시간이 걸릴 수 있습니다. DNS 레코드가 전파될 때까지 Intune의 DNS 변경 내용을 확인할 수 없습니다.

  **EnterpriseEnrollment-s.manage.microsoft.com** – 메일의 도메인 이름에서 도메인을 인식하여 Intune 서비스로 리디렉션을 지원합니다.

  **EnterpriseRegistration.windows.net** – 회사 또는 학교 계정을 사용하여 Azure Active Directory에 등록하는 Windows 8.1 및 Windows 10 Mobile 장치를 지원합니다.

  2.  [Intune 관리 콘솔](http://manage.microsoft.com)에서 **관리** &gt; **모바일 장치 관리** &gt; **Windows**를 클릭합니다.
  ![Windows 장치 관리 대화 상자](../media/enroll-intune-winenr.png)
  3.  회사 웹 사이트의 확인된 도메인 URL을 **확인된 도메인 이름 지정** 상자에 입력하고 **자동 검색 테스트**를 클릭합니다.

### 참고 항목
[Microsoft Intune에 장치를 등록하도록 준비](get-ready-to-enroll-devices-in-microsoft-intune.md)



<!--HONumber=Jul16_HO3-->


