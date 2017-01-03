---
title: "Android용 Microsoft Intune 앱 SDK 개발자 가이드 | Microsoft 문서"
description: "Android용 Microsoft Intune 앱 SDK를 사용하면 Android 앱에 Intune MAM(모바일 앱 관리)을 통합할 수 있습니다."
keywords: SDK
author: mtillman
manager: angrobe
ms.author: mtillman
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0100e1b5-5edd-4541-95f1-aec301fb96af
ms.reviewer: oydang
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b068da7685792757825a4bc0d555e28ee0168cb1
ms.openlocfilehash: ddfd4e8a23f1a7e20230c188ac8203a11e48c4a6


---


# <a name="microsoft-intune-app-sdk-for-android-developer-guide"></a>Android용 Microsoft Intune 앱 SDK 개발자 가이드

> [!NOTE]
> 먼저 SDK의 현재 기능 및 지원되는 각 플랫폼에서 통합을 준비하는 방법을 설명하는 [Intune 앱 SDK 개요](intune-app-sdk.md) 항목을 읽어보는 것이 좋습니다.

Android용 Microsoft Intune 앱 SDK를 사용하면 Android 앱에 Intune MAM(모바일 앱 관리)을 통합할 수 있습니다. MAM 지원 응용 프로그램은 Intune 앱 SDK와 통합된 응용 프로그램입니다. 이를 통해 IT 관리자는 Intune에서 앱을 적극적으로 관리할 때 모바일 앱에 정책을 배포할 수 있습니다.

## <a name="whats-in-the-sdk"></a>SDK에 포함된 내용

Android용 Intune 앱 SDK는 외부 종속성이 없는 표준 Android 라이브러리입니다. SDK는 다음 항목으로 구성됩니다.  

* **Microsoft.Intune.MAM.SDK.jar**: Intune 회사 포털 앱과의 상호 운용성 및 MAM을 사용하도록 설정하는 데 필요한 인터페이스입니다. 앱에서 이 인터페이스를 Android 라이브러리 참조로 지정해야 합니다.

* **Microsoft.Intune.MAM.SDK.Support.v4.jar**: Android v4 지원 라이브러리를 사용하는 앱 내에서 MAM을 사용하도록 설정하는 데 필요한 인터페이스입니다. 이러한 지원이 필요한 앱은 이 JAR 파일을 직접 참조해야 합니다.

* **Microsoft.Intune.MAM.SDK.Support.v7.jar**: Android v7 지원 라이브러리를 활용하는 앱 내에서 MAM을 사용하도록 설정하는 데 필요한 인터페이스입니다. 이러한 지원이 필요한 앱은 이 JAR 파일을 직접 참조해야 합니다.

* **리소스 디렉터리**: SDK에 사용되는 리소스(예: 문자열)입니다.

* **Microsoft.Intune.MAM.SDK.aar**: Support.V4 jar 및 Support.V7 JAR 파일을 제외한 SDK 구성 요소입니다. 빌드 시스템에서 AAR 파일을 지원하는 경우 이 파일을 개별 구성 요소 대신 사용할 수 있습니다.

* **AndroidManifest.xml**: 추가 진입점이며 라이브러리 요구 사항입니다.

* **THIRDPARTYNOTICES.TXT**: 앱에 컴파일될 타사 및/또는 OSS 코드를 확인하는 특성 알림입니다.

## <a name="requirements"></a>요구 사항

Intune 앱 SDK는 컴파일된 Android 프로젝트이므로 대개 최소 또는 대상 API 버전에 대해 앱에서 사용되는 Android 버전의 영향을 받지 않습니다. 이 SDK는 Android API 14(Android 4.0+)부터 Android API 24까지 지원합니다.

Android용 Intune 앱 SDK가 작동하려면 장치에 MAM 정책을 사용하기 위한 [회사 포털](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) 앱이 있어야 합니다. 장치 등록 없이 MAM을 사용하기 위해 사용자가 회사 포털 앱을 통해 장치를 등록할 필요가 *없습니다*.


## <a name="how-the-intune-app-sdk-works"></a>Intune 앱 SDK의 작동 방식

###<a name="entry-points"></a>진입점

Intune 앱 SDK가 작동하려면 앱 관리 정책을 사용하도록 Intune 앱의 소스 코드를 변경해야 합니다. 이렇게 하려면 Android 기본 클래스를 이름에 접두사 `MAM`이 포함된 동등한 Intune 기본 클래스와 바꿉니다. SDK 클래스는 Android 기본 클래스와 앱에서 파생된 고유 버전의 Android 기본 클래스 사이에 존재합니다. 활동의 예를 살펴보자면, `Activity` > `MAMActivity` > `AppSpecificActivity`와 같은 상속 계층이 생성됩니다.

예를 들어 `AppSpecificActivity`가 `super.onCreate()`를 호출하는 등 부모와 상호 작용하는 경우에는 `MAMActivity`가 슈퍼 클래스입니다.

일반적인 Android 앱은 단일 모드를 가지며 [Context](https://developer.android.com/reference/android/content/Context.html) 개체를 통해 시스템에 액세스할 수 있습니다. 반면, Intune 앱 SDK를 통합한 앱은 이중 모드를 가집니다. 이러한 앱은 `Context` 개체를 통해 시스템에 계속 액세스합니다. 사용되는 기본 `Activity`에 따라 `Context` 개체는 Android에서 제공될 수도 있고, Android 제공 `Context` 및 시스템의 제한된 뷰 간에 지능적으로 멀티플렉싱될 수도 있습니다.

Android [진입점](https://developer.android.com/guide/components/fundamentals.html)이 동등한 MAM 항목으로 재정의된 경우 이 진입점 수명 주기의 MAM 버전을 사용해야 합니다(단, `MAMApplication` 클래스의 경우는 예외).

예를 들어 `onCreate`를 재정의하고 `super.onCreate`를 호출하는 대신 `MAMActivity`에서 파생하는 경우 `Activity`는 `onMAMCreate`를 재정의하고 `super.onMAMCreate`를 호출해야 합니다. 이렇게 하면 Intune이 특정한 경우 `Activity` 시작을 제한하는 등의 조치를 취할 수 있습니다.


###<a name="sdk-permissions"></a>SDK 권한

Intune 앱 SDK에는 SDK를 통합하는 앱에 대한 세 가지 [Android 시스템 권한](https://developer.android.com/guide/topics/security/permissions.html)이 있어야 합니다.

* `android.permission.GET_ACCOUNTS`(필요한 경우 런타임에 요청됨)

* `android.permission.MANAGE_ACCOUNTS`

* `android.permission.USE_CREDENTIALS`

조정된 인증을 수행하려면 Azure [ADAL](https://azure.microsoft.com/en-us/documentation/articles/active-directory-authentication-libraries/)(Active Directory Authentication Library)에 이러한 권한이 필요합니다. 이러한 사용 권한이 앱에 부여되지 않거나 사용자에 의해 취소될 경우 브로커(회사 포털 앱)가 필요한 인증 흐름을 사용할 수 없습니다.


###<a name="company-portal-app"></a>회사 포털 앱

회사 포털 앱이 필요한 이유는 무엇인가요? 회사 포털 앱이 장치에 설치되고 Intune 서비스에서 사용자에 대한 응용 프로그램 제한 정책을 검색한 경우에는 SDK 진입점이 비동기적으로 초기화됩니다. Android에서 초기에 프로세스를 만들 때만 초기화를 수행하면 됩니다. 초기화하는 동안 회사 포털 앱과의 연결이 설정되고 앱에서 정책이 검색됩니다.  

> [!NOTE]
> 회사 포털 앱이 장치에 없으면 Intune 지원 앱의 동작이 변경되지 않으며 앱이 일반 앱처럼 동작합니다.


## <a name="how-to-integrate-with-the-intune-app-sdk"></a>Intune 앱 SDK와 통합하는 방법

이전의 설명대로, SDK가 작동하려면 앱 관리 정책을 사용하도록 앱의 소스 코드를 변경해야 합니다. 앱에서 MAM을 사용하도록 설정하는 데 필요한 단계는 다음과 같습니다.

### <a name="replace-classes-methods-and-activities-with-their-mam-equivalent-required"></a>클래스, 메서드, 작업 등을 동등한 MAM 항목으로 바꾸기(필수)

Android 기본 클래스를 동등한 개별 MAM 클래스로 바꿔야 합니다. 이렇게 하려면 아래 표에 나와 있는 클래스의 모든 인스턴스를 찾아서 동등한 Intune 앱 SDK 클래스로 바꾸세요.

| Android 기본 클래스 | Intune 앱 SDK 대체 항목 |
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
| android.app.PendingIntent | MAMPendingIntent* |
| android.app.Service | MAMService |
| android.app.TabActivity | MAMTabActivity |
| android.app.TaskStackBuilder | MAMTaskStackBuilder |
| android.app.backup.BackupAgent | MAMBackupAgent |
| android.app.backup.BackupAgentHelper | MAMBackupAgentHelper |
| android.app.backup.FileBackupHelper | MAMFileBackupHelper |
| android.app.backup.SharePreferencesBackupHelper | MAMSharedPreferencesBackupHelper |
| android.content.BroadcastReceiver | MAMBroadcastReceiver |
| android.content.ContentProvider | MAMContentProvider |
| android.os.Binder | MAMBinder(Binder가 AIDL(Android Interface Definition Language) 인터페이스에서 생성되지 않은 경우에만 필요함) |
| android.provider.DocumentsProvider | MAMDocumentsProvider |
| android.preference.PreferenceActivity | MAMPreferenceActivity |


**Microsoft.Intune.MAM.SDK.Supp또는t.v4.jar**:

| Android 클래스 Intune MAM | Intune 앱 SDK 대체 항목 |
|--|--|
| android.support.v4.app.DialogFragment | MAMDialogFragment
| android.support.v4.app.FragmentActivity | MAMFragmentActivity
| android.support.v4.app.Fragment | MAMFragment
| android.support.v4.app.TaskStackBuilder | MAMTaskStackBuilder
| android.support.v4.content.FileProvider | MAMFileProvider

**Microsoft.Intune.MAM.SDK.Supp또는t.v7.jar**:

|Android 클래스 | Intune 앱 SDK 대체 항목 |
|--|--|
|android.support.v7.app.ActionBarActivity | MAMActionBarActivity |

>[!NOTE]
>주의 - Android [진입점](https://developer.android.com/guide/components/fundamentals.html)이 동등한 MAM 항목으로 재정의된 경우 이 진입점 수명 주기의 MAM 버전을 사용해야 합니다(단, `MAMApplication` 클래스의 경우는 예외).
>
>예를 들어 `onCreate`를 재정의하고 `super.onCreate`를 호출하는 대신 `MAMActivity`에서 파생하는 경우 `Activity`는 `onMAMCreate`를 재정의하고 `super.onMAMCreate`를 호출해야 합니다. 이렇게 하면 Intune이 특정한 경우 `Activity` 시작을 제한하는 등의 조치를 취할 수 있습니다.

#### <a name="pendingintent-classes-and-renamed-methods"></a>PendingIntent 클래스 및 이름이 바뀐 메서드

MAM 진입점 중 하나에서 파생한 후에는 일반적인 방식으로 `Context`를 사용하는 것이 안전합니다. 예를 들어 `Activity` 클래스를 시작하고 `PackageManager`를 사용할 수 있습니다.  

`PendingIntent` 클래스는 이 규칙의 예외입니다. 이러한 클래스를 호출할 때는 클래스 이름을 변경해야 합니다. 예를 들어 `PendingIntent.get*` 대신 `MAMPendingIntent.get*` 메서드를 사용해야 합니다. 그런 다음 결과로 생성된 `PendingIntent`를 일반적인 방식으로 사용할 수 있습니다.

일부 경우, Android 클래스에서 사용할 수 있는 메서드가 MAM 대체 클래스에서 최종본으로 표시되어 있습니다. 이 경우 MAM 대체 클래스는 대신 재정의할 유사한 이름의 메서드(일반적으로 접미사 `MAM`이 붙음)를 제공합니다. 예를 들어 `ContentProvider.query`를 재정의하는 대신 `MAMContentProvider.queryMAM`. Java 컴파일러는 동등한 MAM 메서드 대신 원래 메서드가 실수로 재정의되는 것을 방지하기 위해 최종 제한을 적용해야 합니다.

###<a name="enable-features-that-require-app-participation"></a>앱 참여를 요구하는 기능 사용

SDK는 일부 정책을 자체적으로 구현할 수 없습니다. 앱은 다음의 `AppPolicy` 인터페이스에서 찾을 수 있는 여러 가지 API를 사용하여 이러한 기능을 수행하기 위한 동작을 제어할 수 있습니다.

```
/**
 * External facing application policies.
 */
public interface AppPolicy {

/**
 * Restrict where an app can save personal data.
 * <strong>This function is now deprecated. Please use {@link #getIsSaveToLocationAllowed(SaveLocation, String)} instead</strong>
 * @return True if the app is allowed to save to personal data stores; false otherwise.
 */
@Deprecated
boolean getIsSaveToPersonalAllowed();

/**
 * Check if policy prohibits saving to a content provider location.
 *
 * @param location
 *            a content URI to check
 * @return True if location is not a content URI or if policy does not prohibit saving to the content location.
 */
boolean getIsSaveToLocationAllowed(Uri location);

/**
 * Determines if the SaveLocation passed in can be saved to by the username associated with the cloud service.
 *
 * @param service
 *           see {@link SaveLocation}.
 * @param username
 *           the username/email associated with the cloud service being saved to. Use null if a mapping between the AAD username and the cloud service username does not exist or the username is not known.
 * @return true if the location can be saved to by the identity, false if otherwise.
 */
boolean getIsSaveToLocationAllowed(SaveLocation service, String username);

/**
 * Whether the SDK PIN prompt is enabled for the app.
 *
 * @return True if the PIN is enabled. False otherwise.
 */
boolean getIsPinRequired();

/**
 * Whether the Intune Managed Browser is required to open web links.
 * @return True if the Managed Browser is required, false otherwise
 */
boolean getIsManagedBrowserRequired();

/**
 * Check if policy allows Contact sync to local contact list.
 *
 * @return True if Contact sync is allowed to save to local contact list; false otherwise.
 */
boolean getIsContactSyncAllowed();

/**
 * Return the policy in string format to the app.
 *  
 * @return The string representing the policy.
 */
String toString();


}

```

### <a name="enable-it-control-over-app-saving-behavior"></a>앱 저장 동작을 IT 부서가 제어할 수 있게 설정

다수의 앱에서는 사용자가 로컬에서나 클라우드 저장소 서비스에 파일을 저장할 수 있게 하는 기능을 구현합니다. Intune 앱 SDK에서는 IT 관리자가 조직에 적합하다고 판단하는 대로 정책 제한을 적용하여 데이터 누수를 방지할 수 있습니다.  IT 부서가 제어할 수 있는 정책 중 하나는 사용자에게 관리되지 않는 "개인" 데이터 저장소에 저장하도록 허용하는지 여부입니다. 개인 데이터 저장소에는 로컬 위치, SD 카드, 타사 백업 서비스 등이 포함됩니다.

이 기능을 사용하려면 앱 참여가 필요합니다. 앱에서 직접 개인 저장소나 클라우드 위치에 저장하는 것이 허용되는 경우에는 이 기능을 구현해야만 IT 관리자가 특정 위치에 저장하는 작업을 허용할지 여부를 제어할 수 있습니다.   

정책이 적용되는지 여부를 확인하기 위해 앱은 다음과 같은 호출을 수행할 수 있습니다. 이 호출을 통해 앱은 현재 Intune 관리자의 정책이 개인 저장소에 대한 저장을 허용하는지 여부를 확인할 수 있습니다. 그러면 앱에서는 사용자가 앱을 통해 사용할 수 있는 개인 데이터 저장소를 인식하므로 정책을 적용할 수 있습니다.

```
MAMComponents.get(AppPolicy.class).getIsSaveToPersonalAllowed();
```

> [!NOTE]
> `MAMComponents.get(AppPolicy.class)`은 장치 또는 앱에 Intune 관리 정책이 적용되지 않더라도 항상 Null이 아닌 앱 정책을 반환합니다.

### <a name="let-the-app-detect-if-a-pin-policy-is-required"></a>앱이 PIN 정책 필요 여부를 검색하도록 허용

일부 Intune 앱 제한 사항의 경우 Intune 앱 SDK에서 기능이 중복되지 않게 하기 위해 앱에서 일부 기능을 사용하지 않도록 설정할 수 있습니다. 예를 들어 앱에 고유한 PIN 사용자 환경이 있고 SDK가 사용자에게 PIN 입력을 요구하도록 설정되어 있는 경우 해당 기능을 사용하지 않도록 설정할 수 있습니다.

시작 시 앱 PIN을 요구하도록 Intune PIN 정책이 설정되어 있는지 확인하기 위해 앱은 다음과 같은 호출을 수행할 수 있습니다.

```
MAMComponents.get(AppPolicy.class).getIsPinRequired();
```

### <a name="register-for-notifications-from-the-sdk"></a>SDK에서 알림 등록  

Intune 앱 SDK를 사용하면 IT 관리자가 선택적 초기화와 같은 특정 정책을 배포할 때 해당 동작을 앱에서 제어할 수 있습니다. IT 관리자가 해당 정책을 배포하면 Intune 서비스가 알림을 SDK에 보냅니다.

앱은 `MAMNotificationReceiver` 클래스를 만든 다음 `MAMNotificationReceiverRegistry`에 등록하여 SDK에서 알림을 등록해야 합니다. 이 예제에 나온 대로 `App.onCreate`에서 원하는 수신기 및 알림 유형을 제공하면 됩니다.

```
@Override
public void onCreate() {
    super.onCreate();
    MAMComponents.get(MAMNotificationReceiverRegistry.class)
.registerReceiver(
                new ToastNotificationReceiver(),
MAMNotificationType.WIPE_USER_DATA);
    }
```

`MAMNotificationReceiver`는 Intune 서비스에서 보내는 알림을 수신합니다. SDK는 일부 알림을 직접 처리합니다. 앱이 처리해야 하는 알림도 있습니다.

앱은 알림에서 true 또는 false를 반환*해야* 합니다. 알림의 결과로 시도한 일부 작업에서 오류가 발생하지 않는 한 앱은 항상 true를 반환해야 합니다. 이 오류는 Intune 서비스에 보고될 수 있습니다. 예를 들어 IT 관리자가 초기화를 시작한 후 앱에서 사용자 데이터를 초기화하지 못한 경우 오류가 보고될 수 있습니다.

해당 콜백이 UI 스레드에서 실행되고 있지 않기 때문에 `MAMNotificationReceiver.onReceive`에서 차단해도 안전합니다.

다음의 `MAMNotificationReceiver` 인터페이스가 SDK에 정의되어 있습니다.

```
/**
 * The SDK is signaling that a WG event has occurred.
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

```

###<a name="types-of-notifications"></a>알림 유형

앱에는 다음과 같은 알림이 전송됩니다. 그 중에는 앱에서 처리해야 하는 알림도 있습니다.

* **`WIPE_USER_DATA`**: `MAMUserNotification` 클래스를 통해 전송되는 알림입니다. 이 알림이 수신되면 앱에서는 `MAMUserNotification`을 통해 전달된 "회사" ID와 연결된 모든 데이터를 삭제해야 합니다. 이 알림은 현재 Intune 서비스 등록 취소 과정에 전송됩니다. 사용자의 기본 이름은 일반적으로 등록 프로세스 동안 지정됩니다. 이 알림에 등록하는 경우 앱에서 모든 사용자 데이터가 삭제되었는지 확인해야 합니다. 이 알림에 등록하지 않는 경우에는 앱이 기본 선택적 초기화 동작을 수행합니다.

* **`WIPE_USER_AUXILIARY_DATA`**: Intune 앱 SDK가 기본 선택적 초기화 동작을 수행하도록 하되 초기화 수행 시 일부 보조 데이터도 제거되도록 하려는 경우 앱에서 이 알림을 등록할 수 있습니다.  

* **`REFRESH_POLICY`**: `MAMUserNotification`을 통해 전송되는 알림입니다. 이 알림이 수신되면 캐시된 Intune 정책은 무효화되고 업데이트되어야 합니다. 일반적으로는 SDK가 이 태스크를 처리합니다. 하지만 정책이 영구적인 방식으로 사용되는 경우에는 앱에서 이 태스크를 처리해야 합니다.



### <a name="protection-of-backup-data"></a>백업 데이터 보호

Android Marshmallow(API 23) 현재, Android에는 앱이 데이터를 백업하는 두 가지 방법이 있습니다. 각 옵션을 앱에서 사용할 수 있으며 여러 단계를 거쳐 Intune 데이터 보호가 적절하게 구현되도록 해야 합니다. [Android API 가이드](http://developer.android.com/guide/topics/data/backup.html)에서 백업 방법에 대해 알아볼 수 있습니다.

#### <a name="automatic-backup-for-apps"></a>앱 자동 백업

Android는 앱의 대상 API에 관계없이 Android Marshmallow 장치의 앱에 [자동 전체 백업](https://developer.android.com/guide/topics/data/autobackup.html) 기능을 제공하기 시작했습니다. AndroidManifest.xml에서 `android:allowBackup`을 false로 명시적으로 설정하면 Android는 앱을 백업용 큐에 추가하지 않으며 "회사" 데이터가 앱 내에서 유지됩니다. 이 경우 추가 작업이 필요하지 않습니다.

매니페스트 파일에서 `android:allowBackup`을 지정하지 않더라도 기본적으로 `android:allowBackup` 특성은 true로 설정됩니다. 즉, 모든 앱 데이터가 사용자의 Google Drive 계정에 자동으로 백업되는, 이 동작은 *데이터 누출의 위험*이 있습니다. 따라서 데이터 보호가 적용되도록 SDK를 다음과 같이 변경해야 합니다. Android Marshmallow 장치에서 앱을 실행하려면 이러한 지침에 따라 고객 데이터를 제대로 보호해야 합니다.  

`MAMBackupAgent` 또는 `MAMBackupAgentHelper`를 사용하여 앱을 백업하는 백업 에이전트를 작성하지 않은 경우에는 자동 백업에서 앱 데이터를 업로드하는 방식을 고려하고 제어해야 합니다. Intune에서는 XML에서 사용자 지정 규칙을 정의하는 기능을 비롯하여 Android가 제공하는 모든 [자동 백업 기능](https://developer.android.com/guide/topics/data/autobackup.html)을 사용할 수 있습니다. 하지만 데이터 보안을 유지하려면 다음 단계를 따라야 합니다.

1. 기본 `MAMBackupAgent`를 사용하여 Intune 정책을 준수하는 자동 전체 백업을 허용합니다. `android:backupAgent="com.microsoft.intune.mam.client.app.backup.MAMDefaultBackupAgent"`를 앱 매니페스트에 넣습니다.

2. 앱이 받아야 하는 전체 백업 유형(필터링되지 않음, 필터링됨 또는 없음)을 결정할 때는 `android:fullBackupContent` 특성을 true, false 또는 앱의 XML 리소스로 설정합니다. `android:fullBackupContent`에 넣는 내용이 무엇이든 `com.microsoft.intune.mam.FullBackupContent`라는 메타데이터 태그로 복사하세요.

    예를 들어 XML 파일의 사용자 지정 규칙에 따라 앱에 전체 백업 기능을 포함하려면 다음과 같이 매니페스트의 `com.microsoft.intune.mam.FullBackupContent` 메타데이터 태그 아래에 리소스를 제공합니다.
    ```
    <meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />  
    ```



#### <a name="keyvalue-backup"></a>키/값 백업

키/값 백업 옵션은 모든 API에서 사용 가능하며 `BackupAgentHelper` 및 `BackupAgent`를 사용합니다.

##### <a name="backupagenthelper"></a>BackupAgentHelper

`BackupAgentHelper`는 기본 Android 기능 및 MAM 통합 측면에서 모두 `BackupAgent`에 비해 훨씬 더 간단하게 구현할 수 있습니다. `BackupAgentHelper`를 사용하면 전체 파일과 공유된 기본 설정을 `FileBackupHelper` 또는 `SharedPreferencesBackupHelper`에 각각 등록할 수 있습니다. 그러면 이 두 항목이 작성 시 `BackupAgentHelper`에 추가됩니다.

##### <a name="backupagent"></a>BackupAgent

`BackupAgent`를 사용하면 백업되는 데이터를 훨씬 더 명시적으로 지정할 수 있습니다. 하지만 이 옵션을 사용하는 경우에는 Android 백업 프레임워크를 활용할 수 없습니다. 개발자는 앱을 구현해야 하므로, MAM에서 데이터를 적절하게 보호하려면 추가적인 단계를 수행해야 합니다. 대부분의 작업은 개발자가 담당하므로 좀 더 세부적인 MAM 통합을 수행하게 됩니다.

###### <a name="app-does-not-have-a-backup-agent"></a>앱에 백업 에이전트가 없는 경우

`android:allowBackup =true`일 때 개발자가 사용할 수 있는 옵션은 다음과 같습니다.

####### <a name="full-backup-according-to-a-configuration-file"></a>구성 파일에 따라 전체 백업

매니페스트의 `com.microsoft.intune.mam.FullBackupContent` 메타데이터 태그 아래에 리소스를 제공합니다.      `<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />`

`<application>` 태그에 `android:fullBackupContent="@xml/my_scheme"` 특성을 추가합니다. 여기서 `my_scheme`은 앱의 XML 리소스입니다.

####### <a name="full-backup-without-exclusions"></a>제외 없는 전체 백업

`<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:value="true" />`와 같이 매니페스트에서 태그를 제공합니다.

`<application>` 태그에 다음 특성을 추가합니다. `android:fullBackupContent="true"`

###### <a name="app-has-a-backup-agent"></a>앱에 백업 에이전트가 있는 경우

이 가이드의 앞부분에 나오는 `BackupAgent` 및 `BackupAgentHelper`에 대한 권장 사항을 따릅니다.

Android Marshmallow에서 쉬운 백업을 제공하는 `MAMDefaultFullBackupAgent`를 사용하도록 전환하는 것이 좋습니다.

##### <a name="before-your-backup"></a>백업하기 전에

백업을 시작하기 전에 백업하려는 파일 또는 데이터 버퍼가 백업 가능한지 확인해야 합니다. 백업 가능 여부를 확인할 수 있도록 `MAMFileProtectionManager` 및 `MAMDataProtectionManager`에 `isBackupAllowed` 함수가 포함되어 있습니다. 파일 또는 데이터 버퍼의 백업이 허용되지 않은 경우 백업에서 해당 파일이나 데이터 버퍼를 계속 사용하면 안 됩니다.

1단계에 확인한 파일의 ID를 백업하려는 경우에는 백업 도중 특정 시점에 데이터를 추출할 파일에 대해 `backupMAMFileIdentity(BackupDataOutput data, File … files)`를 호출해야 합니다. 그러면 자동으로 새 백업 엔터티가 생성되어 `BackupDataOutput`에 작성됩니다. 이러한 엔터티는 복원 시 자동으로 사용됩니다.

#### <a name="azure-directory-authentication-library-setup"></a>Active Directory Authentication Library 설정  

Intune 앱 SDK는 해당 인증 및 조건부 시작 시나리오에 ADAL을 사용합니다. 이러한 시나리오를 수행하려면 앱에서 Azure AD(Active Directory) 구성을 어느 정도 수행해야 합니다. 구성 값은 `AndroidManifest` 메타데이터를 통해 SDK에 전달됩니다.

앱을 설정하고 적절한 인증을 사용하도록 설정하려면 `AndroidManifest`의 앱 노드에 다음을 추가합니다. 이러한 구성 중 일부는 앱이 전반적인 인증에 ADAL을 사용하는 경우에만 수행하면 됩니다. ADAL이 사용되는 경우에는 앱이 Azure AD에 등록하는 데 사용한 특정 값이 필요합니다. 이 값을 추가해 두면 Azure AD가 별개의 두 등록 값(앱의 값 및 SDK의 값)을 인식하기 때문에 사용자에게 인증을 요구하는 메시지가 두 번 나타나지 않습니다.

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

##### <a name="common-adal-configurations"></a>일반적인 ADAL 구성

다음은 앞에서 설명한 값에 대한 일반적인 구성입니다.

###### <a name="app-does-not-integrate-adal"></a>앱이 ADAL을 통합하지 않는 경우

* Azure AD 계정이 설정된 원하는 환경으로 인증 기관을 설정해야 합니다.

* SkipBroker를 true로 설정해야 합니다.

###### <a name="app-integrates-adal"></a>앱이 ADAL을 통합하는 경우

* Azure AD 계정이 설정된 원하는 환경으로 인증 기관을 설정해야 합니다.

* 클라이언트 ID는 앱의 클라이언트 ID로 설정해야 합니다.

* `NonBrokerRedirectURI` 를 앱의 유효한 리디렉션 URI로 설정해야 합니다. 또는 `urn:ietf:wg:oauth:2.0:oob`를 유효한 Azure AD 리디렉션 URI로 설정해야 합니다.

* SkipBroker는 false로 설정하거나 비워 두어야 합니다.

* 브로커 리디렉션 URI를 허용하도록 Azure AD를 구성해야 합니다.

###### <a name="app-integrates-adal-but-does-not-support-the-azure-ad-authenticator-app"></a>앱이 ADAL을 통합하지만 Azure AD Authenticator 앱을 지원하지 않는 경우

* Azure AD 계정이 설정된 원하는 환경으로 인증 기관을 설정해야 합니다.

* 클라이언트 ID는 앱의 클라이언트 ID로 설정해야 합니다.

* `NonBrokerRedirectURI` 를 앱의 유효한 리디렉션 URI로 설정해야 합니다. 또는 `urn:ietf:wg:oauth:2.0:oob`를 유효한 Azure AD 리디렉션 URI로 설정해야 합니다.

#### <a name="logging-in-the-sdk"></a>SDK의 로깅

로깅은 `java.util.logging` 프레임워크를 통해 수행됩니다. 로그를 받으려면 [Java 기술 가이드](http://docs.oracle.com/javase/6/docs/technotes/guides/logging/overview.html). 앱에 따라 다르지만 일반적으로 `App.onCreate`가 로깅을 시작하는 가장 좋은 위치입니다. 로그 메시지는 클래스 이름(숨겨져 있을 수 있음)을 키로 사용합니다.

###<a name="multi-identity"></a>다중 ID

기본적으로 Intune 앱 SDK는 앱에 전체적으로 정책을 적용합니다. 다중 ID는 ID 단위 수준에서 정책을 적용하기 위해 사용할 수 있는 MAM 기능입니다. 이 기능을 사용하려면 다른 MAM 기능보다 훨씬 더 많은 앱 참여가 필요합니다. 앱은 활성 ID를 변경하려는 경우 앱 SDK에 알려야 합니다. SDK는 ID 변경이 필요한 경우 앱에도 알립니다.

현재 관리 ID는 하나만 지원됩니다. 사용자가 장치 또는 앱을 등록하고 나면 SDK에서 이 ID를 사용하고 이를 기본 관리 ID로 간주합니다. 앱의 다른 사용자는 무제한 정책 설정이 적용되는 관리되지 않는 항목으로 처리됩니다.

ID는 단순히 문자열로 정의됩니다. ID는 대/소문자를 구분하지 않습니다. ID와 관련한 SDK에 대한 요청은 ID를 설정할 때 원래 사용된 것과 같은 대/소문자를 반환하지 않을 수도 있습니다.

####<a name="enabling-multi-identity"></a>다중 ID 사용

기본적으로 모든 앱은 단일 ID 앱으로 간주합니다. 앱은 Android 매니페스트에 다음 메타데이터를 포함하여 다중 ID를 인식할 수 있음을 선언합니다.

```
<meta-data
            android:name="com.microsoft.intune.mam.MAMMultiIdentity"
            android:value="true" />
```
####<a name="setting-the-identity"></a>ID 설정

개발자는 다음 수준에서 앱의 ID를 설정할 수 있습니다.

1. 프로세스 수준

2. 컨텍스트(일반적으로 `Activity`) 수준

3. 스레드 수준

스레드 수준에서 설정된 ID는 `Context` 수준에서 설정된 ID를 대체하고 프로세스 수준에서 설정된 ID를 대체합니다. `Context`에 설정된 ID는 적절한 경우에만 사용됩니다. 예를 들어 파일 I/O 태스크에는 연결된 `Context`가 없습니다. `MAMPolicyManager`에 대해 다음 메서드를 사용하여 ID를 설정하고 이전에 설정한 ID 값을 검색할 수 있습니다.

```
public static void setUIPolicyIdentity(final Context context, final String identity, final MAMSetUIIdentityCallback mamSetUIIdentityCallback);

public static String getUIPolicyIdentity(final Context context);

public static MAMIdentitySwitchResult setProcessIdentity(final String identity);

public static String getProcessIdentity();

public static MAMIdentitySwitchResult setCurrentThreadIdentity(final String identity);

public static String getCurrentThreadIdentity();

/**
 * Get the currently applicable app policy. Same as MAMComponents.get(AppPolicy.class). This method does
    not take the context identity into account.
 */
public static AppPolicy getPolicy();

/**
 * Get the currently applicable app policy, taking the context
 * identity into account.
 */
public static AppPolicy getPolicy(final Context context);


public static AppPolicy getPolicyForIdentity(final String identity);

public static boolean getIsIdentityManaged(final String identity);

```
앱의 ID를 Null로 설정하여 ID를 지울 수도 있습니다. 빈 문자열을 제한 사항이 없는 ID로 사용할 수 있습니다. ID를 설정하는 모든 메서드는 ``` MAMIdentitySwitchResult```를 통해 결과 값을 다시 보고합니다. 4개의 값이 반환될 수 있습니다.

* **SUCCEEDED**: ID가 변경되었습니다.

* **NOT_ALLOWED**: ID 변경이 허용되지 않습니다. 등록된 사용자와 같은 회사에 속한 다른 회사 사용자로 전환하려고 하면 이 값이 반환됩니다. 현재 스레드에 다른 ID가 설정되어 있을 때 UI(`Context`) ID를 설정하려면 할 경우에도 이 값이 반환됩니다.

* **CANCELLED**: 사용자가 ID 변경을 취소했습니다(일반적으로는 PIN/인증 프롬프트에서 뒤로 단추를 선택하는 경우).

* **FAILED**: 알 수 없는 이유로 ID 변경에 실패했습니다.

`Context` ID를 설정할 경우 결과는 비동기적으로 보고됩니다. `Context`가 `Activity` 클래스이면 조건부 시작 이후까지 ID가 변경되었는지를 확인할 수 없습니다. 조건부 시작 시에는 사용자가 PIN 또는 전체 회사 자격 증명을 입력해야 할 수 있습니다. 앱은 이 매개 변수에 Null을 전달할 수 있더라도 이 결과를 수신하도록 ```MAMSetUIIdentityCallback```을 구현해야 합니다.

```
public interface MAMSetUIIdentityCallback {
    void notifyIdentityResult(MAMIdentitySwitchResult identitySwitchResult);
}
```

```MAMPolicyManager.setUIPolicyIdentity```를 호출하는 대신 `MAMActivity`의 메서드를 통해 직접 활동 ID를 설정할 수도 있습니다. 이 작업에 다음 메서드를 사용할 수 있습니다.

 ```public final void switchMAMIdentity(final String newIdentity);```

앱은 해당 활동의 ID를 변경하려는 시도의 결과를 알리도록 `MAMActivity`의 메서드를 재정의할 수도 있습니다.

```public void onSwitchMAMIdentityComplete(final MAMIdentitySwitchResult result);```

> [!NOTE]
> ID를 전환하려면 활동을 다시 만들어야 할 수 있습니다. 이 경우 ```onSwitchMAMIdentityComplete``` 콜백이 작업의 새 인스턴스에 전달됩니다.


####<a name="implicit-identity-changes"></a>암시적 ID 변경

앱의 ID 설정 기능이 사용되는 경우 외에도, 다른 MAM 지원 앱에서 수신하는 데이터에 따라 스레드 또는 컨텍스트의 ID가 변경될 수 있습니다. 예를 들어 다른 MAM 앱에서 보낸 `Intent` 클래스에서 활동이 시작된 경우 `Intent` 클래스가 전송된 시점에서 다른 앱의 유효 ID에 따라 활동 ID가 설정됩니다.

서비스의 경우 `onStart` 또는 `onBind` 호출 기간 동안 스레드 ID가 비슷하게 설정됩니다. `onBind`에서 반환된 `Binder` 호출도 일시적으로 스레드 ID를 설정합니다. 마찬가지로 ```ContentProvider``` 호출은 해당 기간에 대한 스레드 ID를 설정합니다.

또한 사용자가 활동과 상호 작용할 때 암시적 ID 전환이 수행될 수 있습니다. 예를 들어 사용자가 ```Resume``` 중에 인증 프롬프트에서 취소하면 암시적으로 빈 ID로 전환됩니다.
앱은 이러한 변경 내용을 인식하고 필요한 경우 변경을 금지할 수 있습니다. ```MAMService``` 및 ```MAMContentProvider```는 하위 클래스가 재정의할 수 있는 다음 메서드를 표시합니다.

```
public void onMAMIdentitySwitchRequired(final String identity,
    final AppIdentitySwitchResultCallback callback);
```
```MAMActivity```의 경우 메서드에 다음과 같은 추가 매개 변수가 있습니다.
```
public void onMAMIdentitySwitchRequired(final String identity,
    final AppIdentitySwitchReason reason,
    final AppIdentitySwitchResultCallback callback);
```
```AppIdentitySwitchReason``` 부분은 암시적 스위치의 소스를 캡처하며 ```CREATE```, ```RESUME_CANCELLED```, ```NEW_INTENT``` 값을 허용할 수 있습니다.  ```RESUME_CANCELLED``` 이유는 활동이 다시 시작되어 PIN, 인증 또는 기타 준수 UI가 표시될 때 사용자가 일반적으로 뒤로 단추를 사용하여 해당 UI를 취소하려고 할 때 사용됩니다.
```AppIdentitySwitchResultCallback```은 다음과 같습니다.
```
public interface AppIdentitySwitchResultCallback {
    /**
     * @param result
     *            whether the identity switch can proceed.
     */
    void reportIdentitySwitchResult(AppIdentitySwitchResult result);
}
```
```AppIdentitySwitchResult```는 ```SUCCESS``` 또는 ```FAILURE```입니다.

```MAMService.onMAMBind```에서 반환된 `Binder` 클래스를 통해 적용된 변경을 제외한 모든 암시적 ID 변경에 대해 ```onMAMIdentitySwitchRequired``` 메서드가 호출됩니다. 이유가 ```RESUME_CANCELLED```일 때는 ```onMAMIdentitySwitchRequired```의 기본 구현이 ```reportIdentitySwitchResult(FAILURE)```를 즉시 호출하며, 그 외의 모든 경우에는 ```reportIdentitySwitchResult(SUCCESS)```를 호출합니다.

대부분의 앱은 다른 방식으로 ID 전환을 차단하거나 지연시킬 필요가 없습니다. 그러나 앱이 ID 전환을 차단하거나 지연시켜야 하는 경우에는 다음 사항을 고려하세요.

* ID 전환을 차단하는 경우의 결과는 ```Receive``` 공유 설정이 데이터 수신을 금지한 경우와 동일합니다.

* 서비스가 주 스레드에서 실행 중이면 ```reportIdentitySwitchResult```를 *반드시* 동기적으로 호출해야 합니다. 그렇지 않으면 UI 스레드가 응답하지 않습니다.

* ```Activity``` 만들기의 경우 ```onMAMCreate``` 전에 ```onMAMIdentitySwitchRequired```가 호출됩니다. 앱이 ID 전환 허용 여부를 확인하기 위한 UI를 표시해야 할 경우 해당 UI는 다른 활동을 통해 표시되어야 합니다.

* ```Activity```에서 ```RESUME_CANCELLED```와 같은 이유로 빈 ID로 전환해야 할 경우 앱은 데이터를 해당 ID 전환과 일관되게 표시하도록 다시 시작된 활동을 변경해야 합니다. 이렇게 변경할 수 없는 경우 앱은 전환을 거부해야 합니다. 그리고 사용자에게는 다시 시작하려는 ID에 대한 정책을 준수해야 한다는 메시지가 다시 표시됩니다. 예를 들어 PIN 입력 화면이 표시될 수 있습니다.

> [!NOTE]
> 다중 ID 앱은 항상 관리되는 앱과 관리되지 않는 앱에서 들어오는 데이터를 둘 다 수신합니다. 앱은 관리되는 ID의 데이터를 관리되는 방식으로 처리해야 합니다. 요청된 ID가 관리되는 ID(```(MAMPolicyManager.getIsIdentityManaged)```)인데 앱이 메일 계정 등의 계정을 먼저 설정해야 하기 때문에 해당 계정을 사용할 수 없다면 ID 전환이 거부됩니다.

###<a name="file-protection"></a>파일 보호

모든 파일은 만들어질 때 스레드 및 프로세스 ID를 기준으로 하는 ID에 연결됩니다. 이 ID는 파일 암호화 및 선택적 초기화 둘 다에 사용됩니다. 암호화를 요구하는 정책이 ID에 있는 파일만 암호화됩니다. SDK의 기본 선택적 초기화는 초기화가 요청된 ID와 연결된 파일만 초기화합니다. 앱은 ```MAMFileProtectionManager```를 사용하여 파일 ID를 쿼리하거나 변경할 수 있습니다.
```
public final class MAMFileProtectionManager {

    /**
     * Protect a file. This will synchronously trigger whatever protection is required for the file, and will tag the file for
     * future protection changes.
     *
     * @param identity
     *            Identity to set.
     * @param file
     *            File to protect.
     * @throws IOException
     *             If the file cannot be changed.
     */
    public static void protect(final File file, final String identity) throws IOException;

    /**
     * Get the protection info on a file.
     *
     * @param file
     *            File or directory to get information on.
     * @return File protection info, or null if there is no protection info.
     * @throws IOException
     *             If the file cannot be read or opened.
     */
    public static MAMFileProtectionInfo getProtectionInfo(final File file) throws IOException;
}

public interface MAMFileProtectionInfo {
String getIdentity();
}
```

> [!NOTE]
> 오프라인 모드에서 파일 ID 태그를 지정할 경우 주의하세요. 다음 사항을 고려해야 합니다.
> * 회사 포털 앱이 설치되어 있지 않으면 파일에 ID 태그를 지정할 수 없습니다.
>
> * 회사 포털 앱이 설치되어 있지만 앱에 정책이 없으면 파일에 안정적으로 ID 태그를 지정할 수 없습니다.
>
> * 파일 ID 태그 지정을 사용할 수 있으면 이전에 만든 모든 파일이 빈 문자열 ID에 속한 개인용으로 처리됩니다. 단, 앱이 단일 ID 관리 앱으로 이전에 설치된 경우는 개인용으로 처리되지 않으며 등록된 사용자에게 속하는 것으로 처리됩니다.

####<a name="data-protection"></a>데이터 보호

여러 ID에 속하는 것으로 파일에 태그를 지정할 수는 없습니다. 여러 사용자에게 속한 데이터를 같은 파일에 저장해야 하는 앱은 ```MAMDataProtectionManager```에서 제공하는 기능을 사용하여 수동으로 데이터를 저장할 수 있습니다. 이렇게 하면 앱이 데이터를 암호화하여 특정 사용자에게 연결할 수 있습니다. 암호화된 데이터는 파일로 디스크에 저장하는 데 적합합니다. ID와 연결된 데이터를 쿼리하고 나중에 데이터를 암호 해제할 수 있습니다.

```
public final class MAMDataProtectionManager {
    /**
     * Protect a stream. This will return a stream containing the protected
 * input.
     *
     * @param identity
     *            Identity to set.
     * @param input
     *            Input data to protect, read sequentially. This function
 *            will change the position of the stream but may not have
     *            read the entire stream by the time it returns. The
 *            returned stream will wrap this one. Calls to read on the
     *            returned stream may cause further reads on the original
 *            input stream. Callers should not expect to read directly
     *            from the input stream after passing it to this method.
 *            Calling close on the returned stream will close this one.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be protected
     */
    public static InputStream protect(final InputStream input, final String identity);

    /**
     * Protect a byte array. This will return protected bytes.
     *
     * @param identity
     *            Identity to set.
     * @param input
     *            Input data to protect.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be protected
     */
    public static byte[] protect(final byte[] input, final String identity) throws IOException;

    /**
     * Unprotect a stream. This will return a stream containing the
 * unprotected input.
     *
     * @param input
     *            Input data to protect, read sequentially.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be unprotected
     */
    public static InputStream unprotect(final InputStream input) throws IOException;

    /**
     * Unprotect a byte array. This will return unprotected bytes.
     *
     * @param input
     *            Input data to protect.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be unprotected
     */
    public static byte[] unprotect(final byte[] input) throws IOException;

    /**
     * Get the protection info on a stream.
     *
     * @param input
     *            Input stream to get information on. Either this input
 *            stream must have been returned by a previous call to
     *            protect OR input.markSupported() must return true.
 *            Otherwise it will be impossible to get protection info
 *            without advancing the stream position. The stream must be
 *            positioned at the beginning of the protected data.
     * @return Data protection info, or null if there is no protection
 *            info.
     * @throws IOException
     *             If the input cannot be read.
     */
    public static MAMDataProtectionInfo getProtectionInfo(final InputStream input) throws IOException;

    /**
     * Get the protection info on a stream.
     *
     * @param input
     *            Input bytes to get information on. These must be bytes
 *            returned by a previous call to protect() or a copy of
 *            such bytes.
     * @return Data protection info, or null if there is no protection
 *            info.
     * @throws IOException
     *             If the input cannot be read.
     */
    public static MAMDataProtectionInfo getProtectionInfo(final byte[] input) throws IOException;
}
```
###<a name="content-providers"></a>콘텐츠 공급자

앱이 잠재적으로 ```ContentProvider```를 통해 ```ParcelFileDescriptor``` 이외의 회사 데이터를 제공할 경우 앱은 콘텐츠에 대한 소유자 ```UPN```을 전달하는 ```MAMContentProvider``` 메서드 ```isProvideContentAllowed(String)```를 호출해야 합니다. 이 함수가 false를 반환하면 콘텐츠가 호출자에게 반환될 수 없습니다. 콘텐츠 공급자를 통해 반환된 파일 설명자는 파일 ID에 따라 자동으로 처리됩니다.

###<a name="selective-wipe"></a>선택적 초기화

```WIPE_USER_DATA``` 알림을 등록한 앱에는 SDK 기본 선택적 초기화 동작이 적용되지 않습니다. 다중 ID 인식 앱의 경우 MAM 기본 선택적 초기화는 초기화할 ID와 일치하는 파일만 초기화하므로, 이러한 특성이 더욱 중요할 수 있습니다.

다중 ID 인식 앱을 빌드할 때는 ```WIPE_USER_AUXILIARY_DATA```를 등록할 수 있습니다. 이 알림을 등록하면 SDK 기본 초기화 동작을 활용할 수 있습니다. 이 알림은 SDK 기본 선택적 초기화를 수행하기 직전에 전송됩니다. 앱에서 ```WIPE_USER_DATA``` 및 ```WIPE_USER_AUXILIARY_DATA```를 둘 다 등록할 수는 없습니다.

### <a name="known-platform-limitations"></a>알려진 플랫폼 제한 사항

#### <a name="file-size-limitations"></a>파일 크기 제한

Android에서는 Dalvik 실행 파일 형식이 제한되므로 ProGuard 없이 실행되는 대규모 코드베이스의 경우 문제가 될 수 있습니다. 특히 다음과 같은 제한이 적용될 수 있습니다.

* 필드 65,000개 제한

* 메서드 65,000개 제한

여러 프로젝트를 포함하는 경우 모든 `android:package`에 R 복사본이 포함되므로, 라이브러리가 추가됨에 따라 필드 수가 크게 증가합니다. 다음 권장 사항은 이러한 제한을 완화하는 데 도움이 될 수 있습니다.

* 가능한 경우 모든 라이브러리 프로젝트에서 동일한 `android:package`를 공유해야 합니다. 이렇게 하면 순수하게 빌드 시 문제가 되므로 필드에서 산발적으로 장애가 발생하지 않습니다. 또한 최신 버전의 Android SDK는 DEX 파일을 전처리하여 일부 중복성을 제거합니다. 이를 통해 필드 간격이 더욱 줄어듭니다.

* 사용 가능한 최신 Android SDK 빌드 도구를 사용합니다.

* 불필요한 라이브러리 및 사용하지 않는 라이브러리(예: `android.support.v4`)를 모두 제거합니다.

#### <a name="policy-enforcement-limitations"></a>정책 적용 제한 사항

**화면 캡처**: SDK는 이미 `Activity.onCreate` 처리한 `Activity` 클래스에서 새로운 화면 캡처 설정 값을 적용할 수 없습니다. 이로 인해 앱에서 스크린샷을 사용하지 않도록 설정했는데도 여전히 스크린샷을 만들 수 있는 기간이 발생합니다.

**콘텐츠 확인자**: 전송 또는 수신 정책이 다른 앱에서 콘텐츠 확인자를 사용하여 콘텐츠 공급자에 액세스하는 것을 차단하거나 부분적으로 차단할 수 있습니다. 이 경우 `ContentResolver` 메서드가 null을 반환하거나 오류 값을 throw합니다. 예를 들어 `openOutputStream`은 차단되는 경우 `FileNotFoundException`을 throw합니다. 앱은 이 호출을 수행하여 특정 정책으로 인해 콘텐츠 확인자를 통한 데이터 쓰기가 실패했는지/실패할 수 있는지를 확인할 수 있습니다.

    MAMComponents.get(AppPolicy.class).getIsSaveToLocationAllowed(contentURI)

**내보낸 서비스**: Intune 앱 SDK에 포함된 `AndroidManifest.xml` 파일에는 `MAMNotificationReceiverService`가 있습니다. 회사 포털 앱이 지원 앱에 알림을 보낼 수 있도록 하려면 이 서비스는 내보낸 서비스여야 합니다. 이 서비스는 호출자를 검사하여 회사 포털 앱만 알림을 보낼 수 있는지 확인합니다.

### <a name="android-best-practices"></a>Android 모범 사례

Intune SDK는 Android API에서 제공되는 계약을 유지하지만, 정책 적용의 결과로 오류 상태가 더 빈번하게 트리거될 수 있습니다. 다음 Android 모범 사례는 오류 가능성을 줄입니다.

* null을 반환할 수 있는 Android SDK 함수가 null일 가능성이 높아졌습니다. 문제를 최소화하려면 올바른 위치에서 null 검사가 이루어지도록 합니다.

* 검사할 수 있는 기능의 경우 해당 SDK API를 사용하여 기능을 검사합니다.

* 파생된 함수는 상위 클래스 버전을 통해 호출해야 합니다.

* API를 모호한 방식으로 사용해서는 안 됩니다. 예를 들어 `requestCode` 확인 없이 `Activity.startActivityForResult/onActivityResult`를 사용하면 비정상적인 동작이 발생합니다.



<!--HONumber=Dec16_HO3-->


