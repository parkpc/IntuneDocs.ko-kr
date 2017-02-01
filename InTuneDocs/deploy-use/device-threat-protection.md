---
title: "장치 위협 방지를 사용하여 액세스 보호 | Microsoft 문서"
description: "장치, 네트워크 및 응용 프로그램 위험에 따라 회사 리소스에 대한 액세스를 보호합니다."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 725d9e40-e70c-461a-9413-72ff1b89a938
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 931f222898a224c2f646ad203f12676c39b78946
ms.openlocfilehash: aaa0965c2bd4d4093da0c57eaa2e3bd05eb6779a


---

# <a name="protect-access-to-company-resource-based-on-device-network-and-application-risk"></a>장치, 네트워크 및 응용 프로그램 위험에 따라 회사 리소스에 대한 액세스 제한

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune과 통합된 장치 위협 방지 솔루션인 Lookout에서 수행한 위험 평가에 따라 회사 리소스에 대한 모바일 장치의 액세스를 제어할 수 있습니다. 위험은 다음을 비롯하여 Lookout 서비스를 통해 장치에서 수집된 원격 분석에 따라 평가됩니다.
- 운영 체제 취약점
- 설치된 악성 앱
- 악성 네트워크 프로필

Intune 준수 정책을 통해 Lookout의 위험 평가에 따라 조건부 액세스 정책을 구성할 수 있습니다. 설정을 통해 감지된 위협에 따라 검색 비규격 장치를 허용하거나 차단할 수 있습니다.  

## <a name="what-problem-does-this-solve"></a>어떤 문제를 해결합니까?
회사는 OS 취약점뿐만 아니라 물리적 위협, 앱 기반 위협, 네트워크 기반 위협 등 출현하는 위협에서 중요한 데이터를 보호해야 합니다.

지금까지 회사는 공격으로부터 PC를 보호하는 데 사전 예방적인 자세를 취해 왔지만 모바일 장치는 모니터링 및 보호되지 않고 있습니다. 모바일 플랫폼에는 앱 격리 및 소비자 앱 스토어 점검과 같은 기본 제공 보호 기능이 있지만 이러한 플랫폼은 정교한 공격에 여전히 취약합니다. 오늘날 업무에 장치를 사용하며 중요한 정보에 액세스해야 하는 직원이 늘어나고 있습니다. 따라서 점점 더 정교한 공격으로부터 장치를 보호해야 합니다.

Intune을 사용하면 Lookout 같은 장치 위협 방지 솔루션이 제공하는 위험 평가에 따라 회사 리소스에 대한 액세스를 제어할 수 있습니다.

## <a name="how-do-intune-and-lookout-device-threat-protection-help-protect-company-resources"></a>Intune 및 Lookout 장치 위협 방지가 회사 리소스를 보호하는 데 어떤 도움이 되나요?
Lookout의 모바일 앱인 **Lookout for Work**가 모바일 장치에서 설치되어 실행됩니다. 이 앱은 파일 시스템, 네트워크 스택, 장치 및 앱 원격 분석(사용 가능한 경우)을 캡처한 다음, Lookout 클라우드 서비스로 보내 모바일 위협에 대한 장치의 위험을 평가합니다. 요구 사항에 맞게 Lookout 콘솔에서 위협에 대한 위험 수준 분류를 변경할 수 있습니다.  

Intune의 준수 정책에는 Lookout 위험 평가를 기반으로 하는, Lookout MTP(Mobile Threat Protection)에 대한 규칙이 포함되어 있습니다. 이 규칙을 사용하면 Intune에서 장치가 사용되는 정책을 준수하는지를 평가합니다.

장치는 정책을 준수하지 않으면 Exchange Online, SharePoint Online 등의 리소스에 대한 액세스가 차단될 수 있습니다. 차단된 장치의 사용자는 문제를 해결하고 다시 액세스하는 단계에 대한 지침을 받습니다. 지침은 Lookout for Work 앱에서 실행됩니다.

## <a name="supported-platforms"></a>지원되는 플랫폼:
Intune에 등록한 경우 다음과 같은 플랫폼에서 Lookout이 지원됩니다.
* **Android 4.1 이상**
* **iOS 8 이상** 플랫폼 및 언어 지원에 대한 자세한 내용은 [Lookout 웹 사이트](https://personal.support.lookout.com/hc/en-us/articles/114094140253)를 참조하세요.

## <a name="prerequisites"></a>필수 조건:
* Microsoft Intune 구독
* Azure Active Directory
* Lookout Mobile EndPoint Security 엔터프라이즈 구독  

자세한 내용은 [Lookout Mobile Endpoint Security](https://www.lookout.com/products/mobile-endpoint-security)를 참조하세요.

## <a name="sample-scenarios"></a>샘플 시나리오
다음은 몇 가지 일반적인 시나리오입니다.

### <a name="control-access-based-on-threats-from-malicious-apps"></a>악성 앱의 위협에 따라 액세스 제어
맬웨어와 같은 악성 앱이 장치에서 감지되면 위협이 해결될 때까지 다음으로부터 장치를 차단할 수 있습니다.
* 회사 메일에 연결
* 작업용 OneDrive 앱과 회사 파일 동기화
* 회사 앱에 액세스

**악성 앱이 발견되면 액세스 차단:**
![장치에서 악성 앱이 발견되어 장치가 규정을 준수하지 않는 것으로 확인되면 조건부 액세스 정책으로 액세스를 차단하는 모습을 나타낸 다이어그램](../media/mtp/malicious-apps-blocked.png)

**해결 시 액세스 허용:**

![해결 후 장치가 규정을 준수하는 것으로 확인되면 조건부 액세스 정책을 통해 액세스를 부여하는 모습을 나타낸 다이어그램](../media/mtp/malicious-apps-unblocked.png)

### <a name="control-access-based-on-threat-to-network"></a>네트워크에 대한 위협에 따라 액세스 제어
메시지 가로채기(man-in-the-middle) 공격과 같은 사용자 네트워크 위협을 검색하고 장치 위험에 따라 WiFi 네트워크에 대한 액세스를 보호합니다.

**WiFi를 통한 네트워크 액세스 차단:**
![네트워크 위협에 따라 조건부 액세스를 통해 WiFi 액세스를 차단하는 모습을 나타낸 다이어그램](../media/mtp/network-wifi-blocked.png)

**해결 시 액세스 허용:**

![위협 해결 시 조건부 액세스를 통해 액세스를 허용하는 모습을 나타낸 다이어그램](../media/mtp/network-wifi-unblocked.png)
### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>네트워크에 대한 위협에 따라 SharePoint Online에 대한 액세스 제어

메시지 가로채기(man-in-the-middle) 공격 같은 네트워크에 대한 위협을 감지하여, 장치 위험에 따라 회사 파일 동기화를 금지합니다.

**네트워크 위협이 감지할 경우 SharePoint Online 차단:**

![발견된 위협에 따라 조건부 액세스를 통해 SharePoint Online에 대한 장치의 액세스를 차단하는 모습을 나타낸 다이어그램](../media/mtp/network-spo-blocked.png)


**수정 시 액세스 권한 부여됨:**

![네트워크 위협이 수정된 후 액세스를 허용하는 조건부 액세스를 보여 주는 다이어그램](../media/mtp/network-spo-unblocked.png)

## <a name="next-steps"></a>다음 단계
이 솔루션을 구현하기 위해 수행해야 하는 주요 단계는 다음과 같습니다.
1.  [장치 위협 방지에 대해 구독 설정](device-threat-protection-subscription-setup.md)
2.  [Intune에서 장치 위협 방지 연결을 사용하도록 설정](device-threat-protection-enable.md)
3.  [장치 위협 방지 앱 구성 및 배포](device-threat-protection-apps.md)
4.  [장치 위협 방지 준수 정책 구성](device-threat-protection-policy.md)
5.  [장치 위협 보호 통합 문제 해결](http://docs.microsoft.com/intune/troubleshoot/device-threat-protection-troubleshooting)



<!--HONumber=Jan17_HO4-->


