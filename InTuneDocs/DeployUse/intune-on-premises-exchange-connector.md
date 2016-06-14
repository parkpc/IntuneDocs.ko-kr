---
# required metadata

title: On-Premises Exchange용 Microsoft Intune Exchange Connector 설치 | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 41ff4212-a6f5-4374-8731-631f7560cff1

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# On-Premises Exchange Connector 설치


Microsoft Intune을 사용하여 모바일 장치의 사서함을 호스팅하는 Exchange Server와 통신하도록 연결을 설정하려면 Intune 관리자 콘솔에서 On-Premises Connector 도구를 다운로드하여 구성해야 합니다.

## 온-프레미스 커넥터의 요구 사항
다음 표에는 On-Premises Exchange Connector를 설치하는 컴퓨터의 요구 사항이 정리되어 있습니다.

|요구 사항|추가 정보|
|---------------|--------------------|
|운영 체제|Intune은 Windows Server 2008 SP2 64비트, Windows Server 2008 R2, Windows Server 2012 또는 Windows Server 2012 R2의 모든 버전을 실행하는 컴퓨터에서 On-Premises Exchange Connector를 지원합니다.<br /><br />이 커넥터는 Server Core 설치에서 지원되지 않습니다.|
|Microsoft Exchange 버전|On-Premises Connector를 사용하려면 Microsoft Exchange 2010 SP1 이상이 필요합니다.|
|모바일 장치 관리 기관| [Intune으로 모바일 장치 관리 기관 설정](get-ready-to-enroll-devices-in-microsoft-intune.md#set-mobile-device-management-authority).|
|하드웨어|커넥터를 설치하는 컴퓨터에는 1.6GHz CPU, 2GB RAM 및 10GB의 사용 가능한 디스크 공간 최소 하드웨어가 필요합니다.|
|Active Directory 동기화|커넥터를 사용하여 Exchange Server에 Intune을 연결하려면 먼저 로컬 사용자 및 보안 그룹이 Azure Active Directory의 인스턴스와 동기화되도록 [Active Directory 동기화를 설정](/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3)해야 합니다.|
|추가 소프트웨어|커넥터를 호스트하는 컴퓨터에 Microsoft .NET Framework 4 및 Windows PowerShell 2.0 전체 설치를 설치해야 합니다.|
|네트워크|커넥터를 설치하는 컴퓨터는 Exchange 서버를 호스팅하는 도메인과 트러스트 관계에 있는 도메인에 있어야 합니다.<br /><br />이 컴퓨터에서는 포트 80 및 443을 사용하여 방화벽 및 프록시 서버를 통해 Intune 서비스에 액세스할 수 있도록 구성해야 합니다. Intune에서 사용되는 도메인은 manage.microsoft.com, &#42;manage.microsoft.com, &#42;.manage.microsoft.com 등입니다.|
|호스팅된 Exchange 구성 및 실행|자세한 내용은 [Exchange Server 2016](https://technet.microsoft.com/library/mt170645.aspx)을 참조하세요. |
|Intune으로 모바일 장치 관리 기관 설정|[Intune으로 모바일 장치 기관 설정](get-ready-to-enroll-devices-in-microsoft-intune.md#BKMK_Set_MDM_Authority)|

### Exchange cmdlet 요구 사항

Intune Exchange Connector에서 사용되는 Active Directory 사용자 계정을 만들어야 합니다. 계정에는 다음과 같은 필수 Windows PowerShell Exchange cmdlet을 실행할 수 있는 권한이 있어야 합니다.


 -   Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings
 -   Get-CasMailbox, Set-CasMailbox
 -   Get-ActiveSyncMailboxPolicy, Set-ActiveSyncMailboxPolicy, New-ActiveSyncMailboxPolicy, Remove-ActiveSyncMailboxPolicy
 -   Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule
 -   Get-ActiveSyncDeviceStatistics
 -   Get-ActiveSyncDevice
 -   Get-ExchangeServer
 -   Get-ActiveSyncDeviceClass
 -   Get-Recipient
 -   Clear-ActiveSyncDevice, Remove-ActiveSyncDevice
 -   Set-ADServerSettings
 -   Get-Command

## On-Premises Exchange Connector 소프트웨어 설치 패키지 다운로드

1. On-Premises Exchange Connector에 대해 지원되는 운영 체제에서 Exchange Server를 사용하는 라이선스로 Exchange 테넌트에서 관리자인 사용자 계정으로 [Microsoft Intune 관리 콘솔](http://manage.microsoft.com) (http://manage.microsoft.com)을 엽니다.
![Exchange 연결 설정 열기](../media/ExchangeConnector.gif)

2.  작업 영역 바로 가기 창에서 **ADMIN**을 선택합니다..

3.  탐색 창의 **모바일 장치 관리**에서 **Microsoft Exchange**를 확장하고 **Exchange 연결 설정**을 선택합니다..

4.  **Exchange 연결 설정** 페이지에서 **On-Premises Connector 다운로드**를 선택합니다..

5.  On-Premises Exchange Connector는 열거나 저장할 수 있는 압축(.zip) 폴더에 포함되어 있습니다. **파일 다운로드** 대화 상자에서 **저장**을 선택하여 이 압축(ZIP) 폴더를 안전한 위치에 저장합니다.

> [!IMPORTANT]
> On-Premises Exchange Connector 폴더 내의 파일의 이름을 변경하거나 이동하지 마십시오. 폴더의 내용을 이동하거나 이름을 바꾸면 설치가 중단됩니다.

## Intune On-Premises Exchange Connector 설치 및 구성
Intune On-Premises Exchange Connector를 설치하려면 다음 단계를 수행합니다. On-Premises Exchange Connector는 단 한 컴퓨터에 Intune 구독당 하나만 설치할 수 있습니다. 추가 On-Premises Exchange Connector를 구성하면 새 연결이 원래 연결로 바뀝니다.

1.  On-Premises Connector에 대해 지원되는 운영 체제에서 **Exchange_Connector_Setup.zip**의 파일을 안전한 위치로 추출합니다.

2.  파일을 추출한 후 추출한 폴더를 열고 **Exchange_Connector_Setup.exe**를 두 번 클릭하여 On-Premises Exchange Connector를 설치합니다.

    > [!IMPORTANT]
    > 대상 폴더가 안전한 위치가 아니면 On-Premises Connector를 설치한 후 인증서 파일 **WindowsIntune.accountcert**를 삭제해야 합니다.

3.  **Exchange 서버** 필드에서 Exchange 서버 환경 유형, 즉 **온-프레미스 Microsoft Exchange Server** 또는 **Hosted Microsoft Exchange Server**를 선택합니다..

  ![Exchange Server 종류를 선택합니다.](../media/IntuneSA1dconfigureExchConnector.png)

  On-Premises Exchange Server의 경우 **클라이언트 액세스 서버** 역할을 호스팅하는 Exchange 서버의 서버 이름 또는 정규화된 도메인 이름을 지정합니다.

  Hosted Exchange Server에 대해 Exchange 서버 주소를 지정합니다. Hosted Exchange Server URL을 확인하려면

      1.  Office 365용 Outlook Web App을 엽니다.

      2.  왼쪽 위에 있는 "?" 아이콘을 클릭하고 **정보**를 선택합니다..

      3.  **POP 외부 서버** 값을 찾습니다.

      4.  **프록시 서버**를 선택하여 Hosted Exchange Server의 프록시 서버 설정을 지정합니다.
        1.  **모바일 장치 정보를 동기화는 경우 프록시 서버 사용**을 선택합니다..

        2.  서버에 액세스하는 데 사용할 **프록시 서버 이름** 및 **포트 번호** 를 입력합니다.

        3.  프록시 서버에 액세스하기 위해 사용자 자격 증명을 제공해야 하는 경우 자격 증명을 사용하여 프록시 서버에 연결을 선택하고 **도메인\사용자** 및 **암호**를 입력합니다..

        4.  **확인**을 선택합니다..

5.  Exchange 서버에 연결하는 데 필요한 자격 증명인 **사용자(도메인\사용자)** 및 **암호**를 제공합니다.

6.  사용자의 Exchange 사서함에 알림을 보내는 데 필요한 관리 자격 증명을 입력합니다. 이러한 알림은 Intune으로 조정 가능한 조건부 액세스 정책을 통해 구성할 수 있습니다.

    자동 검색 서비스 및 Exchange 웹 서비스가 Exchange 클라이언트 액세스 서버에 구성되어 있는지 확인합니다. 여기에 대한 자세한 내용은 [클라이언트 액세스 서버](https://technet.microsoft.com/library/dd298114.aspx)를 참조하세요..

7.  Intune이 Exchange Server에 액세스할 수 있도록 **암호** 필드에 이 계정의 암호를 입력합니다.

8. **연결**을 선택합니다..

    연결을 설정하는 데는 몇 분이 걸릴 수 있습니다.

구성하는 동안 인터넷 액세스를 사용할 수 있도록 Exchange Connector에 프록시 설정이 저장됩니다. 프록시 설정을 변경하는 경우 업데이트된 프록시 설정이 Exchange Connector에 적용되도록 Exchange Connector를 다시 구성해야 합니다.

Exchange Connector의 연결을 설정하면 Exchange Connector에서 관리되는 사용자에 연결된 모바일 장치가 자동으로 동기화되어 Exchange Connector에 추가됩니다. 이 동기화를 완료하는 데는 다소 시간이 걸릴 수 있습니다.

> [!NOTE]
> On-Premises Exchange Connector를 설치했다가 어떤 시기에 Exchange 연결을 삭제한 경우 On-Premises Exchange Connector가 설치된 컴퓨터에서 해당 소프트웨어를 제거해야 합니다.

## Exchange 연결 확인

Exchange Connector를 성공적으로 구성한 후 연결 상태 및 마지막으로 성공한 동기화 시도를 볼 수 있습니다. [Microsoft Intune 관리 콘솔](http://manage.microsoft.com)에서 **ADMIN** 작업 영역을 선택하고 **모바일 장치 관리**에서 **Microsoft Exchange**를 선택한 후 제공한 세부 정보가 **Exchange 연결 정보**에 나타나는지 확인합니다..


마지막으로 성공한 동기화 시도의 시간과 날짜를 확인할 수도 있습니다.


<!--HONumber=May16_HO1-->


