---
title: "향후 예정 사항 | Microsoft Intune"
description: 
keywords: 
author: Lindavr
manager: angrobe
ms.date: 08/04/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 500cc93b595e04cea987bda699abf94ae010443a
ms.openlocfilehash: f45fc02003c6b40cc15fabeffff35cf0cde1a830


---

# Microsoft Intune의 향후 예정 사항 - 8월
이 정보는 NDA 하에 매우 제한적으로 제공되며, 변경될 수 있습니다. 여기 나열된 일부 기능은 마감일을 맞추지 못할 위험이 있으며 다음 릴리스까지 지연될 수 있습니다. 다른 기능은 고객용 준비 상태를 확인하기 위해, 파일럿(플라이팅) 테스트 중 입니다. 질문이나 궁금한 내용이 있으면 Intune/PM 담당자에게 연락하세요.

이 페이지는 정기적으로 업데이트됩니다. 다시 방문하여, 향후 예정 사항에 새로운 업데이트가 있는지 확인하십시오.

Intune에 대해 다음 변경 사항을 개발 중입니다. 최종적으로는 이 모든 기능이 하이브리드 고객 배포(Intune과 Configuration Manager )용으로 지원될 예정입니다. 새로운 하이브리드 기능에 대한 자세한 내용은 [hybrid What’s New page](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx)(하이브리드 새로운 기능 페이지)를 참조하세요.


## 앱 관리
### iOS 9.3에 대해 숨겨진/표시된 앱
iOS 9.3 이상을 실행하는 감독된 장치의 경우에는 iOS 일반 구성 정책에서 숨겨진/표시된 앱 목록을 사용하여 다음을 수행할 수 있습니다.
- 사용자로부터 숨길 앱 목록을 지정합니다. 사용자는 이러한 앱을 보거나 시작할 수 없습니다.
- 사용자가 보고 시작할 수 있는 앱 목록을 지정합니다. 다른 앱은 보거나 시작할 수 없습니다.

지정할 수 있는 앱에는 사용자가 배포한 앱과 메시지 및 메모와 같은 기본 제공 iOS 앱이 모두 포함됩니다.
<!---TFS 1279009--->

### Samsung KNOX 장치에 대해 허용된/차단된 앱 정책

이제 Samsung KNOX 장치용 사용자 지정 정책을 구성하여 다음 중 하나를 만들 수 있습니다.
- 장치에서 실행되지 않도록 차단할 앱 목록. 앱이 설치되었더라도 차단 목록에 정의된 앱은 장치에서 활성화할 수 없습니다.
- 장치 사용자가 Google Play 스토어에서 설치할 수 있도록 허용된 앱 목록. 다른 앱은 스토어에서 설치할 수 없습니다.

이러한 설정은 Samsung KNOX를 실행하는 장치에서만 사용할 수 있습니다.
<!--- For details, see [Use custom policies to allow and block apps for Samsung KNOX devices]( custom-policy-to-allow-and-block-samsung-knox-apps.md)--->
<!---TFS 1311629 --->

### MAM(모바일 응용 프로그램 관리) 정책과 호환되는 새로운 앱
[iOS](https://itunes.apple.com/app/yammer/id289559439?mt=8) 및 [Android](https://play.google.com/store/apps/details?id=com.yammer.v1)용 Yammer 앱은 장치 등록 여부에 상관없이 [Intune MAM(모바일 응용 프로그램 관리) 정책](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)과 호환됩니다.

MAM과 호환되는 앱의 전체 목록은 [Microsoft Intune application partners](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners)(Microsoft Intune 응용 프로그램 파트너) 사이트를 참조하세요.
<!--- TFS 1252335 & 1252336--->

## 장치 관리
### Android 7.0 지원
8월에 Intune에서는 모바일 장치용으로 곧 출시 예정인 Android 7.0 운영 체제에 대해 “Day 0” 지원을 제공할 예정입니다.
<!---TFS 1262053--->
### Android 7.0 장치에서 Google의 원격 암호 재설정 기능 제거
Google에서 IT 관리자와 최종 사용자가 Android 7.0 장치의 암호를 원격으로 다시 설정하는 기능을 제거할 예정입니다. 이전에는 IT 관리자가 원격으로 사용자의 암호를 다시 설정하고, 최종 사용자가 회사 포털 웹 사이트에서 자신의 암호를 다시 설정할 수 있었습니다.

## 그룹 관리
### 2016년 9월부터 Intune 그룹에서 Azure Active Directory 그룹으로 전환
Intune은 Intune에서 AAD(Azure Active Directory) 보안 그룹을 사용자 및 장치 그룹으로 사용하는 새로운 그룹 관리 환경을 만들고 있습니다. 이러한 그룹은 **새 Azure 기반 Intune 관리 포털을 도입할 때 **모든 그룹 관리, 정책 배포 및 프로필 배포에 사용됩니다.

이 새로운 환경은 서비스 간에 그룹을 복제할 필요를 없애주고 **몇 가지 새로운 AADP(Azure Active Directory Premium) 그룹 기능에 대한 액세스를 허용하고** PowerShell 및 Graph를 사용하여 확장성을 제공합니다. 또한 엔터프라이즈 이동성 관리에서 그룹 관리 환경을 통합합니다.

보안 그룹으로의 이동을 설정하기 위해 **현재 관리 콘솔**의 환경이 약간 수정될 예정입니다. **이러한 변경 내용 및 AAD 보안 그룹의 사용 방식은 Intune 설명서에 기록됩니다**.

Intune을 처음 사용하는 고객은 **현재 테넌트보다 먼저 일부 보안 그룹의 변경**을 보게 될 것입니다.

그룹 관리에 대한 변경 내용 외에 **다음과 같은 기능은 더 이상 사용되지 않게 됩니다**.
- 새 그룹을 만드는 동안 구성원 또는 그룹 제외
- **그룹 해제된 사용자** 및 **그룹 해제된 장치** 그룹
- 서비스 관리자 역할의 **그룹 관리**
- 알림 규칙에 대한 사용자 지정 그룹 기반 경고
- 보고서에서 그룹으로 피벗
<!--- TFS 1295329--->

## 회사 포털

### 회사 포털에서 Microsoft로 피드백 링크
회사 포털 웹 사이트에서 최종 사용자가 페이지 맨 아래에 새로 생긴 “피드백" 링크를 탭하여 사이트 사용 경험에 대해 피드백을 Microsoft에 보낼 수 있습니다. 익명으로 수집된 피드백은 Microsoft가 사용자를 위해 회사 포털 웹 사이트를 개선하는 데 도움이 됩니다.
<!--- TFS 1313657--->

### Android용 회사 포털에 '알림' 추가
9월에는 홈페이지에 새 **알림** 아이콘을 추가하는 업데이트를 Android용 회사 포털에 릴리스할 예정입니다. 이 아이콘을 누르면 호환되지 않는 장치, 등록 업데이트 및 등록 활성화와 같이 회사 포털 앱에서 주의가 필요한 모든 항목을 최종 사용자에게 표시하는 **알림** 페이지로 이동됩니다. IOS 회사 포털 앱을 사용하는 경우에는 이미 알림을 제공받았을 것입니다. **알림** 페이지가 도입되면서 장치가 등록된 동안 Android용 회사 포털을 시작하거나 다시 시작할 때마다 **회사 액세스 설정** 페이지가 항상 표시되지는 않습니다. 많은 고객 여러분이 최종 사용자 지침을 만드는 데 도움을 주신 점을 알고 있습니다. 지침/스크린샷을 업데이트해야 할 때 미리 알려 주시는 점에 감사드립니다. 예정된 변경 내용을 환경에 반영하려면 설명서를 업데이트하세요. 업데이트된 스크린샷을 보려면 https://aka.ms/androidcpupdate로 이동하세요.  

### iOS 최종 사용자가 앱을 받는 방법에 대한 개선 사항
다음 변경 내용은 9월 iOS용 회사 포털 앱의 앱 타일에 적용되어, 사용를 회사 포털 웹 사이트라는 하나의 위치에서 모든 앱에 대한 다른 보기로 가리킵니다. 현재 Apple 제한 사항은 기간 업무 및 관리되는 App Store 앱이 회사 포털 앱에 나열되는 것을 금지하므로 사용자가 자신의 앱을 모두 찾으려면 여러 보기를 방문해야 합니다.

- 현재 **회사 앱** 타일은 회사 포털 웹 사이트의 모두 탭에 있는 모든 앱 목록을 가리키고 있으며, 계속해서 같은 방식으로 작동합니다. 타일 이름이 **모든 앱**으로 변경됩니다.
- **다른 앱** 타일은 현재 Apple이 표시를 허용하는 모든 회사 포털 앱이 나열된 회사 포털 앱 내 보기를 가리키고 있습니다. 타일 이름이 **추천 앱**으로 변경되며 타일을 탭하면 사용자는 회사 포털 웹 사이트의 추천 탭으로 이동하게 됩니다.
-  **카테고리** 타일은 앱의 범주를 나열하는 회사 포털 앱 내 보기를 현재 가리키고 있습니다. 타일 이름은 변경되지 않지만 이제 회사 포털 웹 사이트의 범주 탭을 가리키게 됩니다.
업데이트된 스크린샷은 [여기](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186)에서 볼 수 있습니다.
<!---TFS 1317133--->

### IT Pro이 해당 앱 요구 사항을 설정하면 iOS Managed Browser 앱을 설치하라는 메시지가 나타납니다.
iOS 회사 포털 앱의 9월 릴리스에서는 사용자가 웹 클립을 Managed Browser에서만 열 수 있도록 구성했지만 장치에 Managed Browser가 설치되어 있지 않은 경우 해당 장치의 회사 포털 앱은 웹 클립을 설치하기 전에 먼저 Managed Browser를 설치하라는 메시지를 사용자에게 표시합니다. 
<!---TFS 1228570--->

## 서비스 중단
### Windows 8 및 Windows Phone 8용 회사 포털 앱은 2016년 9월부터 사용되지 않습니다.
2016년 10월부터 Microsoft Intune에서는 Windows 8 및 Windows Phone 8 회사 포털 앱을 더 이상 지원하지 않습니다. 또한 Windows Phone 8 플랫폼도 지원되지 않습니다. 따라서 Windows Phone 8 장치를 등록하거나 업데이트할 수 없게 됩니다. 이미 등록된 Windows Phone 8 및 Windows 8 장치는 계속 관리할 수 있습니다. 서비스 중단 없이 이러한 장치에 앱을 계속 배포하려면 Windows Phone 8 및 Windows 8 장치를 Windows 8.1 및 Windows Phone 8.1로 업데이트하고 해당하는 Windows 8.1 및 Windows Phone 8.1 회사 포털 앱을 사용하세요.
<!---TFS 1255391--->

### 사용자 지정 그룹을 알림 규칙의 대상으로 지정하는 기능 제거
Intune 알림 규칙은 Intune에서 메일 경고를 보낼 대상자를 정의합니다. 현재 직접 만든 Intune 장치 그룹의 모든 장치 사용자에게 메일을 보내도록 알림 규칙을 구성할 수 있습니다. 2016년 6월부터 사용자가 만든 그룹을 대상으로 지정하는 기능이 더 이상 지원되지 않습니다.

이러한 변경을 준비하기 위한 타임라인은 다음과 같습니다.
- 2016년 9월에는 새 테넌트에 알림 규칙 만들기 마법사의 2단계가 표시되지 않습니다. 기존 테넌트는 영향을 받지 않습니다.
- 2016년 10월경에는 일부 기존 테넌트에 마법사의 "장치 그룹 선택"이 표시되지 않습니다.
- 차후에는 모든 기존 테넌트에 마법사의 "장치 그룹 선택"이 표시되지 않을 것으로 예상됩니다.

<!---   TFS 1278864--->
### iOS 회사 포털 앱에 대한 지원의 변경 내용
9월에 iOS용 Microsoft Intune 회사 포털 앱의 모든 사용자는 최신 버전을 사용해야 합니다. 새 사용자는 최신 버전만 다운로드할 수 있고 현재 사용자는 최신 버전으로 업데이트해야 합니다. 최신 버전을 사용하려면 iOS 8.0 이상이 필요하므로 이전 iOS 버전을 실행하는 장치는 장치를 iOS 8.0 이상으로 업데이트한 다음 회사 포털 앱을 최신 버전으로 업데이트할 때까지 회사 포털을 사용하거나 등록할 수 없습니다. iOS 8.0 이전 버전을 실행하는 등록된 장치는 Intune 관리자 콘솔에서 계속 관리되고 표시됩니다.

<!---TFS 1283165--->


### Intune 뷰어 앱
2016년 8월부터 새로 릴리스되는 RMS 공유 앱에서는 다음 Intune 뷰어 앱이 제거됩니다.
- Intune AV 뷰어
- Intune PDF 뷰어
- Google Play의 Android용 Intune 이미지 뷰어

Intune 뷰어 앱을 사용하는 대신 새로운 Android용 Microsoft Rights Management 공유 앱(RMS 공유)을 사용하는 것이 좋습니다. 이 앱을 통해 세 개의 별도 앱이 아니라 하나의 앱을 배포하여 Android 장치에서 회사 파일을 안전하게 볼 수 있습니다. [RMS 공유 앱](https://docs.microsoft.com/en-us/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app)에 대해 자세히 알아보세요.
<!--- goes in 1608 What's New--->


### 참고 항목
최근 개발 작업에 대한 자세한 내용은 [Microsoft Intune의 새로운 기능](whats-new-in-microsoft-intune.md)을 참조하세요.



<!--HONumber=Aug16_HO5-->


