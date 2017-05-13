---
title: "Intune 네트워크 대역폭 사용 | Microsoft 문서"
description: "Intune 네트워크 대역폭 사용"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 05/04/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0f737d48-24bc-44cd-aadd-f0a1d59f6893
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 33febef8787887401960592d95356347f6917681
ms.openlocfilehash: 5d32729fe5c7188b018e4baad99e4d35b8977086
ms.contentlocale: ko-kr
ms.lasthandoff: 05/04/2017


---

# <a name="intune-network-bandwidth-use"></a>Intune 네트워크 대역폭 사용

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune 관리자는 이 문서의 지침을 참조하여 Intune 서비스의 네트워크 요구 사항을 파악할 수 있습니다. 이 문서의 정보를 참조하여 프록시 설정에 필요한 IP 주소 및 포트 설정과 대역폭 요구 사항을 파악할 수 있습니다.

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
|Endpoint Protection 맬웨어 정의 업데이트|상황에 따라 다름<br /><br />일반적으로 40KB -2MB|**매일**<br /><br />하루에 최대 3번|
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

방화벽 및 프록시 서버로 보호되는 컴퓨터를 관리하려면 Intune에 대한 통신을 허용하도록 방화벽 및 프록시 서버를 설정해야 합니다. 프록시 서버로 보호되는 컴퓨터를 관리하려면 다음 사항에 유의하세요.

-   프록시 서버는 **HTTP(80)**와 **HTTPS(443)**를 모두 지원해야 합니다. Intune 클라이언트에서 두 프로토콜을 모두 사용하기 때문입니다.
-   Intune은 인증되지 않은 프록시 서버를 지원합니다.

개별 클라이언트 컴퓨터에서 프록시 서버 설정을 수정할 수도 있고, 그룹 정책을 사용하여 지정된 프록시 서버로 보호되는 모든 클라이언트 컴퓨터의 설정을 변경할 수도 있습니다.

관리되는 장치를 사용하려면 **모든 사용자**가 방화벽을 통해 서비스에 액세스할 수 있도록 구성해야 합니다.

다음 표에는 Intune 클라이언트에서 액세스하는 포트 및 서비스가 정리되어 있습니다.

|**도메인**|**IP 주소**|
|---------------------|-----------|
|portal.manage.microsoft.com<br> m.manage.microsoft.com |40.86.181.86<br>13.82.59.78<br>13.74.184.100<br>40.68.188.2<br>13.75.42.6<br>52.230.25.184 |
| sts.manage.microsoft.com | 13.93.223.241 <br>52.170.32.182 <br>52.164.224.159 <br>52.174.178.4 <br>13.75.122.143 <br>52.163.120.84|
|Manage.microsoft.com <br>i.manage.microsoft.com <br>r.manage.microsoft.com <br>a.manage.microsoft.com <br>p.manage.microsoft.com <br>EnterpriseEnrollment.manage.microsoft.com <br>EnterpriseEnrollment-s.manage.microsoft.com | 104.40.82.191 <br>13.82.96.212 <br>52.169.9.87 <br>52.174.26.23 <br>40.83.123.72 <br>13.76.177.110 |
|portal.fei.msua01.manage.microsoft.com<br>m.fei.msua01.manage.microsoft.com |13.64.196.170|
|fei.msua01.manage.microsoft.com<br> portal.fei.msua01.manage.microsoft.com <br>m.fei.msua01.manage.microsoft.com |40.71.34.120 |
|fei.msua02.manage.microsoft.com<br>portal.fei.msua02.manage.microsoft.com<br>m.fei.msua02.manage.microsoft.com |13.64.198.190|
|fei.msua02.manage.microsoft.com<br>portal.fei.msua02.manage.microsoft.com<br> m.fei.msua02.manage.microsoft.com |    13.64.198.190|
|fei.msua04.manage.microsoft.com<br> portal.fei.msua04.manage.microsoft.com <br>m.fei.msua04.manage.microsoft.com |13.64.188.173|
|fei.msua04.manage.microsoft.com<br> portal.fei.msua04.manage.microsoft.com <br>m.fei.msua04.manage.microsoft.com |40.71.32.174|
|fei.msua05.manage.microsoft.com <br>portal.fei.msua05.manage.microsoft.com <br>m.fei.msua05.manage.microsoft.com |13.64.197.181 |
|fei.msua05.manage.microsoft.com <br>portal.fei.msua05.manage.microsoft.com <br>m.fei.msua05.manage.microsoft.com |40.71.38.205|
|fei.amsua0502.manage.microsoft.com <br>portal.fei.amsua0502.manage.microsoft.com <br>m.fei.amsua0502.manage.microsoft.com |13.64.191.182 |
|fei.amsua0502.manage.microsoft.com <br>portal.fei.amsua0502.manage.microsoft.com <br>m.fei.amsua0502.manage.microsoft.com |40.71.37.51 |
|fei.msua06.manage.microsoft.com <br>portal.fei.msua06.manage.microsoft.com <br>m.fei.msua06.manage.microsoft.com |40.118.250.246 |
|fei.msua06.manage.microsoft.com <br>portal.fei.msua06.manage.microsoft.com <br>m.fei.msua06.manage.microsoft.com |13.90.142.194 |
|fei.amsua0602.manage.microsoft.com <br>portal.fei.amsua0602.manage.microsoft.com <br>m.fei.amsua0602.manage.microsoft.com |13.64.250.226 |
|fei.amsua0602.manage.microsoft.com <br>portal.fei.amsua0602.manage.microsoft.com <br>m.fei.amsua0602.manage.microsoft.com |13.90.151.142 |
|fei.msub01.manage.microsoft.com <br>portal.fei.msub01.manage.microsoft.com <br>m.fei.msub01.manage.microsoft.com |52.169.155.165 |
|fei.msub01.manage.microsoft.com <br>portal.fei.msub01.manage.microsoft.com <br>m.fei.msub01.manage.microsoft.com |52.174.188.97 |
|fei.amsub0102.manage.microsoft.com <br>portal.fei.amsub0102.manage.microsoft.com <br>m.fei.amsub0102.manage.microsoft.com |52.178.190.24 |
|fei.amsub0102.manage.microsoft.com <br>portal.fei.amsub0102.manage.microsoft.com <br>m.fei.amsub0102.manage.microsoft.com |52.174.16.215 |
|fei.msub02.manage.microsoft.com <br>portal.fei.msub02.manage.microsoft.com <br>m.fei.msub02.manage.microsoft.com |40.69.69.27 |
|fei.msub02.manage.microsoft.com <br>portal.fei.msub02.manage.microsoft.com <br>m.fei.msub02.manage.microsoft.com |52.166.196.199 |
|fei.msub03.manage.microsoft.com <br>portal.fei.msub03.manage.microsoft.com <br>m.fei.msub03.manage.microsoft.com |40.69.71.164 |
|fei.msub03.manage.microsoft.com <br>portal.fei.msub03.manage.microsoft.com <br>m.fei.msub03.manage.microsoft.com |52.174.182.102 |
|fei.msub05.manage.microsoft.com <br>portal.fei.msub05.manage.microsoft.com <br>m.fei.msub05.manage.microsoft.com |40.69.78.145 |
|fei.msub05.manage.microsoft.com <br>portal.fei.msub05.manage.microsoft.com <br>m.fei.msub05.manage.microsoft.com |52.174.192.105 |
|fei.msuc01.manage.microsoft.com <br>portal.fei.msuc01.manage.microsoft.com <br>m.fei.msuc01.manage.microsoft.com |13.94.46.250|
|fei.msuc01.manage.microsoft.com <br>portal.fei.msuc01.manage.microsoft.com <br>m.fei.msuc01.manage.microsoft.com |52.163.119.15 |
|fei.msuc02.manage.microsoft.com <br>portal.fei.msuc02.manage.microsoft.com <br>m.fei.msuc02.manage.microsoft.com |13.75.124.145 |
|fei.msuc02.manage.microsoft.com <br>portal.fei.msuc02.manage.microsoft.com <br>m.fei.msuc02.manage.microsoft.com |52.163.119.5|
|fei.msuc03.manage.microsoft.com <br>portal.fei.msuc03.manage.microsoft.com <br>m.fei.msuc03.manage.microsoft.com |52.175.35.226|
|fei.msuc03.manage.microsoft.com <br>portal.fei.msuc03.manage.microsoft.com <br>m.fei.msuc03.manage.microsoft.com |52.163.119.6|
|fei.msuc05.manage.microsoft.com <br>portal.fei.msuc05.manage.microsoft.com <br>m.fei.msuc05.manage.microsoft.com |52.175.38.24|
|fei.msuc05.manage.microsoft.com <br>portal.fei.msuc05.manage.microsoft.com <br>m.fei.msuc05.manage.microsoft.com |52.163.119.3|

