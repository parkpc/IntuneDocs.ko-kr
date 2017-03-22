---
title: "MAM 정책을 사용하여 앱 데이터 보호 | Microsoft 문서"
description: "이 항목에서는 모바일 응용 프로그램 관리 정책이 회사 데이터를 보호하고, 데이터 손실을 방지하고, 개인 및 회사 정보를 별도로 유지되도록 하는 방법을 설명합니다."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ab6cd622-b738-4a63-9c91-56044aaafa6d
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: fbb41a8cf6fada76b72213b8cb04fdc0428515e9
ms.openlocfilehash: 651899219458f799e26ed7957ccef97d7ae2af09
ms.lasthandoff: 02/14/2017


---

# <a name="protect-app-data-using-app-protection-policies-with-microsoft-intune"></a>Microsoft Intune에서 앱 보호 정책을 사용하여 앱 데이터 보호

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="how-you-can-protect-app-data"></a>앱 데이터를 보호하는 방법
직원은 개인 및 회사 작업 둘 다에 모바일 장치를 사용합니다. 직원의 생산성을 유지하는 동시에 의도했거나 의도하지 않은 데이터 손실을 방지하려고 합니다.  또한 관리하지 않는 장치를 사용하여 직원이 액세스하는 회사 데이터를 보호하기를 원합니다.

Intune 앱 보호 정책을 사용하여 회사 데이터를 보호할 수 있습니다. Intune 앱 보호 정책은 **모든 MDM(모바일 장치 관리) 솔루션에 독립적으로** 사용할 수 있으므로 장치 관리 솔루션에 장치를 등록하고도 MAM을 사용하여 회사 데이터를 보호할 수 있습니다. **앱 수준 정책**을 구현하면 회사 리소스에 대한 액세스를 제한하고 IT 부서의 범위 내에 데이터를 유지할 수 있습니다.

앱 보호 정책은 다음 장치에서 실행되는 앱용으로 구성할 수 있습니다.

-   **Microsoft Intune에 등록:** 이 범주의 장치는 일반적으로 회사에서 소유한 장치입니다.

-   **타사 MDM 솔루션에 등록:** 이 범주의 장치는 일반적으로 회사에서 소유한 장치입니다.

      > [!NOTE]
      > 앱 보호 정책을 타사 모바일 응용 프로그램 관리 또는 보안 컨테이너 솔루션과 함께 사용하지 않는 것이 좋습니다.

-   **MDM 솔루션에 등록되지 않음:** 이 범주의 장치는 일반적으로 직원이 소유한 장치로 Intune 또는 기타 MDM 솔루션에서 관리 또는 등록되지 않습니다.

> [!IMPORTANT]
> Office 365 서비스에 연결되는 Office 모바일 앱에 대한 앱 보호 정책을 만들 수 있습니다. 앱 보호 정책은 온-프레미스 Exchange, 비즈니스용 Skype 또는 SharePoint 서비스에 연결하는 앱에 대해서는 지원되지 않습니다.

## <a name="benefits-of-using-app-protection-policies"></a>앱 보호 정책을 사용할 경우의 이점

-   **앱 수준에서 회사 데이터를 보호할 수 있습니다.** 모바일 응용 프로그램 관리에는 장치 관리가 필요하지 않으므로 관리되는 장치와 관리되지 않는 장치 둘 다에서 회사 데이터를 보호할 수 있습니다. 관리는 사용자 ID를 중심으로 하며 장치 관리에 대한 요구 사항이 제거됩니다.

-   **사용자 생산성은 영향을 받지 않으며, 개인 컨텍스트에서 앱을 사용하는 경우 정책이 적용되지 않습니다.** 회사 컨텍스트에서만 정책이 적용되므로 개인 데이터를 변경하지 않고도 회사 데이터를 보호할 수 있습니다.

앱 보호 정책과 함께 MDM을 사용할 경우 추가적인 혜택이 있으며, 회사에서 동시에 사용하거나 MDM을 제외하고 사용할 수 있습니다. 예를 들어 직원이 개인 태블릿뿐만 아니라 회사에서 발급한 휴대폰을 사용할 수 있습니다. 이 경우 회사 휴대폰은 MDM에 등록되고 앱 보호 정책에 의해 보호되며, 개인 장치는 앱 보호 정책에 의해서만 보호됩니다.

- **MDM은 장치가 보호되도록 합니다**. 예를 들어 장치 액세스 시 PIN을 요구하거나, 관리되는 앱을 장치에 배포할 수 있습니다. 앱 관리를 보다 강력하게 제어하기 위해 MDM 솔루션을 통해 장치에 앱을 배포할 수도 있습니다.

- **앱 보호 정책은 앱 계층 보호가 구현되었는지 확인합니다.** 예를 들어 회사 컨텍스트에서 앱을 열 때 PIN을 요구하고, 데이터가 앱 간에 공유되는 것을 방지하고, 회사 앱 데이터가 개인 저장소 위치에 저장되는 것을 방지하는 정책을 유지할 수 있습니다.

## <a name="devices-that-support-mam"></a>MAM을 지원하는 장치
앱 보호 정책은 현재 다음에서 지원됩니다.
-   iOS 8.1 이상
-   Android 4 이상

>[!NOTE]
>등록 시나리오가 없는 MAM에서는 Windows 장치가 지원되지 않습니다. 그러나 Windows 10 장치를 Intune에 등록할 경우 유사한 기능을 제공하는 Windows Information Protection을 사용할 수 있습니다. 자세한 내용은 [WIP(Windows Information Protection)를 사용하여 엔터프라이즈 데이터 보호](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip)를 참조하세요.


##  <a name="how-app-protection-policies-protect-app-data"></a>앱 보호 정책으로 앱 데이터를 보호하는 방법

###  <a name="apps-without-app-protection-policies"></a>앱 보호 정책을 사용하지 않는 앱

![앱 보호 정책이 마련되지 않은 경우 앱 간에 데이터를 자유롭게 이동할 수 있는 방법을 보여 주는 이미지](../media/Apps_without_MAM_policies.png)

앱을 제한 없이 사용하는 경우 회사 및 개인 데이터가 혼합될 수 있습니다. 회사 데이터가 개인 저장소와 같은 위치에 저장되거나 외부 앱으로 전송되어 데이터가 손실될 수 있습니다. 다이어그램에 있는 화살표는 앱(회사 및 개인) 간 및 저장소 위치로의 무제한 데이터 이동을 표시합니다.

### <a name="data-protection-with-app-protection-policies"></a>앱 보호 정책을 사용하여 앱 보호

![앱 보호 정책이 적용된 경우 회사 데이터가 어떻게 보호되는지를 보여 주는 이미지](../media/Apps_with_mobile_app_policies.png)

앱 보호 정책을 사용하여 회사 데이터가 장치의 로컬 저장소에 저장되지 않도록 하고 앱 보호 정책으로 보호되지 않는 다른 앱으로 데이터가 이동되지 않도록 할 수 있습니다. 앱 보호 정책 설정은 다음과 같습니다.
- **다른 이름으로 저장 차단** 및 **잘라내기, 복사 및 붙여넣기 제한**과 같은 데이터 재배치 정책
- **액세스용 단순 PIN 필요** 및 **관리되는 앱이 탈옥 또는 루팅 상태의 장치에서 실행되지 않도록 차단**과 같은 액세스 정책 설정

### <a name="data-protection-with-app-protection-on-devices-that-are-managed-by-a-mdm-solution"></a>MDM 솔루션으로 관리되는 장치에서 앱 보호 정책으로 데이터 보호

![BYOD(Bring Your Own Devices) 장치에서 앱 보호 정책이 작동하는 방식을 보여 주는 이미지](../media/MAM_BYOD_November.png)

**MDM 솔루션에 등록된 장치의 경우**: 위 다이어그램은 MDM 및 앱 보호 정책이 함께 제공하는 보호 계층을 보여 줍니다.

MDM 솔루션에서 다음을 수행합니다.

-   장치를 등록합니다.

-   장치에 앱을 배포합니다.

-   지속적인 장치 규정 준수 및 관리를 제공합니다.

**앱 보호 정책의 이점:**

-   회사 데이터가 소비자 앱과 서비스에 누출되지 않도록 보호

-   모바일 앱에 제한(다른 이름으로 저장, 클립보드, PIN 등) 적용

-   장치에서 해당 앱을 제거하지 않고 앱에서 회사 데이터 초기화


### <a name="data-protection-with-app-protection-policies-for-devices-without-enrollment"></a>등록되지 않은 장치에 대해 앱 보호 정책으로 데이터 보호

![앱 보호 정책이 관리되는 장치에서 작동하는 방식을 보여 주는 이미지](../media/MAM_ManagedDevices_November.png)

위 다이어그램은 MDM 없이 앱 수준에서 데이터 보호 정책이 작동하는 방식을 보여 줍니다.

MDM 솔루션에 등록되지 않은 BYOD 장치의 경우 앱 보호 정책을 통해 앱 수준에서 회사 데이터를 보호할 수 있습니다.

그러나 다음과 같은 몇 가지 제한 사항에 유의해야 합니다.

-   장치에 앱을 배포할 수 없습니다. 사용자가 스토어에서 앱을 구입해야 합니다.

-   해당 장치에서 인증서 프로필을 프로비전할 수 없습니다.

-   해당 장치에서 회사 Wi-Fi 및 VPN 설정을 지정할 수 없습니다.


## <a name="multi-identity"></a>다중 ID

다중 ID를 지원하는 앱을 사용하면 앱이 회사 컨텍스트에서 사용되는 경우 앱 보호 정책이 적용되는 동안 다른 계정(회사 및 개인)을 사용하여 동일한 앱에 액세스할 수 있습니다.  

예를 들어 사용자가 회사 계정을 사용하여 OneDrive 앱을 시작하면 파일을 개인 저장소 위치로 이동할 수 없습니다. 그러나 사용자가 계인 계정으로 OneDrive를 사용하는 경우 개인 OneDrive에서 제한 없이 데이터를 복사 및 이동할 수 있습니다.  

모든 Office 모바일 앱이 다중 ID 액세스를 지원합니다.

##  <a name="next-steps"></a>다음 단계
- [앱 보호 정책 구성 준비](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)

- [Microsoft Intune으로 앱 보호 정책 만들기 및 배포](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)

