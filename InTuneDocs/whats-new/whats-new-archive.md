---
title: "새로운 기능 아카이브 | Microsoft Intune"
description: 
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ed2db991-4729-49a7-a1e6-be2ffa0d03d1
ROBOTS: noindex,nofollow
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ecf43b38e9593375981770583220d4ce2dfd709f
ms.openlocfilehash: 8b0f393da727b433a926e780d6de42cf7b4c6034


---
## 2015년 12월
### Microsoft 회사 포털에 대한 변경 사항 및 업데이트
이 릴리스에서는 회사 포털에 다음과 같은 변경 내용을 적용했습니다.

**Android 회사 포털 앱**

새 Google 요구 사항을 준수하기 위해 다음과 같이 변경되었습니다. Android 6.0 이상 장치에서는 다음 두 개의 새 메시지가 사용자에게 표시됩니다.
* 회사 포털에서 통화를 하고 전화 통화를 관리하도록 허용하시겠습니까?
* 회사 포털에서 장치의 사진, 미디어 및 파일에 액세스하도록 허용하시겠습니다?

이러한 두 메시지에 대한 자세한 내용은 다음 표를 참조하세요.



메시지 텍스트  |회사 포털에서 통화를 하고 전화 통화를 관리하도록 허용하시겠습니까?  
---------|---------
메시지의 의미     |  사용자의 장치 전화 번호 및 IMEI를 Intune 서비스로 보내고 관리 콘솔의 [하드웨어] 페이지에 표시할 수 있도록 합니다.   </br></br>**참고: 회사 포털 앱은 전화를 걸거나 전화 통화를 관리하지 않습니다.** 메시지 텍스트는 Google에서 제어하므로 변경할 수 없습니다. </br></br>**하드웨어 페이지**를 표시하려면 **그룹** > **모든 모바일 장치** > **장치**로 이동합니다. 사용자의 장치를 선택하고 **속성 보기** > **하드웨어**로 이동합니다.    
메시지 표시 위치 및 시기  | 사용자가 처음으로 회사 포털 앱에 로그인하여 장치 등록을 시작할 때 메시지가 표시됩니다.|         
사용자가 액세스를 허용하는 경우 발생되는 작업  |  장치의 전화 번호와 IMEI가 관리 콘솔의 [하드웨어] 페이지에 표시됩니다. |         
사용자가 액세스를 거부하는 경우 발생되는 작업     | 사용자가 계속해서 회사 포털 앱을 사용하고 장치를 등록할 수 있지만 관리 콘솔의 [하드웨어] 페이지에서 사용자의 장치 전화 번호와 IMEI가 비어 있습니다.       </br></br> 사용자가 액세스 거부 후 두 번째로 회사 포털 앱에 로그인할 때 메시지가 다시 표시되지 않도록 선택할 수 있는 **다시 묻지 않음** 확인란이 메시지에 표시됩니다.</br></br>사용자가 액세스를 허용하지만 나중에 거부하는 경우 등록 후 다음에 사용자가 회사 포털 앱에 로그인할 때 메시지가 표시됩니다.</br></br>사용자가 나중에 액세스를 허용할 경우 **설정** > **앱** > **회사 포털** > **사용 권한** > **휴대폰**으로 이동한 다음 사용 권한을 설정합니다.
추가 정보     |  사용자의 경우: [회사 포털 앱에 로그인](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_signin_cp)  </br></br>IT 전문가의 경우: 이 표에 있는 정보는 [사용자가 회사 포털 앱 메시지를 이해할 수 있도록 지원](https://technet.microsoft.com/library/dn948527.aspx#BKMK_help_users_understd_msgs)에도 있습니다.   

메시지 텍스트  |회사 포털에서 장치의 사진, 미디어 및 파일에 액세스하도록 허용하시겠습니다?  
---------|---------
메시지의 의미     |  장치에서 장치의 SD 카드에 데이터 로그를 쓸 수 있도록 하여 USB 케이블을 사용하여 로그를 이동할 수 있도록 합니다.   </br></br>**참고: 회사 포털 앱은 사용자의 사진, 미디어 및 파일에 액세스하지 않습니다.** 메시지 텍스트는 Google에서 제어하므로 변경할 수 없습니다.     
메시지 표시 위치 및 시기  | 사용자가 **데이터 보내기**를 탭하여 데이터 로그를 IT 관리자에게 보낼 때 메시지가 표시됩니다.|         
사용자가 액세스를 허용하는 경우 발생되는 작업  |  로그가 SD 카드에 복사됩니다. |         
사용자가 액세스를 거부하는 경우 발생되는 작업     | 계속 로그 데이터를 보낼 수는 있지만 로그가 장치의 SD 카드에 복사되지 않습니다.       </br></br> 사용자가 액세스 거부 후 두 번째로 회사 포털 앱에 로그인할 때 메시지가 다시 표시되지 않도록 선택할 수 있는 **다시 묻지 않음** 확인란이 메시지에 표시됩니다.</br></br>사용자가 액세스를 허용하지만 나중에 거부하는 경우 다음에 로그를 보내려고 시도할 때 메시지가 표시됩니다.</br></br>사용자가 나중에 액세스를 허용할 경우 **설정** > **앱** > **회사 포털** > **사용 권한** > **저장소**로 이동한 다음 사용 권한을 설정합니다.
추가 정보     |  사용자의 경우: [메일을 사용하여 진단 데이터 로그를 IT 관리자에게 보내기](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_send_diag_logs)  </br></br>IT 전문가의 경우: 이 표에 있는 정보는 [사용자가 회사 포털 앱 메시지를 이해할 수 있도록 지원](https://technet.microsoft.com/library/dn948527.aspx#BKMK_help_users_understd_msgs)에도 있습니다.   


**iOS 회사 포털 앱**
* 이제 사용자가 Microsoft Outlook 또는 기타 메일 앱을 사용하여 진단 로그를 IT 관리자에게 보낼 수 있습니다. 이전에는 네이티브 앱만 사용할 수 있었습니다.
* Apple의 DEP(장치 등록 프로그램) 및 회사에 등록된 장치에 대한 지원이 향상되었습니다. 자세한 내용은 [등록할 때 장치를 식별하도록 요청](https://technet.microsoft.com/library/mt598622.aspx#BKMK_ios_id_your_device)을 참조하세요.
* 사용자의 등록된 장치 목록에서 이제 현재 사용 중인 장치 옆에 녹색 확인 표시가 나타납니다. 이 확인 표시가 추가되기 전에는 등록된 장치 중에 어떤 장치를 사용 중인지 알 수 없었습니다.

**Windows 회사 포털 앱**

Microsoft는 Microsoft 제품 및 서비스를 개선하기 위해 회사 포털의 성능 및 사용에 대한 익명의 데이터를 자동으로 수집합니다. 최종 사용자는 장치에서 사용 현황 데이터 설정을 사용하여 데이터 수집을 해제할 수 있지만 관리자는 데이터 수집을 제어할 수 없으며 이 설정에 대한 최종 사용자의 선택을 변경할 수 없습니다.



## 2015년 11월
### 앱 관리
Intune에서는 회사 데이터가 소비자 앱이나 서비스에 유출되지 않도록 하는 MAM(모바일 응용 프로그램 관리) 정책을 지원합니다. 지금까지 이러한 정책은 MDM(모바일 장치 관리)에 대해서도 Intune에 등록된 장치에서 실행되는 모바일 앱에만 적용되었습니다.

이번 달 업데이트에서는 Intune이 MAM 기능을 새로운 장치 클래스로 확장합니다. Intune에 등록된 장치 외에도 이제 다음 장치에 MAM 정책을 적용할 수 있습니다.
* 다른 MDM(모바일 장치 관리) 솔루션에서 관리되는 장치
* 장치 관리 시스템에 등록되지 않은 장치, 일반적으로 BYO(Bring Your Own) 장치

이러한 새 MAM 기능에 대한 자세한 내용은 다음 블로그 게시물에서 확인할 수 있습니다.
* [관리되는 모바일 생산성 향상](http://blogs.technet.com/b/microsoftintune/archive/2015/11/17/enhancing-managed-mobile-productivity.aspx)
* [새로운 Microsoft Enterprise Mobility 기능 발표](http://blogs.technet.com/b/microsoftintune/archive/2015/11/17/enhancing-managed-mobile-productivity.aspx)

또한 Intune의 MAM 기능에 대한 몇 가지 중요 사항과 추가 정보는 다음과 같습니다.
* Office 모바일 앱, Intune SDK를 채택한 타사 앱 또는 Intune에 의해 래핑된 기간 업무 앱을 포함하여 Intune 지원 앱 내에서 회사 데이터는 소비자 데이터로부터 격리됩니다.
* 회사 데이터가 개인 앱에 공유되지 않도록 차단하는 동시에 회사 앱 간에 회사 데이터를 공유할 수 있습니다(**잘라내기/복사/붙여넣기**). 자세한 내용은 [MAM 정책이 앱 데이터를 보호하는 방법](https://technet.microsoft.com/library/mt627825.aspx)을 참조하세요. 이 예제 시나리오 [회사 및 개인 작업에 Microsoft Word 앱 사용](https://technet.microsoft.com/library/mt627827.aspx)에서는 회사 데이터가 개인 앱에 공유되지 않도록 하는 방법을 보여 줍니다.
* 앱별 PIN, 다른 이름으로 저장 컨트롤, 앱 간의 관리되는 데이터 공유 등의 주요 데이터 손실 방지 정책. 모든 정책 목록을 보려면 [Microsoft Intune으로 모바일 앱 관리 정책 만들기 및 배포](https://technet.microsoft.com/library/mt627829.aspx)를 참조하세요.
* Word, Excel, PowerPoint, Outlook, OneNote 및 비즈니스용 OneDrive에는 모두 이러한 새로운 기능이 있으며 장치 등록 여부에 관계없이 관리할 수 있습니다. 데이터 손실 방지 기능은 Apple 스토어 또는 Google Play 스토어의 표준 Office 앱에 기본적으로 제공되며 앱 래핑이나 테스트용으로 로드할 필요가 없습니다.
* 시작하는 방법에 대한 자세한 내용은 [Azure 포털에서 모바일 앱 관리 정책 시작](https://technet.microsoft.com/library/mt627830.aspx)을 참조하세요. 모바일 앱 관리 정책을 구성하고 배포하는 방법에 대한 자세한 내용은 [Microsoft Intune으로 모바일 앱 관리 정책 만들기 및 배포](https://technet.microsoft.com/library/mt627829.aspx)를 참조하세요.
* 최종 사용자가 회사 자격 증명으로 앱을 인증하는 경우 데이터 손실 방지 기능이 자동으로 설정됩니다. [Microsoft Intune 모바일 앱 관리 정책과 연결된 앱에 대한 최종 사용자 환경](https://technet.microsoft.com/library/mt627827.aspx) 항목에는 iOS 및 Android 장치에서 OneDrive에 액세스하기 위한 몇 가지 예제 시나리오가 포함되어 있습니다.
* iOS 및 Android 장치 둘 다에서 작동합니다.

[Microsoft Intune 모바일 응용 프로그램 관리 정책과 함께 사용할 수 있는 Microsoft 앱](https://technet.microsoft.com/library/dn708489.aspx) 목록이 최신 앱을 표시하도록 업데이트되었습니다.

### 장치 관리
 **Mac OS X 장치 관리** 이제 Intune을 사용하여 Mac OS X 장치를 등록하고 관리할 수 있습니다. Mac OS X 장치에서 다음을 수행할 수 있습니다.
* Intune에서 관리할 장치를 등록합니다. [Microsoft Intune을 사용한 iOS 및 Mac 관리 설정](https://technet.microsoft.com/library/dn408185.aspx)을 참조하세요.
* 일반 구성 정책을 사용하여 장치 설정을 제어합니다. [Microsoft Intune의 Mac OS X 구성 정책 설정](https://technet.microsoft.com/library/mt627823.aspx)을 참조하세요.
* Apple Configurator를 사용하여 만든 Mac OS X 설정을 배포합니다. [Microsoft Intune의 Mac OS X 사용자 지정 정책 설정](https://technet.microsoft.com/library/mt627820.aspx)을 참조하세요.
* Mac OS X 장치에서 하드웨어 및 소프트웨어 인벤토리를 수집합니다. [Microsoft Intune에서 인벤토리를 사용하는 장치 이해](https://technet.microsoft.com/library/jj733634.aspx)를 참조하세요.
* 관리하는 Mac OS X 장치에 대한 세부 정보를 표시하는 새 보고서를 실행합니다. [보고서를 사용하는 Microsoft Intune 작업 이해](https://technet.microsoft.com/library/dn646977.aspx)를 참조하세요.

**Windows 10 장치에 대한 새 Edge 브라우저 설정** Microsoft Edge 브라우저의 설정과 기능을 관리할 수 있도록 해주는 새로운 설정이 Windows 10 일반 구성 정책에 추가되었습니다. [Microsoft Intune의 Windows 10 구성 정책 설정](https://technet.microsoft.com/library/mt404697.aspx)을 참조하세요.

**메일 프로필** Windows 10 Desktop 및 Windows 10 Mobile 장치에 대한 새로운 메일 프로필 정책이 추가되었습니다. [Microsoft Intune 정책을 사용하여 장치의 설정 및 기능 관리](https://technet.microsoft.com/library/dn646984.aspx)를 참조하세요.

**새로운 준수 정책 설정** 다음과 같은 새 보안 및 시스템 정책 설정이 준수 정책 목록에 추가되었습니다.
* 회사 리소스에 액세스하는 Windows 8.1 이상 장치에 최신 업데이트가 설치되어 있는지 확인하려면 **자동 업데이트 필요** 설정을 사용합니다. 자동으로 설치되는 업데이트 유형(중요로 표시된 모든 업데이트 또는 중요나 권장으로 표시된 모든 업데이트)을 지정할 수도 있습니다. 준수 정책 설정의 전체 목록은 [Microsoft Intune에 대한 장치 정책 준수 정책 관리](https://technet.microsoft.com/library/dn705843.aspx)를 참조하세요.
* 새로운 **장치가 유휴 상태에서 되돌아오는 경우 암호 필요** 설정을 기존의 **암호를 요구하기 전까지 비활성 시간(분)** 설정과 함께 사용하면 최종 사용자가 일정 시간 동안 비활성 상태인 장치를 사용하기 위해 암호를 입력해야 하는 준수 설정을 만들 수 있습니다.

**새 조건부 액세스 정책 옵션** Y기존 또는 새 조건부 액세스 정책에서 **모든 사용자**에게 조건부 액세스 정책을 적용할 수 있습니다. Intune 및 Office 365 사용이 허가된 모든 사용자는 장치를 등록해야 하며, 장치 플랫폼이 Intune에서 지원되지 않는 경우 [Active Directory 인증 기반 로그인(최신 인증)](https://blogs.office.com/2014/11/12/office-2013-updated-authentication-enabling-multi-factor-authentication-saml-identity-providers/)을 사용하는 클라이언트 응용 프로그램에 대해 액세스가 차단됩니다.

**모든 플랫폼**에 조건부 액세스 정책에 적용되도록 지정할 수도 있습니다.  [Active Directory 인증 기반 로그인(최신 인증)](https://blogs.office.com/2014/11/12/office-2013-updated-authentication-enabling-multi-factor-authentication-saml-identity-providers/)을 사용하는 모든 클라이언트 응용 프로그램에 조건부 액세스 정책이 적용되며, 플랫폼이 Intune에서 지원되지 않는 경우 차단됩니다.

### Microsoft 회사 포털에 대한 변경 사항 및 업데이트
이 릴리스에서는 회사 포털 앱에 다음과 같은 변경 내용을 적용했습니다.

* **Android**: 사용자가 회사 포털 앱의 용도를 이해하는 데 도움이 되는 시작 화면이 Android 회사 포털 앱에 추가되었습니다. 이 화면은 회사가 Intune 구독자가 아닌 사용자의 앱 다운로드를 줄이기 위한 것입니다.

* **iOS**: 이제 Intune에서 [회사 포털 웹 사이트](https://portal.manage.microsoft.com)를 사용하여 Mac OS X 장치를 등록할 수 있습니다. 지침은 [Intune에서 Mac OS X 장치 등록](https://technet.microsoft.com/library/mt598622.aspx)을 참조하세요.

* **회사 포털 웹 사이트**: Intune에서 장치를 등록한 사용자는 이제 회사 포털 웹 사이트에서 **암호 초기화** 옵션을 사용하여 암호를 초기화할 수 있습니다. 이전에는 IT 관리자만 사용자 암호를 초기화할 수 있었습니다. [암호 초기화] 옵션은 Windows 8.1 및 Windows RT 장치에서는 지원되지 않으며 MDM(모바일 장치 관리) 또는 Exchange ActiveSync를 사용하는 MDM에서 장치를 등록할 때만 표시됩니다. 사용자 지침은 [암호 재설정](https://technet.microsoft.com/library/mt590895.aspx)을 참조하세요.

### 전역 관리자 라이선싱 변경
10월에 전역 관리자(테넌트 관리자라고도 함)는 별도의 Intune 또는 EMS(Enterprise Mobility Suite) 라이선스 없이 일상적인 관리 작업을 계속 수행할 수 있다고 발표했습니다. 그러나 전역 관리자가 자신의 장치나 회사 장치 등록 또는 Intune 회사 포털 사용 등의 서비스를 사용하려는 경우 다른 사용자와 마찬가지로 Intune 또는 EMS 라이선스가 필요합니다. 몇 가지 추가 정보는 다음과 같습니다.
* Intune 회사 포털에서 최종 사용자는 다음 작업을 수행할 수 있습니다.
    * 장치 등록
    * 장치 상태 보기
    * 전역 관리자가 조직에 배포한 소프트웨어 다운로드
    * 전역 관리자가 해당 IT 부서에 연락하는 방법에 대해 게시한 링크 찾기

    [회사 포털](https://technet.microsoft.com/library/dn646966.aspx#BKMK_CompanyPortal) 및 [회사 포털을 사용자 지정하는 방법](https://technet.microsoft.com/library/dn646983.aspx#BKMK_ConfigureCompanyPortal)에 대해 자세히 알아보세요.
* 조직을 대신해 Intune 또는 EMS를 구입하기 위해 등록한 사람이 자동으로 테넌트의 첫 번째 전역 관리자가 됩니다. 금년 가을에 Intune은 [Office 365 포털](http://portal.office.com/)로 이동하고 [Intune 계정 포털](http://account.manage.microsoft.com/)의 사용을 중지하는 과정의 일환으로 첫 번째 전역 관리자에게 Intune 또는 EMS 라이선스를 자동으로 할당하기 시작했습니다. 추가된 모든 전역 관리자는 별도의 Intune 또는 EMS 라이선스 없이 일상적인 관리 작업을 계속 수행할 수 있습니다. 최종 사용자 역할을 하고 자신의(또는 회사) 장치를 등록하거나 회사 포털에서 소프트웨어를 다운로드하는 경우에는 다른 사용자와 마찬가지로 라이선스가 필요합니다.
* 변경 내용은 단계적으로 도입되며, 이제 2016년 1월에 시작됩니다.
* Microsoft 파트너의 경우 이 변경은 고객을 대신해 서비스를 관리하는 능력에 영향을 주지 않습니다. 최종 사용자 작업의 경우 사용자가 장치를 등록하고 회사 포털에서 소프트웨어를 액세스하거나 다운로드하려면 Intune 또는 EMS 라이선스가 있어야 합니다.

이 변경에 대한 질문이 있으면 언제든지 Intune 지원 팀에 문의하세요.
* [Microsoft Intune 지원 채널](https://technet.microsoft.com/library/jj839713.aspx)
* [커뮤니티 지원](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod)

DCR(디자인 변경 요청) 또는 버그 신고를 포함하여 일반적인 Microsoft Intune 피드백이 있을 경우 [Intune 사용자 의견](https://microsoftintune.uservoice.com/)을 방문하세요.


### Intune 설명서의 새로운 기능 - 2015년 11월
**새 콘텐츠**
* [Microsoft Intune의 Mac OS X 구성 정책 설정](https://technet.microsoft.com/library/mt627823.aspx): Mac OS X 장치에 대한 장치 설정 및 기능을 제어하는 방법입니다.
* [Microsoft Intune의 Mac OS X 사용자 지정 정책 설정](https://technet.microsoft.com/library/mt627820.aspx): Apple Configurator 도구를 사용하여 만든 Mac OS X 장치 설정을 배포하는 방법입니다.
* [Microsoft Intune으로 데이터 손실 방지 앱 정책 구성](https://technet.microsoft.com/library/mt627825.aspx): 모바일 앱 관리 정책이 지원하는 시나리오 및 정책이 데이터를 보호하기 위해 작동하는 방식에 대한 정보가 포함되어 있습니다.
* [Azure 포털에서 모바일 앱 관리 정책 시작](https://technet.microsoft.com/library/mt627830.aspx): Azure Preview 포털을 모바일 앱 관리 정책에 사용하는 데 필요한 사항입니다.
* [Microsoft Intune으로 모바일 앱 관리 정책 만들기 및 배포](https://technet.microsoft.com/library/mt627829.aspx): Azure Preview 포털에서 모바일 앱 관리 정책을 만드는 방법의 단계별 연습이 포함되어 있습니다.
* [Microsoft Intune으로 모바일 앱 관리 정책 모니터링](https://technet.microsoft.com/library/mt627824.aspx): Azure Preview 포털을 사용하여 모바일 앱 관리 정책을 모니터링할 수 있는 방법에 대한 정보입니다.
* [Microsoft Intune 모바일 앱 관리 정책 및 iOS 다음에서 열기](https://technet.microsoft.com/library/mt627821.aspx): 모바일 앱 관리 정책이 iOS 다음에서 열기 기능에서 작동하는 방식에 대한 정보입니다.
* [Microsoft Intune 모바일 앱 관리 정책과 연결된 앱에 대한 최종 사용자 환경](https://technet.microsoft.com/library/mt627827.aspx): 모바일 앱 관리 정책과 연결된 앱을 사용하는 경우 최종 사용자 환경이 무엇인지를 설명합니다.
* [Microsoft Intune을 사용하여 관리되는 업무용 앱 데이터 초기화](https://technet.microsoft.com/library/mt627826.aspx): 회사 앱 데이터를 제거할 수 있는 방법입니다.

**업데이트된 내용**
* [Microsoft Intune의 Windows 10 구성 정책 설정](https://technet.microsoft.com/library/mt404697.aspx): 새로운 Edge 브라우저 설정이 추가되었습니다.
* [Microsoft Intune을 사용하여 IOS 및 Mac 관리 설정](http://technet.microsoft.com/library/dn408185.aspx): Mac OS X 장치를 등록하는 방법에 대한 정보가 추가되었습니다.
* [Microsoft Intune에서 인벤토리를 사용하는 장치 이해](https://technet.microsoft.com/library/jj733634.aspx): Mac OS X 장치에서 수집된 인벤토리에 대한 정보가 추가되었습니다. 또한 모든 장치 플랫폼에 대한 최신 정보로 항목이 업데이트되었습니다.
* [보고서를 사용하는 Microsoft Intune 작업 이해](https://technet.microsoft.com/library/dn646977.aspx): 관리되는 Mac OS X 장치 정보를 표시하는 데 사용되는 두 가지 새 보고서에 대한 정보가 추가되었습니다.
* [Microsoft Intune에 대한 장치 정책 준수 정책 관리](https://technet.microsoft.com/library/dn705843.aspx): 장치가 유휴 상태에서 돌아올 때 자동 업데이트 및 암호 요구 사항을 요구하기 위한 새 준수 정책에 대한 정보가 추가되었습니다.
* [Microsoft Intune으로 메일 액세스 관리](https://technet.microsoft.com/library/dn705841.aspx): 모든 플랫폼 및 모든 사용자에게 조건부 액세스 정책을 적용하는 기능에 대한 정보가 추가되었습니다.
* [Microsoft Intune을 사용한 SharePoint Online 액세스 관리](https://technet.microsoft.com/library/dn705844.aspx): 모든 플랫폼 및 모든 사용자에게 조건부 액세스 정책을 적용하는 기능에 대한 정보가 추가되었습니다.

## 2015년 10월

### Exchange 온-프레미스에 대한 조건부 액세스 업데이트
**이제 전역 Exchange 규칙이 차단 또는 격리로 설정되면 Intune에 등록된 규격 장치에 대해 Exchange Active Sync 메일 액세스를 허용할 수 있습니다.** 지금까지는 등록된 규격 장치에서 메일 액세스를 허용하기 위해 기본 전역 Exchange 규칙을 **허용**으로 설정해야 했습니다.

이 서비스 업데이트를 사용하면 이 설정이 더 이상 조건부 액세스에 대한 요구 사항이 아닙니다. Exchange 환경에서 기본 전역 규칙을 **차단/격리**로 설정해야 할 경우, Exchange 온-프레미스 조건부 액세스 정책 페이지에서 간단히 **기본 규칙보다 우선** 확인란을 선택합니다. [Microsoft Intune으로 메일 액세스 관리](https://technet.microsoft.com/library/dn705841.aspx) 항목에는 규칙 및 결과 최종 사용자 알림에 대한 자세한 내용이 포함되어 있습니다.

**새로운 원클릭 격리 환경** 원클릭 등록을 허용하도록 격리 메일 환경이 간소화되었습니다. 이 서비스 업데이트를 사용하는 최종 사용자는 격리 메일에 있는 하나의 링크를 클릭하여 회사 포털 앱 내에서 등록 프로세스를 완료할 수 있습니다.
### 모바일 장치 및 앱 관리 기능 업데이트
**Android** 이제 모든 Intune 관리 기능이 블로그 게시물 [Microsoft Intune에서 Android Marshmallow에 대한 Day 0 지원 제공](http://blogs.technet.com/b/microsoftintune/archive/2015/10/09/microsoft-intune-to-provide-day-0-support-for-android-marshmallow.aspx)에 설명된 대로 Android 6.0(Marshmallow)을 지원합니다.

**iOS** iOS 7.1 이전 버전을 실행하는 iOS 장치에 대한 새로운 앱 배포를 더 이상 만들 수 없습니다. iOS 7.1의 이전 버전을 실행하는 장치에 대한 모든 기존 앱 배포는 Intune으로 계속 작동 및 관리됩니다.

**Windows 10** 이제 Intune에서 **Windows 앱 패키지** 소프트웨어 설치 관리자 유형을 사용한 Windows 10 유니버설 앱 배포를 지원합니다. 자세한 내용과 요구 사항은 [Microsoft Intune으로 앱 배포 시작하기](http://technet.microsoft.com/en-US/library/dn646955.aspx)를 참조하세요.


### Microsoft 회사 포털 앱에 대한 변경 사항 및 업데이트
이 릴리스에서는 회사 포털 앱에 다음과 같은 변경 내용을 적용했습니다. **iOS** 사용자가 자신의 IT 관리자에게 진단 로그를 더 쉽게 보낼 수 있도록 새 단추가 회사 포털 앱에 추가되었습니다.

|단추 이름|표시되는 곳|
|------------|---------------|
|보고서|오류 경고 메시지|
|진단 보고서 보내기|회사 포털 앱의 정보 화면|



## 2015년 9월
### 모바일 장치 및 앱 관리 기능 업데이트
**이제 모든 Intune iOS 관리 기능이 iOS 9를 지원합니다.** iOS 9 관리 기능에 대한 자세한 내용은 [이 블로그 게시물](http://blogs.technet.com/b/microsoftintune/archive/2015/09/09/day-zero-support-for-ios-9-with-intune.aspx)을 참조하세요.

**iOS에 대한 새로운 모바일 앱 구성 정책** 새 모바일 앱 구성 정책을 사용하여 iOS 앱이 실행될 때 이 앱에서 필요로 할 수 있는 설정을 자동으로 제공합니다. 예를 들어 네트워크 포트나 사용자 이름을 제공할 수 있습니다. 자세한 내용은 [Microsoft Intune에서 모바일 앱 구성 정책을 사용하여 앱 구성](https://technet.microsoft.com/library/mt481447.aspx)을 참조하세요.

**iOS 9 사용자를 위한 더 간단한 앱 관리**
 이 릴리스에서는 iOS 9 사용자를 위해 Intune에서 관리하는 이미 배포된 앱을 가져올 수 있습니다. 이전 버전 iOS에서는 앱을 배포할 때 관리되지 않는 버전의 앱이 이미 장치에 설치되어 있으면 Intune에서 관리되는 앱을 설치하기 전에 사용자에게 수동으로 해당 앱을 제거해 달라고 요청해야 했습니다.

 하지만 Intune의 이번 릴리스에서는 이제 iOS 9 장치 사용자에게 Intune에서 앱을 관리하고 모든 관련 모바일 응용 프로그램 관리 정책을 적용하는 것을 허용하도록 확인할 수 있습니다.

 **Windows 10 관리** 새로운 [Windows 10 일반 구성 정책](https://technet.microsoft.com/library/mt404697.aspx)을 사용하여 Windows 10 및 Windows 10 Mobile을 실행하는 등록된 장치에 대한 암호, 장치, 브라우저 및 기타 설정을 구성합니다.

 **앱 만들기 및 등록된 Windows 10 장치에 배포** 새로운 소프트웨어 설치 관리자인 MDM(&#42;.msi)을 통한 Windows Installer를 사용하면 Windows Installer 앱을 만들고 Windows 10을 실행하는 등록된 장치에 배포할 수 있습니다. 자세한 내용은 [Microsoft Intune으로 앱 배포 시작하기](https://technet.microsoft.com/library/dn646955.aspx)를 참조하세요.

### Microsoft 회사 포털 앱에 대한 변경 사항 및 업데이트
이 릴리스에서는 회사 포털 앱에 다음과 같은 변경 내용을 적용했습니다.

**iOS**
* Microsoft는 Microsoft 제품 및 서비스를 개선하기 위해 회사 포털의 성능 및 사용에 대한 익명의 데이터를 자동으로 수집합니다. 최종 사용자는 장치에서 사용 현황 데이터 설정을 사용하여 데이터 수집을 해제할 수 있지만 관리자는 데이터 수집을 제어할 수 없으며 이 설정에 대한 최종 사용자의 선택을 변경할 수 없습니다.
* iPhone 6 및 6 Plus의 전체 화면 해상도 지원
* 버그를 수정해 보안을 강화했습니다.

### Intune 설명서의 새로운 기능 - 2015년 9월
**새 항목**

|Name|세부 정보|
|----|--------|
|[Microsoft Intune의 Windows 10 구성 정책 설정](https://technet.microsoft.com/library/mt404697.aspx)|이것은 Windows 10 및 Windows 10 Mobile을 실행하는 장치에서 설정 및 기능을 관리할 수 있도록 해주는 새로운 구성 정책입니다.
| [Microsoft Intune에서 모바일 앱 구성 정책을 사용하여 앱 구성](https://technet.microsoft.com/library/mt481447.aspx)|이것은 사용자가 iOS 앱을 실행할 때 필요할 수 있는 설정을 자동으로 제공할 수 있도록 해주는 새로운 정책 형식입니다. |

**업데이트된 항목**

|Name|세부 정보|
|----|-------|
|[Microsoft Intune에서 정책을 사용하여 컴퓨터 및 모바일 장치 관리](https://technet.microsoft.com/library/dn743712.aspx)|정책을 이해하고 만드는 데 도움이 되는 최신 정보를 포함하도록 업데이트되었습니다.|

## 2015년 8월
### 모바일 장치 및 앱 관리 기능 업데이트
* Intune 등록 및 회사 액세스에 대한**사용 조건** 은 [이제 정책을 사용하여 관리](https://technet.microsoft.com/library/mt405893.aspx)됩니다. 특정 사용자 그룹의 요구 사항에 맞게 다른 사용 조건을 지정할 수 있습니다. 예를 들어, 지리적 위치에 따라 정의된 그룹에 맞게 다른 언어의 사용 조건을 배포할 수 있습니다. [사용 조건을 편집](https://technet.microsoft.com/library/mt405893.aspx#BKMK_TCVers) 하고 버전 번호를 늘릴지, 사용자가 회사 포털을 사용하기 전에 사용 조건에 동의해야 하는지도 지정할 수 있습니다.
* **몇 가지 Intune 정책의 이름이 변경** 되어 제품 전체에서 일관성있고 찾기 쉽게 되었습니다. 사용 가능한 모든 Intune 정책 목록은 [Microsoft Intune에서 정책을 사용하여 컴퓨터 및 모바일 장치 관리](https://technet.microsoft.com/library/dn743712.aspx)를 참조하세요.
* **PKCS #12(.PFX) 인증서 프로필**은 Android 4.0 이상, Windows 10(데스크톱 및 모바일) 이상에서 사용할 수 있습니다. .PFX 사용에 NDES 서버는 필요하지 않습니다. [인증서 프로필을 사용하여 회사 리소스에 대한 액세스 사용](http://technet.microsoft.com/library/dn818904.aspx)에서 .PFX 인증서 프로필을 사용하는 방법을 알아봅니다.
* **Windows 10 Desktop 및 Mobile의 회사 경계 설정**에서는 [사용자가 Microsoft Intune에서 VPN 프로필을 사용하여 회사에 연결하도록 지원](https://technet.microsoft.com/library/dn818905.aspx)에 설명된 대로 세부적인 VPN 설정을 사용하도록 설정합니다.
* **이제 Android용 OneDrive 앱이 여러 ID를 지원합니다**. 이 업데이트를 포함하여 모바일 앱 관리 정책에 대한 기타 업데이트는 [관리할 수 있는 Microsoft 응용 프로그램의 목록](https://technet.microsoft.com/library/dn708489.aspx)에 설명되어 있습니다.
* **iOS 활성화 잠금 무시**. 활성화 잠금 기능을 통해 회사가 소유한 iOS 장치를 보호하는 경우에는 사용자의 Apple ID와 암호를 입력해야 장치의 데이터를 지우거나 장치를 다시 활성화할 수 있습니다. 따라서 사용자가 퇴사 시에 활성화 잠금을 끄지 않은 상태로 회사가 소유한 장치를 반납하는 경우에는 문제가 발생할 수 있습니다. [Intune 활성화 잠금 무시](https://technet.microsoft.com/library/mt414176.aspx) 기능을 사용하면 이 문제를 해결할 수 있습니다.

### PC에 대한 조건부 액세스
이제 PC에 대한 조건부 액세스 정책을 구성할 수 있습니다. 이 기능을 사용하면 Office 데스크톱 앱이 Exchange Online 및 SharePoint Online 서비스에 액세스할 수 있습니다.
조건부 액세스를 사용하도록 설정하려는 PC는 도메인에 가입되어 있거나 조건부 액세스 정책을 준수해야 합니다.
* PC에 대한 조건부 액세스를 사용하도록 설정하기 위해 필요한 전체 요구 사항 목록은 [Microsoft Intune을 사용한 메일 및 SharePoint 액세스 관리](http://technet.microsoft.com/library/dn818907)의 **시작하기** 섹션을 참조하세요.
* 메일 액세스에 대한 조건부 액세스를 사용하도록 설정할 때 사용할 수 있는 옵션은 [Microsoft Intune으로 메일 액세스 관리](https://technet.microsoft.com/library/dn705841.aspx)를 참조하세요.
* SharePoint Online에 대한 조건부 액세스를 사용하도록 설정할 때 사용할 수 있는 옵션은 [Microsoft Intune으로 SharePoint Online 액세스 관리](https://technet.microsoft.com/library/dn705844.aspx)를 참조하세요.

### Microsoft 회사 포털 앱에 대한 변경 사항 및 업데이트
이 릴리스에서는 회사 포털 앱에 다음과 같은 변경 내용을 적용했습니다.

**Android**

이제는 사용자가 장치를 관리용으로 아직 등록하지 않은 경우 로그인 후에 장치 등록 지침이 표시됩니다.

### Intune 설명서의 새로운 기능 - 2015년 8월
**새 항목**

|제목|세부 정보|
|-----|-------|
|[Microsoft Intune의 활성화 잠금 무시를 사용하여 iOS 장치 보호](https://technet.microsoft.com/library/mt414176.aspx)|사용자가 퇴사하여 잠긴 장치를 반납했을 때 Intune을 사용하여 iOS 활성화 잠금을 해제하는 방법을 알아봅니다.|

**업데이트된 항목**

|제목|세부 정보|
|-----|-------|
|[Microsoft Intune 모바일 응용 프로그램 관리 정책과 함께 사용할 수 있는 Microsoft 앱](https://technet.microsoft.com/library/dn708489.aspx)|모바일 응용 프로그램 관리 정책으로 관리할 수 있는 앱에 대한 내용을 최신 정보로 업데이트했습니다.
|[Microsoft Intune에서 정책을 사용하여 컴퓨터 및 모바일 장치 관리](http://technet.microsoft.com/library/dn743712.aspx)|Intune에 추가된 최신 정책으로 업데이트했습니다.|
<!---
## July 2015
July updates for Intune are limited to behind-the-scenes enhancements that allow us to continue providing you with a high-quality service experience. New features are not included in this service update.

### Intune Onboarding benefit
Microsoft offers the Intune Onboarding benefit for eligible plans. The Onboarding benefit lets you work remotely with Microsoft specialists to get your Intune environment ready for use. For more information, see [Microsoft Intune Onboarding benefit description](https://technet.microsoft.com/library/mt228266.aspx)
### Changes and updates to Microsoft Company Portal apps
The following changes have been made to the company portal apps in this release.

**Android**

Microsoft automatically collects anonymous data about the performance and use of the company portal to improve Microsoft products and services. End users can turn off data collection by using the Usage Data setting on their device, but administrators have no control over the data collection and cannot change the end user’s selection for this setting.--->



<!--HONumber=Sep16_HO5-->


