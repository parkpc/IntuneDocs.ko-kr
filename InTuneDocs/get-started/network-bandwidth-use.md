---
title: "Intune 네트워크 대역폭 사용 | Microsoft 문서"
description: "Intune 네트워크 대역폭 사용"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0f737d48-24bc-44cd-aadd-f0a1d59f6893
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 0f5972171349325eeb750e552481cbcf903fdf95
ms.openlocfilehash: 9f1cd7ea3e92ac2e3a1b828e8185961060a7c619


---

# <a name="intune-network-bandwidth-use"></a>Intune 네트워크 대역폭 사용

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

이 지침은 기업에서 장치 관리를 담당하는 시스템 관리자용으로 작성되었습니다. 모바일 장치에서 Intune을 사용하는 방법에 대한 도움말은 [Intune 회사 포털에 대한 질문과 대답](https://docs.microsoft.com/intune/enduser/company-portal-frequently-asked-questions)을 참조하세요.

Microsoft Intune을 설정하기 전에 이 항목과 [Microsoft Intune을 시작하기 전에 알아두어야 할 사항](what-to-know-before-you-start-microsoft-intune.md)에 나열된 요구 사항을 검토합니다.

다음 섹션의 정보를 참조하여 Microsoft Intune 클라이언트의 네트워크 트래픽에 대한 계획을 세울 수 있습니다.

## <a name="average-network-traffic"></a>평균 네트워크 트래픽
이 표에는 각 클라이언트의 네트워크를 통해 전송되는 공통 콘텐츠의 대략적인 크기 및 주기가 정리되어 있습니다.

> [!NOTE]
> 컴퓨터와 모바일 장치가 Intune 서비스의 필수 업데이트 및 콘텐츠를 받을 수 있도록 하려면 해당 장치를 인터넷에 주기적으로 연결해야 합니다. 업데이트나 콘텐츠를 받는 데 걸리는 시간은 경우에 따라 다르지만 대략적으로는 매일 1시간 이상 인터넷에 계속 연결된 상태를 유지해야 합니다.

|콘텐츠 유형|대략적인 크기|주기 및 세부 정보|
|----------------|--------------------|-------------------------|
|Intune 클라이언트 설치<br /><br />**Intune 클라이언트 설치 외에도 다음 요구 사항을 충족해야 합니다.**|125 MB|**한 번**<br /><br />클라이언트 다운로드 크기는 클라이언트 컴퓨터의 운영 체제에 따라 다릅니다.|
|클라이언트 등록 패키지|15 MB|**한 번**<br /><br />이 콘텐츠 유형에 대한 업데이트가 있는 경우 추가로 다운로드할 수 있습니다.|
|Endpoint Protection 에이전트|65 MB|**한 번**<br /><br />이 콘텐츠 유형에 대한 업데이트가 있는 경우 추가로 다운로드할 수 있습니다.|
|Operations Manager 에이전트|11 MB|**한 번**<br /><br />이 콘텐츠 유형에 대한 업데이트가 있는 경우 추가로 다운로드할 수 있습니다.|
|정책 에이전트|3 MB|**한 번**<br /><br />이 콘텐츠 유형에 대한 업데이트가 있는 경우 추가로 다운로드할 수 있습니다.|
|Microsoft Easy Assist 에이전트를 통한 원격 지원|6 MB|**한 번**<br /><br />이 콘텐츠 유형에 대한 업데이트가 있는 경우 추가로 다운로드할 수 있습니다.|
|클라이언트의 일별 작업|6 MB|**매일**<br /><br />Intune 클라이언트는 Intune 서비스와 정기적으로 통신하여 업데이트 및 정책을 확인하고 클라이언트의 상태를 서비스에 보고합니다.|
|Endpoint Protection 맬웨어 정의 업데이트|상황에 따라 다름<br /><br />일반적으로 40KB -2MB|**매일**<br /><br />하루에 최대&3;번|
|Endpoint Protection 엔진 업데이트|5 MB|**매월**|
|소프트웨어 업데이트|상황에 따라 다름<br /><br />크기는 배포하는 업데이트에 따라 달라집니다.|**매월**<br /><br />일반적으로 소프트웨어 업데이트는 매월 두 번째 화요일에 배포됩니다.<br /><br />새로 등록되거나 배포된 컴퓨터는 이전에 배포된 업데이트의 전체 집합을 다운로드하는 동안 네트워크 대역폭을 추가로 사용할 수 있습니다.|
|서비스 팩|상황에 따라 다름<br /><br />크기는 배포하는 각 서비스 팩에 따라 달라집니다.|**상황에 따라 다름**<br /><br />서비스 팩을 배포하는 시기에 따라 달라집니다.|
|소프트웨어 배포|상황에 따라 다름<br /><br />크기는 배포하는 소프트웨어에 따라 달라집니다.|**상황에 따라 다름**<br /><br />소프트웨어를 배포하는 시기에 따라 달라집니다.|

## <a name="ways-to-reduce-network-bandwidth-use"></a>네트워크 대역폭 사용량을 줄이는 방법
다음 방법 중 하나 이상을 사용하여 Intune 클라이언트의 네트워크 대역폭 사용을 줄일 수 있습니다.

### <a name="use-a-proxy-server-to-cache-content-requests"></a>프록시 서버를 사용하여 콘텐츠 요청 캐시
콘텐츠를 캐시할 수 있는 프록시 서버를 사용하여 중복 다운로드를 줄이고 인터넷에서 콘텐츠를 요청하는 클라이언트의 네트워크 대역폭 사용량을 줄일 수 있습니다.

캐싱 프록시 서버는 네트워크에 있는 클라이언트 컴퓨터로부터 콘텐츠에 대한 요청을 받고 인터넷에서 해당 콘텐츠를 검색한 후 HTTP 응답 및 이진 다운로드를 모두 캐시할 수 있습니다. 서버는 캐시된 정보를 사용하여 Intune 클라이언트 컴퓨터의 후속 요청에 응답합니다.

다음은 Intune 클라이언트의 콘텐츠를 캐시할 프록시 서버에 사용하는 일반적인 설정입니다.

|설정|권장 값|세부 정보|
|-----------|---------------------|-----------|
|캐시 크기|5GB - 30GB|값은 사용하는 구성 및 네트워크의 클라이언트 컴퓨터의 수에 따라 달라집니다. 파일이 너무 빠르게 삭제되지 않도록 하려면 환경에 맞게 캐시 크기를 조정하세요.|
|개별 캐시 파일 크기|950 MB|이 설정은 모든 캐싱 프록시 서버에서 사용할 수 없습니다.|
|캐시할 개체 유형|HTTP<br /><br />HTTPS<br /><br />BITS|Intune 패키지는 HTTP를 통한 BITS(Background Intelligent Transfer Service) 다운로드로 검색되는 CAB 파일입니다.|
프록시 서버를 사용하여 콘텐츠를 캐시하는 방법에 대해서는 사용 중인 프록시 서버 솔루션의 설명서를 참조하세요.

### <a name="use-background-intelligent-transfer-service-on-computers"></a>컴퓨터에서 BITS(Background Intelligent Transfer Service) 사용
Intune은 Windows 컴퓨터에서 BITS(Background Intelligent Transfer Service)를 사용할 수 있도록 지원하여 구성한 시간 동안 컴퓨터에서 사용하는 네트워크 대역폭을 줄여 줍니다. Intune 에이전트 정책의 **네트워크 대역폭** 페이지에서 BITS에 대한 정책을 구성할 수 있습니다.

BITS 및 Windows 컴퓨터에 대한 자세한 내용은 TechNet 라이브러리의 [Background Intelligent Transfer Service](http://technet.microsoft.com/library/bb968799.aspx)를 참조하세요.

### <a name="use-branchcache-on-computers"></a>컴퓨터에서 BranchCache 사용
Intune 클라이언트는 BranchCache를 사용하여 WAN(광역 네트워크) 트래픽을 줄일 수 있습니다. 클라이언트로 지원되는 다음 운영 체제에서도 BranchCache를 지원합니다.

- Windows 7
- Windows 8.0
- Windows 8.1
- Windows 10

BranchCache를 사용하려면 클라이언트 컴퓨터에서 BranchCache를 사용하도록 설정한 후 **분산 캐시 모드**에 대해 구성해야 합니다.

기본적으로, BranchCache 및 분산 캐시 모드는 Intune 클라이언트를 설치할 때 컴퓨터에서 사용되도록 설정됩니다. 그러나 클라이언트의 기존 그룹 정책에서 BranchCache를 사용하지 않도록 설정하는 경우 Intune에서 해당 정책을 재정의하지 않으므로 BranchCache는 해당 컴퓨터에서 계속 사용되지 않도록 설정됩니다.

BranchCache를 사용하는 경우 조직에서 그룹 정책 및 Intune 방화벽 정책을 관리하는 다른 관리자와 협의하여 BranchCache 또는 방화벽 예외를 사용하지 않도록 설정하는 정책을 배포하지 않아야 합니다. BranchCache에 대한 자세한 내용은 [BranchCache 개요](http://technet.microsoft.com/library/hh831696.aspx)를 참조하세요.

## <a name="network-communication-requirements"></a>네트워크 통신 요구 사항

Intune 구독을 관리하기 위해 관리 및 사용하는 장치와 클라우드 기반 서비스에 필요한 웹 사이트 간에 네트워크 통신을 사용하도록 설정해야 합니다.

Intune은 Intune 소프트웨어를 실행하는 서버와 같은 온-프레미스 인프라를 사용하지 않지만 Exchange 및 Active Directory 동기화 도구를 비롯하여 온-프레미스 인프라를 사용할 수 있는 옵션은 있습니다.

방화벽 및 프록시 서버로 보호되는 컴퓨터를 관리하려면 Intune에 대한 통신을 허용하도록 방화벽 및 프록시 서버를 설정해야 합니다.

### <a name="requirements-for-proxy-servers"></a>프록시 서버에 대한 요구 사항
프록시 서버로 보호되는 컴퓨터를 관리하려면 다음 사항에 유의하세요.

-   프록시 서버는 **HTTP**와 **HTTPS**를 모두 지원해야 합니다. Intune 클라이언트에서 두 프로토콜을 모두 사용하기 때문입니다.
-   Intune은 인증되지 않은 프록시 서버를 지원합니다.

개별 클라이언트 컴퓨터에서 프록시 서버 설정을 수정할 수도 있고, 그룹 정책을 사용하여 지정된 프록시 서버로 보호되는 모든 클라이언트 컴퓨터의 설정을 변경할 수도 있습니다.

### <a name="requirements-for-firewalls-ports-and-domains"></a>방화벽, 포트 및 도메인의 요구 사항
관리되는 장치를 사용하려면 **모든 사용자**가 방화벽을 통해 서비스에 액세스할 수 있도록 구성해야 합니다.

다음 표에는 Intune 클라이언트에서 액세스하는 포트 및 서비스가 정리되어 있습니다.

|**도메인**|**포트**|**IP 주소**|
|------|----|---|
|manage.microsoft.com<br>a.manage.microsoft.com<br>admin.manage.microsoft.com<br>enterpriseenrollment.manage.microsoft.com<br>enterpriseenrollment-s.manageenterpriseenrollment-s.manage.microsoft.com<br>i.manage.microsoft.com<br>p.manage.microsoft.com<br>r.manage.microsoft.com|80 및 443|134.170.168.254<br>134.170.51.126
|m.manage.microsoft.com|80 및 443| 13.91.59.243<br>40.68.30.140
|portal.manage.microsoft.com|80 및 443|40.121.50.69<br>52.169.30.159
|account.manage.microsoft.com|80 및 443|157.56.13.59
|fef.msua01.manage.microsoft.com|80 및 443|138.91.243.97
|fef.msua02.manage.microsoft.com|80 및 443|23.96.112.46
|fef.msua04.manage.microsoft.com|80 및 443|23.96.112.28
|fef.msua05.manage.microsoft.com|80 및 443|138.91.244.151
|fef.msub01.manage.microsoft.com|80 및 443|137.135.128.214
|fef.msub02.manage.microsoft.com|80 및 443|137.135.130.29
|fef.msub03.manage.microsoft.com|80 및 443|23.97.165.17
|fef.msub05.manage.microsoft.com|80 및 443|23.97.166.52
|fef.msuc01.manage.microsoft.com|80 및 443|207.46.225.1
|fef.msuc02.manage.microsoft.com|80 및 443|23.98.66.118
|fef.msuc03.manage.microsoft.com|80 및 443|23.101.0.100
|fef.msuc05.manage.microsoft.com|80 및 443|207.46.154.33
|fef.msua06.manage.microsoft.com|80 및 443|104.42.188.1
|fei.msua01.manage.microsoft.com|80 및 443|138.91.240.131
|fei.msua02.manage.microsoft.com|80 및 443|23.96.112.143
|fei.msua04.manage.microsoft.com|80 및 443|23.96.112.147
|fei.msua05.manage.microsoft.com|80 및 443|138.91.240.163
|fei.msub01.manage.microsoft.com|80 및 443|137.135.130.85
|fei.msub02.manage.microsoft.com|80 및 443|137.135.132.149
|fei.msub03.manage.microsoft.com|80 및 443|23.97.160.232
|fei.msub05.manage.microsoft.com|80 및 443|23.97.162.250
|fei.msuc01.manage.microsoft.com|80 및 443|207.46.224.73
|fei.msuc02.manage.microsoft.com|80 및 443|23.98.66.194
|fei.msuc03.manage.microsoft.com|80 및 443|23.101.2.105
|fei.msuc05.manage.microsoft.com|80 및 443|207.46.147.126
|fei.msua06.manage.microsoft.com|80 및 443|138.91.149.190
|m.fei.msua01.manage.microsoft.com|80 및 443|138.91.240.131
|m.fei.msua02.manage.microsoft.com|80 및 443|23.96.112.143
|m.fei.msua04.manage.microsoft.com|80 및 443|23.96.112.147
|m.fei.msua05.manage.microsoft.com|80 및 443|138.91.240.163
|m.fei.msub01.manage.microsoft.com|80 및 443|137.135.130.85
|m.fei.msub02.manage.microsoft.com|80 및 443|137.135.132.149
|m.fei.msub03.manage.microsoft.com|80 및 443|23.97.160.232
|m.fei.msub05.manage.microsoft.com|80 및 443|23.97.162.250
|m.fei.msuc01.manage.microsoft.com|80 및 443|207.46.224.73
|m.fei.msuc02.manage.microsoft.com|80 및 443|23.98.66.194
|m.fei.msuc03.manage.microsoft.com|80 및 443|23.101.2.105
|m.fei.msuc05.manage.microsoft.com|80 및 443|207.46.147.126
|m.fei.msua06.manage.microsoft.com|80 및 443|138.91.149.190
|m.msua01.manage.microsoft.com|80 및 443|157.55.50.182
|m.msua02.manage.microsoft.com|80 및 443|134.170.49.121
|m.msua04.manage.microsoft.com|80 및 443|134.170.49.126
|m.msua05.manage.microsoft.com|80 및 443|157.55.240.190
|m.msua06.manage.microsoft.com|80 및 443|134.170.49.114
|m.msub01.manage.microsoft.com|80 및 443|94.245.121.50
|m.msub02.manage.microsoft.com|80 및 443|94.245.121.58
|m.msub03.manage.microsoft.com|80 및 443|94.245.121.56
|m.msub05.manage.microsoft.com|80 및 443|157.56.113.123
|m.msuc01.manage.microsoft.com|80 및 443|104.44.84.187
|m.msuc02.manage.microsoft.com|80 및 443|104.44.84.188
|m.msuc03.manage.microsoft.com|80 및 443|104.44.84.189
|m.msuc05.manage.microsoft.com|80 및 443|111.221.76.60
|msua01.manage.microsoft.com|80 및 443|157.55.50.182
|msua02.manage.microsoft.com|80 및 443|134.170.49.121
|msua04.manage.microsoft.com|80 및 443|134.170.49.126
|msua05.manage.microsoft.com|80 및 443|157.55.240.190
|msub01.manage.microsoft.com|80 및 443|94.245.121.50
|msub02.manage.microsoft.com|80 및 443|94.245.121.58
|msub03.manage.microsoft.com|80 및 443|94.245.121.56
|msub05.manage.microsoft.com|80 및 443|157.56.113.123
|msuc01.manage.microsoft.com|80 및 443|104.44.84.187
|msuc02.manage.microsoft.com|80 및 443|104.44.84.188
|msuc03.manage.microsoft.com|80 및 443|104.44.84.189
|msuc05.manage.microsoft.com|80 및 443|111.221.76.60
|msua06.manage.microsoft.com|80 및 443|134.170.49.114
|ncufun.account.manage.microsoft.com|80 및 443|157.55.252.224
|neufun.account.manage.microsoft.com|80 및 443|65.52.229.134
|portal.fei.msua01.manage.microsoft.com|80 및 443|138.91.240.131
|portal.fei.msua02.manage.microsoft.com|80 및 443|23.96.112.143
|portal.fei.msua04.manage.microsoft.com|80 및 443|23.96.112.147
|portal.fei.msua05.manage.microsoft.com|80 및 443|138.91.240.163
|portal.fei.msub01.manage.microsoft.com|80 및 443|137.135.130.85
|portal.fei.msub02.manage.microsoft.com|80 및 443|137.135.132.149
|portal.fei.msub03.manage.microsoft.com|80 및 443|23.97.160.232
|portal.fei.msub05.manage.microsoft.com|80 및 443|23.97.162.250
|portal.fei.msuc01.manage.microsoft.com|80 및 443|207.46.224.73
|portal.fei.msuc02.manage.microsoft.com|80 및 443|23.98.66.194
|portal.fei.msuc03.manage.microsoft.com|80 및 443|23.101.2.105
|portal.fei.msuc05.manage.microsoft.com|80 및 443|207.46.147.126
|portal.fei.msua06.manage.microsoft.com|80 및 443|138.91.149.190
|portal.msua01.manage.microsoft.com|80 및 443|157.55.50.182
|portal.msua02.manage.microsoft.com|80 및 443|134.170.49.121
|portal.msua04.manage.microsoft.com|80 및 443|134.170.49.126
|portal.msua05.manage.microsoft.com|80 및 443|157.55.240.190
|portal.msub01.manage.microsoft.com|80 및 443|94.245.121.50
|portal.msub02.manage.microsoft.com|80 및 443|94.245.121.58
|portal.msub03.manage.microsoft.com|80 및 443|94.245.121.56
|portal.msub05.manage.microsoft.com|80 및 443|157.56.113.123
|portal.msuc01.manage.microsoft.com|80 및 443|104.44.84.187
|portal.msuc02.manage.microsoft.com|80 및 443|104.44.84.188
|portal.msuc03.manage.microsoft.com|80 및 443|104.44.84.189
|portal.msuc05.manage.microsoft.com|80 및 443|111.221.76.60
|portal.msua06.manage.microsoft.com|80 및 443|134.170.49.114
|ssu2.manage.microsoft.com|80 및 443|157.55.99.181
|status.manage.microsoft.com|80 및 443|157.55.99.170
|swda01.manage.microsoft.com<br>swda02.manage.microsoft.com<br>swdb01.manage.microsoft.com<br>swdb02.manage.microsoft.com<br>swdc01.manage.microsoft.com<br>swdc02.manage.microsoft.com|80 및 443|93.184.215.200
|*.microsoftonline-p.com|80 및 443||
|has.spserv.microsoft.com<br>장치 상태 증명 서비스에 필요|443||
|*.microsoftonline-p.net|80 및 443||
|*.portal.office.com|80 및 443||
|*.spynet2.microsoft.com|443||
|c.microsoft.com|80 및 443||
|c1.microsoft.com|80 및 443||
|blob.core.windows.net|80 및 443||
|ajax.aspnetcdn.com|80 및 443||
|*.googleapis.com<br>이 도메인은 회사 포털 웹 사이트를 사용할 경우 JQuery 지원에 필요합니다.|80 및 443||
|wustat.microsoft.com|80 및 443||
|Microsoft 업데이트 서비스|\*.update.microsoft.com<br>download.microsoft.com<br>update.microsoft.com<br>\*.download.windowsupdate.com<br>download.windowsupdate.com<br>\*.windowsupdate.com<br>windowsupdate.microsoft.com<br>ntservicepack.microsoft.com|80 및 443|
|DNS 조회 요청|manage.microsoft.com.nsatc.net|80|
|방화벽을 통한 삼성 KNOX 표준 장치 통신|방화벽을 통해 삼성 KNOX 표준 장치를 서버에 연결할 수 있도록 하려면 삼성 KNOX 표준 FAQ의 지침을 따르세요.||
|조건부 액세스 통신|443|204.79.197.200|
|설명서, 도움말 및 지원:</br></br>*.livemeeting.com<br>\*.microsoftonline.com<br>\*.social.technet.microsoft.com<br>blogs.technet.com<br>go.microsoft.com<br>onlinehelp.microsoft.com<br>www.microsoft.com|80|||

>[!div class="step-by-step"]

>[&larr;**필수 조건**](what-to-know-before-you-start-microsoft-intune.md)[**구독**     &rarr;](start-with-a-paid-subscription-to-microsoft-intune-step-1.md)  



<!--HONumber=Feb17_HO2-->


