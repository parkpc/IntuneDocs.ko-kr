---
title: "iOS용 Intune 앱 구성 정책을 사용하는 방법"
titleSuffix: Intune on Azure
description: "앱 구성 정책을 사용하여 iOS 앱을 실행할 때 이 앱에 구성 데이터를 제공하는 방법을 알아봅니다.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/26/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c9163693-d748-46e0-842a-d9ba113ae5a8
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b261834c85a9dd3cbc6f8fae40933dd7a79acf93
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/03/2017
---
# <a name="how-to-use-microsoft-intune-app-configuration-policies-for-ios"></a>iOS용 Microsoft Intune 앱 구성 정책을 사용하는 방법

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Microsoft Intune에서 앱 구성 정책을 사용하여 사용자가 iOS 앱을 실행할 때 사용되는 설정을 제공할 수 있습니다. 예를 들어 사용자가 앱에서 다음 사항을 지정해야 할 수 있습니다.

-   사용자 지정 포트 번호

-   언어 설정

-   보안 설정

-   회사 로고와 같은 브랜딩 설정

사용자가 이러한 설정을 잘못 입력하면 기술 지원팀의 부담이 증가하며 새 앱 도입이 지연될 수 있습니다.

앱 구성 정책을 사용하는 경우 사용자가 앱을 실행하기 전에 정책에서 이러한 설정을 사용자에게 할당할 수 있으므로 이러한 문제를 방지할 수 있습니다. 배포한 설정은 자동으로 제공되므로 사용자가 아무런 작업을 수행하지 않아도 됩니다. 앱 구성 사용을 지원하도록 앱을 작성해야 합니다. 자세한 내용은 앱 공급업체에 문의하세요.

사용자 및 장치에 이러한 정책을 직접 할당하지는 않으며, 대신 앱에 정책을 연결한 다음 앱을 할당합니다. 정책 설정은 앱에서 해당 설정을 확인할 때마다(일반적으로는 앱을 처음 실행할 때) 사용됩니다.

> [!TIP]
> 이 정책 유형은 현재 iOS 8.0 이상을 실행하는 장치에서만 사용 가능합니다. 지원하는 앱 설치 유형은 다음과 같습니다.
>
> -   **앱 스토어의 관리되는 iOS 앱**
> -   **iOS용 앱 패키지**
>
> 앱 설치 유형에 대한 자세한 내용은 [Microsoft Intune에 앱을 추가하는 방법](apps-add.md)을 참조하세요.

## <a name="create-an-app-configuration-policy"></a>앱 구성 정책 만들기
1.  Azure 포털에 로그인합니다.
2.  **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
3.  **Intune** 블레이드에서 **Mobile Apps**를 선택합니다.
4.  **Mobile apps** 작업에서 **관리** > **앱 구성 정책**을 선택합니다.
5.  정책 목록 블레이드에서 **추가**를 선택합니다.
6.  **구성 정책 추가** 블레이드에서 앱 구성 정책의 **이름** 및 선택적 **설명**을 제공합니다.
7.  **장치 등록 유형**에 대해 다음 중 하나를 선택합니다.
    - **Intune에 등록** - Intune에서 관리하는 앱에 해당합니다.
    - **Intune에 등록되지 않음** - Intune에서 관리되지 않거나 다른 솔루션에서 관리되는 앱에 해당합니다.
8.  **플랫폼**의 경우 **iOS**를 선택합니다(Intune에 등록된 장치만 해당).
9.  **연결된 앱**을 선택한 다음 **연결된 앱** 블레이드에서 구성을 적용할 관리되는 앱을 선택합니다.
10. **구성 정책 추가** 블레이드에서 **구성 설정**을 선택합니다.
11. **구성 설정** 블레이드에서 구성 프로필을 구성하는 XML 값을 지정하는 방법을 다음 중에서 선택합니다.
    - **XML 데이터 입력**(Intune에 등록된 장치만 해당) - 원하는 앱 구성 설정이 포함된 XML 속성 목록을 입력하거나 붙여넣습니다. XML 속성 목록의 형식은 구성하는 앱에 따라 달라집니다. 사용해야 하는 정확한 형식에 대한 자세한 내용은 앱 공급업체에 문의하세요.
Intune에서는 입력한 XML이 올바른 형식인지 확인합니다. 그러나 해당 XML 속성 목록이 연결된 앱에서 작동하는지는 확인하지 않습니다.
XML 속성 목록에 대한 자세한 내용은 iOS Developer Library의 [XML 속성 목록](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html)을 참조하세요.
    - **구성 디자이너 사용**(장치가 Intune에 등록되었는지는 관계없음) - 포털에서 직접 XML 키/값 쌍을 지정할 수 있습니다.
11. 완료되면 **구성 정책 추가** 블레이드로 돌아가서 **만들기**를 누릅니다.

정책이 만들어지고 정책 목록 블레이드에 나타납니다.



>[!Note]
>장치가 Intune에 등록되었는지와 관계없이 [Intune 앱 SDK](https://docs.microsoft.com/intune/app-sdk-ios)를 사용하여 기간 업무 앱이 Intune 앱 보호 정책 및 앱 구성 정책에서 관리되도록 준비할 수 있습니다. 예를 들어 앱 구성 정책을 사용하여 [Intune Managed Browser](app-configuration-managed-browser.md)에 대해 허용된 URL 및 차단된 URL을 구성할 수 있습니다. 앱이 이러한 정책과 호환되면 정책을 사용하여 앱을 구성할 수 있습니다.


할당된 앱은 장치에서 실행될 때 앱 구성 정책에서 구성한 설정을 사용하여 실행됩니다.
하나 이상의 앱 구성 정책이 충돌하는 경우 어떻게 되는지에 대한 자세한 내용은 구성 중인 앱의 설명서를 참조하세요.

>[!Tip]
>또한 Graph API를 사용하여 이러한 작업을 수행할 수 있습니다. 자세한 내용은 [Graph API Reference MAM Targeted Config](https://graph.microsoft.io/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create)(Graph API 참조 MAM 대상 구성)를 참조하세요.


## <a name="information-about-the-xml-file-format"></a>XML 파일 형식에 대한 정보

Intune에서는 속성 목록의 다음 데이터 형식을 지원합니다.

- &lt;integer&gt;
- &lt;real&gt;
- &lt;string&gt;
- &lt;array&gt;
- &lt;dict&gt;
- &lt;true /&gt; 또는 &lt;false /&gt;

데이터 형식에 대한 자세한 내용은 iOS 개발자 라이브러리의 [속성 목록 정보](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/AboutPropertyLists/AboutPropertyLists.html)를 참조하세요.

또한 Intune은 속성 목록에서 다음과 같은 토큰 형식을 지원합니다.
- \{\{userprincipalname\} \} -(예:  **John@contoso.com** )
- \{\{mail\}\} - (예: **John@contoso.com**)
- \{\{partialupn\}\} - (예: **John**)
- \{\{accountid\}\} - (예: **fc0dc142-71d8-4b12-bbea-bae2a8514c81**)
- \{\{deviceid\}\} - (예: **b9841cd9-9843-405f-be28-b2265c59ef97**)
- \{\{userid\}\} - (예: **3ec2c00f-b125-4519-acf0-302ac3761822**)
- \{\{username\}\} - (예: **John Doe**)
- \{\{serialnumber\}\} - (예: **F4KN99ZUG5V2**)(iOS 장치)
- \{\{serialnumberlast4digits\}\} - (예: **G5V2**)(iOS 장치)

\{\{ 및 \}\} 문자는 토큰 형식에만 사용되며 다른 용도로 사용하면 안 됩니다.

## <a name="example-format-for-an-app-configuration-xml-file"></a>앱 구성 XML 파일의 형식 예

앱 구성 파일을 만들 때 이 형식을 사용하여 다음 값 중 하나 이상을 지정할 수 있습니다.

```
<dict>
  <key>userprincipalname</key>
  <string>{{userprincipalname}}</string>
  <key>mail</key>
  <string>{{mail}}</string>
  <key>partialupn</key>
  <string>{{partialupn}}</string>
  <key>accountid</key>
  <string>{{accountid}}</string>
  <key>deviceid</key>
  <string>{{deviceid}}</string>
  <key>userid</key>
  <string>{{userid}}</string>
  <key>username</key>
  <string>{{username}}</string>
  <key>serialnumber</key>
  <string>{{serialnumber}}</string>
  <key>serialnumberlast4digits</key>
  <string>{{serialnumberlast4digits}}</string>
  <key>udidlast4digits</key>
  <string>{{udidlast4digits}}</string>
</dict>

```

## <a name="next-steps"></a>다음 단계

평소대로 앱을 계속 [할당](apps-deploy.md) 및 [모니터링](apps-monitor.md)합니다.