---
title: "장치 위협 방지를 사용하여 액세스 제한 | Microsoft Intune"
description: "장치, 네트워크 및 응용 프로그램 위험에 따라 회사 리소스에 대한 액세스를 제한합니다."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 725d9e40-e70c-461a-9413-72ff1b89a938
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d4cd3d28a9e4c80fb6a2e17856f6dc9230429e70
ms.openlocfilehash: cbd223560810ee1b97966b8bf8da7206cc2a7955


---

# <a name="restrict-access-to-company-resource-based-on-device-network-and-application-risk"></a>장치, 네트워크 및 응용 프로그램 위험에 따라 회사 리소스에 대한 액세스 제한
Microsoft Intune과 통합된 장치 위협 방지 솔루션인 Lookout에서 수행한 위험 평가에 따라 회사 리소스에 대한 모바일 장치의 액세스를 제어할 수 있습니다. 위험은 Lookout 서비스가 OS(운영 체제) 취약성, 설치된 악성 앱 및 악성 네트워크 프로필과 관련해 장치에서 수집하는 원격 분석을 기반으로 합니다. 그러면 Intune 규정 준수 정책을 통해 사용된 Lookout의 보고된 위험 평가에 따라, Intune에서 조건부 액세스 정책을 구성할 수 있고 해당 장치에서 위협이 탐지되어 규정 비준수로 확인된 장치를 허용하거나 차단할 수 있습니다.  

## <a name="what-problem-does-this-solve"></a>어떤 문제를 해결합니까?
회사와 조직은 OS 취약점뿐만 아니라 물리적 위협, 앱 기반 위협, 네트워크 기반 위협 등 출현하는 위협에서 중요한 데이터를 보호해야 합니다.

지금까지 회사와 조직은 악의적인 공격에서 PC를 보호하는 데 적극적인 태도를 취했습니다. 모바일은 신생 영역으로, 보호되지 않는 경우가 많습니다. 모바일 플랫폼에는 앱 격리와 소비자 앱 스토어 점검과 같은 기술을 사용하는, OS 보호 기능이 내장되어 있지만 이러한 플랫폼은 정교한 공격에 갈수록 취약합니다. 모바일 장치는 직원들이 업무용으로 점점 더 많이 사용하고 중요하고 가치 있는 정보에 액세스해야 하기 때문에 다양하고 정교한 공격으로부터 보호해야 합니다.

Intune을 사용하면 Lookout 같은 장치 위협 방지 솔루션이 제공하는 위험 평가에 따라 회사 리소스와 데이터에 대한 액세스를 제어할 수 있습니다.

## <a name="how-do-intune-and-lookout-device-threat-protection-help-protect-company-resources"></a>Intune 및 Lookout 장치 위협 방지가 회사 리소스를 보호하는 데 어떤 도움이 되나요?
모바일 장치에서 실행되는 Lookout의 모바일 앱(Lookout for work)이 파일 시스템, 네트워크 스택, 장치 및 응용 프로그램 원격 분석(사용 가능한 경우)을 캡처한 후 Lookout 장치 위협 방지 클라우드 서비스에 전송하여 모바일 위협에 대한 종합적인 장치 위험을 계산합니다. 요구 사항에 맞게 Lookout 콘솔에서 위협에 대한 위험 수준 분류를 변경할 수도 있습니다.  

현재 Intune의 준수 정책에는 Lookout 장치 위협 위험 평가를 기반으로 하는, Lookout 모바일 위협 방지에 대한 새 규칙이 포함되어 있습니다. 이 규칙을 사용하면 장치가 설정된 정책을 준수하는지 Microsoft Intune이 평가합니다.

장치가 규정 준수 정책을 충족하지 않는 것으로 확인되면 조건부 액세스 정책을 통해 Exchange Online, SharePoint Online 같은 리소스에 대한 액세스를 차단할 수 있습니다. 액세스가 차단된 최종 사용자에게는 문제를 해결하고 회사 리소스에 액세스할 수 있는 연습이 제공됩니다. 이 연습은 Lookout for work 앱에서 시작됩니다.
## <a name="supported-platforms"></a>지원되는 플랫폼:
* **Android 4.1 이상** 및 Microsoft Intune에 등록되어 있어야 함.
* **iOS 8 이상**, 및 Microsoft Intune에 등록되어 있어야 함.
Lookout에서 지원하는 플랫폼 및 언어에 대한 자세한 내용은 이 [문서](https://personal.support.lookout.com/hc/en-us/articles/114094140253)를 참조하세요.

## <a name="prerequisites"></a>필수 조건:
* Microsoft Intune 및 Azure Active Directory에 대한 구독
* Lookout Mobile EndPoint Security에 대한 엔터프라이즈 구독.  자세한 내용은 [Lookout Mobile Endpoint Security](https://www.lookout.com/products/mobile-endpoint-security)를 참조하세요.

## <a name="example-scenarios"></a>예제 시나리오
다음은 몇 가지 일반적인 시나리오입니다.
### <a name="control-access-based-on-threat-from-malicious-apps"></a>악성 앱의 위협에 따라 액세스 제어:
맬웨어 같은 악성 앱이 장치에서 발견되면 이러한 장치가 다음을 하지 못하도록 차단할 수 있습니다.
* 위협을 해결하기 전에 회사 메일에 연결
* OneDrive for Work 앱을 사용하여 회사 파일 동기화
* 비즈니스에 중요한 앱에 액세스

**악성 앱이 발견되면 액세스 차단:**
![장치에서 악성 앱이 발견되어 장치가 규정을 준수하지 않는 것으로 확인되면 조건부 액세스 정책으로 액세스를 차단하는 모습을 나타낸 다이어그램](../media/mtp/malicious-apps-blocked.png)

**위협이 해결되면 장치 차단이 해제되고 장치가 회사 리소스에 액세스할 수 있음:**

![해결 후 장치가 규정을 준수하는 것으로 확인되면 조건부 액세스 정책을 통해 액세스를 부여하는 모습을 나타낸 다이어그램](../media/mtp/malicious-apps-unblocked.png)
### <a name="control-access-based-on-threat-to-network"></a>네트워크에 대한 위협에 따라 액세스 제어:
메시지 가로채기(man-in-the-middle) 공격 같은 네트워크에 대한 위협을 감지하여, 장치 위험에 따라 WiFi 네트워크에 대한 액세스를 제한합니다.

**WiFi를 통한 네트워크 액세스 차단:**
![네트워크 위협에 따라 조건부 액세스를 통해 WiFi 액세스를 차단하는 모습을 나타낸 다이어그램](../media/mtp/network-wifi-blocked.png)

**해결 시 액세스 허용:**

![위협 해결 시 조건부 액세스를 통해 액세스를 허용하는 모습을 나타낸 다이어그램](../media/mtp/network-wifi-unblocked.png)
### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>네트워크에 대한 위협에 따라 SharePoint Online에 대한 액세스 제어:

메시지 가로채기(man-in-the-middle) 공격 같은 네트워크에 대한 위협을 감지하여, 장치 위험에 따라 회사 파일 동기화를 금지합니다.

**장치에서 발견된 네트워크 위협에 따라 SharePoint Online 액세스 차단:**

![발견된 위협에 따라 조건부 액세스를 통해 SharePoint Online에 대한 장치의 액세스를 차단하는 모습을 나타낸 다이어그램](../media/mtp/network-spo-blocked.png)


**해결 시 액세스 허용:**

![네트워크 위협 해결 시 조건부 액세스를 통해 액세스를 허용하는 모습을 나타낸 다이어그램](../media/mtp/network-spo-unblocked.png)

## <a name="next-steps"></a>다음 단계
다음은 이 솔루션을 구현하기 위한 필수 주요 단계입니다.
1.  [Lookout 장치 위협 방지 구독 설정](set-up-your-subscription-with-lookout-mtp.md)
2.  [Intune에서 Lookout MTP 연결](enable-lookout-mtp-connection-in-intune.md)
3.  [Lookout for Work 응용 프로그램 구성 및 배포](configure-and-deploy-lookout-for-work-apps.md)
4.  [준수 정책 구성](enable-device-threat-protection-rule-in-compliance-policy.md)
5.  [Lookout 통합 문제 해결](http://docs.microsoft.com/en-us/intune/troubleshoot/troubleshooting-lookout-integration)



<!--HONumber=Nov16_HO1-->


