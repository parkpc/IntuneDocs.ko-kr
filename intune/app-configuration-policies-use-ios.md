---
title: "관리되는 iOS 장치용 앱 구성 정책 추가 | Microsoft Docs"
titlesuffix: Azure portal
description: "앱 구성 정책을 사용하여 iOS 앱을 실행할 때 이 앱에 구성 데이터를 제공하는 방법을 알아봅니다."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c9163693-d748-46e0-842a-d9ba113ae5a8
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2226477d40f2bb70dd047ed58e8789fd9bee4ecb
ms.sourcegitcommit: ce35790090ebe768d5f75c108e8d5934fd19c8c7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2017
---
# <a name="add-app-configuration-policies-for-managed-ios-devices"></a>관리되는 iOS 장치용 앱 구성 정책 추가

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Microsoft Intune에서 앱 구성 정책을 사용하여 사용자가 iOS 앱을 실행할 때 설정을 제공할 수 있습니다. 사용자 및 장치에 이러한 정책을 직접 할당하지는 않으며, 대신 앱에 정책을 연결한 다음 앱을 할당합니다. 정책 설정은 앱에서 해당 설정을 확인할 때(일반적으로는 앱을 처음 실행할 때) 사용됩니다.

> [!TIP]
> 이 정책 유형은 현재 iOS 8.0 이상을 실행하는 장치에서만 사용 가능합니다. 지원하는 앱 설치 유형은 다음과 같습니다.
>
> -   **앱 스토어의 관리되는 iOS 앱**
> -   **iOS용 앱 패키지**
>
> 앱 설치 유형에 대한 자세한 내용은 [Microsoft Intune에 앱을 추가하는 방법](apps-add.md)을 참조하세요.

## <a name="create-an-app-configuration-policy"></a>앱 구성 정책 만들기

1. Azure Portal에 로그인합니다.
2. **추가 서비스** > **모니터링 + 관리** + **Intune**을 선택합니다.
3. **모바일 앱** 워크로드를 선택합니다.
4. **관리** 그룹에서 **앱 구성 정책**을 선택한 다음 **추가**를 선택합니다.
5. 다음 세부 정보를 설정합니다.
    - **Name**<br>
      Azure Portal에 표시되는 프로필의 이름입니다.
    - **설명**<br>
      Azure Portal에 표시되는 프로필의 설명입니다.
    - **장치 등록 유형**<br>
      **관리되는 장치**를 선택합니다.
6. **플랫폼**으로 **iOS**를 선택합니다.
7.  **연결된 앱**을 선택합니다. 그런 다음 **연결된 앱** 블레이드에서 구성을 적용할 관리되는 앱을 선택합니다.
8.  **구성 정책 추가** 블레이드에서 **구성 설정**을 선택합니다.
9. **구성 설정 형식**을 선택합니다. 다음 중 하나를 선택합니다.
    - **[구성 디자이너 사용](#Use-the-configuration-designer)**
    - **[XML 데이터 입력](#enter-xml-data)**
10. **확인**을 선택한 다음 **추가**를 선택합니다.

## <a name="use-configuration-designer"></a>구성 디자이너 사용

Intune에 등록되었거나 등록되지 않은 장치에서 앱에 대한 구성 디자이너를 사용할 수 있습니다. 디자이너를 사용하면 특정 구성 키 및 값을 구성할 수 있습니다. 또한 각 값에 대한 데이터 형식을 지정해야 합니다. 설정은 앱을 설치하면 앱에 자동으로 제공됩니다.

### <a name="add-a-setting"></a>설정 추가

1. 구성의 각 키 및 값의 경우 다음을 설정합니다.
   - **구성 키**<br>
     특정 설정 구성을 고유하게 식별하는 키입니다.
   - **값 형식**<br>
     구성 값의 데이터 형식입니다. 형식에는 정수, 실수, 문자열 또는 부울이 포함됩니다.
   - **구성 값**<br>
     구성의 값입니다.
2. **확인**을 선택하여 구성 설정을 설정합니다.

### <a name="delete-a-setting"></a>설정 삭제

1. 설정 옆의 줄임표(**...**)를 선택합니다.
2. **삭제**를 선택합니다.

\{\{ 및 \}\} 문자는 토큰 형식에만 사용되며 다른 용도로 사용하면 안 됩니다.

## <a name="enter-xml-data"></a>XML 데이터 입력

Intune에 등록된 장치에 대한 앱 구성 설정이 포함된 XML 속성 목록을 입력하거나 붙여넣을 수 있습니다. XML 속성 목록의 형식은 구성하는 앱에 따라 달라집니다. 사용할 정확한 형식에 대한 자세한 내용은 앱 공급업체에 문의하세요.

Intune에서 XML 형식의 유효성을 검사합니다. 그러나 Intune은 해당 XML 속성 목록(PList)이 대상 앱에서 작동하는지는 확인하지 않습니다.

XML 속성 목록에 대한 자세한 내용을 보려면 다음을 수행합니다.

  -  [Microsoft Intune에서 모바일 앱 구성 정책을 사용하여 iOS 앱 구성](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)을 읽어 보세요.
  -  iOS 개발자 라이브러리에서 [XML 속성 목록 이해](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html)를 참조하세요.

### <a name="example-format-for-an-app-configuration-xml-file"></a>앱 구성 XML 파일의 형식 예

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
### <a name="supported-xml-plist-data-types"></a>지원되는 XML PList 데이터 형식

Intune에서는 속성 목록의 다음 데이터 형식을 지원합니다.

- &lt;integer&gt;
- &lt;real&gt;
- &lt;string&gt;
- &lt;array&gt;
- &lt;dict&gt;
- &lt;true /&gt; 또는 &lt;false /&gt;

### <a name="tokens-used-in-the-property-list"></a>속성 목록에 사용되는 토큰

또한 Intune은 속성 목록에서 다음과 같은 토큰 형식을 지원합니다.
- \{\{userprincipalname\}\}—예: **John@contoso.com**
- \{\{mail\}\}—예: **John@contoso.com**
- \{\{partialupn\}\}—예: **John**
- \{\{accountid\}\}—예: **fc0dc142-71d8-4b12-bbea-bae2a8514c81**
- \{\{deviceid\}\}—예: **b9841cd9-9843-405f-be28-b2265c59ef97**
- \{\{userid\}\}—예: **3ec2c00f-b125-4519-acf0-302ac3761822**
- \{\{username\}\}—예: **John Doe**
- \{\{serialnumber\}\}—예: **F4KN99ZUG5V2**(iOS 장치)
- \{\{serialnumberlast4digits\}\}—예: **G5V2**(iOS 장치)

## <a name="next-steps"></a>다음 단계

평소대로 앱을 계속 [할당](apps-deploy.md) 및 [모니터링](apps-monitor.md)합니다.