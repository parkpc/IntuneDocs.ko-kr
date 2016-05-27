---
# required metadata

title: Microsoft Intune을 사용한 Windows Phone 8.0 관리 설정 | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 61e9b6c3-8795-49b0-8ab2-a9a05ee3ea1f

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Windows Phone 8.0에 대한 장치 관리 설정

Intune을 사용해 Windows Phone 모바일 장치를 관리하려면 먼저 관리 요구 사항을 설정해야 합니다. [DNS CNAME를 만들면](set-up-windows-phone-management-with-microsoft-intune.md) 사용자가 Intune 회사 포털에 연결할 수 있습니다. Windows Phone 8.0에는 장치와 Intune 간의 암호화된 IP 연결을 설정하기 위해 Symantec 인증서가 필요합니다. 또한 인증서는 LOB(기간 업무) 앱에 서명하는 데 필요합니다.

-   **Windows Phone 8.1 및 Windows 10 Mobile**에는 다음의 경우에만 인증서가 필요합니다.

    -   Intune을 사용하여 회사 포털 앱을 배포하려고 합니다.

    -   LOB(기간 업무)(즉, '테스트용으로 로드된') 앱을 배포합니다.

-   **Windows Phone 8** - 필요

![인증서 요구 사항 다이어그램](../media/wpcertreqs.png)

  > [!IMPORTANT]
  > 특정 Windows 및 Windows Phone 모바일 장치를 관리하는 데 사용되는 Symantec 인증서는 [주기적으로 갱신](renew-a-symantec-code-signing-certificate.md)해야 합니다..

Window Phone 모바일 장치 관리에 대한 설치 요구 사항은 장치를 관리하려는 방법에 따라 다릅니다.  회사의 DNS 등록에 두 개의 CNAME를 설정하면 보다 쉽게 등록을 사용할 수 있습니다. 사용자가 저장소에서 회사 포털 앱을 다운로드하려는 경우에 DNS 설정이 구성되었다면 회사 포털을 설정하고 사용자에게 등록 방법을 알려주기만 하면 됩니다.  Windows Phone 8.0 또는 회사 포털을 배포하려는 Windows Phone 8.1의 경우 Symntec 인증서를 사용해 앱에 코드 서명해야 합니다.

## 설정 요구 사항을 구성하여 Windows Phone 관리 사용
1.  **Intune 설정**
    모바일 장치 관리를 아직 준비하지 않은 경우 [모바일 장치 관리 기관](https://technet.microsoft.com/library/mt346013.aspx)을 **Microsoft Intune**으로 설정하고 MDM을 설정하여 관리를 준비합니다.

2.  **등록 서버 주소에 대한 DNS 별칭 설정** (선택 사항)

    DNS 별칭(CNAME 레코드 종류)을 사용하면 등록하는 동안 서버 이름이 자동으로 채워지므로 사용자가 보다 쉽게 장치를 등록할 수 있습니다.

    1.  [Intune 관리 콘솔](http://manage.microsoft.com)에서 **관리** &gt; **모바일 장치 관리** &gt; **Windows Phone**을 클릭합니다..

    2.  회사 웹 사이트의 확인된 도메인 URL을 **확인된 도메인 이름 지정** 상자에 입력하고 **자동 검색 테스트**를 클릭합니다..

    3.  회사의 도메인에 대한 **CNAME** DNS 리소스 레코드를 만들어야 합니다. CNAME 리소스 레코드에는 다음 정보가 포함되어야 합니다.

        |호스트 이름|지시 대상|TTL|
        |-------------|-------------|-------|
        |enterpriseenrollment.company_domain.com|enterpriseenrollment.manage.microsoft.com |1시간|
        |enterpriseregistration.company_domain.com|enterpriseregistration.windows.net|1시간|
        예를 들어, 회사의 웹 사이트가 contoso.com인 경우 DNS에 EnterpriseEnrollment.contoso.com을 manage.microsoft.com으로 리디렉션하는 CNAME을 만들어야 합니다. 확인된 도메인이 둘 이상 있는 경우 각 도메인에 대해 CNAME 레코드를 만듭니다.

        -   `manage.microsoft.com` – 메일의 도메인 이름에서 도메인을 인식하여 Intune 서비스로 리디렉션을 지원합니다.

        -   `enterpriseregistration.windows.net` – 모바일 장치에 대한 작업 공간 조인을 지원합니다. 또한 Windows 8.1에 대한 조건부 액세스도 지원합니다.

    ![Windows Phone 모바일 장치 관리 설정 대화 상자](../media/windows-phone-enrollment.png)

3.  **앱 서명을 지원하기 위한 인증서 관리**
    [Windows Phone 스토어에 액세스하지 않거나 LOB(기간 업무) 앱이 필요한 Windows Phone 8.0 및 Windows Phone 8.1의 경우 필수입니다.]

    Windows Phone 8.0용 회사 포털 앱을 지원하고 Windows Phone 8.1에 회사 앱을 배포하려면 **Symantec Enterprise 모바일 코드 서명 인증서**를 가져와야 합니다. Windows Phone 장치에서는 Symantec 인증서만 신뢰하기 때문에 사용자가 고유의 인증 기관에서 발급한 인증서는 사용할 수 없습니다. 이 인증서는 다음을 위해 필요합니다.

    -   등록 및 휴대폰 관리를 목적으로 [!INCLUDE[winphone8_client_1](../includes/winphone8_client_1_md.md)]에 배포하기 위해 회사 포털 앱에 서명

    -   [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]에서 회사 LOB(기간 업무) 앱을 Windows Phone에 배포할 수 있도록 해당 앱에 서명

    아래 단계에 따라 필요한 인증서를 가져오고 회사 포털 앱에 서명할 수 있습니다. Windows Phone 개발자 센터 계정이 필요하며 Symantec 인증서를 구입해야 합니다.

    1.  **Windows Phone 개발자 센터 가입**
        회사 계정을 구입하기 위해 로그인할 때 사용한 회사 계정 정보를 사용하여 [Windows Phone 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=268442) 에 가입합니다. 이 요청의 경우 코드 서명 인증서를 받기 전에 회사 관리자의 승인을 받아야 합니다.

    2.  **회사 Symantec 인증서 가져오기**
        Symantec ID를 사용하여 [Symantec 웹 사이트](http://go.microsoft.com/fwlink/?LinkId=268441) 에서 인증서를 구입합니다. 인증서를 구입한 후 Windows Phone 개발 센터 계정에서 사용자가 지정한 회사 승인자에게 인증서 요청의 승인을 요청하는 전자 메일이 발송됩니다. Symantec 인증서 요구 사항에 대한 자세한 내용은 [Windows Phone에 Symantec 인증서가 필요한 이유는 무엇인가요?](https://technet.microsoft.com/en-us/library/dn764959.aspx#BKMK_Symantec)를 참조하세요. Windows 장치 등록 FAQ.

    3.  **인증서 가져오기**
        요청이 승인되면 인증서 가져오기에 대한 지침이 포함된 전자 메일을 받습니다. 전자 메일의 지침에 따라 인증서를 가져옵니다.

    4.  **가져온 인증서 확인**
        인증서를 제대로 가져왔는지 확인하려면 **인증서** 스냅인으로 이동하여 **인증서**를 마우스 오른쪽 단추로 클릭하고 **인증서 찾기**를 선택합니다. **포함** 필드에 “Symantec”을 입력하고 **지금 찾기**를 클릭합니다. 가져온 인증서가 결과에 표시됩니다.

        ![Symantec 인증서 찾기](../media/wit.gif)

    5.  **서명 인증서 내보내기**
        인증서가 있는 것을 확인했으면 .pfx 파일을 내보내 회사 포털에 서명할 수 있습니다. **용도**가 "코드 서명"인 Symantec 인증서를 선택합니다. 코드 서명 인증서를 마우스 오른쪽 단추로 클릭하고 **내보내기**를 선택합니다..

        ![서명 인증서 내보내기](../media/wit-walk-cert2.gif)

        **인증서 내보내기 마법사**에서 **예, 개인 키를 내보냅니다.**를 선택한 후 **다음**. **개인 정보 교환 – PKCS #12(.PFX)**를 선택하고 **가능하면 인증 경로에 있는 인증서 모두 포함**을 선택합니다. 마법사를 완료합니다. 자세한 내용은 [개인 키와 함께 인증서 내보내기](http://go.microsoft.com/fwlink/?LinkID=203031)를 참조하세요..

    6.  **회사 포털 앱 다운로드 및 서명**

        Windows Phone 등록을 지원하려면 Windows Phone 8.0 회사 포털 앱에 서명하고 Intune에 업로드해야 합니다.

        1.  **회사 포털 다운로드**
            다운로드 센터에서 [Windows Phone용 Intune 회사 포털](http://go.microsoft.com/fwlink/?LinkId=268440) 을 다운로드합니다. 기본 설치 위치는 다음과 같습니다. `C:\Program Files (x86)\Microsoft Corporation\Windows Intune Company Portal for Windows Phone`.

        2.  **Windows Phone 8.0 SDK 다운로드**
            [Windows Phone SDK](http://go.microsoft.com/fwlink/?LinkId=615570) 다운로드.

        3.  **회사 포털 앱에 코드 서명**
            SDK와 함께 다운로드한 XAPSignTool 앱을 사용하여 Symantec 인증서에서 만든 .pfx 파일로 회사 포털에 서명합니다. 자세한 내용은 [XapSignTool을 사용하여 회사 앱을 서명하는 방법](http://go.microsoft.com/fwlink/?LinkID=280195)을 참조하세요..

    7.  **Intune에 회사 포털 앱 업로드**
        서명한 회사 포털 앱 파일 및 코드 서명 인증서를 업로드하여 최종 사용자가 앱을 사용할 수 있도록 합니다.

        1.  [Intune 관리 콘솔](http://manage.microsoft.com)에서 **관리** &gt; **Windows Phone**을 클릭합니다..

        2.  **서명된 앱 파일 업로드**를 클릭하고 Intune 관리자 ID로 로그인합니다.

        3.  **소프트웨어 설치 파일의 위치 지정**의 **소프트웨어 설치** 페이지에서 코드 서명된 회사 포털 앱 위치로 이동합니다(Windows Phone 8.0의 경우 .xap 또는 Windows Phone 8.1의 경우 .appx).

            Intune을 평가하고 코드 서명된 앱 파일을 평가판 Intune 계정에 업로드하는 경우 **샘플 Symantec 코드 서명 인증서로 서명된 회사 포털 앱 파일 사용** 확인란을 선택 취소합니다.

        4.  내보낸 인증서(.pfx) 파일을 **코드 서명 인증서**에 추가하고 인증서의 암호를 만듭니다.

        5.  **소프트웨어 설명** 페이지에서 사용자가 회사 포털에서 앱에 대한 세부 정보를 볼 때 이 정보가 장치에 표시된다는 점을 고려하여 필드를 완성합니다.

        6.  마법사를 완료합니다. 이제 Windows Phone 8.0 장치를 등록한 사용자는 등록할 때 본인 장치에서 회사 포털 앱을 받을 수 있으며, Windows Phone 8.1 사용자는 회사 포털의 저장소 버전에서 회사 포털 앱을 설치할 수 있습니다.  Windows Phone 8.1 장치가 Windows Phone 스토어에서 차단되었거나 Intune을 사용하여 회사 포털 앱을 배포하려는 경우, Windows Phone 8.1 회사 포털(SSP.appx) 앱을 다운로드하고 서명해야 합니다.

4.  **사용자에게 회사 포털을 사용하여 회사 리소스에 액세스하는 방법 알려주기**
    사용자는 장치를 등록하는 방법과 장치가 관리될 때 발생하는 상황에 대해 알고 있어야 합니다. [Microsoft Intune 사용 방법에 대해 최종 사용자에게 알릴 내용](what-to-tell-your-end-users-about-using-microsoft-intune.md)

## Windows Phone 8.1 회사 포털 앱 배포
Windows Phone 스토어에서 설치하지 않고 Intune을 사용해 회사 포털 앱을 Windows Phone 8.1 장치에 배포할 수 있습니다. Symantec 인증서를 사용해 위의 단계를 통해 Windows Phone 장치 등록을 계속 사용하도록 설정해야 합니다. 그런 다음 Windows Phone 8.1 회사 포털 앱을 다운로드하고 Symantec 인증서로 서명해야 합니다.  사용자가 회사 저장소를 사용하지 않으며 회사 포털을 Windows Phone 8.1 장치에 배포하려는 경우에만 필요합니다.


1.  **회사 포털 다운로드**

    다운로드 센터에서 [Windows Phone 8.1용 Microsoft Intune 회사 포털 앱](http://go.microsoft.com/fwlink/?LinkId=615799)을 다운로드하고 자동으로 압축 해제되는(.exe) 파일을 실행합니다. 이 파일에는 두 개의 파일이 들어 있습니다.

    -   CompanyPortal.appx – Windows Phone 8.1용 회사 포털 설치 앱

    -   WinPhoneCompanyPortal.ps1 – 회사 포털 앱 파일을 Windows Phone 8.1 장치에 배포할 수 있도록 서명하는 데 사용할 수 있는 PowerShell 스크립트

2.  **Windows Phone SDK 다운로드**
    [Windows Phone SDK 8.0](http://go.microsoft.com/fwlink/?LinkId=615570)(http://go.microsoft.com/fwlink/?LinkId=268439)을 다운로드하고 이 SDK를 컴퓨터에 설치합니다. 이 SDK는 응용 프로그램 등록 토큰을 생성하는 데 필요합니다.

3.  **AETX 파일 생성**
    Windows Phone SDK 8.0의 일부인 AETGenerator.exe를 사용하여 Symantec PFX 에서 응용 프로그램 등록 토큰(.aetx) 파일을 생성합니다. AETX 파일을 생성하는 방법에 대한 지침은 [Windows Phone용 응용 프로그램 등록 토큰을 생성하는 방법](https://msdn.microsoft.com/library/windows/apps/jj735576.aspx)을 참조하세요.

4.  **Windows 8.1용 Windows SDK 다운로드**
    [Windows Phone SDK](http://go.microsoft.com/fwlink/?LinkId=613525)(http://go.microsoft.com/fwlink/?LinkId=613525)를 다운로드하여 설치합니다. 참고로 회사 포털 앱에 포함된 PowerShell 스크립트는 기본 설치 위치 `${env:ProgramFiles(x86)}\Windows Kits\8.1`을 사용합니다. 다른 위치에 설치하는 경우 cmdlet 매개 변수에 해당 위치를 포함해야 합니다.

5.  **PowerShell을 사용하여 앱에 코드 서명**
    관리자로 로그인하고 Windows SDK, Symantec Enterprise 모바일 코드 서명 인증서가 설치된 호스트 컴퓨터에서 **Windows PowerShell**을 연 다음 Sign-WinPhoneCompanyPortal.ps1 파일을 찾아 스크립트를 실행합니다.

    **예 1**

    ```
    .\Sign-WinPhoneCompanyPortal.ps1 -InputAppx 'C:\temp\CompanyPortal.appx' -OutputAppx 'C:\temp\CompanyPortalEnterpriseSigned.appx' -PfxFilePath 'C:\signing\cert.pfx' -PfxPassword '1234' -AetxPath 'C:\signing\cert.aetx'
    ```
    이 예에서는 C:\temp\에 있는 CompanyPortal.appx에 서명하고 CompanyPortalEnterpriseSigned.appx를 생성합니다. 이 파일은 PFX 암호 1234를 사용하고 PFX 파일에서 게시자 ID를 읽습니다. 또한 cert.aetx 파일에서 엔터프라이즈 ID도 읽습니다.

    **예 2**

    ```
    .\Sign-WinPhoneCompanyPortal.ps1 -InputAppx 'C:\temp\CompanyPortal.appx' -OutputAppx 'C:\temp\CompanyPortalEnterpriseSigned.appx' -PfxFilePath 'C:\signing\cert.pfx' -PfxPassword '1234' -PublisherId 'OID.0.9.2342.19200300.100.1.1=1000000001, CN="Test, Inc.", OU=Test 1' -EnterpriseId 1000000001
    ```
    이 예에서는 C:\temp\에 있는 CompanyPortal.appx에 서명하고 CompanyPortalEnterpriseSigned.appx를 생성합니다. 이 파일은 PFX 암호 1234를 사용하고 지정된 게시자 ID를 사용합니다.

    **매개 변수:**

    -   `-InputAppx` - 작은 따옴표로 묶은 CompanyPortal.appx 파일에 대한 로컬 경로입니다. 예: 'C:\temp\CompanyPortal.appx'

    -   `-OutputAppx` – 작은 따옴표로 묶은 서명된 회사 포털 앱에 대한 로컬 경로 및 파일 이름입니다. 예: 'C:\temp\CompanyPortalEnterpriseSigned.appx'

    -   `-PfxFilePath` – Symantec 인증서의 내보낸 PFX 파일에 대한 로컬 경로 및 파일 이름입니다. 예: 'C:\signing\cert.pfx'

    -   `-PfxPassword` – 작은 따옴표로 묶은 PFX 파일에 서명하는 데 사용되는 암호입니다. 예: '1234'

    -   `-AetxPath` – 'EnterpriseId' 인수가 정의되지 않은 경우 엔터프라이즈 ID를 읽는 데 사용되는 .aetx 파일에 대한 로컬 경로입니다. 이 인수 또는 EnterpriseId를 제공해야 합니다. 예: 'C:\signing\cert.aetx'

    -   `-PublisherId` - 엔터프라이즈의 게시자 ID입니다. 없는 경우 Symantec Enterprise 모바일 코드 서명 인증서의 '제목' 필드를 사용합니다. 예: 'OID.0.9.2342.19200300.100.1.1=1000000001, CN="Test, Inc.", OU=Test 1'

    -   `-SdkPath` - Windows 8.1용 Windows SDK의 루트 폴더에 대한 경로입니다. 이 인수는 선택 사항이며 기본적으로 ${env:ProgramFiles(x86)}\Windows Kits\8.1입니다.

    -   `-EnterpriseId` - 엔터프라이즈 ID입니다. 이 인수 또는 'AetxPath'를 제공해야 합니다. 이 인수를 제공하지 않으면 AETX 파일에서 엔터프라이즈 ID를 읽습니다. 예: 1000000001

6.  Windows Phone 8.1 회사 포털(SSP.appx) 앱을 배포합니다.

    > [!IMPORTANT]
    > 저장소에서 회사 포털과 ssp.xap를 모두 동시에 설치할 수 있어 사용자에게 혼란을 줄 수 있습니다. 모든 사용자가 ssp.xap를 이용하도록 하려면 저장소 버전의 회사 포털에 차단된 앱을 만듭니다. 모든 Windows Phone 8.1 장치에서 저장소 버전의 회사 포털만 사용하도록 하려면 다음의 세 가지 방법을 선택할 수 있습니다.
    >
    > -   테스트용 로드 앱이 필요하지 않고 Windows Phone 8.0을 지원할 필요가 없는 경우 서명된 signed ssp.xap를 업로드하지 않습니다.
    > -   테스트용 로드 앱이 필요하지만 Windows Phone 8을 등록하지 않은 경우 자동으로 만들어진 ssp.xap 배포를 "사용 가능"에서 "제거"로 변경합니다.
    > -   테스트용 로드 앱을 설치해야 하고 Windows Phone 8.0 장치에서 ssp.xap를 등록 및 수신해야 하는 경우 새로운 ssp.xap 소프트웨어 배포를 만들어 **제거** 작업을 통해 배포합니다. Windows Phone 8.0 장치에서는 강제 설치를 지원하지 않거나 앱을 제거하면 배포를 무시하고, Windows Phone 8.1 장치에서는 제거 작업을 지원하여 ssp.xap를 제거합니다.


<!--HONumber=May16_HO1-->


