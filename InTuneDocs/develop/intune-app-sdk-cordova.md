---
title: "Microsoft Intune 앱 SDK Cordova 플러그 인 | Microsoft 문서"
description: 
keywords: sdk, Cordova, intune
author: oydang
manager: angrobe
ms.author: oydang
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bb940cb9-d43f-45ca-b065-ac0adc61dc6f
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: df54ac3a62b5ef21e8a32f3a282dd5299974a1b0
ms.openlocfilehash: 40c369bb0ff18bda30b221c461f75799e601c67c
ms.lasthandoff: 04/12/2017


---
# <a name="microsoft-intune-app-sdk-cordova-plugin"></a>Microsoft Intune 앱 SDK Cordova 플러그 인

> [!NOTE]
> 먼저 지원되는 각 플랫폼에서 통합을 준비하는 방법을 설명하는 [Intune 앱 SDK 시작](intune-app-sdk-get-started.md) 문서를 읽어보는 것이 좋습니다.

## <a name="overview"></a>개요

[Intune 앱 SDK Cordova 플러그 인](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam)은 Cordova에 내장된 iOS 및 Android 앱의 [Intune 모바일 앱 보호 정책](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)을 사용하도록 설정합니다. 개발자는 플러그 인을 사용하여 Cordova 기반 앱에 Intune 앱 및 데이터 보호 기능을 통합할 수 있습니다.

앱의 동작을 변경하지 않고 SDK 기능을 사용하도록 설정할 수 있습니다. iOS 또는 Android 앱에 플러그 인을 빌드하면 Microsoft Intune 관리자가 다양한 데이터 보호 기능으로 구성된 Intune 앱 보호 정책을 배포할 수 있습니다. 대부분의 단계가 Cordova 빌드 프로세스에서 자동으로 수행되도록 플러그 인을 빌드했습니다. 결과적으로 앱에서 Intune 앱을 신속하게 보호하도록 설정할 수 있게 되었습니다. 시작하려면 대상 플랫폼에 따라 다음 단계를 수행합니다.

## <a name="supported-platforms"></a>지원되는 플랫폼

* 플러그 인이 Windows, Mac, Linux OS에서 작동
* 플러그 인이 `minSdkVersion` >= 14 및 `targetSdkVersion` <= 24의 Android 앱에서 작동
* 플러그 인이 iOS 9.0 이상을 대상으로 하는 iOS 앱에서 작동

## <a name="intune-mobile-application-management-scenarios"></a>Intune 모바일 응용 프로그램 관리 시나리오

* Intune MAM 등록 장치
* 타사 EMM 등록 장치
* 관리되지 않는 장치(어떤 MDM에도 등록되지 않음)

이제는 Intune 앱 SDK Cordova 플러그 인이 내장된 Cordova 앱에서는 Intune 모바일 장치 관리(MDM)가 등록된 장치 및 등록되지 않은 장치 모두에서 Intune 앱 보호 정책을 받을 수 있습니다.

## <a name="prerequisites"></a>필수 구성 요소

### <a name="android"></a>Android

* 최신 Microsoft Intune 회사 포털 앱이 항상 장치에 설치된 상태여야 합니다.
* 플러그 인을 사용할 때 Java 7 이상이 Cordova 빌드가 실행될 경로에 있어야 합니다.

### <a name="ios"></a>iOS

* MDM 기능을 사용하려면 최신 Microsoft Intune 회사 포털 앱이 장치에 설치된 상태여야 합니다. 장치 등록 기능이 없는 Intune 앱 보호 정책에는 필요하지 *않습니다*.

### <a name="both-platforms"></a>두 플랫폼 모두

* [Cordova용 Azure Active Directory 인증 라이브러리(ADAL) 플러그 인](https://github.com/AzureAD/azure-activedirectory-library-for-cordova)의 0.8.0 버전 이상이 필요합니다.

> [!NOTE]
> [여기](https://issues.apache.org/jira/browse/CB-6227?jql=text%20~%20%22plugin%20dependency%22) 제출된 Apache Cordova로 인해 플러그 인 종속성이 이미 있는 앱은 플러그 인을 요청된 버전으로 자동으로 업그레이드하지 않습니다.



## <a name="quick-start"></a>빠른 시작

1. ADAL 버전 업데이트:

  ```shell
  cordova plugin remove cordova-plugin-ms-adal
  cordova plugin add cordova-plugin-ms-adal@0.8.x
  ```

2. Cordova 플러그 인에 대한 Intune 앱 SDK 추가:

  ```shell
  cordova plugin add cordova-plugin-ms-intune-mam
  ```

## <a name="build-the-plugin-into-your-ios-app"></a>IOS 앱에 플러그 인 빌드

Intune 앱 보호 정책을 사용하도록 설정하려면 앱에서 몇 가지 단계를 완료해야 합니다. 편의를 위해 이러한 단계는 Cordova 빌드 프로세스에서 빌드 전 후크로 자동 수행됩니다. 결과적으로 자동화된 단계를 통해 프로젝트 구성과 연관된 `*.pbxproj`, `*-Info.plist` 및 `*.entitlements`파일이 수정됩니다. 프로젝트에 권한 부여 파일이 포함되지 않으면 플러그 인이 자동으로 그러한 파일을 만듭니다.

이 설치는 단일 대상만 지원하며 대상이 여러 개 있는 경우에는 첫 번째로 발견된 대상에서 구성을 수행합니다. 프로세스가 실패하면 다음을 확인합니다.

1. 앱의 Xcode 프로젝트는 `config.xml`에 정의된 값이 있는 `[name].xcodeproj`위치`[name]`입니다.
2. 사용자 프로젝트에는 [표준 Cordova 앱 디렉터리 구조](https://cordova.apache.org/docs/en/latest/reference/cordova-cli/index.html#directory-structure)가 사용됩니다.

## <a name="build-the-plugin-into-your-android-app"></a>Android 앱에 플러그 인 빌드

1. 최신 Cordova 도구로 이 플러그 인을 가져옵니다. 플러그 인은 `after_compile` 단계로 자동 호출됩니다.

2. 플러그 인은 빌드 프로세스의 끝에 빌드된 apk(Android API 14+)의 Intune 사용 버전을 생성합니다. 빌드 출력에는 `[Project]-intunewrapped-[Build_Configuration].apk`(예: `helloWorld-intunewrapped-debug.apk`)가 포함됩니다.

> [!NOTE]
> 플러그 인은 gradle 빌드만 지원합니다.

특정 Cordova 후크가 `cordova run`에서 무시되도록 하는 [여기](https://issues.apache.org/jira/browse/CB-9434) 제출된 Cordova 버그로 인해, 명령줄에서 래핑된 앱을 실행하려면 다음을 수행해야 합니다.

```shell
$ cordova build
$ cordova run --nobuild
```

## <a name="sign-your-android-app"></a>Android 앱 서명

다음 위치에서 Cordova에 제공한 서명 정보를 플러그 인이 자동으로 인식합니다.

* platforms/android/debug-signing.properties
* platforms/android/release-signing.properties
* res/native/android/ant.properties

예상되는 형식에 대한 자세한 내용은 [정보 Cordova Gradle 서명 정보](https://cordova.apache.org/docs/en/latest/guide/platforms/android/#using-gradle) 참조하세요.

현재에는 `build.json` 또는 매개 변수를 통해 제공된 임의 위치에서 Cordova 빌드에 서명 정보를 제공하는 기능을 지원하지 않습니다.

## <a name="debugging-from-visual-studio"></a>Visual Studio에서 디버깅

앱을 처음 시작한 후 앱이 Intune에서 관리되고 있음을 알리는 대화 상자가 표시됩니다. "다시 표시 안 함"을 누르고 중단점을 누르려면 VS에서 디버그/실행 단추를 다시 클릭합니다.

## <a name="known-limitations"></a>알려진 제한 사항

### <a name="android"></a>Android

* MultiDex 지원은 완전하지 않습니다.
* 앱은 `minSdkVersion` 14 및 `targetSdkVersion` 24 이하여야 합니다. 현재에는 API 25가 대상인 앱을 지원하지 않습니다.
* V2 서명 기법을 사용하여 서명된 앱에 다시 서명할 수 없습니다. V2로 서명된 앱을 플러그 인이 래핑하면 래핑된 출력 .apk는 서명이 취소됩니다.
*
  * 다음을 `build-extras.gradle` 파일에 추가하여 Cordova의 기본 V2 서명을 사용하지 않도록 설정할 수 있습니다.

  ```gradle
  android {
      signingConfigs {
          release {
              v2SigningEnabled false
          }
          debug {
              v2SigningEnabled false
          }
      }
      buildTypes {
          release {
              signingConfig signingConfigs.release
          }
          debug {
              signingConfig signingConfigs.debug
          }
      }
  }
  ```

### <a name="ios"></a>iOS

* **Info.plist** 파일의 **CFBundleDocumentTypes** 노드에서 UTI 목록을 수정할 때마다 다시 빌드하기 전에 동일한 plist 파일의 Imported UTI 섹션(**UTImportedTypeDeclarations** 노드)에서 Intune UTI를 제거해야 합니다. 모든 Intune UTI는 접두사 `com.microsoft.intune.mam`으로 시작합니다.

* 또한 Cordova 프로젝트에서 Cordova용 Intune 앱 SDK 플러그 인을 제거하려는 경우에는 iOS 플랫폼도 제거했다가 다시 추가해야 .xcodeproj 및.plist 파일에 있는 Intune 구성을 실행 취소할 수 있습니다.

