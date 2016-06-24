---
# required metadata

title: 장치 준수 정책 | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 0775107a-6662-41c8-9404-be14bbb599f3

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: chrisgre
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune의 장치 준수 정책
## 준수 정책이란?
회사 데이터를 보호하려면 회사 앱 및 데이터에 액세스하는 데 사용되는 장치가 PIN 사용과 같은 특정 규칙을 준수하여 장치 및 장치에 저장된 데이터의 암호화에 액세스하는지 확인해야 합니다. 이러한 규칙의 집합은 준수 정책이라고 합니다.

## 준수 정책은 어떻게 사용해야 합니까?
규정 준수 정책을 조건부 액세스 정책과 함께 사용하여 규정 준수 정책 규칙을 준수하는 장치만 메일과 기타 서비스에 액세스할 수 있도록 허용할 수 있습니다. 두 정책을 함께 사용할 수 있는 방법을 이해하려면 [전자 메일 및 O365 서비스에 대한 액세스 제한](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) 문서를 참조하세요.

또한 준수 정책을 조건부 액세스와 독립적으로 사용할 수 있습니다. 독립적으로 사용하는 경우 대상 장치는 평가되고 준수 상태와 함께 보고됩니다. 예를 들어 암호화되지 않는 장치의 수 또는 탈옥 또는 루팅된 장치에 대해 보고할 수 있습니다. 그러나 독립적으로 사용하는 경우 회사 리소스에 대한 액세스 제한이 없습니다.

사용자에게 준수 정책을 배포합니다. 준수 정책을 사용자에게 배포하면 사용자 장치의 준수가 확인됩니다.

다음 테이블은 정책을 조건부 액세스 정책과 함께 사용하는 경우 규정 준수 정책에서 지원하는 장치 유형 및 규정에 위반된 설정을 관리하는 방법을 나열합니다.

--------------

|정책 설정| Windows 8.1 이상| Windows Phone 8.1 이상| iOS 6.0 이상|Android 4.0 이상<br/>Samsung KNOX Standard 4.0 이상|
|-----|----|----|----|
|**PIN 또는 암호 구성** |재구성됨|재구성됨|재구성됨|격리됨|
|**장치 암호화**|해당 없음|재구성됨|재구성됨(PIN 설정)|격리됨|
|**무단 해제 또는 루팅된 장치**|해당 없음|해당 없음|격리됨(설정 아님)|격리됨(설정 아님)|
|**전자 메일 프로필**|해당 없음|해당 없음|격리됨|해당 없음|
|**최소 OS 버전**|격리됨|격리됨|격리됨|격리됨|
|**최대 OS 버전**|격리됨| 격리됨| 격리됨| 격리됨|
|**Windows 상태 증명**|Windows 10 및 Windows 10 Mobile은 격리됩니다.<br /><br />Windows 8.1에는 설정이 적용되지 않습니다.|해당 없음|해당 없음|해당 없음|
--------------
**재구성됨** = 장치 운영 체제에서 준수를 적용하도록 요구합니다. 예를 들어, 사용자는 직접 PIN을 설정해야 합니다.  설정이 비규격인 경우는 없습니다.

**격리됨** = 장치 운영 체제에서 준수를 적용하도록 요구하지 않습니다. 예를 들어, Android 장치에서 사용자에게 장치를 암호화하도록 강제하지 않습니다. 장치가 호환되지 않으면 다음 작업이 수행됩니다.

-   사용자가 조건부 액세스 정책의 대상인 장치가 차단됩니다.

-   회사 포털은 모든 규정 준수 문제에 대해 사용자에게 알립니다.

## 다음 단계
[장치 준수 정책 만들기](create-a-device-compliance-policy-in-microsoft-intune.md)

[장치 준수 정책 배포 및 모니터링](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md)

### 참고 항목
[전자 메일 및 O365 서비스에 대한 액세스 제한](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)


<!--HONumber=Jun16_HO2-->


