---
title: "Windows 10 장치에 대한 Intune 사용자 지정 설정 | Intune Azure 미리 보기 | Microsoft Docs"
description: "Intune Azure 미리 보기: Windows 10 사용자 지정 프로필에서 사용할 수 있는 설정을 알아봅니다."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7bcea136-7260-4042-b21b-c7dab86b380d
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0da8c0fe399f76f43439cc66eaecd12bb454f9a6
ms.openlocfilehash: 05856480f8bb76e561f2b459d4ab800f9909a40a


---

# <a name="custom-device-settings-for-windows-10-devices-in-intune-azure-preview"></a>Intune Azure 미리 보기의 Windows 10 장치에 대한 사용자 지정 장치 설정

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

 장치의 기능을 제어하는 데 사용할 수 있는 OMA-URI(Open Mobile Alliance Uniform Resource Identifier)를 배포하려면 Windows 10 및 Windows 10 Mobile용 Microsoft Intune **사용자 지정** 프로필을 사용합니다. Windows 10에서는 [정책 CSP(구성 서비스 제공자)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers)를 통해 다양한 설정이 제공됩니다.

1. [Microsoft Intune에서 사용자 지정 장치 설정을 구성하는 방법](how-to-configure-custom-settings.md)의 지침을 사용하여 시작합니다.
2. **프로필 만들기** 블레이드에서 **설정**을 선택하여 하나 이상의 OMA-URI 설정을 추가합니다.
3. **사용자 지정 OMA-URI 설정** 블레이드에서 **추가**를 클릭하여 새 값을 추가합니다. **내보내기**를 클릭하여 쉼표로 구분된 값(.csv) 파일로 구성한 모든 값의 목록을 만들 수도 있습니다.
4. 추가하려는 각 OMA-URI 설정에 대해 다음 정보를 입력합니다. 사용할 수 있는 설정에 대해 알아보려면 이 항목의 목록을 사용하세요.
    - **설정 이름** - 설정 목록에서 쉽게 식별할 수 있도록 OMA-URI 설정에 대한 고유한 이름을 입력합니다.
    - **설정 설명** -필요에 따라 설정에 대한 설명을 입력합니다.
    - **데이터 형식** - 다음 중에서 선택합니다.
        - **문자열**
        - **문자열(XML)**
        - **날짜 및 시간**
        - **정수**
        - **부동 소수점**
        - **부울**
    - **OMA-URI(대/소문자 구분)** - 설정을 제공할 OMA-URI를 지정합니다.
    - **값** - 입력한 OMA-URI와 연결할 값을 지정합니다.
5. 완료되면 **프로필 만들기** 블레이드로 돌아가서 **만들기**를 누릅니다.
프로필이 만들어지고 프로필 목록 블레이드에 표시됩니다.

## <a name="example"></a>예
아래 스크린샷에서는 **Connectivity/AllowVPNOverCellular** 설정을 사용하도록 설정되어 있습니다. 따라서 Windows 10 장치는 셀룰러 네트워크에서 VPN 연결을 열 수 있습니다.

> ![VPN 설정을 포함하는 사용자 지정 정책의 예](./media/custom-policy-example.png)


## <a name="policy-settings"></a>정책 설정

|정책 이름 및 URI|세부 정보|
|---------------|------------|-----------|
|**자동 업데이트 허용**<br>./Vendor/MSFT/Policy/Config/Update/AllowAutoUpdate|Desktop에만 해당<br>**데이터 형식:** 정수<br />**값:** **0** - **5**(기본값: **1**)|
|**설치 날짜 예약**<br>./Vendor/MSFT/Policy/Config/Update/ScheduledInstallDay|Mobile에만 해당<br>**데이터 형식:** 정수<br />**값:**<br>**0** - 매일(기본값)<br>**1** - 일요일<br>**2** - 월요일<br>**3** - 화요일<br>**4** - 수요일<br>**5** - 목요일<br>**6** - 금요일<br>**7** - 토요일|
|**설치 시간 예약**<br>./Vendor/MSFT/Policy/Config/Update/ScheduledInstallTime|Desktop 및 Mobile<br />**데이터 형식:** 정수<br />**값:** **0** – **23**시간(**0**: 자정)(기본값: **3**)|
|**DeviceLock/AllowIdleReturnWithoutPassword**<br>./Vendor/MSFT/Policy/Config/DeviceLock/AllowIdleReturnWithoutPassword|Mobile에만 해당<br />**데이터 형식:** 정수<br />**값:**<br>**0** -사용자가 암호 유예 기간 타이머를 설정할 수 없으며 값은 "항상"으로 설정됩니다.<br>**1** - 사용자가 암호 유예 기간 타이머를 설정할 수 있습니다(기본값).|
|**WiFi/AllowWiFi**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowWiFi|Mobile에만 해당<br />**데이터 형식:** 정수<br />**값:**<br>**0** – **Wi-Fi 연결 사용**을 허용하지 않습니다.<br>**1** - **Wi-Fi 연결 사용을 허용합니다**(기본값).|
|**WiFi/AllowInternetSharing**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowInternetSharing|Desktop 및 Mobile<br>**데이터 형식:** 정수<br />**값:** **0** – 인터넷 공유 허용 안 함, **1** – 인터넷 공유 허용(기본값)|
|**WiFi/AllowAutoConnectToWiFiSenseHotspots**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowAutoConnectToWiFiSenseHotspots|Desktop 및 Mobile<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**WiFi/AllowManualWiFiConfiguration**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowManualWiFiConfiguration|Mobile에만 해당<br />**데이터 형식:** 정수<br />**값:**<br>**0** – 프로비전된 MDM 외부의 Wi-Fi 연결이 허용되지 않습니다.<br>**1** – 이미 프로비전된 MDM을 초과하는 새 네트워크 SSID의 추가를 허용합니다(기본값).|
|**System/AllowLocation**<br>./Vendor/MSFT/Policy/Config/System/AllowLocation|Desktop 및 Mobile<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**System/AllowTelemetry**<br>./Vendor/MSFT/Policy/Config/System/AllowTelemetry|Desktop 및 Mobile<br>**데이터 형식:** 정수<br />**값:**<br>**0** – 허용되지 않음(기업 전용 설정)<br>**1** – 제한됨<br>**2** - 전체(기본값)<br>**3** - 전체 및 진단 정보|
|**System/AllowExperimentation**<br>./Vendor/MSFT/Policy/Config/System/AllowExperimentation|Desktop 및 Mobile<br />**데이터 형식:** 정수<br />**값:**<br>**0** – 허용되지 않음<br>**1** - 설정만(기본값)<br>**2** - 설정 및 실험|
|**Security/AntiTheftMode**<br>./Vendor/MSFT/Policy/Config/Security/AntiTheftMode|Mobile에만 해당<br />**데이터 형식:** 정수<br />**값:**<br>**0** - 도난 방지 모드를 허용하지 않음<br>**1** - 사용자 기본 설정(기본값)|
|**Connectivity/AllowUSBConnection**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowUSBConnection|Mobile에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**System/AllowUserToResetPhone**<br>./Vendor/MSFT/Policy/Config/System/AllowUserToResetPhone|Mobile에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**Connectivity/AllowCellularDataRoaming**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowCellularDataRoaming|Desktop 및 Mobile<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**Connectivity/AllowVPNOverCellular**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNOverCellular|Desktop 및 Mobile<br />**데이터 형식:** 정수<br />**값:**<br>**0** - 휴대폰을 통한 VPN이 허용되지 않음<br>**1** - VPN이 휴대폰을 포함한 모든 연결을 사용할 수 있음(기본값)|
|**Connectivity/AllowVPNRoamingOverCellular**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular|Mobile에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**Connectivity/AllowVPNRoamingOverCellular**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular|Mobile에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**Connectivity/AllowBluetooth**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowBluetooth|Desktop 및 Mobile<br />**데이터 형식:** 정수<br />**값:**<br>**0** – 사용자가 Bluetooth를 켜도록 허용하지 않습니다.<br>**1** – 예약됨. 사용자가 Bluetooth를 켜고 구성할 수 있습니다(Windows 10 Mobile 또는 MDM, EAS, Windows 10 Desktop용 Windows Phone 8.1에는 지원되지 않음).<br>**2** - 허용됨. 사용자가 Bluetooth를 켜고 구성할 수 있습니다(기본값).|
|**Experience/AllowScreenCapture**<br>./Vendor/MSFT/Policy/Config/Experience/AllowScreenCapture|Mobile에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**Experience/AllowTaskSwitcher**<br>./Vendor/MSFT/Policy/Config/Experience/AllowTaskSwitcher|Mobile에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**Experience/AllowVoiceRecording**<br>./Vendor/MSFT/Policy/Config/Experience/AllowVoiceRecording|Mobile에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**Experience/AllowSyncMySettings**<br>./Vendor/MSFT/Policy/Config/Experience/AllowSyncMySettings|Mobile에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 로밍 허용 안 함, **1** – 로밍 허용(기본값)|
|**Experience/AllowManualMDMUnenrollment**<br>./Vendor/MSFT/Policy/Config/Experience/AllowManualMDMUnenrollment|Desktop 및 Mobile<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**Accounts/AllowMicrosoftAccountConnection**<br>./Vendor/MSFT/Policy/Config/Accounts/AllowMicrosoftAccountConnection|Desktop 및 Mobile<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**Accounts/AllowAddingNonMicrosoftAccountsManually**<br>./Vendor/MSFT/Policy/Config/Accounts/AllowAddingNonMicrosoftAccountsManually|Desktop 및 Mobile<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**Security/AllowManualRootCertificateInstallation**<br>./Vendor/MSFT/Policy/Config/Security/AllowManualRootCertificateInstallation|Mobile에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**Security/AllowAddProvisioningPackages**<br>./Vendor/MSFT/Policy/Config/Security/AllowAddProvisioningPackages|Desktop 및 Mobile<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**Search/DisableBackoff**<br>./Vendor/MSFT/Policy/Config/Search/DisableBackoff|Desktop 및 Mobile<br />**데이터 형식:** 정수<br />**값:** **0**(기본값), **1**|
|**Search/PreventRemoteQueries**<br>./Vendor/MSFT/Policy/Config/Search/PreventRemoteQueries|Desktop 및 Mobile<br />**데이터 형식:** 정수<br />**값:** **0**, **1**(기본값)|
|**Search/AllowUsingDiacritics**<br>./Vendor/MSFT/Policy/Config/Search/AllowUsingDiacritics|Desktop 및 Mobile<br />**데이터 형식:** 정수<br />**값:** **0**(기본값), **1**|
|**Search/AlwaysUseAutoLangDetection**<br>./Vendor/MSFT/Policy/Config/Search/AlwaysUseAutoLangDetection|Desktop 및 Mobile<br />**데이터 형식:** 정수<br />**값:** **0**(기본값), **1**|
|**Search/DisableRemovableDriveIndexing**<br>./Vendor/MSFT/Policy/Config/Search/DisableRemovableDriveIndexing|Desktop 및 Mobile<br />**데이터 형식:** 정수<br />**값:** **0**(기본값), **1**|
|**Search/PreventIndexingLowDiskSpaceMB**<br>./Vendor/MSFT/Policy/Config/Search/PreventIndexingLowDiskSpaceMB|Desktop 및 Mobile<br />**데이터 형식:** 정수<br />**값:** **0**, **1**(기본값)|
|**Search/AllowIndexingEncryptedStoresOrItems**<br>./Vendor/MSFT/Policy/Config/Search/AllowIndexingEncryptedStoresOrItems|Desktop 및 Mobile<br />**데이터 형식:** 정수<br />**값:** **0**(기본값), **1**|
|**Security/AllowRemoveProvisioningPackage**<br>./Vendor/MSFT/Policy/Config/Security/AllowRemoveProvisioningPackage|Desktop 및 Mobile<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**Security/RequireProvisioningPackageSignature**<br>./Vendor/MSFT/Policy/Config/Security/RequireProvisioningPackageSignature|Desktop 및 Mobile<br />**데이터 형식:** 정수<br />**값:** **0**(기본값), **1**|
|**AboveLock/AllowActionCenterNotifications**<br>./Vendor/MSFT/Policy/Config/AboveLock/AllowActionCenterNotifications|Desktop 및 Mobile<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**TextInput/AllowIMENetworkAccess**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowIMENetworkAccess|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:**<br>**0** – 허용하지 않음<br>개방형 확장 사전이 꺼집니다.<br>사용자는 다음 작업을 수행할 수 없습니다.<br>-새 개방형 확장 사전 추가<br />-새 검색 통합 구성 파일 추가<br>-클라우드 후보 기능 사용<br>-사용자 등록 단어 보내기<br>**1** - 허용<br>개방형 확장 사전을 기본적으로 추가하고 사용할 수 있습니다. 또한 검색 통합 기능을 기본적으로 사용할 수 있습니다.<br>사용자는 다음 작업을 수행할 수 있습니다.<br>클라우드 후보 기능 사용|
|**TextInput/AllowIMELogging**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowIMELogging|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:**<br>**0** - 변환 오류 로깅이 해제됩니다.<br>**1** - 변환 오류 로깅이 설정됩니다(기본값).|
|**TextInput/AllowJapaneseNonPublishingStandardGlyph**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseNonPublishingStandardGlyph|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**TextInput/AllowJapaneseIVSCharacters**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIVSCharacters|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**TextInput/AllowJapaneseUserDictionary**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseUserDictionary|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**TextInput/AllowJapaneseIMESurrogatePairCharacters**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIMESurrogatePairCharacters|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**TextInput/ExcludeJapaneseIMEExceptShiftJIS**<br>./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptShiftJIS|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:**<br>**0** - 문자가 필터링되지 않음(기본값)<br>**1** - Shift JIS 문자를 제외한 모든 내용이 필터링됨|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208**<br>./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:**<br />**0** - 문자가 필터링되지 않음(기본값)<br>**1** - JIS0208 문자를 제외한 모든 내용이 필터링됨|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC**<br>./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:**<br>**0** - 문자가 필터링되지 않음(기본값)<br>**1** - JIS0208 문자 또는 EUDC 문자를 제외한 모든 내용이 필터링됨|
|**TextInput/AllowInputPanel**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowInputPanel|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**Bluetooth/AllowDiscoverableMode**<br>./Vendor/MSFT/Policy/Config/Bluetooth/AllowDiscoverableMode|Desktop 및 Mobile<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**Bluetooth/AllowAdvertising**<br>./Vendor/MSFT/Policy/Config/Bluetooth/AllowAdvertising|Desktop 및 Mobile<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**Settings/AllowDataSense**<br>./Vendor/MSFT/Policy/Config/Settings/AllowDataSense|Desktop 및 Mobile<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**Settings/AllowVPN**<br>./Vendor/MSFT/Policy/Config/Settings/AllowVPN|Desktop 및 Mobile<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**Settings/AllowWorkplace**<br>./Vendor/MSFT/Policy/Config/Settings/AllowWorkplace|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**Settings/AllowDateTime**<br>./Vendor/MSFT/Policy/Config/Settings/AllowDateTime|Desktop 및 Mobile<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**Settings/AllowLanguage**<br>./Vendor/MSFT/Policy/Config/Settings/AllowLanguage|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**Settings/AllowRegion**<br>./Vendor/MSFT/Policy/Config/Settings/AllowRegion|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**Settings/AllowSignInOptions**<br>./Vendor/MSFT/Policy/Config/Settings/AllowSignInOptions|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**Settings/AllowYourAccount**<br>./Vendor/MSFT/Policy/Config/Settings/AllowYourAccount|Desktop 및 Mobile<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**Settings/AllowPowerSleep**<br>./Vendor/MSFT/Policy/Config/Settings/AllowPowerSleep|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**Settings/AllowAutoPlay**<br>./Vendor/MSFT/Policy/Config/Settings/AllowAutoPlay|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**Experience/AllowCortana**<br>./Vendor/MSFT/Policy/Config/Experience/AllowCortana|Desktop 및 Mobile<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**Search/SafeSearchPermissions**<br>./Vendor/MSFT/Policy/Config/Search/SafeSearchPermissions|Mobile에만 해당<br />**데이터 형식:** 정수<br />**값:**<br>**0** – 엄격, 성인용 콘텐츠에 대한 최고의 필터링<br>**1** – 보통, 성인용 콘텐츠에 대한 보통 필터링(유효한 검색 결과는 필터링되지 않음 - 기본값)|
|**Experience/AllowCopyPaste**<br>./Vendor/MSFT/Policy/Config/Experience/AllowCopyPaste|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**시작 크기 적용**<br>./Vendor/MSFT/Policy/Config/Start/ForceStartSize|Mobile에만 해당<br />**데이터 형식:** 정수<br />**값:**<br>**0** - 사용자가 크기 변경 가능(기본값)<br>**1** - 전체 화면이 아닌 화면 적용<br>**2** - 전체 화면 적용|
|**Update/RequireDeferUpgrade**<br>./Vendor/MSFT/Policy/Config/Update/RequireDeferUpgrade|Desktop 및 Mobile<br />**데이터 형식:** 정수<br />**값:**<br>**0**: 업그레이드를 연기하지 않음(CB(Current Branch) 유지 - 기본값)<br>**1**: 업데이트 및 업그레이드 연기 허용(장치가 CBB(Current Branch for Business) 규칙을 따름)<br />자세한 내용은 다음을 참조하세요.<br>[Windows 10 서비스 소개](https://technet.microsoft.com/library/mt598226.aspx)<br>[Windows 10 배포에 대한 계획](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpdatePeriod**<br>./Vendor/MSFT/Policy/Config/Update/DeferUpdatePeriod|Desktop 및 Mobile<br>**설명:** 최대 4주 동안 소프트웨어 업데이트를 연기하는 정책<br />**데이터 형식:** 정수<br />**값:**<br> **0**: 즉시 업데이트 적용(기본값)<br>**1**-**4**: 소프트웨어 업데이트를 연기할 주 수<br />자세한 내용은 다음을 참조하세요.<br>[Windows 10 서비스 소개](https://technet.microsoft.com/library/mt598226.aspx)<br>[Windows 10 배포에 대한 계획](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpgradePeriod**<br>./Vendor/MSFT/Policy/Config/Update/DeferUpgradePeriod|Desktop 및 Mobile<br>**설명:** 최대 8개월 동안 기능 업그레이드를 연기하는 정책<br />**데이터 형식:** 정수<br />**값:**<br>**0**: 즉시 업데이트 적용(기본값)<br>**1**-**8**: 기능 업그레이드를 연기할 개월 수<br />자세한 내용은 다음을 참조하세요.<br>[Windows 10 서비스 소개](https://technet.microsoft.com/library/mt598226.aspx)<br>[Windows 10 배포에 대한 계획](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/PauseDeferrals**<br>./Vendor/MSFT/Policy/Config/Update/PauseDeferrals|Desktop 및 Mobile<br>**설명:** 장치에서 5주 동안 업데이트 및 업그레이드 수신을 중지하도록 허용합니다.<br />**데이터 형식:** 정수<br />**값:**<br>**0**: 즉시 업데이트 적용(기본값)<br>**1**: 업데이트 및 업그레이드 일시 중지(5주 후에 만료)|

## <a name="windows-defender-settings"></a>Windows Defender 설정

|정책 이름 및 URI|세부 정보|
|---------------|-----------|
|**AllowRealtimeMonitoring**<br>./Vendor/MSFT/Policy/Config/Defender/AllowRealtimeMonitoring|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**AllowBehaviorMonitoring**<br>./Vendor/MSFT/Policy/Config/Defender/AllowBehaviorMonitoring|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**AllowIntrusionPreventionSystem**<br>./Vendor/MSFT/Policy/Config/Defender/AllowIntrusionPreventionSystem|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**AllowIOAVProtection**<br>./Vendor/MSFT/Policy/Config/Defender/AllowIOAVProtection|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**AllowScriptScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowScriptScanning|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**AllowOnAccessProtection**<br>./Vendor/MSFT/Policy/Config/Defender/AllowOnAccessProtection|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**RealTimeScanDirection**<br>./Vendor/MSFT/Policy/Config/Defender/RealTimeScanDirection|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:**<br>**0** – 모든 파일 모니터링(기본값)<br>**1** – 들어오는 파일 모니터링<br>**2** – 나가는 파일 모니터링|
|**DaysToRetainCleanedMalware**<br>./Vendor/MSFT/Policy/Config/Defender/DaysToRetainCleanedMalware|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:**<br>**0** - **90** – 맬웨어가 유지되는 길이를 나타냄<br>**기본값:** **0** – 격리 폴더를 영구적으로 유지하고 자동으로 제거하지 않음|
|**AllowUserUIAccess**<br>./Vendor/MSFT/Policy/Config/Defender/AllowUserUIAccess|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**ScanParameter**<br>./Vendor/MSFT/Policy/Config/Defender/ScanParameter|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:**<br>**1** - 빠른 검색(기본값)<br>**2** - 전체 검색|
|**ScheduleScanDay**<br>./Vendor/MSFT/Policy/Config/Defender/ScheduleScanDay|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:**<br>**0** - 매일(기본값)<br>**1** - 월요일<br>**2** - 화요일<br>**3** - 수요일<br>**4** - 목요일<br>**5** - 금요일<br>**6** - 토요일<br>**7** - 일요일<br>**8** – 예약된 검색 없음|
|**ScheduleScanTime**<br>./Vendor/MSFT/Policy/Config/Defender/ScheduleScanTime|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:**<br>**0** - 12:00 am<br>**60** ~ 1:00 am<br>**120** – 2:00 am(기본값)<br>**180** ~ 3:00 am<br>**240** ~ 4:00 am<br>**300** ~ 5:00 am<br>**360** ~ 6:00 am<br>**420** ~ 7:00 am<br>**480** ~ 8:00 am<br>**540** ~ 9:00 am<br>**600** ~ 10:00 am<br>**660** ~ 11:00 am<br>**720** ~ 12:00 pm<br>**780** ~ 1:00 pm<br>**840** ~ 2:00 pm<br>**900** ~ 3:00 pm<br>**960** ~ 4:00 pm<br>**1020** ~ 5:00 pm<br>**1080** ~ 6:00 pm<br>**1140** ~ 7:00 pm<br>**1200** ~ 8:00 pm<br>**1260** ~ 9:00 pm<br>**1320** ~ 10:00 pm<br>**1381** – 유지 관리 기간|
|**ScheduleQuickScanTime**<br>./Vendor/MSFT/Policy/Config/Defender/ScheduleQuickScanTime|Desktop에만 해당<br>**데이터 형식:** 정수<br />**값:**<br>**0** - 12:00 am<br>**60** ~ 1:00 am<br>**120** – 2:00 am(기본값)<br>**180** ~ 3:00 am<br>**240** ~ 4:00 am<br>**300** ~ 5:00 am<br>**360** ~ 6:00 am<br>**420** ~ 7:00 am<br>**480** ~ 8:00 am<br>**540** ~ 9:00 am<br>**600** ~ 10:00 am<br>**660** ~ 11:00 am<br>**720** ~ 12:00 pm<br>**780** ~ 1:00 pm<br>**840** ~ 2:00 pm<br>**900** ~ 3:00 pm<br>**960** ~ 4:00 pm<br>**1020** ~ 5:00 pm<br>**1080** ~ 6:00 pm<br>**1140** ~ 7:00 pm<br>**1200** ~ 8:00 pm<br>**1260** ~ 9:00 pm<br>**1320** ~ 10:00 pm<br>**1380** ~ 11:00 pm|
|**AVGCPULoadFactor**<br>./Vendor/MSFT/Policy/Config/Defender/AVGCPULoadFactor|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** - **100**(기본값: **50**)|
|**AllowArchiveScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowArchiveScanning|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**AllowEmailScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowEmailScanning|Desktop에만 해당<br />**데이터 형식:** 정수<br>**값:** **0** – 허용되지 않음(기본값), **1** – 허용됨|
|**AllowFullScanRemovableDriveScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowFullScanRemovableDriveScanning|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음(기본값), **1** – 허용됨|
|**AllowFullScanOnMappedNetworkDrives**<br>./Vendor/MSFT/Policy/Config/Defender/AllowFullScanOnMappedNetworkDrives|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**AllowScanningNetworkFiles**<br>./Vendor/MSFT/Policy/Config/Defender/AllowScanningNetworkFiles|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값) - 허용됨으로 설정하는 경우 RTP가 켜져 있을 때도 실행됨|
|**SignatureUpdateInterval**<br>./Vendor/MSFT/Policy/Config/Defender/SignatureUpdateInterval|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:**<br>**0** – 일정 간격으로 서명을 확인하지 않음<br>**1** - 매 시간마다 서명 검사<br>**2** – 일정 간격(예: 2시간 등)으로 서명 확인<br>**24** – 매일 서명 확인<br>**기본값:** 8 – 8시간마다 확인|
|**AllowCloudProtection**<br>./Vendor/MSFT/Policy/Config/Defender/AllowCloudProtection|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**SubmitSamplesConsent**<br>./Vendor/MSFT/Policy/Config/Defender/SubmitSamplesConsent|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:**<br>**0** – 항상 메시지 표시(기본값)<br>**1** – 자동으로 안전 샘플 보내기<br>**2** – 보내지 않음<br>**3** – 자동으로 모든 샘플 보내기|
|**ExcludedExtensions**<br>./Vendor/MSFT/Policy/Config/Defender/ExcludedExtensions|Desktop에만 해당<br />**데이터 형식:** 문자열<br />**값:**<br>*&lt;세미콜론으로 구분된 확장자 목록&gt;* 예: **obj;lib**<br>**기본값:** 제외되는 확장 없음|
|**ExcludedPaths**<br>./Vendor/MSFT/Policy/Config/Defender/ExcludedPaths|Desktop에만 해당<br />**데이터 형식:** 문자열<br />**값:**<br />*&lt;세미콜론으로 구분된 경로 목록&gt;*<br />예: **c:\test;c:\test1.exe**<br />**기본값:** 제외되는 경로 없음|
|**ExcludedProcesses**<br>./Vendor/MSFT/Policy/Config/Defender/ExcludedProcesses|Desktop에만 해당<br />**데이터 형식:** 문자열<br />**값:**<br>*&lt;세미콜론으로 구분된 경로 목록&gt;*<br>예: **c:\test.exe;c:\test1.exe**<br>**기본값:** 제외되는 프로세스 없음|

## <a name="edge-browser-settings"></a>Edge 브라우저 설정

|정책 이름 및 URI|세부 정보|
|---------------|------------|-----------|
|**브라우저 허용**<br>./Vendor/MSFT/Policy/Config/Browser/AllowBrowser|Mobile에만 해당<br />**데이터 형식:** 정수<br />**값:** **0**: 찾아보기 해제, **1**: 찾아보기 설정(기본값)|
|**AllowSearchSuggestionsinAddressBar**<br>./Vendor/MSFT/Policy/Config/Browser/AllowSearchSuggestionsinAddressBar|Desktop 및 Mobile<br />**데이터 형식:** 정수<br />**값:** **0**: 제안 사항 표시 안 함, **1**: 제안 사항 표시(기본값)|
|**SendIntranetTraffictoInternetExplorer**<br>./Vendor/MSFT/Policy/Config/Browser/SendIntranetTraffictoInternetExplorer|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:**<br>**0**: 사용 안 함(Edge 브라우저에서 인트라넷 사이트 열기 - 기본값)<br>**1** - 사용(Internet Explorer에서 인트라넷 사이트 열기)|
|**Do Not Track 허용**<br>./Vendor/MSFT/Policy/Config/Browser/AllowDoNotTrack|Desktop 및 Mobile<br />**데이터 형식:** 정수<br />**값:** **0** – 사용 안 함(DNT를 보내지 않음 - 기본값), **1** – 사용(DNT를 보냄)|
|**SmartScreen 구성**<br>./Vendor/MSFT/Policy/Config/Browser/AllowSmartScreen|Desktop 및 Mobile<br />**데이터 형식:** 정수<br />**값:** **0** – 허용하지 않음, **1** – 허용(기본값)|
|**팝업 허용**<br>./Vendor/MSFT/Policy/Config/Browser/AllowPopups|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 팝업 차단(기본값), **1** – 팝업 허용|
|**쿠키 허용**<br>./Vendor/MSFT/Policy/Config/Browser/AllowCookies|Desktop 및 Mobile<br />**데이터 형식:** 정수<br />**값:**<br>**0** - 모든 웹 사이트의 쿠키 허용(기본값)<br>**1** – 타사 쿠키만 차단<br>**2** – 모든 쿠키 차단|
|**암호 저장 허용**<br>./Vendor/MSFT/Policy/Config/Browser/AllowPasswordManager|Desktop 및 Mobile<br />**데이터 형식:** 정수<br />**값:**<br>**0** – 암호 관리자 사용 안 함 <br>**1** – 암호 관리자 사용(기본값)|
|**자동 채우기 허용**<br>./Vendor/MSFT/Policy/Config/Browser/AllowAutofill|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 사용 안 함(기본값), **1** – 사용|
|**엔터프라이즈 사이트 목록 구성**<br>./Vendor/MSFT/Policy/Config/Browser/EnterpriseModeSiteList|Desktop에만 해당<br />**데이터 형식:** 문자열<br />**값:<br>**0** – 구성되지 않음<br>**1** – 구성되어 있는 경우 IE의 엔터프라이즈 모드 사이트 목록 사용(기본값)<br>**2** – 엔터프라이즈 사이트 목록의 위치 지정|



<!--HONumber=Feb17_HO1-->


