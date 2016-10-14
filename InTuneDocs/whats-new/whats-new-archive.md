---
title: "새로운 기능 아카이브 | Microsoft Intune"
description: 
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 10/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ed2db991-4729-49a7-a1e6-be2ffa0d03d1
ROBOTS: noindex,nofollow
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ec77bc20bf429c804cb502bb46fc549d080a94ac
ms.openlocfilehash: 14698e5f40e76e370e178aeb6187d89fbc5cb2bd


---
## 2016년 9월
## 새로운 기능, 공지 사항 및 정보
* [Windows 조건부 액세스](#windows-conditional-access)
* [iOS 10 지원](#ios-10-support)
* [앱 래핑 도구는 Android 및 iOS에 대한 장치 등록 없이 MAM 지원](#app-wrapping-tool-supports-mam-without-device-enrollment-for-android-and-ios)
* [9월에 Intune 그룹에서 Azure Active Directory로 전환 시작](#intune-groups-begin-transitioning-to-azure-active-directory-in-september)
* [Android 장치를 보호하기 위한 Lookout 통합](#lookout-integration-to-protect-android-devices)
* [Android, iOS 및 Windows용 회사 포털 업데이트](#company-portal-updates)
* [Intune 용어](#intune-glossary)
* [향후 예정 사항](#whats-coming)

## Windows 조건부 액세스
이제 Intune 관리 콘솔을 통해 Windows PC가 Exchange Online 및 SharePoint Online에 액세스하지 못하도록 하는 조건부 액세스 정책을 만들 수 있습니다. 또한 Office 데스크톱 및 유니버설 응용 프로그램에 대한 액세스를 차단하기 위한 조건부 액세스 정책을 만들 수 있습니다.

## iOS 10 지원
기존 Intune MDM 및 MAM 시나리오는 iOS 10과 호환됩니다. 팁은 [Intune Support Team Blog](https://blogs.technet.microsoft.com/intunesupport/2016/09/13/support-tip-intune-support-for-ios-10/)(Intune 지원 팀 블로그)를 참조하세요.

## 앱 래핑 도구는 Android 및 iOS에 대한 장치 등록 없이 MAM 지원
Intune 앱 래핑 도구는 iOS 및 Android용 LOB(기간 업무) 앱에서 Intune MAM을 사용하도록 설정하는 데 사용하는 명령줄 도구입니다. Intune을 통해 배포된 MAM 정책을 앱에서 적용할 수 있도록 앱에 Intune MAM SDK를 통합하는 가장 간단한 방법입니다. MAM 정책을 사용하여 다음을 수행할 수 있습니다.

1. 응용 프로그램의 데이터를 암호화합니다.
2. 정보 근로자가 앱을 시작할 때 PIN을 입력하도록 요구합니다.
3. 앱에서 다른 관리되는 앱으로만 데이터를 전송하도록 허용합니다.
4. 앱에서 데이터를 Android, iTunes 및 iCloud에 백업하지 못하게 합니다.
5. 다른 관리되는 앱으로 또는 이 앱에서 잘라내기, 복사 및 붙여넣기만 허용합니다.

업데이트된 Intune 앱 래핑 도구의 공개 미리 보기에서는 이제 iOS 및 Android의 내부 LOB 앱에서 장치 등록 없이도 MAM를 지원합니다. 즉, 최종 사용자가 장치를 Intune에 등록하지 않고도 MAM 지원 LOB 앱을 사용할 수 있습니다.

누구나 공개 미리 보기 소프트웨어를 테스트하고 msintuneappsdk의 GitHub에 있는 유용한 설명서를 읽을 수 있습니다.

http://www.github.com/msintuneappsdk/intune-app-wrapper-ios-preview

http://www.github.com/msintuneappsdk/intune-app-wrapper-android-preview

Android 및 iOS용 Microsoft Intune 앱 래퍼 시험판을 설치하고 사용하기 전에 다음을 수행해야 합니다.

* Android 및 iOS용 Microsoft Intune 앱 래퍼 시험판에 대한 Microsoft 사용 조건 검토
* 기록을 위해 사용 조건의 사본을 인쇄하여 보관. Android용 Microsoft Intune 앱 래핑 도구 시험판을 다운로드하고 사용하면 이러한 사용 조건에 동의하는 것입니다. 동의하지 않는 경우 소프트웨어를 사용하지 마세요.
<!---TFS 1235607--->

## 9월에 Intune 그룹에서 Azure Active Directory로 전환 시작
일부 새 Intune 계정은 Intune 사용자 그룹이 아닌 Azure Active Directory 보안 그룹을 사용합니다. Intune 포털 그룹 페이지에 Azure 관리 포털로 연결되는 링크가 있으면 보안 그룹을 사용 중인 것입니다.

## Android 장치를 보호하기 위한 Lookout 통합
Microsoft는 Android 장치에서 맬웨어, 위험한 앱 등을 감지하여 장치를 보호하기 위해 Lookout의 모바일 위협 방지 솔루션과 통합합니다. Lookout의 솔루션을 통해 위협 수준을 결정할 수 있고, 이 수준은 구성이 가능합니다. Lookout의 위협 평가를 기준으로 장치 준수를 결정하는 준수 정책 규칙을 Intune에서 만들 수 있습니다. 조건부 액세스 정책을 사용하여 장치 준수 상태에 따라 회사 리소스에 대한 액세스를 허용하거나 차단할 수 있습니다.

비준수 장치의 최종 사용자는 등록하라는 메시지가 표시되며 Android 장치에서 Lookout for Work 응용 프로그램을 설치하고, 앱을 활성화하고, Lookout for Work 응용 프로그램에 보고된 위협을 해결해야만 액세스 권한을 얻게 됩니다. 자세한 내용은 [Restrict access based on device, network, and application risk](restrict-access-based-on-device-network-app-risk.md)(장치, 네트워크 및 응용 프로그램 위험에 따라 액세스 제한)를 참조하세요.


## 회사 포털 업데이트

### Android

**Android용 회사 포털에 “알림” 추가**<br/>
홈페이지의 Android용 회사 포털에 새 알림 아이콘이 추가되었습니다. 이 아이콘을 누르면 호환되지 않는 장치, 등록 업데이트 및 등록 활성화와 같이 회사 포털 앱에서 주의가 필요한 모든 항목을 최종 사용자에게 표시하는 알림 페이지로 이동됩니다. iOS 회사 포털 앱에 이 알림 환경이 이미 있습니다. 새 알림 페이지가 있으면 장치가 등록된 동안 회사 포털을 시작하거나 다시 시작할 때마다 회사 액세스 설정 페이지가 항상 표시되지는 않습니다. 최종 사용자 지침을 만들 경우 이 변경 내용을 반영하도록 문서를 업데이트할 수 있습니다. 업데이트된 스크린샷은 [여기](https://aka.ms/androidcpupdate)에서 볼 수 있습니다.  
<!---TFS 1095560--->

**Android용 회사 포털에서 사용자 의견 제공**</br>
Android용 회사 포털의 메뉴에 새 항목이 추가되었습니다. **도움말 및 피드백** 세 가지 작업이 표시됩니다.
* **도움말 보기**를 사용하여 IT 부서에 회사 포털에 대한 문제를 보고할 수 있습니다. IT에서는 사용자 메일 클라이언트를 사용하여 메일을 작성하고 이 메일에 회사 포털 로그를 첨부합니다. **도움말 보기**가 **설정** 페이지의 **데이터 보내기** 기능을 대체합니다.
* **사용자 의견 제공**을 사용하여 회사 포털 팀에 사용자 의견을 제공할 수 있습니다.
* **앱 평가**를 사용하여 Google Play에서 회사 포털 앱 평가 또는 리뷰를 남길 수 있습니다.

### iOS
**iOS 회사 포털 앱에 대한 지원의 변경 내용**<br/>
이제 iOS용 Microsoft Intune 회사 포털 앱의 모든 사용자는 최신 버전을 사용해야 합니다. 새 사용자는 최신 버전만 다운로드할 수 있고 현재 사용자는 최신 버전으로 업데이트해야 합니다. 최신 버전을 사용하려면 iOS 8.0 이상이 필요하므로 이전 iOS 버전을 실행하는 장치는 장치를 iOS 8.0 이상으로 업데이트한 다음 회사 포털 앱을 최신 버전으로 업데이트할 때까지 회사 포털을 사용하거나 등록할 수 없습니다. iOS 8.0 이전 버전을 실행하는 등록된 장치는 Intune 관리자 콘솔에서 계속 관리되고 표시됩니다.
<!---TFS 1283165--->

**iOS 최종 사용자가 앱을 받는 방법에 대한 개선 사항**<br/>
iOS용 회사 포털 앱의 앱 타일이 다음과 같이 변경되어 사용자의 모든 앱에 대해 회사 포털 웹 사이트라는 하나의 위치에 있는 다른 보기를 가리킵니다. Apple 제한 사항에 따라 기간 업무 및 관리되는 앱 스토어 앱이 회사 포털 앱에 나열되지 못하므로 사용자는 앱을 모두 찾으려면 여러 보기를 방문해야 합니다.

- **회사 앱** 타일은 이전에 회사 포털 웹 사이트의 모두 탭에 있는 모든 앱 목록을 가리켰는데, 계속해서 같은 방식으로 작동합니다. 타일 이름은 **모든 앱**으로 변경되었습니다.
- **기타 앱** 타일은 기존에는 Apple이 회사 포털 앱에서 표시하도록 허용하는 모든 앱을 나열하는 회사 포털 앱 내의 보기를 가리켰습니다. 타일 이름이 **추천 앱**으로 변경되었으며 타일을 탭하면 회사 포털 웹 사이트의 추천 탭으로 이동됩니다.
-  **카테고리** 타일은 이전에 앱의 범주를 나열하는 회사 포털 앱 내 보기를 가리켰습니다. 타일 이름이 변경되지 않았지만 이제는 회사 포털 웹 사이트의 범주 탭을 가리킵니다.
업데이트된 스크린샷은 [여기](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186)에서 볼 수 있습니다.
<!---TFS 1317133--->

**IT Pro이 해당 앱 요구 사항을 설정하면 iOS Managed Browser 앱을 설치하라는 메시지가 나타납니다.**<br/>
웹 클립을 Managed Browser에서만 열 수 있도록 구성했지만 장치에 Managed Browser가 설치되어 있지 않은 경우 장치의 회사 포털 앱에서는 웹 클립을 설치하기 전에 먼저 Managed Browser를 설치하라는 메시지를 표시합니다.
<!---TFS 1228570--->

### Windows
**Windows Phone 8.1 회사 포털 앱에 추가된 사용자 의견 단추**<br/>
최종 사용자는 Windows Phone 8.1 회사 포털 앱의 새 “사용자 의견 보내기” 단추를 사용하여 앱에 대한 사용자 의견을 보낼 수 있습니다. 단추를 찾으려면 회사 포털 앱 화면의 오른쪽 아래에 있는 “세 점” 메뉴를 탭한 다음 **사용자 의견 보내기**를 탭합니다. 익명으로 수집된 피드백은 Microsoft가 사용자를 위해 회사 포털 앱 환경을 개선하는 데 도움이 됩니다.
<!---TFS 1317806--->

## Intune 용어</br>
Intune 제품에 사용되는 일부 용어를 이해하는 데 도움이 되도록 라이브러리에 새 [용어 항목](https://docs.microsoft.com/intune/understand-explore/intune-glossary)을 추가했습니다.



<!--HONumber=Oct16_HO2-->


