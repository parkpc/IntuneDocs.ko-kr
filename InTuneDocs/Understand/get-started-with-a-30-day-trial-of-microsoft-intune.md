---
title: "Intune 평가판 가이드 | Microsoft Intune"
description: 
keywords: 
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 619a1d11-3d22-4635-8f70-770eba3e1712
ms.reviewer: jeffgilb
ms.suite: ems
ms.sourcegitcommit: 4af13629986e7cef814104f3d1f298eb2be240ac
ms.openlocfilehash: 26ecc3dfe8816da9f30829901d929af53b1bedc0


---

# Intune 평가판 가이드
모바일 장치와 컴퓨터를 관리할 수 있는 Intune의 무료 30일 평가판을 설치하는 과정은 빠르고 간단합니다. 평가판에서 몇 가지 간단한 단계만 거치면 최대 100명의 사용자와 장치를 추가하고, 그룹을 설정하고, 규정 준수 정책을 구성하고, 모바일 장치 및 컴퓨터를 등록하고 관리할 수 있습니다.

이 항목에서는 Intune 평가판을 실행하는 기본적인 방법과 Intune의 특징과 기능을 평가할 수 있는 서비스의 개요를 알아봅니다.

5분 분량의 짧은 다음 데모 비디오를 통해 Microsoft Intune 무료 평가판으로 장치 관리를 시작하는 것이 얼마나 쉬운지 알아보세요. 비디오 첫 부분에서는 “사용이 중지된” 포트에 대해 언급됩니다. 다른 포털을 사용하더라도 적용되는 단계는 같습니다. [여기](https://docs.microsoft.com/intune/deploy-use/account-portal-merged-with-Office-365)에서 이 포털에 대해 자세히 알아볼 수 있습니다.

<iframe width="675" height="480" src="https://www.youtube.com/embed/ltcZvm4VOFU" frameborder="0" allowfullscreen></iframe>

## 시작하기 전에
Intune을 시작하기 전에 다음이 필요합니다.

-   Silverlight 지원 웹 브라우저가 포함된 장치. 이 장치를 사용하여 Intune 사용자 계정을 만들고(**Office 365 관리 센터**) 장치, 그룹 및 정책을 관리(**Intune 관리 콘솔**)할 웹 사이트에 액세스할 수 있습니다.

-   Intune 사용자가 회사 포털을 사용하여 자신의 장치를 등록 및 관리하는 방법을 테스트하는 데 사용할 추가 장치(웹 브라우저 포함). 사용자가 앱을 찾고 설치하는 방법과 관리자에게 도움을 요청하는 방법도 테스트할 것입니다. 추가 장치가 없다면 Intune 관리에 사용하는 브라우저에서 "개인 정보 모드" 설정을 사용할 수 있습니다. 예를 들어 Internet Explorer에서 **도구**&gt;**InPrivate 브라우징**을 선택하면 됩니다.

-   기존 Microsoft Online Services 계정이 있는 경우 이 계정의 관리자 자격 증명이 필요합니다. 이러한 계정이 없거나 이 Intune 테넌트를 평가용으로만 사용하려는 경우에는 테넌트 관리자 자격 증명이 필요하지 않습니다.

-   Intune 평가판을 통해 iOS 또는 Windows Phone 장치를 관리하려는 경우 인증서(또는 키) 및 해당 인증서를 받을 계정이 필요합니다(아래 표 참조). Android 장치의 경우 추가 인증서가 필요하지 않습니다.

    |플랫폼|인증서 요구 사항|추가 정보|
    |------------|----------------------------|--------------------|
    |Windows Phone 8.1 및 Windows Phone 8 |스토어에서 회사 포털 앱을 설치하는 Windows 8.1 사용자의 경우 인증서가 필요하지 않습니다. Intune을 사용하여 회사 포털 앱을 Windows Phone 8.1 장치로 배포하려는 경우 또는 Windows Phone 8.0을 사용하는 경우에는 Symantec 인증서가 필요합니다.|이 지침에서는 사용자가 Windows Phone 8.1 이상 장치에서 스토어의 회사 포털 앱을 다운로드한다고 가정합니다. Windows Phone 8.0 지원에 대한 자세한 내용은 [Microsoft Intune을 사용한 Windows Phone 관리 설정](/Intune/Deploy-Use/set-up-windows-phone-management-with-microsoft-intune)을 참조하세요.|
    |Windows 10, Windows RT 8.1, Windows RT 또는 Windows 8.1 장치|Windows RT 및 Windows 장치 등록을 위한 인증서 요구 사항은 없습니다.|[Microsoft Intune을 사용하여 Windows PC 클라이언트 설치](/Intune/Deploy-Use/install-the-windows-pc-client-with-microsoft-intune)|
    |iOS 7.1 이상|APNs(Apple Push Notification service) 인증서를 가져옵니다.|[Microsoft Intune을 사용하여 iOS 및 Mac 관리 설정](/Intune/Deploy-Use/set-up-ios-and-mac-management-with-microsoft-intune)에 설명된 대로 Apple에서 Apple Push Notification Service 인증서를 요청합니다.|

## Intune의 30일 평가판을 완료하기 위한 단계
- [1단계: 30일 평가판에 로그인 또는 등록](get-started-with-a-30-day-trial-of-microsoft-intune-step-1.md). Intune에 로그인하거나 등록하기 전에 기존 계정을 사용하여 로그인하거나 Microsoft Intune의 30일 평가판에만 사용할 임시 계정을 만들 것인지 여부를 고려해야 합니다.
- [2단계: 사용자 추가](get-started-with-a-30-day-trial-of-microsoft-intune-step-2.md). 계정을 설정했으므로 이제 Intune에 개별 사용자 계정을 추가하거나 여러 사용자를 일괄 추가할 수 있습니다(이 섹션의 지침 참조). 시작하기 전에 Intune에서 관리자 계정을 처리하는 방법을 이해하는 것이 중요합니다.
- [3단계: 사용자 및 장치를 구성하는 그룹 만들기](get-started-with-a-30-day-trial-of-microsoft-intune-step-3.md). Intune의 그룹을 통해 장치 및 사용자를 매우 유연하게 관리할 수 있습니다. 지리적 위치, 부서, 하드웨어 특성 등의 조직 요구 사항에 맞게 그룹을 설정한 후 사용자 집합에 대한 정책 설정, 장치 집합에 대한 응용 프로그램 배포 등의 다양한 관리 작업을 수행하는 데 사용할 수 있습니다.
- [4단계: 정책 만들기 및 앱 게시](get-started-with-a-30-day-trial-of-microsoft-intune-step-4.md). Intune 정책은 모바일 장치에 대한 보안 설정을 제어하고, 컴퓨터에 대한 Windows 방화벽 및 Endpoint Protection 설정을 유지하고, 응용 프로그램을 배포하는 데 사용할 수 있는 설정을 제공합니다.
- [5단계: 모바일 장치 등록 및 앱 설치](get-started-with-a-30-day-trial-of-microsoft-intune-step-5.md). Intune을 사용하여 모바일 장치 관리를 설정하려면 모바일 장치 관리 기관을 설정하고, 특정 장치 플랫폼에 대한 관리를 사용하도록 설정한 다음, 회사 포털 앱을 사용하여 장치를 등록해야 합니다. 그러면 게시한 Microsoft Skype 응용 프로그램을 배포할 수 있습니다.
- [6단계: 기타 옵션 및 추가 기능](get-started-with-a-30-day-trial-of-microsoft-intune-step-6.md). 비즈니스 요구를 충족하기 위해 경고, 보고서 및 기타 Intune 기능을 사용하는 방법을 선택합니다.
- [7단계: 다음 단계](get-started-with-a-30-day-trial-of-microsoft-intune-step-7.md). Intune 유료 구독으로 이동할 준비 및 Intune "FastTrack 센터 혜택 활용.


### 다음 단계
30일 평가판 구독을 시작할 때입니다.

>[!div class="step-by-step"]
[**Intune에 등록** &rarr;](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-1.md)

### 참고 항목
[Intune 빠른 시작 가이드](/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune)



<!--HONumber=Jul16_HO2-->


