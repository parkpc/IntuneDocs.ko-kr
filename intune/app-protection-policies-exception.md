---
title: "응용 프로그램을 위한 데이터 전송 정책 예외"
titleSuffix: Azure portal
description: "Intune 모바일 응용 프로그램 관리(MAM) 데이터 전송 정책에 대한 예외를 만듭니다."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/20/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f9015e3a-c22c-42eb-90e6-ba48dee3a41d
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b24060d1b042322f1c7607aba7266421a0effc52
ms.sourcegitcommit: 80a2eefc1896a42cc2bc16be23093d1abf58b088
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/27/2018
---
# <a name="how-to-create-exceptions-to-the-intune-mobile-application-management-mam-data-transfer-policy"></a>Intune 모바일 응용 프로그램 관리(MAM) 데이터 전송 정책에 대한 예외를 만드는 방법

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

관리자로서 Intune 모바일 응용 프로그램 관리(MAM) 데이터 전송 정책에 대한 예외를 만들 수 있습니다. 예외를 통해 관리되지 않는 응용 프로그램과 관리되는 응용 프로그램 간에 데이터를 전송할 수 있도록 구체적으로 선택할 수 있습니다. 예외 목록에 포함된 관리되지 않는 응용프로그램은 IT의 신뢰를 받아야 합니다. 

>[!WARNING] 
> 데이터 전송 예외 정책의 변경에 책임이 있습니다. 이 정책에 대한 추가는 관리되지 않는 응용프로그램(Intune에서 관리되지 않는 응용프로그램)이 관리되는 응용프로그램의 보호를 받는 데이터에 액세스할 수 있게 합니다. 보호된 데이터에 대한 액세스는 데이터 보안이 유출될 수 있습니다. 조직이 사용해야 하는 응용 프로그램에 대한 데이터 전송 예외만 추가하지만 Intune APP(응용 프로그램 보호 정책)을 지원하지는 않습니다. 또한 데이터 유출 위험으로 간주되지 않는 응용 프로그램에 대한 예외만 추가합니다.

이 기능은 **관리 되는 앱만**으로 설정된 데이터 전송을 사용해 Intune 응용 프로그램 보호 정책을 만들 때 적용됩니다. 관리자가 만드는 예외를 제외하고, 데이터 전송 정책을 **관리되는 앱만**으로 설정하는 경우 데이터 전송은 Intune에서 관리하는 응용 프로그램으로 계속 제한됩니다. 프로토콜(iOS) 또는 패키지(Android)를 사용하여 제한을 만들 수 있습니다.

이 기능을 구성해 Intune MAM 응용 프로그램 보호 정책에 대한 예외가 **데이터 전송을 제한**하게 할 수 있습니다. 이 정책은 데이터가 Intune APP을 지원하지 않는 응용 프로그램에 전송되게 하고자 하는 경우에만 필요합니다. 이 정책을 통해 **관리 되는 앱만**으로 데이터 전송을 설정해 Intune에서 관리하는 응용 프로그램이 URL 프로토콜(iOS) 또는 패키지 이름(Android)에 기반해 관리되지 않는 응용 프로그램을 호출하게 할 수 있습니다. Intune은 중요한 네이티브 응용 프로그램을 기본 예외 목록에 추가합니다. 

## <a name="ios-data-transfer-exceptions"></a>iOS 데이터 전송 예외
IOS를 대상으로 하는 정책의 경우 URL 프로토콜에서 데이터 전송 예외를 구성할 수 있습니다. 예외를 추가하려면 지원되는 URL 프로토콜 정보 찾기 응용 프로그램의 개발자가 제공한 설명서를 확인합니다. IOS 데이터 전송 예외에 대한 자세한 내용은 [iOS 응용 프로그램 보호 정책 설정 - 데이터 전송 예외](app-protection-policy-settings-ios.md#data-transfer-exemptions)를 참조합니다.

## <a name="android-data-transfer-exceptions"></a>Android 데이터 전송 예외
Android 대상으로 하는 정책의 경우 응용 프로그램 패키지 이름으로 데이터 전송 예외를 구성할 수 있습니다. 예외를 추가하고자 하는 응용 프로그램에 대해 **Google Play** 스토어 페이지를 확인해 응용 프로그램 패키지 이름을 찾을 수 있습니다. Android 데이터 전송 예외에 대한 자세한 내용은 [Android 응용 프로그램 보호 정책 설정 - 데이터 전송 예외](app-protection-policy-settings-android.md#data-transfer-exemptions)를 참조합니다.

### <a name="example"></a>예제
**Webex** 패키지를 예외로 MAM 데이터 전송 정책에 추가함으로써 관리되는 Outlook 이메일 메시지 내의 Webex 링크는 Webex 응용 프로그램에서 직접 열 수 있습니다. 데이터 전송은 관리되지 않는 다른 응용 프로그램에서 계속 제한됩니다.

- iOS **Webex** 예: 관리되는 Intune 앱에서 호출할 수 있도록 **Webex** 앱을 제외하려면 다음 문자열 <code>wbx</code>에 대한 데이터 전송 예외를 추가해야 합니다.

- Android **Webex** 예: 관리되는 Intune 앱에서 호출할 수 있도록 **Webex** 앱을 제외하려면 다음 문자열 <code>com.cisco.webex.meetings</code>에 대한 데이터 전송 예외를 추가해야 합니다. 

## <a name="next-steps"></a>다음 단계

- [앱 보호 정책 만들기 및 배포](app-protection-policies.md)
- [iOS 앱 보호 정책 설정 - 데이터 전송 예외](app-protection-policy-settings-ios.md#data-transfer-exemptions)
- [Android 앱 보호 정책 설정 - 데이터 전송 예외](app-protection-policy-settings-android.md#data-transfer-exemptions)
