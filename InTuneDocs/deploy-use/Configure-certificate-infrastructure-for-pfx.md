---
title: "PFX 인증서 인프라 구성 | Microsoft Intune"
description: ".PFX 인증서 프로필을 만들고 배포합니다."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 11/17/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2c543a02-44a5-4964-8000-a45e3bf2cc69
ms.reviewer: vinaybha
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 7d1f37a2ba2e634fb75058d33eaaccf3aa5845b0
ms.openlocfilehash: 8fc1cc718fd0edae8b8ec4a0a8dc25487eafda2b



---
# <a name="configure-certificate-infrastructure"></a>인증서 인프라 구성
이 항목은 .PFX 인증서 프로필을 만들고 배포하기 위해 필요한 것을 설명합니다.

조직에서 인증서 기반 인증을 수행하려면 엔터프라이즈 인증 기관이 필요합니다.

엔터프라이즈 인증 기관 외에도 .PFX 인증서 프로필을 사용하려면 다음이 필요합니다.

-   인증 기관과 통신할 수 있는 컴퓨터. 또는 인증 기관 컴퓨터 자체를 사용할 수 있습니다.

-  인증 기관과 통신할 수 있는 컴퓨터에서 실행되는 Intune 인증서 커넥터입니다.

## <a name="onpremises-infrastructure-description"></a>온-프레미스 인프라 설명


-    **Active Directory 도메인**: 웹 응용 프로그램 프록시 서버를 제외하고 이 섹션에 나열된 모든 서버는 Active Directory 도메인에 가입되어 있어야 합니다.

-  **인증 기관**: Windows Server 2008 R2 이상의 Enterprise Edition에서 실행되는 엔터프라이즈 CA(인증 기관)입니다. 독립 실행형 CA는 지원되지 않습니다. 인증 기관을 설정하는 방법에 대한 지침은 [인증 기관 설치](http://technet.microsoft.com/library/jj125375.aspx)를 참조하세요.
    CA에서 Windows Server 2008 R2를 실행하는 경우에는 [KB2483564의 핫픽스를 설치](http://support.microsoft.com/kb/2483564/)해야 합니다.

-  **인증 기관과 통신할 수 있는 컴퓨터**: 또는 인증 기관 컴퓨터 자체를 사용합니다.
-  **Microsoft Intune 인증서 커넥터**: 관리 콘솔을 사용하여 **인증서 커넥터** 설치 관리자(**ndesconnectorssetup.exe**)를 다운로드합니다. 그러면 인증서 커넥터를 설치할 컴퓨터에서 **ndesconnectorssetup.exe** 를 실행할 수 있습니다. .PFX 인증서 프로필에 대해 인증 기관과 통신하는 컴퓨터에 인증서 커넥터를 설치합니다.
-  **웹 응용 프로그램 프록시 서버**(선택 사항): Windows Server 2012 R2 이상을 실행하는 서버를 WAP(웹 응용 프로그램 프록시) 서버로 사용할 수 있습니다. 이 구성의 특징은 다음과 같습니다.
    -  장치에서 인터넷 연결을 사용하여 인증서를 받을 수 있습니다.
    -  장치가 인터넷을 통해 연결하여 인증서를 받고 갱신하는 경우 보안상 안전합니다.

 > [!NOTE]           
> -    WAP를 호스트하는 서버의 경우 NDES(네트워크 장치 등록 서비스)에서 사용하는 긴 URL을 지원할 수 있도록 하는 [업데이트를 설치](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx)해야 합니다. 이 업데이트는 [2014년 12월 업데이트 롤업](http://support.microsoft.com/kb/3013769)에 포함되어 있으며, [KB3011135](http://support.microsoft.com/kb/3011135)에서 개별적으로 다운로드할 수도 있습니다.
>-  또한 WAP를 호스트하는 서버에는 NDES 서버에서 사용되는 SSL 인증서를 신뢰할 뿐만 아니라 외부 클라이언트에 게시된 이름과 일치하는 SSL 인증서가 있어야 합니다. 이러한 인증서를 통해 WAP 서버는 클라이언트와의 SSL 연결을 종료하고 NDES 서버로의 새 SSL 연결을 생성할 수 있습니다.
    WAP용 인증서에 대한 자세한 내용은 **웹 응용 프로그램 프록시를 사용한 응용 프로그램 게시 계획** 의 [인증서 계획](https://technet.microsoft.com/library/dn383650.aspx)섹션을 참조하세요. WAP 서버에 대한 일반 정보는 [웹 응용 프로그램 프록시 작업](http://technet.microsoft.com/library/dn584113.aspx)을 참조하세요.


### <a name="certificates-and-templates"></a>인증서 및 템플릿

|개체|세부 정보|
|----------|-----------|
|**인증서 템플릿**|발급 CA에서 이 템플릿을 구성합니다.|
|**신뢰할 수 있는 루트 CA 인증서**|발급 CA 또는 발급 CA를 신뢰하는 장치에서 이 인증서를 **.cer** 파일로 내보낸 다음 신뢰할 수 있는 CA 인증서 프로필을 사용하여 장치에 배포합니다.<br /><br />운영 체제 플랫폼당 하나의 신뢰할 수 있는 루트 CA 인증서를 사용하고, 새로 만드는 각 신뢰할 수 있는 루트 인증서 프로필과 연결합니다.<br /><br />필요하면 신뢰할 수 있는 루트 CA 인증서를 추가로 사용할 수 있습니다. 예를 들어, Wi-Fi 액세스 지점의 서버 인증 인증서에 서명하는 CA에 신뢰를 제공하기 위해 사용하게 될 수도 있습니다.|


## <a name="configure-your-infrastructure"></a>인프라 구성
인증서 프로필을 구성하려면 다음 태스크를 완료해야 합니다. 이러한 태스크를 수행하려면 Windows Server 2012 R2 및 ADCS(Active Directory 인증서 서비스)에 대한 지식이 있어야 합니다.

- **태스크 1** - 인증 기관에서 인증서 템플릿 구성
- **태스크 2** - Intune 인증서 커넥터 사용, 설치 및 구성

### <a name="task-1-configure-certificate-templates-on-the-certification-authority"></a>작업 1 - 인증 기관에서 인증서 템플릿 구성
이 태스크에서는 인증서 템플릿을 게시합니다.

##### <a name="to-configure-the-certification-authority"></a>인증 기관을 구성하려면

1.  발급 CA에서 인증서 템플릿 스냅인을 사용하여 사용자 지정 템플릿을 새로 만들거나 사용자 템플릿과 같은 기존 템플릿을 복사한 후 .PFX에 사용할 수 있도록 편집합니다.

    템플릿은 다음 항목을 포함해야 합니다.

    -   템플릿에 친숙한 **템플릿 표시 이름** 을 지정합니다.

    -   **주체 이름** 탭에서 **요청에서 제공**을 선택합니다. 

    -   **확장** 탭에서 **응용 프로그램 정책 설명** 에 **클라이언트 인증**이 포함되어 있는지 확인합니다.

        > [!IMPORTANT]
        > iOS 및 Mac OS X 인증서 템플릿의 경우 **확장** 탭에서 **키 사용**을 편집하고 **서명이 원본 증명임**이 선택되어 있지 않음을 확인합니다.

2.  템플릿의 **일반** 탭에서 **유효 기간** 을 검토합니다. 기본적으로 Intune은 템플릿에 구성된 값을 사용합니다. 그러나 요청자가 다른 값을 지정할 수 있도록 CA를 구성할 수도 있습니다. 이와 같이 구성하면 Intune 관리자 콘솔 내에서 다른 값을 설정할 수 있습니다. 항상 템플릿의 값을 사용하려면 이 단계의 나머지 부분을 건너뜁니다.

    > [!IMPORTANT]
    > iOS 및 Mac OS X 플랫폼은 다른 구성 내용에 관계없이 항상 템플릿에 설정된 값을 사용합니다.

    요청자가 유효 기간을 지정할 수 있도록 CA를 구성하려면 CA에서 다음 명령을 실행합니다.

    a.  **certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**

    b.  **net stop certsvc**

    c.  **net start certsvc**

3.  발급 CA에서 인증 기관 스냅인을 사용하여 인증서 템플릿을 게시합니다.

    a.  **인증서 템플릿** 노드를 선택하고 **작업** - &gt;**새로 만들기 ** &gt;**발급할 인증서 템플릿**을 클릭한 후에 2단계에서 만든 템플릿을 선택합니다.

    b.  **인증서 템플릿** 폴더에서 게시된 템플릿을 확인하여 유효성을 검사합니다.

4.  CA 컴퓨터에서 Intune 인증서 커넥터를 호스트하는 컴퓨터에 등록 권한이 있는지 확인합니다. 이 권한이 있어야 해당 컴퓨터가 .PFX 프로필을 만드는 데 사용된 템플릿에 액세스할 수 있습니다. CA 컴퓨터 속성의 **보안** 탭에서 권한을 설정합니다.

### <a name="task-2-enable-install-and-configure-the-intune-certificate-connector"></a>작업 2 - Intune 인증서 커넥터 사용, 설치 및 구성
이 작업에서는 다음을 수행합니다.

인증서 커넥터 다운로드, 설치 및 구성

##### <a name="to-enable-support-for-the-certificate-connector"></a>인증서 커넥터에 대한 지원을 사용하도록 설정하려면

1.  [Intune 관리 콘솔](https://manage.microsoft.com)을 열고 **관리자** &gt; **인증서 커넥터**를 선택합니다.

2.  **온-프레미스 인증서 커넥터 구성**을 선택합니다.

3.  **인증서 커넥터 사용**을 선택하고 **확인**을 선택합니다.

##### <a name="to-download-install-and-configure-the-certificate-connector"></a>인증서 커넥터를 다운로드, 설치 및 구성하려면

1.  [Intune 관리 콘솔](https://manage.microsoft.com)을 연 후 **관리자** &gt; **모바일 장치 관리** &gt; **인증서 커넥터** &gt; **인증서 커넥터 다운로드**를 선택합니다.

2.  다운로드가 완료되면 다운로드한 설치 관리자(**ndesconnectorssetup.exe**)를 실행합니다.

  인증 기관에 연결할 수 있는 컴퓨터에서 설치 관리자를 실행합니다. .PFX 배포 옵션을 선택한 다음 **설치**를 선택합니다. 설치가 완료되면 [인증서 프로필 구성](configure-intune-certificate-profiles.md)에서 설명한 대로 인증서 프로필을 만들어 계속합니다.

   <!-- Not sure about step 3 below -->

3.  인증서 커넥터용 클라이언트 인증서를 선택하라는 메시지가 표시되면 **선택**을 선택하고 태스크 3에서 설치한 **클라이언트 인증** 인증서를 선택합니다.

    클라이언트 인증 인증서를 선택하고 나면 **Microsoft Intune 인증서 커넥터용 클라이언트 인증서** 화면으로 돌아가게 됩니다. 선택한 인증서는 표시되지 않지만 **다음**을 선택하면 해당 인증서의 속성을 볼 수 있습니다. 그런 후에 **다음**, **설치**를 차례로 선택합니다.

4.  마법사를 완료한 후 마법사를 닫기 전에 **인증서 커넥터 UI 시작**을 클릭합니다.

    > [!TIP]
    > 인증서 커넥터 UI를 시작하기 전에 마법사를 닫은 경우에는 다음 명령을 실행하여 마법사를 다시 열 수 있습니다.
    >
    > **&lt;install_Path&gt;\NDESConnectorUI\NDESConnectorUI.exe**

5.  **인증서 커넥터** UI에서:

    a. **로그인**을 선택하고 Intune 서비스 관리자의 자격 증명이나 전역 관리 권한이 있는 테넌트 관리자의 자격 증명을 입력합니다.

    b. **고급** 탭을 선택하고 발급 인증 기관에 대한 **인증서 발급 및 관리** 권한이 있는 계정의 자격 증명을 입력합니다.

    c. **적용**을 선택합니다.

    이제 인증서 커넥터 UI를 닫아도 됩니다.

6.  명령 프롬프트를 열고 **services.msc**를 입력합니다. 그런 다음 **Enter** 키를 누르고 **Intune 커넥터 서비스**를 마우스 오른쪽 단추로 클릭한 후에 **다시 시작**을 선택합니다.


### <a name="next-steps"></a>다음 단계
이제 [인증서 프로필 구성](Configure-Intune-certificate-profiles.md)에 설명된 대로 인증서 프로필을 설정할 준비가 되었습니다.



<!--HONumber=Nov16_HO3-->


