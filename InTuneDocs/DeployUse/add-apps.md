---
# required metadata

title: 앱 추가 | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 2b770f4f-6d36-41e4-b535-514b46e29aaa

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: mghadial
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune을 사용하여 앱 추가
Microsoft Intune을 사용하여 앱의 배포를 시작하기 전에 이 항목에서 소개하는 개념에 대해 알아보세요. 어떤 플랫폼에 어떤 앱을 배포할 수 있는지를 이해하고 이렇게 하기 전에 충족해야 하는 필수 구성 요소를 이해하는 데 도움이 됩니다.

## Intune을 사용하여 배포할 수 있는 앱 유형
Intune에서 지원하는 모든 장치 유형에 앱을 배포할 수 있습니다. 배포하려는 앱 유형에 따라 프로세스 및 지원되는 장치가 달라집니다. 다음 정보를 통해 배포할 수 있는 항목과 배포할 수 없는 항목을 파악할 수 있습니다.


### **Windows Installer(&#42;.exe, &#42;.msi)**
- 이런 종류의 앱은 사용자 입력 없이 자동 설치를 지원해야 합니다. 앱 설명서에는 앱을 자동으로 설치하기 위한 관련 명령줄 옵션이 있어야 합니다(예: **/q**). 일반 명령줄 옵션 목록은 [여기](https://support.microsoft.com/en-us/kb/227091)에서 확인할 수 있습니다.
- 앱의 설치 프로그램에 필요한 모든 추가 파일 및 폴더는 앱 설치 파일에 대해 사용자가 지정한 위치에서 사용할 수 있어야 합니다.
- 대부분의 경우 Intune을 통해 Windows Installer(.msi) 및 Windows Installer 패치(.msp) 파일을 설치하는 데 어떤 명령줄 인수도 필요하지 않습니다. 앱 설명서를 확인하십시오. 명령줄 인수가 필요한 경우에는 이름=값 쌍(예: TRANSFORMS=custom_transform.mst)으로 입력해야 합니다.

이 유형의 앱은 클라우드 저장소 공간에 업로드됩니다.
### **Android용 앱 패키지(&#42;.apk 파일)**
이 유형의 앱은 클라우드 저장소 공간에 업로드됩니다.
### **iOS용 앱 패키지(&#42;.ipa 파일)**
- iOS 앱을 배포하려면 유효한 .ipa 패키지가 있어야 합니다.
- .ipa 패키지는 Apple에 의해 서명되어야 하고, 프로비전 프로필에 표시된 만료 날짜가 유효해야 합니다. Intune에서는 엔터프라이즈 인증서 iOS 응용 프로그램을 배포할 수 있습니다. 일부 Apple 개발자 인증서 앱은 지원되지 않습니다.
- 회사가 iOS Developer Enterprise Program에 등록되어 있어야 합니다.
- 조직의 방화벽에서 iOS 프로비전 및 인증 웹 사이트에 대한 액세스를 허용해야 합니다.
- 매니페스트 파일(.plist)은 앱과 함께 배포할 필요가 없습니다.

이 유형의 앱은 클라우드 저장소 공간에 업로드됩니다.

현재 최종 사용자는 iOS용 Intune 회사 포털 앱에서 회사 앱을 바로 설치할 수 없습니다. 이 iOS 앱스 토 어에에서 게시 된 응용 프로그램에 배치 하는 제한 사항으로 인해 (참조 [앱 스토어 검토 지침](https://developer.apple.com/app-store/review/guidelines/)). 사용자가 장치에서 회사 포털 앱을 시작하고 회사 앱 타일을 눌러 회사 앱(관리 앱 스토어 및 LOB(기간 업무) 앱 패키지 포함)에 액세스할 수 있습니다. 그러면 브라우저가 열리고 Intune 웹 포털로 리디렉션됩니다.

### **Windows Phone 앱 패키지(&#42;.xap, .appx, .appxbundle)**
- 앱을 배포하려면 기업용 모바일 코드 서명 인증서가 필요합니다. 자세한 내용은 [Microsoft Intune을 사용한 Windows Phone 관리 설정](set-up-windows-phone-management-with-microsoft-intune.md)을 참조하세요.

이 유형의 앱은 클라우드 저장소 공간에 업로드됩니다.

Intune을 사용하여 LOB(기간 업무) UWP(유니버설 Windows 플랫폼) 앱을 설치하는 방법에 대한 정보는 아래를 참조하세요.

### **Windows 앱 패키지(.appx, .appxbundle)**
- 앱을 배포하려면 기업용 모바일 코드 서명 인증서가 필요합니다. 자세한 내용은 [Microsoft Intune을 사용한 Windows 장치 관리 설정](set-up-windows-device-management-with-microsoft-intune.md)을 참조하세요.

이 유형의 앱은 클라우드 저장소 공간에 업로드됩니다.
### **MDM을 사용하는 Windows Installer(&#42;.msi)**
이 설치 관리자 유형을 사용하면 Windows Installer 기반 앱을 만들어 Windows 10을 실행하는 등록된 PC에 배포할 수 있습니다.<br /><br />이 설치 관리자 유형을 사용하는 경우에 고려해야 하는 사항은 다음과 같습니다.
- 확장명이 .msi인 파일 하나만 업로드할 수 있습니다.
- 파일의 제품 코드와 제품 버전을 앱 검색에 사용합니다.
- 앱의 기본 다시 시작 동작이 사용됩니다. Intune에서 다시 시작을 제어하지는 않습니다.
- 단일 사용자에 대해 사용자별 MSI 패키지가 설치됩니다.
- 장치의 모든 사용자에 대해 컴퓨터별 MSI 패키지가 설치됩니다.
- 이중 모드 MSI 패키지는 현재 장치의 모든 사용자에 대해서만 설치됩니다.
- 각 버전의 MSI 제품 코드가 동일하면 앱 업데이트가 지원됩니다.

이 유형의 앱은 클라우드 저장소 공간에 업로드됩니다.
### **외부 링크**
다음이 있는 경우에 사용됩니다.
- 사용자가 앱 스토어에서 앱을 다운로드할 수 있는 **URL**
- 웹 브라우저에서 실행되는 웹 기반 앱으로 연결되는 **Link**

외부 링크를 기반으로 하는 앱은 Intune 클라우드 저장소 공간에 저장되지 않습니다.
### **앱 스토어에서 관리되는 iOS 앱**
앱 스토어에서 무료 iOS 앱을 관리하고 배포할 수 있습니다. 또한 [모바일 응용 프로그램 관리 정책](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md)을 [호환되는 앱](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx)과 연결하고 관리자 콘솔에서 관련 상태를 검토할 수 있습니다.<br /><br />관리되는 iOS 앱은 Intune 클라우드 저장소 공간에 저장되지 않습니다.
> [!TIP] Intune에 [모바일 장치 관리 기관을 설정](get-ready-to-enroll-devices-in-microsoft-intune.md)할 때까지 모바일 장치에 대한 옵션을 사용할 수 없습니다.

## UWP(유니버설 Windows 플랫폼) 앱 지원
Windows 10 PC에서는 LOB(기간 업무) 앱을 설치하기 위한 테스트용 로드 키가 필요하지 않습니다. 그러나 레지스트리 키 **HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Appx\AllowAllTrustedApps**에 **1**의 값이 있어야 테스트용 로드를 수행할 수 있습니다.

이 레지스트리 키를 구성하지 않으면 앱을 처음으로 장치에 배포할 때 Intune에서 이 값을 자동으로 **1**로 설정하게 됩니다. 이 값을 **0**으로 설정한 경우 Intune에서 이 값을 자동으로 변경할 수 없고 LOB(기간 업무) 앱의 배포가 실패하게 됩니다.

유니버설 Windows 플랫폼 LOB(기간 업무) 앱은 앱을 배포하는 각 장치에서 신뢰할 수 있는 코드 서명 인증서로 서명되어 있어야 합니다. 사내 PKI 인프라의 인증서나 장치에 설치된 타사 공개 루트 인증서의 인증서를 사용할 수 있습니다.

Windows 10 Mobile 장치에서 비Symantec 코드 서명 인증서를 사용하여 유니버설 **.appx** 앱에 서명할 수 있습니다. **.xap** 앱 및 Windows 10 Mobile 장치에 설치할 Windows Phone 8.1용으로 작성된 **.appx** 패키지에는 Symantec 코드 서명 인증서를 사용해야 합니다.

## 다음 단계 

다음으로, 배포하기 전에 Intune 콘솔에서 앱을 추가해야 합니다. [등록된 장치](add-apps-for-mobile-devices-in-microsoft-intune.md) 또는 [Intune 클라이언트 소프트웨어를 사용하여 관리하는 Windows PC](add-apps-for-windows-pcs-in-microsoft-intune.md)에 대한 앱을 추가할 수 있습니다.

<!--HONumber=Jun16_HO2-->


