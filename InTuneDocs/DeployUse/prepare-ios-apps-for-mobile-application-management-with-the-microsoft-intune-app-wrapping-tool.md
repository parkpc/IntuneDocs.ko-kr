---
# required metadata

title: 앱 래핑 도구를 사용하여 관리하도록 iOS 앱 준비 | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 99ab0369-5115-4dc8-83ea-db7239b0de97

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Intune 앱 래핑 도구를 사용하여 모바일 응용 프로그램 관리를 위해 iOS 앱 준비
**iOS용 Microsoft Intune 앱 래핑 도구**를 사용하여 사내 iOS 앱의 동작을 수정하면 해당 앱 코드를 변경하지 않고도 앱 기능을 제한할 수 있습니다.

이 도구는 앱 주위에 '래퍼'를 만드는 Mac OS 명령줄 응용 프로그램입니다. 앱을 처리한 후에는 구성하는 [모바일 응용 프로그램 관리 정책](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md)을 사용하여 앱의 기능을 변경할 수 있습니다.

이 도구를 다운로드하려면 [iOS용 Microsoft Intune 앱 래핑 도구](http://www.microsoft.com/en-us/download/details.aspx?id=45218)를 참조하세요..

## 1단계 앱 래핑 도구 사용을 위한 필수 구성 요소 준비

|요구 사항|추가 정보|
|---------------|--------------------------------|
|지원되는 운영 체제 및 도구 집합|앱 래핑 도구는 Xcode 도구 집합 버전 5 이상이 설치된 OS X 10.8.5 이상의 Mac 컴퓨터에서 실행해야 합니다.|
|인증서 및 프로비저닝 프로필 서명|Apple 서명 인증서 및 프로비저닝 프로필이 있어야 합니다. [Apple 개발자 설명서](https://developer.apple.com/)를 참조하세요..|
|앱 래핑 도구를 사용하여 앱 처리|사용자의 회사나 ISV(Independent Software Vendor)에서 개발 및 서명한 앱이어야 합니다. 이 도구를 사용하여 Apple 스토어의 앱을 처리할 수는 없습니다. iOS 7.0 이상용으로 작성된 앱이어야 합니다. 또한 PIE(Position Independent Executable) 형식의 앱이어야 합니다. PIE 형식에 대한 자세한 내용은 Apple 개발자 설명서를 참조하세요. 마지막으로, 앱의 확장명이 **.app**, 또는 **.ipa** 형식이어야 합니다.|
|래핑 도구에서 처리할 수 없는 앱|암호화된 앱, 서명되지 않은 앱 및 확장된 파일 특성을 가진 앱입니다.|
|ADAL(Azure Active Directory 라이브러리)을 사용하는 앱|앱에서 ADAL을 사용하는 경우 앱은 ADAL 버전 1.0.2 이상을 포함하고 있어야 하며 개발자는 Intune 모바일 응용 프로그램 관리 리소스에 대한 액세스 권한을 앱에 부여해야 합니다.<br /><br />ADAL 사용 방법에 관한 자세한 내용은 이 문서의 [Azure Active Directory 라이브러리를 사용하는 앱에 대한 정보](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md#information-for-apps-that-use-the-azure-active-directory-library)를 참조하세요.|
|앱에 대한 자격 설정|앱을 래핑하려면 먼저 일반적으로 부여되는 권한 및 기능 이외에 앱에 추가적인 사용 권한 및 기능을 제공하는 자격을 설정해야 합니다. 지침은 [앱 자격 설정](#setting-app-entitlements)을 참조하세요.|

## 2단계 앱 래핑 도구 설치

1.  [Microsoft 다운로드 센터](https://www.microsoft.com/download/details.aspx?id=45218)의 **iOS용 Microsoft Intune 앱 래핑 도구** 페이지에서 앱 래핑 도구용 설치 파일을 Mac 컴퓨터에 다운로드합니다.

2.  Mac 컴퓨터에서 설치 파일 **Microsoft Intune App Wrapping Tool for iOS.dmg**를 두 번 클릭합니다..

3.  **동의** 를 선택하여 EULA(최종 사용자 사용권 계약)에 동의합니다. Mac 컴퓨터에서 설치 관리자가 탑재되어 표시됩니다.

4.  설치 관리자를 열고 표시된 파일을 Mac 컴퓨터의 새 폴더에 복사합니다. 이제 탑재된 설치 관리자 드라이브의 연결을 끊을 수 있습니다.

    이제 앱 래핑 도구를 실행할 수 있습니다.

## 3단계 앱 래핑 도구 실행

1.  Mac 컴퓨터에서 터미널 창을 열고 파일을 저장한 폴더로 이동합니다. 실행 파일은 패키지 내에 있으므로 다음과 같이 명령을 실행해야 합니다.
```
    ./IntuneMAMPackager.app/Contents/MacOS/IntuneMAMPackager –i /<path of input app>/<app filename> -o /<path to output folder>/<app filename> –p /<path to provisioning profile> –c <SHA1 hash of the certificate> -a <client ID of input app> -r <reply URI of input app> -v true
```
    > [!NOTE]
    > Some parameters are optional as shown in the table below.

    **Example:** The following example command runs the app wrapping tool on an app named **MyApp.ipa**. A provisioning profile and SHA-1 hash are specified. The processed app is created and stored in the **/users/myadmin/Documents** on the Mac computer.

    ```
    /users/myadmin/Downloads/IntuneMAMPackager.app/Contents/MacOS/IntuneMAMPackager -i /users/myadmin/Downloads/MyApp.ipa -o /users/myadmin/Documents/MyApp_Wrapped.ipa -p /users/myadmin/Downloads/My_Provisioning_Profile_.mobileprovision -c 12A3BC45D67EF8901A2B3CDEF4ABC5D6E7890FAB –a 20e1cd0d-268e-4308-9583-02ae97dd353e –r https://contoso/ -v true
    ```
    You can use the following command line properties with the app wrapping tool:

|속성|추가 정보|
  |------------|--------------------|
  |**-h**|앱 래핑 도구에 대해 사용 가능한 명령줄 속성을 표시합니다.|
  |**-i**|입력 앱의 경로와 파일 이름을 지정합니다.|
  |**-o**|처리된 앱을 저장할 경로를 지정합니다.|
  |**-p**|iOS 앱용 프로비저닝 프로필의 경로를 지정합니다.|
  |**-c**|서명 인증서의 SHA1 해시를 지정합니다.|
  |**-a**|앱이 Azure Active Directory 라이브러리를 사용하는 경우 GUID 형식의 입력 앱 클라이언트 ID입니다(선택 사항).|
  |**-r**|앱이 Azure Active Directory 라이브러리를 사용하는 경우 입력 앱의 리디렉션 URI입니다(선택 사항).|
  |**-v**|콘솔에 자세한 정보 표시 메시지를 출력합니다(선택 사항).|

2. 처리가 완료되면 **응용 프로그램이 래핑되었습니다.** 메시지가 표시됩니다.

    오류가 발생한 경우 도움이 필요하면 [오류 메시지](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md#error-messages)를 참조하세요.

3.  래핑된 앱은 이전에 지정한 출력 폴더에 저장됩니다. 이제 앱을 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]에 업로드하고 모바일 응용 프로그램 관리 정책에 연결할 수 있습니다.

    > [!IMPORTANT]
    > 앱은 새 앱으로 업로드해야 합니다. 래핑되지 않은 이전 버전의 앱을 업데이트할 수는 없습니다.

    이제 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] 그룹에 앱을 배포할 수 있으며, 지정한 앱 제한을 사용하여 장치에서 앱이 실행됩니다.

## 오류 메시지 및 로그 파일
앱 래핑 도구 관련 문제를 해결하려면 다음 정보를 사용하세요.

### 오류 메시지
앱 래핑 도구가 정상적으로 완료되지 않으면 다음 오류 메시지 중 하나가 표시됩니다.

|오류 메시지|추가 정보|
|-----------------|--------------------|
|올바른 iOS 프로비저닝 프로필을 지정해야 합니다.|프로비저닝 프로필이 유효하지 않을 수 있습니다. 장치에 대한 올바른 권한이 있으며 프로필이 올바른 대상(개발 또는 배포)을 지정하는지 확인하세요. 프로비저닝 프로필이 만료되었을 수도 있습니다.|
|올바른 입력 응용 프로그램 이름을 지정하세요.|지정한 입력 응용 프로그램 이름이 올바른지 확인합니다.|
|출력 응용 프로그램의 올바른 경로를 지정하세요.|지정한 출력 응용 프로그램의 경로가 있으며 올바른지 확인합니다.|
|올바른 입력 프로비저닝 프로필을 지정하세요.|올바른 프로비저닝 프로필 이름 및 확장명을 입력했는지 확인합니다. 프로비저닝 프로필에서 권한 부여가 누락되었거나 **–p** 명령줄 옵션을 포함하지 않았을 수 있습니다.|
|지정한 입력 응용 프로그램을 찾을 수 없습니다. 올바른 입력 응용 프로그램 이름 및 경로를 지정하세요.|입력 앱 경로가 유효하며 있는지 확인합니다. 입력 앱이 해당 위치에 있는지 확인합니다.|
|지정한 입력 프로비저닝 프로필 파일을 찾을 수 없습니다. 올바른 입력 프로비저닝 프로필 파일을 지정하세요.|입력 프로비저닝 파일의 경로가 올바르며 지정한 파일이 있는지 확인합니다.|
|지정한 출력 응용 프로그램 폴더를 찾을 수 없습니다. 출력 응용 프로그램의 올바른 경로를 지정하세요.|지정한 출력 경로가 유효하며 있는지 확인합니다.|
|출력 앱의 확장명이 .ipa가 아닙니다.|앱 래핑 도구에서는 확장명이 **.app** 및 **.ipa** 인 앱만 사용할 수 있습니다. 출력 파일의 확장명이 올바른지 확인합니다.|
|잘못된 서명 인증서가 지정되어 있습니다. 올바른 Apple 서명 인증서를 지정하세요.|Apple 개발자 포털에서 올바른 서명 인증서를 다운로드했는지 확인합니다. 인증서가 만료되었을 수도 있습니다. Apple 인증서 및 프로비저닝 프로필을 사용하여 Xcode 내에서 앱에 올바르게 서명할 수 있으면 해당 인증서와 프로필을 앱 래핑 도구에서 사용할 수 있습니다.|
|지정한 입력 응용 프로그램이 잘못되었습니다. 올바른 응용 프로그램을 지정하세요.|.app 또는 .ipa 파일로 컴파일된 올바른 iOS 응용 프로그램이 있는지 확인합니다.|
|지정한 입력 응용 프로그램이 암호화되어 있습니다. 암호화되지 않은 올바른 응용 프로그램을 지정하세요.|앱 래핑 도구에서는 암호화된 앱을 지원하지 않으므로 암호화되지 않은 앱을 지정해야 합니다.|
|지정한 입력 응용 프로그램이 PIE(Position Independent Executable) 형식이 아닙니다. PIE 형식의 올바른 응용 프로그램을 지정하세요.|PIE(Position Independent Executable) 앱은 실행 시 임의 메모리 주소에서 로드할 수 있으므로 보안상 유리합니다. 자세한 내용은 Apple 개발자 설명서를 참조하세요.|
|지정한 입력 앱은 이미 래핑되었습니다. 래핑되지 않은 올바른 응용 프로그램을 지정하세요.|도구에서 이미 처리된 앱은 처리할 수 없습니다. 앱을 다시 처리하려면 원래 앱 버전을 사용하여 도구를 다시 실행합니다.|
|지정한 입력 응용 프로그램이 서명되지 않았습니다. 서명된 올바른 응용 프로그램을 지정하세요.|앱 래핑 도구에서 처리할 앱은 서명되어져야 합니다. 래핑된 앱에 서명을 하는 방법은 개발자 설명서를 참조하세요.|
|지정한 입력 응용 프로그램은 .ipa 또는 .app 형식이어야 합니다.|확장명이 .ipa인 앱만 앱 래핑 도구에서 처리할 수 있습니다. 입력 파일의 확장명이 올바르고 .app 또는 .ipa 파일로 컴파일되었는지 확인합니다.|
|지정한 입력 앱은 이미 래핑되었으며 최신 정책 템플릿 버전을 사용합니다.|앱 래핑 도구는 기존에 래핑된 앱을 최신 정책 템플릿 버전을 사용하여 다시 래핑하지 않습니다.|
|지정된 Azure Active Directory 클라이언트 ID는 올바른 형식의 GUID가 아닙니다. 올바른 클라이언트 ID를 지정하세요|클라이언트 ID 매개 변수를 사용할 때는 올바른 클라이언트 ID를 GUID 형식으로 입력했는지 확인합니다.|
|지정된 Azure Active Directory 회신 URI는 올바른 형식의 URI가 아닙니다. 올바른 회신 URI를 지정하세요.|회신 URI 명령줄 속성을 사용할 때는 올바른 회신 URI를 입력했는지 확인합니다.|
|경고: SHA1 인증서 해시를 지정하지 않았습니다. 배포 전에 래핑된 응용 프로그램이 서명되어 있는지 확인하세요.|**–c** 명령줄 속성을 사용하여 올바른 SHA 해시를 지정했는지 확인합니다.|

### 앱 래핑 도구의 로그 파일
앱 래핑 도구를 사용하여 앱을 래핑하면 iOS 클라이언트 장치 콘솔에 작성되는 로그가 생성됩니다. 응용 프로그램에서 문제가 발생하여 앱 래핑 도구 관련 문제인지를 진단해야 하는 경우 이 정보가 유용합니다. 이 정보를 검색하려면 다음 단계를 수행합니다.

1.  앱을 실행하여 문제를 재현합니다.

2.  [배포된 iOS 앱 디버깅](https://developer.apple.com/library/ios/qa/qa1747/_index.html)과 관련한 Apple의 지침에 따라 콘솔 출력을 수집합니다..

3.  콘솔에 다음 스크립트를 입력하여 앱 제한 출력에 대해 저장된 로그를 필터링합니다.

    ```
    grep “IntuneAppRestrictions” <text file containing console output> > <required filtered log file name>
    ```
    필터링된 로그를 Microsoft에 제출할 수 있습니다.

    > [!NOTE]
    > 로그 파일에서 항목 '빌드 버전'은 Xcode의 빌드 버전을 나타냅니다.

    래핑된 앱은 앱 작동이 중단된 후 전자 메일을 통해 장치에서 로그를 직접 보내는 옵션도 제공합니다. 사용자는 개발자가 점검하여 필요한 경우 Microsoft로 전달할 수 있는 로그를 보낼 수 있습니다.

## Azure Active Directory 라이브러리를 사용하는 앱에 대한 정보
이 섹션의 정보는 ADAL(Azure Active Directory 라이브러리)을 사용하는 앱에만 적용됩니다. 앱이 해당 라이브러리를 사용하는지 확실치 않으면 앱의 개발자에게 문의하세요.

버전 1.0.2 이상의 ADAL이 통합되어 있어야 합니다.

ADAL을 사용하는 앱은 다음 조건을 충족해야 합니다.

-   1.0.2 이상의 ADAL 버전이 통합되어 있어야 합니다.

-   개발자는 [ADAL을 사용하는 앱에 대해 수행할 단계](#steps-to-follow-for-apps-that-use-adal)에 설명된 대로 Intune 모바일 응용 프로그램 관리 리소스에 대한 액세스 권한을 앱에 부여해야 합니다..

### 가져와야 하는 식별자 개요
앱의 두 고유 식별자를 가져오려면 Azure 관리 포털을 통해 ADAL을 사용하는 앱을 등록해야 합니다.

|식별자|추가 정보|기본값|
|--------------|--------------------|-----------------|
|**클라이언트 ID**|각 앱을 Azure Active Directory에 등록하면 고유 GUID 식별자가 생성됩니다.<br /><br />앱별 클라이언트 ID를 알고 있으면 이 값을 지정할 수 있습니다. 그렇지 않은 경우에는 기본값을 사용해야 합니다.|6c7e8096-f593-4d72-807f-a5f86dcc9c77|
|**리디렉션 URI**|인증 토큰이 해당 끝점으로만 반환되도록 개발자가 Azure Active Directory에 앱을 등록할 때 제공할 수 있는 URI 값입니다.<br /><br />리디렉션 URI는 앱 래핑 도구에 대한 선택적 매개 변수로 입력할 수 있습니다. 이 URI를 지정하지 않으면 기본 URI가 사용됩니다.|urn:ietf:wg:oauth:2.0:oob|


### ADAL을 사용하는 앱에 대해 수행할 절차

1.  [가져와야 하는 ID 개요](#overview-of-identifiers-you-need-to-get)를 검토하여 가져와야 하는 값을 식별합니다.

2.  다음을 수행하여 Azure Active Directory에서 모바일 응용 프로그램 관리 기능에 대한 액세스 구성합니다.

    1. Azure 관리 포털에서 기존 Azure Active Directory 계정에 로그인합니다.

    2.  Azure Active Directory에서 **기존 LOB 응용 프로그램 등록** 을 클릭합니다.

    3.  구성 섹션에서 **다른 응용 프로그램의 웹 API에 대한 액세스 구성**을 선택합니다..

    4.  **다른 응용 프로그램에 대한 사용 권한** 섹션의 첫 번째 드롭다운 목록에서 **Intune 모바일 응용 프로그램 관리**를 선택합니다..

        이제 앱 래핑 도구에서 앱의 클라이언트 ID를 사용할 수 있습니다. 앱의 클라이언트 ID는 [가져와야 하는 ID 개요](#overview-of-identifiers-you-need-to-get) 섹션에 설명된 대로 Azure Active Directory 관리 포털에서 찾을 수 있습니다.

3.  앱 래핑 도구에서 명령줄 속성으로서 **Client-ID**(속성 **–a** 사용) 및 **Redirect-URI** 값을 사용합니다. 이 값들이 없으면 기본값이 사용됩니다. 두 값을 모두 지정해야 하며, 그렇지 않으면 최종 사용자가 처리된 앱을 정상적으로 인증할 수 없습니다.

### 인증서, 프로비저닝 프로필 및 인증 요구 사항

|요구 사항|세부 정보|
|---------------|-----------|
|프로비저닝 프로필|**프로비저닝 프로필을 포함하기 전에 프로필이 올바른지 확인** - 앱 래핑 도구에서는 iOS 앱을 처리할 때 프로비저닝 프로필이 만료되었는지 확인하지 않습니다. 만료된 프로비저닝 프로필을 지정하면 앱 래핑 도구는 만료된 프로비저닝 프로필을 그대로 포함하며, iOS 장치에서 앱 설치가 실패할 때까지 문제가 있음을 알 수 없습니다.|
|인증서|**인증서를 지정하기 전에 해당 인증서가 올바른지 확인** - 도구에서는 iOS 앱을 처리할 때 인증서가 만료되었는지 확인하지 않습니다. 따라서 만료된 인증서의 해시를 제공하면 도구에서 앱을 처리하고 서명을 하기는 하지만 장치에 앱을 설치하지는 못합니다.<br /><br />**패키지된 응용 프로그램 서명용으로 제공되는 인증서와 일치하는 항목이 프로비저닝 프로필에 있는지 확인** - 이 도구는 래핑된 응용 프로그램에 서명하도록 제공된 인증서와 일치하는 항목이 프로비저닝 프로필에 있는지 확인하지 않습니다.|
|인증|암호화가 작동하려면 장치에서 핀을 설정해야 합니다. 사용자는 래핑된 응용 프로그램을 배포한 장치의 상태 표시줄을 터치할 때 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]에 다시 인증해야 합니다. 래핑된 응용 프로그램의 기본 정책은 *다시 시작할 때 인증*입니다. iOS는 앱을 종료했다가 다시 시작할 때 전화 통화 등의 외부 알림을 처리합니다.<br /><br />래핑된 앱의 경우 같은 게시자의 래핑된 앱에 처음 로그인하는 사용자가 캐시됩니다. 그 이후에는 해당 사용자만 앱에 액세스할 수 있습니다. 사용자를 다시 설정하려면 장치 등록을 취소했다가 다시 등록해야 합니다.|

### ADAL에 대한 문제 해결 및 기술 참고 사항

-   ADAL 리소스가 없으면 ADAL 동적 라이브러리가 도구에 포함됩니다. 도구는 루트 폴더에서 이름이 **ADALiOS.bundle** 인 ADAL 라이브러리를 검색합니다.

-   도구는 앱 내의 ADAL 바이너리(있는 경우)를 검색하지는 않습니다. 앱이 오래된 버전에 연결되어 있는 경우 인증 정책을 사용하도록 설정되어 있으면 로그인 중에 런타임 오류가 발생할 수 있습니다.

-   [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] 인증을 위해 AAD 토큰을 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] MAM 리소스 ID로 가져옵니다. 그러나 이 토큰은 토큰의 유효성을 검사하는 호출에 사용되지 않습니다. [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] 에서는 앱 액세스 확인을 위해 로그인한 사용자의 UPN만 읽습니다. 다른 서비스 호출에서도 AAD 토큰은 사용되지 않습니다.

-   인증 토큰은 공유 키 집합에 저장되므로 같은 게시자의 앱 간에 공유됩니다. 특정 앱을 격리하려면 해당 앱에 대해 다른 서명 인증서 및 프로비저닝 프로필을 사용해야 합니다.

-   클라이언트 응용 프로그램의 클라이언트 ID 및 리디렉션 URI를 제공하면 이중 로그인 시도가 차단됩니다. AAD 대시보드에서 게시된 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] MAM 리소스 ID에 액세스하려면 이 클라이언트 ID를 등록해야 합니다. 이렇게 하지 않으면 앱을 실행할 때 로그인이 실패합니다.

## 앱 자격 설정
앱을 래핑하기 전에 **자격**을 부여하여 앱이 일반적으로 수행할 수 있는 작업을 초과하는 추가적인 권한 및 기능을 제공할 수 있습니다.  **자격 파일**은 앱 내에서 특정 권한(예: 공유 키 집합에 대한 액세스 권한)을 지정하는 코드 서명 동안 사용됩니다. **기능**이라는 특정 앱 서비스는 앱 개발 동안 Xcode 내에서 사용하도록 설정됩니다. 이렇게 사용하도록 설정되면 기능이 자격 파일에 반영됩니다. 자격 및 기능에 대한 자세한 내용은 iOS 개발자 라이브러리의 [기능 추가](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html)를 참조하세요. 지원되는 전체 기능 목록이 필요하면 [지원되는 기능](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/SupportedCapabilities/SupportedCapabilities.html)을 참조하세요..

### IOS용 앱 래핑 도구에 지원되는 기능

|기능|설명|권장 지침|
|--------------|---------------|------------------------|
|앱 그룹|앱 그룹을 사용하여 여러 앱에서 공유 컨테이너에 액세스하도록 허용하고 앱들 간의 추가적인 프로세스 간 통신을 허용합니다.<br /><br />앱 그룹을 사용하도록 설정하려면 **기능** 창을 열고, **앱 그룹** 섹션에서 **ON** 스위치를 클릭합니다. 앱 그룹을 추가하거나 기존 앱 그룹을 선택할 수 있습니다.|앱 그룹을 사용할 때에는 역방향 DNS 표기법을 사용합니다.<br /><br />*group.com.companyName.AppGroup*|
|Background Modes(백그라운드 모드)|백그라운드 모드를 사용하면 iOS이 백그라운드에서 계속 실행될 수 있습니다.||
|데이터 보호|데이터 보호 기능을 사용하면 iOS 앱에 의해 디스크에 저장된 파일에 보안 수준이 추가됩니다. 데이터 보호 기능에서는 특정 장치에 있는 기본 제공 암호화 하드웨어를 사용하여 디스크에서 파일을 암호화된 형식으로 저장합니다. 데이터 보호를 사용하도록 앱을 프로비저닝해야 합니다.||
|앱에서 바로 구매|앱에서 바로 구매 기능에서는 스토어에 연결하여 사용자의 지불을 안전하게 처리할 수 있도록 하여 스토어를 앱에 바로 포함합니다. 앱에서 바로 구매 기능을 사용하여 향상된 기능이나 앱에서 사용할 수 있는 추가적인 콘텐츠에 대한 지불을 회수할 수 있습니다.||
|키 집합 공유|키 집합 공유 기능을 사용하면 자신의 앱이 팀에서 개발한 다른 앱과 키 집합에 있는 암호를 공유할 수 있습니다.|키 집합 공유 기능을 사용할 때에는 역방향 DNS 표기법을 사용합니다.<br /><br />*com.companyName.KeychainGroup*|
|Personal VPN(개인 VPN)|앱이 네트워크 확장 프레임워크를 사용하여 사용자 지정 시스템 VPN 구성을 만들고 제어할 수 있도록 하려면 개인 VPN을 사용합니다.||
|푸시 알림|APNs(Apple 푸시 알림 서비스)를 사용하면 포그라운드에서 실행되지 않고 있는 앱이 사용자에 대한 정보를 보유하고 있다고 사용자에게 알릴 수 있습니다.|푸시 알림이 작동하도록 하려면 앱별 프로비저닝 프로필을 사용해야 합니다.<br /><br />[Apple 개발자 설명서](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html)의 절차를 따릅니다..|
|Wireless Accessory Configuration(무선 액세서리 구성)|무선 액세서리 구성 기능을 사용하면 프로젝트에 외부 액세서리 프레임워크가 추가되고 앱이 MFi Wi-Fi 액세서리를 구성할 수 있게 됩니다.||

### 자격을 사용하도록 설정하는 절차

1.  앱에서 기능을 사용하도록 설정합니다.

    1.  Xcode에서 앱의 대상으로 이동하고 **기능** 창을 클릭합니다.

    2.  적절한 기능을 켭니다. 각 기능 및 올바른 값을 결정하는 방법에 대한 자세한 내용은 iOS 개발자 라이브러리의 [기능 추가](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html)를 참조하세요.

    3.  프로세스 중에 만든 ID를 확인합니다.

    4.  래핑할 앱을 빌드하고 서명합니다.

2.  프로비저닝 프로필에서 자격을 사용하도록 설정합니다.

    1.  Apple Developer Member Center에 로그인합니다.

    2.  앱용 프로비저닝 프로필을 만듭니다. 자세한 지침은 [iOS용 Intune 앱 래핑 도구에 대한 필수 구성 요소를 가져오는 방법](http://blogs.technet.com/b/microsoftintune/archive/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios.aspx)을 참조하세요..

    3.  프로비저닝 프로필에서 앱에 있는 것과 동일한 자격을 사용하도록 설정합니다. 앱을 개발하는 동안 지정한 것과 동일한 ID를 제공해야 합니다.

    4.  프로비저닝 프로필 마법사를 완료하고 파일을 다운로드합니다.

3.  모든 필수 구성 요소가 충족되었는지 확인한 다음 앱을 래핑합니다.

### 자격과 관련한 일반적인 오류 문제 해결
iOS용 앱 래핑 도구에 자격 오류가 표시되는 경우 다음의 문제 해결 절차를 수행해 보세요.

|문제|원인|해결 방법|
|---------|---------|--------------|
|입력 응용 프로그램에서 생성된 자격을 구문 분석하지 못했습니다.|앱 래핑 도구가 앱에서 추출된 자격 파일을 읽을 수 없습니다. 자격 파일의 형식이 잘못되었을 수 있습니다.|앱용 자격 파일을 검사합니다. 이를 수행하려면 아래 설명된 지침을 따르세요. 자격 파일을 검사할 때에는 잘못된 구문이 있는지 확인합니다. 파일이 XML 형식으로 되어있어야 합니다.|
|프로비저닝 프로필에 자격이 누락되었습니다(누락된 자격이 나열됨). 이러한 자격이 있는 프로비저닝 프로필로 앱을 다시 패키징합니다.|프로비저닝 프로필에서 사용할 수 있는 자격과 앱에서 사용할 수 있는 기능 간에 일치하지 않는 사항이 있습니다. 이 불일치는 특정 기능(즉, 앱 그룹, 키 집합 액세스 등)과 연결된 ID에도 적용됩니다.|일반적으로 앱과 동일한 기능을 사용하는 새 프로비저닝 프로필을 만들 수 있습니다. 프로필과 앱 간 ID가 일치하지 않으면 가능할 경우 앱 래핑 도구가 ID 대체하게 됩니다. 새 프로비저닝 프로필을 만든 후에도 이 오류가 여전히 발생하면 **-e** 매개 변수를 사용하여 앱에서 자격의 제거를 시도할 수 있습니다(아래 섹션 "-e 매개 변수를 사용하여 앱에서 자격 제거" 참조).|

### 서명된 앱의 기존 자격 찾기
서명된 앱 및 프로비저닝 프로필의 기존 자격을 확인하려면

1.  .ipa 파일을 찾고 확장명을 .zip으로 변경합니다.

2.  .zip 파일을 확장합니다. .app 번들에 포함된 페이로드 폴더가 생성됩니다.

3.  코드 서명 도구를 사용하여 다음과 같이 .app 번들에 대한 자격을 확인합니다.

    ```
    $ codesign -d --entitlements :- "Payload/YourApp.app"
    ```
    여기서 `YourApp.app`는 .app 번들의 실제 이름입니다.

4.  보안 도구를 사용하여 앱의 포함된 프로비저닝 프로필 자격을 확인합니다.

    ```
    $ security -D -i "Payload/YourApp.app/embedded.mobileprovision"
    ```
    여기서 `YourApp.app`는 .app 번들의 실제 이름입니다.

### –e 매개 변수를 사용하여 앱에서 자격 제거
이 명령은 자격 파일에 없는 앱에서 사용할 수 있는 기능을 모두 제거합니다. 앱에서 사용 중인 기능을 제거하면 앱이 중단될 수 있습니다. 누락된 기능을 제거할 수 있는 위치의 예로 기본적으로 모든 기능을 갖춘 공급업체에서 만든 앱이 있는 경우입니다.

```
./IntuneMAMPackager.app/Contents/MacOS/IntuneMAMPackager –i /<path of input app>/<app filename> -o /<path to output folder>/<app filename> –p /<path to provisioning profile> –c <SHA1 hash of the certificate> -e
```

## 앱 래핑 도구의 보안 및 개인 정보
앱 래핑 도구를 사용할 때는 다음의 보안 및 개인 정보 관련 모범 사례를 사용합니다.

-   지정하는 서명 인증서, 프로비저닝 프로필, LOB(기간 업무) 앱은 앱 래핑 도구를 실행하는 데 사용하는 것과 같은 Mac 컴퓨터에 있어야 합니다. 파일이 UNC 경로에 있으면 Mac 컴퓨터에서 해당 파일에 액세스할 수 있는지 확인합니다. IPsec 또는 SMB 서명을 통해 경로를 보호해야 합니다.

    [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] 콘솔로 가져온 래핑된 응용 프로그램은 도구를 실행하는 동일한 컴퓨터에 있어야 합니다. 파일이 UNC 경로에 있으면 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] 콘솔을 실행하는 컴퓨터에서 해당 파일에 액세스할 수 있는지 확인합니다. IPsec 또는 SMB 서명을 통해 경로를 보호해야 합니다.

-   Microsoft 다운로드 센터 사이트에서 앱 래핑 도구를 다운로드하는 환경은 IPsec 또는 SMB 서명을 통해 보호해야 합니다.

-   공격을 차단하려면 신뢰할 수 있는 출처의 앱만 처리해야 합니다.

-   앱 래핑 도구에 지정된 출력 폴더(특히 원격 폴더)를 보호해야 합니다.

-   파일 업로드 대화 상자를 포함하는 iOS 앱에서는 사용자가 앱에 적용된 잘라내기, 복사, 붙여넣기 제한을 우회할 수 있습니다. 예를 들어 사용자가 파일 업로드 대화 상자를 사용하여 앱 데이터의 스크린샷을 업로드할 수 있습니다.

-   사용자가 래핑된 앱 내에서 장치의 문서 폴더를 모니터링할 때는 **.msftintuneapplauncher**라는 폴더가 표시될 수 있습니다. 이 폴더를 변경하거나 삭제하면 제한된 앱이 정상적으로 작동하지 않을 수 있습니다.

### 참고 항목
- [Microsoft Intune으로 모바일 응용 프로그램 관리용 앱을 준비하는 방법 결정](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md)</br>
- [Microsoft Intune 정책을 사용하여 장치의 설정 및 기능 관리](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)</br>
- [SDK를 사용하여 모바일 응용 프로그램 관리에 앱을 사용하도록 설정](use-the-sdk-to-enable-apps-for-mobile-application-management.md)


<!--HONumber=May16_HO1-->


