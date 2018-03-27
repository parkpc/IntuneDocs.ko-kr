---
title: 0365에 대한 앱 기반 조건부 액세스
description: O365 서비스에 액세스할 수 있는 앱을 제어하도록 MAM CA에서 지원하는 방식을 이해합니다.
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 12/05/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: bd6bee60-5e39-42c8-a2e9-f5865ac3573f
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b0b0fbfce086729551b211dd4bc4b83348aa4787
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2018
---
# <a name="allow-only-mobile-apps-that-support-intune-app-protection-policies-to-access-office-365-services"></a>Intune 앱 보호 정책을 지원하는 모바일 앱만 Office 365 서비스에 액세스하도록 허용

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

[Intune 앱 보호 정책](protect-apps-and-data-with-microsoft-intune.md)을 사용하면 Intune에서 관리를 위해 등록된 장치에서 회사 데이터를 보호하는 데 도움이 됩니다. **Intune에서 관리를 위해 등록되지 않은 직원 소유 장치**에서 앱 보호 정책을 사용할 수도 있습니다.  이 경우 장치를 관리하지 않더라도 여전히 회사 데이터와 리소스가 보호되고 있음을 확인해야 합니다. MAM과 함께 앱 기반 조건부 액세스를 사용하여 Intune 앱 보호 정책을 지원하는 모바일 앱만 Exchange Online과 같은 O365 서비스에 액세스하도록 허용하는 정책을 만들 수 있습니다.

예를 들어 **Microsoft Outlook 앱**만 Exchange Online 액세스를 허용하면 **iOS 및 Android의 기본 제공 메일 앱을 차단**할 수 있습니다. 기본 제공 메일 앱에는 **Exchange Online**에서 메일을 가져올 수 있는 Intune MAM 정책의 데이터 보호 기능이 없습니다. 또는 Intune MAM 지원이 없는 모바일 앱에서 **SharePoint Online**에 액세스하지 못하게 차단할 수 있습니다.

아래 다이어그램은 앱 기반 조건부 액세스 정책에서 액세스를 허용하거나 차단하는 경우를 결정하는 데 사용되는 흐름을 보여 줍니다. ![액세스를 허용할지 또는 거부할지를 결정하기 위해 포함된 다양한 기준을 보여 주는 다이어그램](../media/mam-ca-decision-flow_simple.png).

다이어그램에 사용된 약어 설명:
* **CP**: 회사 포털 앱
* **AA**: Azure Authenticator 앱
* **AAD**: Azure Active Directory
* **EAS**: Exchange Active Sync

## <a name="prerequisites"></a>전제 조건
앱 기반 조건부 액세스 정책을 만들려면 **먼저** **Enterprise Mobility + Security 또는 Azure Active Directory Premium 구독**을 사용하고 사용자는 EMS 또는 Azure AD의 라이선스를 취득해야 합니다. 자세한 내용은 [Enterprise Mobility 가격 책정 페이지](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) 또는 [Azure Active Directory 가격 책정 페이지](https://azure.microsoft.com/pricing/details/active-directory/)를 참조하세요.


## <a name="supported-apps"></a>지원되는 앱
**Exchange Online**:
* Android 및 **iOS용 Microsoft Outlook**입니다.

**SharePoint Online**
* iOS 및 Android용 Microsoft Word
* iOS 및 Android용 Microsoft Excel
* iOS 및 Android용 Microsoft PowerPoint
* iOS 및 Android용 Microsoft OneDrive for Business
* iOS용 Microsoft OneNote

>[!IMPORTANT]
>Android 장치의 경우 초기 장치 등록은 OneDrive app 또는 Outlook 앱에 로그인하여 수행해야 합니다. Android용 OneNote 앱에서는 아직 등록이 안 된 MAM이 지원되지 않습니다.

앱 기반 조건부 액세스 정책이 포함된 앱 관련 사용자 환경에 대한 자세한 내용은 [MAM CA와 함께 앱을 사용할 경우의 예상 결과](use-apps-with-mam-ca.md)를 참조하세요.


## <a name="next-steps"></a>다음 단계
[MAM 앱에 대한 Exchange Online 정책 만들기](mam-ca-for-exchange-online.md)

[MAM 앱에 대한 SharePoint Online 정책 만들기](mam-ca-for-sharepoint-online.md)

[최신 인증이 없는 앱 차단](block-apps-with-no-modern-authentication.md)

### <a name="see-also"></a>참고 항목

[앱 보호 정책을 사용하여 앱 데이터 보호](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)
