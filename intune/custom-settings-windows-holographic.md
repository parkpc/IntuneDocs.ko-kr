---
title: "Windows Holographic for Business 장치에 대한 Intune 사용자 지정 설정"
titlesuffix: Azure portal
description: "Windows Holographic for Business 사용자 지정 프로필에서 사용할 수 있는 설정을 알아봅니다.\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 1/24/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ae46aef10ca294637a4d433ce273d3c53e695d64
ms.sourcegitcommit: 93622d740cbd12043eedc25a9699cc4256e23e7e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2018
---
# <a name="custom-device-settings-for-windows-holographic-for-business-devices-in-microsoft-intune"></a>Microsoft Intune의 Windows Holographic for Business 장치에 대한 사용자 지정 장치 설정

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

 장치의 기능을 제어하는 데 사용할 수 있는 OMA-URI(Open Mobile Alliance Uniform Resource Identifier) 설정을 배포하려면 Windows Holographic for Business용 Microsoft Intune **사용자 지정** 프로필을 사용합니다. Windows Holographic for Business는 많은 CSP(구성 서비스 공급자) 설정을 사용할 수 있게 합니다. CSP 개요는 [IT 전문가용 구성 CSP(구성 서비스 공급자) 소개](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers)를 참조하세요. Windows Holographic에서 지원되는 특정 CSP의 경우 [Windows Holographic에서 지원되는 CSP](https://docs.microsoft.com/en-us/windows/client-management/mdm/configuration-service-provider-reference#hololens)를 참조하세요.

특정 설정을 찾고 있는 경우 [Windows Holographic for Business 장치 제한 프로필](device-restrictions-windows-holographic.md)에 기본 제공 설정이 많기 때문에 사용자 지정 값을 지정할 필요가 없습니다.

1. [Microsoft Intune에서 사용자 지정 장치 설정을 구성하는 방법](custom-settings-configure.md)의 지침을 사용하여 시작합니다.
2. **프로필 만들기** 블레이드에서 **설정**을 선택하여 하나 이상의 OMA-URI 설정을 추가합니다.
3. **사용자 지정 OMA-URI 설정** 블레이드에서 **추가**를 클릭하여 새 값을 추가합니다. **내보내기**를 클릭하여 쉼표로 구분된 값(.csv) 파일로 구성한 모든 값의 목록을 만들 수도 있습니다.
4. 추가하려는 각 OMA-URI 설정에 대해 다음 정보를 입력합니다. 사용할 수 있는 설정에 대해 알아보려면 이 항목의 목록을 사용하세요.
    - **설정 이름** - 설정 목록에서 쉽게 식별할 수 있도록 OMA-URI 설정에 대한 고유한 이름을 입력합니다.
    - **설정 설명** -필요에 따라 설정에 대한 설명을 입력합니다.
    - **데이터 형식** - 다음 중에서 선택합니다.
        - **문자열**
        - **문자열(XML)**
        - **날짜 및 시간**
        - **정수**
        - **부동 소수점**
        - **부울**
    - **OMA-URI(대/소문자 구분)** - 설정을 제공할 OMA-URI를 지정합니다.
    - **값** - 입력한 OMA-URI와 연결할 값을 지정합니다.
5. 완료되면 **프로필 만들기** 블레이드로 돌아와서 **만들기**를 클릭합니다.
프로필이 만들어지고 프로필 목록 블레이드에 표시됩니다.

## <a name="supported-custom-settings"></a>지원되는 사용자 지정 설정

Windows Holographic for Business는 다음과 같은 사용자 지정 설정을 지원합니다.


|설정 이름|OMA URI|데이터 형식  |
|---------|---------|---------|
|AllowFastReconnect     |./Vendor/MSFT/Policy/Config/Authentication/AllowFastReconnect|정수(0 - 허용 안 함, 1 - 허용)|
|AllowVPN     |./Vendor/MSFT/Policy/Config/Settings/AllowVPN|정수(0 - 허용 안 함, 1 - 허용)|



## <a name="how-to-find-the-policies-you-can-configure"></a>구성할 수 있는 정책을 찾는 방법

[Windows Holographic에서 지원되는 CSP](https://docs.microsoft.com/en-us/windows/client-management/mdm/configuration-service-provider-reference#hololens)에서 Windows Holographic이 지원하는 모든 CSP(구성 서비스 공급자)의 전체 목록을 찾을 수 있습니다. 일부 Windows Holographic 버전과 호환되지 않는 설정도 있습니다. Windows 항목의 표에서 각 CSP에 지원되는 버전을 알려 줍니다.

또한, Intune은 항목에 나열된 일부 설정을 지원합니다. 원하는 설정을 Intune에서 지원하는지 확인하려면 해당 설정에 대한 항목을 엽니다. 각 설정 페이지에 지원되는 작업이 표시되어 있습니다. Intune으로 작업하려면 설정에서 **추가** 또는 **대체** 작업을 지원해야 합니다.


