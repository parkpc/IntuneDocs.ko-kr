﻿---
title: "SCEP 인증서 인프라 구성"
description: "SCEP 인증서 프로필을 만들고 배포하기 위한 인프라"
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 1/11/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4ae137ae-34e5-4a45-950c-983de831270f
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: kmyrup
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ddf7b2e90b0008e23d550cc347d2c904cc9bc9be
ms.sourcegitcommit: 22ab1c6a6bfeb4fef9850d12b29829c3fecbbeed
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2018
---
# <a name="configure-certificate-infrastructure-for-scep"></a>SCEP 인증서 인프라 구성

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

이 항목에서는 SCEP 인증서 프로필을 만들고 배포하기 위해 필요한 인프라를 설명합니다.

### <a name="on-premises-infrastructure"></a>온-프레미스 인프라

-    **Active Directory 도메인**: 웹 응용 프로그램 프록시 서버를 제외하고 이 섹션에 나열된 모든 서버는 Active Directory 도메인에 가입되어 있어야 합니다.

-  **인증 기관**(CA): Windows Server 2008 R2 이상에서 실행되는 엔터프라이즈 CA(인증 기관)입니다. 독립 실행형 CA는 지원되지 않습니다. 인증 기관을 설정하는 방법에 대한 지침은 [인증 기관 설치](http://technet.microsoft.com/library/jj125375.aspx)를 참조하세요.
    CA에서 Windows Server 2008 R2를 실행하는 경우에는 [KB2483564의 핫픽스를 설치](http://support.microsoft.com/kb/2483564/)해야 합니다.
I
-  **NDES 서버**: Windows Server 2012 R2 이상을 실행하는 서버에 NDES(네트워크 장치 등록 서비스)를 설치해야 합니다. 엔터프라이즈 CA를 실행하는 서버에 NDES가 실행되는 경우 Intune는 사용을 지원하지 않습니다. 네트워크 장치 등록 서비스를 호스트하도록 Windows Server 2012 R2를 구성하는 방법에 대한 지침은 [네트워크 장치 등록 서비스 지침](http://technet.microsoft.com/library/hh831498.aspx)을 참조하세요. NDES 서버는 CA를 호스트하는 도메인에 가입해야 하며 CA와 동일한 서버에 있지 않아야 합니다. 별도의 포리스트, 격리된 네트워크 또는 내부 도메인에 NDES 서버를 배포하는 방법에 대한 자세한 내용은 [네트워크 장치 등록 서비스와 함께 정책 모듈 사용](https://technet.microsoft.com/library/dn473016.aspx) 항목에서 찾아볼 수 있습니다.

-  **Microsoft Intune 인증서 커넥터**: 관리 콘솔을 사용하여 **인증서 커넥터** 설치 관리자(**ndesconnectorssetup.exe**)를 다운로드합니다. 그러면 인증서 커넥터를 설치할 컴퓨터에서 **ndesconnectorssetup.exe** 를 실행할 수 있습니다.
-  **웹 응용 프로그램 프록시 서버**(선택 사항): Windows Server 2012 R2 이상을 WAP(웹 응용 프로그램 프록시) 서버로 실행하는 서버를 사용할 수 있습니다. 이 구성의 특징은 다음과 같습니다.
    -  장치에서 인터넷 연결을 사용하여 인증서를 받을 수 있습니다.
    -  장치가 인터넷을 통해 연결하여 인증서를 받고 갱신하는 경우 보안상 안전합니다.

 > [!NOTE]           
> -    WAP를 호스팅하는 서버에는 네트워크 장치 등록 서비스에서 사용하는 긴 URL을 지원할 수 있도록 하는 [업데이트를 설치](https://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) 해야 합니다. 이 업데이트는 [2014년 12월 업데이트 롤업](https://support.microsoft.com/kb/3013769)에 포함되어 있으며, [KB3011135](https://support.microsoft.com/kb/3011135)에서 개별적으로 다운로드할 수도 있습니다.
>-  또한 WAP를 호스트하는 서버에는 NDES 서버에서 사용되는 SSL 인증서를 신뢰할 뿐만 아니라 외부 클라이언트에 게시된 이름과 일치하는 SSL 인증서가 있어야 합니다. 이러한 인증서를 통해 WAP 서버는 클라이언트와의 SSL 연결을 종료하고 NDES 서버로의 새 SSL 연결을 생성할 수 있습니다.
    WAP용 인증서에 대한 자세한 내용은 **웹 응용 프로그램 프록시를 사용한 응용 프로그램 게시 계획** 의 [인증서 계획](https://technet.microsoft.com/library/dn383650.aspx)섹션을 참조하세요. WAP 서버에 대한 일반 정보는 [웹 응용 프로그램 프록시 작업](http://technet.microsoft.com/library/dn584113.aspx)을 참조하세요.

### <a name="network-requirements"></a>네트워크 요구 사항

인터넷에서 경계 네트워크까지, NDES 서버가 연결된 인터넷에 있는 모든 호스트/IP 주소에서 포트 443을 허용해야 합니다.

경계 네트워크에서 신뢰할 수 있는 네트워크까지, 도메인에 가입된 NDES 서버에서 도메인 액세스에 필요한 모든 포트 및 프로토콜을 허용해야 합니다. NDES 서버는 인증서 서버, DNS 서버, Configuration Manager 서버 및 도메인 컨트롤러에 액세스해야 합니다.

[Azure AD 응용 프로그램 프록시](https://azure.microsoft.com/documentation/articles/active-directory-application-proxy-publish/), [웹 액세스 프록시](https://technet.microsoft.com/library/dn584107.aspx) 또는 타사 프록시와 같은 프록시를 통해 NDES 서버를 게시하는 것이 좋습니다.


### <a name="BKMK_CertsAndTemplates"></a>인증서 및 템플릿

|개체|세부 정보|
|----------|-----------|
|**인증서 템플릿**|발급 CA에서 이 템플릿을 구성합니다.|
|**클라이언트 인증 인증서**|발급 CA 또는 공용 CA에서 이 인증서를 요청한 다음 NDES 서버에 설치합니다.|
|**서버 인증 인증서**|발급 CA 또는 공용 CA에서 이 SSL 인증서를 요청한 다음 NDES 서버의 IIS에 설치 및 바인딩합니다.|
|**신뢰할 수 있는 루트 CA 인증서**|루트 CA 또는 루트 CA를 신뢰하는 장치에서 이 인증서를 **.cer** 파일로 내보낸 후 신뢰할 수 있는 CA 인증서 프로필을 사용하여 장치에 배포합니다.<br /><br />운영 체제 플랫폼당 하나의 신뢰할 수 있는 루트 CA 인증서를 사용하고, 새로 만드는 각 신뢰할 수 있는 루트 인증서 프로필과 연결합니다.<br /><br />필요하면 신뢰할 수 있는 루트 CA 인증서를 추가로 사용할 수 있습니다. 예를 들어, Wi-Fi 액세스 지점의 서버 인증 인증서에 서명하는 CA에 신뢰를 제공하기 위해 사용하게 될 수도 있습니다.|

### <a name="BKMK_Accounts"></a>계정

|이름|세부 정보|
|--------|-----------|
|**NDES 서비스 계정**|NDES 서비스 계정으로 사용할 도메인 사용자 계정을 지정합니다.|

## <a name="BKMK_ConfigureInfrastructure"></a>인프라 구성
인증서 프로필을 구성하려면 먼저 다음 작업을 완료해야 합니다. 이러한 작업을 수행하려면 Windows Server 2012 R2 및 ADCS(Active Directory 인증서 서비스)에 대해 잘 알고 있어야 합니다.

**작업 1**: NDES 서비스 계정 만들기

**작업 2**: 인증 기관에서 인증서 템플릿 구성

**작업 3**: NDES 서버에서 필수 구성 요소 구성

**작업 4**: Intune에 사용할 수 있도록 NDES 구성

**작업 5**: Intune 인증서 커넥터 사용, 설치 및 구성

### <a name="task-1---create-an-ndes-service-account"></a>작업 1 - NDES 서비스 계정 만들기

NDES 서비스 계정으로 사용할 도메인 사용자 계정을 만듭니다. NDES를 설치하고 구성하기 전 발급 CA에서 템플릿을 구성할 때 이 계정을 지정합니다. 사용자에게 기본 권한 즉, **로컬 로그온**, **서비스로 로그온** 및 **일괄 작업으로 로그온** 권한이 있는지 확인합니다. 일부 조직에는 해당 권한을 사용하지 않도록 설정하는 보안 강화 정책이 있습니다.




### <a name="task-2---configure-certificate-templates-on-the-certification-authority"></a>작업 2 - 인증 기관에서 인증서 템플릿 구성
이 작업에서는 다음을 수행합니다.

-   NDES의 인증서 템플릿 구성

-   NDES의 인증서 템플릿 게시

##### <a name="to-configure-the-certification-authority"></a>인증 기관을 구성하려면

1.  엔터프라이즈 관리자로 로그온합니다.

2.  발급 CA에서 인증서 템플릿 스냅인을 사용하여 사용자 지정 템플릿을 새로 만들거나 기존 템플릿을 복사한 다음 NDES에 사용할 수 있도록 기존 템플릿(예: 사용자 템플릿)을 편집합니다.

    템플릿의 다음 항목이 구성되어 있어야 합니다.

    -   템플릿에 친숙한 **템플릿 표시 이름** 을 지정합니다.

    -   **주체 이름** 탭에서 **요청에서 제공**을 선택합니다. 보안은 NDES용 Intune 정책 모듈을 통해 적용됩니다.

    -   **확장** 탭에서 **응용 프로그램 정책 설명** 에 **클라이언트 인증**이 포함되어 있는지 확인합니다.

        > [!IMPORTANT]
        > iOS 및 Mac OS X 인증서 템플릿의 경우 **확장** 탭에서 **키 사용**을 편집하고 **서명이 원본 증명임**이 선택되어 있지 않은지 확인합니다.

    -   On the **보안** 탭에서 NDES 서비스 계정을 추가하고 템플릿에 **등록** 권한을 부여합니다. SCEP 프로필을 만들 Intune 관리자는 SCEP 프로필을 만들 때 템플릿을 찾아볼 수 있도록 **읽기** 권한이 필요합니다.

    > [!NOTE]
    > 인증서를 해지하려면 NDES 서비스 계정에 인증서 프로필에서 사용하는 각 인증서 템플릿에 대한 *인증서 발급 및 관리* 권한이 필요합니다.

3.  템플릿의 **일반** 탭에서 **유효 기간** 을 검토합니다. 기본적으로 Intune은 템플릿에 구성된 값을 사용합니다. 그러나 요청자가 다른 값을 지정할 수 있도록 CA를 구성할 수도 있습니다. 이와 같이 구성하면 Intune 관리자 콘솔 내에서 다른 값을 설정할 수 있습니다. 항상 템플릿의 값을 사용하려면 이 단계의 나머지 부분을 건너뜁니다.

    > [!IMPORTANT]
    > iOS 및 Mac OS X 플랫폼은 다른 구성 내용에 관계없이 항상 템플릿에 설정된 값을 사용합니다.

다음은 템플릿 구성 예제의 스크린샷입니다.

![템플릿, 요청 처리 탭](..\media\scep_ndes_request_handling.png)

![템플릿, 주체 이름 탭](..\media\scep_ndes_subject_name.jpg)

![템플릿, 보안 탭](..\media\scep_ndes_security.jpg)

![템플릿, 확장 탭](..\media\scep_ndes_extensions.jpg)

![템플릿, 발급 요구 사항 탭](..\media\scep_ndes_issuance_reqs.jpg)

>   [!IMPORTANT]
    > 응용 프로그램 정책(4번째 스크린샷)의 경우 필요한 응용 프로그램 정책만 추가합니다. 보안 관리자와 선택 사항을 확인합니다.



요청자가 유효 기간을 지정할 수 있도록 CA를 구성하려면 CA에서 다음 명령을 실행합니다.

   1.  **certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**
   2.  **net stop certsvc**

   3.  **net start certsvc**

4.  발급 CA에서 인증 기관 스냅인을 사용하여 인증서 템플릿을 게시합니다.

    1.  **인증서 템플릿** 노드를 선택하고 **작업** - &gt;**새로 만들기**  &gt;**발급할 인증서 템플릿**을 클릭한 후에 2단계에서 만든 템플릿을 선택합니다.

    2.  **인증서 템플릿** 폴더에서 게시된 템플릿을 확인하여 유효성을 검사합니다.


### <a name="task-3---configure-prerequisites-on-the-ndes-server"></a>작업 3 - NDES 서버에서 필수 구성 요소 구성
이 작업에서는 다음을 수행합니다.

-   Windows Server에 NDES를 추가하고 NDES를 지원하도록 IIS 구성

-   IIS_IUSR 그룹에 NDES 서비스 계정 추가

-   NDES 서비스 계정의 SPN 설정




   1.  NDES를 호스팅할 서버에서 **엔터프라이즈 관리자**로 로그온한 다음 [역할 및 기능 추가 마법사](https://technet.microsoft.com/library/hh831809.aspx) 를 사용하여 NDES를 설치해야 합니다.

    1.  마법사에서 **Active Directory 인증서 서비스** 를 선택하여 AD CS 역할 서비스에 대한 액세스 권한을 받습니다. **네트워크 장치 등록 서비스**를 선택하고 **인증 기관**선택을 취소한 다음 마법사를 완료합니다.

        > [!TIP]
        > 마법사의 **설치 진행률** 페이지에서 **닫기**를 클릭하지 말고 **대상 서버에서 Active Directory 인증서 서비스 구성**링크를 클릭하세요. 그러면 다음 작업에 사용할 **AD CS 구성** 마법사가 열립니다. AD CS 구성이 열리면 역할 및 기능 추가 마법사를 닫을 수 있습니다.

    2.  NDES를 서버에 추가할 때는 마법사에서 IIS도 설치합니다. IIS에서 다음과 같은 구성을 사용하는지 확인합니다.

        -   **웹 서버** &gt; **보안** &gt; **요청 필터링**

        -   **웹 서버** &gt; **응용 프로그램 개발** &gt; **ASP.NET 3.5**. ASP.NET 3.5를 설치하면 .NET Framework 3.5가 설치됩니다. .NET Framework 3.5를 설치할 때는 핵심 **.NET Framework 3.5** 기능과 **HTTP 활성화**를 모두 설치합니다.

        -   **웹 서버** &gt; **응용 프로그램 개발** &gt; **ASP.NET 4.5**. ASP.NET 4.5를 설치하면 .NET Framework 4.5가 설치됩니다. .NET Framework 4.5를 설치할 때는 핵심 **.NET Framework 4.5** 기능, **ASP.NET 4.5** 및 **WCF 서비스** &gt; **HTTP 활성화** 기능을 설치합니다.

        -   **관리 도구** &gt; **IIS 6 관리 호환성** &gt; **IIS 6 메타베이스 호환성**

        -   **관리 도구** &gt; **IIS 6 관리 호환성** &gt; **IIS 6 WMI 호환성**

  2.  서버에서 NDES 서비스 계정을 **IIS_IUSR** 그룹의 구성원으로 추가합니다.

   3.  관리자 권한 명령 프롬프트에서 다음 명령을 실행하여 NDES 서비스 계정의 SPN을 설정합니다.

`**setspn -s http/&lt;DNS name of NDES Server&gt; &lt;Domain name&gt;\&lt;NDES Service account name&gt;**`

   예를 들어 NDES 서버의 이름은 **Server01**, 도메인 이름은 **Contoso.com**, 서비스 계정 이름은 **NDESService**이면 다음 명령을 실행합니다.

`**setspn –s http/Server01.contoso.com contoso\NDESService**`

### <a name="task-4---configure-ndes-for-use-with-intune"></a>작업 4 - Intune에 사용할 수 있도록 NDES 구성
이 작업에서는 다음을 수행합니다.

-   발급 CA에 사용할 수 있도록 NDES 구성

-   IIS에서 서버 인증(SSL) 인증서 바인딩

-   IIS에서 요청 필터링 구성

##### <a name="to-configure-ndes-for-use-with-intune"></a>Intune에 사용할 수 있도록 NDES를 구성하려면

1.  NDES 서버에서 AD CS 구성 마법사를 열고 다음과 같이 구성합니다.

    > [!TIP]
    > 이전 작업에서 링크를 클릭한 경우 이 마법사는 이미 열려 있는 상태입니다. 링크를 클릭하지 않은 경우에는 서버 관리자를 열어 Active Directory 인증서 서비스의 배포 후 구성에 액세스합니다.

    -   **역할 서비스** 페이지에서 **네트워크 장치 등록 서비스**를 선택합니다.

    -   **NDES의 서비스 계정** 페이지에서 NDES 서비스 계정을 지정합니다.

    -   **NDES를 위한 CA** 페이지에서 **선택**을 클릭하고 인증서 템플릿을 구성한 발급 CA를 선택합니다.

    -   **NDES의 암호화** 페이지에서 회사 요구 사항에 맞는 키 길이를 설정합니다.

    **확인** 페이지에서 **구성** 을 클릭하여 마법사를 완료합니다.

2.  마법사를 완료한 후 NDES 서버에서 다음 레지스트리 키를 편집합니다.

    -   **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\MSCEP\**

    이 키를 편집하려면 인증서 템플릿의 **요청 처리** 탭에 나와 있는 **용도**를 확인한 다음 레지스트리에서 해당 항목을 편집합니다. 이렇게 하려면 기존 데이터를 작업 1에서 지정한 인증서 템플릿 이름(템플릿의 표시 이름 아님)으로 바꿉니다. 다음 표는 인증서 템플릿 목적을 레지스트리의 값에 매핑합니다.

    |요청 처리 탭에 나와 있는 인증서 템플릿 용도|편집할 레지스트리 값|SCEP 프로필의 Intune 관리 콘솔에 표시되는 값|
    |--------------------------------------------------------------|--------------------------|------------------------------------------------------------------------------------------------------------|
    |서명|SignatureTemplate|디지털 서명|
    |암호화|EncryptionTemplate|키 암호화|
    |서명 및 암호화|GeneralPurposeTemplate|키 암호화<br /><br />디지털 서명|
    예를 들어 인증서 템플릿의 용도가 **암호화**이면 **EncryptionTemplate** 값을 편집하여 인증서 템플릿의 이름으로 설정합니다.

3. NDES 서버가 매우 긴 URL(쿼리)을 수신하며, 다음과 같은 두 개의 레지스트리 항목을 추가해야 합니다.

    |위치|값|유형|Data|
    |-------|-----|----|----|
    |HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters|MaxFieldLength|DWORD|65534(10진수)|
    |HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters|MaxRequestBytes|DWORD|65534(10진수)|


4. IIS 관리자에서 **기본 웹 사이트** -> **요청 필터링** -> **기능 설정 편집**을 선택하고, 표시된 것처럼 **최대 URL 길이** 및 **최대 쿼리 문자열**을 *65534*로 변경합니다.

    ![IIS 최대 URL 및 쿼리 길이](..\media\SCEP_IIS_max_URL.png)

5.  서버를 다시 시작합니다. 서버에서 **iisreset**을 실행하는 것으로 이러한 변경을 마무리하지는 못합니다.
6. http://*FQDN*/certsrv/mscep/mscep.dll로 이동합니다. 다음과 유사하게 NDES 페이지가 표시됩니다.

    ![NDES 테스트](..\media\SCEP_NDES_URL.png)

    **503 서비스를 사용할 수 없음** 오류가 발생하는 경우 이벤트 뷰어를 확인합니다. 응용 프로그램 풀이 NDES 사용자 권한에 대한 누락으로 인해 중지되었을 가능성이 높습니다. 이러한 권한은 작업 1에 설명되어 있습니다.

##### <a name="to-install-and-bind-certificates-on-the-ndes-server"></a>NDES 서버에서 인증서를 설치하고 바인딩하려면

1.  NDES 서버에서 내부 CA 또는 공용 CA로부터 **서버 인증** 인증서를 요청하여 설치합니다. 그런 다음 IIS에서 SSL 인증서를 바인딩합니다.

    > [!TIP]
    > IIS에서 SSL 인증서를 바인딩한 후에는 클라이언트 인증 인증서도 설치합니다. 이 인증서는 NDES 서버에서 신뢰하는 모든 CA가 발급할 수 있습니다. 가장 적절한 방식은 아니지만 서버 및 클라이언트 인증에 같은 인증서를 사용할 수도 있습니다. 하지만 이 경우 인증서에 서버 인증과 클라이언트 인증 둘 다를 위한 EKU(확장된 키 사용) 기능이 있어야 합니다. 이러한 인증 인증서에 대한 자세한 내용을 보려면 다음 단계를 검토하세요.

    1.  서버 인증 인증서를 가져온 후에 **IIS 관리자**를 열고 **연결** 창에서 **기본 웹 사이트** 를 선택한 다음 **작업** 창에서 **바인딩** 을 클릭합니다.

    2.  **추가**를 클릭하고 **유형** 을 **https**로 설정한 후에 포트가 **443**인지 확인합니다. (독립 실행형 Intune에는 포트 443만 지원됩니다.

    3.  **SSL 인증서**의 경우 서버 인증 인증서를 지정합니다.

        > [!NOTE]
        > NDES 서버가 단일 네트워크 주소에 대해 외부 이름과 내부 이름을 모두 사용하는 경우 서버 인증 인증서에는 외부 공용 서버 이름을 사용하는 **주체 이름** 과 내부 서버 이름을 포함하는 **주체 대체 이름** 이 있어야 합니다.

2.  NDES 서버에서 내부 CA 또는 공용 인증 기관으로부터 **클라이언트 인증** 인증서를 요청하여 설치합니다. 인증서가 두 기능을 모두 포함하는 경우 서버 인증 인증서와 같은 인증서를 사용할 수 있습니다.

    클라이언트 인증 인증서는 다음 속성을 포함해야 합니다.

    **확장된 키 사용** - 여기에는 **클라이언트 인증**이 포함되어야 합니다.

    **주체 이름** - 인증서가 설치되는 서버(NDES 서버)의 DNS 이름과 같아야 합니다.

##### <a name="to-configure-iis-request-filtering"></a>IIS 요청 필터링을 구성하려면

1.  NDES 서버에서 **IIS 관리자**를 열고 **연결** 창에서 **기본 웹 사이트** 를 선택한 후 **요청 필터링**을 엽니다.

2.  **기능 설정 편집**을 클릭하고 다음 항목을 설정합니다.

    **쿼리 문자열(바이트)** = **65534**

    **최대 URL 길이(바이트)** = **65534**

3.  다음 레지스트리 키를 검토합니다.

    **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\HTTP\Parameters**

    다음 값이 DWORD 항목으로 설정되어 있는지 확인합니다.

    이름: **MaxFieldLength**, 십진수 값 **65534**

    이름: **MaxRequestBytes**, 십진수 값 **65534**

4.  NDES 서버를 다시 부팅합니다. 이제 서버가 인증서 커넥터를 지원할 수 있습니다.

### <a name="task-5---enable-install-and-configure-the-intune-certificate-connector"></a>작업 5 - Intune 인증서 커넥터 사용, 설치 및 구성
이 작업에서는 다음을 수행합니다.

Intune에서 NDES를 지원하도록 설정

NDES 서버에서 인증서 커넥터 다운로드, 설치 및 구성

##### <a name="to-enable-support-for-the-certificate-connector"></a>인증서 커넥터에 대한 지원을 사용하도록 설정하려면

1.  [Intune 관리 콘솔](https://manage.microsoft.com)을 열고 **관리자** &gt; **인증서 커넥터**를 클릭합니다.

2.  **온-프레미스 인증서 커넥터 구성**을 클릭합니다.

3.  **인증서 커넥터 사용**을 선택하고 **확인**을 클릭합니다.

##### <a name="to-download-install-and-configure-the-certificate-connector"></a>인증서 커넥터를 다운로드, 설치 및 구성하려면

1.  [Intune 관리 콘솔](https://manage.microsoft.com)을 연 후 **관리자** &gt; **모바일 장치 관리** &gt; **인증서 커넥터** &gt; **인증서 커넥터 다운로드**를 클릭합니다.

2.  다운로드가 완료되면 Windows Server 2012 R2 서버에서 다운로드한 설치 관리자(**ndesconnectorssetup.exe**)를 실행합니다. 설치 관리자가 NDES에 대한 정책 모듈 및 CRP 웹 서비스도 설치합니다. CRP 웹 서비스 CertificateRegistrationSvc는 IIS에서 응용 프로그램으로 실행됩니다.

    > [!NOTE]
    > 독립 실행형 Intune에 NDES를 설치하면 CRP 서비스가 인증서 커넥터와 함께 자동으로 설치됩니다. 구성 관리자와 함께 Intune을 사용할 때는 별도의 사이트 시스템 역할로 인증서 등록 지점을 설치합니다.

3.  인증서 커넥터용 클라이언트 인증서를 선택하라는 메시지가 표시되면 **선택**을 클릭하고 작업 3에서 NDES 서버에 설치한 **클라이언트 인증** 인증서를 선택합니다.

    클라이언트 인증 인증서를 선택하고 나면 **Microsoft Intune 인증서 커넥터용 클라이언트 인증서** 화면으로 돌아가게 됩니다. 선택한 인증서는 표시되지 않지만 **다음** 을 클릭하면 해당 인증서의 속성을 볼 수 있습니다. **다음**, **설치**를 차례로 클릭합니다.

4.  마법사를 완료한 후 마법사를 닫기 전에 **인증서 커넥터 UI 시작**을 클릭합니다.

    > [!TIP]
    > 인증서 커넥터 UI를 시작하기 전에 마법사를 닫은 경우에는 다음 명령을 실행하여 마법사를 다시 열 수 있습니다.
    >
    > **&lt;install_Path&gt;\NDESConnectorUI\NDESConnectorUI.exe**

5.  **인증서 커넥터** UI에서:

    **로그인** 을 클릭하고 Intune 서비스 관리자 자격 증명 또는 전역 관리 권한이 있는 테넌트 관리자의 자격 증명을 입력합니다.

    > [!NOTE]
    > NDESConnectorUI.exe에 로그인할 때 **사용자 이름이 인식되지 않음** 오류가 발생하면 이는 일반적으로 유효한 Intune 라이선스가 없는 계정을 사용했음을 의미합니다. 계정을 Intune 또는 EMS 라이선스에 할당하고 작업을 다시 시도합니다.

    조직에서 프록시 서버를 사용하며 NDES 서버에서 인터넷에 액세스하는 데 프록시가 필요한 경우 **프록시 서버 사용**을 클릭한 후 프록시 서버 이름, 포트 및 계정 자격 증명을 입력하여 연결합니다.

    **고급** 탭을 선택하고 발급 인증 기관에 대한 **인증서 발급 및 관리** 권한이 있는 계정의 자격 증명을 입력한 후에 **적용**을 클릭합니다.

    이제 인증서 커넥터 UI를 닫아도 됩니다.

6.  명령 프롬프트를 열고 **services.msc**를 입력한 후에 **Enter** 키를 누르고 **Intune Connector 서비스**를 마우스 오른쪽 단추로 클릭한 다음 **다시 시작**을 클릭합니다.

서비스가 실행되고 있는지 확인하려면 브라우저를 열고 다음 URL을 입력합니다. 그러면 **403** 오류가 반환됩니다.

**https:// &lt;FQDN_of_your_NDES_server&gt;/certsrv/mscep/mscep.dll**

## <a name="next-steps"></a>다음 단계
이제 [인증서 프로필 구성](Configure-Intune-certificate-profiles.md)에 설명된 대로 인증서 프로필을 구성할 준비가 되었습니다.
