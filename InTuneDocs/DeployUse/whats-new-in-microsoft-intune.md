---
title: "새로운 기능 | Microsoft Intune"
description: "이번 달의 새로운 소식과 Microsoft Intune의 이전 릴리스 확인"
keywords: 
author: Lindavr
manager: jeffgilb
ms.date: 06/16/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 79617dd41e51402a73759da792f581028095a2f5
ms.openlocfilehash: 65e53ad6a74fbf0e9249c367f517ab52ea0efa80


---

# Microsoft Intune의 새로운 기능
이번 Microsoft Intune 릴리스의 새로운 기능에 대해 알아봅니다. 이전 릴리스에 대한 정보뿐만 아니라 계획을 수립해야 하는 예정된 변경에 대해서도 알아볼 수 있습니다.

다음은 이 릴리스의 새로운 기능입니다. Windows Defender 정책 설정 업데이트를 제외하고 이러한 모든 기능이 하이브리드 고객 배포(Intune이 있는 Configuration Manager)에서도 지원됩니다. 새로운 하이브리드 기능에 대한 자세한 내용은 [hybrid What’s New page](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx)(하이브리드 새로운 기능 페이지)를 참조하세요.

## 2016년 6월
### Intune 서비스 상태
Intune에 대한 서비스 상태 정보는 다른 Microsoft 서비스와 함께 중앙 위치로 이동되었습니다. 이 정보는 이제 Office 365 관리 포털의 서비스 상태에서 찾을 수 있습니다. 자세한 내용은 [이 블로그 게시물](https://blogs.technet.microsoft.com/enterprisemobility/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/)을 참조하세요.

## 앱 관리
- **Windows 10 엔터프라이즈 데이터 정책 구성 환경이 개선되었습니다.** 앱 규칙 생성, 네트워크 경계 정의 지정 및 기타 엔터프라이즈 데이터 보호 설정과 관련된 Windows 10 엔터프라이즈 데이터 보호 정책 구성 환경이 개선되었습니다. 자세한 내용은 [Create an enterprise data protection (EDP) policy using Microsoft Intune](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune)(Microsoft Intune을 사용하여 EDP(엔터프라이즈 데이터 보호) 정책 만들기)을 참조하세요.


## 장치 관리
- **원치 않는 앱으로부터 보호하기 위한 Windows Defender 정책 설정.** **사용자 동의 없이 설치된 응용 프로그램 검색**이라고 하는 새로운 Windows Defender 설정이 Windows 10 Desktop 및 Mobile에 대한 일반 구성 정책에 추가되었습니다. 이 설정을 사용하여 Windows Defender에서 사용자 동의 없이 설치된 소프트웨어로 분류된 프로그램에 대해 등록된 Windows 데스크톱 컴퓨터를 보호할 수 있습니다. 실행 중인 이러한 응용 프로그램으로부터 보호하거나 감사 모드를 사용하여 사용자 동의 없이 응용 프로그램이 설치될 때 보고할 수 있습니다. 자세한 내용은 [Microsoft Intune의 Windows 10 정책 설정](https://docs.microsoft.com/en-us/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)을 참조하세요.
<!---TFS 1244478--->

## 조건부 액세스
- **Intune에 대한 Cisco ISE 네트워크 액세스 제어 정책.**  Cisco ISE(Identity Service Engine) 2.1 및 Microsoft Intune을 사용하는 고객은 ISE에서 네트워크 액세스 제어 정책을 설정할 수 있습니다.

    이 정책을 사용하여 WiFi 또는 VPN을 통해 네트워크에 연결해야 하는 장치는 다음 조건을 충족해야 액세스가 허용됩니다.

    * Intune에서 관리되어야 합니다.
    * 배포된 Intune 준수 정책을 준수해야 합니다.

 비규격 장치의 최종 사용자는 액세스하기 위해 등록하고 준수 문제를 해결하도록 요구됩니다.
- **브라우저에 대한 조건부 액세스.** 정책을 준수하고 관리되는 iOS 및 Android 장치의 지원되는 웹 브라우저에서만 액세스할 수 있도록 [Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md) 및 [SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)에 대한 조건부 액세스 정책을 설정할 수 있게 됩니다. iOS 및 Android 장치를 사용하여 Outlook Web Access(OWA) 및 SharePoint 사이트에 로그인하려는 최종 사용자에게는 Intune을 사용하여 장치를 등록하라는 메시지는 물론 로그인을 완료하기 전에 비호환 문제가 있으면 수정하라는 메시지를 표시하게 됩니다.
<!---TFS 1175844--->

- **Dynamics CRM Online에서 조건부 액세스를 지원합니다.** 정책을 준수하고 관리되는 iOS 및 Android 장치에서만 액세스할 수 있도록, [Dynamics CRM Online](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md)에 대한 조건부 액세스 정책을 설정할 수 있습니다. iOS 및 Android에서 Dynamics CRM 모바일 앱에 로그인하려고 하는 최종 사용자에게 Intune에 등록하고 로그인을 완료하기 전에 모든 비호환성 문제를 해결해야 한다는 메시지가 표시됩니다.
<!---TFS1295358--->

## 회사 포털 업데이트

### Android 회사 포털 앱

- IT 관리자가 새 “장치가 알 수 없는 소스의 앱 설치를 방지해야 함(Android 4.0 이상)” 정책을 적용하면 Android 4.0 이상 장치를 사용하는 최종 사용자에게 "알 수 없는 소스에서의 설치를 금지해야 합니다." 메시지가 표시됩니다. **설정** > **보안**으로 이동한 후 **알 수 없는 원본**을 해제해야 합니다. 규정 준수 메시지의 링크를 클릭하면 해당 메시지에 대한 추가 [정보](/Intune/EndUser/you-are-asked-to-turn-off-unknown-sources-android)와 설정을 해제해야 하는 이유가 표시됩니다.

- IT 관리자가 새 “앱의 보안 위협 검색을 사용하도록 장치가 설정되어 있어야 함(Android 4.0 이상)” 정책을 적용하면 Android 4.0 이상 장치를 사용하는 최종 사용자에게 "장치의 보안 위협 검색" 메시지가 표시됩니다. 사용자는 **설정** > **Google** > **보안**으로 이동한 후 **장치의 보안 위협 검색**을 켜야 합니다. 규정 준수 메시지의 링크를 클릭하면 해당 메시지에 대한 추가 [정보](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android)와 설정을 켜야 하는 이유가 표시됩니다.

- IT 관리자가 새 "USB 디버깅을 사용하지 않도록 설정되어야 함(Android 4.2 이상)" 정책을 적용하면 Android 4.2 이상 장치를 사용하는 최종 사용자에게 "USB 디버깅을 사용하지 않도록 설정해야 합니다." 메시지가 표시됩니다. **설정** > **개발자 옵션**으로 이동하여 **USB 디버깅**을 해제해야 합니다. 규정 준수 메시지의 링크를 클릭하면 해당 메시지에 대한 추가 [정보](/Intune/EndUser/you-are-asked-to-turn-off-usb-debugging-android)와 설정을 해제해야 하는 이유가 표시됩니다.

- IT 관리자가 새 "최소 Android 보안 패치 수준(Android 6.0 이상)" 정책을 적용하면 Android 6.0 이상 장치를 사용하는 최종 사용자에게 "이 장치는 최소 Android 보안 패치 수준을 충족하지 않습니다." 메시지가 표시됩니다. 사용자는 필수 보안 패치를 설치해야 합니다. 규정 준수 메시지의 링크를 클릭하면 필수 보안 패치를 설치하고 현재 설치되어 있는 보안 패치를 확인하는 방법에 대한 [정보](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android)가 표시됩니다.

### iOS 회사 포털 앱

- 최종 사용자가 기간 업무 앱을 설치하는 경우, 향상된 앱 설치 환경이 표시됩니다. 앱 설치가 너무 오래 걸리면, 사용자는 동기화 프로세스가 다시 시작되도록 장치를 수동으로 동기화할 수 있습니다. 최종 사용자 지침을 검토하려면 [iOS 장치를 수동으로 동기화](/Intune/EndUser/sync-your-device-manually-ios)를 참조하세요.

- iOS에 대한 Microsoft Intune 회사 포털 앱은 iOS 버전 8.0 이상을 지원하도록 업데이트되었습니다. 이 업데이트를 사용하면 장치가 iOS 버전 8.0 이상을 실행하는 경우에만 최종 사용자가 Intune에서 회사 포털 앱을 설치하고 새 장치를 등록할 수 있습니다. 지원되지 않는 iOS 버전을 실행 중이고 이미 등록된 장치가 있는 사용자는 자신의 장치에 있는 회사 포털 앱을 계속 사용할 수 있습니다.


## 향후 예정 사항

### 클라우드 로드맵
[클라우드 플랫폼 로드맵](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)에서 Intune에 대해 예정된 개발 정보를 지속적으로 받습니다.

### 서비스 중단
- **Intune 뷰어 앱.** 2016년 8월부터 새 RMS 공유 앱의 릴리스에서 다음 Intune 뷰어 앱을 제거합니다.
    - Intune AV 뷰어
    - Intune PDF 뷰어
    - Google Play의 Android용 Intune 이미지 뷰어

  Intune 뷰어 앱을 사용하는 대신 새로운 Android용 Microsoft Rights Management 공유 앱(RMS 공유)을 사용하는 것이 좋습니다. 이 앱을 통해 세 개의 별도 앱이 아니라 하나의 앱을 배포하여 Android 장치에서 회사 파일을 안전하게 볼 수 있습니다.

- **사용자 지정 그룹을 알림 규칙의 대상으로 지정하는 기능 제거.**
Intune 알림 규칙은 Intune에서 메일 경고를 보낼 대상자를 정의합니다. 현재 직접 만든 Intune 장치 그룹의 모든 장치 사용자에게 메일을 보내도록 알림 규칙을 구성할 수 있습니다. 2016년 6월 1일경부터는 사용자가 만든 그룹을 대상으로 지정하는 기능이 더 이상 지원되지 않습니다.

    이제 Microsoft Intune 관리 콘솔에서 직접 만든 그룹을 알림 규칙 대상으로 지정하려면 다음 단계를 수행하세요.

    **관리자** 작업 영역에서 **알림 규칙** > **새 규칙 만들기**를 클릭합니다.

    알림 규칙 만들기 마법사의 2단계에서 규칙의 대상이 되는 장치 그룹을 선택합니다. 이 단계 즉, “장치 그룹 선택”은 Intune 콘솔에서 제거됩니다.

    이러한 변경을 준비하기 위한 타임라인은 다음과 같습니다.
    - 2016년 8월에는 새 테넌트에 알림 규칙 만들기 마법사의 2단계가 표시되지 않습니다. 기존 테넌트는 영향을 받지 않습니다.
    - 2016년 9월경에는 일부 기존 테넌트에 마법사의 "장치 그룹 선택"이 표시되지 않습니다.
    - 2016년 11월경에는 모든 기존 테넌트에 마법사의 "장치 그룹 선택"이 표시되지 않을 것으로 예상됩니다.


- **iOS 회사 포털 앱에 대한 지원의 변경 내용**. 7월에 iOS용 Microsoft Intune 회사 포털 앱의 모든 사용자는 최신 버전을 사용해야 합니다. 새 사용자는 최신 버전만 다운로드할 수 있고 현재 사용자는 최신 버전으로 업데이트해야 합니다. 최신 버전을 사용하려면 iOS 8.0 이상이 필요하므로 이전 iOS 버전을 실행하는 장치는 장치를 iOS 8.0 이상으로 업데이트한 다음 회사 포털 앱을 최신 버전으로 업데이트할 때까지 회사 포털을 사용하거나 등록할 수 없습니다. iOS 8.0 이전 버전을 실행하는 등록된 장치는 Intune 관리자 콘솔에서 계속 관리되고 표시됩니다.





## 이전 Intune 릴리스
지난 6개월간 Intune에 릴리스된 목록을 보려면 [이전 Intune 릴리스](previous-intune-releases.md) 문서를 참조하세요.



### 참고 항목
* [Microsoft Intune 블로그](http://go.microsoft.com/fwlink/?LinkID=273882)
* [클라우드 플랫폼 로드맵](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)



<!--HONumber=Jul16_HO1-->


