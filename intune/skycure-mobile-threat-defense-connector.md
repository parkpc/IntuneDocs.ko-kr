---
title: "Intune을 사용한 Skycure 커넥터 통합"
titleSuffix: Intune on Azure
description: "Intune을 사용하여 Skycure 커넥터를 통합합니다."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: df4ce3f6-a093-432c-ab86-7a83865e389e
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2a7c15cf695fd88ba5961611c78ecc28a29238af
ms.sourcegitcommit: 3b21f20108e2bf1cf47c141b36a7bdae609c4ec3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2017
---
# <a name="skycure-mobile-threat-defense-connector"></a>Skycure Mobile Threat Defense

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

![감지된 악성 앱](./media/skycure-arch-1.png)

**수정 시 액세스 권한 부여됨:**

![감지된 악성 앱에 액세스 권한 부여됨](./media/skycure-arch-2.png)

### <a name="control-access-based-on-threat-to-network"></a>네트워크에 대한 위협에 따라 액세스 제어

네트워크에서 **메시지 가로채기(man-in-the-middle)**와 같은 위협을 감지하고 장치 위험에 따라 Wi-Fi 네트워크에 대한 액세스를 보호합니다.

**Wi-Fi를 통한 네트워크 액세스 차단:**

![Wi-Fi를 통한 네트워크 액세스 차단](./media/skycure-arch-3.png)

**수정 시 액세스 권한 부여됨:**

![수정 시 액세스 권한 부여됨](./media/skycure-arch-4.png)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>네트워크에 대한 위협에 따라 SharePoint Online에 대한 액세스 제어

네트워크에서 **메시지 가로채기(man-in-the-middle)**와 같은 공격을 감지하여, 장치 위험에 따라 회사 파일 동기화를 금지합니다.

**네트워크 위협이 감지할 경우 SharePoint Online 차단:**

![네트워크 위협이 감지되면 SharePoint Online 차단](./media/skycure-arch-5.png)

**수정 시 액세스 권한 부여됨:**

![SharePoint에 대해 수정 시 액세스 권한이 부여된 예](./media/skycure-arch-6.png)

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

1.  [Skycure 앱, Microsoft Authenticator 및 iOS 앱 구성 정책 추가 및 할당](mtd-apps-ios-app-configuration-policy-add-assign.md)

2.  [Intune과 Skycure 통합 설정](skycure-mtd-connector-integration.md)

3.  [Intune에서 Skycure MTD 커넥터 사용](mtd-connector-enable.md)

4.  [Intune을 사용하여 Skycure 장치 준수 정책 만들기](mtd-device-compliance-policy-create.md)
