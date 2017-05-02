---
title: "Intune 최종 사용자 앱 UI 업데이트 | Microsoft 문서"
description: "최종 사용자 장치에서 Intune과 함께 작동하는 앱의 UI가 어떻게 변경되었는지 알아보세요."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 04/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b782e382-8deb-48a7-a437-d7c5a17163f1
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 62dcb40ad5a7921c514a9d41da14b991e39f3bcd
ms.openlocfilehash: f4a48b889702147abe20fd513fdb0f774020a54a
ms.lasthandoff: 04/20/2017


---
# <a name="ui-updates-for-intune-end-user-apps"></a>Intune 최종 사용자 앱 UI 업데이트
최종 사용자가 이 Microsoft Intune 릴리스에서 보게 될 앱의 UI가 어떻게 업데이트되었는지 알아보세요. 그러면 사용자 커뮤니케이션 및 배포를 지원하기 위해 만든 사용자 지정 문서 업데이트에 도움이 될 것입니다. 사용자가 회사 포털을 사용하여 지원 센터에 전화해 지원을 요청하는 경우 사용자에게 발생하는 문제를 더 잘 해결하는 방법을 이해하는 데에도 도움이 될 수 있습니다.

> [!Note]
> 아래 그림은 미리 보기이며, 발표된 제품은 제시된 버전과 다를 수 있습니다.

## <a name="april-2017"></a>2017년 4월

### <a name="improved-sign-in-experience-across-company-portal-apps-for-all-platforms---user-story-1132123--"></a>모든 플랫폼에 대해 회사 포털 앱 전체에서 로그인 환경 개선됨 <!--User Story 1132123-->

Android, iOS 및 Windows용 Intune 회사 포털 앱에 대한 로그인 환경을 개선하고 있습니다.  Azure AD에서 이 변경 내용을 적용할 경우 회사 포털 앱에 대한 모든 플랫폼에서 새로운 사용자 환경이 자동으로 나타나게 됩니다. 또한 사용자가 이제 생성된 일회용 코드를 사용하여 다른 장치에서 회사 포털에 로그인할 수도 있습니다. 이 기능은 사용자가 자격 증명 없이 로그인해야 할 경우에 특히 유용합니다.  

아래에서 이전 로그인 환경, 자격 증명을 사용하는 새 로그인 환경, 그리고 다른 장치로부터의 새 로그인 환경을 볼 수 있습니다.

__이전 로그인 환경__

![웹 사이트가 그림으로 표시되면서 그 앞에 사람 아이콘이 포함된 회사 포털 로그인 페이지 그 아래 “로그인” 단추가 있습니다. Microsoft 개인 정보 및 쿠키 정보로 이동하게 하는 하단의 링크](./media/cp_ios_aad_signin_before_1704_001.png)

![사용자는 로그인을 탭한 후 전자 메일 및 암호를 요구하는 이 페이지에서 암호 오류를 해결하는 방법을 제공하고 자격 증명을 입력합니다.](./media/cp_ios_aad_signin_before_1704_002.png)

![암호를 입력한 후 회사 포털 앱에 로그인되며 이 상태는 로드 중 막대로 표현됩니다.](./media/cp_ios_aad_signin_before_1704_003.png)

__새 로그인 환경__

![웹 사이트가 그림으로 표시되면서 그 앞에 사람 아이콘이 포함된 회사 포털 로그인 페이지 그 아래 “로그인” 단추가 있습니다. Microsoft 개인 정보 및 쿠키 정보로 이동하게 하는 하단의 링크](./media/cp_ios_aad_signin_after_1704_001.png)

![사용자는 같은 화면에서 전자 메일 및 암호 대신 전자 메일 주소만 입력하라는 메시지를 받습니다.](./media/cp_ios_aad_signin_after_1704_002.png)

![전자 메일 주소가 승인된 후에 암호를 입력하라는 메시지가 표시됩니다.](./media/cp_ios_aad_signin_after_1704_003.png)

__다른 장치에서 로그인 시 새 로그인 환경__

![웹 사이트가 그림으로 표시되면서 그 앞에 사람 아이콘이 포함된 회사 포털 로그인 페이지 그 아래 “로그인” 단추가 있습니다. Microsoft 개인 정보 및 쿠키 정보로 이동하게 하는 하단의 링크](./media/cp_ios_aad_signin_from_another_device_after_1704_001.png)

__다른 장치에서 로그인__ 링크를 탭합니다.

![사용자는 같은 화면에서 전자 메일 및 암호 대신 전자 메일 주소만 입력하라는 메시지를 받습니다. 전자 메일 필드 아래의 링크에서 “다른 장치에서 로그인”이 표시됩니다.](./media/cp_ios_aad_signin_from_another_device_after_1704_002.png)

![회사 컴퓨터의 고유 암호를 사용하여 aka.ms/devicelogin 페이지로 이동하여 로그인 시 해당 코드를 사용하라는 지침이 제공됩니다.](./media/cp_ios_aad_signin_from_another_device_after_1704_003.png)

브라우저를 열고 [http://aka.ms/devicelogin](https://aka.ms/devicelogin)으로 이동합니다.

![회사 포털 앱이 아닌 작업 컴퓨터에서 사용자 브라우저 이미지 표시되는 "장치 로그인" 페이지에서 사용자에게 회사 포털 앱에서 받은 코드를 입력하라는 메시지가 나타납니다.](./media/cp_ios_aad_signin_from_another_device_after_1704_004.png)

회사 포털 앱에서 확인한 코드를 입력합니다. __계속__을 선택하면 스마트 카드와 같이 회사에서 지원되는 방법을 사용하여 인증할 수 있습니다.

![사용자는 필드에 고유한 코드를 입력하고 "장치 로그인" 사이트에서 Intune 회사 포털이 로그인에 필요한 인증을 수신하는 올바른 앱인지 확인을 요구합니다.](./media/cp_ios_aad_signin_from_another_device_after_1704_005.png)

![사용자가 장치에서 회사 포털 앱에 로그인했으며 이 페이지를 닫을 수 있음을 언급하는 확인 페이지](./media/cp_ios_aad_signin_from_another_device_after_1704_006.png)

회사 포털 앱에서 로그인이 시작됩니다.

![인증 프로세스를 진행하고 나면 회사 포털 앱에 로그인되며 이 상태는 로드 중 막대로 표현됩니다.](./media/cp_ios_aad_signin_from_another_device_after_1704_007.png)

### <a name="new-icons-for-the-managed-browser-and-the-company-portal---918433-918431--"></a>Managed Browser 및 회사 포털의 새 아이콘 <!--918433, 918431-->

Managed Browser 앱의 Android 및 iOS 버전 모두에서 아이콘이 업데이트됩니다. 새 아이콘은 업데이트된 Intune 배지를 포함하므로 EM+S(Enterprise Mobility + Security)의 다른 앱과 더 일관된 환경을 제공합니다.

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="https://docs.microsoft.com/InTune/whats-new/media/cp_manbro_before_042017.png" alt="The previous version of the Managed Browser app icon." width=200 height=366 align=center>
          </td>
          <td>
             <img src="https://docs.microsoft.com/InTune/whats-new/media/cp_manbro_after_042017.png" alt="The updated version of the Managed Browser app icon." width=200 height=366 align=center>
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
            <img src="https://docs.microsoft.com/InTune/whats-new/media/cp_android_signing_in_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Connecting' underneath it." width=200 height=366 align=center>
          </td>
          <td>
             <img src="https://docs.microsoft.com/InTune/whats-new/media/cp_android_checking_security_reqs_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Signing in' underneath it." width=200 height=366 align=center>
           </td>
           <td>
              <img src="https://docs.microsoft.com/InTune/whats-new/media/cp_android_connecting_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Checking for security requirements' underneath it." width=200 height=366 align=center>
           </td>
      </tr>
   </table>
</body>
</html>

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
            <img src="https://docs.microsoft.com/InTune/whats-new/media/cp_android_contactit_after.png" alt="The Company Portal app for Android displaying an updated version of the Contact IT tab. The tab shows available contact information for IT, including phone number, email address, IT website, and IT contact information." width=200 height=366 align=center>
          </td>
      </tr>
   </table>
</body>
</html>

## <a name="january-2017"></a>2017년 1월

### <a name="modernizing-the-company-portal-website---753980-announced-1701--"></a>회사 포털 웹 사이트 현대화 <!--753980, announced 1701-->
2월부터 회사 포털 웹 사이트는 관리 장치가 없는 사용자를 대상으로 하는 앱을 지원합니다. 웹 사이트는 다른 Microsoft 제품과 마찬가지로 새로운 고대비 색 구성표, 동적 그림 및 "햄버거 메뉴"를 사용합니다. ![이제 회사 포털 웹 사이트 왼쪽 상단에 추가된 햄버거 메뉴의 작은 이미지에는](./media/CP_hamburger_menu.png) 기술 지원팀 연락처 세부 정보와 기존 관리되는 장치에 관한 정보가 포함됩니다. 방문 페이지는 추천 및 최근에 업데이트된 앱에 대한 슬라이드를 포함하여 사용자가 사용할 수 있는 앱을 강조하도록 재조정됩니다.

![왼쪽은 이전 버전의 [앱], [내 장치] 및 [Featured and Categories](추천 및 범주) 보기를 포함하는 회사 포털 웹 사이트의 현재 버전 이미지입니다. 오른쪽은 새로 고쳐진 앱 슬라이드, [Recently Published](최근 게시) 앱 목록 및 업데이트된 [Categories](범주) 보기가 포함된 회사 포털 웹 사이트의 업데이트된 버전 이미지입니다.](./media/CP_Website_BeforeAfter_Feb2016.png)


### <a name="see-also"></a>참고 항목
* [Microsoft Intune 블로그](http://go.microsoft.com/fwlink/?LinkID=273882)
* [클라우드 플랫폼 로드맵](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Azure Tools의 새로운 기능](https://docs.microsoft.com/intune-azure/introduction/whats-new)
* [새로운 기능 - 아카이브](whats-new-archive.md)

