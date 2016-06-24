---
# required metadata

title: 이전 릴리스 | Microsoft Intune
description:
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 45dad14a-d412-488d-bb1e-ad990ea503df

# optional metadata

ROBOTS: noindex,nofollow
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# 이전 Intune 릴리스
## 2016년 3월
### 2016년 3월 29일 기준 새로운 기능
Windows 10 일반 구성 정책으로 업데이트를 제외하고, 2016년 3월 29일에 릴리스된 모든 기능이 하이브리드 고객에 대해서도 지원됩니다(Configuration Manager가 Intune과 통합됨). Windows 10 일반 구성 정책 업데이트를 위한 하이브리드 지원도 곧 제공됩니다. 이러한 기능 중 일부에는 최신 버전의 Configuration Manager가 필요할 수 있습니다.

### 앱 관리
- **Outlook 연락처 동기화를 방지하기 위한 MAM 컨트롤(iOS).** 장치 등록 없이 새 설정을 모바일 응용 프로그램 관리에 사용할 수 있습니다. 이 설정을 통해 응용 프로그램이 iOS 장치의 기본 주소록에 대해 연락처를 동기화하는 것을 방지할 수 있습니다. 이 설정을 사용하는 경우 앱에서 연락처를 기본 주소록에 더 이상 저장할 수 없게 됩니다. 이 설정을 사용하지 않는 경우 앱에서 연락처를 기본 주소록에 저장할 수 있게 됩니다. 장치를 선택적으로 초기화하는 경우 기본 주소록에 이미 저장되어 있는 모든 연락처가 제거됩니다. 이 새로운 설정은 iOS 장치의 Outlook 응용 프로그램에서 지원됩니다. 이 내용과 기타 설정에 대한 자세한 내용은 [MAM 정책 만들기 및 배포](https://technet.microsoft.com/en-us/library/dn292747.aspx)를 참조하세요..

### 액세스 제어
- **비즈니스용 Skype Online에서 조건부 액세스를 지원합니다.** 비즈니스용 Skype Online에 대한 조건부 액세스 정책을 설정하여 관리되는 호환 iOS 및 Android 장치에서만 액세스할 수 있습니다. iOS 및 Android에서 비즈니스용 Skype 모바일 앱에 로그인하려고 하는 최종 사용자에게 Intune에 등록하고 로그인을 완료하기 전에 모든 비호환성 문제를 해결해야 한다는 메시지가 표시됩니다. 자세한 내용은 [비즈니스용 Skype Online에 대한 액세스 관리](https://technet.microsoft.com/en-us/library/mt695297.aspx)를 참조하세요..

### 장치 관리
- **iOS 9.3에 대한 Intune 지원.** 3월 21일 월요일, Apple은 iOS 9.3의 가용성을 발표했습니다. Microsoft Intune이 최신 버전의 Apple 모바일 운영 체제와 호환되도록 끊임없이 노력해왔으며 [Intune이 iOS 9.3 장치 관리를 지원함을 발표하게 되어 기쁩니다](https://blogs.technet.microsoft.com/microsoftintune/2016/03/23/microsoft-intune-provides-support-for-ios-9-3/)..

  iOS 장치 관리에 사용할 수 있는 기존의 모든 Intune 기능은 사용자가 자신이 장치를 iOS 9.3으로 업그레이드함에 따라 계속해서 원활하게 작동합니다. 또한 오늘 하이브리드 고객에 대해서도 iOS 9.3이 지원됩니다(Configuration Manager가 Intune과 통합됨).

- **Windows 10 일반 구성 정책에는 이제 등록된 Windows 10 PC에서 Windows Defender를 관리하는 설정이 포함됩니다.** 자세한 내용은 [Microsoft Intune의 Windows 10 구성 정책 설정](https://technet.microsoft.com/en-us/library/mt404697.aspx)을 참조하세요..


### 회사 포털

- **Windows 앱 패키지는 회사 포털 웹 사이트에서 직접 사용할 수 있습니다.** 이제 Windows 8, Windows 8.1, Windows RT PC 사용자가 회사 포털 웹 사이트에서 직접 Windows 앱 패키지(.appx 확장명 포함)를 설치할 수 있습니다. 이전에는 직접 배포하거나 사용자가 앱을 설치할 장치에 회사 포털 앱을 설치해야 했습니다.

- **사용자는 회사 포털 웹 사이트에서 장치를 원격으로 잠글 수 있습니다.** 새 원격 잠금 옵션이 회사 포털 웹 사이트에 추가되어 사용자가 장치를 분실하거나 도난당한 경우 포털에서 자신의 장치를 원격으로 잠글 수 있습니다. [최종 사용자 지침](https://technet.microsoft.com/library/mt590895.aspx/?wt.mc_id=ui#BKMK_iwp_remote_lock)을 참조하세요. 다음 표에는 Intune 독립 실행형 및 Configuration Manager 포함 Intune의 원격 잠금에 대한 플랫폼별 지원이 나열되어 있습니다.

|플랫폼 | 지원 세부 정보|
|---------|----------------|
|Android |지원됨|
|iOS |지원됨|
|Windows 10 Mobile |휴대폰에 암호가 설정된 경우에만 지원됨|
|Windows 10 Desktop |지원되지 않음|
|Windows Phone 8.1 |휴대폰에 암호가 설정된 경우에만 지원됨|
|Windows Phone 8.0 |지원되지 않음|
|PC(Windows 8.0 이전 버전) |지원되지 않음|
|PC(Windows 8.1) |지원되지 않음|

### 2016년 3월 10일 기준 새로운 기능

### 앱 관리

- **타사 MDM 솔루션에 등록된 장치에 대해 iOS "다음에서 열기" 관리 활용**
타사 MDM(모바일 장치 관리) 공급업체를 사용하여 IOS "다음에서 열기" 관리를 활용할 수 있습니다. 구성 프로필 설정에서 제한 사항을 설정하고 [iOS 앱 간에 데이터 전송 관리](manage-data-transfer-between-ios-apps-with-microsoft-intune.md)를 사용하여 앱을 배포할 수 있습니다..

     이 방법은 다음과 같은 두 가지 주요 이점이 있습니다.

     1. 사용자가 회사 계정으로 로그인해야 클라우드 서비스 또는 다른 앱에서 회사 데이터에 액세스할 수 있습니다. 이렇게 하면 데이터에 액세스할 때 MAM(모바일 앱 관리) 정책이 적용됩니다.

     2. 관리되는 메일 프로필 및 타사 MDM 솔루션을 통해 배포된 기타 관리되는 앱은 Intune MAM 정책이 있는 앱과 파일 및 데이터를 공유할 수 있습니다.

- **Intune에 등록되지 않은 장치에 대한 MAM 정책을 사용하여 Microsoft Outlook 앱 관리**
이제 Intune 모바일 응용 프로그램 관리 정책을 사용하여 Intune에 등록되지 않은 장치의 Microsoft Outlook 앱을 관리할 수 있습니다. MAM 기능이 있는 업데이트된 Microsoft Outlook 앱은 [iOS](https://itunes.apple.com/us/app/microsoft-outlook-email-calendar/id951937596?mt=8) 및 [Android](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook) 장치 둘 다에 사용할 수 있습니다. [모바일 앱 관리 정책 만들기 및 배포](https://technet.microsoft.com/library/mt627829.aspx) 항목의 지침에 따라 MAM 정책을 만듭니다.  


- **모바일 앱 구성 정책을 사용하면 보다 유연성 있게 iOS 앱에 대한 사용자 세부 정보를 지정할 수 있습니다.**
iOS 앱을 열 때 필요할 수 있는 사용자 설정을 제공할 수 있습니다. 예를 들어 네트워크 포트나 사용자 이름을 제공할 수 있습니다. 자세한 내용은 [Microsoft Intune에서 모바일 앱 구성 정책을 사용하여 iOS 앱 구성](configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune.md)을 참조하세요..


- **엔터프라이즈의 Intune 관리 iOS 장치에 Microsoft Intune용 Adobe Reader 배포**
이제 Intune 모바일 응용 프로그램 관리 정책을 사용하여 등록된 장치에서 iOS용 Adobe Reader 앱을 관리할 수 있습니다.

- **배포된 웹 클립이 Managed Browser에서 열리는지 확인**
iOS 및 Android 장치에서 Managed Browser를 통해서만 열 수 있는 대상 지정 웹 클립을 배포할 수 있습니다. 예를 들어 회사 포털을 통해 회사 리소스에 대한 링크를 배포하면 사용자가 링크로 이동할 때 MAM 정책으로 보호될 수 있는 Managed Browser에서 바로 열립니다. 자세한 내용은 [앱 배포](deploy-apps.md)를 참조하세요..


- **Intune 관리자 콘솔에서 Windows 10 장치에 대한 비즈니스용 Windows 스토어 앱 찾기, 관리 및 배포**
앱을 찾고 관리하고 관리 중인 Windows 10 장치에 배포하는 데 도움이 되는 비즈니스용 Windows 스토어 지원을 Intune에서 사용할 수 있습니다. 비즈니스용 Windows 스토어를 사용하면 Intune 관리자 콘솔(다른 앱 관리에 사용하는 콘솔과 같음)에서 이러한 앱을 배포하고 모니터링하는 과정을 관리할 수 있습니다. 특히, 비즈니스용 Windows 스토어는 "온라인 사용이 허가된 앱"의 콘텐츠와 라이선스를 관리합니다. 자세한 내용은 [비즈니스용 Windows 스토어에서 구입한 앱 관리](manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune.md)를 참조하세요..


### 장치 관리
- **iOS 장치에 대한 PFX 인증서 배포**
Intune 관리자는 iOS 장치에서 Wi-Fi, 메일 및 VPN 인증에 사용되는 iOS PFX 인증서를 만들고 배포할 수 있습니다. Android 및 Windows 10 장치에서는 이 기능을 이미 사용할 수 있습니다. 자세한 내용은 [인증서 프로필을 사용하여 회사 리소스에 대한 액세스 사용](secure-resource-access-with-certificate-profiles.md)을 참조하세요..


- **사용자 범주 선택에 따라 서로 다른 장치 그룹에 앱 및 정책 적용**
이제 Intune 관리자가 등록 중에 사용자가 선택하는 사용자 지정 장치 범주를 정의할 수 있습니다. 예를 들어 관리자는 사용자가 "현금 등록기", "배달 트럭" 또는 "인벤토리 공간"에 사용되는 장치를 등록할지 여부를 지정할 수 있습니다. 선택한 범주에 따라 장치는 등록된 장치에 다른 앱과 정책을 배포하는 데 사용될 수 있는 Intune 장치 그룹의 구성원이 됩니다. 자세한 내용은 [장치 그룹 매핑을 사용하여 장치 분류](categorize-devices-with-device-group-mapping-in-microsoft-intune.md)를 참조하세요..

### Microsoft 회사 포털에 대한 변경 사항 및 업데이트
이 릴리스에서는 회사 포털에 다음과 같은 변경 내용을 적용했습니다.

**Android 회사 포털 앱**

* 사용자가 MAM(모바일 응용 프로그램 관리)에서 관리되는 앱을 시작하면 앱이 회사에서 관리됨을 알리는 메시지가 나타납니다. 이제 사용자가 “자세한 정보” 링크를 탭하여 여기서 “관리되는 앱”이 의미하는 바에 대한 [자세한 내용](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_use_mgd_apps)을 확인할 수 있습니다. 앱을 시작할 때 메시지가 더 이상 표시되지 않도록 "다시 표시 안 함"을 탭할 수도 있습니다.
* 사용자에게 등록 과정을 안내하고 사용자가 등록해야 이유 및 IT 관리자가 등록 된 장치에서 볼 수 있는 사항과 볼 수 없는 사항에 대한 자세한 정보를 제공하는 새 화면이 추가되었습니다. 자세한 내용은 [등록 지침](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_enroll_devc)을 참조하세요.
* 이제 등록 오류 메시지가 회사 포털 앱에 표시됩니다. 이전에는 이러한 메시지가 회사 포털 웹 사이트에 표시되었습니다. 이러한 변경은 두 개의 장소가 아니라 한 장소에 모든 오류 메시지가 표시됨을 의미합니다.


**iOS 회사 포털 앱**
* 사용자가 MAM(모바일 응용 프로그램 관리)에서 관리되는 앱을 시작하면 앱이 회사에서 관리됨을 알리는 메시지가 나타납니다. 이제 사용자가 “자세한 정보” 링크를 탭하여 여기서 “관리되는 앱”이 의미하는 바에 대한 [자세한 내용](https://technet.microsoft.com/library/mt598622.aspx#BKMK_ios_use_mgd_apps)을 확인할 수 있습니다. 앱을 시작할 때 메시지가 더 이상 표시되지 않도록 "다시 표시 안 함"을 탭할 수도 있습니다.
* 사용자에게 등록 과정을 안내하고 사용자가 등록해야 이유 및 IT 관리자가 등록 된 장치에서 볼 수 있는 사항과 볼 수 없는 사항에 대한 자세한 정보를 제공하는 새 화면이 추가되었습니다. 자세한 내용은 [등록 지침](https://technet.microsoft.com/library/mt598622.aspx#BKMK_enroll_ios_device)을 참조하세요.
* 이제 등록 오류 메시지가 회사 포털 앱에 표시됩니다. 이전에는 이러한 메시지가 회사 포털 웹 사이트에 표시되었습니다. 이러한 변경은 두 개의 장소가 아니라 한 장소에 모든 오류 메시지가 표시됨을 의미합니다.




## 2016년 2월
### Microsoft 회사 포털에 대한 변경 사항 및 업데이트

이 릴리스에서는 회사 포털에 다음과 같은 변경 내용을 적용했습니다.

#### Android 회사 포털 앱
- 사용자에게 등록 과정을 안내하고 사용자가 등록해야 이유 및 IT 관리자가 등록 된 장치에서 볼 수 있는 사항과 볼 수 없는 사항에 대한 자세한 정보를 제공하는 새 화면이 추가되었습니다. 자세한 내용은 [등록 지침](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_enroll_devc)을 참조하세요.
- 이제 등록 오류 메시지가 회사 포털 앱에 표시됩니다. 이전에는 이러한 메시지가 회사 포털 웹 사이트에 표시되었습니다. 이러한 변경은 두 개의 장소가 아니라 한 장소에 모든 오류 메시지가 표시됨을 의미합니다.

#### iOS 회사 포털 앱
 - 사용자에게 등록 과정을 안내하고 사용자가 등록해야 이유 및 IT 관리자가 등록 된 장치에서 볼 수 있는 사항과 볼 수 없는 사항에 대한 자세한 정보를 제공하는 새 화면이 추가되었습니다. 자세한 내용은 [등록 지침](https://technet.microsoft.com/library/mt598622.aspx#BKMK_enroll_ios_device)을 참조하세요.

 - 이제 등록 오류 메시지가 회사 포털 앱에 표시됩니다. 이전에는 이러한 메시지가 회사 포털 웹 사이트에 표시되었습니다. 이러한 변경은 두 개의 장소가 아니라 한 장소에 모든 오류 메시지가 표시됨을 의미합니다.


## 2016년 1월

### Windows 10 기능 활용
* **상태 증명 서비스를 사용한 조건부 액세스**
이제 Intune 관리자가 Intune 관리 콘솔에서 Windows 10 장치 상태 증명의 상태를 볼 수 있습니다. 장치 상태 증명을 사용하여 관리자는 클라이언트 컴퓨터가 신뢰할 수 있는 BIOS, TPM 및 소프트웨어 구성을 갖는지 확인할 수 있습니다. 장치 상태 증명을 지원하려면 클라이언트 장치에서 TPM 2가 설정된 Windows 10이 실행되고 있어야 합니다. 장치 상태 증명은 다음 각각에 대해 사용하도록 설정된 장치 수를 표시합니다.
    * 맬웨어 방지 조기 실행
    * BitLocker
    * 보안 부팅
    * 코드 무결성

    장치 상태 설정, 수집되는 데이터 요소 및 상태 증명 보고서에 대한 자세한 내용은 [Microsoft Intune에 대한 장치 규정 준수 정책 소개](introduction-to-device-compliance-policies-in-microsoft-intune.md)를 참조하세요. [HAS 서비스 정보](https://msdn.microsoft.com/en-us/library/dn934876.aspx)에서는 서비스에 대해 자세히 설명합니다.

* **Windows 10 Passport for Work 정책 및 인증서 관리**
Intune에서는 Active Directory 또는 Azure Active Directory 계정을 사용하여 암호, 스마트 카드 또는 가상 스마트 카드를 대신하는 Windows 10의 대체 로그인 방법인 [Microsoft Passport for Work와 통합](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md)할 수 있습니다. Passport를 사용하면 암호 대신 사용자 제스처를 사용하여 로그인할 수 있습니다. 사용자 제스처는 단순 PIN, 생체 인식 인증(예: Windows Hello) 또는 외부 장치(예: 지문 판독기)일 수 있습니다.

* **특정 앱에 대한 VPN**
VPN을 통해 자동으로 회사 네트워크에 연결하는 앱을 선택할 수 있습니다. 사용자가 Microsoft Intune에서 VPN 프로필을 사용하여 회사에 연결하도록 지원에 설명된 대로 VPN 프로필을 설정할 때 앱 목록을 만듭니다.

* **Windows 10 전체 초기화 지원**
이제 Intune 관리 콘솔을 통해 Intune에 등록된 Windows 10 Desktop 장치의 원격 전체 초기화를 실행할 수 있습니다. Windows 10 전체 초기화는 장치를 공장 기본 설정으로 되돌립니다.


### Apple VPP(대량 구매 프로그램) 업데이트
이제 Intune에서 [Apple 비즈니스용 VPP(대량 구매 프로그램)를 통해 구입한 앱의 관리](manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune.md)를 도와줍니다. 여기에는 Apple과 Intune 간의 라이선스 정보 동기화와 배포한 각 앱의 복사본 수 추적이 포함됩니다.

### IMEI 번호를 사용하여 회사 소유의 장치 식별
이제 회사 소유의 모바일 장치를 식별하는 데 도움이 되는 IMEI 번호가 있는 모바일 장치 플랫폼에 대해 [IMEI(International Mobile Equipment Identity) 번호를 가져올](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md) 수 있습니다. Intune에 등록되고 나면 가져온 IMEI 번호가 있는 장치에는 회사 태그가 지정되며, 이 태그를 사용하여 개인 소유 장치에 적용되는 정책과 다른 정책을 적용할 수 있습니다.

### 이제 더 많은 앱이 Intune MAM 정책과 호환됨
이제 Microsoft 파트너의 추가 앱이 Intune MAM(모바일 응용 프로그램 관리) 정책과 호환됩니다(Intune에서 관리되는 장치의 경우).
* Box for EMM(Box Inc) – iOS에만 해당
* Adobe Reader(Adobe) – Android에만 해당
* Foxit PDF Reader(Foxit Corporation) – iOS 및 Android


### IE9 지원이 1월에 종료됨
Internet Explorer 9는 2016년 2월부터 더 이상 Microsoft Intune 회사 포털 웹 사이트, Intune 계정 포털 및 Intune 관리 콘솔에 액세스하기 위한 공식 브라우저로 지원되지 않습니다. Internet Explorer 10 이상으로 마이그레이션해야 합니다.

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
메시지의 의미     |  사용자의 장치 전화 번호 및 IMEI를 Intune 서비스로 보내고 관리 콘솔의 [하드웨어] 페이지에 표시할 수 있도록 합니다.   </br></br>**참고: 회사 포털 앱은 전화를 걸거나 전화 통화를 관리하지 않습니다.** 메시지 텍스트는 Google에서 제어하므로 변경할 수 없습니다. </br></br>**하드웨어 페이지**를 표시하려면 **그룹** > **모든 모바일 장치** > **장치**로 이동합니다. 사용자의 장치를 선택하고 **속성 보기** > **하드웨어**로 이동합니다..    
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
* Apple의 DEP(장치 등록 프로그램) 및 회사에 등록된 장치에 대한 지원이 향상되었습니다. 자세한 내용은 [등록할 때 장치를 식별하도록 요청](https://technet.microsoft.com/library/mt598622.aspx#BKMK_ios_id_your_device)을 참조하세요..
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
* Office 모바일 앱, Intune SDK를 채택한 타사 앱 또는 Intune에 의해 래핑된 LOB(기간 업무) 앱을 포함하여 Intune 지원 앱 내에서 회사 데이터는 소비자 데이터로부터 격리됩니다.
* 회사 데이터가 개인 앱에 공유되지 않도록 차단하는 동시에 회사 앱 간에 회사 데이터를 공유할 수 있습니다(**잘라내기/복사/붙여넣기**). 자세한 내용은 [MAM 정책이 앱 데이터를 보호하는 방법](https://technet.microsoft.com/library/mt627825.aspx)을 참조하세요. 이 예제 시나리오 [회사 및 개인 작업에 Microsoft Word 앱 사용](https://technet.microsoft.com/library/mt627827.aspx)에서는 회사 데이터가 개인 앱에 공유되지 않도록 하는 방법을 보여 줍니다.
* 앱별 PIN, 다른 이름으로 저장 컨트롤, 앱 간의 관리되는 데이터 공유 등의 주요 데이터 손실 방지 정책. 모든 정책 목록을 보려면 [Microsoft Intune으로 모바일 앱 관리 정책 만들기 및 배포](https://technet.microsoft.com/library/mt627829.aspx)를 참조하세요.
* Word, Excel, PowerPoint, Outlook, OneNote 및 비즈니스용 OneDrive에는 모두 이러한 새로운 기능이 있으며 장치 등록 여부에 관계없이 관리할 수 있습니다. 데이터 손실 방지 기능은 Apple 스토어 또는 Google Play 스토어의 표준 Office 앱에 기본적으로 제공되며 앱 래핑이나 테스트용으로 로드할 필요가 없습니다.
* 시작하는 방법에 대한 자세한 내용은 [Azure 포털에서 모바일 앱 관리 정책 시작](https://technet.microsoft.com/library/mt627830.aspx)을 참조하세요. 모바일 앱 관리 정책을 구성하고 배포하는 방법에 대한 자세한 내용은 [Microsoft Intune으로 모바일 앱 관리 정책 만들기 및 배포](https://technet.microsoft.com/library/mt627829.aspx)를 참조하세요..
* 최종 사용자가 회사 자격 증명으로 앱을 인증하는 경우 데이터 손실 방지 기능이 자동으로 설정됩니다. [Microsoft Intune 모바일 앱 관리 정책과 연결된 앱에 대한 최종 사용자 환경](https://technet.microsoft.com/library/mt627827.aspx) 항목에는 iOS 및 Android 장치에서 OneDrive에 액세스하기 위한 몇 가지 예제 시나리오가 포함되어 있습니다.
* iOS 및 Android 장치 둘 다에서 작동합니다.

[Microsoft Intune 모바일 응용 프로그램 관리 정책과 함께 사용할 수 있는 Microsoft 앱](https://technet.microsoft.com/library/dn708489.aspx) 목록이 최신 앱을 표시하도록 업데이트되었습니다.

### 장치 관리
 **Mac OS X 장치 관리**
이제 Intune을 사용하여 Mac OS X 장치를 등록하고 관리할 수 있습니다. Mac OS X 장치에서 다음을 수행할 수 있습니다.
* Intune에서 관리할 장치를 등록합니다. [Microsoft Intune을 사용한 iOS 및 Mac 관리 설정](https://technet.microsoft.com/library/dn408185.aspx)을 참조하세요..
* 일반 구성 정책을 사용하여 장치 설정을 제어합니다. [Microsoft Intune의 Mac OS X 구성 정책 설정](https://technet.microsoft.com/library/mt627823.aspx)을 참조하세요..
* Apple Configurator를 사용하여 만든 Mac OS X 설정을 배포합니다. [Microsoft Intune의 Mac OS X 사용자 지정 정책 설정](https://technet.microsoft.com/library/mt627820.aspx)을 참조하세요..
* Mac OS X 장치에서 하드웨어 및 소프트웨어 인벤토리를 수집합니다. [Microsoft Intune에서 인벤토리를 사용하는 장치 이해](https://technet.microsoft.com/library/jj733634.aspx)를 참조하세요..
* 관리하는 Mac OS X 장치에 대한 세부 정보를 표시하는 새 보고서를 실행합니다. [보고서를 사용하는 Microsoft Intune 작업 이해](https://technet.microsoft.com/library/dn646977.aspx)를 참조하세요..

**Windows 10 장치에 대한 새 Edge 브라우저 설정**
Microsoft Edge 브라우저의 설정과 기능을 관리할 수 있도록 해주는 새로운 설정이 Windows 10 일반 구성 정책에 추가되었습니다. [Microsoft Intune의 Windows 10 구성 정책 설정](https://technet.microsoft.com/library/mt404697.aspx)을 참조하세요..

**전자 메일 프로필**
Windows 10 Desktop 및 Windows 10 Mobile 장치에 대한 새로운 메일 프로필 정책이 추가되었습니다. [Microsoft Intune 정책을 사용하여 장치의 설정 및 기능 관리](https://technet.microsoft.com/library/dn646984.aspx)를 참조하세요..

**새로운 준수 정책 설정**
다음과 같은 새 보안 및 시스템 정책 설정이 준수 정책 목록에 추가되었습니다.
* 회사 리소스에 액세스하는 Windows 8.1 이상 장치에 최신 업데이트가 설치되어 있는지 확인하려면 **자동 업데이트 필요** 설정을 사용합니다. 자동으로 설치되는 업데이트 유형(중요로 표시된 모든 업데이트 또는 중요나 권장으로 표시된 모든 업데이트)을 지정할 수도 있습니다. 준수 정책 설정의 전체 목록은 [Microsoft Intune에 대한 장치 정책 준수 정책 관리](https://technet.microsoft.com/library/dn705843.aspx)를 참조하세요..
* 새로운 **장치가 유휴 상태에서 되돌아오는 경우 암호 필요** 설정을 기존의 **암호를 요구하기 전까지 비활성 시간(분)** 설정과 함께 사용하면 최종 사용자가 일정 시간 동안 비활성 상태인 장치를 사용하기 위해 암호를 입력해야 하는 준수 설정을 만들 수 있습니다.

**새 조건부 액세스 정책 옵션**
기존 또는 새 조건부 액세스 정책에서 **모든 사용자**에게 조건부 액세스 정책을 적용할 수 있습니다. Intune 및 Office 365 사용이 허가된 모든 사용자는 장치를 등록해야 하며, 장치 플랫폼이 Intune에서 지원되지 않는 경우 [Active Directory 인증 기반 로그인(최신 인증)](https://blogs.office.com/2014/11/12/office-2013-updated-authentication-enabling-multi-factor-authentication-saml-identity-providers/)을 사용하는 클라이언트 응용 프로그램에 대해 액세스가 차단됩니다..

**모든 플랫폼**에 조건부 액세스 정책에 적용되도록 지정할 수도 있습니다.  [Active Directory 인증 기반 로그인(최신 인증)](https://blogs.office.com/2014/11/12/office-2013-updated-authentication-enabling-multi-factor-authentication-saml-identity-providers/)을 사용하는 모든 클라이언트 응용 프로그램에 조건부 액세스 정책이 적용되며, 플랫폼이 Intune에서 지원되지 않는 경우 차단됩니다.

### Microsoft 회사 포털에 대한 변경 사항 및 업데이트
이 릴리스에서는 회사 포털 앱에 다음과 같은 변경 내용을 적용했습니다.

* **Android**: 사용자가 회사 포털 앱의 용도를 이해하는 데 도움이 되는 시작 화면이 Android 회사 포털 앱에 추가되었습니다. 이 화면은 회사가 Intune 구독자가 아닌 사용자의 앱 다운로드를 줄이기 위한 것입니다.

* **iOS**: 이제 Intune에서 [회사 포털 웹 사이트](https://portal.manage.microsoft.com)를 사용하여 Mac OS X 장치를 등록할 수 있습니다. 지침은 [Intune에서 Mac OS X 장치 등록](https://technet.microsoft.com/library/mt598622.aspx)을 참조하세요..

* **회사 포털 웹 사이트**: Intune에서 장치를 등록한 사용자는 이제 회사 포털 웹 사이트에서 **암호 초기화** 옵션을 사용하여 암호를 초기화할 수 있습니다. 이전에는 IT 관리자만 사용자 암호를 초기화할 수 있었습니다. [암호 초기화] 옵션은 Windows 8.1 및 Windows RT 장치에서는 지원되지 않으며 MDM(모바일 장치 관리) 또는 Exchange ActiveSync를 사용하는 MDM에서 장치를 등록할 때만 표시됩니다. 사용자 지침은 [암호 재설정](https://technet.microsoft.com/library/mt590895.aspx)을 참조하세요..

### 전역 관리자 라이선싱 변경
10월에 전역 관리자(테넌트 관리자라고도 함)는 별도의 Intune 또는 EMS(Enterprise Mobility Suite) 라이선스 없이 일상적인 관리 작업을 계속 수행할 수 있다고 발표했습니다. 그러나 전역 관리자가 자신의 장치나 회사 장치 등록 또는 Intune 회사 포털 사용 등의 서비스를 사용하려는 경우 다른 사용자와 마찬가지로 Intune 또는 EMS 라이선스가 필요합니다. 몇 가지 추가 정보는 다음과 같습니다.
* Intune 회사 포털에서 최종 사용자는 다음 작업을 수행할 수 있습니다.
    * 장치 등록
    * 장치 상태 보기
    * 전역 관리자가 조직에 배포한 소프트웨어 다운로드
    * 전역 관리자가 해당 IT 부서에 연락하는 방법에 대해 게시한 링크 찾기

    [회사 포털](https://technet.microsoft.com/library/dn646966.aspx#BKMK_CompanyPortal) 및 [회사 포털을 사용자 지정하는 방법](https://technet.microsoft.com/library/dn646983.aspx#BKMK_ConfigureCompanyPortal)에 대해 자세히 알아보세요..
* 조직을 대신해 Intune 또는 EMS를 구입하기 위해 등록한 사람이 자동으로 테넌트의 첫 번째 전역 관리자가 됩니다. 금년 가을에 Intune은 [Office 365 포털](http://portal.office.com/)로 이동하고 [Intune 계정 포털](http://account.manage.microsoft.com/)의 사용을 중지하는 과정의 일환으로 첫 번째 전역 관리자에게 Intune 또는 EMS 라이선스를 자동으로 할당하기 시작했습니다. 추가된 모든 전역 관리자는 별도의 Intune 또는 EMS 라이선스 없이 일상적인 관리 작업을 계속 수행할 수 있습니다. 최종 사용자 역할을 하고 자신의(또는 회사) 장치를 등록하거나 회사 포털에서 소프트웨어를 다운로드하는 경우에는 다른 사용자와 마찬가지로 라이선스가 필요합니다.
* 변경 내용은 단계적으로 도입되며, 이제 2016년 1월에 시작됩니다.
* Microsoft 파트너의 경우 이 변경은 고객을 대신해 서비스를 관리하는 능력에 영향을 주지 않습니다. 최종 사용자 작업의 경우 사용자가 장치를 등록하고 회사 포털에서 소프트웨어를 액세스하거나 다운로드하려면 Intune 또는 EMS 라이선스가 있어야 합니다.

이 변경에 대한 질문이 있으면 언제든지 Intune 지원 팀에 문의하세요.
* [Microsoft Intune 지원 채널](https://technet.microsoft.com/library/jj839713.aspx)
* [커뮤니티 지원](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod)

DCR(디자인 변경 요청) 또는 버그 신고를 포함하여 일반적인 Microsoft Intune 피드백이 있을 경우 [Intune 사용자 의견](https://microsoftintune.uservoice.com/)을 방문하세요..


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
**이제 전역 Exchange 규칙이 차단 또는 격리로 설정되면 Intune에 등록된 규격 장치에 대해 Exchange Active Sync 메일 액세스를 허용할 수 있습니다.** 지금까지는 등록된 규격 장치에서 메일 액세스를 허용하기 위해 기본 전역 Exchange 규칙을 **허용**으로 설정해야 했습니다..

이 서비스 업데이트를 사용하면 이 설정이 더 이상 조건부 액세스에 대한 요구 사항이 아닙니다. Exchange 환경에서 기본 전역 규칙을 **차단/격리**로 설정해야 할 경우, Exchange 온-프레미스 조건부 액세스 정책 페이지에서 간단히 **기본 규칙보다 우선** 확인란을 선택합니다. [Microsoft Intune으로 메일 액세스 관리](https://technet.microsoft.com/library/dn705841.aspx) 항목에는 규칙 및 결과 최종 사용자 알림에 대한 자세한 내용이 포함되어 있습니다.

**새로운 원클릭 격리 환경** 원클릭 등록을 허용하도록 격리 메일 환경이 간소화되었습니다. 이 서비스 업데이트를 사용하는 최종 사용자는 격리 메일에 있는 하나의 링크를 클릭하여 회사 포털 앱 내에서 등록 프로세스를 완료할 수 있습니다.
### 모바일 장치 및 앱 관리 기능 업데이트
**Android** 이제 모든 Intune 관리 기능이 블로그 게시물 [Microsoft Intune에서 Android Marshmallow에 대한 Day 0 지원 제공](http://blogs.technet.com/b/microsoftintune/archive/2015/10/09/microsoft-intune-to-provide-day-0-support-for-android-marshmallow.aspx)에 설명된 대로 Android 6.0(Marshmallow)을 지원합니다.

**iOS** iOS 7.1 이전 버전을 실행하는 iOS 장치에 대한 새로운 앱 배포를 더 이상 만들 수 없습니다. iOS 7.1의 이전 버전을 실행하는 장치에 대한 모든 기존 앱 배포는 Intune으로 계속 작동 및 관리됩니다.

**Windows 10** 이제 Intune에서 **Windows 앱 패키지** 소프트웨어 설치 관리자 유형을 사용한 Windows 10 유니버설 앱 배포를 지원합니다. 자세한 내용과 요구 사항은 [Microsoft Intune으로 앱 배포 시작하기](http://technet.microsoft.com/en-US/library/dn646955.aspx)를 참조하세요..


### Microsoft 회사 포털 앱에 대한 변경 사항 및 업데이트
이 릴리스에서는 회사 포털 앱에 다음과 같은 변경 내용을 적용했습니다.
**iOS**
사용자가 자신의 IT 관리자에게 진단 로그를 더 쉽게 보낼 수 있도록 새 단추가 회사 포털 앱에 추가되었습니다.

|단추 이름|표시되는 곳|
|------------|---------------|
|보고서|오류 경고 메시지|
|진단 보고서 보내기|회사 포털 앱의 정보 화면|


>[!div class="step-by-step"]

>[&larr; **Intune의 새로운 기능**](whats-new-in-microsoft-intune.md)    


<!--HONumber=May16_HO1-->


