# <a name="february-2017"></a>2017 년 2월

## <a name="new-capabilities"></a>새로운 기능

### <a name="modernizing-the-company-portal-website---753980--"></a>회사 포털 웹 사이트 현대화 <!--753980-->
회사 포털 웹 사이트는 관리 장치가 없는 사용자를 대상으로 하는 앱을 지원합니다. 이 웹 사이트는 새로운 대비 색 구성표, 동적 일러스트레이션, 기술 지원팀 연락처 세부 정보 및 기존 관리 장치에 대한 정보를 포함하는 "햄버거 메뉴" ![이제 회사 포털 웹 사이트 왼쪽 상단에 추가된 햄버거 메뉴의 작은 이미지](/intune/whats-new/media/CP_hamburger_menu.png)를 사용하여 다른 Microsoft 제품 및 서비스에 맞춥니다. 방문 페이지는 추천 및 최근에 업데이트된 앱에 대한 슬라이드를 포함하여 사용자가 사용할 수 있는 앱을 강조하도록 재조정됩니다. [UI 업데이트 페이지](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui)에서 이전 및 이후 이미지를 찾을 수 있습니다.

### <a name="new-guided-experience-for-windows-10-company-portal---713927--"></a>Windows 10 회사 포털에 대한 새로운 단계별 환경 <!--713927-->
3월부터 Windows 10용 회사 포털에 식별되거나 등록되지 않은 장치에 대한 단계별 Intune 연습 환경이 포함됩니다. 새 환경에서는 사용자의 Windows 10 빌드에 맞게 사용자 지정된 단계별 지침을 제공합니다. 이를 통해 사용자는 AAD 등록(조건부 액세스 식별 기능에 필요) 및 MDM 등록(장치 관리 기능에 필요)을 수행할 수 있습니다. 단계별 환경은 회사 포털 홈에서 액세스할 수 있으며 선택 사항입니다. 사용자는 등록을 완료하지 않은 경우에도 앱을 계속 사용할 수 있지만 기능이 제한될 수 있습니다.

## <a name="notices"></a>알림

### <a name="group-migration-will-not-require-any-updates-to-groups-or-policies-for-ios-devices---898837--"></a>iOS 장치의 그룹 또는 정책에 대한 업데이트에는 그룹 마이그레이션이 필요 없음 <!--898837-->
회사 장치 등록 프로필에서 미리 할당된 모든 Intune 장치 그룹마다, Azure Active Directory 장치 그룹으로 마이그레이션하는 동안 회사 장치 등록 프로필 이름을 기반으로 AAD에 동적인 장치 그룹이 생성됩니다. 그러면 장치가 등록될 때 자동으로 그룹화되어 원래 Intune 그룹과 동일한 정책 및 앱을 받습니다.

테넌트가 그룹화 및 타기팅을 위한 마이그레이션 프로세스에 들어가고 나면, Intune은 회사 장치 등록 프로필을 통해 타기팅된 Intune 그룹에 맞는 동적 AAD 그룹을 자동으로 생성합니다. Intune 관리자가 타기팅된 Intune 그룹을 삭제해도 해당되는 동적 AAD 그룹은 삭제되지 않습니다. 그룹의 구성원과 동적 쿼리는 지워지지만, 그룹 자체는 IT 관리자가 AAD 포털을 통해 제거할 때까지 남습니다.

마찬가지로 IT 관리자가 회사 장치 등록 프로필을 통해 타기팅되는 Intune 그룹이 무엇인지 변경할 경우, Intune에서는 새 프로필 할당을 반영한 새 동적 그룹을 생성하지만 이전 할당에 대해 생성된 동적 그룹을 제거하지는 않습니다t.

### <a name="defaulting-to-managing-windows-desktop-devices-through-windows-settings---663050--"></a>Windows 설정을 통해 Windows 데스크톱 장치 관리를 기본값으로 설정<!--663050-->
Windows 10 데스크톱을 등록하는 기본 동작이 바뀌고 있습니다. 새 등록은 PC 에이전트를 통해서가 아니라 일반적인 MDM 에이전트 등록 흐름을 따릅니다. 회사 포털 웹 사이트는 Windows 10 데스크톱 사용자에게 모바일 장치로 Windows 10 데스크톱 컴퓨터를 추가하는 과정을 안내하는 등록 지침을 제공합니다. 현재 등록된 PC에는 영향을 주지 않으며, [원하는 경우](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune) 조직에서 PC 에이전트를 사용하여 Windows 10 데스크톱을 계속 관리할 수 합니다.

### <a name="improving-mobile-app-management-support-for-selective-wipe---581242--"></a>선택적 초기화에 대한 모바일 앱 관리 지원 향상 <!--581242-->
"앱 데이터를 초기화하기 전의 오프라인 간격" 정책으로 인해 데이터가 자동으로 제거되는 경우 회사 또는 학교 데이터에 다시 액세스하는 방법에 대한 추가 지침이 최종 사용자에게 제공됩니다.<!--, or the removal of the Intune Company Portal on Android.-->

### <a name="company-portal-for-ios-links-open-inside-the-app---665954--"></a>iOS용 회사 포털 링크가 앱 내에서 열림<!--665954-->
설명서 및 앱에 대한 링크를 포함하여 iOS용 회사 포털 앱 내의 링크는 Safari의 앱 내 보기를 사용하여 회사 포털 앱에서 직접 열립니다. 이 업데이트는&1;월에 서비스 업데이트에서 별도로 제공됩니다.

### <a name="new-mdm-server-address-for-windows-devices---893007--"></a>Windows 장치의 새 MDM 서버 주소 <!--893007-->
Windows 및 Windows Phone 사용자가 MDM 서버 주소 입력 메시지가 표시되었을 때 __manage.microsoft.com__을 입력할 경우 장치 등록이 실패합니다. MDM 서버 주소가 __manage.microsoft.com__에서 __enrollment.manage.microsoft.com__으로 변경됩니다. 사용자에게 Windows 또는 Windows Phone 장치를 등록하는 동안 MDM 서버 주소를 입력하라는 메시지가 표시되면 __enrollment.manage.microsoft.com__을 사용하라고 알리세요. CNAME 설정을 변경할 필요는 없습니다. 이 변경에 대한 자세한 내용을 보려면 [aka.ms/intuneenrollsvrchange](https://aka.ms/intuneenrollsvrchange)를 방문하세요.

### <a name="new-user-experience-for-the-company-portal-app-for-android---621622--"></a>Android용 회사 포털 앱의 새 사용자 환경 <!--621622-->
3월부터, Android용 회사 포털 앱이 [material design guidelines](https://material.io/guidelines/material-design/introduction.html)(재료 디자인 지침)에 따라 모양과 느낌이 더욱 세련되어집니다. 이러한 향상된 사용자 환경에는 다음이 포함됩니다.

* __색__: 탭 헤더에 사용자 지정 색상표에 따라 색을 표시할 수 있습니다.
* __인터페이스__: 앱 탭에서 추천 앱 및 모든 앱 단추가 업데이트되었습니다. 검색 단추는 이제 부동 작업 단추입니다.
* __탐색__: 모든 앱은 쉽게 탐색할 수 있도록 추천, 전체 및 범주 탭으로 구분된 뷰를 표시합니다.
* __서비스__: 내 장치 및 IT 담당자 탭 가독성을 개선했습니다.

[UI 업데이트 페이지](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui)에서 이전 및 이후 이미지를 찾을 수 있습니다.

### <a name="associate-multiple-management-tools-with-the-windows-store-for-business---926135--"></a>비즈니스용 Windows 스토어와 여러 관리 도구 연결<!--926135-->
둘 이상의 관리 도구를 사용하여 비즈니스용 Windows 스토어 앱을 배포하는 경우, 이전에는 그 중에 하나만 비즈니스용 Windows 스토어에 연결할 수 있었습니다. 이제 Intune 및 Configuration Manager와 같은 여러 관리 도구를 스토어에 연결할 수 있습니다. 자세한 내용은 [Microsoft Intune을 사용하여 비즈니스용 Windows 스토어에서 구입한 앱 관리](https://docs.microsoft.com/en-us/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune#associate-your-windows-store-for-business-account-with-intune)를 참조하세요.

## <a name="whats-new-in-the-public-preview-of-the-intune-admin-experience-on-azure---736542--"></a>Azure의 Intune 관리 환경 공개 미리 보기의 새로운 기능<!--736542-->

2017년 초에 Microsoft에서는 전체 관리 환경을 Azure로 마이그레이션합니다. 이를 통해 Graph API를 사용하여 확장 가능한 최신 서비스 플랫폼에서 핵심 EMS 워크플로에 대한 강력한 통합 관리를 지원합니다.

새 평가판 테넌트에서는 이번 달에 Azure Portal에서 새 관리 환경의 공개 미리 보기를 표시하기 시작합니다. 미리 보기 상태에서는 기존 Intune 콘솔의 기능과 패리티가 반복적으로 제공됩니다.

Azure Portal의 관리 환경에서는 이미 발표된 새 그룹화 및 대상 지정 기능을 사용합니다. 따라서 기존 테넌트가 새 그룹화 환경으로 마이그레이션될 때 사용자도 마이그레이션되어 테넌트에 새 관리 환경의 미리 보기가 표시됩니다. 그 동안 테넌트가 마이그레이션될 때까지 새 기능을 테스트하거나 살펴보려는 경우 새 Intune 평가판 계정에 등록하거나 [새 설명서](https://docs.microsoft.com/intune-azure/introduction/whats-new)를 살펴보세요.

Azure의 Intune 미리 보기에 대한 새로운 기능은 [여기](https://docs.microsoft.com/intune-azure/introduction/whats-new)에서 찾을 수 있습니다.

## <a name="january-2017"></a>2017년 1월

### <a name="new-capabilities"></a>새로운 기능

<!--### Actions for non-compliance <!--730266
_Actions for non-compliance_ is a new feature of compliance policies that lets you take action on devices that are out of compliance. You can specify single or multiple actions and specify the time period at which those actions must occur. For example, you can notify users of non-compliant devices immediately after the devices become non-compliant through email, or you can block non-compliant devices from accessing corporate resources after a 3-day grace period via Conditional Access.-->

#### <a name="in-console-reports-for-mam-without-enrollment---677961--"></a>등록과 상관없는 MAM에 대한 콘솔 내 보고서<!--677961-->
등록된 장치 및 등록되지 않은 장치 모두에 대한 새 앱 보호 보고서가 추가되었습니다. [intune을 사용하여 모바일 앱 관리 정책을 모니터링할 수 있는 방법은 여기](https://docs.microsoft.com/intune/deploy-use/monitor-mobile-app-management-policies-with-microsoft-intune)에서 확인하세요.

<!--### Conditional access for MAM with SharePoint Online <!--679339
You can block apps that are not supported by Intune mobile app management (MAM) policies from accessing SharePoint Online.  You can get started using Intune mobile app management in the Azure portal. Look for the __Conditional Access__ section in the __Settings__ blade which will include the option for SharePoint Online. This feature will ship separately from the rest of the service release. <!--Find out more about this new feature [here](https://docs.microsoft.com/intune/deploy-use/mam-ca-for-sharepoint-online).-->

#### <a name="android-711-support---694397--"></a>Android 7.1.1 지원<!--694397-->
Intune은 이제 Android 7.1.1을 완벽하게 지원하고 관리합니다.

#### <a name="resolve-issue-where-ios-devices-are-inactive-or-the-admin-console-cannot-communicate-with-them---unknown--"></a>iOS 장치가 비활성 상태이거나, 관리 콘솔에서 통신할 수 없는 경우 문제 해결 <!--unknown-->
사용자 장치에서 Intune과의 연결이 끊기는 경우 회사 리소스에 대한 액세스 권한을 다시 얻도록 새로운 문제 해결 단계를 제공할 수 있습니다. [장치가 비활성 상태이거나, 관리 콘솔에서 통신할 수 없음](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#devices-are-inactive-or-the-admin-console-cannot-communicate-with-them)을 참조하세요.

### <a name="notices"></a>알림

#### <a name="defaulting-to-managing-windows-desktop-devices-through-windows-settings---663050--"></a>Windows 설정을 통해 Windows 데스크톱 장치 관리를 기본값으로 설정<!--663050-->
Windows 10 데스크톱을 등록하는 기본 동작이 바뀌고 있습니다. 새 등록은 PC 에이전트를 통해서가 아니라 일반적인 MDM 에이전트 등록 흐름을 따릅니다.

회사 포털 웹 사이트는 Windows 10 데스크톱 사용자에게 모바일 장치로 Windows 10 데스크톱 컴퓨터를 추가하는 과정을 안내하는 등록 지침을 제공합니다. 현재 등록된 PC에는 영향을 주지 않으며, [원하는 경우](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune) 조직에서 PC 에이전트를 사용하여 Windows 10 데스크톱을 계속 관리할 수 합니다.

#### <a name="improving-mobile-app-management-support-for-selective-wipe---581242--"></a>선택적 초기화에 대한 모바일 앱 관리 지원 향상 <!--581242-->
"앱 데이터를 초기화하기 전의 오프라인 간격" 정책으로 인해 데이터가 자동으로 제거되는 경우 회사 또는 학교 데이터에 다시 액세스하는 방법에 대한 추가 지침이 최종 사용자에게 제공됩니다.<!--, or the removal of the Intune Company Portal on Android.-->

#### <a name="company-portal-for-ios-links-open-inside-the-app---665954--"></a>iOS용 회사 포털 링크가 앱 내에서 열림<!--665954-->
설명서 및 앱에 대한 링크를 포함하여 iOS용 회사 포털 앱 내의 링크는 Safari의 앱 내 보기를 사용하여 회사 포털 앱에서 직접 열립니다. 이 업데이트는&1;월에 서비스 업데이트에서 별도로 제공됩니다.

#### <a name="modernizing-the-company-portal-website---753980--"></a>회사 포털 웹 사이트 현대화 <!--753980-->
2월부터 회사 포털 웹 사이트는 관리 장치가 없는 사용자를 대상으로 하는 앱을 지원합니다. 이 웹 사이트는 새로운 대비 색 구성표, 동적 일러스트레이션, 기술 지원팀 연락처 세부 정보 및 기존 관리 장치에 대한 정보를 포함하는 "햄버거 메뉴" ![회사 포털 웹 사이트 햄버거 메뉴](/Intune/whats-new/media/CP_hamburger_menu.png)를 사용하여 다른 Microsoft 제품 및 서비스에 맞춥니다. 방문 페이지는 추천 및 최근에 업데이트된 앱에 대한 슬라이드를 포함하여 사용자가 사용할 수 있는 앱을 강조하도록 재조정됩니다. [Intune 앱 UI의 새로운 기능](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui) 페이지에서 사용 가능한 이전 및 이후 이미지를 찾을 수 있습니다.

#### <a name="new-documentation-for-app-protection-policies---583398--"></a>앱 보호 정책에 대한 새 설명서<!--583398-->
iOS 및 Android 앱에서 Intune 앱 래핑 도구 또는 Intune 앱 SDK를 사용하여 앱 보호 정책(MAM 정책이라고도 함)을 사용하도록 설정하려는 관리자 및 앱 개발자를 위한 설명서를 업데이트했습니다.

다음 문서가 업데이트되었습니다.

* [Microsoft Intune으로 모바일 응용 프로그램 관리용 앱을 준비하는 방법 결정](https://docs.microsoft.com/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune)
* [Intune 앱 래핑 도구를 사용하여 모바일 응용 프로그램 관리를 위해 iOS 앱 준비](https://docs.microsoft.com/intune/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)
* [Microsoft Intune 앱 SDK 시작](https://docs.microsoft.com/intune/develop/intune-app-sdk-get-started)
* [iOS용 Intune 앱 SDK 개발자 가이드](https://docs.microsoft.com/intune/develop/intune-app-sdk-ios)

다음 문서가 문서 라이브러리에 새로 추가되었습니다.

* [Intune 앱 SDK Cordova 플러그 인](https://docs.microsoft.com/intune/develop/intune-app-sdk-cordova)
* [Intune 앱 SDK Xamarin 구성 요소](https://docs.microsoft.com/intune/develop/intune-app-sdk-xamarin)

#### <a name="progress-bar-when-launching-the-company-portal-on-ios---665978--"></a>iOS에서 회사 포털을 시작할 경우의 진행률 표시줄 <!--665978-->
iOS용 회사 포털은 수행되는 로드 프로세스에 대한 정보를 사용자에게 제공하는 시작 화면의 진행률 표시줄을 도입하기로 했습니다. 진행률 표시줄이 단계적으로 회전자를 바꿀 예정입니다. 즉, 일부 사용자에게는 새로운 진행률 표시줄이 표시되지만 다른 사용자에게는 계속 회전자가 표시됩니다.

## <a name="december-2016"></a>2016년 12월

### <a name="public-preview-of-the-new-intune-admin-experience-on-azure---736542--"></a>Azure의 새 Intune 관리 환경에 대한 공개 미리 보기<!--736542-->
2017년 초에 Microsoft에서는 전체 관리 환경을 Azure로 마이그레이션합니다. 이를 통해 Graph API를 사용하여 확장 가능한 최신 서비스 플랫폼에서 핵심 EMS 워크플로에 대한 강력한 통합 관리를 지원합니다. 모든 Intune 테넌트에 대해 이 포털을 일반 공급하기 전에, 이번 달 후반부터 일부 테넌트에게 이 새로운 관리 환경의 미리 보기 제공을 개시할 것임을 알려 드립니다.

Azure Portal의 관리 환경에서는 이미 발표된 새 그룹화 및 대상 지정 기능을 사용합니다. 따라서 기존 테넌트가 새 그룹화 환경으로 마이그레이션될 때 사용자도 마이그레이션되어 테넌트에 새 관리 환경의 미리 보기가 표시됩니다. Azure Portal에서 Microsoft Intune용으로 제공되는 기능에 대한 자세한 내용을 [새로운 설명서](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune)에서 확인해 보시기 바랍니다.

__Azure Portal의 공개 미리 보기에 통신 지출 관리 통합__ <!--747605--> 이제 Azure Portal 내에서 타사 TEM(통신 지출 관리) 서비스와의 통합 미리 보기를 시작합니다. Intune을 사용하여 국내 및 로밍 데이터 사용량을 제한할 수 있습니다. 우선 [Saaswedo](http://www.saaswedo.com)와의 통합으로 시작합니다. 평가판 테넌트에 이 기능을 사용하려면 [Microsoft 지원에 문의](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune)하세요.

### <a name="new-capabilities"></a>새로운 기능

__모든 플랫폼에서 다단계 인증__ <!--747590--> 이제 선택한 사용자 그룹이 Azure 관리 포털에서 iOS, Android, Windows 8.1+ 또는 Windows Phone 8.1+ 장치를 등록할 때 Azure Active Directory의 Microsoft Intune 등록 응용 프로그램에서 MFA(Multi-Factor Authentication)를 구성하여 해당 사용자 그룹에 MFA를 적용할 수 있습니다.

__모바일 장치 등록을 제한하는 기능__ <!--747596--> Intune은 등록할 수 있는 모바일 장치 플랫폼을 제어하는 새로운 등록 제한을 추가합니다. Intune은 모바일 장치 플랫폼을 iOS, macOS, Android, Windows 및 Windows Mobile로 구분합니다.
* 모바일 장치 등록을 제한해도 PC 클라이언트 등록은 제한되지 않습니다.
* iOS에 한해, 개인 소유 장치의 등록을 차단하는 한 가지 추가 옵션이 있습니다.

Intune은 [이 문서](https://docs.microsoft.com/en-us/intune/deploy-use/manage-corporate-owned-devices)에 설명된 대로 IT 관리자가 회사 소유로 표시하기 위한 조치를 취하지 않은 한 모든 새 장치를 개인 소유 장치로 표시합니다.

### <a name="notices"></a>알림

__Azure Portal로 등록 시 Multi-Factor Authentication 이동__ <!--VSO 750545--> 이전에는 관리자가 Intune 콘솔 또는 Configuration Manager(2016년 10월 이전 릴리스) 콘솔로 이동하여 Intune 등록에 대한 MFA를 설정했습니다. 이 업데이트된 기능을 사용하면 이제 [Microsoft Azure Portal](https://manage.windowsazure.com)에 Intune 자격 증명으로 로그인하고 Azure AD를 통해 MFA 설정을 구성합니다. 이 기능에 대한 자세한 내용은 [여기](https://aka.ms/mfa_ad)를 참조하세요.

__이제 중국에서 Android용 회사 포털 앱 사용 가능__ <!--VSO 658093--> 중국에서 Android용 회사 포털 앱을 다운로드할 수 있도록 게시합니다. 중국에는 Google Play 스토어를 사용할 수 없으므로 Android 장치 사용자는 중국 앱 마켓플레이스에서 앱을 다운로드해야 합니다. Android용 회사 포털 앱은 다음 스토어에서 다운로드할 수 있습니다.
* [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
* [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
* [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
* [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)
* [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)

Android 용 회사 포털 앱은 Google Play 서비스를 사용하여 Microsoft Intune 서비스와 통신합니다. 중국에서는 Google Play 서비스가 아직 제공되지 않으므로 다음 작업을 수행하면 완료까지 최대 8시간 걸릴 수 있습니다. 

|Intune 관리 콘솔| Android용 Intune 회사 포털 앱 |Intune 회사 포털 웹 사이트|   
|---|---|---|
|전체 초기화| 원격 장치 제거| 장치(로컬 및 원격) 제거|
|선택적 초기화| 장치 다시 설정| 장치 재설정|
|신규 또는 업데이트된 앱 배포| 사용 가능한 LOB(기간 업무) 앱 설치| 장치 암호 재설정|
|원격 잠금|||
|암호 재설정|||

### <a name="deprecations"></a>지원 중단

__Firefox에서 더 이상 Silverlight를 지원하지 않음__ <!--VSO TBA--> Mozilla는 2017년 3월부터 [Firefox 브라우저](https://www.mozilla.org/firefox) 버전 52에서 Silverlight를 지원하지 않을 예정입니다. 따라서 51 이후의 Firefox 버전을 사용하여 기존 Intune 콘솔에 더 이상 로그인할 수 없게 됩니다. Internet Explorer 10/11 또는 [버전 52 이전의 Firefox](https://ftp.mozilla.org/pub/firefox/releases/)를 사용하여 관리 콘솔에 액세스하는 것이 좋습니다. Intune이 Azure Portal로 전환되면 Silverlight를 사용하지 않고도 다수의 [최신 브라우저](https://docs.microsoft.com/en-us/azure/azure-preview-portal-supported-browsers-devices)가 지원될 예정입니다.

__Exchange Online 모바일 사서함 정책 제거__ <!--770687-->&12;월부터 관리자는 더 이상 Intune 콘솔 내에서 Exchange Online(EAS) 모바일 사서함 정책을 보거나 구성할 수 없습니다. 12월과&1;월 동안에 이 변경 내용이 모든 Intune 테넌트로 롤아웃됩니다. 모든 기존 정책은 구성된 상태로 유지됩니다. 새 정책을 구성하려면 Exchange 관리 셸을 사용하세요. 자세한 내용은 [여기](https://technet.microsoft.com/en-us/library/bb123783%28v=exchg.150%29.aspx)를 참조하세요.

__Intune AV Player, 이미지 뷰어 및 PDF 뷰어 앱이 Android에서 더 이상 지원되지 않음__ <!--747553--> 2016년 12월 중순부터 사용자는 더 이상 Intune AV Player, 이미지 뷰어 및 PDF 뷰어 앱을 사용할 수 없습니다. 이러한 앱은 Azure Information Protection 앱으로 대체되었습니다. Azure Information Protection 앱에 대한 자세한 내용은 [여기](https://docs.microsoft.com/information-protection/rms-client/mobile-app-faq)를 참조하세요.

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

<!--Existing Intune customers can use this feature in production once their tenant has been migrated. Existing customers are welcome to create a trial Intune account to plan for and test this feature until their tenant has been migrated. -->

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

비준수 장치의 최종 사용자는 등록하라는 메시지가 표시되며 Android 장치에서 Lookout for Work 응용 프로그램을 설치하고, 앱을 활성화하고, Lookout for Work 응용 프로그램에 보고된 위협을 해결해야만 액세스 권한을 얻게 됩니다. 자세한 내용은 [Restrict access based on device, network, and application risk](https://docs.microsoft.com/en-us/intune/deploy-use/device-threat-protection)(장치, 네트워크 및 응용 프로그램 위험에 따라 액세스 제한)를 참조하세요.


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

__Android용 회사 포털에 '알림' 추가__&9;월에는 홈페이지에 새 **알림** 아이콘을 추가하는 업데이트를 Android용 회사 포털에 릴리스할 예정입니다. 이 아이콘을 누르면 호환되지 않는 장치, 등록 업데이트 및 등록 활성화와 같이 회사 포털 앱에서 주의가 필요한 모든 항목을 최종 사용자에게 표시하는 **알림** 페이지로 이동됩니다. IOS 회사 포털 앱을 사용하는 경우에는 이미 알림을 제공받았을 것입니다. **알림** 페이지가 도입되면서 장치가 등록된 동안 Android용 회사 포털을 시작하거나 다시 시작할 때마다 **회사 액세스 설정** 페이지가 항상 표시되지는 않습니다. 많은 고객 여러분이 최종 사용자 지침을 만드는 데 도움을 주신 점을 알고 있습니다. 지침/스크린샷을 업데이트해야 할 때 미리 알려 주시는 점에 감사드립니다. 예정된 변경 내용을 환경에 반영하려면 설명서를 업데이트하세요. 업데이트된 스크린샷을 보려면 https://aka.ms/androidcpupdate로 이동하세요.  

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
