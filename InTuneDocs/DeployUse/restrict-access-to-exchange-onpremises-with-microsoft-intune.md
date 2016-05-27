---
# required metadata

title: Exchange 온-프레미스 및 레거시 Exchange Online Dedicated에 대한 메일 액세스 제한 | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: a55071f5-101e-4829-908d-07d3414011fc

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Intune을 사용하여 Exchange 온-프레미스 및 레거시 Exchange Online Dedicated에 대한 메일 액세스 제한


Exchange Online Dedicated 환경이 있고 신규 또는 기존 구성 상태인지를 확인해야 하는 경우 계정 관리자에게 문의하세요.


Exchange 온-프레미스 또는 레거시 Exchange Online Dedicated 환경에 대한 메일 액세스를 제어하려면 Intune에서 Exchange 온-프레미스에 대한 조건부 액세스를 구성합니다.
조건부 액세스가 어떻게 작동하는지에 대한 자세한 내용은 [전자 메일 및 O365 서비스에 대한 액세스 제한]( restrict-access-to-email-and-o365-services-with-microsoft-intune.md) 문서를 읽어보세요.

조건부 액세스를 구성하기 **전에** 다음을 확인합니다.

-   Exchange 버전은 **Exchange 2010 이상**이어야 합니다. Exchange Server CAS(클라이언트 액세스 서버) 배열이 지원됩니다.

-   [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]를 Microsoft Exchange 온-프레미스에 연결하는 **온-프레미스 Exchange Connector**를 사용해야 합니다. 이렇게 하면 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] 콘솔을 통해 장치를 관리할 수 있습니다. 커넥터에 대한 자세한 내용은 [Intune 온-프레미스 Exchange Connector](intune-on-premises-exchange-connector.md)를 참조하세요..

    -   Intune 콘솔에서 사용할 수 있는 온-프레미스 Exchange Connector는 Intune 테넌트에 고유하며 다른 테넌트에 사용할 수 없습니다. 또한 테넌트를 위한 Exchange Connector가 **한 대의 컴퓨터**에만 설치되어 있는지 확인해야 합니다..

        이 커넥터는 Intune 관리 콘솔에서 다운로드해야 합니다.  온-프레미스 Exchange Connector를 구성하는 방법에 대한 연습은 [온-프레미스 또는 Hosted Exchange용 Exchange 온-프레미스 커넥터 구성](intune-on-premises-exchange-connector.md)을 참조하세요..

    -   Exchange 서버와 통신할 수 있기만 하면 모든 컴퓨터에 커넥터를 설치할 수 있습니다.

    -   이 커넥터는 **Exchange CAS 환경**을 지원합니다. 원할 경우 Exchange CAS 서버에 직접 커넥터를 설치하는 것도 기술적으로 가능하지만 서버의 부하가 증가하므로 권장되지 않습니다.
    커넥터를 구성할 때는 커넥터가 Exchange CAS 서버 중 하나와 통신하도록 설정해야 합니다.

-   **Exchange ActiveSync**는 인증서 기반 인증 또는 사용자 자격 증명 항목으로 구성되어야 합니다.

조건부 액세스 정책이 구성되고 사용자를 대상으로 지정한 경우 사용자가 자신의 전자 메일에 연결하기 전에 사용하는 **장치**는 다음과 같아야 합니다.

-  [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]에 **등록**되어 있거나 도메인에 가입된 PC이어야 합니다.

-  **Azure Active Directory에 등록**되어야 합니다. 또한 클라이언트 Exchange ActiveSync ID가 Azure Active Directory에 등록되어 있어야 합니다.

  Intune 및 Office 365 고객의 경우에는 AAD DRS가 자동으로 활성화됩니다. ADFS 장치 등록 서비스를 이미 배포한 고객의 온-프레미스 Active Directory에는 등록된 장치가 표시되지 않습니다. **Windows PC 및 Windows Phone 장치에는 적용되지 않습니다.**.

-   해당 장치에 배포된 모든 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] 규정 준수 정책을 **준수**해야 합니다.

다음 다이어그램은 Exchange 온-프레미스 환경에 대한 조건부 액세스 정책에서 장치를 허용할지 또는 차단할지를 평가하기 위해 사용하는 흐름을 보여 줍니다.

![장치가 Exchange 온-프레미스에 대한 액세스를 허용 또는 차단할지를 결정하는 결정 지점을 보여 주는 다이어그램](../media/ConditionalAccess8-2.png)
조건부 액세스 정책이 충족되지 않으면 사용자가 로그인할 때 다음 메시지 중 하나가 표시됩니다.

- 장치를 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]에 등록하지 않았거나 Azure Active Directory에 등록하지 않은 경우, 회사 포털 앱을 설치하고 장치를 등록하며 전자 메일을 활성화하는 방법에 대한 지침이 포함된 메시지가 표시됩니다. 이 프로세스는 또한 장치의 Exchange ActiveSync ID를 Azure Active Directory의 장치 레코드와 연결합니다.

-   장치가 규정을 준수하지 않으면 사용자가 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] 회사 포털 웹 사이트 또는 회사 포털 앱으로 이동하는 메시지가 표시되며 여기에서 문제에 대한 정보와 이를 해결하는 방법을 확인할 수 있습니다.

## 모바일 장치에 대한 지원
-   Windows Phone 8 이상

-   iOS의 기본 메일 앱

-   Android 4 이상의 기본 메일 앱

## PC 지원

Windows 8 이상에서 **메일** 응용 프로그램(등록된 경우) [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)])

##  조건부 액세스 정책 구성

1.  [Microsoft Intune 관리 콘솔](https://manage.microsoft.com)에서 **정책** > **조건부 액세스** > **Exchange 온-프레미스 정책**을 선택합니다..
![IntuneSA5aSelectExchOnPremPolicy](../media/IntuneSA5aSelectExchOnPremPolicy.png)

2.  필요한 설정이 포함된 정책을 구성합니다.
![Exchange 온-프레미스 정책 페이지의 스크린샷](../media/IntuneSA5bExchangeOnPremPolicy.png)

  - **장치가 비준수이거나 Microsoft Intune에 등록되지 않은 경우 전자 메일 앱이 Exchange 온-프레미스에 액세스하지 못하도록 차단:** 이 옵션을 선택하면 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]에서 관리되지 않거나 규정 준수 정책을 준수하지 않는 장치에서 Exchange 서비스로의 액세스가 차단됩니다.

  - **기본 규칙 재정의 - 등록 및 준수 장치가 Exchange에 액세스할 수 있도록 항상 허용:** 이 옵션을 선택하면 Intune에 등록되어 있고 준수 정책을 준수하는 장치는 Exchange에 액세스할 수 있습니다.  
  이 규칙은 **기본 규칙**을 재정의하며, 이는 액세스를 격리 또는 차단하도록 **기본 규칙**을 설정하더라도 등록된 규격 장치는 여전히 Exchange에 액세스할 수 있음을 의미합니다.

  - **대상 그룹:** [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]에 등록해야 Exchange에 액세스할 수 있는 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] 사용자 그룹을 선택합니다.

  - **제외된 그룹:** 조건부 액세스 정책에서 제외된 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] 사용자 그룹을 선택합니다. 이 목록에 있는 사용자는 **대상 그룹** 목록에 있더라도 제외됩니다.

  - **플랫폼 예외:** **규칙 추가**를 선택하여 지정한 모바일 장치 제품군 및 모델에 대한 액세스 수준을 정의하는 규칙을 구성합니다. 이러한 장치는 유형을 불문하므로 다음에서 지원하지 않는 장치 유형도 구성할 수 있습니다. [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

  - **기본 규칙:** 다른 규칙이 적용되지 않는 장치의 경우, Exchange 액세스를 허용하거나, 차단하거나, 격리하도록 선택할 수 있습니다. 등록 및 규격 장치의 경우 액세스를 허용하도록 규칙을 설정하면 iOS, Windows 및 삼성 KNOX 장치의 경우 메일 액세스 권한이 자동으로 부여됩니다. 최종 사용자는 메일을 가져오기 위해 어떠한 프로세스도 거칠 필요가 없습니다.  삼성 KNOX를 실행하지 않는 Android 장치를 사용하는 최종 사용자는 메일에 액세스하기 전에 등록 및 규정 준수를 확인하는 안내 방식 연습을 포함하는 격리 메일을 받게 됩니다. 액세스를 차단하거나 격리하는 규칙을 설정하면 모든 장치가 이미 Intune에 등록되었는지 여부에 관계 없이 교환에 대한 액세스 권한을 얻을 수 없게 차단됩니다. 등록된 규격 장치가 이 규칙의 영향을 받지 않도록 하려면 **기본 규칙 재정의**를 선택합니다.
>[!TIP]
>메일에 대한 액세스 권한을 부여하기 전에 먼저 모든 장치를 차단할 의도라면, 차단 액세스 권한이나 격리 규칙을 선택합니다. 기본 규칙이 모든 장치 유형에 적용되므로 플랫폼 제외로 구성했는데 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] 에서 지원하지 않는 장치 유형도 영향을 받습니다.

  - **사용자 알림:** Exchange에서 보내는 알림 전자 메일 외에도 Intune은 장치를 차단 해제하는 단계를 포함하는 전자 메일을 보냅니다. 기본 메시지를 필요에 맞게 사용자 지정하도록 편집할 수 있습니다. 관리 지침이 포함된 Intune 알림 전자 메일은 사용자의 Exchange 사서함에 배달되므로, 사용자가 전자 메일 메시지를 받기 전에 해당 사용자의 장치가 차단된 경우 차단 해제된 장치 또는 다른 방법을 사용하여 Exchange에 액세스하여 메시지를 볼 수 있습니다. 이것은 특히 **기본 규칙**이 차단 또는 격리로 설정된 경우 유용합니다.  이러한 경우 최종 사용자는 앱 스토어로 가서 Microsoft 회사 포털 앱을 다운로드하고 장치를 등록해야 합니다. 이것은 iOS, Windows 및 삼성 KNOX 장치에 적용할 수 있습니다.  삼성 KNOX를 실행하지 않는 장치를 사용하는 경우 격리 메일을 대체 메일 계정에 보내어 최종 사용자가 이것을 차단된 자신의 장치에 복사하여 등록 및 규정 준수 프로세스를 완료해야 합니다.|
  > [!NOTE]
  > Exchange가 알림 전자 메일을 보낼 수 있도록 하려면 알림 전자 메일을 보내는 데 사용할 계정을 지정해야 합니다.
  >
  > 자세한 내용은 [온-프레미스 또는 Hosted Exchange용 Exchange 온-프레미스 커넥터 구성](intune-on-premises-exchange-connector.md)을 참조하세요..

3.  작업이 끝나면 **저장**을 선택합니다..

-   조건부 액세스 정책을 배포할 필요는 없으며, 즉시 적용됩니다.

-   사용자가 Exchange ActiveSync 프로필을 설정한 후에 장치가 차단되기까지 1~3시간이 걸릴 수 있습니다(다음에서 관리되지 않는 경우 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]).

-   그런 다음 차단된 사용자가 장치를 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]에 등록하거나 정책 미준수 상태를 재구성하면) 2분 내에 전자 메일 액세스 차단이 해제됩니다.

-   사용자가 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]에서 등록을 취소되면 장치가 차단되기까지 1~3시간이 걸릴 수 있습니다.

**장치 액세스를 제한하는 조건부 액세스 정책을 구성하는 방법에 대한 몇 가지 시나리오 예를 보려면 [전자 메일 액세스 제한 예제 시나리오](restrict-email-access-example-scenarios.md)를 참조하세요..**

## 다음 단계
[SharePoint Online에 대한 액세스 제한](restrict-access-to-sharepoint-online-with-microsoft-intune.md)

[비즈니스용 Skype Online에 대한 액세스 제한](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)


<!--HONumber=May16_HO1-->


