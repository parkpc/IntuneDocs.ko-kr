---
title: "일반적인 Windows PC 관리 작업 | Microsoft Intune"
description: "Intune PC 클라이언트 소프트웨어를 실행하는 컴퓨터를 관리하는 방법에 대해 알아보려면 이 항목의 작업을 검토합니다."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 08/04/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: eb912c73-54d2-4d78-ac34-3cbe825804c7
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: dcfa3af374a7e64e931508e1a8022bf8a50c71a7
ms.openlocfilehash: 93d5718fcd9949945180434b0f89eea96e92bbc6


---

# Microsoft Intune 컴퓨터 클라이언트를 사용한 일반 Windows PC 관리 작업
Intune PC 클라이언트 소프트웨어를 실행하는 컴퓨터를 관리하는 방법에 대해 알아보려면 이 항목의 작업을 검토합니다. 컴퓨터에 클라이언트를 아직 설치하지 않은 경우 [Microsoft Intune을 사용하여 Windows PC 클라이언트 설치](install-the-windows-pc-client-with-microsoft-intune.md)를 참조하세요.


## 정책을 사용하여 PC 관리 간소화
### Windows 방화벽 관리
정책을 사용하면 관리 컴퓨터의 Windows Firewall 방화벽 설정을 쉽게 관리할 수 있습니다. 자세한 내용은 [Microsoft Intune에서 Windows 방화벽 정책을 사용하여 Windows PC 보호](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md)를 참조하세요.

### Microsoft Intune Center 관리
Microsoft Intune Center를 통해 사용자는 다음을 수행할 수 있습니다.

-   회사 포털에서 응용 프로그램 가져오기

-   업데이트 확인

-   Microsoft Intune Endpoint Protection 관리

-  원격 지원 요청

Microsoft Intune Center는 모든 관리 컴퓨터에 설치됩니다. Intune 정책에서 다음 설정을 구성할 수 있으며 이러한 설정은 Microsoft Intune Center에 표시됩니다.

|정책 설정|세부 정보|
|------------------|--------------------|
|**Name**|컴퓨터를 관리하는 관리자의 이름<br /><br />최대 길이: 40자|
|**전화 번호**|컴퓨터를 관리하는 관리자의 전화번호<br /><br />최대 길이: 20자|
|**전자 메일 주소**|컴퓨터를 관리하는 관리자의 전자 메일 주소<br /><br />최대 길이: 40자|
|**웹 사이트 이름**|사용자를 위한 지원 웹 사이트 이름<br /><br />최대 길이: 40자|
|**웹 사이트 URL**|지원 웹 사이트의 URL<br /><br />최대 길이: 150자|
|**참고**|사용자에게 표시되는 참고 사항<br /><br />최대 길이: 120자|

### 소프트웨어 업데이트 설정 관리
정책을 사용하여 관리 컴퓨터에서 Microsoft 및 타사의 소프트웨어 업데이트를 확인 및 다운로드하는 데 사용하는 설정을 구성할 수 있습니다. 자세한 내용은 [Microsoft Intune에서 소프트웨어 업데이트를 사용하여 Windows PC를 최신 상태로 유지](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md)를 참조하세요.

### Endpoint Protection 설정 관리
정책을 사용하여 관리 컴퓨터에 배포할 Endpoint Protection 설정을 구성할 수 있습니다. 이러한 설정에는 검색 일정, 맬웨어 검색 시 수행할 작업 등이 포함됩니다. 자세한 내용은 [Microsoft Intune용 Endpoint Protection을 사용한 Windows PC의 보안 유지 방법](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md)을 참조하세요.

## 하드웨어 및 소프트웨어 인벤토리 보기
Intune에서는 관리 컴퓨터의 하드웨어 및 소프트웨어에 대한 자세한 정보를 수집합니다. 다음 절차의 정보를 통해 다음을 만드는 방법에 대해 알아볼 수 있습니다.

-   컴퓨터의 하드웨어 성능에 대한 정보를 나열하는 보고서

-   각 컴퓨터에 설치된 소프트웨어를 나열하는 보고서

-   보고서의 현재 데이터를 확인하기 위해 컴퓨터 인벤토리를 새로 고치는 방법

### 컴퓨터에 대한 정보를 표시하려면

1.  [Microsoft Intune 관리 콘솔](https://manage.microsoft.com/)에서 **보고서** &gt; **컴퓨터 인벤토리 보고서**를 선택합니다.

2.   **새 보고서 만들기** 페이지에서 기본값을 그대로 사용하거나 보고서에서 반환할 결과를 필터링하도록 값을 사용자 지정합니다. 예를 들어 Windows 8.1을 실행하는 컴퓨터만 보고서에 표시되도록 선택할 수 있습니다.

3.  **컴퓨터 인벤토리 보고서**를 새 창으로 열려면 **보고서 보기**를 선택합니다.

    **이름**, **섀시 종류** 또는 **제조업체**와 같은 각 열 제목을 선택하여 보고서를 열별로 정렬할 수 있습니다.

### 컴퓨터에 설치된 소프트웨어를 표시하려면

1.  [Microsoft Intune 관리 콘솔](https://manage.microsoft.com/)에서 **보고서** &gt; **검색된 소프트웨어 보고서**를 선택합니다.

2.   **새 보고서 만들기** 페이지에서 기본값을 그대로 사용하거나 보고서에서 반환할 결과를 필터링하도록 값을 사용자 지정합니다. 예를 들어 Microsoft에서 게시한 소프트웨어만 보고서에 표시되도록 선택할 수 있습니다.

3.  **검색된 소프트웨어 보고서**를 새 창으로 열려면 **보고서 보기**를 선택합니다.

    **이름**, **게시자** 또는 **범주**와 같은 각 열 제목을 선택하여 보고서를 열별로 정렬할 수 있습니다. 목록 항목 옆에 있는 방향 화살표를 선택해서 목록에서 업데이트를 확장하여 세부 정보(예: 설치되어 있는 컴퓨터)를 표시할 수 있습니다.

### 현재 컴퓨터 인벤토리를 확인하기 위해 새로 고치려면

1.  [Microsoft Intune 관리 콘솔](https://manage.microsoft.com/)에서 **그룹** &gt; **모든 장치**(또는 인벤토리를 새로 고치려는 컴퓨터가 포함된 다른 그룹)를 선택합니다.

2.  컴퓨터를 선택하거나, **Ctrl** 키를 누른 상태에서 여러 컴퓨터를 선택합니다.

3.  작업 표시줄에서 **원격 작업** &gt; **인벤토리 새로 고침**을 선택합니다.

4.  작업 상태를 확인하려면 페이지의 오른쪽 아래 모서리에 있는 **원격 작업**을 선택합니다.

     **작업 상태** 대화 상자에는 현재 원격 작업, 작업 상태, 장치 이름 및 보고된 모든 오류 목록이 표시되고, 문제 해결 정보 링크도 제공됩니다.


## 원격으로 Windows PC 다시 시작

1.  [Microsoft Intune 관리 콘솔](https://manage.microsoft.com/)에서 **그룹** &gt; **모든 장치**(또는 다시 시작하려는 컴퓨터가 포함된 다른 그룹)를 선택합니다.

2.  컴퓨터를 하나 이상 선택한 후 **원격 작업** &gt; **컴퓨터 다시 시작**을 선택합니다.

3.  작업 상태를 확인하려면 페이지의 오른쪽 아래 모서리에 있는 **원격 작업**을 선택합니다.

4.   **작업 상태** 대화 상자에서 현재 원격 작업, 작업 상태, 장치 이름 및 보고된 모든 오류를 검토할 수 있습니다.

## 컴퓨터 사용 중지

1.  [Microsoft Intune 관리 콘솔](https://manage.microsoft.com/)에서 **그룹** &gt; **모든 장치**(또는 사용 중지하려는 컴퓨터가 포함된 다른 그룹)를 선택합니다.

2.  사용 중지하려는 장치를 선택한 후 **사용 중지/초기화**를 선택합니다.

컴퓨터를 Intune에 다시 등록하려면 [Microsoft Intune을 사용하여 Windows PC 클라이언트 설치](install-the-windows-pc-client-with-microsoft-intune.md) 항목의 정보를 사용하여 컴퓨터에 클라이언트 소프트웨어를 다시 설치합니다.

컴퓨터에서 Intune에 연결할 수 없는 경우 **대시보드** 작업 영역에 메시지가 표시됩니다.

컴퓨터를 사용 중지하는 경우

-   해당 컴퓨터가 Intune 관리 및 인벤토리에서 제거되며, 컴퓨터와 연결된 라이선스를 다시 사용할 수 있습니다. 사용 중지/초기화는 Intune 소프트웨어 클라이언트를 제거하지만, 컴퓨터에서 앱 또는 데이터는 제거하지 않습니다.

-   또한 해당 상태가 Intune 콘솔에 더 이상 표시되지 않습니다.

-   Intune은 컴퓨터에서 클라이언트 소프트웨어를 제거합니다. 컴퓨터가 Intune 서비스에 연결되지 않은 경우 클라이언트 소프트웨어가 다음 연결 시에 제거됩니다.

-   Microsoft Intune Endpoint Protection이 컴퓨터에서 제거됩니다. 컴퓨터에 다른 끝점 응용 프로그램이 설치되어 있지만 사용되지 않도록 설정된 경우, Microsoft Intune Endpoint Protection을 제거하면 이 응용 프로그램이 다시 사용되도록 설정되어 컴퓨터가 보호될 수 있습니다.

-   컴퓨터에서 정책을 제거하면 해당 정책으로 설정된 값이 변경됩니다.

-   컴퓨터는 Intune 서비스로부터 소프트웨어 업데이트나 맬웨어 정의 업데이트를 더 이상 받지 않습니다.

-   구성 방법에 따라 사용 중지된 컴퓨터도 Windows Server Update Services, Windows 업데이트 또는 Microsoft 업데이트를 사용하여 업데이트를 계속 수신할 수 있습니다.

    > [!IMPORTANT]
    > GPO(그룹 정책 개체)를 사용하여 클라이언트 소프트웨어를 설치한 경우 해당 클라이언트 소프트웨어를 제거하려면 먼저 해당 GPO(그룹 정책 개체)를 제거해야 소프트웨어가 다시 설치되는 것을 방지할 수 있습니다.

    클라이언트를 제거하지 못한 경우 자세한 내용은 [Endpoint Protection 문제 해결](/intune/troubleshoot/troubleshoot-endpoint-protection-in-microsoft-intune)을 참조하세요.

## 사용자 장치 연결 관리
소프트웨어를 사용자에게 배포하려면 먼저 사용자를 컴퓨터에 연결해야 합니다. 여러 컴퓨터에 사용자를 연결할 수 있지만 각 컴퓨터는 한 사용자에게만 연결할 수 있습니다. 사용자는 회사 포털을 사용하여 Intune에 등록한 모든 컴퓨터에 자동으로 연결됩니다.

### 사용자를 컴퓨터에 연결하려면

1.  [Microsoft Intune 관리 콘솔](https://manage.microsoft.com/)에서 **그룹** &gt; **모든 장치**(또는 사용자에게 연결하려는 컴퓨터가 포함된 다른 그룹)를 선택합니다.

2.  사용자를 연결할 컴퓨터를 선택한 후 **사용자 연결**을 선택합니다.

     **사용자 연결** 대화 상자에는 표시 이름과 함께 사용 가능한 사용자, 사용자 ID 및 각 사용자가 현재 연결되어 있는 컴퓨터 수의 목록이 표시됩니다. 사용자가 선택한 컴퓨터에 이미 연결되어 있는 경우 해당 사용자 이름과 사용자 ID가 **현재 사용자**아래에 표시됩니다. 컴퓨터가 어떤 사용자에게도 연결되지 않은 경우 **현재 사용자** 아래에 **사용자 없음**이 표시됩니다.

3.  다음 중 하나를 수행합니다.

    -   현재 사용자(있는 경우)에 연결되어 있는 컴퓨터를 그대로 두려면 **취소**를 선택합니다.

    -   현재 사용자에 대한 연결(있는 경우)을 제거하려면 **연결 제거** &gt; **확인**을 선택합니다.

    -   새 사용자와 컴퓨터를 연결하려면 **모든 사용자** 목록에서 사용자를 선택합니다. 사용자 데이터가 올바른지 확인한 후 **확인**을 선택합니다.

> [!TIP]
> 최종 사용자가 컴퓨터에 자신을 연결하는 기능을 제한하려면 **Microsoft Intune 에이전트 설정** 정책에서 **사용자와 컴퓨터를 연결하는 기능 제한** 옵션을 설정합니다.

## Intune 클라이언트 소프트웨어를 사용하는 Windows PC에 대한 원격 지원 요청 및 제공

Microsoft Intune은 [TeamViewer](https://www.teamviewer.com) 소프트웨어를 사용하여 Intune 클라이언트 소프트웨어를 실행하는 PC의 사용자가 원격 지원을 받을 수 있게 할 수 있습니다. 사용자가 Microsoft Intune Center의 도움을 요청하는 경우 이를 안내하는 알림이 표시되므로 해당 요청을 수신한 후 지원을 제공할 수 있습니다.
이 기능은 Intune에서 기존의 Windows 원격 지원 기능을 대체합니다.


### 시작하기 전에

원격 지원을 설정하고 원격 지원 요청에 응답하려면 먼저, 다음과 같은 선행 조건을 충족했는지 확인해야 합니다.

- TeamViewer 웹 사이트에 로그인하기 위한 [TeamViewer 계정을 등록](https://login.teamviewer.com/LogOn#register)해야 합니다.
- 관리하려는 Windows PC를 [Windows PC 클라이언트에서 관리](manage-windows-pcs-with-microsoft-intune.md)해야 합니다.
- Intune에서 지원하는 모든 Windows PC 운영 체제를 관리할 수 있어야 합니다.

### TeamViewer 커넥터 구성

1. [Microsoft Intune 관리 콘솔](https://manage.microsoft.com)에서 **관리자**를 선택합니다.
2. **관리자** 작업 영역에서 **TeamViewer**를 선택합니다.
3. **TeamViewer** 페이지의 **TeamViewer 커넥터**에서 **사용**을 선택합니다.
4. **TeamViewer 사용** 대화 상자에서 사용 조건을 확인한 후 **동의**합니다. TeamViewer 라이선스가 아직 없는 경우 **TeamViewer 라이선스 구입**을 선택합니다.
5. TeamViewer 브라우저 창이 열리면 TeamViewer 자격 증명을 사용하여 사이트에 로그인합니다.
6. TeamViewer 사이트에서 옵션을 읽은 후 동의하여 Intune에서 TeamViewer에 연결하도록 합니다.
7. Intune 콘솔에서 **TeamViewer 커넥터** 항목이 **사용**으로 표시되는지 확인합니다.


### 원격 지원 요청 열기(최종 사용자)

1. 클라이언트 Windows PC에서 **Microsoft Intune Center**를 엽니다.
2. **원격 지원** 아래에서 **원격 지원 요청**을 선택합니다.
3. 요청을 승인하면(아래 참조) 클라이언트에서 TeamViewer가 열립니다. 사용자는 웹 브라우저에서 TeamViewer 응용 프로그램을 열려고 한다는 사실을 나타내는 메시지에 동의해야 합니다.
4. PC를 제어하도록 허용할지 묻는 메시지가 사용자에게 표시됩니다. 계속하려면 이 메시지에 동의해야 합니다.
5. 원격 지원 세션 중 연결되어 있음을 보여 주는 창이 사용자에게 표시됩니다. 사용자가 이 창을 닫으면 원격 세션이 종료됩니다.

### 원격 지원 요청에 응답

1. 사용자가 원격 지원 요청을 제출하는 경우 **경고** 작업 영역의 **모니터링** > **원격 지원**에서 해당 요청을 확인할 수 있습니다. 예를 들면 다음과 같습니다.
> ![원격 지원 요청 스크린샷](./media/team-viewer.png)

<br>요청에 대해 4시간 이상 동안 답변하지 않으면 해당 요청이 제거됩니다.
2. 요청을 수락하려면 **요청을 승인하고 원격 지원을 시작합니다.**를 선택합니다.
3. **새 원격 지원 요청이 보류 중입니다.** 대화 상자에서 **원격 지원 요청 수락**을 선택합니다. 아직 설치되어 있지 않은 경우 TeamViewer가 컴퓨터에 필요한 모든 앱을 설치합니다.
4. 그런 다음, TeamViewer가 최종 사용자에게 PC 제어를 허용하려는지 묻는 알림을 표시합니다. 사용자가 그 요청을 수락하면 TeamViewer 창이 열리며, PC를 제어할 수 있게 됩니다.

원격 지원 세션에서 작업하는 동안, 사용 가능한 모든 TeamViewer 명령을 사용하여 원격 PC를 제어할 수 있습니다. 이러한 명령의 도움말을 보려면 TeamViewer 웹 사이트에서 [원격 제어 매뉴얼](http://www.teamviewer.com/en/support/documents/)을 다운로드하세요.

### 원격 지원 세션 닫기

**TeamViewer** 창의 **작업** 메뉴에서 **세션 끝내기**를 선택합니다.



<!--HONumber=Aug16_HO1-->

