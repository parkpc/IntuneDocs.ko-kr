---
title: "Intune과 Check Point SandBlast Mobile 커넥터"
titleSuffix: Intune on Azure
description: "Intune과 Check Point SandBlast 통합"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 706a4228-9bdf-41e0-b8d1-64c923dd2d2b
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e722411e7eea11a604cdd2c6f7f818053d0ffbb0
ms.sourcegitcommit: 3b21f20108e2bf1cf47c141b36a7bdae609c4ec3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2017
---
# <a name="check-point-sandblast-mobile-threat-defense-connector-with-intune"></a>Intune과 Check Point SandBlast Mobile Threat Defense 커넥터

Microsoft Intune과 통합된 Mobile Threat Defense 솔루션인 Check Point SandBlast Mobile에서 수행한 위험 평가에 따라 조건부 액세스를 사용하여 회사 리소스에 대한 모바일 장치 액세스를 제어할 수 있습니다. Check Point SandBlast Mobile 앱을 실행하는 장치에서 수집된 원격 분석에 따라 위험이 평가됩니다.

Intune 장치 준수 정책을 통해 사용하도록 설정된 Check Point SandBlast Mobile 위험 평가에 따라 조건부 액세스 정책을 구성할 수 있습니다. 이 정책을 사용하여 회사 리소스에 액세스하는 미준수 장치를 감지된 위협에 따라 허용하거나 차단할 수 있습니다.

## <a name="how-do-intune-and-check-point-sandblast-mobile-help-protect-your-company-resources"></a>Intune과 Check Point SandBlast Mobile이 회사 리소스를 보호하는 데 어떤 도움이 되나요?

Android 및 iOS용 Check Point SandBlast Mobile 앱은 파일 시스템, 네트워크 스택, 장치 및 응용 프로그램 원격 분석(사용 가능한 경우)을 캡처한 다음, 원격 분석 데이터를 Check Point SandBlast 클라우드 서비스로 보내 모바일 위협에 대한 장치의 위험을 평가합니다.

Intune 장치 준수 정책에는 Check Point SandBlast 위험 평가를 기반으로 한 Check Point SandBlast Mobile Threat Defense에 대한 규칙이 포함되어 있습니다. 이 규칙을 사용하면 Intune에서 장치가 사용되는 정책을 준수하는지를 평가합니다. 장치가 정책을 준수하지 않으면 Exchange Online, SharePoint Online 등의 회사 리소스에 대한 사용자의 액세스가 차단됩니다. 사용자는 문제를 해결하고 회사 리소스에 대한 액세스 권한을 다시 얻을 수 있도록 장치에 설치된 Check Point SandBlast 모바일 앱에서 지침을 받습니다.

<!-- ## Sample scenarios

Here are some common scenarios:

### Control access based on threats from malicious apps

When malicious apps such as malware are detected on devices, you can block devices until the threat is resolved:

-   Connecting to corporate e-mail

-   Syncing corporate files with the OneDrive for Work app

-   Accessing company apps

**Block when malicious apps are detected:**

![Check Point MTD block when malicious apps are detected](./media/checkpoint-MTD-2.PNG)

**Access granted on remediation:**

![Check Point MTD access granted](./media/checkpoint-MTD-3.PNG)

### Control access based on threat to network

Detect threats like **Man-in-the-middle** in network, and protect access to Wi-Fi networks based on the device risk.

**Block network access through Wi-Fi:**

![Check Point MTD block network access through Wi-Fi](./media/checkpoint-MTD-4.PNG)

**Access granted on remediation:**

![Check Point MTD Wi-Fi access granted](./media/checkpoint-MTD-5.PNG)

### Control access to SharePoint Online based on threat to network

Detect threats like **Man-in-the-middle** in network, and prevent synchronization of corporate files based on the device risk.

**Block SharePoint Online when network threats are detected:**

![Check Point MTD block SharePoint Online access](./media/checkpoint-MTD-6.PNG)

**Access granted on remediation:**

![Check Point MTD SharePoint Online access granted](./media/checkpoint-MTD-7.PNG)

## Supported platforms

-   **Android 4.1 and later**

-   **iOS 8 and later**

## Pre-requisites

-   Azure Active Directory Premium

-   Microsoft Intune subscription

-   Check Point SandBlast Mobile Threat Defense subscription
    -   See [CheckPoint SandBlast website](https://www.checkpoint.com/) for more information.

## Next steps

[Set up CheckPoint SandBlast Mobile app](mtd-apps-ios-app-configuration-policy-add-assign.md)

[Integrate CheckPoint SandBlast with Intune](checkpoint-sandblast-mobile-mtd-connector-integration.md)

[Enable CheckPoint SandBlast Mobile MTD connector](mtd-connector-enable.md)

[Create CheckPoint SandBlast Mobile device compliance policy](mtd-device-compliance-policy-create.md)
