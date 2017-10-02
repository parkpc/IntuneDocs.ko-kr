---
title: "Intune을 사용하여 Windows 장치의 암호 재설정"
titlesuffix: Azure portal
description: "Intune을 사용하여 Microsoft PIN 재설정 서비스와 통합된 Windows 장치의 암호를 재설정하는 방법을 알아봅니다.\""
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5027d012-d6c2-4971-a9ac-217f91d67d87
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: faf3e9b81f76755135f73f8753305d96d227ec14
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2017
---
# <a name="reset-the-passcode-on-windows-devices-integrated-with-the-microsoft-pin-reset-service-using-intune"></a>Intune을 사용하여 Microsoft PIN 재설정 서비스와 통합된 Windows 장치의 암호 재설정

Windows 장치에 대한 암호 재설정 기능이 Microsoft PIN 재설정 서비스와 통합되어 Windows 10 Mobile을 실행하는 장치에 대한 새 암호를 생성할 수 있습니다. 장치에서 Windows 10 크리에이터스 업데이트 이상을 실행하고 있어야 합니다.

## <a name="supported-platforms"></a>지원되는 플랫폼

- Windows - Windows 10 크리에이터스 업데이트 이상에서 지원됨(Azure AD 연결)
- Windows Phone - 지원되지 않음
- iOS - 지원되지 않음
- macOS - 지원되지 않음
- Android - 지원되지 않음


## <a name="before-you-start"></a>시작하기 전에

관리할 수 있는 Windows 장치의 암호를 원격으로 재설정하려면 Intune 테넌트에 PIN 재설정 서비스를 온보딩하고 관리하는 장치를 구성해야 합니다. 설정하려면 다음 지침을 따르세요.

### <a name="connect-intune-with-the-pin-reset-service"></a>PIN 재설정 서비스에 Intune 연결

1. [Microsoft PIN 재설정 서비스 통합 웹 사이트](https://login.windows.net/common/oauth2/authorize?response_type=code&client_id=b8456c59-1230-44c7-a4a2-99b085333e84&resource=https%3A%2F%2Fgraph.windows.net&redirect_uri=https%3A%2F%2Fcred.microsoft.com&state=e9191523-6c2f-4f1d-a4f9-c36f26f89df0&prompt=admin_consent)로 이동한 다음 Intune 테넌트를 관리하는 데 사용하는 테넌트 관리자 계정으로 로그인합니다.
2. 로그인한 후 **동의**를 클릭하여 PIN 재설정 서비스가 계정에 액세스할 수 있도록 동의합니다.<br>
![PIN 재설정 서비스 사용 권한 페이지](./media/pin-reset-service-application.png)
3. Azure Portal의 엔터프라이즈 응용 프로그램 - 모든 응용 프로그램 블레이드에서 Intune과 PIN 재설정 서비스가 다음 스크린샷과 같이 통합된 것을 확인할 수 있습니다.<br>
![Azure의 PIN 재설정 서비스 응용 프로그램](./media/pin-reset-service-home-screen.png)
4. Intune 테넌트 관리자 자격 증명으로 [이 웹 사이트](https://login.windows.net/common/oauth2/authorize?response_type=code&client_id=9115dd05-fad5-4f9c-acc7-305d08b1b04e&resource=https%3A%2F%2Fcred.microsoft.com%2F&redirect_uri=ms-appx-web%3A%2F%2FMicrosoft.AAD.BrokerPlugin%2F9115dd05-fad5-4f9c-acc7-305d08b1b04e&state=6765f8c5-f4a7-4029-b667-46a6776ad611&prompt=admin_consent)에 로그인한 다음 **동의**를 다시 선택하여 서비스가 계정에 액세스할 수 있도록 동의합니다.

### <a name="configure-windows-devices-to-use-pin-reset"></a>PIN 재설정을 사용하도록 Windows 장치 구성

관리하는 Windows 장치에서 PIN 재설정을 구성하려면 [Intune Windows 10 사용자 지정 장치 정책](custom-settings-windows-10.md)을 사용하여 기능을 활성화합니다. 다음 Windows 정책 CSP(구성 서비스 공급자)를 사용하여 정책을 구성합니다.


- **장치의 경우** - **./Device/Vendor/MSFT/PassportForWork/*tenant ID*/Policies/EnablePinRecovery**

*tenant ID*는 Azure Active Directory의 **속성** 페이지에서 얻을 수 있는 Azure Active Directory, Directory ID를 나타냅니다.

이 CSP의 값을 **True**로 설정합니다.

## <a name="steps-to-reset-the-passcode"></a>암호 재설정 단계

1. Azure 포털에 로그인합니다.
2. **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
3. **Intune** 블레이드에서 **장치**를 선택합니다.
4. **장치** 블레이드에서 **관리** > **모든 장치**를 선택합니다.
5. 암호를 재설정할 장치를 선택한 다음 장치 속성 블레이드에서 **새 암호**를 선택합니다.
6. 표시되는 확인에서 **예**를 선택합니다. 암호가 생성되고 다음 7일 동안 포털에 표시됩니다.

## <a name="next-steps"></a>다음 단계

암호 재설정에 실패하면 자세한 정보를 가져오는 링크가 포털에 제공됩니다.


