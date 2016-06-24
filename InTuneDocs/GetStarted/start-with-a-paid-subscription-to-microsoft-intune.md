---
# required metadata

title: Intune 빠른 시작 가이드 | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: d158503c-1276-422b-ab81-5f66c1cd7e7a

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Intune 빠른 시작 가이드
이 빠른 시작 가이드에서는 조직에서 사용 중인 모바일 장치 및 Windows PC 관리를 빠르고 쉽게 시작하도록 Microsoft Intune의 유료 구독을 설정하는 단계를 안내합니다. 순서로 각 단계를 수행하거나 사용자의 환경 또는 비즈니스 요구에 적용할 수 없는 경우 건너뛰고 진행할 수 있습니다.

>[!NOTE]
>이 문서는 Intune을 독립 실행형 서비스로 설정하는 것에 중점을 두고 있습니다. 또는 현재 Microsoft System Center Configuration Manager를 사용하여 컴퓨터와 서버를 관리하고 있다면, 하이브리드 MDM 배포에서 Configuration Manager와 Intune을 연결하여 [모바일 장치를 관리하도록 Configuration Manager를 확장](https://technet.microsoft.com/library/jj884158.aspx)할 수 있습니다.

이 빠른 시작 가이드의 단계는 [Intune 평가 가이드](/intune/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune)에 있는 단계와 동일한 단계를 많이 공유하고 있습니다. 하지만, 평가 후에 모바일 장치를 관리할 준비가 되면, 몇 가지 추가적인 요구 사항을 처리해야 합니다. 이것은 현재 네트워크 인프라 및 비즈니스 요구 사항에 따라 달라지며, 다음과 같은 작업을 포함합니다.

-   온-프레미스 Active Directory 계정을 Intune 및 Azure Active Directory와 동기화

-   도메인 등록자를 통해 공용 도메인 및 DNS 서비스 레코드 업데이트

-   프로덕션용 Intune 기능 사용자 지정

>[!TIP]
>적합한 요금제로 Microsoft Intune용 라이선스를 150개 이상 구매하면 Microsoft 전문가가 참여하는 서비스인 "FastTrack 센터 혜택"을 사용하여 Intune 사용 준비가 완료된 환경을 구현할 수 있습니다. [Microsoft Intune 서비스 혜택 설명](https://technet.microsoft.com/library/mt228265.aspx)을 참조하세요..


## 시작하기 전에
유료 구독을 시작하는 상황이고 기존 네트워크 인프라를 변경하고 Intune을 배포할 준비가 된 경우에 이 가이드를 사용합니다. 유료 구독 사용 시에는 단순히 내부 및 외부 DNS 레코드를 추가하거나 업데이트할 수도 있고, 기존 Active Directory 사용자 계정을 Azure Active Directory에 동기화할 수도 있습니다. 어떠한 조합의 Intune 모바일 장치 관리 기능을 결정하든 Intune이 기존 네트워크 구성 요소 및 서비스와 상호 작용하도록 할 방법을 면밀하게 계획해야 합니다. 구체적으로는 다음 사항을 검토해야 합니다.

-   **사용자 ID 관리 방법**: 대부분의 중간에서 대규모의 조직에서 Azure Active Directory를 통해 Intune에 기존 디렉터리 서비스를 연결하면 Intune을 통해 사용자 ID를 가장 편리하게 관리할 수 있습니다. 특히 Office 365 또는 Exchange Online과 같은 기타 Microsoft 클라우드 서비스를 이미 사용하는 경우에는 더욱 그러합니다. [Microsoft Azure Active Directory Connect](https://www.microsoft.com/download/details.aspx?id=47594)를 사용하여 기존 사용자 계정을 동기화하면 온-프레미스 Active Directory를 Azure Active Directory에 빠르고 쉽게 연결하고 사용자를 위한 Single Sign-On 인증 환경을 구성할 수 있습니다.

-   **DNS에 미치는 영향**: Intune에 처음 등록 시 받는 기본 onmicrosoft.com 도메인 대신 자신의 도메인 이름을 사용하려면, 공용 DNS 레코드를 업데이트해야 합니다. DNS 레코드 업데이트는 모바일 장치가 Intune을 찾을 수 있도록 하고 구독에 대한 관리 서비스가 조직 내에 사용 중인 모든 장치를 관리하기 위해 제대로 작동하도록 하기 위해 필요합니다.

## 필요한 항목
관련 준비가 완료되면 Intune 유료 구독 사용을 시작하는 경우 다음 항목이 필요합니다.

### Silverlight 사용 웹 브라우저가 설치된 장치
이 항목은 장치, 앱, 정책을 관리하는 Intune 관리 콘솔에 액세스하기 위해 필요합니다. 모바일 장치에서 회사 포털 앱에 액세스하지 않을 때 웹 기반 회사 포털에 액세스하기 위해 웹 브라우저도 필요합니다. 쉽게 하려면, Intune 관리에 사용하는 브라우저에서 "개인 정보 보호 모드" 설정을 사용할 수 있습니다. 예를 들어 Internet Explorer에서 **도구** &gt; **InPrivate 브라우징**을 클릭하면 됩니다.).

>[!TIP]
>이 요구 사항으로 인해, Microsoft Edge 브라우저는 Intune 관리 콘솔에 대한 액세스가 지원되지 않습니다.


### 모바일 장치에 대한 인증서
Intune을 통해 iOS 또는 Windows Phone 장치를 관리하려는 경우에는 인증서 및 해당 인증서를 검색할 계정이 필요합니다. Android 장치 관리를 위해서는 추가적인 인증서가 필요하지 않습니다.

- 스토어에서 회사 포털 앱을 설치하는 **Windows Phone 8.1** 사용자의 경우 인증서가 필요하지 않습니다. 하지만, Intune을 사용하여 회사 포털 앱을 Windows Phone 8.1 장치로 배포하려는 경우 또는 **Windows Phone 8.0**을 사용하는 경우에는 [Symantec 코드 서명 인증서](https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do)가 필요합니다.

>[!NOTE]
>이 빠른 시작 가이드에서는 사용자가 Windows Phone 8.1 이상의 장치에서 스토어의 회사 포털 앱을 다운로드한다고 가정합니다. Windows Phone 8.0 지원에 대한 자세한 내용은 [Microsoft Intune을 사용한 Windows Phone 8.0 관리 설정](/Intune/deploy-use/set-up-windows-phone-8.0-management-with-microsoft-intune)을 참조하세요..

- Windows PC를 장치로 등록하거나 [Microsoft Intune용 Windows PC 클라이언트를 설치](/intune/deploy-use/install-the-windows-pc-client-with-microsoft-intune)하는 경우에는 **Windows PC** 또는 **Windows RT 장치**에 대한 인증서 요구 사항이 없습니다..

- **iOS** 또는 **Mac OS X** 장치의 경우, [Microsoft Intune을 사용한 iOS 및 Mac 관리 설정](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) 3단계에 설명된 대로 Apple의 Apple Push Notification Service 인증서를 요청해야 합니다..

### 다음 단계
Intune 빠른 시작 가이드를 시작할 시간입니다.

>[!div class="step-by-step"]
[**Intune에 로그인** &rarr;](start-with-a-paid-subscription-to-microsoft-intune-step-1.md)


<!--HONumber=May16_HO1-->


