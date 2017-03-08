---
title: "클라이언트 소프트웨어로 PC 관리 | Microsoft 문서"
description: "Intune 클라이언트 소프트웨어를 설치하여 Windows PC를 관리합니다."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b8d22fe-c318-4796-b760-44f1ccf34312
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 2e7062169ceb855f03a13d1afb4b4de41af593ac
ms.openlocfilehash: 10ba007095182c9cb07710656ba5f275e254d92e
ms.lasthandoff: 02/15/2017


---

# <a name="manage-windows-pcs-with-intune-pc-client-software"></a>Intune PC 클라이언트 소프트웨어를 사용하여 Windows PC 관리
[Windows PC 모바일 장치로 등록](set-up-windows-device-management-with-microsoft-intune.md)은 Intune에 Windows PC를 등록하는 기본 방법이지만 이 항목에 설명된 대로 Intune 클라이언트 소프트웨어를 설치하여 Windows PC를 등록하고 관리할 수도 있습니다.

Intune에서는 Windows Server AD DS(Active Directory Domain Services) GPO(그룹 정책 개체)와 비슷한 방식으로 정책을 사용하여 컴퓨터를 관리합니다. Intune에서 Active Directory 도메인에 가입된 컴퓨터를 관리하려는 경우에는 조직에서 사용 중인 [GPO와 Intune 정책이 충돌하지 않는지를 확인](resolve-gpo-and-microsoft-intune-policy-conflicts.md)해야 합니다. [GPO](https://technet.microsoft.com/library/hh147307.aspx)에 대해 자세히 알아볼 수 있습니다.

## <a name="policies-and-app-deployments-for-the-intune-software-client"></a>Intune 소프트웨어 클라이언트의 정책 및 앱 배포

Intune 클라이언트 소프트웨어는 소프트웨어 업데이트, Windows 방화벽, Endpoint Protection을 관리함으로써 [PC를 보호하는 관리 기능](policies-to-protect-windows-pcs-in-microsoft-intune.md)을 지원하지만, Intune 클라이언트 소프트웨어를 통해 관리되는 PC는 모바일 장치 관리 관련 **Windows** 정책 설정을 비롯한 기타 Intune 정책을 사용하여 대상으로 지정할 수 없습니다. 

Intune 클라이언트 소프트웨어를 사용하여 Windows PC를 관리하는 경우 **컴퓨터 관리** 섹션에 표시된 정책만 사용할 수 있습니다.

  ![새 Windows PC 정책에 대한 템플릿 선택](../media/select-template-for-pc-policy.png)

설정할 수 있는 정책에 대한 자세한 설명은 다음을 참조하세요.

- [정책을 사용하여 Intune 클라이언트 소프트웨어를 실행하는 Windows PC 보호](https://docs.microsoft.com/intune/deploy-use/policies-to-protect-windows-pcs-in-microsoft-intune)
- [Microsoft Intune에서 소프트웨어 업데이트를 사용하여 Windows PC를 최신 상태로 유지](https://docs.microsoft.com/intune/deploy-use/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)
- [Microsoft Intune에서 Windows 방화벽 정책을 사용하여 Windows PC 보호](https://docs.microsoft.com/intune/deploy-use/help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune)
- [Microsoft Intune용 Endpoint Protection을 사용한 Windows PC의 보안 유지 방법](https://docs.microsoft.com/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)

또한 앱을 배포할 때 Windows Installer(.exe, .msi)만 사용할 수 있습니다.

  ![PC 클라이언트 소프트웨어 파일의 플랫폼 및 위치 선택](../media/select-platform-of-software-files-for-pc-agent.png)

> [!NOTE]
> Windows 8.1 이상 장치는 Intune 클라이언트 소프트웨어를 사용하여 PC로 또는 MDM(모바일 장치 관리) 기능을 사용하여 모바일 장치로 관리할 수 있습니다. 두 방법을 함께 사용할 수 없으므로 Intune 클라이언트 소프트웨어를 사용하여 PC를 관리하도록 결정하기 전에 신중하게 고려해야 합니다. 이 항목은 Intune 클라이언트 소프트웨어를 실행하여 장치를 PC로 관리하는 경우에만 적용됩니다.

## <a name="requirements-for-intune-pc-client-management"></a>Intune PC 클라이언트 관리를 위한 요구 사항

**하드웨어**: 다음은 Intune 클라이언트 소프트웨어를 설치하기 위한 최소 하드웨어 요구 사항입니다.

|요구 사항|추가 정보|
|---------------|--------------------|
|네트워크|클라이언트를 설치하려면 PC가 인터넷에 연결되어 있어야 합니다.|
|프로세서 및 메모리|PC 운영 체제의 프로세서 및 RAM 요구 사항을 참조하세요.|
|디스크 공간|클라이언트 소프트웨어를 설치하려면 먼저&200;MB의 사용 가능한 디스크 공간이 필요합니다.|

**소프트웨어**: 다음은 클라이언트 소프트웨어를 설치하기 위한 소프트웨어 요구 사항입니다.

|요구 사항|추가 정보|
|---------------|--------------------|
|운영 체제 | Windows Vista 이상을 실행하는 Windows 장치 </br></br>**Home Edition 버전은 지원되지 않습니다.**|
|관리자 권한|클라이언트 소프트웨어를 설치하는 계정에는 해당 장치에 대한 로컬 관리자 권한이 있어야 합니다.|
|Windows Installer 3.1|PC에 최소 Windows Installer 3.1이 설치되어 있어야 합니다.<br /><br />PC의 Windows Installer 버전을 확인하려면<br /><br />  PC에서 **%windir%\System32\msiexec.exe**를 마우스 오른쪽 단추로 클릭한 다음 **속성**을 클릭합니다.<br /><br />Windows Installer의 최신 버전은 Microsoft Developer Network 웹 사이트의 [Windows Installer Redistributables(Windows Installer 재배포 가능 구성 요소)](http://go.microsoft.com/fwlink/?LinkID=234258) 에서 다운로드할 수 있습니다.|
|호환되지 않는 클라이언트 소프트웨어를 제거합니다.|Intune 클라이언트 소프트웨어를 설치하기 전에 해당 PC에서 구성 관리자, Operations Manager, Operations Management Suite 및 Service Manager 클라이언트 소프트웨어를 모두 제거하세요.|

## <a name="computer-management-capabilities-with-the-intune-client-software"></a>Intune 클라이언트 소프트웨어의 컴퓨터 관리 기능

Intune 클라이언트 소프트웨어가 설치된 후 관리 기능에는 다음이 포함됩니다. 

- [응용 프로그램 관리](deploy-apps-in-microsoft-intune.md)

- [실시간 모니터링 및 Endpoint Protection](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md) -Endpoint Protection은 Windows Defender와 동일한 작업을 합니다. 끝점 보호는 Windows 7 및 Windows 8에 적용됩니다. Windows 10 이상의 경우 제품 이름이 Windows Defender로 변경되었습니다.

- [Windows 방화벽 설정 관리](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md), 하드웨어 및 소프트웨어 인벤토리, 원격 제어(원격 지원 요청을 통해)

- [소프트웨어 업데이트 설정](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md)

- 준수 설정 보고

Intune 관리 콘솔에서 "업데이트," "보호" 및 "라이선스"와 같은 특정 섹션은 Intune 클라이언트 소프트웨어를 사용하여 장치를 등록한 경우에만 표시됩니다.

  ![PC 클라이언트에 대해서만 표시되는 관리 콘솔 항목](../media/admin-console-settings-only-for-pc-agent.png)

클라이언트가 설치된 Windows PC에서 Intune 관리자 콘솔을 사용하여 다른 일반적인 컴퓨터 관리 작업을 수행할 수도 있습니다.

-   관리되는 컴퓨터에 대한 하드웨어 및 소프트웨어 인벤토리 정보 보기
-   원격으로 컴퓨터 다시 시작
-   컴퓨터를 사용 중지하고 클라이언트 소프트웨어를 제거한 다음 Intune에서 관리되지 않도록 컴퓨터 제거
-   특정 관리되는 컴퓨터에 사용자 연결
-   원격 지원 요청에 응답

위의 작업에 대한 자세한 내용은 [일반적인 컴퓨터 관리 작업](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)을 참조하세요.

## <a name="management-limitations-of-the-intune-client-software"></a>Intune 클라이언트 소프트웨어의 관리 제한 사항

PC를 모바일 장치로 관리하는 데 사용할 수 있는 일부 관리 옵션은 Intune 클라이언트 소프트웨어로 관리되는 PC에 사용할 수 없습니다.

-   전체 초기화(선택적 초기화는 사용 가능함)

-   조건부 액세스

## <a name="help-with-troubleshooting"></a>문제 해결 지원

Intune 클라이언트 소프트웨어는 보통 백그라운드에서 자동으로 실행되므로 많은 사용자 상호 작용 또는 문제 해결을 수행할 필요가 없습니다. PC 관리 문제를 해결해야 하는 경우 로그를 확인할 수 있습니다. Intune 클라이언트 소프트웨어 및 해당 로그는 %Program Files%\Microsoft\OnlineManagement 디렉터리에 설치됩니다.

[Microsoft Intune에서 클라이언트 설정 문제 해결](/intune/troubleshoot/troubleshoot-client-setup-in-microsoft-intune)을 검토하여 발생할 수 있는 문제 및 해결 방법을 확인할 수도 있습니다.

