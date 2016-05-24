---
# required metadata

title: 새로운 기능 아카이브 | Microsoft Intune
description:
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: ed2db991-4729-49a7-a1e6-be2ffa0d03d1

# optional metadata

ROBOTS: noindex,nofollow
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


## 2015년 9월
### 모바일 장치 및 앱 관리 기능 업데이트
**이제 모든 Intune iOS 관리 기능이 iOS 9를 지원합니다.**
iOS 9 관리 기능에 대한 자세한 내용은 [이 블로그 게시물](http://blogs.technet.com/b/microsoftintune/archive/2015/09/09/day-zero-support-for-ios-9-with-intune.aspx)을 참조하세요..

**iOS에 대한 새로운 모바일 앱 구성 정책**
새 모바일 앱 구성 정책을 사용하여 iOS 앱이 실행될 때 이 앱에서 필요로 할 수 있는 설정을 자동으로 제공합니다. 예를 들어 네트워크 포트나 사용자 이름을 제공할 수 있습니다. 자세한 내용은 [Microsoft Intune에서 모바일 앱 구성 정책을 사용하여 앱 구성](https://technet.microsoft.com/library/mt481447.aspx)을 참조하세요..

**IOS 9 사용자를 위한 보다 쉬운 앱 관리**
 이 릴리스에서 iOS 9 사용자를 위한 Intune 관리 아래에서 이미 배포된 앱을 가져올 수 있습니다. 이전 버전 iOS에서는 앱을 배포할 때 관리되지 않는 버전의 앱이 이미 장치에 설치되어 있으면 Intune에서 관리되는 앱을 설치하기 전에 사용자에게 수동으로 해당 앱을 제거해 달라고 요청해야 했습니다.

 하지만 Intune의 이번 릴리스에서는 이제 iOS 9 장치 사용자에게 Intune에서 앱을 관리하고 모든 관련 모바일 응용 프로그램 관리 정책을 적용하는 것을 허용하도록 확인할 수 있습니다.

 **Windows 10 관리** 새로운 [Windows 10 일반 구성 정책](https://technet.microsoft.com/library/mt404697.aspx)을 사용하여 Windows 10 및 Windows 10 Mobile을 실행하는 등록된 장치에 대한 암호, 장치, 브라우저 및 기타 설정을 구성합니다.

 **앱 만들기 및 등록된 Windows 10 장치에 배포** 새로운 소프트웨어 설치 관리자인 MDM(&#42;.msi)을 통한 Windows Installer를 사용하면 Windows Installer 앱을 만들고 Windows 10을 실행하는 등록된 장치에 배포할 수 있습니다. 자세한 내용은 [Microsoft Intune으로 앱 배포 시작하기](https://technet.microsoft.com/library/dn646955.aspx)를 참조하세요..

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
* **몇 가지 Intune 정책의 이름이 변경** 되어 제품 전체에서 일관성있고 찾기 쉽게 되었습니다. 사용 가능한 모든 Intune 정책 목록은 [Microsoft Intune에서 정책을 사용하여 컴퓨터 및 모바일 장치 관리](https://technet.microsoft.com/library/dn743712.aspx)를 참조하세요..
* **PKCS #12(.PFX) 인증서 프로필**은 Android 4.0 이상, Windows 10(데스크톱 및 모바일) 이상에서 사용할 수 있습니다. .PFX 사용에 NDES 서버는 필요하지 않습니다. [인증서 프로필을 사용하여 회사 리소스에 대한 액세스 사용](http://technet.microsoft.com/library/dn818904.aspx)에서 .PFX 인증서 프로필을 사용하는 방법을 알아봅니다.
* **Windows 10 Desktop 및 Mobile의 회사 경계 설정**에서는 [사용자가 Microsoft Intune에서 VPN 프로필을 사용하여 회사에 연결하도록 지원](https://technet.microsoft.com/library/dn818905.aspx)에 설명된 대로 세부적인 VPN 설정을 사용하도록 설정합니다.
* **이제 Android용 OneDrive 앱이 여러 ID를 지원합니다**. 이 업데이트를 포함하여 모바일 앱 관리 정책에 대한 기타 업데이트는 [관리할 수 있는 Microsoft 응용 프로그램의 목록](https://technet.microsoft.com/library/dn708489.aspx)에 설명되어 있습니다..
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


<!--HONumber=May16_HO1-->


