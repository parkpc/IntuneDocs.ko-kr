---
title: "Exchange 온-프레미스에 대한 메일 보호 | Microsoft 문서"
description: "조건부 액세스로 Exchange 온-프레미스에서 회사 전자 메일을 보호하고 액세스를 제어합니다."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a55071f5-101e-4829-908d-07d3414011fc
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 53d2c0d5b2157869804837ae2fa08b1cce429982
ms.openlocfilehash: e3b404526d8e662fd8ae285c144b1d6f5cf22bf3


---

# <a name="protect-email-access-to-exchange-on-premises-and-legacy-exchange-online-dedicated-with-intune"></a>Intune을 사용하여 Exchange 온-프레미스 및 레거시 Exchange Online Dedicated에 대한 메일 액세스 보호

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune을 사용하여 레거시 Exchange Online Dedicated 또는 Exchange 온-프레미스에 조건부 액세스 제어 메일 액세스를 구성할 수 있습니다.
조건부 액세스가 어떻게 작동하는지에 대한 자세한 내용은 [메일 및 O365 서비스에 대한 액세스 보호](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) 문서를 읽어보세요.

> [!NOTE]
> Exchange Online Dedicated 환경이 있고 신규 또는 기존 구성 상태인지를 확인해야 하는 경우 계정 관리자에게 문의하세요.

## <a name="before-you-begin"></a>시작하기 전에

다음 사항을 확인해야 합니다.

-   Exchange 버전은 **Exchange 2010 이상**이어야 합니다. Exchange Server CAS(클라이언트 액세스 서버) 배열이 지원됩니다.

-   [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]를 Exchange 온-프레미스에 연결하는 [Intune 온-프레미스 Exchange Connector](intune-on-premises-exchange-connector.md)를 사용해야 합니다. 이렇게 하면 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] 콘솔을 통해 장치를 관리할 수 있습니다.

    -   Intune 콘솔에서 사용할 수 있는 온-프레미스 Exchange Connector는 Intune 테넌트에 고유하며 다른 테넌트에 사용할 수 없습니다. 또한 테넌트용 Exchange Connector가 **한 대의 컴퓨터**에만 설치되어 있는지 확인하는 것이 좋습니다.

        Intune 관리 콘솔에서 커넥터를 다운로드할 수 있습니다. 온-프레미스 Exchange Connector를 구성하는 방법에 대한 연습은 [configure Exchange on-premises connector for on-premises or hosted Exchange](intune-on-premises-exchange-connector.md)(온-프레미스 또는 Hosted Exchange용 Exchange 온-프레미스 커넥터 구성) 항목을 참조하세요.

    -   Exchange 서버와 통신할 수 있기만 하면 모든 컴퓨터에 커넥터를 설치할 수 있습니다.

    -   이 커넥터는 **Exchange CAS 환경**을 지원합니다. 원하는 경우 Exchange CAS 서버에 커넥터를 기술적으로 직접 설치할 수 있습니다. 그러나 서버의 부하가 늘어나기 때문에 그렇게 하지 않는 것이 좋습니다. 커넥터를 구성할 때는 Exchange CAS 서버 중 하나와 통신하도록 커넥터를 설정해야 합니다.

-   인증서 기반 인증 또는 사용자 자격 증명 항목으로 **Exchange ActiveSync**를 구성해야 합니다.

### <a name="device-compliance-requirements"></a>장치 정책 준수 요구 사항

조건부 액세스 정책을 구성하고 사용자를 대상으로 지정한 경우 사용자가 자신의 메일에 연결하기 전에 사용하는 **장치**는 다음과 같아야 합니다.

-  도메인에 가입된 PC 또는 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]에 **등록**된 PC이어야 합니다.

-  **Azure Active Directory에 등록**되어야 합니다. 또한 클라이언트 Exchange ActiveSync ID가 Azure Active Directory에 등록되어 있어야 합니다.

  Intune 및 Office 365 고객의 경우에는 Azure Active Directory Device Registration Service가 자동으로 활성화됩니다. ADFS Device Registration Service를 이미 배포한 고객의 온-프레미스 Active Directory에는 등록된 장치가 표시되지 않습니다. **Windows PC 및 Windows Phone 장치에는 적용되지 않습니다**.

-   해당 장치에 배포된 모든 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] **준수 정책을 준수해야 합니다**.

### <a name="how-conditional-access-works-with-exchange-on-premises"></a>Exchange 온-프레미스 조건부 액세스의 작동 방식

다음 다이어그램은 Exchange 온-프레미스 환경에 대한 조건부 액세스 정책에서 장치를 허용할지 또는 차단할지를 평가하기 위해 사용하는 흐름을 보여 줍니다.

![장치가 Exchange 온-프레미스에 대한 액세스를 허용하거나 차단할지를 결정하는 결정 지점을 보여 주는 다이어그램](../media/ConditionalAccess8-2.png)

조건부 액세스 정책이 충족되지 않는 경우 장치가 차단되고 10분 후 사용자에게 다음 격리 메시지(로그인 시) 중 하나가 제공됩니다.

- 장치를 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]에 등록하지 않았거나 Azure Active Directory에 등록하지 않은 경우, 회사 포털 앱을 설치하고 장치를 등록하며 메일을 활성화하는 방법에 대한 지침이 포함된 메시지가 표시됩니다. 이 프로세스는 또한 장치의 Exchange ActiveSync ID를 Azure Active Directory의 장치 레코드와 연결합니다.

-   장치가 규정을 준수하지 않으면 사용자가 문제에 관한 정보를 찾을 수 있는 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] 회사 포털 웹 사이트 또는 회사 포털 앱과, 문제의 수정 방법을 알려 주는 메시지가 표시됩니다.

## <a name="support-for-mobile-devices"></a>모바일 장치에 대한 지원
지원되는 운영 체제는 다음과 같습니다.
-   Windows Phone 8.1 이상

-   iOS의 기본 메일 앱

-   Exchange ActiveSync 메일 클라이언트(예: Android 4 이상의 Gmail)
- **Android for Work 장치**의 Exchange ActiveSync 메일 클라이언트: **회사 프로필**에서 **Gmail** 및 **Nine Work** 앱만 Android for Work에 대해 지원됩니다. 조건부 액세스가 Android for Work에서 작동하려면 Gmail 또는 Nine Work 앱에 대한 메일 프로필을 배포하고, 이러한 앱을 필수 설치로 배포해야 합니다. 

[!INCLUDE[wit_nextref](../includes/afw_rollout_disclaimer.md)]

> [!NOTE]
> Android 및 iOS용 Microsoft Outlook 앱은 지원되지 않습니다.

## <a name="support-for-pcs"></a>PC 지원
다음은 지원됩니다.
-   Windows 8.1 이상에 설치된 **메일** 응용 프로그램(PC가 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]에 등록된 경우)

##  <a name="configure-a-conditional-access-policy"></a>조건부 액세스 정책 구성

1.  [Microsoft Intune 관리 콘솔](https://manage.microsoft.com)에서 **정책** > **조건부 액세스** > **Exchange 온-프레미스 정책**을 선택합니다.
![IntuneSA5aSelectExchOnPremPolicy](../media/IntuneSA5aSelectExchOnPremPolicy.png)

2.  필요한 설정이 포함된 정책을 구성합니다. ![Exchange 온-프레미스 정책 페이지의 스크린샷](../media/IntuneSA5bExchangeOnPremPolicy.png)

  - **비규격 장치이거나 Microsoft Intune에 등록되지 않은 장치인 경우 메일 앱의 Exchange 온-프레미스 액세스를 차단합니다.:** 이 옵션을 선택하면 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]에서 관리되지 않거나 준수 정책을 준수하지 않는 장치에서 Exchange 서비스로의 액세스가 차단됩니다.

  - **기본 규칙 재정의 - 등록 및 준수 장치가 Exchange에 액세스할 수 있도록 항상 허용:** 이 옵션을 선택하면 Intune에 등록되어 있고 준수 정책을 준수하는 장치는 Exchange에 액세스할 수 있습니다.
  이 규칙은 **기본 규칙**을 재정의합니다. 즉, 액세스를 격리 또는 차단하도록 **기본 규칙**을 설정하더라도 등록된 규격 장치는 여전히 Exchange에 액세스할 수 있습니다.

  - **대상이 지정된 그룹:** [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]에 등록해야 Exchange에 액세스할 수 있는 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] 사용자 그룹을 선택합니다.

  - **제외된 그룹:** 조건부 액세스 정책에서 제외된 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] 사용자 그룹을 선택합니다. 이 목록에 있는 사용자는 **대상이 지정된 그룹** 목록에 있더라도 제외됩니다.

  - **플랫폼 예외:** **규칙 추가**를 선택하여 지정한 모바일 장치 제품군 및 모델에 대한 액세스 수준을 정의하는 규칙을 구성합니다. 장치의 유형과는 상관이 없으므로 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]에서 지원하지 않는 장치 유형도 구성할 수 있습니다.

  - **기본 규칙**: 다른 규칙이 적용되지 않는 장치의 경우, Exchange 액세스를 허용하거나, 차단하거나, 격리하도록 선택할 수 있습니다. 등록 및 규격 장치의 경우 액세스를 허용하도록 규칙을 설정하면 iOS, Windows 및 삼성 KNOX 장치의 경우 메일 액세스 권한이 자동으로 부여됩니다. 사용자는 메일을 가져오기 위해 어떠한 프로세스도 거칠 필요가 없습니다.

        Samsung KNOX를 실행하지 않는 Android 장치를 사용하는 사용자는 메일에 액세스하기 전에 등록 및 준수를 확인하는 안내 방식 연습을 포함하는 격리 메일을 받게 됩니다. 액세스를 차단하거나 격리하는 규칙을 설정하면 모든 장치가 이미 Intune에 등록되었는지 여부와 관계없이 Exchange에 대한 액세스가 차단됩니다. 등록된 규격 장치가 이 규칙의 영향을 받는 것을 방지하려면 **기본 규칙 재정의** 상자를 선택합니다.
>[!TIP]
>메일에 대한 액세스 권한을 부여하기 전에 먼저 모든 장치를 차단하려면 액세스 차단 규칙이나 격리 규칙을 선택합니다. 기본 규칙이 모든 장치 유형에 적용되므로, [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]에서 지원되지 않는 플랫폼 예외로 구성한 장치 유형도 영향을 받습니다.

  - **사용자 알림**: Exchange에서 보내는 알림 메일 외에도 Intune은 장치를 차단 해제하는 단계를 포함하는 메일을 보냅니다. 기본 메시지를 필요에 맞게 사용자 지정하도록 편집할 수 있습니다. 사용자가 관리 지침이 포함된 Intune 알림 메일을 받기 전에 해당 사용자의 장치가 차단된 경우(이 메일은 사용자의 Exchange 사서함으로 배달됨) 차단 해제된 장치 또는 다른 방법을 사용하여 Exchange에 액세스하여 메시지를 볼 수 있습니다.

        This is especially true when the **Default Rule** is set to block or quarantine. In this case, the user has to go to their app store, download the Microsoft Company Portal app, and enroll their device. This is applicable to iOS, Windows, and Samsung KNOX devices. For devices that don't run Samsung KNOX, you need to send the quarantine email to an alternate email account. The user has to copy the email to their blocked device to complete the enrollment and compliance process.
  > [!NOTE]
  > Exchange에서 알림 메일을 보내도록 하려면 알림 메일을 보내는 계정을 지정해야 합니다.
  >
  > 자세한 내용은 [Intune 온-프레미스 Exchange Connector 설치](intune-on-premises-exchange-connector.md)를 참조하세요.

3.  작업이 완료되면 **저장**을 선택합니다.

-   조건부 액세스 정책은 배포하지 않아도 즉시 적용됩니다.

-   사용자가 Exchange ActiveSync 프로필을 설정한 후에 장치가 차단되기까지&1;~3시간이 걸릴 수 있습니다([!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]에서 관리되지 않는 경우).

-   그런 다음 차단된 사용자가 장치를 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]에 등록하거나 미준수 상태를 재구성하면&2;분 내에 메일 액세스 차단이 해제됩니다.

-   사용자가 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]에서 등록을 취소하면 장치가 차단되기까지&1;~3시간이 걸릴 수 있습니다.

**장치 액세스를 보호하는 조건부 액세스 정책을 구성하는 방법에 대한 몇 가지 시나리오 예를 보려면 [메일 액세스 보호 예제 시나리오](restrict-email-access-example-scenarios.md)를 참조하세요.**

## <a name="next-steps"></a>다음 단계
-   [SharePoint Online에 대한 액세스 보호](restrict-access-to-sharepoint-online-with-microsoft-intune.md)

-   [비즈니스용 Skype Online에 대한 액세스 보호](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)



<!--HONumber=Feb17_HO2-->


