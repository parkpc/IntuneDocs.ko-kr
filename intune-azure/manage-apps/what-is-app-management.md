---
title: "앱 관리란? | Intune Azure 미리 보기 | Microsoft Docs"
description: "Intune Azure 미리 보기: 이 항목에서는 Microsoft Intune을 사용한 앱 관리의 기본 사항을 알아봅니다."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/23/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1975a2dc-3a14-4cb9-9afb-e2ba01a1c51b
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 424fae862592c1ab5b4221fb5ad40a52c39f6760
ms.openlocfilehash: 33bc87d16834cb2950cc7c66ad4887dddb12e811


---

# <a name="what-is-app-management"></a>앱 관리란?


[!INCLUDE[azure_preview](../includes/azure_preview.md)]


IT 관리자는 최종 사용자가 작업 수행에 필요한 앱에 액세스할 수 있도록 해야 합니다. 이는 다음과 같은 이유로 까다로운 일일 수 있습니다.
- 장치 플랫폼 및 앱 유형이 광범위합니다.
- 회사 장치뿐만 아니라 사용자 소유 장치의 앱을 관리해야 할 수도 있습니다.
- 네트워크와 데이터의 보안을 유지하면서 이 모든 작업을 수행해야 합니다. 

또한 Intune에 등록되지 않은 장치에서 앱을 할당하고 관리할 수 있습니다.

Intune에서는 원하는 장치에서 필요한 앱을 얻도록 도와주는 다양한 기능을 제공합니다.

## <a name="app-management-capabilities-by-platform"></a>플랫폼별 앱 관리 기능

||||||
|-|-|-|-|-|
|&nbsp; |Android|iOS|Windows Phone 8.1|Windows 10|
|장치 및 사용자에게 앱 추가 및 할당|예|예|예|예|
|Intune에 등록되지 않은 장치에 앱 할당|예|예|아니요|아니요|
|앱 구성 정책을 사용하여 앱의 시작 동작 제어|아니요|예|아니요|아니요|
|앱 보호 정책이 적용되는 앱에서 회사 데이터 보호|예|예|아니요|아니요<sup>1</sup>|
|설치된 앱에서 회사 데이터만 제거(앱 선택적 초기화)|예|예|예|예|
|앱 할당 모니터링|예|예|예|예|
|앱 스토어에서 대량 구매 앱 할당 및 추적|아니요|아니요|아니요|예|
|장치에 앱 필수 설치(필수)<sup>2</sup>|예|예|예|예|
|회사 포털에서 장치에 선택적 설치(사용 가능한 설치)|예|예|예|예|
|웹에서 앱에 바로 가기 설치(웹 클립)|예|예|예|예|
|사내(기간 업무) 앱|예|예|아니요|아니요|
|스토어의 앱|예|예|예|예|
|앱 업데이트|예|예|예|예|

<sup>1</sup> Windows 10을 실행하는 장치에서 앱을 보호하려면 [Windows Information Protection](/intune-azure/configure-devices/how-to-configure-windows-information-protection)을 사용하는 것이 좋습니다.

<sup>2</sup>Intune에서 관리하는 장치에만 적용됩니다.


## <a name="how-to-get-started"></a>시작하는 방법

대부분의 앱 관련 정보는 다음과 같이 액세스할 수 있는 **모바일 앱** 워크로드에서 확인할 수 있습니다.

1. Azure 포털에 로그인합니다.
2. **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
3. **Intune** 블레이드에서 **앱 관리**를 선택합니다.

    ![모바일 앱 워크로드](./media/apps-workload.png)

### <a name="manage"></a>관리
- **앱** - 대부분의 앱을 추가, 할당 및 모니터링할 수 있습니다. 
    - [앱 추가](add-apps.md)
    - [앱 할당](deploy-apps.md)
    - [앱 모니터링](monitor-apps.md)
- **사용이 허가된 앱** - 앱 스토어에서 대량 구매 앱을 보고, 배포하고, 모니터링할 수 있습니다.
    - [비즈니스용 Windows 스토어 대량 구매 앱](wsfb-apps.md)
- **앱 구성 정책** - 앱 구성 정책을 사용하여 사용자가 앱을 실행할 때 필요할 수 있는 설정을 제공할 수 있습니다. 자세한 내용은 다음을 참조하세요.
    - [앱 구성 정책](app-configuration-policies.md)
- **앱 보호 정책** - 설정을 앱에 연결하여 앱에서 사용 중인 회사 데이터를 보호할 수 있습니다. 예를 들어 다른 앱과 통신하는 앱의 기능을 제한하고 사용자에게 회사 앱에 액세스하려면 PIN을 입력하도록 요구할 수 있습니다.
    - [앱 보호 정책](app-protection-policies.md)
- **앱 선택적 초기화** - 선택한 사용자의 장치에서 회사 데이터만 제거합니다.
    - [앱 선택적 초기화](app-selective-wipe.md)

### <a name="monitor"></a>모니터
- **검색된 앱** - Intune에서 할당하고 장치에 설치된 모든 앱을 표시합니다.
- **앱 설치 상태** - 생성한 앱 할당의 상태를 표시합니다.
- **앱 보호 사용자 상태** - 선택한 사용자에 대한 앱 보호 정책의 상태를 표시합니다.

자세한 내용은 [앱 모니터링](monitor-apps.md)을 참조하세요.

### <a name="setup"></a>설정
<!--- **iOS VPP Tokens**
    - [iOS volume-purchased apps](ios-vpp-apps.md) --->
- **비즈니스용 Windows 스토어** - 비즈니스용 Windows 스토어에 대한 통합을 설정합니다. 이렇게 하면 구매한 응용 프로그램을 Intune에 동기화하고 할당한 후 라이선스 사용 현황을 추적할 수 있습니다. 
    - [비즈니스용 Windows 스토어 대량 구매 앱](wsfb-apps.md)
- **회사 포털 브랜딩** - 회사 포털을 사용자 지정하여 회사 브랜딩을 제공할 수 있습니다. 
    - [회사 포털 구성](company-portal-app.md)



<!--HONumber=Feb17_HO1-->


