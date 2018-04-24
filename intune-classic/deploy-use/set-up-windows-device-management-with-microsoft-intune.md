---
title: Microsoft Intune을 사용한 Windows 장치 관리 설정
description: Microsoft Intune으로 Windows 장치에 대한 MDM(모바일 장치 관리)을 사용하도록 설정합니다.
keywords: ''
author: NathBarn
manager: angrobe
ms.date: 03/20/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: fb2d724cc87ffdc506eda8d5ea2330ab9aacd3e9
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="set-up-windows-device-management"></a>Windows 장치 관리 설정

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

이 항목은 IT 관리자가 사용자를 위해 Windows 등록을 간소화하는 데 도움이 됩니다.  Windows 장치는 추가 단계 없이도 등록할 수 있지만 사용자가 더 쉽게 등록하도록 할 수 있습니다.

다음의 두 가지 요소로 Windows 장치를 간편하게 등록하는 방법을 결정합니다.
- **Azure Active Directory Premium을 사용하나요?** <br>[Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium)은 Enterprise Mobility + Security 및 기타 라이선싱 계획에 포함되어 있습니다.
- **등록할 Windows 클라이언트 버전은 무엇인가요?** <br>Windows 10 장치는 회사 또는 학교 계정을 추가하여 자동으로 등록할 수 있습니다. 이전 버전은 회사 포털 앱을 사용하여 등록해야 합니다.

||**Azure AD Premium**|**기타 AD** |
|----------|---------------|---------------|  
|**Windows 10**|[자동 등록](#enable-windows-10-automatic-enrollment) |[사용자 등록](#enable-windows-enrollment-without-automatic-enrollment)|
|**이전 버전의 Windows**|[사용자 등록](#enable-windows-enrollment-without-automatic-enrollment)|[사용자 등록](#enable-windows-enrollment-without-automatic-enrollment)|

[!INCLUDE [AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="enable-windows-enrollment-without-automatic-enrollment"></a>자동 등록을 사용하지 않고 Windows 등록 사용
사용자가 Azure AD Premium 자동 등록 없이도 장치를 등록하도록 할 수 있습니다. 라이선스를 할당하고 나면 사용자가 개인 소유 장치에 자신의 작업 계정을 추가하거나 회사 소유의 장치를 Azure AD에 연결한 후에 등록할 수 있습니다. DNS 별칭(CNAME 레코드 유형)을 만들면 사용자가 자신의 장치를 쉽게 등록할 수 있습니다. DNS CNAME 리소스 레코드를 만들면 사용자가 Intune 서버 이름을 입력하지 않고도 Intune에서 연결 및 등록할 수 있습니다.

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
[Intune 관리 콘솔](https://manage.microsoft.com)에서 **관리** &gt; **모바일 장치 관리** &gt; **Windows**를 선택합니다. 회사 웹 사이트의 확인된 도메인 URL을 **확인된 도메인 이름 지정** 상자에 입력하고 **자동 검색 테스트**를 선택합니다.

## <a name="tell-users-how-to-enroll-windows-devices"></a>사용자에게 Windows 장치를 등록하는 방법 안내
사용자에게 Windows 장치를 등록하는 방법과 장치가 관리될 때 발생할 수 있는 상황에 대해 알려주어야 합니다.
최종 사용자 등록 지침은 [Intune에서 Windows 장치 등록](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows)을 참조하세요. [IT 관리자가 장치에 대해 볼 수 있는 정보](https://docs.microsoft.com/intune-user-help/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows)로 사용자를 보낼 수도 있습니다.

최종 사용자 작업에 대한 자세한 내용은 [Microsoft Intune에서 최종 사용자 환경 관련 리소스](/intune/end-user-educate)를 참조하세요.

### <a name="see-also"></a>참고 항목
[Microsoft Intune에서 장치 등록을 위한 필수 구성 요소](prerequisites-for-enrollment.md)
