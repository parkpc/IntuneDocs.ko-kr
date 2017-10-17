---
title: "iOS 모바일 앱 구성 정책 사용"
description: "Intune에서 모바일 앱 구성 정책을 사용하여 사용자가 iOS 앱을 실행할 때 필요할 수도 있는 설정을 제공할 수 있습니다."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fc6b645a-e837-4b2a-a10f-144065cbd8dd
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 31acadce1af55b2ce751b4c6b5bfead27fce3c8c
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/10/2017
---
# <a name="configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune"></a>Microsoft Intune에서 모바일 앱 구성 정책을 사용하여 iOS 앱 구성

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune에서 모바일 앱 구성 정책을 사용하여 사용자가 앱을 실행할 때 필요할 수 있는 설정을 제공할 수 있습니다. 예를 들어 사용자가 앱에서 다음 사항을 지정해야 할 수 있습니다.

-   사용자 지정 포트 번호

-   언어 설정

-   보안 설정

-   회사 로고와 같은 브랜딩 설정

사용자가 이러한 설정을 잘못 입력하면 기술 지원팀의 부담이 증가하며 새 앱 도입이 지연됩니다.

모바일 앱 구성 정책을 사용하는 경우 사용자가 앱을 실행하기 전에 정책에서 이러한 설정을 사용자에게 배포할 수 있으므로 이와 같은 문제를 방지할 수 있습니다. 배포한 설정은 자동으로 제공되므로 사용자가 아무런 작업을 수행하지 않아도 됩니다.

사용자 및 장치에 이러한 정책을 직접 배포하지는 않으며, 대신 앱에 정책을 연결한 다음 앱을 배포합니다. 정책 설정은 앱에서 해당 설정을 확인할 때마다(일반적으로는 앱을 처음 실행할 때) 사용됩니다.

> [!TIP]
> 이 정책 유형은 현재 iOS 8.0 이상을 실행하는 장치에서만 사용 가능합니다. 지원하는 앱 설치 유형은 다음과 같습니다.
>
> -   **앱 스토어의 관리되는 iOS 앱**
> -   **iOS용 앱 패키지**
>
> 앱 설치 유형에 대한 자세한 내용은 [Microsoft Intune을 사용하여 앱 배포](deploy-apps.md) 항목을 참조하세요.

## <a name="configure-a-mobile-app-configuration-policy"></a>모바일 앱 구성 정책 구성

1.  [Microsoft Intune 관리 콘솔](https://manage.microsoft.com)에서 **정책** &gt; **개요** &gt; **정책 추가**를 선택합니다.

2.  정책 목록에서 **iOS**를 확장하고 **모바일 앱 구성**을 선택한 다음 **정책 만들기**를 선택합니다.

    > [!TIP]
    > 이 정책 유형에는 사용자 지정 설정만 구성할 수 있습니다. 권장 설정은 사용할 수 없습니다.

3.  **정책 만들기** 페이지의 **일반** 섹션에서 모바일 앱 구성 정책의 이름을 입력하고 원하는 경우 설명을 입력합니다.

4.  해당 페이지의 **모바일 앱 구성 정책** 섹션에서 상자에 원하는 앱 구성 설정이 포함된 XML 속성 목록을 입력하거나 붙여 넣습니다. XML 속성 목록의 형식은 구성하는 앱에 따라 달라집니다. 사용해야 하는 정확한 형식에 대한 자세한 내용은 앱 공급업체에 문의하세요.

    > [!TIP]
    > XML 속성 목록에 대한 자세한 내용은 iOS 개발자 라이브러리의 [XML 속성 목록 이해](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html)를 참조하세요.

5.  **유효성 검사** 를 클릭하여 입력한 XML이 올바른 속성 목록 형식인지 확인합니다.

    > [!IMPORTANT]
    > **유효성 검사**를 클릭하면 Intune에서는 입력한 XML이 올바른 형식인지 확인합니다. 그러나 해당 XML 속성 목록이 연결된 앱에서 작동하는지는 확인되지 않습니다.

6.  완료되면 **정책 저장**을 클릭합니다.

새 정책이 **구성 정책** 노드에 표시됩니다.

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

## <a name="associate-a-mobile-app-configuration-policy-with-an-app"></a>앱에 모바일 앱 구성 정책 연결
모바일 앱 구성 정책을 만든 후에는 구성 정책의 설정을 적용할 iOS 앱에 해당 정책을 연결해야 합니다.

이렇게 하려면 [Microsoft Intune에서 모바일 장치에 앱 배포](add-apps-for-mobile-devices-in-microsoft-intune.md) 및 [Microsoft Intune을 사용하여 앱 배포](deploy-apps-in-microsoft-intune.md)에 나와 있는 앱 배포를 만드는 단계를 수행합니다. 마법사에서 **모바일 앱 구성** 페이지가 표시되면 **앱 구성 정책** 드롭다운 목록에서 앱과 연결할 정책을 선택합니다.

그런 다음 일반적인 방식으로 앱을 배포하고 배포를 모니터링합니다.

배포된 앱은 장치에서 실행하면 모바일 앱 구성 정책에서 구성한 설정을 사용하여 실행됩니다.

> [!TIP]
> 하나 이상의 모바일 앱 구성 정책이 충돌하는 경우에는 어떤 정책도 적용되지 않습니다. 충돌 내용은 Intune 관리 콘솔 **대시보드**에 보고됩니다.

## <a name="example-format-for-a-mobile-app-configuration-xml-file"></a>모바일 앱 구성 XML 파일의 형식 예

모바일 앱 구성 파일을 만들 때 이 형식을 사용하여 다음 값 중 하나 이상을 지정할 수 있습니다.

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
