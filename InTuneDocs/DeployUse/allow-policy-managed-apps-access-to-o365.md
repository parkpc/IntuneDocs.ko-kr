---
title: "0365에 대한 앱 기반 조건부 액세스 | Microsoft Intune"
description: "O365 서비스에 액세스할 수 있는 앱을 제어하도록 MAM CA에서 지원하는 방식을 이해합니다."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bd6bee60-5e39-42c8-a2e9-f5865ac3573f
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 64eaba6918c4a5c7ccc39fb8ccfeae729a34ff4c
ms.openlocfilehash: a03faa57f9bf1ec6784f0b1ec2d41d3f4cd88a12


---

# Intune MAM 정책을 지원하는 모바일 앱만 Office 365 서비스 액세스가 허용되도록 정책 만들기
[Intune MAM(모바일 앱 관리) 정책](protect-apps-and-data-with-microsoft-intune.md)을 사용하면 Intune에서 관리를 위해 등록된 장치에서 회사 데이터를 보호하는 데 도움이 됩니다. MAM 정책은 **Intune에서 관리를 위해 장치를 등록하지 않고 직원이 소유한 장치**에서 사용할 수도 있습니다.  이 경우 장치를 관리하지 않더라도 여전히 회사 데이터와 리소스가 보호되고 있음을 확인해야 합니다. MAM 조건부 액세스(MAM CA)를 사용하여 Intune MAM 정책을 지원하는 모바일 앱만 Exchange Online과 같은 Office 365 서비스 액세스가 허용되도록 정책을 만들 수 있습니다.

예를 들어 **Microsoft Outlook 앱**만 Exchange Online 액세스를 허용하면 **iOS 및 Android의 기본 제공 메일 앱을 차단**할 수 있습니다. 기본 제공 메일 앱에는 **Exchange Online**에서 메일을 가져올 수 있는 Intune MAM 정책의 데이터 보호 기능이 없습니다.

## 필수 구성 요소
MAM CA 정책을 구성하려면 **먼저** **Enterprise Mobility + Security 또는 Azure Active Directory Premium 구독**을 사용하고 사용자는 EMS 또는 Azure AD의 라이선스를 취득해야 합니다. 자세한 내용은 [Enterprise Mobility 가격 책정 페이지](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility-pricing) 또는 [Azure Active Directory 가격 책정 페이지](https://azure.microsoft.com/en-us/pricing/details/active-directory/)를 참조하세요.


## 지원되는 앱
**Exchange Online**
* Android 및 iOS용 Microsoft Outlook

## 다른 조건부 액세스 및 인증 방법과 겹치기
### Azure Active Directory 인증서 기반 인증이 포함된 MAM CA

MAM CA는 Azure AD(Azure Active Directory) 인증서 기반 인증으로 사용할 수 없습니다. 한 번에 하나만 구성할 수 있습니다.
### 장치 규정 준수를 기반으로 하는 조건부 액세스 정책이 포함된 MAM CA  

[장치 규정 준수를 기반으로 하는 조건부 액세스](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)(**장치 CA**)를 [Intune 관리자 콘솔](https://manage.microsoft.com) 또는 [Azure AD Premium 관리 콘솔](https://manage.windowsazure.com)에 구성할 수 있습니다. 장치 CA를 사용하려면 사용자는 Intune 장치 규정 준수 정책을 준수하는 Intune 관리 장치 또는 도메인에 가입된 PC를 통해서만 Exchange Online에 연결해야 합니다.  사용자가 MAM CA와 장치 CA 정책 모두에 대해 대상이 지정된 보안 그룹에 하나 이상 속해 있는 경우 사용자는 두 가지 요구 사항 중 하나를 충족해야 합니다.
* 서비스에 액세스하는 데 사용하는 앱이 MAM CA에서 지원되는 모바일 앱이고, 앱이 실행 중인 장치에 **iOS Authenticator(iOS 장치용)** 또는 **회사 포털 앱(Android 장치용)**이 설치되어 있어야 합니다.
* 서비스에 액세스하는 데 사용하는 장치가 **Intune에서 관리되고 Intune 장치 규정 준수 정책을 준수하거나**, 장치가 **도메인에 가입된 PC**입니다.  이에 대해 설명하는 몇 가지 예는 다음과 같습니다.
  * 사용자가 **네이티브 iOS 메일 앱**에서 연결할 경우 네이티브 메일 앱은 MAM CA에서 지원되지 않으므로 사용자가 **관리되고 규정을 준수하는 장치**에 있어야 합니다.
  * 사용자가 **Windows 가정용 PC**에서 연결할 경우 **장치 CA 정책**이 적용되어 사용자가 도메인에 가입된 PC를 사용해야 합니다.


## MAM CA가 적용된 앱을 사용할 경우 어떤가요?
MAM CA는 장치에 존재해야 하는 Broker 앱을 통해 승인된 응용 프로그램 ID를 확인합니다.
*  **iOS**에서는 **Azure Authenticator 앱**이 Broker 앱입니다.
* **Android**에서는 **Intune 회사 포털 앱**이 Broker 앱입니다. 

OneDrive 또는 Outlook과 같이 MAM CA에서 지원되는 앱에 처음으로 로그인하는 최종 사용자에게는 Broker 앱을 설치하고 Azure AD에 장치를 등록하라는 메시지가 표시됩니다. Azure AD(이전의 Workplace Join)의 장치 등록에서 토큰을 발행한 장치 레코드와 인증서가 만들어집니다.  **MDM 등록**과 동일하지는 **않습니다**. 적용되는 관리 프로필 또는 정책이 없으며 장치에 앱에서 가져온 앱 인벤토리가 없습니다.  Broker 앱을 설치하고 장치를 등록하는 프로세스는 관리되는 앱을 처음 사용할 때만 실행됩니다.


## 다음 단계
[MAM 앱에 대한 Exchange Online 정책 만들기](mam-ca-for-exchange-online.md)

[최신 인증이 없는 앱 차단](block-apps-with-no-modern-authentication.md)

### 참고 항목

[MAM 정책으로 앱 데이터 보호](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Oct16_HO2-->


