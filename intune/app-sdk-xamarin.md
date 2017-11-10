---
title: "Microsoft Intune 앱 SDK Xamarin 구성 요소"
description: 
keywords: sdk, Xamarin, intune
author: mattbriggs
manager: angrobe
ms.author: mabriggs
ms.date: 11/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f50ecfbf5a0ac0b05de38e0ad29b27a729ab824b
ms.sourcegitcommit: 0f877251e6adf4e45b918cc8dc9193626727f2d9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2017
---
# <a name="microsoft-intune-app-sdk-xamarin-component"></a>Microsoft Intune 앱 SDK Xamarin 구성 요소

> [!NOTE]
> 먼저 지원되는 각 플랫폼에서 통합을 준비하는 방법을 설명하는 [Intune 앱 SDK 시작](app-sdk-get-started.md) 문서를 읽어보는 것이 좋습니다.



## <a name="overview"></a>개요
[Intune 앱 SDK Xamarin 구성 요소](https://components.xamarin.com/view/microsoft.intune.mam)는 Xamarin에 내장된 iOS 및 Android 앱의 [Intune 앱 보호 정책](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)을 사용하도록 설정합니다. 개발자는 구성 요소를 사용하여 Intune 앱 보호 기능을 Xamarin 기반 앱에 손쉽게 빌드할 수 있습니다.

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

3.  [GitHub](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) 또는 [Xamarin](https://components.xamarin.com/license/microsoft.intune.mam)에서 Intune 앱 SDK Xamarin 구성 요소 폴더를 다운로드하여 압축을 풉니다. 1단계와 3단계에서 다운로드한 파일은 모두 동일한 디렉터리 수준에 있어야 합니다.

4.  관리자 권한으로 명령줄에서 `Xamarin.Component.exe install <.xam> file`을 실행합니다.

5.  Visual Studio에서 이전에 만든 Xamarin 프로젝트의 **구성 요소**를 마우스 오른쪽 단추로 클릭합니다.

6.  **구성 요소 편집**을 선택하고 로컬로 다운로드한 Intune 앱 SDK 구성 요소를 컴퓨터에 추가합니다.



## <a name="enabling-intune-app-protection-polices-in-your-ios-mobile-app"></a>iOS 모바일 앱에서 Intune 앱 보호 정책을 사용하도록 설정
1.  Intune 앱 SDK를 초기화하려면 `AppDelegate.cs` 클래스의 모든 API에 대해 호출을 수행해야 합니다. 예를 들면 다음과 같습니다.

      ```csharp
      public override bool FinishedLaunching (UIApplication application, NSDictionary launchOptions)
      {
            Console.WriteLine ("Is Managed: {0}", IntuneMAMPolicyManager.Instance.PrimaryUser != null);
            return true;
      }

      ```

2.  구성 요소가 추가되고 초기화되었으면 앱 SDK를 iOS 모바일 앱에 빌드하는 데 필요한 일반적인 단계를 따를 수 있습니다. [iOS용 Intune 앱 SDK 개발자 가이드](app-sdk-ios.md)에서 네이티브 iOS 앱을 사용 설정하기 위한 전체 설명서를 찾을 수 있습니다.
3. **중요**: Xamarin 기반 iOS 앱에서만 수정할 사항이 여러 가지 있습니다. 예를 들어 키 집합 그룹을 사용 설정하는 경우에는 구성 요소에 포함된 Xamarin 샘플 앱을 포함하기 위해 다음을 추가해야 합니다. 다음은 Keychain Access 그룹에 있어야 하는 그룹의 예입니다.

      ```xml
      <?xml version="1.0" encoding="UTF-8"?>
      <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
      <plist version="1.0">
            <dict>
                  <key>keychain-access-groups</key>
                  <array>
                        <string>$(AppIdentifierPrefix)com.xamarin.microsoftintunesample</string>
                        <string>$(AppIdentifierPrefix)com.xamarin.microsoftintunesample.intunemam</string>
                        <string>$(AppIdentifierPrefix)com.microsoft.intune.mam</string>
                        <string>$(AppIdentifierPrefix)com.microsoft.adalcache</string>
                  </array>
            </dict>
      </plist>
      ```

Xamarin 기반의 iOS 앱에 구성 요소를 빌드하는 데 필요한 단계를 완료했습니다. Xcode를 사용하여 프로젝트를 빌드하는 경우에는 `Intune App SDK Settings.bundle`을 사용할 수 있습니다. 이렇게 하면 프로젝트를 빌드하여 테스트하고 디버그할 때 Intune 정책 설정을 켜고 끌 수 있습니다. 이 번들을 이용하려면 [iOS용 Intune 앱 SDK 개발자 가이드](app-sdk-ios.md)에 나오는 단계를 따르고 [Xcode에서 디버깅](app-sdk-ios.md#status-result-and-debug-notifications)에 나오는 섹션을 읽어보세요.

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
