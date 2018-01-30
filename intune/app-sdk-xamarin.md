---
title: "Microsoft Intune 앱 SDK Xamarin 구성 요소"
description: 
keywords: sdk, Xamarin, intune
author: erikre
manager: dougeby
ms.author: erikre
ms.date: 11/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4b52b83b84e36a89b5e578c9e14c5093715a559c
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2018
---
# <a name="microsoft-intune-app-sdk-xamarin-component"></a>Microsoft Intune 앱 SDK Xamarin 구성 요소

> [!NOTE]
> 먼저 지원되는 각 플랫폼에서 통합을 준비하는 방법을 설명하는 [Intune 앱 SDK 시작](app-sdk-get-started.md) 문서를 읽어보는 것이 좋습니다.



## <a name="overview"></a>개요
[Intune 앱 SDK Xamarin 구성 요소](https://github.com/msintuneappsdk/intune-app-sdk-xamarin)는 Xamarin에 내장된 iOS 및 Android 앱의 [Intune 앱 보호 정책](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)을 사용하도록 설정합니다. 개발자는 구성 요소를 사용하여 Intune 앱 보호 기능을 Xamarin 기반 앱에 손쉽게 빌드할 수 있습니다.

> [!NOTE]
> Xamarin에 대한 Intune SDK 지원은 현재 미리 보기로 제공됩니다. 

Microsoft Intune 앱 SDK Xamarin 구성 요소를 사용하면 Xamarin으로 개발한 앱에 Intune 앱 보호 정책(APP 또는 MAM 정책이라고도 함)을 통합할 수 있습니다. MAM 지원 응용 프로그램은 Intune 앱 SDK와 통합된 응용 프로그램입니다. IT 관리자는 Intune에서 앱을 적극적으로 관리할 때 모바일 앱에 앱 보호 정책을 배포할 수 있습니다.

## <a name="whats-supported"></a>지원되는 기능

### <a name="developer-machines"></a>개발자 컴퓨터
* macOS


### <a name="mobile-app-platforms"></a>모바일 앱 플랫폼
* Android
* iOS


### <a name="intune-mobile-application-management-scenarios"></a>Intune 모바일 응용 프로그램 관리 시나리오

* Intune MAM 등록 장치
* 타사 EMM 등록 장치
* 관리되지 않는 장치(어떤 MDM에도 등록되지 않음)

이제 Intune 앱 SDK Xamarin 구성 요소가 내장된 Xamarin 앱에서는 Intune 모바일 장치 관리(MDM)가 등록된 장치 및 등록되지 않은 장치 모두에서 Intune 앱 보호 정책을 받을 수 있습니다.

## <a name="prerequisites"></a>전제 조건

* **[Android만 해당]** 최신 Microsoft Intune 회사 포털 앱이 장치에 설치되어 있어야 합니다.

## <a name="get-started"></a>시작

1.  [여기](https://components.xamarin.com/submit/xpkg)에서 **Xamarin-component.exe**를 다운로드하여 압축을 풉니다.

2. Microsoft Intune MAM Xamarin 구성 요소에 대한 [사용 조건](https://components.xamarin.com/license/microsoft.intune.mam)을 읽습니다.

3.  [GitHub](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) 또는 [Nuget.org](https://www.nuget.org/profiles/msintuneappsdk)에서 Intune 앱 SDK Xamarin 구성 요소 폴더를 다운로드하여 압축을 풉니다. 1단계와 3단계에서 다운로드한 파일은 모두 동일한 디렉터리 수준에 있어야 합니다.

4.  관리자 권한으로 명령줄에서 `Xamarin.Component.exe install <.xam> file`을 실행합니다.

5.  Visual Studio에서 이전에 만든 Xamarin 프로젝트의 **구성 요소**를 마우스 오른쪽 단추로 클릭합니다.

6.  **구성 요소 편집**을 선택하고 로컬로 다운로드한 Intune 앱 SDK 구성 요소를 컴퓨터에 추가합니다.



## <a name="enabling-intune-app-protection-polices-in-your-ios-mobile-app"></a>iOS 모바일 앱에서 Intune 앱 보호 정책을 사용하도록 설정
1.  Intune 앱 SDK를 iOS 모바일 앱에 통합하는 데 필요한 일반적인 단계를 따르세요. [iOS용 Intune 앱 SDK 개발자 가이드](app-sdk-ios.md#build-the-sdk-into-your-mobile-app)의 통합 지침 3단계에서 시작할 수 있습니다.
    **중요**: 앱에 키 집합 공유를 사용하도록 설정하는 작업이 Visual Studio와 Xcode에서 약간 다릅니다. 앱의 Entitlements plist를 열고 "키 집합 사용" 옵션이 설정되었으며 해당 섹션에 적절한 키 집합 공유 그룹이 추가되어 있는지 확인합니다. 그런 다음 적절한 모든 구성/플랫폼 조합에 대해 프로젝트 "iOS 번들 서명" 옵션의 "사용자 지정 자격" 필드에 Entitlements plist가 지정되어 있는지 확인합니다.
2.  구성 요소를 추가하고 앱을 제대로 구성하면 앱에서 Intune SDK API를 사용할 수 있습니다. 이렇게 하려면 다음 네임스페이스를 포함해야 합니다.

      ```csharp
      using Microsoft.Intune.MAM;
      ```
3.    앱 보호 정책을 받기 시작하려면 앱이 Intune MAM 서비스에 등록되어 있어야 합니다. 앱이 이미 Azure ADAL(Active Directory Authentication Library)을 사용하여 사용자를 인증하는 경우 앱에서 성공적으로 인증한 후 IntuneMAMEnrollmentManager의 registerAndEnrollAccount 메서드에 사용자 UPN을 제공해야 합니다.
      ```csharp
      IntuneMAMEnrollmentManager.Instance.RegisterAndEnrollAccount(string identity);
      ```
      **중요**: Intune 앱 SDK의 기본 ADAL 설정을 앱 설정으로 재정의해야 합니다. [iOS용 Intune 앱 SDK 개발자 가이드](app-sdk-ios.md#configure-settings-for-the-intune-app-sdk)에 설명된 대로 앱의 Info.plist에 있는 IntuneMAMSettings 사전을 통해 재정의하거나, IntuneMAMPolicyManager 인스턴스의 AAD 재정의 속성을 사용할 수 있습니다. Info.plist 접근 방법은 ADAL 설정이 정적인 응용 프로그램에 권장되고, 재정의 속성은 런타임에 이러한 값을 확인하는 응용 프로그램에 권장됩니다. 
      
      앱이 ADAL을 사용하지 않고 Intune SDK를 사용하여 인증을 처리하려는 경우에는 앱에서 IntuneMAMEnrollmentManager의 loginAndEnrollAccount 메서드를 호출해야 합니다.
      ```csharp
       IntuneMAMEnrollmentManager.Instance.LoginAndEnrollAccount([NullAllowed] string identity);
      ```

## <a name="enabling-app-protection-policies-in-your-android-mobile-app"></a>Android 모바일 앱에서 앱 보호 정책을 사용하도록 설정
UI 프레임워크를 사용하지 않는 Xamarin 기반 Android 앱의 경우에는 [Android용 Intune 앱 SDK 개발자 가이드](app-sdk-android.md)를 읽고 따라야 합니다. Xamarin 기반 Android 앱의 경우에는 클래스, 메서드 및 활동을 가이드에 포함된 [표](app-sdk-android.md#replace-classes-methods-and-activities-with-their-mam-equivalent)에 따라 MAM 클래스, 메서드 및 활동으로 대체해야 합니다. 앱에서 `android.app.Application` 클래스를 정의하지 않는 경우에는 클래스를 새로 만들고 `MAMApplication`에서 상속해야 합니다.

Xamarin Forms 및 기타 UI 프레임워크의 경우에는 `MAM.Remapper`라는 도구를 제공합니다. 이 도구를 통해 클래스를 바꿀 수 있습니다. 그러나 다음 단계를 수행해야 합니다.

1.  `Microsoft.Intune.MAM.Remapper.Tasks` NuGet 패키지 버전 0.1.0.0 이상에 대한 참조를 추가합니다.

2.  Android csproj에 다음 줄을 추가합니다.
  ```xml
  <Import
  Project="$(NugetPack)\\Microsoft.Intune.MAM.Remapper.Tasks.0.1.X.X\\build\\MonoAndroid10\\Microsoft.Intune.MAM.Remapper.targets" />
  ```

3.  추가된 `remapping-config.json` 파일의 빌드 작업을 **RemappingConfigFile**로 설정합니다. 포함된 `remapping-config.json`은 Xamarin.Forms에서만 작동합니다. 기타 UI 프레임워크의 경우에는 Remapper NuGet 패키지와 함께 포함된 추가 정보 파일을 참조하세요.

## <a name="next-steps"></a>다음 단계

앱에 구성 요소를 빌드하기 위한 기본 단계를 완료했습니다. 이제 Xamarin.android 샘플 앱에 포함된 단계를 수행할 수 있습니다. Xamarin.Forms의 샘플과 Android의 샘플이 제공되어 있습니다.
