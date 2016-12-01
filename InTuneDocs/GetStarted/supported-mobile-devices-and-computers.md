---
title: "지원되는 모바일 장치 및 브라우저 | Microsoft Intune"
description: "Intune에서 지원하는 모바일 장치 및 컴퓨터"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: aeeccfa4-0f14-447e-a3df-c8435c8a4bb2
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 149f3a3310907d131affeaad4bd372aa60be9206
ms.openlocfilehash: 80541567c535cfeb7fca3eda3c9143f4b11d7abb


---

# <a name="supported-mobile-devices-and-computers"></a>지원되는 모바일 장치 및 컴퓨터

등록한 후 다음 장치 유형을 관리할 수 있습니다.

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

장치를 등록하면 [이러한 기능](/Intune/get-started/choose-how-to-manage-devices)이 제공됩니다.

또는 Intune PC 클라이언트 소프트웨어로 Windows PC를 관리할 수 있습니다. Intune PC 클라이언트 소프트웨어는 Windows 7 이상 버전(Windows 10 Home 제외)을 지원합니다. 클라이언트 소프트웨어를 사용하여 PC를 관리하면 [다음 기능](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune)을 수행할 수 있습니다.

Enterprise Management Suite가 있는 고객은 Azure AD(Azure Active Directory)를 사용하여 Windows 10 장치를 등록할 수도 있습니다.

## <a name="microsoft-intune-supported-web-browsers"></a>Microsoft Intune 지원 웹 브라우저

여러 관리 작업을 수행하려면 다음과 같은 관리 웹 사이트 중 하나를 사용해야 합니다.

- [Office 365 포털](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Microsoft Intune 관리자 콘솔](https://admin.manage.microsoft.com/)

> [!Note]
> Microsoft Edge 및 모바일 브라우저는 [Microsoft Silverlight](https://msdn.microsoft.com/en-us/library/cc838158(v=vs.95).aspx)를 지원하지 않기 때문에 관리 콘솔에 대해 지원되지 않습니다. Intune 콘솔은 일정 시간에 걸쳐 Silverlight 환경에서 이동되므로 결국 모든 Intune의 모바일 장치 및 응용 프로그램 관리 기능을 [새 Microsoft Azure 포털에서 사용할 수 있게 됩니다](https://blogs.technet.microsoft.com/enterprisemobility/2015/11/17/enhancing-managed-mobile-productivity/).

|Intune 기능 |지원되는 브라우저|
|---------|---------|
|Intune 관리 콘솔     |  Internet Explorer 10 이상<br /><br />Google Chrome(버전 42 이전 버전)<br /><br />Silverlight가 사용되는 Mozilla Firefox<br /><br />**참고:** 관리 콘솔에서 Microsoft Edge 및 모바일 브라우저는 지원되지 않습니다.                      
|Office 365 관리 포털     |모바일 브라우저 및 관리되는 브라우저를 포함하는 모든 브라우저  |
|회사 포털 웹 사이트     |**모바일 장치:** 지원되는 각 플랫폼의 기본 웹 브라우저를 사용합니다.   <br /><br />**Windows PC:** Internet Explorer 10 이상 또는 Microsoft Edge<br /><br />**Mac OS X 10.9 이상:** Apple Safari    |

> [!Note]
> Microsoft Edge 및 모바일 브라우저는 [Microsoft Silverlight](https://msdn.microsoft.com/en-us/library/cc838158(v=vs.95).aspx)를 지원하지 않기 때문에 관리 콘솔에 대해 지원되지 않습니다. Intune 콘솔은 일정 시간에 걸쳐 Silverlight 환경에서 이동되므로 결국 모든 Intune의 모바일 장치 및 응용 프로그램 관리 기능을 [새 Microsoft Azure 포털에서 사용할 수 있게 됩니다](https://blogs.technet.microsoft.com/enterprisemobility/2015/11/17/enhancing-managed-mobile-productivity/).

### <a name="office-365-portalhttpgomicrosoftcomfwlinkplinkid698854"></a>[Office 365 포털](http://go.microsoft.com/fwlink/p/?LinkId=698854)

**테넌트 관리자는 이 포털을 사용하여 구독을 관리하며**, 관리자 역할에서 허용할 경우 다음 작업도 수행합니다.

- 구독에 대한 사용자 계정을 관리하고 온-프레미스 Active Directory에서의 디렉터리 동기화를 구성합니다.
- 보안 그룹이라는 사용자 그룹을 관리합니다.
- Intune을 사용할 수 있는 라이선스를 사용자에게 할당합니다.
- 구독에 사용하는 도메인 이름을 구성합니다. 도메인 이름은 사용자가 로그인하는 데 사용하는 계정을 정의합니다.
- 보유한 라이선스 수 또는 사용할 수 있는 클라우드 저장소 공간의 양을 비롯하여 구독에 대한 대금 청구 및 구매 정보를 관리합니다.
- Intune 서비스의 상태를 확인할 수 있는 링크를 찾습니다.
- 테넌트 관리자는 계정에 Intune을 사용할 수 있는 라이선스가 할당되지 않은 경우에도 Office 365 포털에 로그인하여 구독을 관리할 수 있습니다.
- Intune에 대한 라이선스가 있지만 관리자가 아닌 사용자는 이 포털을 사용하여 계정 암호를 재설정하고 프로필을 편집할 수 있습니다.
- Office 365 포털에 액세스하려면 계정의 로그인 상태가 **허용**이어야 합니다. 이 상태는 구독에 대한 라이선스 보유와는 다른 문제입니다. 기본적으로 모든 사용자 계정은 **허용**됩니다.


### <a name="microsoft-intune-administrator-consolehttpsmanagemicrosoftcom"></a>[Microsoft Intune 관리자 콘솔](https://manage.microsoft.com/)

**서비스 관리자는 이 포털을 사용하여 일상적인 작업을 관리**하며, 다음과 같은 작업이 포함됩니다.

- 컴퓨터 및 모바일 장치에 대한 정책을 설정합니다.
- 소프트웨어 업데이트 및 앱과 같은 소프트웨어를 업로드 및 배포합니다.
- 컴퓨터에서 Endpoint Protection을 관리합니다.
- 장치 상태를 확인하고 보고서를 실행합니다.
- 이 포털에 로그인합니다. 이 포털에 로그인하려면 서비스 관리자 권한이 있거나전역 관리자 역할이 있는 테넌트 관리자여야 합니다.


서비스 관리자 권한이 있는 사용자이거나 전역 관리자 역할이 있는 테넌트 관리자만이 이 포털에 로그인할 수 있습니다. 관리 콘솔에 액세스하려면 계정에 Intune을 사용할 수 있는 라이선스가 있어야 하며 계정의 로그인 상태가 **허용**이어야 합니다.



<!--HONumber=Nov16_HO4-->


