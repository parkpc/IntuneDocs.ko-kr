---
title: "장치를 관리할 필요 없이 Office 365 Exchange Online 보호"
description: "직원에게 회사 메일에 대한 액세스 권한을 제공하세요. 장치를 관리할 필요가 없습니다."
keywords: "Office 365 Exchange 메일 액세스"
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 10/31/2017
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 88a0d3b9-2622-403b-8374-1396afd8066e
ms.reviewer: pchacon
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 53872921bc4c7a52224741ab3b743a1d9ac52f42
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2018
---
# <a name="protect-office-365-exchange-online-without-requiring-device-management"></a>장치를 관리할 필요 없이 Office 365 Exchange Online 보호

장치 관리 시스템 설정에 대한 오버헤드 없이 직원에게 회사 메일에 대한 액세스 권한을 제공하고 싶은 경우 그렇게 할 수 있습니다. Intune을 통해 Office 365 Exchange Online에 대한 액세스 권한을 제공할 수 있습니다. 필요한 단계를 완료하려면 Microsoft 365 또는 Azure Active Directory (Premium) 및 Intune에 대한 라이선스가 있는지 확인합니다. 직원에게는 [지원되는 iOS 또는 Android 장치](supported-devices-browsers.md)가 있어야 합니다. 

장치 관리 시스템을 설정하려면 그렇게 할 수 있습니다. 이러한 유형의 앱 보호는 장치 관리와 독립적으로 작동합니다. 

## <a name="action-plan"></a>작업 계획

1. [조건부 액세스에 대해 자세히 알아봅니다](conditional-access.md). 
2. [앱 기반 조건부 액세스에 대해 자세히 알아봅니다](app-based-conditional-access-intune.md).
3. [Exchange Online에 대한 앱 기반 조건부 액세스 정책을 설정합니다](app-based-conditional-access-intune-create.md).
4. [관리할 수 없는 앱을 차단](app-modern-authentication-block.md)합니다. 특히 Azure ADAL(Active Directory 인증 라이브러리)을 사용하지 않는 앱을 차단합니다.
5. (선택 사항) [SharePoint Online에 대한 앱 기반 조건부 액세스 정책을 설정합니다](app-based-conditional-access-intune-create.md). 이러한 정책은 관리 및 보호할 수 없는 앱에서 회사 데이터에 액세스하는 것을 차단합니다. 또한 SharePoint 모바일을 통해 액세스를 제한합니다. 

## <a name="what-to-tell-employees-and-students"></a>직원 및 학생에게 정보 안내

* 직원 및 학생에게 iOS용인 경우 Microsoft Outlook 또는 Microsoft SharePoint를 Apple 앱 스토어에서, Android용인 경우 Google Play 스토어에서 다운로드하고 설치하도록 요청합니다. 
* 최신 인증을 사용하지 않는 앱에 대한 액세스를 차단하는 경우, 직원 및 학생에게 이러한 제한을 알립니다. 

## <a name="next-steps"></a>다음 단계

회사 데이터의 보안을 강화하기 위해 앱 기반 조건부 액세스를 사용했습니다. 다음 단계의 일부로, 다음을 비롯하여 회사 데이터의 보안을 향상할 수 있는 다른 방법에 대해 자세히 알아볼 수 있습니다. 

* [Active Directory 및 Azure Active Directory에서 장치 준수, 장치 위험, 위치 및 사용자 특성에 따라 조건부 액세스](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) 설정  
* 고의적이거나 고의적이지 않은 데이터 유출로부터 회사 데이터를 보호하기 위해 앱 보호 정책 설정 
* 네트워크 외부에서 회사 데이터를 보호하기 위해 Azure Information Protection 활용 

이 EMS 또는 다른 EMS나 Office 365 시나리오 사용에 어떤 도움이 필요하시나요? Microsoft 365, Enterprise Mobility + Security 또는 Azure Active Directory Premium에 대한 라이선스를 150개 이상 가지고 있는 경우 [FastTrack 혜택](https://docs.microsoft.com/enterprise-mobility-security/solutions/enterprise-mobility-fasttrack-program)을 사용하세요. 