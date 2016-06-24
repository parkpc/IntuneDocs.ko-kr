---
# required metadata

title: Intune을 사용하여 Windows PC 관리 | Microsoft Intune
description:
keywords:
author: nathbarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 3b8d22fe-c318-4796-b760-44f1ccf34312

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune을 사용하여 Windows PC 관리
Intune을 사용하면 장치 등록뿐만 아니라 Intune Windows PC 클라이언트 소프트웨어를 사용하여 지원되는 운영 체제를 실행하는 Windows PC를 관리할 수도 있습니다. 컴퓨터 클라이언트를 실행하려면 최소한의 하드웨어 및 소프트웨어 요구 사항만 충족하면 되며, 기본적으로는 Windows 7 이상을 실행할 수 있는 모든 시스템이 지원됩니다.  또한 클라이언트 소프트웨어는 도메인(어떤 도메인인지는 관계없음)에 가입된 컴퓨터나 가입되지 않은 컴퓨터에 쉽게 설치할 수 있습니다.

Intune에서는 Windows Server AD DS(Active Directory 도메인 서비스) GPO(그룹 정책 개체)와 비슷한 방식으로 정책을 사용하여 컴퓨터를 관리합니다. Intune에서 Active Directory 도메인에 가입된 컴퓨터를 관리하려는 경우에는 조직에서 사용 중인 [GPO와 Intune 정책이 충돌하지 않는지를 확인](resolve-gpo-and-microsoft-intune-policy-conflicts.md)해야 합니다.

> [!NOTE]
> Microsoft Intune은 독립 실행형 서비스로 이와 같은 컴퓨터 관리용 기능을 제공합니다. Windows 8.1을 실행하는 장치는 Intune 클라이언트를 사용하여 관리하거나 모바일 장치로 등록할 수 있습니다. 아래 정보는 Intune 클라이언트를 실행하는 컴퓨터에 적용됩니다.

## Intune PC 관리를 위한 요구 사항

**하드웨어**:
다음은 Intune 클라이언트를 설치하기 위한 최소 하드웨어 요구 사항입니다.

|요구 사항|추가 정보|
|---------------|--------------------|
|네트워크|클라이언트를 설치하려면 PC가 인터넷에 연결되어 있어야 합니다.|
|프로세서 및 메모리|PC 운영 체제의 프로세서 및 RAM 요구 사항을 참조하세요.|
|디스크 공간|클라이언트 소프트웨어를 설치하려면 먼저 200MB의 사용 가능한 디스크 공간이 필요합니다.|

**소프트웨어**:
다음은 클라이언트를 설치하기 위한 최소 하드웨어 요구 사항입니다.

|요구 사항|추가 정보|
|---------------|--------------------|
|관리자 권한|클라이언트 소프트웨어를 설치하는 계정에는 해당 PC에 대한 로컬 관리자 권한이 있어야 합니다.|
|Windows Installer 3.1|PC에 최소 Windows Installer 3.1이 설치되어 있어야 합니다.<br /><br />PC의 Windows Installer 버전을 확인하려면<br /><br />-   PC에서 **%windir%\System32\msiexec.exe**를 마우스 오른쪽 단추로 클릭한 다음 **속성**을 클릭합니다..<br /><br />Windows Installer의 최신 버전은 Microsoft Developer Network 웹 사이트의 [Windows Installer Redistributables(Windows Installer 재배포 가능 구성 요소)](http://go.microsoft.com/fwlink/?LinkID=234258) 에서 다운로드할 수 있습니다.|
|호환되지 않는 클라이언트 소프트웨어를 제거합니다.|Intune 클라이언트 소프트웨어를 설치하기 전에 해당 PC에서 구성 관리자 또는 System Management Server 클라이언트 소프트웨어를 제거해야 합니다.|

## Intune 컴퓨터 클라이언트 설치
Intune을 사용하여 Windows PC를 관리하는 첫 단계는 클라이언트를 설치하는 것입니다. 다음 방식 중 하나로 Intune 서비스를 통해 관리용으로 등록한 PC에 클라이언트 소프트웨어를 설치할 수 있습니다.

-   [Microsoft Intune 클라이언트 소프트웨어는 수동으로 배포](install-the-windows-pc-client-with-microsoft-intune.md#to-manually-deploy-the-client-software)할 수 있습니다. 이 유형의 배포에서는 관리자가 Intune 클라이언트 소프트웨어를 다운로드하여 각 PC에 수동으로 설치합니다.

    Intune 클라이언트 소프트웨어를 다운로드하려면 Intune 관리 콘솔을 열고 클라이언트 소프트웨어 다운로드 영역에서 클라이언트 소프트웨어 패키지를 다운로드합니다. 클라이언트 소프트웨어를 설치하고 나면 Intune에서 컴퓨터 관리에 필요한 추가 소프트웨어를 자동으로 설치합니다.

-   Intune 클라이언트를 수동으로 설치하기 위해 다운로드한 동일 파일을 사용하여 [Active Directory GPO를 사용하는 도메인에 가입된 컴퓨터에 클라이언트를 배포](install-the-windows-pc-client-with-microsoft-intune.md#to-automatically-deploy-the-client-software-by-using-group-policy)할 수 있습니다..

-   Intune 회사 포털을 통해[최종 사용자는 각 컴퓨터를 자체 등록](install-the-windows-pc-client-with-microsoft-intune.md#how-users-can-self-enroll-their-computers) 할 수 있습니다. 등록된 각 컴퓨터는 Intune 클라이언트 소프트웨어를 설치하는 데 사용한 사용자 계정에 자동으로 연결됩니다.

-   마지막으로, [운영 체제 배포](install-the-windows-pc-client-with-microsoft-intune.md#install-the-microsoft-intune-client-software-as-part-of-an-image)의 일부분으로 Intune 클라이언트 소프트웨어를 컴퓨터에 배포할 수도 있습니다..

## Intune 컴퓨터 클라이언트를 통해 컴퓨터 관리
Intune 클라이언트를 설치하고 나면 클라이언트 소프트웨어를 통해 [응용 프로그램 관리](deploy-apps-in-microsoft-intune.md), Endpoint Protection, 하드웨어 및 소프트웨어 인벤토리, 원격 지원 요청을 통한 원격 제어, 소프트웨어 업데이트, 준수 설정 보고 등의 다양한 컴퓨터 관리 기능을 사용할 수 있습니다.

컴퓨터 클라이언트를 통해 사용할 수 있는 다음과 같은 여러 컴퓨터 관리 작업은 Intune 정책을 통해 관리됩니다.

-   관리되는 컴퓨터에서 [Windows 방화벽 설정](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md) 구성.

-   관리되는 컴퓨터에서 필수 소프트웨어 업데이트를 확인하고 다운로드하기 위한 [소프트웨어 업데이트 설정](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md) 구성

-   [실시간 모니터링 및 Endpoint Protection](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md) 을 통해 잠재적 위협과 악성 소프트웨어로부터 관리되는 컴퓨터 보호

개별 컴퓨터에서 로컬로 수행되는 Intune 클라이언트 에이전트 작업 외에, 클라이언트가 설치된 Windows PC에서 Intune 관리 콘솔을 사용하여 다음과 같은 기타 [일반적인 컴퓨터 관리 작업](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md) 도 수행할 수 있습니다.

-   관리되는 컴퓨터에 대한 하드웨어 및 소프트웨어 인벤토리 정보 보기

-   원격으로 컴퓨터 다시 시작

-   컴퓨터를 사용 중지하고 클라이언트 소프트웨어를 제거한 다음 Intune에서 관리되지 않도록 컴퓨터 제거

-   특정 관리되는 컴퓨터에 사용자 연결

-   원격 지원 요청에 응답

Intune 클라이언트 에이전트는 보통 백그라운드에서 자동으로 실행되므로 많은 사용자 상호 작용 또는 문제 해결을 수행할 필요가 없습니다. 그러나 컴퓨터 관리 문제를 해결하는 데 도움이 필요한 경우에는 [문제 해결에 사용할 수 있는 리소스](/intune/troubleshoot/troubleshoot-client-setup-in-microsoft-intune)가 다수 제공됩니다..


<!--HONumber=May16_HO1-->


