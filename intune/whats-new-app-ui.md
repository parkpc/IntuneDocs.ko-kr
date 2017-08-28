---
title: "Intune 최종 사용자 앱 UI 업데이트"
description: "최종 사용자 장치에서 Intune과 함께 작동하는 앱의 UI가 어떻게 변경되었는지 알아보세요."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 08/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b782e382-8deb-48a7-a437-d7c5a17163f1
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 33d1f28cd5522ed47c3fdf83b289116728ded12b
ms.sourcegitcommit: 0b164f806165d312acfc88815a60e325e3d02672
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2017
---
# <a name="ui-updates-for-intune-end-user-apps"></a>Intune 최종 사용자 앱 UI 업데이트
최종 사용자가 이 Microsoft Intune 릴리스에서 보게 될 앱의 UI가 어떻게 업데이트되었는지 알아보세요. 그러면 사용자 커뮤니케이션 및 배포를 지원하기 위해 만든 사용자 지정 문서 업데이트에 도움이 될 것입니다. 사용자가 회사 포털을 사용하여 지원 센터에 전화해 지원을 요청하는 경우 사용자에게 발생하는 문제를 더 잘 해결하는 방법을 이해하는 데에도 도움이 될 수 있습니다.

## <a name="week-of-august-14-2017"></a>2017년 8월 14일 주

### <a name="updates-to-the-device-details-page-on-the-company-portal-app-for-windows-10"></a>Windows 10용 회사 포털 앱의 “장치 세부 정보” 페이지에 대한 업데이트

Windows 10용 회사 포털 앱이 __장치 세부 정보__ 페이지의 제목 아래에서 속성으로 __범주__ 태그가 이동됩니다.

![Windows용 회사 포털 앱의 “장치 세부 정보” 화면으로, 이제 해당 화면의 제목 바로 아래가 아니라 속성으로 “범주” 필드가 표시됩니다.](./media/cp_win10_category_tag_move_after_1708.png)

## <a name="week-of-july-31-2017"></a>2017년 7월 31일 주

### <a name="improved-sign-in-experience-across-company-portal-apps-for-all-platforms---user-story-1132123--"></a>모든 플랫폼에 대해 회사 포털 앱 전체에서 로그인 환경 개선됨 <!--User Story 1132123-->

Android, iOS 및 Windows용 Intune 회사 포털 앱에 대한 로그인 환경을 개선하게 될 향후 몇 개월 내에 제공될 변경이 있음을 알려드립니다. Azure AD에서 이 변경 내용을 적용할 경우 회사 포털 앱에 대한 모든 플랫폼에서 새로운 사용자 환경이 자동으로 나타나게 됩니다. 또한 사용자가 이제 생성된 일회용 코드를 사용하여 다른 장치에서 회사 포털에 로그인할 수도 있습니다. 이 기능은 사용자가 자격 증명 없이 로그인해야 할 경우에 특히 유용합니다.  

아래에서 이전 로그인 환경, 자격 증명을 사용하는 새 로그인 환경, 그리고 다른 장치로부터의 새 로그인 환경을 볼 수 있습니다.

__이전 로그인 환경__

![웹 사이트가 그림으로 표시되면서 그 앞에 사람 아이콘이 포함된 회사 포털 로그인 페이지 그 아래 “로그인” 단추가 있습니다. Microsoft 개인 정보 및 쿠키 정보로 이동하게 하는 하단의 링크](./media/cp_ios_aad_signin_before_1704_001.png)

![사용자는 로그인을 탭한 후 전자 메일 및 암호를 요구하는 이 페이지에서 암호 오류를 해결하는 방법을 제공하고 자격 증명을 입력합니다.](./media/cp_ios_aad_signin_before_1704_002.png)

![암호를 입력한 후 회사 포털 앱에 로그인되며 이 상태는 로드 중 막대로 표현됩니다.](./media/cp_ios_aad_signin_before_1704_003.png)

__새 로그인 환경__

![웹 사이트가 그림으로 표시되면서 그 앞에 사람 아이콘이 포함된 회사 포털 로그인 페이지 그 아래 “로그인” 단추가 있습니다. Microsoft 개인 정보 및 쿠키 정보로 이동하게 하는 하단의 링크](./media/cp_ios_aad_signin_after_1704_001.png)

![사용자는 같은 화면에서 전자 메일 및 암호 대신 전자 메일 주소만 입력하라는 메시지를 받습니다.](./media/cp_ios_aad_signin_after_1704_002.png)

![전자 메일 주소가 승인된 후에 암호를 입력하라는 메시지가 표시됩니다.](./media/cp_ios_aad_signin_after_1704_003.png)

![인증 프로세스를 진행하고 나면 회사 포털 앱에 로그인되며 이 상태는 로드 중 막대로 표현됩니다.](./media/cp_ios_aad_signin_from_another_device_after_1704_007.png)

__다른 장치에서 로그인 시 새 로그인 환경__

![웹 사이트가 그림으로 표시되면서 그 앞에 사람 아이콘이 포함된 회사 포털 로그인 페이지 그 아래 “로그인” 단추가 있습니다. Microsoft 개인 정보 및 쿠키 정보로 이동하게 하는 하단의 링크](./media/cp_ios_aad_signin_from_another_device_after_1704_001.png)

__다른 장치에서 로그인__ 링크를 탭합니다.

![회사 컴퓨터의 고유 암호를 사용하여 aka.ms/devicelogin 페이지로 이동하여 로그인 시 해당 코드를 사용하라는 지침이 제공됩니다.](./media/cp_ios_aad_signin_from_another_device_after_1704_003.png)

브라우저를 시작하고 [https://aka.ms/devicelogin](https://aka.ms/devicelogin)으로 이동합니다.

![회사 포털 앱이 아닌 작업 컴퓨터에서 사용자 브라우저 이미지 표시되는 "장치 로그인" 페이지에서 사용자에게 회사 포털 앱에서 받은 코드를 입력하라는 메시지가 나타납니다.](./media/cp_ios_aad_signin_from_another_device_after_1704_004.png)

회사 포털 앱에서 확인한 코드를 입력합니다. __계속__을 선택하면 스마트 카드와 같이 회사에서 지원되는 방법을 사용하여 인증할 수 있습니다.

![사용자는 필드에 고유한 코드를 입력하고 "장치 로그인" 사이트에서 Intune 회사 포털이 로그인에 필요한 인증을 수신하는 올바른 앱인지 확인을 요구합니다.](./media/cp_ios_aad_signin_from_another_device_after_1704_005.png)

![사용자가 장치에서 회사 포털 앱에 로그인했으며 이 페이지를 닫을 수 있음을 언급하는 확인 페이지](./media/cp_ios_aad_signin_from_another_device_after_1704_006.png)

회사 포털 앱에서 로그인이 시작됩니다.

![인증 프로세스를 진행하고 나면 회사 포털 앱에 로그인되며 이 상태는 로드 중 막대로 표현됩니다.](./media/cp_ios_aad_signin_from_another_device_after_1704_007.png)

## <a name="week-of-june-12-2017"></a>2017년 6월 12일 주

### <a name="company-portal-app-for-android-now-has-a-new-end-user-experience-for-app-protection-policies---1305217--"></a>이제 Android용 회사 포털 앱에 앱 보호 정책에 대한 새로운 최종 사용자 환경이 있음 <!--1305217-->
고객 의견에 따라 Android용 회사 포털 앱에 **회사 콘텐츠 액세스** 단추가 표시됩니다. 이는 Intune 모바일 응용 프로그램 관리의 기능인 앱 보호 정책을 지원하는 앱만 액세스하면 되는 경우 최종 사용자가 불필요하게 등록 프로세스를 수행하지 않도록 하기 위한 것입니다.

사용자는 장치 등록을 시작하는 대신 **회사 콘텐츠 액세스** 단추를 탭합니다.

![표준 사례처럼 즉각적인 등록 옵션을 제공하는 대신 중간에 큰 텍스트 "회사 콘텐츠 액세스"가 표시된 Android 회사 포털 앱 이미지](./media/and_access_company_content_after_1706.png)

그러면 사용자가 장치에서 사용하기 위해 앱에 권한을 부여하도록 회사 포털 웹 사이트로 이동됩니다. 회사 포털 웹 사이트에서 사용자 자격 증명을 확인합니다.

![로그인을 확인하는 회사 포털 웹 사이트 이미지](./media/and_iwp_sign_in_auth_page_after_1706.png)

**동작** 메뉴를 탭하면 전체 관리에 앱을 등록할 수 있습니다.

![장치 등록 옵션이 있는 화면 오른쪽 위의 메뉴가 표시된 Android용 회사 포털 앱 이미지](./media/and_sign_in_menu_after_app_protection_policy_enrolled_after_1706.png)

### <a name="improvements-to-app-syncing-with-windows-10-creators-update---676505--"></a>Windows 10 크리에이터스 업데이트와 동기화하는 앱 개선 사항 <!--676505-->

Windows 10용 회사 포털 앱은 이제 Windows 10 크리에이터스 업데이트(버전 1703)가 설치되어 있는 장치의 앱 설치 요청 동기화를 자동으로 시작합니다. 이렇게 하면 "동기화 보류 중" 상태에 있는 동안의 앱 설치 지연 문제를 줄일 수 있습니다. 사용자가 수동으로 앱 내에서 동기화를 시작할 수도 있습니다.

![Microsoft Word 다운로드가 회사 포털 앱 스토어에서 보류 중 상태인 Windows 10 회사 포털 앱 이미지](./media/w10_download_pending_after_1706.png)

![장치가 동기화 중이며 앱 다운로드를 시도하고 있음을 나타내는 상태 메시지와 함께 새 자동 동기화 상태가 표시된 Windows 10 회사 포털 앱 이미지](./media/w10_download_pending_syncing_after_1706.png)

### <a name="new-guided-experience-for-windows-10-company-portal----1058938---"></a>Windows 10 회사 포털에 대한 새로운 단계별 환경 <!---1058938--->
Windows 10용 회사 포털 앱에 식별되거나 등록되지 않은 장치에 대한 단계별 Intune 연습 환경이 포함될 예정입니다. 새 환경에서는 Azure Active Directory 등록(조건부 액세스 기능에 필요) 및 MDM 등록(장치 관리 기능에 필요) 과정을 사용자에게 안내하는 단계별 지침을 제공합니다. 회사 포털 홈 페이지에서 안내 방식 환경에 액세스할 수 있습니다. 사용자는 등록을 완료하지 않아도 앱을 계속 사용할 수는 있지만 기능이 제한됩니다.

이 업데이트는 Windows 10 1주년 업데이트(빌드 1607) 이상을 실행하는 장치에서만 표시됩니다.

![사용 중인 장치가 회사에서 사용하도록 아직 설정되지 않았으며 사용자가 설정을 시작하려면 메시지를 선택해야 한다고 사용자에게 알리는 상태 메시지가 "장치" 목록의 중간에 표시된 Windows 10 회사 포털 앱 방문 페이지 이미지](./media/win10_guided_enroll_select_setup_after_1706.png)

![이 장치에 회사 계정을 추가해야 관리에 등록할 수 있다고 사용자에게 경고하는 Windows 10 회사 포털 앱 설정 페이지 이미지](./media/win10_guided_enroll_we_help_setup_after_1706.png)

![등록을 완료하려면 설정 앱으로 이동한 다음 "연결"을 선택해야 한다고 사용자에게 알리는 Windows 10 회사 포털 앱의 이 장치에 회사 계정 추가 페이지 이미지 이렇게 하면 화면에서 회사 포털 앱으로 돌아가 등록을 완료해야 한다고 알립니다.](./media/win10_guided_enroll_leaving_for_iwp_after_1706.png)

![이제 사용자 장치가 등록되었으며 계속하려면 '다음' 단추를 탭해야 한다고 알리는 완료 상태 메시지가 표시된 Windows 10 회사 포털 앱의 관리에 등록 화면 이미지](./media/win10_guided_enroll_youre_now_enrolled_after_1706.png)

![사용자에게 모든 설정이 완료되었으며 회사 계정을 제대로 추가하여 장치가 등록되었음을 알리는 Windows 10 회사 포털 앱 완료 화면 이미지](./media/win10_guided_enroll_youre_all_set_after_1706.png)

### <a name="new-menu-action-to-easily-remove-company-portal---1164569--"></a>회사 포털을 쉽게 제거할 수 있는 새로운 메뉴 작업 <!--1164569-->
사용자 여러분의 의견에 따라 장치에서 회사 포털 제거를 시작할 수 있는 새로운 메뉴 작업이 Android용 회사 포털 앱에 추가되었습니다. 이 작업을 수행하면 Intune 관리에서 장치가 제거되므로 사용자가 장치에서 앱을 제거할 수 있습니다.

![오른쪽 위에 작업 메뉴가 열려 있는 Android 회사 포털 앱의 이미지 새로운 "회사 포털 제거" 옵션은 "내 프로필"과 "설정" 아래, 그리고 "사용 약관", "도움말 및 의견", "정보" 위에 있는 세 번째 옵션으로 제공됩니다.](./media/android_remove_cp_menu_action_after_1705.png)

![작업 메뉴에서 새로운 "회사 포털 제거" 옵션을 선택하면 제공되는 확인 대화 상자 이미지 이 대화 상자에는 "회사 포털을 제거하면 장치를 더 이상 IT 관리자가 관리하지 않게 되며 회사 데이터, 회사 앱 및 회사 메일에 대한 액세스 권한이 제거될 수 있습니다."라는 알림이 표시됩니다. 그런 다음 "예"를 선택하여 회사 포털 앱을 제거할 것인지를 확인하라는 메시지가 표시됩니다.](./media/android_remove_cp_menu_confirmation_after_1705.png)

## <a name="week-of-june-5-2017"></a>2017년 6월 5일 주

### <a name="improvements-to-the-app-tiles-in-the-company-portal-app-for-ios"></a>iOS 용 회사 포털 앱의 앱 타일 개선 사항
사용자가 회사 포털에 대해 설정하는 브랜딩 색을 반영하도록 홈 페이지의 앱 타일 디자인이 업데이트되었습니다.

**업데이트 전**

!["모든 앱", "추천 앱" 및 "범주"의 미리 설정된 채우기 이미지가 표시되어 있는 업데이트 전의 iOS용 회사 포털 앱 이미지](./media/cp_ios_homepage_before_1705.png)

**업데이트 후**

![조직에 맞는 색을 선택하는 기능이 반영된 업데이트 후의 iOS용 회사 포털 앱 이미지](./media/cp_ios_homepage_after_1705.png)

### <a name="account-picker-now-available-for-the-company-portal-app-for-ios"></a>이제 iOS용 회사 포털 앱에서 계정 선택기 사용 가능
사용자가 회사 또는 학교 계정을 사용하여 iOS 장치에서 다른 Microsoft 앱에 로그인한 경우 처음으로 회사 포털에 로그인할 때 새로운 계정 선택기가 나타날 수 있습니다.

![테스트 사용자 "Robin Swanson"이 두 전자 메일 주소 중 하나를 선택하는 방법을 보여 주는 계정 선택기 이미지 위 그림에 나와 있는 것처럼, 두 주소 아래에는 사용자가 다른 계정으로 로그인하는 데 사용할 수 있는 단추가 있습니다.](./media/cp_ios_multi-account-selector-after-1705.png)

## <a name="april-2017"></a>2017년 4월

### <a name="new-icons-for-the-managed-browser-and-the-company-portal---918433-918431--"></a>Managed Browser 및 회사 포털의 새 아이콘 <!--918433, 918431-->

Managed Browser 앱의 Android 및 iOS 버전 모두에서 아이콘이 업데이트됩니다. 새 아이콘은 업데이트된 Intune 배지를 포함하므로 EM+S(Enterprise Mobility + Security)의 다른 앱과 더 일관된 환경을 제공합니다.

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="/intune/media/cp_manbro_before_042017.png" alt="The previous version of the Managed Browser app icon." width=200 height=366 align=center>
          </td>
          <td>
             <img src="/intune/media/cp_manbro_after_042017.png" alt="The updated version of the Managed Browser app icon." width=200 height=366 align=center>
           </td>
      </tr>
   </table>
</body>
</html>

회사 포털도 앱의 Android, iOS 및 Windows 버전에 대해 업데이트된 아이콘을 수신하므로 EM+S의 다른 앱과의 일관성을 개선합니다. 이러한 아이콘은 4월부터 5월 말까지 여러 플랫폼에서 점진적으로 출시됩니다.

### <a name="sign-in-progress-indicator-in-android-company-portal---953374--"></a>Android 회사 포털의 로그인 진행률 표시기 <!--953374-->

Android 회사 포털 앱의 업데이트에는 사용자가 앱을 시작하거나 다시 시작할 때 로그인 진행률 표시기가 표시됩니다. 표시기에서는 "연결 중..."에서부터 "로그인 중...", "보안 요구 사항을 확인하는 중..."까지 새로운 상태를 진행한 후 사용자가 앱에 액세스할 수 있도록 허용합니다.

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="/intune/media/cp_android_connecting_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Connecting' underneath it." width=200 height=366 align=center>
          </td>
          <td>
             <img src="/intune/media/cp_android_signing_in_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Signing in' underneath it." width=200 height=366 align=center>
           </td>
           <td>
              <img src="/intune/media/cp_android_checking_security_reqs_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Checking for security requirements' underneath it." width=200 height=366 align=center>
           </td>
      </tr>
   </table>
</body>
</html>

### <a name="improved-app-install-status-for-the-windows-10-company-portal-app---676495--"></a>Windows 10 회사 포털 앱에 대해 앱 설치 상태 개선 <!--676495-->
이제 Windows 10 회사 포털 앱에서는 앱 세부 정보 페이지에 설치 진행률 표시줄을 제공합니다. 이 진행률 표시줄은 Windows 10 1주년 업데이트 이상을 실행하는 장치의 최신 앱에서 지원됩니다.

__이전__ ![상태가 ‘설치 중’으로 표시되는 이전 버전의 로딩 화면 이미지](./media/cp_win10_install_status_before_1704.png)

__이후__ ![이제 설치 진행률 표시줄이 표시되는 업데이트된 버전의 로딩 화면 이미지](./media/cp_win10_install_status_after_1704.png)

## <a name="february-2017"></a>2017 년 2월

### <a name="new-user-experience-for-the-company-portal-app-for-android---621622-announced-1702--"></a>Android용 회사 포털 앱의 새 사용자 환경 <!--621622, announced 1702-->
3월부터, Android용 회사 포털 앱이 [material design guidelines](https://material.io/guidelines/material-design/introduction.html)(재료 디자인 지침)에 따라 모양과 느낌이 더욱 세련되어집니다. 이러한 향상된 사용자 환경에는 다음이 포함됩니다.

* __색__: 탭 헤더에 사용자 지정 색상표에 따라 색을 표시할 수 있습니다.

![왼쪽은 업데이트 전의 Android용 회사 포털 앱 이미지입니다. 오른쪽은 업데이트 후의 Android용 회사 포털 앱 이미지입니다. 두 이미지 모두에서 사용 가능한 세 탭인 앱, 장치 및 IT 담당자 중에 장치 탭이 선택된 탭으로 표시되어 있습니다.](./media/CP_Android_DevicesTab_BeforeAfter.png)

* __인터페이스__: __앱__ 탭에서 __추천 앱__ 및 __모든 앱__ 단추가 업데이트되었습니다. __검색__ 단추는 이제 부동 작업 단추입니다.

![왼쪽은 업데이트 전의 Android용 회사 포털 앱 이미지입니다. 오른쪽은 업데이트 후의 Android용 회사 포털 앱 이미지입니다. 두 이미지 모두에서 사용 가능한 세 탭인 앱, 장치, IT 담당자 중에서 앱 탭이 선택된 탭으로 표시되어 있습니다.](./media/CP_Android_AppsTab_BeforeAfter.png)

* __탐색__: 모든 앱은 쉽게 탐색할 수 있도록 __추천__, __전체__ 및 __범주__ 탭으로 구분된 뷰를 표시합니다. __IT 담당자__는 가독성 향상을 위해 간소화 되었습니다.

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="/intune/media/cp_android_contactit_after.png" alt="The Company Portal app for Android displaying an updated version of the Contact IT tab. The tab shows available contact information for IT, including phone number, email address, IT website, and IT contact information." width=200 height=366 align=center>
          </td>
      </tr>
   </table>
</body>
</html>

## <a name="january-2017"></a>2017년 1월

### <a name="modernizing-the-company-portal-website---753980-announced-1701--"></a>회사 포털 웹 사이트 현대화 <!--753980, announced 1701-->
2월부터 회사 포털 웹 사이트는 관리 장치가 없는 사용자를 대상으로 하는 앱을 지원합니다. 웹 사이트는 다른 Microsoft 제품과 마찬가지로 새로운 고대비 색 구성표, 동적 그림 및 "햄버거 메뉴"를 사용합니다. ![이제 회사 포털 웹 사이트 왼쪽 상단에 추가된 햄버거 메뉴의 작은 이미지에는](./media/CP_hamburger_menu.png) 기술 지원팀 연락처 세부 정보와 기존 관리되는 장치에 관한 정보가 포함됩니다. 방문 페이지는 추천 및 최근에 업데이트된 앱에 대한 슬라이드를 포함하여 사용자가 사용할 수 있는 앱을 강조하도록 재조정됩니다.

![왼쪽은 이전 버전의 [앱], [내 장치] 및 [Featured and Categories](추천 및 범주) 보기를 포함하는 회사 포털 웹 사이트의 현재 버전 이미지입니다. 오른쪽은 새로 고쳐진 앱 슬라이드, [Recently Published](최근 게시) 앱 목록 및 업데이트된 [Categories](범주) 보기가 포함된 회사 포털 웹 사이트의 업데이트된 버전 이미지입니다.](./media/CP_Website_BeforeAfter_Feb2016.png)

## <a name="coming-soon-in-the-ui"></a>UI에서 곧 공개 예정
이는 사용자 인터페이스를 업데이트하여 사용자 환경을 개선할 방법에 대한 계획입니다.

> [!Note]
> 아래 이미지는 미리 보기일 수 있으며 발표된 제품은 제공된 버전과 다를 수 있음에 유의하세요.

### <a name="ui-updates-to-the-company-portal-website---1313244-part-2--"></a>회사 포털 웹 사이트의 UI 업데이트 <!--1313244 part 2-->

__추천 앱 업데이트__ 사용자가 추천하기 위해 선택한 앱을 찾아볼 수 있는 사이트에 전용 페이지를 추가하고 홈페이지의 추천 섹션에서 UI를 일부 조정했습니다.

![앱을 표시하는 다양한 색상의 타일입니다. 각 앱 아래에는 큰 사각형의 색상이 있습니다. 여기서 이 색상은 앱 로고의 기본 색상에서 가져옵니다. “추천 앱” 섹션은 회사 포털 앱의 맨 위에 표시됩니다.](./media/cp_win10_colorful_tiles_after_1708.png)

### <a name="see-also"></a>참고 항목
* [Microsoft Intune 블로그](http://go.microsoft.com/fwlink/?LinkID=273882)
* [클라우드 플랫폼 로드맵](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Intune의 새로운 기능](https://docs.microsoft.com/intune/whats-new)