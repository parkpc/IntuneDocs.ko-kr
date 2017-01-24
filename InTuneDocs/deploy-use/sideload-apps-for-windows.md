---
title: "Windows 및 Windows Phone용 앱을 테스트용으로 로드 | Microsoft 문서"
description: "Intune을 사용하여 LOB(기간 업무) 앱을 배포할 수 있도록 앱에 서명하는 방법을 알아봅니다."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: e44f1756-52e1-4ed5-bf7d-0e80363a8674
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 2e8220f850e3b38a24aa4c48bcc3a59088251c24


---
# <a name="sign-line-of-business-apps-so-they-can-be-deployed-to-windows-devices-with-intune"></a>Intune으로 Windows 장치에 기간 업무 앱을 배포할 수 있도록 앱에 서명

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune 관리자는 회사 포털 앱을 비롯한 LOB(기간 업무) 앱을 Windows 및 Windows 10 Mobile 장치에 배포할 수 있습니다. Windows 10 및 Windows 10 Mobile 장치에 .appx 또는 .xap 앱을 배포하거나 Windows 8.1 또는 Windows Phone 8.1 장치에 LOB 앱을 배포하려면 **Symantec Enterprise 모바일 코드 서명 인증서**를 얻어야 합니다. 해당 Windows 장치에서 이러한 앱용으로 Symantec 인증서만 신뢰할 수 있습니다. Windows 10 앱 및 "유니버설" 앱에는 사용자 고유의 인증 기관을 사용할 수 있습니다. 이 인증서는 다음을 위해 필요합니다.

-   Windows PC, Windows 10 Mobile 장치 및 Windows Phone 장치에 배포하기 위해 회사 포털 앱에 서명

-   Intune에서 회사 기간 업무 앱을 Windows 장치에 배포할 수 있도록 해당 앱에 서명

아래 단계에 따라 필요한 인증서를 가져오고 앱에 서명할 수 있습니다. Windows Phone 개발자 센터 계정이 필요하며 Symantec 인증서를 구입해야 합니다.


1. **Windows Phone 개발자 센터 가입**<br>
   회사 계정을 구입하기 위해 로그인할 때 사용한 회사 계정 정보를 사용하여 [Windows Phone 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=268442) 에 가입합니다. 이 요청의 경우 코드 서명 인증서를 받기 전에 회사 관리자의 승인을 받아야 합니다.

2. **회사 Symantec 인증서 가져오기**<br>
  Symantec ID를 사용하여 [Symantec 웹 사이트](http://go.microsoft.com/fwlink/?LinkId=268441) 에서 인증서를 구입합니다. 인증서를 구입한 후 Windows Phone 개발 센터 계정에서 사용자가 지정한 회사 승인자에게 인증서 요청의 승인을 요청하는 전자 메일이 발송됩니다. Symantec 인증서 요구 사항에 대한 자세한 내용은 [Windows Phone에 Symantec 인증서가 필요한 이유는 무엇인가요?](https://technet.microsoft.com/en-us/library/dn764959.aspx#BKMK_Symantec)를 참조하세요. Windows 장치 등록 FAQ.

3.  **인증서 가져오기**<br>
    요청이 승인되면 인증서 가져오기에 대한 지침이 포함된 전자 메일을 받습니다. 전자 메일의 지침에 따라 인증서를 가져옵니다.

4.  **가져온 인증서 확인**<br>
    인증서를 제대로 가져왔는지 확인하려면 **인증서** 스냅인으로 이동하여 **인증서**를 마우스 오른쪽 단추로 클릭하고 **인증서 찾기**를 선택합니다. **포함** 필드에 “Symantec”을 입력하고 **지금 찾기**를 클릭합니다. 가져온 인증서가 결과에 표시됩니다.

    ![Symantec 인증서 찾기](./media/wit.gif)

5. **서명 인증서 내보내기**<br>
    인증서가 있는 것을 확인했으면 .pfx 파일을 내보내 회사 포털에 서명할 수 있습니다. **용도**가 "코드 서명"인 Symantec 인증서를 선택합니다. 코드 서명 인증서를 마우스 오른쪽 단추로 클릭하고 **내보내기**를 선택합니다.

    ![서명 인증서 내보내기](./media/wit-walk-cert2.gif)

    **인증서 내보내기 마법사**페이지에서 **예, 개인 키를 내보냅니다.** 를 클릭하고 **다음**을 클릭합니다. **개인 정보 교환 –PKCS #12(.PFX)** 를 선택하고 **가능하면 인증 경로에 있는 인증서 모두 포함**을 선택합니다. 마법사를 완료합니다. 자세한 내용은 [개인 키와 함께 인증서 내보내기](http://go.microsoft.com/fwlink/?LinkID=203031)를 참조하세요.

6.  **앱을 Intune에 업로드**<br>
    서명한 앱 파일 및 코드 서명 인증서를 업로드하여 최종 사용자가 앱을 사용할 수 있도록 합니다.

    1.  [Intune 관리 콘솔](http://manage.microsoft.com)에서 **관리** &gt; **Windows Phone**을 클릭합니다.

    2.  **서명된 앱 파일 업로드**를 클릭하고 Intune 관리자 ID로 로그인합니다.

    3.  내보낸 인증서(.pfx) 파일을 **코드 서명 인증서**에 추가하고 인증서의 암호를 만듭니다.

    4.  마법사를 완료합니다.

## <a name="example-download-sign-and-deploy-the-company-portal-app-for-windows-devices"></a>예: Windows 장치용 회사 포털 앱 다운로드, 서명 및 배포

회사 포털 앱을 Windows Phone 스토어에서 설치하지 않고 Intune을 사용해 Windows Phone 및 Windows 10 Mobile 장치를 비롯한 Windows 장치에 배포할 수 있습니다. 회사 포털 앱을 다운로드하고 인증서로 서명해야 합니다.  사용자가 회사 저장소를 사용하지 않으며 회사 포털을 Windows Phone 8.1 장치에 배포하려는 경우에만 필요합니다.


1.  **회사 포털 다운로드**

    Intune을 사용하여 회사 포털 앱을 배포하려면 다운로드 센터에서 [Windows Phone 8.1용 Microsoft Intune 회사 포털 앱](http://go.microsoft.com/fwlink/?LinkId=615799)을 다운로드하고 자동으로 압축 해제되는 파일(.exe)을 실행합니다. 이 파일에는 두 개의 파일이 들어 있습니다.

    -   CompanyPortal.appx – Windows Phone 8.1용 회사 포털 설치 앱

    -   WinPhoneCompanyPortal.ps1 – 회사 포털 앱 파일을 Windows Phone 8.1 장치에 배포할 수 있도록 서명하는 데 사용할 수 있는 PowerShell 스크립트

    또는 [비즈니스용 Windows 스토어](http://businessstore.microsoft.com/)에서 Windows Phone 8.1 회사 포털(오프라인 사용이 허가된 패키지) 또는 Windows 10 회사 포털(오프라인 사용이 허가된 패키지)을 다운로드할 수 있습니다. 회사 포털 앱과 함께 오프라인 라이선스 및 오프라인에서 사용하기 위해 다운로드한 적절한 패키지를 얻어야 합니다. 선택 영역의 Windows 8 및 Windows Phone 8 플랫폼 목록은 상응하는 8.1 플랫폼을 나타냅니다. Intune을 사용하여 이 작업을 수행하는 방법에 대한 자세한 내용은 [비즈니스용 Windows 스토어에서 구입한 앱 관리](manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune.md)를 참조하세요.

2.  **Windows Phone SDK 다운로드** Windows Phone SDK 8.0(http://go.microsoft.com/fwlink/?LinkId=615570)을 다운로드하고 이 SDK를 컴퓨터에 설치합니다. 이 SDK는 응용 프로그램 등록 토큰을 생성하는 데 필요합니다.

3.  **AETX 파일 생성** Windows Phone SDK 8.0의 일부인 AETGenerator.exe를 사용하여 Symantec PFX 에서 응용 프로그램 등록 토큰(.aetx) 파일을 생성합니다. AETX 파일을 생성하는 방법에 대한 지침은 [Windows Phone용 응용 프로그램 등록 토큰을 생성하는 방법](https://msdn.microsoft.com/library/windows/apps/jj735576.aspx)을 참조하세요.

4.  **Windows 8.1용 Windows SDK 다운로드** [Windows Phone SDK](http://go.microsoft.com/fwlink/?LinkId=613525)(http://go.microsoft.com/fwlink/?LinkId=613525)를 다운로드하여 설치합니다. 참고로 회사 포털 앱에 포함된 PowerShell 스크립트는 기본 설치 위치 `${env:ProgramFiles(x86)}\Windows Kits\8.1`을 사용합니다. 다른 위치에 설치하는 경우 cmdlet 매개 변수에 해당 위치를 포함해야 합니다.

5.  **PowerShell을 사용하여 앱에 코드 서명** 관리자로 로그인하고 Windows SDK, Symantec Enterprise 모바일 코드 서명 인증서가 설치된 호스트 컴퓨터에서 **Windows PowerShell**을 열어 Sign-WinPhoneCompanyPortal.ps1 파일을 찾아 스크립트를 실행합니다.

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

    -   `-InputAppx` –작은따옴표로 묶은 CompanyPortal.appx 파일에 대한 로컬 경로입니다. 예: 'C:\temp\CompanyPortal.appx'

    -   `-OutputAppx` – 작은따옴표로 묶은 서명된 회사 포털 앱에 대한 로컬 경로 및 파일 이름입니다. 예: 'C:\temp\CompanyPortalEnterpriseSigned.appx'

    -   `-PfxFilePath` – Symantec 인증서의 내보낸 PFX 파일에 대한 로컬 경로 및 파일 이름입니다. 예: 'C:\signing\cert.pfx'

    -   `-PfxPassword` – 작은따옴표로 묶은 PFX 파일에 서명하는 데 사용되는 암호입니다. 예: '1234'

    -   `-AetxPath` – 'EnterpriseId' 인수가 정의되지 않은 경우 엔터프라이즈 ID를 읽는 데 사용되는 .aetx 파일에 대한 로컬 경로입니다. 이 인수 또는 EnterpriseId를 제공해야 합니다. 예: 'C:\signing\cert.aetx'

    -   `-PublisherId` - 엔터프라이즈의 게시자 ID입니다. 없는 경우 Symantec Enterprise 모바일 코드 서명 인증서의 '제목' 필드를 사용합니다. 예: 'OID.0.9.2342.19200300.100.1.1=1000000001, CN="Test, Inc.", OU=Test 1'

    -   `-SdkPath` - Windows 8.1용 Windows SDK의 루트 폴더에 대한 경로입니다. 이 인수는 선택 사항이며 기본적으로 ${env:ProgramFiles(x86)}\Windows Kits\8.1입니다.

    -   `-EnterpriseId` - 엔터프라이즈 ID입니다. 이 인수 또는 'AetxPath'를 제공해야 합니다. 이 인수를 제공하지 않으면 AETX 파일에서 엔터프라이즈 ID를 읽습니다. 예: 1000000001

6.  Windows Phone 8.1 회사 포털(SSP.appx) 앱을 배포합니다. 지침에 대해서는 [Microsoft Intune에서 앱 배포](deploy-apps-in-microsoft-intune.md)를 참조하세요.

## <a name="how-to-renew-the-symantec-enterprise-code-signing-certificate"></a>Symantec 엔터프라이즈 코드 서명 인증서를 갱신하는 방법

Windows 및 Windows Phone 모바일 앱을 배포하는 데 사용되는 Symantec 인증서는 주기적으로 갱신해야 합니다.

1.  인증서가 만료되기 약 14일 전에 Symantec에서 보낸 갱신 전자 메일을 찾습니다. 이 전자 메일에 Symantec의 엔터프라이즈 인증서 갱신 관련 지침이 포함되어 있습니다.

    Symantec 인증서에 대한 자세한 내용을 확인하려면 [www.symantec.com](http://www.symantec.com) 을 방문하거나 1-877-438-8776 또는 1-650-426-3400로 전화 문의하세요.

2.  웹 사이트(예: [https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do](https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do))로 이동한 다음 인증서에 연결된 Symantec 게시자 ID 및 전자 메일 주소를 사용하여 로그인합니다. 이때 인증서를 다운로드하는 데 사용하려는 것과 같은 컴퓨터를 사용하여 갱신을 시작해야 합니다.

3.  갱신이 승인 및 결제되면 인증서를 다운로드합니다.

### <a name="how-to-install-the-updated-certificate-for-line-of-business-lob-apps"></a>LOB(기간 업무) 앱에 업데이트된 인증서를 설치하는 방법

1.  기간 업무 앱의 최신 버전에 서명합니다.

2.  [Intune 관리 콘솔](https://admin.manage.microsoft.com)(https://admin.manage.microsoft.com)을 열고 **관리** &gt; **모바일 장치 관리** &gt; **Windows Phone**으로 이동한 후에 **서명된 앱 업로드**를 클릭합니다.

3.  새로 서명된 회사 포털을 업로드합니다. 새로 서명된 SSP.xap와 Symantec에서 받은 새로운 .PFX 파일 또는 이러한 새 .PFX 파일로 생성한 응용 프로그램 등록 토큰이 필요합니다.

4.  업로드가 완료되면 **소프트웨어**  작업 영역에서 이전 회사 포털 버전을 제거합니다.

5.  새 인증서를 사용하여 모든 신규 및 업데이트된 엔터프라이즈 기간 업무 앱에 서명합니다. 기존 응용 프로그램에 다시 서명하고 다시 배포할 필요가 없습니다.



<!--HONumber=Dec16_HO2-->


