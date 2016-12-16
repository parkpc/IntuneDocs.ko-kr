## <a name="november-2016"></a>2016년 11월

### <a name="new-capabilities"></a>새로운 기능

<!--### View App States for All Platforms in Real Time
App installation status is now shown in real-time in the console. When you previously deployed an app, you had to wait for a targeted device to report back before the app install status was displayed in the Intune console.

### Streamline iOS App Management for your End Users
Intune can now automatically take over management of the previously installed app and no end user action is required.

Previously, if the end user of an enrolled iOS device installed an app from the App Store before you deployed that same app with a deployment action of __Available__, then the end user had to:

1. Open the __Company Portal__.
2. Select the app.
3. Tap __Install__ to enable Intune to take over management of the app.-->

__Windows 10 장치에 사용할 수 있는 새로운 Microsoft Intune 회사 포털__ Microsoft는 새로운 [Windows 10 장치용 Microsoft Intune 회사 포털 앱](https://www.microsoft.com/store/apps/9wzdncrfj3pz)을 출시했습니다. 이 앱은 새로운 Windows 10 유니버셜 형식을 활용하고 있으며, 현재 사용 중인 모든 기능을 계속 사용할 수 있게 하면서 사용자에게 앱의 업데이트된 사용자 환경과 모든 Windows 10 장치, PC 및 모바일 유사 장치에 걸쳐 동일한 환경을 제공합니다.

새 앱을 사용하면 사용자가 Windows 10 장치에서 SSO(Single Sign-On) 및 인증서 기반 인증과 같은 추가적인 플랫폼 기능도 활용할 수 있습니다. 이 앱은 기존 Windows 8.1 회사 포털과 Windows Phone 8.1 회사 포털에 대한 업그레이드로서 Windows 스토어에서 설치해 사용할 수 있습니다. 자세한 내용은 [aka.ms/intunecp_universalapp](http://aka.ms/intunecp_universalapp)를 참조하세요.

<!--### Support for Windows Store for Business Apps Being Deployed as Available
You can now deploy apps you synchronized from the Windows Store for Business (WSfB) with a deployment action of __Available__ or __Required__. After syncing WSfB apps into Intune, administrators will be able to target those apps as available installs to groups of users. End users will see the deployed WSfB apps as available for install in the Universal Company Portal, where they can choose whether they would like to acquire the apps.

### Conditional Access for MAM with SharePoint Online

You can block apps that are not supported by Intune mobile app management (MAM) policies from accessing SharePoint online.  You can get started in Intune mobile app management via the Azure portal. Look for the  Conditional Access section in the “Settings” blade which now includes the option for SharePoint online.-->

> [!IMPORTANT]

> __Intune 및 Android for Work에 대한 업데이트__

> __필수__ 작업을 통해 Android for Work 앱을 배포할 수 있는 반면, Intune 그룹이 새 Azure AD 그룹 환경으로 마이그레이션된 경우에는 앱을 __사용 가능__으로 배포할 수 있습니다.

__Intune 앱 SDK Cordova 플러그 인을 통해 별도의 등록 없이 MAM 사용__ 앱 개발자는 Cordova용 Intune 앱 SDK 플러그 인을 사용하여 Cordova 기반 Android 및 iOS용 앱에 장치를 등록하지 않고도 MAM 기능을 설정할 수 있습니다. Cordova용 Intune 앱 SDK 플러그 인은 [여기](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam)에서 제공됩니다.

__Intune 앱 SDK Xamarin 구성 요소를 통해 별도의 등록 없이 MAM 사용__ 앱 개발자는 Intune 앱 SDK Xamarin 구성 요소를 사용하여 Xamarin 기반 Android 및 iOS용 앱에 장치를 등록하지 않고도 MAM 기능을 설정할 수 있습니다. Intune 앱 SDK Xamarin 구성 요소는 [여기](https://github.com/msintuneappsdk/intune-app-sdk-xamarin)에서 제공됩니다.

### <a name="notices"></a>알림

__이제 Symantec 서명 인증서를 업로드할 때 서명된 Windows Phone 8 회사 포털이 필요하지 않음__ Symantec 서명 인증서를 업로드할 때 서명된 Windows Phone 8 회사 포털 앱이 더 이상 필요하지 않습니다. 인증서는 개별적으로 업로드할 수 있습니다.

###<a name="deprecations"></a>지원 중단

__Windows Phone 8 회사 포털에 대한 지원__ 이제 Windows Phone 8 회사 포털은 지원되지 않습니다. Windows Phone 8 및 WinRT 플랫폼 지원이 2016년 10월에 중단되었습니다. Windows 8 회사 포털 지원도 2016년 10월에 중단되었습니다.

## <a name="october-2016"></a>2016년 10월

### <a name="conditional-access-for-mobile-application-management"></a>모바일 응용 프로그램 관리용 조건부 액세스
Exchange Online에 대한 액세스를 제한하여 Outlook과 같이 Intune 모바일 응용 프로그램 정책을 지원하는 앱에서만 액세스하도록 할 수 있습니다. [이 새로운 기능](/intune/deploy-use/allow-policy-managed-apps-access-to-o365)은 Intune MAM(모바일 앱 관리) 정책과 완벽히 쌍을 이루어 기본 제공 메일 클라이언트나 Intune MAM 정책을 사용하여 구성되지 않은 기타 앱에 대한 액세스를 차단할 수 있습니다. 이렇게 하면 사용자가 Intune MAM으로 보호할 수 있는 앱을 사용하여 조직의 데이터에 액세스합니다. Azure Portal을 통해 Intune 모바일 앱 관리를 시작할 수 있습니다. "설정" 블레이드에서 새 조건부 액세스 섹션을 찾아보세요.

### <a name="conditional-access-for-windows-pcs"></a>Windows PC에 대한 조건부 액세스
이제 Intune 관리 콘솔을 통해 Windows PC가 [Exchange Online](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune) 및 [SharePoint Online](/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune)에 액세스하지 못하도록 하는 조건부 액세스 정책을 만들 수 있습니다. 또한 Office 데스크톱 및 유니버설 응용 프로그램에 대한 액세스를 차단하기 위한 조건부 액세스 정책을 만들 수 있습니다.

### <a name="android-for-work-support"></a>Android for Work 지원

> [!IMPORTANT]

> __필수__ 작업을 통해 Android for Work 앱을 배포할 수 있는 반면, Intune 그룹이 새 Azure AD 그룹 환경으로 마이그레이션된 경우에는 앱을 __사용 가능__으로 배포할 수 있습니다.

Intune은 이제 AfW(Android for Work) 프로그램의 일부입니다. Microsoft는 이번 달부터 다음 몇 달에 걸쳐 AfW 기능을 지원한다고 발표할 것입니다. AfW의 사용 가능한 앱 배포에는 새로운 그룹화 및 대상 지정 환경이 사용됩니다. 새로 프로비전된 Intune 서비스 계정에 AfW가 제공되면 해당 계정은 이 기능을 사용할 수 있습니다.

<!--Existing Intune customers can use this feature in production once their tenant has been migrated. Existing customers are welcome to create a trial Intune account to plan for and test this feature until their tenant has been migrated. Any questions on grouping and targeting timelines, please contact our [migration team](mailto:intunegrps@microsoft.com).-->

[Intune의 Android for Work 지원에 대한 Microsoft 공지 사항 읽기](https://blogs.technet.microsoft.com/enterprisemobility/2016/09/12/microsoft-intune-support-for-android-for-work/)를 참조하세요.

다음 Intune 항목은 새롭거나 업데이트된 Android for Work 정보입니다.

IT 전문가용:
- [Android for Work 설정](/intune/deploy-use/set-up-android-for-work)
<!--- [Nathan Bigman's resource access topics]()-->
- [Intune을 사용하여 Exchange Online 및 새 Exchange Online Dedicated에 대한 메일 액세스 제한](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)
- [Intune을 사용하여 Exchange 온-프레미스 및 레거시 Exchange Online Dedicated에 대한 메일 액세스 제한](/intune/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)
- [Android for Work 준수 정책 설정](/intune/deploy-use/afw-compliance-policy-settings-in-microsoft-intune)
- [Android for Work 앱을 배포하는 방법](/intune/deploy-use/android-for-work-apps)
- [모바일 앱 구성 정책을 사용하여 Android for Work 앱 구성](/intune/deploy-use/afw-app-configuration-policy)
- [Android for Work 정책 설정](/intune/deploy-use/android-for-work-policy-settings-in-microsoft-intune)

최종 사용자:
- [회사 프로필을 만들면 어떻게 되나요?](/intune/enduser/what-happens-when-you-create-a-work-profile-android)
- [회사 프로필을 만들고 Intune에서 장치 등록](/intune/enduser/create-a-work-profile-and-enroll-your-device-in-intune-android)

### <a name="lookout-integration-to-protect-ios-devices"></a>iOS 장치를 보호하기 위한 Lookout 통합
10월에 Microsoft는 맬웨어, 위험한 앱 등을 감지한 iOS 모바일 장치를 보호하기 위해 Lookout의 모바일 위협 방지 솔루션과 통합합니다. Lookout의 솔루션을 통해 위협 수준을 결정할 수 있고, 이 수준은 구성이 가능합니다. Lookout의 위협 평가를 기준으로 장치 준수를 결정하는 준수 정책 규칙을 Intune에서 만들 수 있습니다. 조건부 액세스 정책을 사용하여 장치 준수 상태에 따라 회사 리소스에 대한 액세스를 허용하거나 차단할 수 있습니다.

비준수 iOS 장치의 최종 사용자는 표시되는 등록 요청 메시지에서 회사 데이터에 대한 액세스 권한을 얻기 위해 Lookout for Work 앱을 장치에 설치하여 활성화하고 이 앱에 보고된 위협을 해결하도록 요청받습니다. [Lookout for Work 앱 구성 및 배포](/intune/deploy-use/configure-and-deploy-lookout-for-work-apps) 방법을 알아 봅니다.
<!--TFS 1319493-->

<!--### New Microsoft Intune Company Portal available for Windows 10 devices
Microsoft is releasing a new [Microsoft Intune Company Portal for Windows 10 devices](https://go.microsoft.com/fwlink/?linkid=830663). This app, which leverages the new Windows 10 Universal format, will provide the user with an updated user experience within the app and identical experiences across all Windows 10 devices, PC and Mobile alike, while still enabling all the same functionality that they are using today.

The new app will also allow users to leverage additional platform features like single sign-on (SSO) and certificate-based authentication on Windows 10 devices. The app will be made available as an upgrade to the existing Windows 8.1 Company Portal and Windows Phone 8.1 Company Portal installs from the Windows Store.-->

### <a name="intune-app-wrapping-tool-for-android"></a>Android용 Intune 앱 래핑 도구
Intune 앱 래핑 도구를 사용하여 Intune 모바일 앱에서 MAM(모바일 응용 프로그램 관리) 정책을 사용할 수 있게 할 수 있습니다. 이제 장치 등록을 요구하지 않는 Intune MAM 정책이 지원됩니다.

### <a name="manage-printing-from-apps-managed-using-mam-policies"></a>MAM 정책으로 관리되는 앱에서 인쇄 관리
이제는 MAM 정책을 포함한 앱에서 회사 데이터를 인쇄할 없습니다. 이 설정은 [Azure 포털](/Intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune)에서 사용할 수 있으며 [iOS](/Intune/deploy-use/ios-mam-policy-settings) 및 [Android](/Intune/deploy-use/android-mam-policy-settings) 장치에서 모두 지원됩니다.
<!--TFS 1014328-->

### <a name="support-for-fingerprints-on-android-devices"></a>Android 장치에서 지문 지원
Android MAM(모바일 앱 관리) 정책에서는 이제 사용자가 PIN을 입력하는 대신 지문으로 앱에 액세스하도록 허용합니다. 다양한 [Microsoft Intune에서 Android 모바일 앱 관리 정책 설정](/Intune/deploy-use/android-mam-policy-settings)을 참조하세요.

### <a name="notices"></a>알림

__Intune과 Android Samsung KNOX의 호환성__ Intune에서는 특정 모델의 삼성 Galaxy Ace 전화를 Samsung KNOX 장치로 관리할 수 없습니다. 대신 Intune에서 이러한 장치를 등록하면 해당 장치가 표준 Android 장치로 관리됩니다.

영향을 받는 모델 번호는 다음과 같습니다.

* SM-G313HU
* SM-G313HY
* SM-G313M
* SM-G313MY
* SM-G313U

관리자와 최종 사용자는 더 이상 조치를 취할 필요가 없습니다. 자세한 내용은 [Samsung KNOX](https://www.samsungknox.com) 웹 사이트를 참조하세요.

__Windows 8용 회사 포털 앱은 사용되지 않으며, Windows Phone 8 및 Windows RT 플랫폼도 사용되지 않을 것입니다.__ 2016년 10월부터 Microsoft Intune에서는 Windows 8 회사 포털을 더 이상 지원하지 않습니다. 또한 Windows Phone 8 및 Windows RT 플랫폼도 지원되지 않을 것입니다. 따라서 Windows Phone 8 또는 Windows RT 장치를 등록하거나 업데이트할 수 없게 됩니다.

이미 등록된 Windows Phone 8, Windows RT 및 Windows 8 장치는 계속 관리할 수 있습니다. 서비스 중단 없이 이러한 장치에 앱을 계속 배포하려면 Windows Phone 8 및 Windows 8 장치를 Windows 8.1 및 Windows Phone 8.1로 업데이트하고 해당하는 Windows 8.1 및 Windows Phone 8.1 회사 포털 앱을 사용하세요.

2016년 11월부터 Windows Phone 8 회사 포털을 더 이상 지원하지 않습니다.
<!--TFS 1255391-->

### <a name="whats-coming"></a>향후 예정 사항

__Windows 10 장치에 사용할 수 있는 새로운 Microsoft Intune 회사 포털__ Microsoft는 새로운 Windows 10 장치용 Microsoft Intune 회사 포털을 출시하고 있습니다. 이 앱은 새로운 Windows 10 유니버셜 형식을 활용하고 있으며, 현재 사용 중인 모든 기능을 계속 사용할 수 있게 하면서 사용자에게 앱의 업데이트된 사용자 환경과 모든 Windows 10 장치, PC 및 모바일 유사 장치에 걸쳐 동일한 환경을 제공합니다.

새 앱을 사용하면 사용자가 Windows 10 장치에서 SSO(Single Sign-On) 및 인증서 기반 인증과 같은 추가적인 플랫폼 기능도 활용할 수 있습니다. 이 앱은 기존 Windows 8.1 회사 포털과 Windows Phone 8.1 회사 포털에 대한 업그레이드로서 Windows 스토어에서 설치해 사용할 수 있습니다. 자세한 내용은 [aka.ms/intunecp_universalapp](http://aka.ms/intunecp_universalapp)를 참조하세요.
<!--TFS 1016502-->

## <a name="september-2016"></a>2016년 9월
### <a name="new-features-announcements-and-information"></a>새로운 기능, 공지 사항 및 정보
* [Windows 조건부 액세스](#windows-conditional-access)
* [iOS 10 지원](#ios-10-support)
* [앱 래핑 도구는 Android 및 iOS에 대한 장치 등록 없이 MAM 지원](#app-wrapping-tool-supports-mam-without-device-enrollment-for-android-and-ios)
* [9월에 Intune 그룹에서 Azure Active Directory로 전환 시작](#intune-groups-begin-transitioning-to-azure-active-directory-in-september)
* [Android 장치를 보호하기 위한 Lookout 통합](#lookout-integration-to-protect-android-devices)
* [Android, iOS 및 Windows용 회사 포털 업데이트](#company-portal-updates)
* [Intune 용어](#intune-glossary)
* [향후 예정 사항](#whats-coming)

### <a name="windows-conditional-access"></a>Windows 조건부 액세스
이제 Intune 관리 콘솔을 통해 Windows PC가 Exchange Online 및 SharePoint Online에 액세스하지 못하도록 하는 조건부 액세스 정책을 만들 수 있습니다. 또한 Office 데스크톱 및 유니버설 응용 프로그램에 대한 액세스를 차단하기 위한 조건부 액세스 정책을 만들 수 있습니다.

### <a name="ios-10-support"></a>iOS 10 지원
기존 Intune MDM 및 MAM 시나리오는 iOS 10과 호환됩니다. 팁은 [Intune Support Team Blog](https://blogs.technet.microsoft.com/intunesupport/2016/09/13/support-tip-intune-support-for-ios-10/)(Intune 지원 팀 블로그)를 참조하세요.

### <a name="app-wrapping-tool-supports-mam-without-device-enrollment-for-android-and-ios"></a>앱 래핑 도구는 Android 및 iOS에 대한 장치 등록 없이 MAM 지원
Intune 앱 래핑 도구는 iOS 및 Android용 LOB(기간 업무) 앱에서 Intune MAM을 사용하도록 설정하는 데 사용하는 명령줄 도구입니다. Intune을 통해 배포된 MAM 정책을 앱에서 적용할 수 있도록 앱에 Intune MAM SDK를 통합하는 가장 간단한 방법입니다. MAM 정책을 사용하여 다음을 수행할 수 있습니다.

1. 응용 프로그램의 데이터를 암호화합니다.
2. 정보 근로자가 앱을 시작할 때 PIN을 입력하도록 요구합니다.
3. 앱에서 다른 관리되는 앱으로만 데이터를 전송하도록 허용합니다.
4. 앱에서 데이터를 Android, iTunes 및 iCloud에 백업하지 못하게 합니다.
5. 다른 관리되는 앱으로 또는 이 앱에서 잘라내기, 복사 및 붙여넣기만 허용합니다.

업데이트된 Intune 앱 래핑 도구의 공개 미리 보기에서는 이제 iOS 및 Android의 내부 LOB 앱에서 장치 등록 없이도 MAM를 지원합니다. 즉, 최종 사용자가 장치를 Intune에 등록하지 않고도 MAM 지원 LOB 앱을 사용할 수 있습니다.

누구나 공개 미리 보기 소프트웨어를 테스트하고 msintuneappsdk의 GitHub에 있는 유용한 설명서를 읽을 수 있습니다.

<p style="margin-left: 40px">http://www.github.com/msintuneappsdk/intune-app-wrapper-ios-preview

<p style="margin-left: 40px">http://www.github.com/msintuneappsdk/intune-app-wrapper-android-preview

Android 및 iOS용 Microsoft Intune 앱 래퍼 시험판을 설치하고 사용하기 전에 다음을 수행해야 합니다.

* Android 및 iOS용 Microsoft Intune 앱 래퍼 시험판에 대한 Microsoft 사용 조건 검토
* 기록을 위해 사용 조건의 사본을 인쇄하여 보관. Android용 Microsoft Intune 앱 래핑 도구 시험판을 다운로드하고 사용하면 이러한 사용 조건에 동의하는 것입니다. 동의하지 않는 경우 소프트웨어를 사용하지 마세요.
<!---TFS 1235607--->

### <a name="intune-groups-begin-transitioning-to-azure-active-directory-in-september"></a>9월에 Intune 그룹에서 Azure Active Directory로 전환 시작
일부 새 Intune 계정은 Intune 사용자 그룹이 아닌 Azure Active Directory 보안 그룹을 사용합니다. Intune 포털 그룹 페이지에 Azure 관리 포털로 연결되는 링크가 있으면 보안 그룹을 사용 중인 것입니다.

### <a name="lookout-integration-to-protect-android-devices"></a>Android 장치를 보호하기 위한 Lookout 통합
Microsoft는 Android 장치에서 맬웨어, 위험한 앱 등을 감지하여 장치를 보호하기 위해 Lookout의 모바일 위협 방지 솔루션과 통합합니다. Lookout의 솔루션을 통해 위협 수준을 결정할 수 있고, 이 수준은 구성이 가능합니다. Lookout의 위협 평가를 기준으로 장치 준수를 결정하는 준수 정책 규칙을 Intune에서 만들 수 있습니다. 조건부 액세스 정책을 사용하여 장치 준수 상태에 따라 회사 리소스에 대한 액세스를 허용하거나 차단할 수 있습니다.

비준수 장치의 최종 사용자는 등록하라는 메시지가 표시되며 Android 장치에서 Lookout for Work 응용 프로그램을 설치하고, 앱을 활성화하고, Lookout for Work 응용 프로그램에 보고된 위협을 해결해야만 액세스 권한을 얻게 됩니다. 자세한 내용은 [Restrict access based on device, network, and application risk](https://docs.microsoft.com/en-us/intune/deploy-use/restrict-access-based-on-device-network-app-risk)(장치, 네트워크 및 응용 프로그램 위험에 따라 액세스 제한)를 참조하세요.


### <a name="company-portal-updates"></a>회사 포털 업데이트

__Android__

<p style="margin-left: 40px">**Android용 회사 포털에 “알림” 추가**<br/>
<p style="margin-left: 40px">홈페이지의 Android용 회사 포털에 새 알림 아이콘이 추가되었습니다. 이 아이콘을 탭하면 장치 비준수, 등록 업데이트, 등록 활성화 등 회사 포털 앱에서 주의가 필요한 모든 항목을 최종 사용자에게 보여 주는 알림 페이지에 액세스할 수 있습니다. iOS 회사 포털 앱에는 이 알림 환경이 이미 있습니다. 새 알림 페이지가 있으므로 장치가 이미 등록되어 있으면 사용자가 회사 포털을 실행하거나 다시 시작할 때마다 회사 액세스 설정 페이지가 표시되지 않습니다. 고유한 최종 사용자 지침을 만든 경우 이 변경 내용을 반영하도록 문서를 업데이트하는 것이 좋습니다. 업데이트된 스크린샷은 [여기](https://aka.ms/androidcpupdate)에서 볼 수 있습니다.  

__iOS__
<p style="margin-left: 40px">**iOS 회사 포털 앱에 대한 지원의 변경 내용**<br/>
<p style="margin-left: 40px">이제 iOS용 Microsoft Intune 회사 포털 앱의 모든 사용자가 최신 버전을 사용해야 합니다. 새 사용자는 최신 버전만 다운로드할 수 있고 현재 사용자는 최신 버전으로 업데이트해야 합니다. 최신 버전을 사용하려면 iOS 8.0 이상이 필요하므로 이전 iOS 버전을 실행하는 장치는 장치를 iOS 8.0 이상으로 업데이트한 다음 회사 포털 앱을 최신 버전으로 업데이트할 때까지 회사 포털을 사용하거나 등록할 수 없습니다. iOS 8.0 이전 버전을 실행하는 등록된 장치는 Intune 관리자 콘솔에서 계속 관리되고 표시됩니다.
<!---TFS 1283165--->

<p style="margin-left: 40px">**iOS 최종 사용자가 앱을 받는 방법에 대한 개선 사항**<br/>
<p style="margin-left: 40px">iOS용 회사 포털 앱의 앱 타일이 다음과 같이 변경되어 사용자의 모든 앱에 대해 회사 포털 웹 사이트라는 하나의 위치에 있는 다른 보기를 가리킵니다. Apple 제한 사항에 따라 기간 업무 및 관리되는 앱 스토어 앱이 회사 포털 앱에 나열되지 못하므로 사용자는 앱을 모두 찾으려면 여러 보기를 방문해야 합니다.

<p style="margin-left: 40px">**회사 앱** 타일은 이전에 회사 포털 웹 사이트의 모두 탭에 있는 모든 앱 목록을 가리켰는데, 계속해서 같은 방식으로 작동합니다. 타일 이름은 **모든 앱**으로 변경되었습니다.

<p style="margin-left: 40px">**기타 앱** 타일은 기존에는 Apple이 회사 포털 앱에서 표시하도록 허용하는 모든 앱을 나열하는 회사 포털 앱 내의 보기를 가리켰습니다. 타일 이름이 **추천 앱**으로 변경되었으며 타일을 탭하면 회사 포털 웹 사이트의 추천 탭으로 이동됩니다.

<p style="margin-left: 40px">**카테고리** 타일은 이전에 앱의 범주를 나열하는 회사 포털 앱 내 보기를 가리켰습니다. 타일 이름이 변경되지 않았지만 이제는 회사 포털 웹 사이트의 범주 탭을 가리킵니다. 업데이트된 스크린샷은 [여기](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186)에서 볼 수 있습니다.
  <!---TFS 1317133--->

<p style="margin-left: 40px">**IT Pro에서 해당 앱 요구 사항을 설정하면 iOS Managed Browser 앱을 설치하라는 메시지가 표시됨**<br/>
<p style="margin-left: 40px">웹 클립을 Managed Browser에서만 열 수 있도록 구성했지만 장치에 Managed Browser가 설치되어 있지 않은 경우 장치의 회사 포털 앱에서는 웹 클립을 설치하기 전에 먼저 Managed Browser를 설치하라는 메시지를 표시합니다.
  <!---TFS 1228570--->

__Windows__
<p style="margin-left: 40px">**Windows Phone 8.1 회사 포털 앱에 추가된 사용자 의견 단추**<br/>
<p style="margin-left: 40px">Windows Phone 8.1 회사 포털 앱에서는 최종 사용자가 새 "사용자 의견 보내기" 단추를 사용하여 앱에 대한 피드백을 보낼 수 있습니다. 단추를 찾으려면 회사 포털 앱 화면의 오른쪽 아래에 있는 "3개의 점" 메뉴를 탭한 다음 **사용자 의견 보내기**를 탭합니다. 익명으로 수집된 피드백은 Microsoft가 사용자를 위해 회사 포털 앱 환경을 개선하는 데 도움이 됩니다.
<!---TFS 1317806--->

### <a name="intune-glossarybr"></a>Intune 용어</br>
Intune 제품에 사용되는 일부 용어를 이해하는 데 도움이 되도록 라이브러리에 새 [용어 항목](https://docs.microsoft.com/intune/understand-explore/intune-glossary)을 추가했습니다.

## <a name="august-2016"></a>2016년 8월
### <a name="app-management"></a>앱 관리
<!---@Barry, I created the buckets of App management, Device management, etc but am not tied to them. Just wanted to break up and organize the feature list. If you're going to take over the Company Portal section, please talk to Stacie about how she's been organizing it. --->

__iOS 9.3에 대해 숨겨진/표시된 앱__ iOS 9.3 이상을 실행하는 장치의 경우 iOS 일반 구성 정책에서 숨겨진/표시된 앱 목록을 사용하여 다음을 수행할 수 있습니다.
- 사용자로부터 숨길 앱 목록을 지정합니다. 사용자는 이러한 앱을 보거나 시작할 수 없습니다.
- 사용자가 보고 시작할 수 있는 앱 목록을 지정합니다. 다른 앱은 보거나 시작할 수 없습니다.

지정할 수 있는 앱에는 사용자가 배포한 앱과 메시지 및 메모와 같은 기본 제공 iOS 앱이 모두 포함됩니다. 자세한 내용은 [Microsoft Intune의 iOS 정책 설정](https://docs.microsoft.com/intune/deploy-use/ios-policy-settings-in-microsoft-intune)을 참조하세요.
<!---TFS 1279009 checked--->
__Samsung KNOX 장치에 대해 허용된/차단된 앱 정책__ 이제 Samsung KNOX 장치용 사용자 지정 정책을 구성하여 다음 중 하나를 만들 수 있습니다.
- 장치에서 실행되지 않도록 차단할 앱 목록. 차단된 목록에 정의된 앱은 설치된 경우에도 장치에서 활성화할 수 없습니다.
- 장치의 사용자가 Google Play 스토어에서 설치할 수 있는 앱 목록입니다. 다른 앱은 스토어에서 설치할 수 없습니다.

이러한 설정은 삼성 KNOX를 실행하는 장치에서만 사용할 수 있습니다.
자세한 내용은 [사용자 지정 정책을 사용하여 Samsung KNOX 장치에 대해 앱을 허용하거나 차단](https://docs.microsoft.com/en-us/intune/deploy-use/custom-policy-to-allow-and-block-samsung-knox-apps)을 참조하세요.
<!---TFS 1311629 checked --->

__MAM(모바일 응용 프로그램 관리) 정책과 호환되는 새로운 앱__ [iOS](https://itunes.apple.com/app/yammer/id289559439?mt=8) 및 [Android](https://play.google.com/store/apps/details?id=com.yammer.v1)용 Yammer 앱은 이제 장치 등록 여부에 상관없이 [Intune MAM(모바일 응용 프로그램 관리) 정책](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)과 호환됩니다.

MAM과 호환되는 앱의 전체 목록은 [Microsoft Intune application partners](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners)(Microsoft Intune 응용 프로그램 파트너) 사이트를 참조하세요.
<!--- TFS 1252335 & 1252336 checked--->


<!--- I started putting TFS numbers in the What's Coming topic and found it helpful when updating the What's New. Up to you if you want to continue. --->

__Intune 뷰어 앱__ 2016년 8월부터 새 RMS 공유 앱의 릴리스에서 다음 Intune 뷰어 앱을 제거합니다.
- Intune AV 뷰어
- Intune PDF 뷰어
- Google Play의 Android용 Intune 이미지 뷰어

Intune 뷰어 앱을 사용하는 대신 [새로운 Android용 Microsoft Rights Management 공유 앱(RMS 공유)](https://docs.microsoft.com/en-us/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app)을 사용하는 것이 좋습니다. 이 앱을 통해 세 개의 별도 앱이 아니라 하나의 앱을 배포하여 Android 장치에서 회사 파일을 안전하게 볼 수 있습니다. Intune 뷰어 앱이 더 이상 지원되지 않으면 Google 스토어에서 제거되며 향후 사용할 수 없게 됩니다.

### <a name="device-management"></a>장치 관리
__Android 7.0 지원__ Intune에서는 모바일 장치용으로 곧 출시 예정인 Android 7.0 운영 체제에 대해 “Day 0” 지원을 제공합니다.
<!---TFS 1262053--->
### <a name="google-removal-of-remote-passcode-reset-capability-on-android-70-devices"></a>Android 7.0 장치에서 Google의 원격 암호 재설정 기능 제거
Google에서 IT 관리자와 최종 사용자가 Android 7.0 장치의 암호를 원격으로 다시 설정하는 기능을 제거할 예정입니다. 이전에는 IT 관리자가 원격으로 사용자의 암호를 다시 설정하고, 최종 사용자가 회사 포털 웹 사이트에서 자신의 암호를 다시 설정할 수 있었습니다.



### <a name="company-portal-updates"></a>회사 포털 업데이트
__회사 포털 웹 사이트__
- **회사 포털에서 Microsoft로 피드백 링크** <br/>
최종 사용자는 회사 포털 웹 사이트에서 페이지 맨 아래에 있는 새 "사용자 의견" 링크를 탭하여 사이트 경험에 대한 피드백을 Microsoft에 보낼 수 있습니다. 익명으로 수집된 피드백은 Microsoft가 사용자를 위해 회사 포털 웹 사이트를 개선하는 데 도움이 됩니다.
<!--- TFS 1313657 checked--->

__iOS__
- **최소 iOS 관리 브라우저 버전이 8.0으로 업데이트됨**<br/>
iOS용 Microsoft Intune Managed Browser 앱이 iOS 8.0 이상을 실행하는 장치를 지원하도록 업데이트되었습니다. iOS 7.1 장치는 기존의 관리 브라우저 앱을 사용할 수 있지만 새로운 관리 브라우저 기능을 액세스하고 완전히 사용하기 위해서는 iOS 8.0 이상으로 업데이트하는 것이 좋습니다.  
<!---TFS 1313253 checked--->

### <a name="whats-coming"></a>향후 예정 사항
__2016년 9월부터 Intune 그룹에서 Azure Active Directory 그룹으로 전환__ Intune은 Intune에서 AAD(Azure Active Directory) 보안 그룹을 사용자 및 장치 그룹으로 사용하는 새로운 그룹 관리 환경을 만들고 있습니다. 이러한 그룹은 **새 Azure 기반 Intune 관리 포털을 도입할 때 **모든 그룹 관리, 정책 배포 및 프로필 배포에 사용됩니다.

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

__Android용 회사 포털에 '알림' 추가__ 9월에는 홈페이지에 새 **알림** 아이콘을 추가하는 업데이트를 Android용 회사 포털에 릴리스할 예정입니다. 이 아이콘을 누르면 호환되지 않는 장치, 등록 업데이트 및 등록 활성화와 같이 회사 포털 앱에서 주의가 필요한 모든 항목을 최종 사용자에게 표시하는 **알림** 페이지로 이동됩니다. IOS 회사 포털 앱을 사용하는 경우에는 이미 알림을 제공받았을 것입니다. **알림** 페이지가 도입되면서 장치가 등록된 동안 Android용 회사 포털을 시작하거나 다시 시작할 때마다 **회사 액세스 설정** 페이지가 항상 표시되지는 않습니다. 많은 고객 여러분이 최종 사용자 지침을 만드는 데 도움을 주신 점을 알고 있습니다. 지침/스크린샷을 업데이트해야 할 때 미리 알려 주시는 점에 감사드립니다. 예정된 변경 내용을 환경에 반영하려면 설명서를 업데이트하세요. 업데이트된 스크린샷을 보려면 https://aka.ms/androidcpupdate로 이동하세요.  

### <a name="service-deprecation"></a>서비스 중단
<!---@Barry, we started listing service deprecations earlier this summer. --->
- **iOS 회사 포털 앱에 대한 지원의 변경 내용**<br/>
9월에 iOS용 Microsoft Intune 회사 포털 앱의 모든 사용자는 최신 버전을 사용해야 합니다. 새 사용자는 최신 버전만 다운로드할 수 있고 현재 사용자는 최신 버전으로 업데이트해야 합니다. 최신 버전을 사용하려면 iOS 8.0 이상이 필요하므로 이전 iOS 버전을 실행하는 장치는 장치를 iOS 8.0 이상으로 업데이트한 다음 회사 포털 앱을 최신 버전으로 업데이트할 때까지 회사 포털을 사용하거나 등록할 수 없습니다. iOS 8.0 이전 버전을 실행하는 등록된 장치는 Intune 관리자 콘솔에서 계속 관리되고 표시됩니다.  

- **최소 iOS 관리 브라우저 버전이 8.0으로 업데이트됨**<br/>
8월에 Intune은 iOS 8.0 이상이 실행되는 장치만 지원하는 업데이트된 iOS용 Microsoft Intune 관리 브라우저 앱을 릴리스할 예정입니다. IOS 7.1 장치는 기존의 관리 브라우저 앱을 사용할 수 있지만 새로운 관리 브라우저 기능을 액세스하고 완전히 사용하기 위해서는 iOS 8.0 이상으로 업데이트하는 것이 좋습니다.  
<!---TFS 1313253--->

- **Windows 8 및 Windows Phone 8용 회사 포털 앱은 2016년 9월부터 사용되지 않습니다.** <br/>
2016년 9월부터 Microsoft Intune은 Windows Phone 8 및 Windows 8 플랫폼용 Microsoft Intune 회사 포털 앱에 대한 지원을 종료합니다. 장치를 Windows 8.1 및 Windows Phone 8.1로 업데이트하고 해당하는 Windows 8.1 및 Windows Phone 8.1 회사 포털 앱을 사용하여 이러한 장치에 앱을 계속 배포하세요.
<!---TFS 1255391--->

<!--- - **Custom Group Targeting of Notification Rules Removal.**<br/>
Intune notification rules define who an email alert will be sent to from Intune. Currently, you can configure notification rules to send emails to all users of devices in an Intune device group that you created. From around June 1st 2016 moving forward, targeting user-created groups will no longer be supported.

    Today, to target a notification rule to a group you created from the Microsoft Intune administration console, you would take the following steps:

    In the **Admin** workspace, click **Notification Rules** > **Create New Rule**

    In step two of the Create Notification Rule Wizard, select the device groups which the rule will target. This step, “select device groups”, is being removed from the Intune Console.

    The preliminary timeline for this change is as follows:
    - In August, 2016, new tenants will not see step two of the Create Notification Rule Wizard. Exiting tenants are unaffected.
    - Around September, 2016, some existing tenants will not see the “select device groups” in the wizard.
    - Around November, 2016, we expect that all tenants will not see the “select device groups” in the wizard.

--->

## <a name="july-2016"></a>2016년 7월
### <a name="app-management"></a>앱 관리

__앱 프로비전 프로필 업데이트 환경 개선__ Apple iOS LOB(기간 업무) 모바일 앱은 프로비전 프로필을 포함하고 인증서로 코드에 서명하여 빌드됩니다. 앱이 iOS 장치에서 실행되면 iOS는 iOS 앱의 무결성을 확인하고 프로비전 프로필에 정의된 정책을 적용합니다.

일반적으로 앱에 서명하기 위해 사용하는 엔터프라이즈 서명 인증서는 3년 동안 유지됩니다. 그러나 프로비전 프로필은 1년 후에 만료됩니다. 이 업데이트를 사용하면 Intune은 인증서가 여전히 유효한 동안 만료일이 다가오는 앱이 있는 장치에 새 프로비전 프로필 정책을 미리 배포하기 위한 도구를 제공합니다. 자세한 내용은 [iOS 모바일 프로비전 프로필 정책을 사용하여 LOB(기간 업무) 앱을 최신 상태로 유지](/intune/deploy-use/ios-mobile-app-provisioning-profiles)를 참조하세요.
<!--- TFS 1280247--->

__Intune용 Xamarin SDK 앱을 사용할 수 있음__ Intune 앱 SDK Xamarin 구성 요소를 사용하면 Xamarin으로 빌드된 모바일 iOS 및 Android 앱에서 Intune 모바일 앱 관리 기능을 설정할 수 있습니다. [Xamarin 스토어](https://components.xamarin.com/view/Microsoft.Intune.MAM) 또는 [Microsoft Intune Github 페이지](https://github.com/msintuneappsdk)에서 해당 구성 요소를 찾을 수 있습니다.
<!--- TFS 1061478 --->

### <a name="device-management"></a>장치 관리
__증가된 장치 등록 제한__ Intune은 사용자당 구성 가능한 최대 장치 등록 제한을 5대에서 15대로 늘립니다.
<!---TFS 1289896 --->

__Intune 클라이언트 소프트웨어를 실행하는 Windows PC용 TeamViewer 통합__
Intune 클라이언트를 실행하는 Windows PC용 [TeamViewer](https://www.teamviewer.com) 통합을 통해 Windows PC와 원격 지원 세션을 설정하여 최종 사용자 지원 센터 부서를 지원할 수 있습니다. 여기에는 Windows 7, 8, 8.1 및 Windows 10이 포함됩니다. 자세한 내용은 [Microsoft Intune 컴퓨터 클라이언트를 사용한 일반 Windows PC 관리 작업](/intune/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client) 항목을 참조하세요.
<!---TFS 1284856--->

### <a name="company-portal-updates"></a>회사 포털 업데이트

__회사 포털 웹 사이트__
- **Windows 장치를 등록할 때 향상된 최종 사용자 환경**<br/>
조건부 액세스를 사용하는 경우 회사 포털 웹 사이트에서 Windows 8.1, Windows 10 Desktop 및 Windows 10 Mobile 등록 단계가 명확해졌습니다. 이제 "장치 등록" 및 "작업 공간 연결" 단계가 별도로 표시되므로, WPJ(작업 공간 연결) 오류가 발생한 경우 장치의 상태를 더욱 쉽게 확인하고 프로세스를 완료할 수 있습니다. 또한 별도의 단계를 통해 IT 관리자의 문제 해결 프로세스를 간소화할 수 있을 것으로 예상됩니다. 이전에는 최종 사용자가 등록하려고 할 때 WPJ를 제외한 모든 등록 단계가 정상적으로 수행되면, 등록된 장치가 사용자의 장치 목록에 나타나지 않아 혼동을 줄 수 있었습니다.

__Android__
- **Android 회사 포털 앱**<br/>
Android 최종 사용자에게 장치에 필수 인증서가 없다는 오류 메시지가 표시되면 "이 문제를 해결하는 방법" 단추를 눌러 누락된 인증서를 설치하기 위한 [단계](/intune/enduser/your-device-is-missing-a-required-certificate-android#your-device-is-missing-a-certificate-required-by-your-it-administrator)를 진행할 수 있습니다. 이러한 단계를 완료해도 "누락된 인증서" 오류 메시지가 추가로 표시될 경우 IT 관리자에게 문의하여 IT 관리자가 인증서 문제를 해결하는 데 사용할 수 있는 단계가 포함된 [링크](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#android-certificate-issues)를 제공해야 합니다.

- **테스트용으로 앱 설치를 등록된 장치로 제한**<br/>
장치가 Android용 Intune 회사 포털 앱을 사용하여 Intune에 등록되어 있지 않으면 더 이상 Android 장치에 회사 포털 웹 사이트를 통해 응용 프로그램을 설치할 수 없습니다.
<!---TFS 1299082--->

__iOS__
- **iOS 회사 포털 앱의 장치 등록 관리자 계정의 변경 내용**<br/>
성능과 확장성을 개선하기 위해, Intune은 iOS 회사 포털 앱의 **내 장치** 창에 더 이상 모든 장치 등록 관리자(DEM)를 표시하지 않을 예정입니다. 앱을 실행하는 로컬 장치가 회사 포털 앱을 통해 등록된 경우에만 표시합니다.

DEM 사용자는 로컬 장치에서 작업을 수행할 수 있지만 다른 등록된 장치의 원격 관리는 Intune 관리 콘솔에서만 수행할 수 있습니다. 또한 Intune은 Apple 장비 등록 프로그램 또는 Apple Configurator 도구에서 DEM 계정 사용을 더 이상 지원하지 않습니다. 두 등록 방법은 모두 공유 iOS 장치에 대한 사용자가 지정되지 않은 등록을 이미 지원합니다.

공유 장치에 대한 사용자가 지정되지 않은 등록을 사용할 수 없는 경우만 DEM 계정을 사용합니다. 자세한 내용은 [Microsoft Intune에서 장치 등록 관리자를 사용하여 회사 소유의 장치 등록](https://docs.microsoft.com/en-us/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)을 참조하세요.
<!---TFS 1233681--->

### <a name="change-of-names-for-windows-features"></a>Windows 기능의 이름 변경
- 이제 [Microsoft Passport for Windows](/intune/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune)를 **비즈니스용 Windows Hello**라고 합니다.
- [엔터프라이즈 데이터 보호](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune)를 **Windows 정보 보호**라고 합니다.

## <a name="june-2016"></a>2016년 6월
### <a name="intune-service-health"></a>Intune 서비스 상태
Intune에 대한 서비스 상태 정보는 다른 Microsoft 서비스와 함께 중앙 위치로 이동되었습니다. 이 정보는 이제 Office 365 관리 포털의 서비스 상태에서 찾을 수 있습니다. 자세한 내용은 [이 블로그 게시물](https://blogs.technet.microsoft.com/enterprisemobility/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/)을 참조하세요.

### <a name="app-management"></a>앱 관리
- **Windows 10 엔터프라이즈 데이터 정책 구성 환경이 개선되었습니다.** 앱 규칙 생성, 네트워크 경계 정의 지정 및 기타 엔터프라이즈 데이터 보호 설정과 관련된 Windows 10 엔터프라이즈 데이터 보호 정책 구성 환경이 개선되었습니다. 자세한 내용은 [Create an enterprise data protection (EDP) policy using Microsoft Intune](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune)(Microsoft Intune을 사용하여 EDP(엔터프라이즈 데이터 보호) 정책 만들기)을 참조하세요.


### <a name="device-management"></a>장치 관리
- **원치 않는 앱으로부터 보호하기 위한 Windows Defender 정책 설정.** **사용자 동의 없이 설치된 응용 프로그램 검색**이라고 하는 새로운 Windows Defender 설정이 Windows 10 Desktop 및 Mobile에 대한 일반 구성 정책에 추가되었습니다. 이 설정을 사용하여 Windows Defender에서 사용자 동의 없이 설치된 소프트웨어로 분류된 프로그램에 대해 등록된 Windows 데스크톱 컴퓨터를 보호할 수 있습니다. 실행 중인 이러한 응용 프로그램으로부터 보호하거나 감사 모드를 사용하여 사용자 동의 없이 응용 프로그램이 설치될 때 보고할 수 있습니다. 자세한 내용은 [Microsoft Intune의 Windows 10 정책 설정](https://docs.microsoft.com/en-us/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)을 참조하세요.
<!---TFS 1244478--->

### <a name="conditional-access"></a>조건부 액세스
- **Intune에 대한 Cisco ISE 네트워크 액세스 제어 정책.**  Cisco ISE(Identity Service Engine) 2.1 및 Microsoft Intune을 사용하는 고객은 ISE에서 네트워크 액세스 제어 정책을 설정할 수 있습니다.

    이 정책을 사용하여 WiFi 또는 VPN을 통해 네트워크에 연결해야 하는 장치는 다음 조건을 충족해야 액세스가 허용됩니다.

    * Intune에서 관리되어야 합니다.
    * 배포된 Intune 준수 정책을 준수해야 함

 비규격 장치의 최종 사용자는 액세스하기 위해 등록하고 준수 문제를 해결하도록 요구됩니다.
- **브라우저에 대한 조건부 액세스.** 정책을 준수하고 관리되는 iOS 및 Android 장치의 지원되는 웹 브라우저에서만 액세스할 수 있도록 [Exchange Online](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune) 및 [SharePoint Online](/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune)에 대한 조건부 액세스 정책을 설정할 수 있게 됩니다. iOS 및 Android 장치를 사용하여 Outlook Web Access(OWA) 및 SharePoint 사이트에 로그인하려는 최종 사용자에게는 Intune을 사용하여 장치를 등록하라는 메시지는 물론 로그인을 완료하기 전에 비호환 문제가 있으면 수정하라는 메시지를 표시하게 됩니다.
<!---TFS 1175844--->

- **Dynamics CRM Online에서 조건부 액세스를 지원합니다.** 정책을 준수하고 관리되는 iOS 및 Android 장치에서만 액세스할 수 있도록, [Dynamics CRM Online](/intune/deploy-use/restrict-access-to-dynamics-crm-online-with-microsoft-intune)에 대한 조건부 액세스 정책을 설정할 수 있습니다. iOS 및 Android에서 Dynamics CRM 모바일 앱에 로그인하려고 하는 최종 사용자에게 Intune에 등록하고 로그인을 완료하기 전에 모든 비호환성 문제를 해결해야 한다는 메시지가 표시됩니다.
<!---TFS1295358--->

### <a name="intune-company-portal-updates"></a>Intune 회사 포털 업데이트

__Android 회사 포털 앱__

- IT 관리자가 새 “장치가 알 수 없는 소스의 앱 설치를 방지해야 함(Android 4.0 이상)” 정책을 적용하면 Android 4.0 이상 장치를 사용하는 최종 사용자에게 "알 수 없는 소스에서의 설치를 금지해야 합니다." 메시지가 표시됩니다. **설정** > **보안**으로 이동한 후 **알 수 없는 원본**을 해제해야 합니다. 규정 준수 메시지의 링크를 클릭하면 해당 메시지에 대한 추가 [정보](/Intune/EndUser/you-are-asked-to-turn-off-unknown-sources-android)와 설정을 해제해야 하는 이유가 표시됩니다.

- IT 관리자가 새 “앱의 보안 위협 검색을 사용하도록 장치가 설정되어 있어야 함(Android 4.0 이상)” 정책을 적용하면 Android 4.0 이상 장치를 사용하는 최종 사용자에게 "장치의 보안 위협 검색" 메시지가 표시됩니다. 사용자는 **설정** > **Google** > **보안**으로 이동한 후 **장치의 보안 위협 검색**을 켜야 합니다. 규정 준수 메시지의 링크를 클릭하면 해당 메시지에 대한 추가 [정보](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android)와 설정을 켜야 하는 이유가 표시됩니다.

- IT 관리자가 새 "USB 디버깅을 사용하지 않도록 설정되어야 함(Android 4.2 이상)" 정책을 적용하면 Android 4.2 이상 장치를 사용하는 최종 사용자에게 "USB 디버깅을 사용하지 않도록 설정해야 합니다." 메시지가 표시됩니다. **설정** > **개발자 옵션**으로 이동하여 **USB 디버깅**을 해제해야 합니다. 규정 준수 메시지의 링크를 클릭하면 해당 메시지에 대한 추가 [정보](/Intune/EndUser/you-are-asked-to-turn-off-usb-debugging-android)와 설정을 해제해야 하는 이유가 표시됩니다.

- IT 관리자가 새 "최소 Android 보안 패치 수준(Android 6.0 이상)" 정책을 적용하면 Android 6.0 이상 장치를 사용하는 최종 사용자에게 "이 장치는 최소 Android 보안 패치 수준을 충족하지 않습니다." 메시지가 표시됩니다. 사용자는 필수 보안 패치를 설치해야 합니다. 규정 준수 메시지의 링크를 클릭하면 필수 보안 패치를 설치하고 현재 설치되어 있는 보안 패치를 확인하는 방법에 대한 [정보](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android)가 표시됩니다.

__iOS 회사 포털 앱__

- 최종 사용자가 기간 업무 앱을 설치하는 경우, 향상된 앱 설치 환경이 표시됩니다. 앱 설치가 너무 오래 걸리면, 사용자는 동기화 프로세스가 다시 시작되도록 장치를 수동으로 동기화할 수 있습니다. 최종 사용자 지침을 검토하려면 [iOS 장치를 수동으로 동기화](/Intune/EndUser/sync-your-device-manually-ios)를 참조하세요.

- iOS에 대한 Microsoft Intune 회사 포털 앱은 iOS 버전 8.0 이상을 지원하도록 업데이트되었습니다. 이 업데이트를 사용하면 장치가 iOS 버전 8.0 이상을 실행하는 경우 최종 사용자가 회사 포털 앱을 설치하고 Intune에 새 장치를 등록할 수 있습니다. 지원되지 않는 iOS 버전을 실행 중이고 이미 등록된 장치가 있는 사용자는 자신의 장치에 있는 회사 포털 앱을 계속 사용할 수 있습니다.


<!--HONumber=Dec16_HO1-->


