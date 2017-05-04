---
title: "Skycure Mobile Threat Defense 커넥터 | Microsoft Docs"
description: "Skycure Mobile Threat Defense 커넥터 및 Intune을 사용하여 장치, 네트워크 및 응용 프로그램 위험에 따라 회사 리소스에 대한 액세스를 보호합니다."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7a004e6c-604a-448c-bfb8-cfda63749f5b
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: e10453155343bb7fd91a4fd3874d393ef78d0b1a
ms.openlocfilehash: f034114736e7de0ee6d0dd7fbdb121a2a092d1c5
ms.lasthandoff: 04/25/2017


---

# <a name="skycure-mobile-threat-defense-connector"></a>Skycure Mobile Threat Defense

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune과 통합된 모바일 위협 방어 솔루션인 Skycure에서 수행한 위험 평가에 따라 조건부 액세스를 사용하여 회사 리소스에 대한 모바일 장치의 액세스를 제어할 수 있습니다. 위험은 다음을 비롯하여 Skycure를 실행하는 장치에서 수집된 원격 분석에 따라 평가됩니다.

-   물리적 방어

-   네트워크 방어

-   응용 프로그램 방어

-   취약성 방어

Intune 장치 준수 정책을 통해 사용하도록 설정된 Skycure 위험 평가에 따라 조건부 액세스 정책을 구성할 수 있습니다. 이 정책을 사용하여 회사 리소스에 액세스하는 미준수 장치를 감지된 위협에 따라 허용하거나 차단할 수 있습니다.

## <a name="how-do-intune-and-skycure-help-protect-your-company-resources"></a>Intune과 Skycure가 회사 리소스를 보호하는 데 어떤 도움이 되나요?

Android 또는 iOS용 Skycure 모바일 앱은 파일 시스템, 네트워크 스택, 장치 및 응용 프로그램 원격 분석(사용 가능한 경우)을 캡처한 다음, Skycure 클라우드 서비스로 보내 모바일 위협에 대한 장치의 위험을 평가합니다.

Intune 장치 준수 정책에는 Skycure 위험 평가에 기반을 둔 Skycure Mobile Threat Defense에 대한 규칙이 포함되어 있습니다. 이 규칙을 사용하면 Intune에서 장치가 사용되는 정책을 준수하는지를 평가합니다.

장치가 정책을 준수하지 않으면 Exchange Online, SharePoint Online 등의 리소스에 대한 액세스가 차단됩니다. 차단된 장치의 사용자는 문제를 해결하고 회사 리소스에 대한 액세스 권한을 다시 얻을 수 있도록 Skycure 모바일 앱에서 지침을 받습니다.

Intune은 Skycure와의 통합을 두 가지 모드로 지원합니다.

-   **기본 설정**은 읽기 전용 모드로, Intune에서 장치에 대한 Skycure 표시를 허용합니다.

-   **전체 통합**을 사용하면 Skycure에서 장치 위험 및 보안 문제 세부 정보를 Intune에 보고할 수 있습니다.

## <a name="sample-scenarios"></a>샘플 시나리오

다음은 몇 가지 일반적인 시나리오입니다.

### <a name="control-access-based-on-threats-from-malicious-apps"></a>악성 앱의 위협에 따라 액세스 제어

맬웨어와 같은 악성 앱이 장치에서 감지되면 위협이 해결될 때까지 장치를 차단할 수 있습니다.

-   회사 메일에 연결

-   작업용 OneDrive 앱과 회사 파일 동기화

-   회사 앱에 액세스

**악성 앱이 발견되면 액세스 차단:**

![감지된 악성 앱](../media/mtp/skycure-arch-1.png)

**수정 시 액세스 권한 부여됨:**

![감지된 악성 앱에 액세스 권한 부여됨](../media/mtp/skycure-arch-2.png)

### <a name="control-access-based-on-threat-to-network"></a>네트워크에 대한 위협에 따라 액세스 제어

네트워크에서 **메시지 가로채기(man-in-the-middle)**와 같은 위협을 감지하고 장치 위험에 따라 Wi-Fi 네트워크에 대한 액세스를 보호합니다.

**Wi-Fi를 통한 네트워크 액세스 차단:**

![Wi-Fi를 통한 네트워크 액세스 차단](../media/mtp/skycure-arch-3.png)

**수정 시 액세스 권한 부여됨:**

![수정 시 액세스 권한 부여됨](../media/mtp/skycure-arch-4.png)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>네트워크에 대한 위협에 따라 SharePoint Online에 대한 액세스 제어

네트워크에서 **메시지 가로채기(man-in-the-middle)**와 같은 공격을 감지하여, 장치 위험에 따라 회사 파일 동기화를 금지합니다.

**네트워크 위협이 감지할 경우 SharePoint Online 차단:**

![네트워크 위협이 감지되면 SharePoint Online 차단](../media/mtp/skycure-arch-5.png)

**수정 시 액세스 권한 부여됨:**

![SharePoint에 대해 수정 시 액세스 권한이 부여된 예](../media/mtp/skycure-arch-6.png)

## <a name="supported-platforms"></a>지원되는 플랫폼

-   **Android 4.1 이상**

-   **iOS 8 이상**

## <a name="pre-requisites"></a>필수 구성 요소

-   Azure Active Directory Premium

-   Microsoft Intune 구독

-   Skycure Mobile Threat Defense 구독

자세한 내용은 [Skycure 웹 사이트](https://www.skycure.com/skycure-microsoft-integration/)를 참조하세요.

## <a name="next-steps"></a>다음 단계

Skycure와 Intune을 통합하기 위해 완료해야 할 단계는 다음과 같습니다.

1.  [Azure Active Directory SSO(Single Sign-On)를 사용하도록 Skycure 구성](https://docs.microsoft.com/intune/deploy-use/configure-skycure-to-use-azure-active-directory-single-sign-on)

2.  [Skycure iOS 앱 구성 정책 다운로드](https://docs.microsoft.com/intune/deploy-use/download-skycure-ios-app-configuration-policy)

3.  [Skycure 앱, Microsoft Authenticator 및 iOS 앱 구성 정책 추가](https://docs.microsoft.com/intune/deploy-use/add-skycure-apps-microsoft-authenticator-and-ios-app-configuration-policy)

4.  [Skycure 앱, Microsoft Authenticator 및 iOS 앱 구성 정책 배포](https://docs.microsoft.com/intune/deploy-use/deploy-skycure-apps-microsoft-authenticator-app-and-ios-app-configuration-policy)

5.  [Intune과 Skycure 통합 설정](https://docs.microsoft.com/intune/deploy-use/setup-the-skycure-integration-with-Intune)

6.  [Intune에서 Skycure Mobile Threat Defense를 사용하도록 설정](https://docs.microsoft.com/intune/deploy-use/enable-skycure-mobile-threat-defense-in-intune)

7.  [Intune에서 Skycure Mobile Threat Defense 준수 정책 만들기](https://docs.microsoft.com/intune/deploy-use/create-skycure-mobile-threat-defense-compliance-policy)

