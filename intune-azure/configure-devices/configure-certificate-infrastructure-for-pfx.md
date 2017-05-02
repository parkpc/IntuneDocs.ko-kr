---
title: "Intune을 사용하여 PKCS 인증서 구성 및 관리"
titleSuffix: Intune Azure preview
description: "Intune Azure 미리 보기: 인프라를 구성한 다음 Intune PKCS 인증서 프로필을 만들어 할당하는 방법을 알아봅니다."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/22/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e189ebd1-6ca1-4365-9d5d-fab313b7e979
ms.reviewer: vinaybha
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 8b2bd3ecba0b597bc742ea08872ffe8fc58155cf
ms.openlocfilehash: 11bb2cbcf14abe5966e0b203ba3466adc12bd4dd
ms.lasthandoff: 04/24/2017



---
# <a name="configure-and-manage-pkcs-certificates-with-intune"></a>Intune을 사용하여 PKCS 인증서 구성 및 관리
[!INCLUDE[azure_preview](../includes/azure_preview.md)]

이 항목에서는 Intune에서 인프라를 구성하고 PKCS 인증서를 만들고 할당하는 방법을 보여 줍니다.

조직에서 인증서 기반 인증을 수행하려면 엔터프라이즈 인증 기관이 필요합니다.

PKCS 인증서 프로필을 사용하려면 엔터프라이즈 인증 기관 외에 다음도 필요합니다.

-   인증 기관과 통신할 수 있는 컴퓨터. 또는 인증 기관 컴퓨터 자체를 사용할 수 있습니다.

-  인증 기관과 통신할 수 있는 컴퓨터에서 실행되는 Intune 인증서 커넥터입니다.

## <a name="important-terms"></a>중요한 용어


-    **Active Directory 도메인**: 웹 응용 프로그램 프록시 서버를 제외하고 이 섹션에 나열된 모든 서버는 Active Directory 도메인에 가입되어 있어야 합니다.

-  **인증 기관**: Windows Server 2008 R2 이상의 Enterprise Edition에서 실행되는 엔터프라이즈 CA(인증 기관)입니다. 독립 실행형 CA는 지원되지 않습니다. 인증 기관을 설정하는 방법에 대한 지침은 [인증 기관 설치](http://technet.microsoft.com/library/jj125375.aspx)를 참조하세요.
    CA에서 Windows Server 2008 R2를 실행하는 경우에는 [KB2483564의 핫픽스를 설치](http://support.microsoft.com/kb/2483564/)해야 합니다.

-  **인증 기관과 통신할 수 있는 컴퓨터**: 또는 인증 기관 컴퓨터 자체를 사용합니다.
-  **Microsoft Intune Certificate Connector**: Azure Portal에서 **인증서 커넥터** 설치 관리자(**ndesconnectorssetup.exe**)를 다운로드합니다. 그러면 인증서 커넥터를 설치할 컴퓨터에서 **ndesconnectorssetup.exe** 를 실행할 수 있습니다. PKCS 인증서 프로필에 대해 인증 기관과 통신하는 컴퓨터에 인증서 커넥터를 설치합니다.
-  **웹 응용 프로그램 프록시 서버**(선택 사항): Windows Server 2012 R2 이상을 실행하는 서버를 WAP(웹 응용 프로그램 프록시) 서버로 사용할 수 있습니다. 이 구성의 특징은 다음과 같습니다.
    -  장치에서 인터넷 연결을 사용하여 인증서를 받을 수 있습니다.
    -  장치가 인터넷을 통해 연결하여 인증서를 받고 갱신하는 경우 보안상 안전합니다.

 > [!NOTE]           
> -    WAP를 호스트하는 서버의 경우 NDES(네트워크 장치 등록 서비스)에서 사용하는 긴 URL을 지원할 수 있도록 하는 [업데이트를 설치](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx)해야 합니다. 이 업데이트는 [2014년 12월 업데이트 롤업](http://support.microsoft.com/kb/3013769)에 포함되어 있으며, [KB3011135](http://support.microsoft.com/kb/3011135)에서 개별적으로 다운로드할 수도 있습니다.
>-  또한 WAP를 호스트하는 서버에는 NDES 서버에서 사용되는 SSL 인증서를 신뢰할 뿐만 아니라 외부 클라이언트에 게시된 이름과 일치하는 SSL 인증서가 있어야 합니다. 이러한 인증서를 통해 WAP 서버는 클라이언트와의 SSL 연결을 종료하고 NDES 서버로의 새 SSL 연결을 생성할 수 있습니다.
    WAP용 인증서에 대한 자세한 내용은 **웹 응용 프로그램 프록시를 사용한 응용 프로그램 게시 계획** 의 [인증서 계획](https://technet.microsoft.com/library/dn383650.aspx)섹션을 참조하세요. WAP 서버에 대한 일반 정보는 [웹 응용 프로그램 프록시 작업](http://technet.microsoft.com/library/dn584113.aspx)을 참조하세요.


## <a name="certificates-and-templates"></a>인증서 및 템플릿

|개체|세부 정보|
|----------|-----------|
|**인증서 템플릿**|발급 CA에서 이 템플릿을 구성합니다.|
|**신뢰할 수 있는 루트 CA 인증서**|발급 CA 또는 발급 CA를 신뢰하는 장치에서 이 인증서를 **.cer** 파일로 내보낸 다음 신뢰할 수 있는 CA 인증서 프로필을 사용하여 장치에 할당합니다.<br /><br />운영 체제 플랫폼당 하나의 신뢰할 수 있는 루트 CA 인증서를 사용하고, 새로 만드는 각 신뢰할 수 있는 루트 인증서 프로필과 연결합니다.<br /><br />필요하면 신뢰할 수 있는 루트 CA 인증서를 추가로 사용할 수 있습니다. 예를 들어, Wi-Fi 액세스 지점의 서버 인증 인증서에 서명하는 CA에 신뢰를 제공하기 위해 사용하게 될 수도 있습니다.|


## <a name="configure-your-infrastructure"></a>인프라 구성
인증서 프로필을 구성하려면 다음 단계를 완료해야 합니다. 이러한 단계를 완료하려면 Windows Server 2012 R2 및 ADCS(Active Directory 인증서 서비스)에 대한 지식이 있어야 합니다.

- **1단계** - 인증 기관에서 인증서 템플릿 구성
- **2단계** - Intune 인증서 커넥터 사용, 설치 및 구성

## <a name="step-1---configure-certificate-templates-on-the-certification-authority"></a>1단계 - 인증 기관에서 인증서 템플릿 구성

### <a name="to-configure-the-certification-authority"></a>인증 기관을 구성하려면

1.  발급 CA에서 인증서 템플릿 스냅인을 사용하여 사용자 지정 템플릿을 새로 만들거나 사용자 템플릿과 같은 기존 템플릿을 복사한 후 PKCS에 사용할 수 있도록 편집합니다.

    템플릿은 다음 항목을 포함해야 합니다.

    -   템플릿에 친숙한 **템플릿 표시 이름** 을 지정합니다.

    -   **주체 이름** 탭에서 **요청에서 제공**을 선택합니다. 보안은 NDES용 Intune 정책 모듈을 통해 적용됩니다.

    -   **확장** 탭에서 **응용 프로그램 정책 설명** 에 **클라이언트 인증**이 포함되어 있는지 확인합니다.

        > [!IMPORTANT]
        > iOS 및 macOS 인증서 템플릿의 경우 **확장** 탭에서 **키 사용**을 편집하고 **서명이 원본 증명임**이 선택되어 있지 않음을 확인합니다.

2.  템플릿의 **일반** 탭에서 **유효 기간** 을 검토합니다. 기본적으로 Intune은 템플릿에 구성된 값을 사용합니다. 그러나 요청자가 다른 값을 지정할 수 있도록 CA를 구성할 수도 있습니다. 이와 같이 구성하면 Intune 관리자 콘솔 내에서 다른 값을 설정할 수 있습니다. 항상 템플릿의 값을 사용하려면 이 단계의 나머지 부분을 건너뜁니다.

    > [!IMPORTANT]
    > iOS 및 macOS는 다른 구성 내용에 관계없이 항상 템플릿에 설정된 값을 사용합니다.

    요청자가 유효 기간을 지정할 수 있도록 CA를 구성하려면 CA에서 다음 명령을 실행합니다.

    a.  **certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**

    b.  **net stop certsvc**

    c.  **net start certsvc**

3.  발급 CA에서 인증 기관 스냅인을 사용하여 인증서 템플릿을 게시합니다.

    a.  **인증서 템플릿** 노드를 선택하고 **작업** - &gt;**새로 만들기**  &gt;**발급할 인증서 템플릿**을 클릭한 후에 2단계에서 만든 템플릿을 선택합니다.

    b.  **인증서 템플릿** 폴더에서 게시된 템플릿을 확인하여 유효성을 검사합니다.

4.  CA 컴퓨터에서 Intune 인증서 커넥터를 호스트하는 컴퓨터에 등록 권한이 있는지 확인합니다. 이 권한이 있어야 해당 컴퓨터가 PKCS 인증서 프로필을 만드는 데 사용된 템플릿에 액세스할 수 있습니다. CA 컴퓨터 속성의 **보안** 탭에서 권한을 설정합니다.

## <a name="step-2---enable-install-and-configure-the-intune-certificate-connector"></a>2단계 - Intune 인증서 커넥터 사용, 설치 및 구성
이 단계에서는 다음을 수행합니다.

- 인증서 커넥터에 대한 지원을 사용하도록 설정
- 인증서 커넥터 다운로드, 설치 및 구성

### <a name="to-enable-support-for-the-certificate-connector"></a>인증서 커넥터에 대한 지원을 사용하도록 설정하려면

1.  Azure 포털에 로그인합니다.
2.  **추가 서비스** > **기타** > **Intune**을 선택합니다.
3.  **Intune** 블레이드에서 **장치 구성**을 선택합니다.
2.  **장치 구성** 블레이드에서 **설정** > **인증 기관**을 선택합니다.
2.  **1단계** 아래에서 **사용**을 선택합니다.

### <a name="to-download-install-and-configure-the-certificate-connector"></a>인증서 커넥터를 다운로드, 설치 및 구성하려면

1.  **장치 구성** 블레이드에서 **설정** > **인증 기관**을 선택합니다.
2.  **인증서 커넥터 다운로드**를 선택합니다.
2.  다운로드가 완료되면 다운로드한 설치 관리자(**ndesconnectorssetup.exe**)를 실행합니다.
  인증 기관에 연결할 수 있는 컴퓨터에서 설치 관리자를 실행합니다. PKCS(PFX) 배포 옵션을 선택한 다음 **설치**를 선택합니다. 설치가 완료되면 [인증서 프로필을 구성하는 방법](how-to-configure-certificates.md)에서 설명한 대로 인증서 프로필을 만들어 계속합니다.

3.  인증서 커넥터용 클라이언트 인증서를 선택하라는 메시지가 표시되면 **선택**을 선택하고 설치한 **클라이언트 인증** 인증서를 선택합니다.

    클라이언트 인증 인증서를 선택하고 나면 **Microsoft Intune 인증서 커넥터용 클라이언트 인증서** 화면으로 돌아가게 됩니다. 선택한 인증서는 표시되지 않지만 **다음**을 선택하면 해당 인증서의 속성을 볼 수 있습니다. 그런 후에 **다음**, **설치**를 차례로 선택합니다.

4.  마법사를 완료한 후 마법사를 닫기 전에 **인증서 커넥터 UI 시작**을 클릭합니다.

    > [!TIP]
    > 인증서 커넥터 UI를 시작하기 전에 마법사를 닫은 경우에는 다음 명령을 실행하여 마법사를 다시 열 수 있습니다.
    >
    > **&lt;install_Path&gt;\NDESConnectorUI\NDESConnectorUI.exe**

5.  **인증서 커넥터** UI에서:

    a. **로그인**을 선택하고 Intune 서비스 관리자의 자격 증명이나 전역 관리 권한이 있는 테넌트 관리자의 자격 증명을 입력합니다.

  <!--  If your organization uses a proxy server and the proxy is needed for the NDES server to access the Internet, click **Use proxy server** and then provide the proxy server name, port, and account credentials to connect.-->

    b. **고급** 탭을 선택하고 발급 인증 기관에 대한 **인증서 발급 및 관리** 권한이 있는 계정의 자격 증명을 입력합니다.

    c. **적용**을 선택합니다.

    이제 인증서 커넥터 UI를 닫아도 됩니다.

6.  명령 프롬프트를 열고 **services.msc**를 입력합니다. 그런 다음 **Enter** 키를 누르고 **Intune 커넥터 서비스**를 마우스 오른쪽 단추로 클릭한 후에 **다시 시작**을 선택합니다.

서비스가 실행되고 있는지 확인하려면 브라우저를 열고 다음 URL을 입력합니다. 그러면 **403** 오류가 반환됩니다.

**http:// &lt;FQDN_of_your_NDES_server&gt;/certsrv/mscep/mscep.dll**


### <a name="how-to-create-a-pkcs-certificate-profile"></a>PKCS 인증서 프로필을 만드는 방법

Azure Portal에서 **장치 구성** 워크로드를 선택합니다.
2. **장치 구성** 블레이드에서 **관리** > **프로필**을 선택합니다.
3. 프로필 블레이드에서 **프로필 만들기**를 클릭합니다.
4. **프로필 만들기** 블레이드에서 PKCS 인증서 프로필에 대한 **이름** 및 **설명**을 입력합니다.
5. **플랫폼** 드롭다운 목록에서 이 PKCS 인증서에 대한 장치 플랫폼을 선택합니다.
    - **Android**
    - **Android for Work**
    - **iOS**
    - **Windows 10 이상**
6. **프로필** 유형 드롭다운 목록에서 **PKCS 인증서**를 선택합니다.
7. **PKCS 인증서** 블레이드에서 다음 설정을 구성합니다.
    - **갱신 임계값(%)** - 장치에서 인증서 갱신을 요청하기 전까지 남은 인증서 수명을 백분율로 지정합니다.
    - **인증서 유효 기간** - 발급 CA에 대해 사용자 지정 유효 기간을 허용하는 **certutil - setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE** 명령을 실행한 경우 인증서가 만료될 때까지 남은 기간을 지정할 수 있습니다.<br>지정된 인증서 템플릿에서 유효 기간보다 작은 값은 지정할 수 있지만 높은 값은 지정할 수 없습니다. 예를 들어 인증서 템플릿의 인증서 유효 기간이 2년이면 값을 1년으로 지정할 수는 있어도 5년으로는 지정할 수 없습니다. 또한 이 값은 발급 CA 인증서의 남은 유효 기간보다 작아야 합니다.
    - **KSP(키 저장소 공급자)**(Windows 10): 인증서에 키가 저장될 위치를 지정합니다. 다음 값 중 하나를 선택합니다.
        - **있는 경우 TPM(신뢰할 수 있는 플랫폼 모듈) KSP에 등록, 그렇지 않으면 소프트웨어 KSP에 등록**
        - **TPM(신뢰할 수 있는 플랫폼 모듈) KSP에 등록, 그러지 않으면 실패**
        - **Passport에 등록, 그러지 않으면 실패(Windows 10 이상)**
        - **소프트웨어 KSP에 등록**
    - **인증 기관**: Windows Server 2008 R2 이상의 Enterprise Edition에서 실행되는 엔터프라이즈 CA(인증 기관)입니다. 독립 실행형 CA는 지원되지 않습니다. 인증 기관을 설정하는 방법에 대한 지침은 [인증 기관 설치](http://technet.microsoft.com/library/jj125375.aspx)를 참조하세요. CA에서 Windows Server 2008 R2를 실행하는 경우에는 [KB2483564의 핫픽스를 설치](http://support.microsoft.com/kb/2483564/)해야 합니다.
    - **인증 기관 이름** - 인증 기관의 이름을 입력합니다.
    - **인증서 템플릿 이름** - 네트워크 장치 등록 서비스에서 사용하도록 구성되고 발급 CA에 추가된 인증서 템플릿의 이름을 입력합니다.
    이름이 네트워크 장치 등록 서비스를 실행하는 서버의 레지스트리에 나열된 인증서 템플릿 중 하나와 일치하는지 확인합니다. 또한 인증서 템플릿의 표시 이름이 아닌 인증서 템플릿 이름을 지정했는지 확인합니다. 
    인증서 템플릿의 이름을 찾으려면 HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\MSCEP 키로 이동합니다. 인증서 템플릿이 **EncryptionTemplate**, **GeneralPurposeTemplate**및 **SignatureTemplate**의 값으로 나열됩니다. 기본적으로 모든 세 인증서 템플릿의 값은 IPSECIntermediateOffline이며, 이는 **IPSec(오프라인 요청)**라는 템플릿 표시 이름으로 매핑됩니다. 
    - **주체 이름 형식** - 인증서 요청 시 Intune에서 자동으로 주체 이름을 만드는 방식을 목록에서 선택합니다. 사용자용 인증서인 경우 주체 이름에 사용자의 전자 메일 주소를 포함할 수도 있습니다. 다음 중에서 선택합니다.
        - **구성되지 않음**
        - **일반 이름**
        - **메일이 포함된 일반 이름**
        - **메일인 일반 이름**
    - **주체 대체 이름** - Intune에서 인증서 요청의 SAN(주체 대체 이름) 값을 자동으로 만드는 방법을 지정합니다. 예를 들어 사용자 인증서 유형을 선택한 경우 주체 대체 이름에 UPN(사용자 계정 이름)을 포함할 수 있습니다. 클라이언트 인증서가 네트워크 정책 서버에 대한 인증에 사용되는 경우 주체 대체 이름을 UPN으로 설정해야 합니다.
    - **확장 키 사용**(Android) - **추가**를 클릭하여 인증서의 용도에 대한 값을 추가합니다. 대부분의 경우 인증서는 사용자 또는 장치가 서버에 인증할 수 있는 **클라이언트 인증** 이 필요합니다. 그러나 필요에 따라 다른 키 사용을 추가할 수 있습니다. 
    - **루트 인증서**(Android) - 이전에 구성하고 사용자 또는 장치에 할당한 루트 CA 인증서 프로필을 선택합니다. 이 CA 인증서는 이 인증서 프로필에서 구성하려는 인증서를 발급할 CA에 대한 루트 인증서여야 합니다. 이전에 만들어 놓은 신뢰할 수 있는 인증서 프로필입니다.
8. 완료되면 **프로필 만들기** 블레이드로 돌아가서 **만들기**를 누릅니다.

프로필이 만들어지고 프로필 목록 블레이드에 표시됩니다.

## <a name="how-to-assign-the-certificate-profile"></a>인증서 프로필을 할당하려면

인증서 프로필을 그룹에 할당하기 전에 다음 사항을 고려합니다.

- 인증서 프로필을 그룹에 할당할 때는 신뢰할 수 있는 CA 인증서 프로필의 인증서 파일이 장치에 설치됩니다. 장치에서는 PKCS 인증서 프로필을 사용하여 장치의 인증서 요청을 만듭니다.
- 인증서 프로필은 프로필을 만들 때 사용하는 플랫폼을 실행 중인 장치에만 설치됩니다.
- 사용자 컬렉션 또는 장치 컬렉션에 인증서 프로필을 할당할 수 있습니다.
- 장치를 등록한 후 인증서를 장치에 빠르게 게시하려면 인증서 프로필을 장치 그룹이 아닌 사용자 그룹에 할당합니다. 장치 그룹에 프로필을 할당하는 경우에는 장치에서 정책을 수신하기 전에 전체 장치 등록을 수행해야 합니다.
- 각 프로필을 별도로 할당하더라도 신뢰할 수 있는 루트 CA 및 PKCS 프로필을 할당해야 합니다. 그렇지 않으면 PKCS 인증서 정책에서 오류가 발생합니다.

프로필을 할당하는 방법에 대한 내용은 [장치 프로필을 할당하는 방법](how-to-assign-device-profiles.md)을 참조하세요.

