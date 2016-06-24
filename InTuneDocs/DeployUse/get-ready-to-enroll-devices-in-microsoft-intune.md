---
# required metadata

title: 장치를 등록하도록 준비 | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 44fd4af0-f9b0-493a-b590-7825139d9d40

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune에 장치를 등록하도록 준비
Intune으로 직원이 모바일 장치([Android](set-up-android-management-with-microsoft-intune.md), [iOS 및 Mac](set-up-ios-and-mac-management-with-microsoft-intune.md), [Windows Phone](set-up-windows-phone-management-with-microsoft-intune.md) 및 [Windows PC](set-up-windows-device-management-with-microsoft-intune.md) 포함)를 등록할 수 있도록 하려면 장치 등록을 활성화해야 합니다. 등록을 허용하려면 모바일 장치 관리 기관을 설정하고 Intune 회사 포털을 구성하고 라이선스를 할당하고 장치 플랫폼에 대한 등록을 활성화해야 합니다.

## 모바일 장치 관리 기관 설정
MDM 기관은 일련의 장치를 관리할 권한을 가진 관리 서비스를 정의합니다. MDM 기관에 대한 옵션에는 Intune 자체 및 Intune을 사용하는 Configuration Manager가 포함됩니다. Configuration Manager를 관리 기관으로 설정한 경우 모바일 장치 관리에 다른 서비스를 사용할 수 없습니다.

>[!IMPORTANT]
> Intune만 사용(온라인 서비스)하여 모바일 장치를 관리할지, 아니면 Intune으로 System Center Configuration Manager(온-프레미스 소프트웨어 솔루션 및 온라인 서비스 결합)를 사용하여 모바일 장치를 관리할지를 신중히 고려해야 합니다. 이런 항목을 설정한 후에는 모바일 장치 관리 기관을 변경할 수 없습니다.



1.  [Microsoft Intune 관리 콘솔](http://manage.microsoft.com)에서 **관리** &gt; **모바일 장치 관리**를 선택합니다.

2.  **작업** 목록에서 **모바일 장치 관리 기관 설정**을 클릭합니다. **MDM 기관 설정** 대화 상자가 열립니다.

    ![MDM 기관 설정 대화 상자](../media/intune-mdm-authority.png)

3.  Intune을 MDM 기관으로 지정할 것임을 확인하라는 요청 메시지가 표시됩니다. 이 확인란을 선택한 후 **예**를 선택하여 모바일 장치를 관리하는 데 Microsoft Intune을 사용합니다.

## Intune 회사 포털 구성

Intune 회사 포털에서 사용자는 회사 데이터에 액세스하고 장치 등록, 앱 설치, IT 부서 지원 정보 찾기 등의 일반적인 작업을 수행할 수 있습니다.

> [!TIP] 회사 포털을 사용자 지정할 때는 구성이 회사 포털 웹 사이트 및 회사 포털 앱에 모두 적용됩니다.

회사 포털을 사용자 지정하면 최종 사용자에게 친숙하고 유용한 환경을 제공하는 데 도움이 됩니다. 그렇게 하려면 [Microsoft Intune 관리자 콘솔](https://manage.microsoft.com)에 테넌트 또는 서비스 관리자로 로그인하고, **관리** &gt; **회사 포털**을 선택하여 회사 포털 설정을 구성합니다.

![admin-console-admin-workspace-comp-portal-settings](../media/cp_sa_cpsetup.PNG)

#### 회사 연락처 정보 및 개인정보취급방침

회사 이름은 회사 포털의 제목으로 표시됩니다. 연락처 정보 및 세부 정보는 회사 포털의 IT 담당자 화면에서 사용자에게 표시됩니다. 개인정보취급방침은 사용자가 개인정보취급방침 링크를 클릭하면 표시됩니다.

|필드 이름|최대 길이|추가 정보|
    |----------|------------------------|----------------|
    |회사 이름|40|이 이름은 회사 포털의 제목으로 표시됩니다.|
    |IT 부서 연락처 이름|40|이 이름은 **IT 담당자** 페이지에 표시됩니다.|
    |IT 부서 전화 번호|20|이 연락처 번호는 **IT 담당자** 페이지에 표시됩니다.|
    |IT 부서 전자 메일 주소|40|이 연락처 주소는 **IT 담당자** 페이지에 표시됩니다. 유효한 메일 주소를 **alias@domainname.com** 형식으로 입력해야 합니다.|
    |추가 정보|120|**IT 담당자** 페이지에 표시됩니다.|
    |회사 개인정보취급방침 URL|79|사용자가 회사 포털에서 개인정보취급방침 링크를 클릭할 때 표시되는 회사 개인정보취급방침을 지정할 수 있습니다. https://www.contoso.com 형식의 올바른 URL을 입력해야 합니다.|

#### 지원 연락처
지원 웹 사이트가 회사 포털의 사용자에게 표시되어, 온라인 지원에 액세스할 수 있도록 합니다.

|필드 이름|최대 길이|추가 정보|
    |----------|------------------------|----------------|
    |지원 웹 사이트 URL|150|최종 사용자가 사용할 지원 웹 사이트가 있는 경우 여기에서 URL을 지정합니다. URL은 https://www.contoso.com 형식이어야 합니다. URL을 지정하지 않으면 회사 포털의 **IT 담당자** 페이지에서 지원 웹 사이트에 대해 아무 내용도 표시되지 않습니다.|
    |웹 사이트 이름|40|이 이름은 지원 웹 사이트의 URL에 대해 표시되는 식별 이름입니다. 지원 웹 사이트 URL을 지정하고 식별 이름을 지정하지 않으면 **IT 웹 사이트로 이동**이 회사 포털의 **IT 담당자** 페이지에 표시됩니다.|


#### 회사 브랜딩 사용자 지정

회사 로고, 회사 이름, 테마 색 및 배경으로 회사 포털을 사용자 지정할 수 있습니다.

|필드 이름|추가 정보|
    |----------|----------------|
    |테마 색|회사 포털에 적용할 테마 색을 선택합니다.|
    |회사 로고 포함|이 옵션을 사용하도록 설정한 경우 회사 포털에서 표시할 회사 로고를 업로드할 수 있습니다. 회사 포털 배경이 흰색인 경우에 표시되는 로고 하나와 회사 포털 배경이 직접 선택한 테마 색을 사용하는 경우에 표시되는 로고 하나, 두 개의 로고를 업로드할 수 있습니다. 각 로고는 .png 또는 .jpg 파일 형식이어야 하며 최대 해상도가 400 x 100픽셀이고 크기가 750KB 이하여야 합니다.|
    |[!INCLUDE[win8_client_2](../includes/win8_client_2_md.md)] 회사 포털 앱의 배경 선택|이 설정은 [!INCLUDE[win8_client_2](../includes/win8_client_2_md.md)] 회사 포털 앱의 배경에만 적용됩니다.|


변경 내용을 저장한 후 관리 콘솔의 **회사 포털** 페이지 맨 아래에 제공된 링크를 사용하여 회사 포털 웹 사이트를 확인할 수 있습니다. 이러한 링크는 변경할 수 없습니다. 사용자가 로그인하면 이러한 링크가 회사 포털에 구독을 표시합니다.

## Intune 사용자 라이선스 할당

**Office 365 관리 포털**을 사용하여 클라우드 기반 사용자를 수동으로 추가하고, 클라우드 기반 사용자 계정 및 온-프레미스 Active Directory에서 Azure AD로 동기화한 계정에 라이선스를 할당합니다.

1.  테넌트 관리자 자격 증명을 사용하여 [Office 365 관리 포털](https://portal.office.com/Admin/Default.aspx)에 로그인합니다.

2.  할당할 사용자 계정과 Intune 사용자 라이선스를 선택하고, 사용자 계정 속성의 **Microsoft Intune** 확인란을 활성화합니다.

3.  사용자 계정이 Microsoft Intune 사용자 그룹에 추가되고 그에 따라 서비스를 사용하고 장치를 관리하도록 등록할 권한이 사용자에게 부여됩니다.

## 모바일 장치 설정
MDM 기관을 설정한 후 조직에서 지원하려는 운영 체제에 대한 장치 관리를 설정해야 합니다. 장치 관리를 설정하는 데 필요한 단계는 운영 체제에 따라 다릅니다. 예를 들어 Android OS는 Intune 관리 콘솔에서 아무런 작업이 필요하지 않습니다. 반면에 Windows 및 iOS는 관리를 허용하려면 장치와 Intune 간의 트러스트 관계가 필요합니다.

> [!div class="op_single_selector"]
- [Microsoft Intune을 사용한 Android 관리 설정](set-up-android-management-with-microsoft-intune.md)
- [Set up iOS and Mac management with Microsoft Intune](set-up-ios-and-mac-management-with-microsoft-intune.md)
- [Microsoft Intune을 사용한 Windows Phone 관리 설정](set-up-windows-phone-management-with-microsoft-intune.md)
- [Microsoft Intune을 사용한 Windows 장치 관리 설정](set-up-windows-device-management-with-microsoft-intune.md)

또한 다음을 수행할 수 있습니다.
 - [장치 등록 관리자 계정](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)을 사용하여 여러 장치 등록
 - 장치 및 대상 정책 등록을 돕도록 [IMEI 번호를 사용하여 회사 소유 장치 지정](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md)


<!--HONumber=Jun16_HO1-->


