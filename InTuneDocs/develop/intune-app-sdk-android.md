---
# required metadata

title: Android용 Microsoft Intune 앱 SDK 개발자 가이드 | Microsoft Intune
description:
keywords:
author: Msmbaldwin
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 0100e1b5-5edd-4541-95f1-aec301fb96af

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Android용 Microsoft Intune 앱 SDK 개발자 가이드

> [!NOTE] 먼저 SDK의 현재 기능 및 지원되는 각 플랫폼에서 통합을 준비하는 방법을 설명하는 [Intune 앱 SDK 개요](intune-app-sdk.md) 항목을 읽어보는 것이 좋습니다. 

# SDK에 포함된 내용 

Android용 Intune 앱 SDK는 외부 종속성이 없는 표준 Android 라이브러리입니다. 
SDK는 다음으로 구성되어 있습니다.  

* **`Microsoft.Intune MAM.SDK.jar`**: Microsoft Intune 회사 포털 앱과의 상호 운용성을 지원할 뿐 아니라 앱 내에서 MAM을 사용하도록 설정하는 데 필요한 인터페이스입니다. 앱에서 이 인터페이스를 Android 라이브러리 참조로 지정해야 합니다.

*  **`Microsoft.Intune.MAM.SDK.Support.v4.jar`**: Android v4 지원 라이브러리를 활용하는 앱 내에서 MAM을 사용하도록 설정하는 데 필요한 인터페이스입니다.  이러한 지원이 필요한 앱은 이 jar 파일을 직접 참조해야 합니다. 

* **`Microsoft.Intune.MAM.SDK.Support.v7.jar`**: Android v7 지원 라이브러리를 활용하는 앱 내에서 MAM을 사용하도록 설정하는 데 필요한 인터페이스입니다.   이러한 지원이 필요한 앱은 이 jar 파일을 직접 참조해야 합니다.

* **리소스 디렉터리**: SDK에 사용되는 리소스(예: 문자열)입니다. 

* **`Microsoft.Intune.MAM.SDK.aar`**: Support.V4 jar 및 Support.V7 jar를 제외한 SDK 구성 요소입니다. 빌드 시스템에서 AAR 파일을 지원하는 경우 이 파일을 개별 구성 요소 대신 사용할 수 있습니다.

* **`AndroidManifest.xml`**: 추가 진입점이며 라이브러리 요구 사항입니다. 

* **`THIRDPARTYNOTICES.TXT`**: 앱에 컴파일될 타사 및/또는 OSS 코드를 확인하는 특성 알림입니다. 

# 요구 사항 

Intune 앱 SDK는 컴파일된 Android 프로젝트이므로 일반적으로 최소 또는 대상 API 버전에 대해 앱에서 사용되는 Android 버전에 관계가 없습니다. 이 SDK는 Android API 14(Android 4.0+)부터 Android 24까지 지원합니다. 

# Intune 앱 SDK의 작동 방식 

Intune 앱 SDK가 작동하려면 앱 관리 정책을 사용하도록 앱의 소스 코드를 변경해야 합니다. 이렇게 하려면 접두사 `MAM`. SDK 클래스는 Android 기본 클래스와 앱에서 파생된 고유 버전의 Android 기본 클래스 사이에 존재합니다.  활동을 예제로 사용하면 `Activity ->MAMActivity->AppSpecificActivity`.

`AppSpecificActivity`가 예를 들어 `super.onCreate())`와 같은 상위와 상호 작용하려는 경우 `MAMActivity`는 상속 계층 구조에 포함되며 다수의 메서드를 대체하기는 하지만 상위 클래스에 해당합니다. Android 앱은 단일 모드를 가지며 Context 개체를 통해 전체 시스템에 액세스합니다.  반면, Intune 앱 SDK를 통합한 앱은 계속해서 Context 개체를 통해 시스템에 액세스하지만 사용된 기본 Activity에 따라 Context 개체가 Android에서 제공되거나 제한된 시스템 뷰와 Android 제공 Context 사이를 지능적으로 멀티플렉싱하므로 이중 모드를 가집니다.

Android용 Intune 앱 SDK가 작동하려면 장치에 MAM 정책을 사용하기 위한 회사 포털 앱이 있어야 합니다. 회사 포털 앱이 없을 때는 MAM 지원 앱의 동작이 변경되지 않고 다른 모바일 앱처럼 작동합니다. 회사 포털이 설치되어 있고 사용자에 대한 정책이 있는 경우에는 SDK 진입점이 비동기적으로 초기화됩니다. 초기화는 Android에서 프로세스가 처음 만들어질 때만 필요합니다. 초기화하는 동안 회사 포털 앱과 연결이 설정되고 앱 제한 정책이 다운로드됩니다.  

# Intune 앱 SDK와 통합하는 방법
 
이전의 개략적인 설명대로, SDK가 작동하려면 앱 관리 정책을 사용하도록 앱의 소스 코드를 변경해야 합니다. 앱에서 MAM을 사용하도록 설정하는 데 필요한 단계는 다음과 같습니다. 

## 클래스, 메서드, 작업 등을 동등한 MAM 항목으로 바꾸기(필수) 

* Android 기본 클래스를 동등한 MAM 클래스로 바꿔야 합니다. 이렇게 하려면 아래 표에 나온 클래스의 모든 인스턴스를 동등한 Intune 앱 SDK 클래스로 바꾸세요.  

    | Android 클래스 | Intune 앱 SDK 대체 항목 |
    |--|--|
    | android.app.Activity | MAMActivity |
    | android.app.ActivityGroup | MAMActivityGroup |
    | android.app.AliasActivity | MAMAliasActivity |
    | android.app.Application | MAMApplication |
    | android.app.DialogFragment | MAMDialogFragment |
    | android.app.ExpandableListActivity | MAMExpandableListActivity |
    | android.app.Fragment | MAMFragment |
    | android.app.IntentService | MAMIntentService |
    | android.app.LauncherActivity | MAMLauncherActivity |
    | android.app.ListActivity | MAMListActivity |
    | android.app.NativeActivity | MAMNativeActivity |
    | android.app.PendingIntent | MAMPendingIntent |
    | android.app.Service | MAMService |
    | android.app.TabActivity | MAMTabActivity |
    | android.app.TaskStackBuilder | MAMTaskStackBuilder |
    | android.app.backup.BackupAgent | MAMBackupAgent |
    | android.app.backup.BackupAgentHelper | MAMBackupAgentHelper |
    | android.app.backup.FileBackupHelper | MAMFileBackupHelper |
    | android.app.backup.SharePreferencesBackupHelper | MAMSharedPreferencesBackupHelper |
    | android.content.BroadcastReceiver | MAMBroadcastReceiver |
    | android.content.ContentProvider | MAMContentProvider |
    | android.os.Binder | MAMBinder* |
    | android.provider.DocumentsProvider | MAMDocumentsProvider |
    | android.preference.PreferenceActivity | MAMPreferenceActivity |

    * Binder가 AIDL 인터페이스에서 생성되지 않는 경우에만 Binder를 MAMBinder와 바꿔야 합니다.

    **Microsoft.Intune.MAM.SDK.Supp또는t.v4.jar**:

    | Android 클래스 Intune MAM | SDK 대체 항목 |
    |--|--|
    | android.support.v4.app.DialogFragment | MAMDialogFragment
    | android.support.v4.app.FragmentActivity | MAMFragmentActivity
    | android.support.v4.app.Fragment | MAMFragment
    | android.support.v4.app.TaskStackBuilder | MAMTaskStackBuilder
    | android.support.v4.content.FileProvider | MAMFileProvider
    
    **Microsoft.Intune.MAM.SDK.Supp또는t.v7.jar**:

    |Android 클래스 | Intune MAM SDK 대체 항목 |
    |--|--|
    |android.support.v7.app.ActionBarActivity | MAMActionBarActivity |


* 동등한 MAM 항목으로 재정의된 Android 진입점을 사용할 때는 이 진입점 수명 주기의 대체 버전을 사용해야 합니다(단, `MAMApplication`클래스의 경우 예외).

    예를 들어 `MAMActivity`를 재정의하고 `onCreate` 를 호출하는 대신 `super.onCreate`에서 파생하는 경우 Activity는 `onMAMCreate` 를 재정의하고`uper.onMAMCreate`. 이렇게 하면 경우에 따라 Activity 시작이 제한됩니다. 

# 앱 참여를 요구하는 기능 사용 

SDK가 자체적으로 구현할 수 없는 일부 정책이 있습니다. 앱이 이러한 기능을 위한 동작을 제어할 수 있게 만들기 위해 아래에 포함된 `AppPolicy` 인터페이스에서 찾을 수 있는 API를 노출합니다.  

    /**
     * External facing app policies.
     */
    public interface AppPolicy {
        /**
         * Restrict where an app can save personal data.
         * 
         * @return True if the app is allowed to save to personal data stores;
         *         false otherwise.
         */
        boolean getIsSaveToPersonalAllowed();
    
        /**
         * Check if policy prohibits saving to a content provider location.
         * 
         * @param location
         *            a content URI to check
         * @return True if location is not a content URI or if policy does not 
         *         prohibit saving to the content location.
         */
        boolean getIsSaveToLocationAllowed(android.net.Uri location); 
    
        /**
         * Whether the SDK PIN prompt is enlightened for the app.
         * 
         * @return True if the PIN is enabled. False otherwise.
         */
        boolean getIsPinRequired();
        /**
         * Whether the Intune Managed Browser is required to open web links.
         *
         * @return True if the Managed Browser is required, false otherwise
         */
        boolean getIsManagedBrowserRequired();
    }

## 앱 저장 동작을 IT 관리자가 제어할 수 있게 설정

다수의 앱에서는 최종 사용자가 로컬에서나 다른 서비스에 파일을 저장할 수 있게 하는 기능을 구현합니다. Intune 앱 SDK에서는 IT 관리자가 조직에 적합하다고 판단하는 대로 정책 제한을 적용하여 데이터 누출을 방지할 수 있습니다.  관리자가 제어할 수 있는 정책 중 하나는 최종 사용자에게 개인 데이터 저장소에 저장하도록 허용하는지 여부입니다. 개인 데이터 저장소에는 로컬 위치, SD 카드, 백업 서비스 등이 포함됩니다. 이 기능을 사용하려면 앱 참여가 필요합니다. 앱에서 직접 개인 저장소나 클라우드 위치에 저장하는 것이 허용되는 경우에는 이 기능을 구현해야만 IT 관리자가 특정 위치에 저장하는 작업을 허용할지 여부를 제어할 수 있습니다. 아래 API는 현재 관리 정책에 따라 개인 저장소에 저장하는 작업이 허용되는지 여부를 앱에 알립니다. 그러면 앱에서는 최종 사용자가 앱을 통해 사용할 수 있는 개인 데이터 저장소를 인식하므로 정책을 적용할 수 있습니다.  

정책이 적용되는지 여부를 확인하려면 앱에서 다음을 호출할 수 있습니다. 

    MAMComponents.get(AppPolicy.class).getIsSaveToPersonalAllowed();

**참고**: MAMComponents.get(AppPolicy.class)는 장치 또는 앱이 관리 중인 상태가 아니더라도 항상 null이 아닌 앱 정책을 반환합니다. 

## 앱에서 PIN 정책 필요성을 감지하도록 허용
 
 Intune 앱 SDK에서 기능이 중복되지 않게 하기 위해 앱에서 일부 기능을 사용하지 않도록 설정하는 데 사용할 수 있는 추가 정책이 있습니다. 예를 들어 앱에 고유한 PIN 사용자 환경이 있고 SDK가 최종 사용자에게 PIN 입력을 요구하는 경우 앱의 해당 기능을 사용하지 않도록 설정해야 할 수 있습니다. 

정기적으로 PIN 입력을 요구하도록 PIN 정책이 구성되었는지 확인하려면 앱에서 다음을 호출할 수 있습니다. 

    MAMComponents.get(AppPolicy.class).getIsPinRequired();

## SDK에서 알림 등록  

Intune 앱 SDK는 IT 관리자가 원격 초기화 정책과 같은 특정 정책을 사용하는 경우 앱에서 동작을 제어하도록 만들 수 있습니다. 그러려면 `MAMNotificationReceiver` 클래스를 만들고 `MAMNotificationReceiverRegistry`. 다음 예제에 나온 대로 수신기 및 수신기에서 수신할 알림 유형을  `App.onCreate`에 제공하면 됩니다.
 
    @Override
      public void onCreate() {
            super.onCreate();
    MAMComponents.get(MAMNotificationReceiverRegistry.class).registerReceiver(
    new ToastNotificationReceiver(), MAMNotificationType.WIPE_USER_DATA);
    }

`MAMNotificationReceiver` 는 알림을 수신합니다. 일부 알림은 SDK에서 직접 처리되고, 일부 알림의 경우 앱 참여가 필요합니다. 앱은 알림에서 true 또는 false를 반환해야 합니다. 알림의 결과로 시도한 일부 작업에서 오류가 발생하지 않는 한 앱은 항상 true를 반환해야 합니다. 이 오류(예: 앱에서 사용자 데이터를 초기화하지 못했다고 나타나는 경우)는 Intune 서비스에 보고될 수 있습니다. `MAMNotificationReceiver.onReceive`에서 차단해도 안전합니다. 해당 콜백이 UI 스레드에서 실행되고 있지 않습니다. 

아래에는 SDK에 정의된 'MAMNotificationReceiver 인터페이스가 포함되어 있습니다. 

    /**
     * The SDK is signaling that a MAM event has occurred. 
     * 
     */
    public interface MAMNotificationReceiver {
      /**
      * A notification was received.
      * 
      * @param notification
      *            The notification that was received.
    * @return The receiver should return true if it handled the
    *   notification without error (or if it decided to ignore the
    *   notification). If the receiver tried to take some action in 
    *   response to the notification but failed to complete that
      *   action it should return false.
      */
      boolean onReceive(MAMNotification notification);
    }

다음과 같은 알림이 앱에 전송되고, 일부 알림의 경우 앱 참여가 필요할 수 있습니다. 

* **`WIPE_USER_DATA` 알림**: 이 알림은 `MAMUserNotification` 클래스를 통해 전송됩니다. 이 알림이 수신되면 앱에서는 `MAMUserNotification`. 이 알림은 현재 Intune 서비스 등록 취소 과정에 전송됩니다. 사용자의 기본 이름은 일반적으로 등록 프로세스 동안 지정됩니다. 이 알림에 등록하는 경우 앱에서 모든 사용자 데이터가 삭제되었는지 확인해야 합니다. 이 알림에 등록하지 않는 경우는 기본 선별적 초기화 동작이 수행됩니다. 

* **`WIPE_USER_AUXILIARY_DATA` 알림**: Intune 앱 SDK에서 기본 초기화를 수행하며 초기화 발생 시 일부 보조 데이터도 제거되도록 하려면 앱에서 이 알림을 등록할 수 있습니다.  

* **`REFRESH_POLICY` 알림**: 이 알림은 추가 정보 없이 MAMNotification을 통해 전송됩니다. 이 알림이 수신되면 캐시된 정책은 무효화된 것으로 취급해야 하며 따라서 해당 정책이 무엇인지 확인해야 합니다. 이 작업은 일반적으로 SDK에서 처리되지만 정책이 영구적인 방식으로 사용되는 경우에는 앱에서 처리해야 합니다. 

## 보류 중인 의도 및 메서드 

MAM 진입점 중 하나에서 파생한 후에는 작업 시작을 위해 일반적으로 `PackageManager`등을 사용할 때처럼 Context를 사용할 수 있습니다.  `PendingIntents` 는 이 규칙의 예외입니다. 이러한 클래스를 호출할 때는 클래스 이름을 변경해야 합니다. 예를 들어 `PendingIntent.get*`을 사용하는 대신 `MAMPendingIntents.get*`을 사용해야 합니다. 

일부 경우, Android 클래스에서 사용할 수 있는 메서드가 MAM 대체 클래스에서 최종본으로 표시되어 있습니다. 이 경우 MAM 대체 클래스는 대신 재정의할 유사한 이름의 메서드(일반적으로 접미사 "MAM"이 붙음)를 제공합니다. 예를 들어 `ContentProvider.query`를 재정의하는 대신 `MAMContentProvider.queryMAM`. Java 컴파일러는 동등한 MAM 메서드 대신 원래 메서드가 실수로 재정의되는 것을 방지하기 위해 최종 제한을 적용해야 합니다. 

# 백업 데이터 보호 

Android Marshmallow(API 23) 현재, Android에는 앱이 데이터를 백업하는 두 가지 방법이 있습니다. 이러한 옵션을 앱에서 사용할 수 있으며 여러 단계를 거쳐 MAM 데이터 보호가 적절하게 적용되도록 해야 합니다. 아래 표를 검토하면 올바른 데이터 보호 동작에 필요한 적절한 작업에 대해 빠르게 개요를 살펴볼 수 있습니다.  또한 Android 백업에 대한 자세한 내용은 [Android 개발자 데이터 백업 가이드](http://developer.android.com/guide/topics/data/backup.html.). 

## 자동 전체 백업

Android M에서 Android는 Android M 장치에서 실행할 때 대상 API와 관계없이 앱에 대해 자동 전체 백업을 제공하기 시작했습니다. `android:allowBackup` 특성이 false가 아닌 경우 앱은 해당 앱에 대해 필터링되지 않은 전체 백업을 수신합니다. 이로 인해 데이터 누출 위험이 발생하며, 따라서 아래 표의 개략적인 설명대로 SDK를 변경해야 데이터 보호를 적용할 수 있습니다.  고객 데이터를 제대로 보호하려면 아래의 지침을 따라야 합니다.  `android:allowBackup=false`를 설정하는 경우 앱은 운영 체제가 수행하는 백업을 위한 큐에 들어가지 않습니다. 또한 백업이 없으므로 MAM에 대해 수행할 추가 작업이 없습니다.
 
 ## "키/값" 백업

모든 API에서 이 옵션을 사용할 수 있으며, 이 옵션에는 `BackupAgent` 및 `BackupAgentHelper`. 

### BackupAgentHelper 사용

`BackupAgentHelper` 는 기본 Android 기능 및 MAM 통합 면에서 `BackupAgent`에 비해 훨씬 더 간단하게 구현할 수 있습니다. `BackupAgentHelper` 를 통해 개발자는 전체 파일 및 공유 기본 설정을 `FileBackupHelper` 또는 `SharedPreferencesBackupHelper`에 각각 등록할 수 있으며 이들 항목은 생성된 `BackupAgentHelper`에 추가됩니다. 

### BackupAgent 사용

`BackupAgent` 를 사용하면 백업되는 데이터에 대해 훨씬 더 명확히 지정할 수 있습니다. 하지만 이 옵션은 Android 백업 프레임워크를 활용할 수 없음을 의미합니다.  구현을 직접 수행하는 연습을 해야 하므로 MAM으로부터 데이터를 적절하게 보호하기 위해 필요한 추가 단계가 있습니다. 대부분의 작업을 개발자가 담당하게 되므로, MAM 통합이 약간 더 개입됩니다. 

#### 앱에 백업 에이전트가 없는 경우
  
다음은 `Android:allowbBackup =true`:

##### 구성 파일에 따라 전체 백업: 

매니페스트의 `com.microsoft.intune.mam.FullBackupContent` 메타데이터 태그 아래에 리소스를 제공합니다. 예를 들어 다음과 같습니다.
    `<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />`

`<application>` 태그에 `android:fullBackupContent="@xml/my_scheme"` 특성을 추가합니다. 여기서 `my_scheme`은 앱의 XML 리소스입니다. 

##### 예외 없는 전체 백업 

매니페스트에서 태그를 제공합니다. 예를 들면 다음과 같습니다. `<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:value="true" />` 
 
`<application>` 태그에 다음 특성을 추가합니다. `android:fullBackupContent="true"`

#### 앱에 백업 에이전트가 있는 경우

위에 나온 `BackupAgent` 및 `BackupAgentHelper` 섹션의 권장 사항을 따릅니다. 

Android M에서 손쉬운 백업을 제공하는 `MAMDefaultFullBackupAgent`를 사용하도록 전환하는 것이 좋습니다. 

### 백업하기 전에

백업을 시작하기 전에 백업하려는 파일 또는 데이터 버퍼가 실제로 백업 가능한지 확인해야 합니다. `MAMFileProtectionManager` 및 `MAMDataProtectionManager`에서 `isBackupAllowed` 함수를 사용하여 이를 확인할 수 있습니다. 파일 또는 데이터 버퍼가 백업하도록 허용되지 않은 경우에는 백업에 활용하려고 해서는 안 됩니다.

1단계에 확인한 파일의 ID를 백업하려는 경우에는 백업 도중 특정 시점에 데이터를 추출할 파일에 대해 `backupMAMFileIdentity(BackupDataOutput data, File … files)`를 호출해야 합니다. 그러면 자동으로 새 백업 엔터티가 생성되고 이 엔터티가 `BackupDataOutput` 에 작성됩니다. 이러한 엔터티는 복원 시 자동으로 사용됩니다. 

## Azure ADAL(Active Directory Authentication Library) 구성  

SDK가 작동하려면 인증 및 조건부 시작 시나리오를 위한 ADAL이 필요하며, 이 경우 앱에 일부 Azure Active Directory 구성이 있어야 합니다. 구성 값은 `AndroidManifest` 메타데이터를 통해 SDK에 전달됩니다. 앱을 구성하고 적절한 인증을 사용하려면 다음을 `AndroidManifest`. 이러한 일부 구성은 앱에서 일반적으로 인증에 ADAL을 사용하는 경우에만 필요합니다. 이 경우 앱이 AAD를 사용하여 자체를 등록하는 데 사용하는 특정 값이 필요합니다. 이것은 AAD에서 별개의 두 등록 값(앱의 값 및 SDK의 값)을 인식하기 때문에 최종 사용자에게 인증을 요구하는 메시지가 두 번 나타나는 일이 없도록 하려는 것입니다. 

        <meta-data
            android:name="com.microsoft.intune.mam.aad.Authority"
            android:value="https://AAD authority/" />
        <meta-data
            android:name="com.microsoft.intune.mam.aad.ClientID"
            android:value="your-client-ID-GUID" />
        <meta-data
            android:name="com.microsoft.intune.mam.aad.NonBrokerRedirectURI"
            android:value="your-redirect-URI" />
        <meta-data
            android:name="com.microsoft.intune.mam.aad.SkipBroker"
            android:value="[true | false]" />

GUID의 앞이나 뒤에 중괄호가 와서는 안 됩니다.

### 일반적인 ADAL 구성 

다음은 위에서 설명한 값에 대한 일반적인 구성입니다. 

#### 앱이 ADAL을 통합하지 않는 경우

* AAD 계정이 구성된 원하는 환경으로 인증 기관을 설정해야 합니다.

* SkipBroker를 true로 설정해야 합니다.

#### 앱이 ADAL을 통합하는 경우

* AAD 계정이 구성된 원하는 환경으로 인증 기관을 설정해야 합니다.

* 클라이언트 ID는 앱의 클라이언트 ID로 설정해야 합니다.

* `NonBrokerRedirectURI` 를 앱의 유효한 리디렉션 URI로 설정해야 합니다.
    * Or `urn:ietf:wg:oauth:2.0:oob` 를 유효한 AAD 리디렉션 URI로 구성해야 합니다.

* SkipBroker를 false로 설정하거나 비워 둬야 합니다.

* 브로커 리디렉션 URI를 허용하도록 AAD를 구성해야 합니다.

#### 앱이 ADAL을 통합하지만 AAD Authenticator 앱을 지원하지 않는 경우

* AAD 계정이 구성된 원하는 환경으로 인증 기관을 설정해야 합니다.

* 클라이언트 ID는 앱의 클라이언트 ID로 설정해야 합니다.

* `NonBrokerRedirectURI` 를 앱의 유효한 리디렉션 URI로 설정해야 합니다.

    * Or `urn:ietf:wg:oauth:2.0:oob` 를 유효한 AAD 리디렉션 URI로 구성해야 합니다.

## SDK에서 로깅을 사용하는 방법 

로깅은 `java.util.logging` 프레임워크를 통해 수행됩니다. 로그를 받으려면 [Java 기술 가이드](http://docs.oracle.com/javase/6/docs/technotes/guides/logging/overview.html). 앱에 따라 다르지만 일반적으로 `App.onCreate` 가 로깅을 시작하는 가장 좋은 위치입니다. 로그 메시지는 난독 처리될 수 있는 클래스 이름을 키로 사용합니다.

# 알려진 플랫폼 제한 사항 

## 파일 크기 제한 

Android에서는 Dalvik 실행 파일 형식의 제한 사항으로 인해 ProGuard 없이 실행되는 대규모 코드 기반의 경우 문제가 될 수 있습니다. 특히 다음과 같은 제한 사항이 발생할 수 있습니다. 

* 필드의 경우 65K로 제한됩니다.

* 메서드의 경우 65K로 제한됩니다.

여러 프로젝트를 포함하는 경우 모든 android:package는 라이브러리가 추가됨에 따라 필드 수를 현저히 늘리는 R의 복사본을 가지게 됩니다. 다음 권장 사항은 이러한 제한을 완화하는 데 도움이 될 수 있습니다.
 
* 가능한 경우 모든 라이브러리 프로젝트에서 동일한 android:package를 공유해야 합니다. 이렇게 하면 순수하게 빌드 시 문제가 되므로 필드에서 산발적으로 장애가 발생하지 않습니다.   또한 최신 버전의 Android SDK는 DEX 파일을 전처리하여 일부 중복성을 제거합니다. 이를 통해 필드 간격이 더욱 줄어듭니다.

* 사용 가능한 최신 Android SDK 빌드 도구를 사용합니다.

* 불필요한 라이브러리 및 사용하지 않는 라이브러리(예: `android.support.v4`)를 모두 제거합니다.

## 정책 적용 제한 사항

**화면 캡처**: SDK는 이미 Activity.onCreate 처리한 작업에서 새로운 화면 캡처 설정 값을 적용할 수 없습니다. 이로 인해 앱에서 스크린샷을 사용하지 않도록 구성했지만 여전히 스크린샷을 만들 수 있는 기간이 발생합니다.

**콘텐츠 확인자 사용*: 전송 또는 수신 정책이 다른 앱에서 콘텐츠 확인자를 사용하여 콘텐츠 공급자에 액세스하는 것을 차단하거나 부분적으로 차단할 수 있습니다. 이로 인해 ContentResolver 메서드에서 null이 반환되거나 오류 값이 발생합니다(예: 차단된 경우 `openOutputStream` 에서 `FileNotFoundException` 이 발생함). 앱에서는 콘텐츠 확인자를 통한 데이터 쓰기가 정책으로 인해 실패했거나 정책으로 인해 실패할 것인지 여부를 다음을 호출하여 확인할 수 있습니다.

    MAMComponents.get(AppPolicy.class).getIsSaveToLocationAllowed(contentURI)

**내보낸 서비스**: Intune 앱 SDK에 포함된 `AndroidManifest.xml` 파일에는 `MAMNotificationReceiverService`가 들어 있습니다. 내보낸 서비스가 이 서비스여야 회사 포털에서 지원 앱에 알림을 보낼 수 있습니다. 이 서비스는 호출자를 검사하여 회사 포털만 알림을 보낼 수 있는지 확인합니다. 

# 권장되는 Android 모범 사례 

Intune SDK는 Android API에서 제공되는 계약을 유지하지만, 정책 적용의 결과로 오류 상태가 더 빈번하게 트리거될 수 있습니다. 다음 Android 모범 사례는 오류 가능성을 줄입니다. 

* null을 반환할 수 있는 Android SDK 함수가 null일 가능성이 높아졌습니다.  문제를 최소화하려면 올바른 위치에서 null 검사가 이루어지도록 합니다.

* 확인할 수 있는 기능은 SDK API를 통해 확인해야 합니다.

* 파생된 함수는 상위 클래스 버전을 통해 호출해야 합니다.

* API를 모호한 방식으로 사용해서는 안 됩니다. 예를 들어 requestCode 확인 없이 `Activity.startActivityForResult/onActivityResult` 를 사용하면 이상한 동작이 발생합니다.


<!--HONumber=May16_HO2-->


