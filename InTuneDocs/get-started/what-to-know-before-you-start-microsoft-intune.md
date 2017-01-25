---
title: "필수 조건 | Microsoft 문서"
description: "Intune 필수 구성 요소 및 요구 사항에 대한 링크"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 01/10/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d1ac59c-a885-4276-8576-f3cf81c2d268
ms.reviewer: angrobe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e2810513646828cc5da734f3af9cc8d81e0c03fc
ms.openlocfilehash: 444d08d1a5e709572efbc2f639cef037453b9c0e


---

# <a name="prerequisites-to-getting-started-with-intune"></a>Intune을 시작하기 위한 필수 구성 요소

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune의 설정을 시작하기 전에 다음 요구 사항을 검토합니다.

- [지원되는 장치 및 컴퓨터](#intune-supported-devices)
- [Intune을 사용하도록 지원되는 웹 브라우저 목록](#intune-supported-web-browsers)

또한 [Intune 네트워크 대역폭 사용량](network-bandwidth-use.md)을 잘 이해해야 합니다.

## <a name="intune-supported-devices"></a>Intune 지원 장치

Intune 모바일 장치 관리 기능을 사용하면 다음과 같은 장치를 관리할 수 있습니다.

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

Intune을 사용하여 Windows Server 운영 체제를 관리할 수는 없습니다.

Intune 장치 관리에서 제공하는 [기능](mobile-device-management-capabilities-in-microsoft-intune.md)을 확인해 보세요.

### <a name="windows-pc-software-client"></a>Windows PC 소프트웨어 클라이언트

Windows PC에서는 대체 등록 방법으로 [Intune 소프트웨어 클라이언트](/intune/deploy-use/manage-windows-pcs-with-microsoft-intune)를 배포하고 설치할 수 있습니다. Intune 소프트웨어 클라이언트를 사용하면 Windows 7 이상 버전(Windows 10 Home Edition은 제외)을 실행하는 PC를 관리할 수 있습니다. 클라이언트 소프트웨어를 사용하여 PC를 관리하면 [다음 기능](windows-pc-management-capabilities-in-microsoft-intune.md)을 수행할 수 있습니다.

### <a name="exchange-activesync-management"></a>Exchange ActiveSync 관리

Intune 콘솔에서 [Exchange ActiveSync 장치](/intune/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune)를 관리할 수 있습니다. 이 옵션은 다른 방법에 비해 제한적인 관리 기능 집합을 제공합니다. 지원되는 장치 목록은 [Office 365의 기본 제공 모바일 장치 관리 기능](https://support.office.com/article/Capabilities-of-built-in-Mobile-Device-Management-for-Office-365-a1da44e5-7475-4992-be91-9ccec25905b0)을 참조하세요.

## <a name="intune-supported-web-browsers"></a>Intune 지원 웹 브라우저

여러 관리 태스크를 수행하려면 다음과 같은 관리 웹 사이트 중 하나를 사용해야 합니다.

- [Office 365 포털](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Microsoft Intune 관리자 콘솔](https://admin.manage.microsoft.com/)

|Intune 기능 |지원되는 브라우저|
|---------|---------|
|**Intune 관리 콘솔**     |  Internet Explorer 10 이상<br /><br />Google Chrome(버전 42 이전 버전)<br /><br />Silverlight가 사용되는 Mozilla Firefox<br />**참고:** Mozilla는 2017년 3월부터 Silverlight를 지원하지 않습니다. [자세히 알아봅니다](https://go.microsoft.com/fwlink/?linkid=836872). |
|**Office 365 관리 포털**     |모바일 브라우저 및 관리되는 브라우저를 포함하는 모든 브라우저  |
|**회사 포털 웹 사이트**     |**모바일 장치:** 지원되는 각 플랫폼의 기본 웹 브라우저를 사용합니다.   <br /><br />**Windows PC:** Internet Explorer 10 이상 또는 Microsoft Edge<br /><br />**Mac OS X 10.9 이상:** Apple Safari    |

> [!Note]
> Microsoft Edge 및 모바일 브라우저는 [Microsoft Silverlight](https://msdn.microsoft.com/en-us/library/cc838158(v=vs.95).aspx)를 지원하지 않기 때문에 관리 콘솔에 대해 지원되지 않습니다. Intune 콘솔은 일정 시간에 걸쳐 Silverlight 환경에서 이동되므로 결국 모든 Intune의 모바일 장치 및 응용 프로그램 관리 기능을 [새 Microsoft Azure 포털에서 사용할 수 있게 됩니다](https://blogs.technet.microsoft.com/enterprisemobility/2015/11/17/enhancing-managed-mobile-productivity/).


서비스 관리자 권한이 있는 사용자이거나 전역 관리자 역할이 있는 테넌트 관리자만이 이 포털에 로그인할 수 있습니다. 관리 콘솔에 액세스하려면 계정에 Intune을 사용할 수 있는 라이선스가 있어야 하며 계정의 로그인 상태가 **허용**이어야 합니다.

>[!div class="step-by-step"]

>[**네트워킹** &rarr;](network-bandwidth-use.md)  



<!--HONumber=Jan17_HO4-->


