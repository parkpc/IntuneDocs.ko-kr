---
# required metadata

title: 관리 브라우저 정책을 사용하여 인터넷 액세스 관리 | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: dc946303-e09b-4d73-8bf4-87742299bc54

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune에서 관리 브라우저 정책을 사용하여 인터넷 액세스 관리
관리 브라우저는 Microsoft Intune을 사용하여 조직에서 배포할 수 있는 웹 브라우징 응용 프로그램입니다. 관리 브라우저 정책은 관리 브라우저의 사용자가 방문할 수 있는 웹 사이트를 제한하는 허용 목록 또는 차단 목록을 구성합니다.

이 앱은 관리 앱이므로 잘라내기, 복사 및 붙여넣기 제어, 화면 캡처 방지, 사용자가 클릭하는 콘텐츠에 대한 링크를 다른 관리 앱에서만 열리게 하는 기능 등과 같은 모바일 응용 프로그램 관리 정책을 앱에 적용할 수 있습니다. 자세한 내용은 [Microsoft Intune 콘솔에서 모바일 응용 프로그램 관리 정책 구성 및 배포](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md)를 참조하세요..

> [!IMPORTANT]
>사용자가 앱 스토어에서 Managed Browser를 설치하며 브라우저가 Intune에서 관리되지 않는 경우 다음 동작이 적용됩니다.
iOS – Managed Browser 앱을 기본 웹 브라우저로 사용할 수 있지만 일부 기능이 제공되지 않으며 다른 Intune 관리 앱의 데이터에 액세스할 수 없습니다.
Android – Managed Browser 앱을 사용할 수 없습니다.
사용자가 iOS 9보다 이전 버전이 있는 iOS 장치에 Managed Browser를 직접 설치하는 경우에는 만든 정책에 의해 관리되지 않습니다. 브라우저가 Intune을 통해 관리되게 하려면 앱을 관리 앱으로 배포하기 전에 제거해야 합니다. iOS 9 이상에서 사용자가 Managed Browser를 직접 설치하는 경우 정책에 의해 관리될 수 있도록 허용하라는 메시지가 표시됩니다.

다음 장치 유형에 대한 관리 브라우저 정책을 만들 수 있습니다.

-   Android 4 이상을 실행하는 장치

-   iOS 7.1 이상을 실행하는 장치

Intune Managed Browser는 [Microsoft Intune 응용 프로그램 파트너](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx)에서 웹 콘텐츠 열기를 지원합니다..

## 관리 브라우저 정책 만들기

1.  [Microsoft Intune 관리 콘솔](https://manage.microsoft.com)에서 **정책** &gt; **정책 추가**를 클릭합니다..

2.  다음 **소프트웨어** 정책 유형 중 하나를 구성합니다.

    -   **관리되는 브라우저 정책(Android 4 이상)**

    -   **Managed Browser 정책(iOS 7.1 이상)**

    정책을 만들고 배포하는 방법에 대한 자세한 내용은 [Microsoft Intune 정책을 사용하여 장치에 관한 설정 및 기능 관리](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) 항목을 참조하세요.

3.  다음 테이블을 사용하여 관리 브라우저 정책 설정을 쉽게 구성할 수 있습니다.

|설정 이름|세부 정보|
    |----------------|--------------------|
    |**Name**|Intune 콘솔에서 쉽게 식별할 수 있도록 관리 브라우저 정책에 대한 고유한 이름을 입력합니다.|
    |**설명**|관리 브라우저 정책의 개요에 대한 설명과 찾을 때 도움이 되는 기타 관련 정보를 제공합니다.|
    |**사용하도록 설정하면 허용 목록 또는 차단 목록을 사용하여 관리 브라우저에서 열 수 있는 URL을 제한할 수 있습니다.**|다음 옵션 중 하나를 선택합니다.<br /><br />**Managed Browser가 아래 나열된 URL만 열 수 있도록 허용** – Managed Browser에서 열 수 있는 URL 목록을 지정합니다.<br /><br />**Managed Browser가 아래에 나열된 URL을 열지 못하도록 차단** – Managed Browser에서 열 수 있는 URL 목록을 지정합니다. **참고:** 동일한 Managed Browser 정책에 허용 URL과 차단 URL을 함께 포함할 수 없습니다.<br />지정할 수 있는 URL에 대한 자세한 내용은 이 항목의 **허용 및 차단 URL에 대한 URL 형식**을 참조하세요.|

4.  작업이 끝나면 **정책 저장**을 클릭합니다..

새 정책이 **정책** 작업 영역의 **구성 정책** 노드에 표시됩니다.

## 관리 브라우저 앱에 대한 배포 만들기
관리 브라우저 정책을 만든 후 관리 브라우저 앱에 대한 소프트웨어 배포를 만든 후 만든 관리 브라우저 정책과 연결할 수 있습니다.

> [!IMPORTANT]
> 관리 브라우저 정책은 다른 Intune 정책과 같은 방법으로 배포되지 않습니다. 이 유형의 정책은 관리 브라우저 소프트웨어 패키지와 연결되어야 합니다.

**모바일 앱 관리** 페이지에서 정책을 앱과 연결하기 위한 관리 브라우저 정책이 확실히 선택되도록 앱을 배포합니다.

앱을 배포하는 방법에 대한 자세한 내용은 [Microsoft Intune에서 앱 배포](deploy-apps-in-microsoft-intune.md)를 참조하세요..

## 관리 브라우저에 대한 보안 및 개인 정보

-   iOS 장치에서 만료되거나 신뢰할 수 없는 인증서가 있는 웹 사이트를 사용자가 방문하면 해당 웹 사이트를 열 수 없습니다.

-   사용자가 자신의 장치에서 기본 제공 브라우저에 대해 구성하는 설정은 관리 브라우저에서 사용되지 않습니다. 관리 브라우저는 이러한 설정에 액세스할 수 없기 때문입니다.

-   관리 브라우저와 연결된 모바일 응용 프로그램 관리 정책에 **액세스하려면 단순 PIN 필요** 또는 **액세스하려면 회사 자격 증명 필요** 옵션을 구성했는데 사용자가 인증 페이지의 도움말 링크를 클릭한 경우 해당 사용자는 관리 브라우저 정책의 차단 목록에 추가되었는지 여부와 상관없이 아무 인터넷 사이트나 탐색할 수 있습니다.

-   관리 브라우저는 직접 액세스하는 사이트에 대한 액세스만 차단할 수 있습니다. 중간 서비스(변환 서비스 등)를 사용하여 사이트에 액세스하는 경우 액세스를 차단할 수 없습니다.

-   인증을 허용하고 Intune 문서에 액세스할 수 있도록 하기 위해 **&#42;.microsoft.com**은 허용 또는 차단 목록 설정에서 제외되며 항상 허용됩니다.

### 사용 데이터 해제
Microsoft는 Microsoft 제품 및 서비스를 개선하기 위해 Managed Browser의 성능 및 사용에 대한 익명의 데이터를 자동으로 수집하지만 사용자가 장치의 **사용 현황 데이터** 설정을 사용하여 데이터 수집 기능을 끌 수 있습니다. 이 데이터의 수집은 제어할 수 없습니다.

## 참조 정보

### 허용 및 차단 URL에 대한 URL 형식
다음 정보를 사용하여 허용 및 차단 목록에 URL을 지정할 때 사용할 수 있는 형식 및 와일드카드에 대해 알아볼 수 있습니다.

-   아래와 같은 허용 패턴 목록의 규칙에 따라 와일드카드 기호 '**&#42;**'를 사용할 수 있습니다.

-   URL을 목록에 입력할 때 모든 URL의 앞에 **http** 또는 **https** 를 덧붙여야 합니다.

-   주소에 포트 번호를 지정할 수 있습니다. 포트 번호를 지정하지 않은 경우 다음 값이 사용됩니다.

    -   http의 경우 포트 80

    -   https의 경우 포트 443

    포트 번호에 대한 와일드 카드 사용은 지원되지 않습니다. 예: **http://www.contoso.com:*;** and **http://www.contoso.com: /*;**

-   다음 표를 사용하여 URL을 지정할 때 사용할 수 있는 패턴에 대해 알아볼 수 있습니다.

|URL|세부 정보|일치하는 항목|일치하지 않는 항목|
    |-------|---------------|-----------|------------------|
    |http://www.contoso.com|단일 페이지와 일치|www.contoso.com|host.contoso.com<br /><br />www.contoso.com/images<br /><br />contoso.com/|
    |http://contoso.com|단일 페이지와 일치|contoso.com/|host.contoso.com<br /><br />www.contoso.com/images<br /><br />www.contoso.com|
    |http://www.contoso.com/&#42;|www.contoso.com으로 시작하는 모든 URL과 일치|www.contoso.com<br /><br />www.contoso.com/images<br /><br />www.contoso.com/videos/tvshows|host.contoso.com<br /><br />host.contoso.com/images|
    |http://&#42;.contoso.com/&#42;|contoso.com 아래의 모든 하위 도메인과 일치|developer.contoso.com/resources<br /><br />news.contoso.com/images<br /><br />news.contoso.com/videos|contoso.host.com|
    |http://www.contoso.com/images|단일 폴더와 일치|www.contoso.com/images|www.contoso.com/images/dogs|
    |http://www.contoso.com:80|포트 번호를 사용하여 단일 페이지와 일치|http://www.contoso.com:80||
    |https://www.contoso.com|안전한 단일 페이지와 일치|https://www.contoso.com|http://www.contoso.com|
    |http://www.contoso.com/images/&#42;|단일 폴더 및 모든 하위 폴더와 일치|www.contoso.com/images/dogs<br /><br />www.contoso.com/images/cats|www.contoso.com/videos|

-   다음은 지정할 수 없는 몇몇 입력의 예입니다.

    -   &#42;.com

    -   &#42;.contoso/&#42;

    -   www.contoso.com/&#42;images

    -   www.contoso.com/&#42;images&#42;pigs

    -   www.contoso.com/page&#42;

    -   IP 주소

    -   https://&#42;

    -   http://&#42;

    -   http://www.contoso.com:&#42;

    -   http://www.contoso.com: /&#42;

### 허용 목록과 차단 목록 간의 충돌을 해결하는 방법
여러 관리 브라우저 정책을 장치에 배포했는데 설정이 충돌하면 모드(허용 또는 차단)와 URL 목록에 대해 모두 충돌을 평가합니다. 충돌이 발생할 경우 다음 동작이 적용됩니다.

-   각 정책의 모듈이 같지만 URL 목록이 서로 다르면 해당 장치에 URL이 적용되지 않습니다.

-   각 정책의 모듈이 서로 다르지만 URL 목록이 같으면 해당 장치에 URL이 적용되지 않습니다.

-   장치가 처음으로 관리 브라우저 정책을 받고 있는데 두 정책이 충돌하면 해당 장치에 URL이 적용되지 않습니다. **정책** 작업 영역의 **정책 충돌** 노드를 사용하여 충돌을 볼 수 있습니다.

-   장치가 관리 브라우저 정책을 이미 받았는데 두 번째 정책이 충돌하는 설정을 가지고 배포되는 경우 원래 설정은 해당 장치에 유지됩니다. **정책** 작업 영역의 **정책 충돌** 노드를 사용하여 충돌을 볼 수 있습니다.


<!--HONumber=May16_HO1-->


