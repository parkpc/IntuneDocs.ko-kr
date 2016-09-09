---
title: "네트워크 인프라 요구 사항 | Microsoft Intune"
description: "Intune 방화벽, 포트, 도메인 및 프록시 서버 요구 사항"
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 08/29/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 074de65b-84a5-4a01-a824-18ffd838eab0
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 073e3df63a5de9cf92c739c1ced858e21a9ac351
ms.openlocfilehash: aa4d2219a5962d83b80630ed3a09660a76469764


---

# Microsoft Intune의 네트워크 인프라 요구 사항
Microsoft Intune을 설정하기 전에, 이 항목과 [Microsoft Intune을 시작하기 전에 알아두어야 할 사항](what-to-know-before-you-start-microsoft-intune.md) 항목에 나열된 요구 사항을 검토합니다.

이 항목에서는 네트워크 인프라가 Intune 구독을 관리하기 위해 사용 및 관리하는 장치와 클라우드 기반 서비스에서 사용하는 인터넷의 웹 사이트 간에 통신을 전달할 수 있는 요구 사항을 나열합니다.

온-프레미스 인프라(예: 소프트웨어를 설치해야 하는 서버)를 사용하기 위한 요구 사항은 없지만 Exchange 및 Active Directory 동기화 도구를 비롯하여 온-프레미스 인프라를 사용할 수 있는 옵션은 있습니다.

방화벽 및 프록시 서버로 보호되는 컴퓨터를 관리하려면 Intune에 대한 통신을 허용하도록 방화벽 및 프록시 서버를 설정해야 합니다.

## 방화벽, 포트 및 도메인의 요구 사항
관리되는 장치를 사용하려면 **모든 사용자**가 방화벽을 통해 다양한 서비스에 액세스할 수 있도록 구성해야 합니다.

다음 표에는 Intune 클라이언트에서 액세스하는 포트 및 서비스가 정리되어 있습니다.


|**도메인**|**포트**|**IP 주소**|
|------|----|---|
|manage.microsoft.com<br>a.manage.microsoft.com<br>admin.manage.microsoft.com<br>enterpriseenrollment.manage.microsoft.com<br>enterpriseenrollment-s.manageenterpriseenrollment-s.manage.microsoft.com<br>i.manage.microsoft.com<br>m.manage.microsoft.com<br>p.manage.microsoft.com<br>portal.manage.microsoft.com<br>r.manage.microsoft.com|80 및 443|134.170.168.254<br>134.170.51.126
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
|방화벽을 통한 삼성 KNOX 장치 통신|방화벽을 통해 삼성 KNOX 장치를 서버에 연결할 수 있도록 하려면 삼성 KNOX FAQ의 지침을 따르세요.||
|조건부 액세스 통신|443|204.79.197.200|
|설명서, 도움말 및 지원:</br></br>*.livemeeting.com<br>\*.microsoftonline.com<br>\*.social.technet.microsoft.com<br>blogs.technet.com<br>go.microsoft.com<br>onlinehelp.microsoft.com<br>www.microsoft.com|80|||



## 프록시 서버에 대한 요구 사항
프록시 서버로 보호되는 컴퓨터를 관리하려면 다음 사항에 유의하세요.

-   프록시 서버는 **HTTP**와 **HTTPS**를 모두 지원해야 합니다. Intune 클라이언트에서 두 프로토콜을 모두 사용하기 때문입니다.

-   Intune은 인증되지 않은 프록시 서버를 지원합니다.

개별 클라이언트 컴퓨터에서 프록시 서버 설정을 수정할 수도 있고, 그룹 정책을 사용하여 지정된 프록시 서버로 보호되는 모든 클라이언트 컴퓨터의 설정을 변경할 수도 있습니다.

또한 Intune 클라이언트에 사용되는 [네트워크 대역폭을 줄이기](network-bandwidth-use.md) 위해 콘텐츠를 캐시하는 프록시 서버를 사용할 수도 있습니다.


### 참고 항목
[Microsoft Intune을 시작하기 전에 알아두어야 할 사항](what-to-know-before-you-start-microsoft-intune.md)



<!--HONumber=Sep16_HO2-->


