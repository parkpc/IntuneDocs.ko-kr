<<<<<<< HEAD
---
title: "장치 등록 문제 해결| Microsoft Intune"
description: "장치 등록 문제 해결을 위한 제안 사항"
keywords: 
author: nathbarn
manager: angrobe
ms.date: 08/02/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6982ba0e-90ff-4fc4-9594-55797e504b62
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c880bd9dfb998355a18e78af898a96d4cee393f7
ms.openlocfilehash: d8d64fcdd783401fd41415702d5ff4ae18215cca

||||||| merged common ancestors
---
title: "장치 등록 문제 해결| Microsoft Intune"
description: "장치 등록 문제 해결을 위한 제안 사항"
keywords: 
author: nathbarn
manager: angrobe
ms.date: 08/02/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6982ba0e-90ff-4fc4-9594-55797e504b62
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 7b16c19c95384655e170c199597dd6bd31afb90d
ms.openlocfilehash: 226376601fdd381839ca389fd012e4bc462abfd5

=======
---
title: "장치 등록 문제 해결| Microsoft Intune"
description: "장치 등록 문제 해결을 위한 제안 사항"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/02/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6982ba0e-90ff-4fc4-9594-55797e504b62
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c880bd9dfb998355a18e78af898a96d4cee393f7
ms.openlocfilehash: d8d64fcdd783401fd41415702d5ff4ae18215cca

>>>>>>> 359d4f486355df1be118d8fdb698694ae632df85

---

# Intune에서 장치 등록 문제 해결

이 항목에서는 장치 등록 문제 해결을 위한 제안 사항을 제공합니다. 이 정보로 문제가 해결되지 않는 경우 [Microsoft Intune에 대한 지원을 받는 방법](how-to-get-support-for-microsoft-intune.md)을 참조하여 도움을 얻을 수 있는 다른 방법을 찾아보세요.


## 초기 문제 해결 단계

문제 해결을 시작하기 전에 등록이 설정되도록 Intune을 올바르게 구성했는지 확인하세요. 다음에서 이러한 구성 요구 사항에 대해 자세히 읽어볼 수 있습니다.

-   [Microsoft Intune에 장치를 등록하도록 준비](/intune/deploy-use/gprerequisites-for-enrollment.md)
-   [iOS 및 Mac 관리 설정](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune)
-   [Microsoft Intune을 사용한 Windows Phone 및 Windows 10 Mobile 관리 설정](/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune)
-   [Windows 장치 관리 설정](/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune)


관리되는 장치 사용자는 여러분이 검토할 등록 및 진단 로그를 수집할 수 있습니다. 로그 수집에 대한 지침은 다음과 같이 제공됩니다.

- [USB 케이블을 사용하여 IT 관리자에게 Android 진단 데이터 로그 보내기](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-a-usb-cable-android)
- [메일을 사용하여 IT 관리자에게 Android 진단 데이터 로그 보내기](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-email-android)
- [IT 관리자에게 Android 등록 오류 보내기](/intune/enduser/send-enrollment-errors-to-your-it-administrator-android)
- [IT 관리자에게 iOS 등록 오류 보내기](/intune/enduser/send-errors-to-your-it-admin-ios)



## 일반적인 등록 문제
이러한 문제는 모든 장치 플랫폼에서 발생할 수 있습니다.

### 장치 최대값 도달
**문제:** iOS 장치에서 발생하는 **회사 포털을 일시적으로 사용할 수 없음** 오류와 같은 오류가 등록하는 동안 사용자에게 표시되고, Configuration Manager의 DMPdownloader.log에 **DeviceCapReached**라는 오류가 포함됩니다.

**해결 방법:** 기본적으로 사용자는 장치를 6개 이상 등록할 수 없습니다.

#### 등록된 장치 수와 및 허용된 장치 수 확인

1.  Intune 관리 포털에서 사용자에게 5개 이하의 장치가 할당되어 있는지 확인합니다.

2.  관리\모바일 장치 관리자\등록 규칙의 Intune 관리 포털에서 장치 등록 제한이 5로 설정되어 있는지 확인합니다.

모바일 장치 사용자는 다음 URL에서 장치를 삭제할 수 있습니다. [https://byodtestservice.azurewebsites.net/](https://byodtestservice.azurewebsites.net/).

관리자는 Azure Active Directory 포털에서 장치를 삭제할 수 있습니다.

#### Azure Active Directory 포털에서 장치를 삭제하려면

1.  [http://aka.ms/accessaad](http://aka.ms/accessaad)로 이동하거나 [https://portal.office.com](https://portal.office.com)에서 **관리자** &gt; **Azure AD**를 선택합니다.

2.  페이지의 왼쪽에 있는 링크를 사용하여 조직 ID로 로그인합니다.

3.  조직 ID가 없다면 Azure 구독을 만듭니다. 유료 계정이 있는 경우 신용 카드나 결제가 필요하지 않습니다(**Register your free Azure Active Directory(무료 Azure Active Directory 등록)** 구독 링크 선택).

4.  **Active Directory** 를 선택한 다음, 조직을 선택합니다.

5.  **사용자** 탭을 선택합니다.

6.  삭제하려는 장치의 사용자를 선택합니다.

7.  **장치**를 선택합니다.

8.  더 이상 사용 중이 아닌 장치나 정의가 부정확한 장치 등 장치를 적절하게 제거합니다.

> [!NOTE]

> [Microsoft Intune에서 장치 등록 관리자를 사용하여 회사 소유 장치 등록](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)에 설명된 대로 장치 등록 관리자를 사용하여 장치 등록 최대값에 도달하는 것을 방지할 수 있습니다.
>
> 장치 등록 관리자 그룹에 추가된 사용자 계정은 해당 특정 사용자 로그인에 대해 조건부 액세스 정책이 적용되는 경우 등록을 완료할 수 없습니다.

### 회사 포털을 일시적으로 사용할 수 없음
**문제:** 장치에서 **회사 포털을 일시적으로 사용할 수 없음** 오류가 사용자에게 표시됩니다.

#### 회사 포털을 일시적으로 사용할 수 없음 오류 문제 해결

1.  장치에서 Intune 회사 포털 앱을 제거합니다.

2.  장치에서 브라우저를 열고, [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com)으로 이동한 다음, 사용자 로그인을 시도합니다.

3.  사용자가 로그인하지 못하면 사용자가 다른 네트워크를 사용하도록 해보세요.

4.  이것이 하면 사용자의 자격 증명이 Azure Active Directory와 올바로 동기화했는지 확인합니다.

5.  사용자가 성공적으로 로그인하면 iOS 장치에 Intune 회사 포털 앱을 설치하고 등록하라는 메시지가 나타납니다. Android 장치에서는 Intune 회사 포털 앱을 수동으로 설치해야 합니다. 그 다음에 다시 등록할 수 있습니다.

### MDM 기관이 정의되지 않았습니다
**문제:** 사용자에게 **MDM 기관이 정의되지 않았습니다.** 오류가 표시됩니다.

#### MDM 기관이 정의되지 않았습니다 오류 문제 해결

1.  MDM 기관이 사용 중인 Intune 서비스 버전, 즉 Intune, O365 MDM 또는 System Center Configuration Manager with Intune에 대해 적절히 설정되었는지 확인합니다. Intune의 경우, MDM 기관은 **관리** &gt; **모바일 장치 관리**에 설정되어 있습니다. Intune의 Configuration Manager의 경우, Intune 커넥터를 구성할 때 설정하고, O365에서는 **모바일 장치** 설정입니다.

    > [!NOTE]
    > MDM 기관을 설정한 후에는 [Microsoft Intune에 대한 지원을 받는 방법](how-to-get-support-for-microsoft-intune.md)의 설명에 따라 지원 팀에 연락해야만 변경할 수 있습니다.

2.  해당 UPN이 계정 포털에서 Active Directory 정보와 일치하는지 확인하여 사용자의 자격 증명이 Azure Active Directory와 올바른 동기화했는지 확인합니다.
    UPN은 Active Directory 정보와 일치하지 않으면

    1.  로컬 서버에서 DirSync를 해제합니다.

    2.  일치하지 않는 사용자를 **Intune 계정 포털** 사용자 목록에서 삭제합니다.

    3.  Azure 서비스에서 잘못된 데이터를 제거할 수 있도록 1시간 가량 기다립니다.

    4.  DirSync를 다시 설정하고 이제 사용자가 제대로 동기화되었는지 확인합니다.

3.  System Center Configuration Manager with Intune을 사용하는 상황에서는 사용자에게 유효한 클라우드 사용자 ID가 있는지 확인합니다.

    1.  SQL Management Studio를 엽니다.

    2.  적절한 DB에 연결합니다.

    3.  데이터베이스 폴더를 열고 **CM_DBName** 폴더를 찾아 엽니다. 여기서 DBName은 고객 데이터베이스의 이름입니다.

    4.  맨 위에서 **새 쿼리**를 클릭하고 다음 쿼리를 실행합니다.

        -   모든 사용자를 보려면: `select * from [CM_ DBName].[dbo].[User_DISC]`

        -   특정 사용자를 보려면 다음 쿼리를 사용합니다. 여기서 %testuser1%은 조회하려는 사용자에 대한 username@domain.com을 나타냅니다. `select * from [CM_ DBName].[dbo].[User_DISC] where User_Principal_Name0 like '%testuser1%'`

        쿼리를 작성한 후 **!Execute(!실행)**를 선택합니다.
        결과가 반환되면 클라우드 사용자 ID를 찾습니다.  ID를 찾을 수 없으면 Intune을 사용할 라이선스가 없는 것입니다.

### 회사 이름에 특수 문자가 포함되어 있으면 정책을 만들거나 장치를 등록할 수 없습니다.
**문제:** 정책을 만들거나 장치를 등록할 수 없습니다.

**해결 방법:** [Office 365 관리 센터](https://portal.office.com/)에서, 회사 이름의 특수 문자를 제거하고 회사 정보를 저장합니다.

### 확인된 도메인이 여럿이면 로그인하거나 장치를 등록할 수 없습니다.
**문제:** ADFS에 두 번째 확인된 도메인을 추가하는 경우, UPN(사용자 계정 이름) 접미사가 두 번째 도메인인 사용자가 포털에 로그인하거나 장치를 등록할 수 없습니다.


**해결 방법:** AD FS 2.0을 통해 SSO(Single Sign-On)를 활용하며, 조직 내에 사용자 UPN 접미사에 대한 최상위 도메인이 여럿인(예: @contoso.com 또는 @fabrikam.com) Microsoft Office 365 고객은, 각 접미사에 대해 AD FS 2.0 페더레이션 서비스를 개별적으로 배포해야 합니다.  추가적인 AD FS 2.0 서버를 필요로 하지 않고 AD FS 서버가 이 시나리오를 지원할 수 있도록 하는, **SupportMultipleDomain** 스위치와 함께 작동하는 [AD FS 2.0 롤업](http://support.microsoft.com/kb/2607496)이 있습니다. 자세한 정보는 [이 블로그](https://blogs.technet.microsoft.com/abizerh/2013/02/05/supportmultipledomain-switch-when-managing-sso-to-office-365/)를 참조하세요.


## Android 문제
### 프로필 설치 실패
**문제:** Android 장치에서 **프로필 설치 실패** 오류가 사용자에게 표시됩니다.

### 실패한 프로필 설치에 대한 문제 해결 절차

1.  사용 중인 Intune 서비스 버전에 적절한 라이선스를 사용자에게 할당했는지 확인합니다.

2.  장치가 아직 다른 MDM 공급자에게 등록하지 않았는지 또는 아직 관리 프로필을 설치하지 않았는지 확인합니다.

4.  Android용 Chrome이 기본 브라우저이고 쿠키가 사용할 수 있도록 설정되어 있는지 확인합니다.

### Android 인증서 문제

**문제**: 장치에서 다음과 같은 메시지가 표시됩니다. *필요한 인증서가 장치에 없으므로 로그인할 수 없습니다.*

**해결 방법**:

- [다음 지침](/intune/enduser/your-device-is-missing-a-required-certificate-android#your-device-is-missing-a-certificate-required-by-your-it-administrator)을 수행하여 누락된 인증서를 검색할 수 있습니다.
- 인증서를 검색할 수 없는 경우 ADFS 서버에서 중간 인증서가 누락된 것일 수 있습니다. 중간 인증서는 Android에서 서버를 신뢰하는 데 필요합니다.

다음과 같이 ADFS 서버 또는 프록시의 중간 저장소에 인증서를 가져올 수 있습니다.

1.  ADFS 서버에서 **Microsoft Management Console**을 시작하고 **컴퓨터 계정**에 대한 인증서 스냅인을 추가합니다.
5.  ADFS 서비스가 사용하는 인증서를 찾은 후 해당 부모 인증서를 확인합니다.
6.  부모 인증서를 복사한 후 **컴퓨터\중간 인증 기관 \인증서** 아래에 붙여넣습니다.
7.  ADFS, ADFS 암호 해독 및 ADFS 서명 인증서를 복사하고 ADFS 서비스에 대한 개인 저장소에 붙여넣습니다.
8.  ADFS 서버를 다시 시작합니다.

이제 사용자는 Android 장치에서 회사 포털에 로그인할 수 있습니다.



## iOS 문제
### 프로필 설치 실패
**문제:** iOS 장치에서 **프로필 설치 실패** 오류가 사용자에게 표시됩니다.

### 실패한 프로필 설치에 대한 문제 해결 절차

1.  사용 중인 Intune 서비스 버전에 적절한 라이선스를 사용자에게 할당했는지 확인합니다.

2.  장치가 아직 다른 MDM 공급자에게 등록하지 않았는지 또는 아직 관리 프로필을 설치하지 않았는지 확인합니다.

3.  [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com)으로 이동하고 메시지가 표시되면 프로필을 설치해 봅니다.

4.  iOS용 Safari가 기본 브라우저이고 쿠키가 사용할 수 있도록 설정되어 있는지 확인합니다.

### Intune에서 System Center Configuration Manager를 사용하면, 등록된 iOS 장치가 콘솔에 표시되지 않습니다.
**문제:** 사용자가 iOS 장치를 등록하지만 Configuration Manager 관리 콘솔에 나타나지 않습니다. 장치가 등록되었다는 것을 나타내지 않습니다. 가능한 원인:

- Intune 커넥터를 하나의 계정에 등록한 다음 또 다른 계정에 등록했을 수 있습니다.
- 하나의 계정으로 MDM 인증서를 다운로드하고 다른 계정에서 사용했을 수 있습니다.


**해결 방법:** 다음 단계를 수행합니다.

1. Windows Intune 커넥터 내에서 iOS를 비활성화합니다.
    1. Intune 구독을 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.
    1. "iOS" 탭에서 "iOS 등록을 사용하도록 설정합니다." 선택을 해제합니다.



1. SQL로, CAS DB에서 다음 단계를 실행합니다.

    1. update SC_ClientComponent_Property set Value2 = '' where Name like '%APNS%'
    1. delete from MDMPolicy where PolicyType = 7
    1. delete from MDMPolicyAssignment where PolicyType = 7
    1. update SC_ClientComponent_Property set Value2 = '' where Name like '%APNS%'
    1. delete from MDMPolicy where PolicyType = 11
    1. delete from MDMPolicyAssignment where PolicyType = 11
    1. DELETE Drs_Signals
1. SMS Executive 서비스를 다시 시작하거나 CM 서버를 다시 시작합니다.



1. 새 APN 인증서를 가져와서 업로드합니다. Configuration Manager 왼쪽 창에서 Intune 구독을 마우스 오른쪽 단추로 클릭합니다. **APNs 인증서 요청 만들기**를 선택하고 지침에 따릅니다.
## System Center Configuration Manager with Intune 사용 시 문제
### 모바일 장치가 사라집니다.
**문제:** 모바일 장치를 Configuration Manager에 성공적으로 등록한 후 모바일 장치가 모바일 장치 컬렉션에서 사라집니다. 하지만 장치에는 여전히 관리 프로필이 있고 CSS 게이트웨이에는 이 장치가 나열됩니다.

**해결 방법:** 이런 일은 도메인에 가입되지 않은 장치를 제거하는 사용자 지정 프로세스가 있거나 사용자가 장치를 가입에서 더 이상 사용하지 않으면 발생할 수 있습니다. 어느 프로세스나 사용자 계정이 Configuration Manager 콘솔에서 장치를 제거했는지 확인하려면 다음 절차를 수행하세요.

#### 장치가 제거된 방법 확인

1.  Configuration Manager 관리자 콘솔에서 **모니터링** &gt; **시스템 상태** &gt; **상태 메시지 쿼리**를 선택합니다.

2.  **Collection Member Resources Manually Deleted**를 마우스 오른쪽 단추로 클릭하고 **메시지 표시**를 선택합니다.

3.  적절한 시간/날짜 또는 지난 12시간을 선택합니다.

4.  문제의 장치를 찾아 장치가 제거된 방법을 확인합니다. 다음 예제에서는 SCCMInstall 계정이 알 수 없는 응용 프로그램을 통해 장치를 삭제했음을 보여 줍니다.

    ![장치 삭제 진단 스크린샷](./media/CM_With_Intune_Unknown_App_Deleted_Device.jpg)

5.  Configuration Manager에 예약된 작업, 스크립트, 또는 도메인이 아닌, 모바일 또는 관련 장치를 자동으로 제거할 수 있는 기타 프로세스가 없는지 확인합니다.




### 기타 iOS 등록 오류
iOS 등록 오류의 목록은 장치-사용자 설명서의 [Intune에서 장치를 등록하는 동안 오류가 발생하는 경우](/intune/enduser/using-your-ios-or-mac-os-x-device-with-intune)에서 제공됩니다.

## PC 문제

### 컴퓨터가 이미 등록되었습니다. - 오류: hr 0x8007064c
**문제:** **컴퓨터가 이미 등록되었습니다.**라는 오류와 함께 등록에 실패합니다. 등록 로그에 **hr 0x8007064c** 오류가 표시됩니다.

컴퓨터가 이전에 등록되었거나, 등록된 컴퓨터의 복제 이미지를 사용하기 때문일 수 있습니다. 이전 계정의 계정 인증서가 컴퓨터에 아직 존재합니다.



**해결 방법:**

1. **시작** 메뉴에서 **실행** -> **MMC**로 이동합니다.
1. **파일** -> **스냅인 추가/제거**로 이동합니다.
1. **인증서**를 두 번 클릭하고 **컴퓨터 계정**, **다음**을 선택한 후 **로컬 컴퓨터**를 선택합니다.
1. **인증서(로컬 컴퓨터)**를 두 번 클릭하고 **개인/인증서**를 선택합니다.
1. Sc_Online_Issuing에서 발급한 Intune 인증서를 찾아서 있으면 삭제합니다.
1. 아래 레지스트리가 있으면 **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\OnlineManagement regkey** 및 모든 하위 키를 삭제합니다.
1. 재등록을 시도합니다.
1. 여전히 컴퓨터를 등록할 수 없는 경우에는 **KEY_CLASSES_ROOT\Installer\Products\6985F0077D3EEB44AB6849B5D7913E95** 키를 찾아서 있으면 삭제합니다.
1. 재등록을 시도합니다.

    > [!IMPORTANT]
    > 이 섹션, 방법, 또는 작업에는 레지스트리를 수정하는 방법이 포함됩니다. 하지만, 레지스트리를 잘못 수정하면 심각한 문제가 발생할 수 있습니다. 따라서, 단계를 신중하게 따라야 합니다. 추가적인 보호를 위해, 수정하기 전에 레지스트리를 백업하세요. 그러면 문제가 발생했을 때 레지스트리를 복원할 수 있습니다.
    > 레지스트리를 백업하고 복원하는 방법에 대한 자세한 내용은 [How to back up and restore the registry in Windows](https://support.microsoft.com/en-us/kb/322756)(Windows에서 레지스트리를 백업하고 복원하는 방법)을 참조하세요.

## 일반적인 등록 오류 코드

|오류 코드|가능한 문제|권장되는 해결 방법|
|--------------|--------------------|----------------------------------------|
|0x80CF0437 |클라이언트 컴퓨터의 시계가 올바른 시간으로 설정되어 있지 않습니다.|클라이언트 컴퓨터의 시계 및 표준 시간대가 올바른 시간 및 표준 시간대로 설정되어 있는지 확인합니다.|
|0x80240438, 0x80CF0438, 0x80CF402C|Intune 서비스에 연결할 수 없습니다. 클라이언트 프록시 설정을 확인합니다.|클라이언트 컴퓨터의 프록시 구성을 Intune에서 지원하는지 그리고 클라이언트 컴퓨터가 인터넷에 연결되어 있는지 확인합니다.|
|0x80240438, 0x80CF0438|Internet Explorer 및 로컬 시스템의 프록시 설정이 구성되어 있지 않습니다.|Intune 서비스에 연결할 수 없습니다. 클라이언트 프록시 설정을 확인하고 클라이언트 컴퓨터의 프록시 구성이 Intune에서 지원되는 지와 클라이언트 컴퓨터에서 인터넷에 연결할 수 있는지 확인하세요.|
|0x80043001, 0x80CF3001, 0x80043004, 0x80CF3004|등록 패키지가 오래되었습니다.|관리 작업 영역에서 최신 클라이언트 소프트웨어 패키지를 다운로드하여 설치합니다.|
|0x80043002, 0x80CF3002|계정이 유지 관리 모드에 있습니다.|계정이 유지 관리 모드에 있는 경우 새 클라이언트 컴퓨터를 등록할 수 없습니다. 계정 설정을 보려면 자신의 계정으로 로그인합니다.|
|0x80043003, 0x80CF3003|계정이 삭제되었습니다.|Intune에 대한 계정과 구독이 계속 활성 상태인지 확인하십시오. 계정 설정을 보려면 자신의 계정으로 로그인합니다.|
|0x80043005, 0x80CF3005|클라이언트 컴퓨터가 사용 중지되었습니다.|몇 시간 기다렸다가 이전 버전의 클라이언트 소프트웨어를 컴퓨터에서 제거한 다음 클라이언트 소프트웨어를 다시 설치해 봅니다.|
|0x80043006, 0x80CF3006|계정에 허용되는 최대 사용자 수에 도달했습니다.|서비스에 클라이언트 컴퓨터를 더 등록하려면 조직에서 추가 사용자 수를 구매해야 합니다.|
|0x80043007, 0x80CF3007|설치 관리자 프로그램과 같은 폴더에서 인증서 파일을 찾을 수 없습니다.|모든 파일을 추출한 후에 설치를 시작합니다. 추출된 파일의 이름이나 위치를 바꾸지 마십시오. 모든 파일은 같은 폴더에 있어야 합니다. 그렇지 않으면 설치할 수 없습니다.|
|0x8024D015, 0x00240005, 0x80070BC2, 0x80070BC9, 0x80CFD015|클라이언트 컴퓨터를 다시 시작하는 작업이 보류되어 소프트웨어를 설치할 수 없습니다.|컴퓨터를 다시 시작한 다음 클라이언트 소프트웨어를 다시 설치해 봅니다.|
|0x80070032|클라이언트 컴퓨터에 클라이언트 소프트웨어를 설치하기 위한 필수 구성 요소가 하나 이상 없습니다.|클라이언트 컴퓨터에 필수 업데이트가 모두 설치되었는지 확인한 다음 클라이언트 소프트웨어를 다시 설치해 봅니다.|
|0x80043008, 0x80CF3008|Microsoft Online Management Updates 서비스를 시작하지 못했습니다.|[Microsoft Intune에 대한 지원을 받는 방법](how-to-get-support-for-microsoft-intune.md)의 설명에 따라 Microsoft 지원에 문의합니다.|
|0x80043009, 0x80CF3009|클라이언트 컴퓨터가 이미 서비스에 등록되어 있습니다.|클라이언트 컴퓨터를 서비스에 다시 등록하기 전에 사용 중지해야 합니다.|
|0x8004300B, 0x80CF300B|클라이언트를 실행 중인 Windows 버전이 지원되지 않으므로 클라이언트 소프트웨어 설치 패키지를 실행할 수 없습니다.|Intune에서 클라이언트 컴퓨터에서 실행 중인 Windows 버전을 지원하지 않습니다.|
|0xAB2|Windows Installer에서 사용자 지정 작업에 대한 VBScript 런타임에 액세스할 수 없습니다.|이 오류는 DLL(동적 연결 라이브러리)에 기반한 사용자 지정 작업으로 인해 발생합니다. DLL 문제를 해결하려면 [Microsoft Support KB198038: Useful Tools for Package and Deployment Issues(Microsoft 지원 기술 자료 198038: 패키지 및 배포 문제에 유용한 도구)](https://support.microsoft.com/en-us/kb/198038)에 설명된 도구를 사용해야 할 수 있습니다.|
|0x80cf0440|서비스 끝점에 대한 연결이 종료되었습니다.|평가판 또는 유료 계정 일시 중단되었습니다. 새 평가판 또는 유료 계정을 만들고 다시 등록합니다.|




### 다음 단계
문제 해결 정보가 도움이 되지 않는 경우 [Microsoft Intune에 대한 지원을 받는 방법](how-to-get-support-for-microsoft-intune.md)의 설명에 따라 Microsoft 지원에 문의하세요.


<<<<<<< HEAD
||||||| merged common ancestors
<!--HONumber=Aug16_HO1-->
=======
<!--HONumber=Sep16_HO4-->
>>>>>>> 359d4f486355df1be118d8fdb698694ae632df85

<!--HONumber=Sep16_HO4-->


