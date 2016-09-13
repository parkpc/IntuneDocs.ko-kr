---
title: "Windows 10 정책 설정 | Microsoft Intune"
description: "이 항목에 나열된 정책 설정을 사용하면 등록된 Windows 10 Desktop 및 Windows 10 Mobile 장치의 기본 제공 및 사용자 지정 설정을 구성하는 데 도움이 됩니다."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 08/31/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00a602d9-b339-4fd8-ab70-defbf6686855
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 4ce69e8a22f1b25dac7060ff575bbd97934eff91
ms.openlocfilehash: 712883874f022ceb3f38473839fe0d6e4c373164


---

# Microsoft Intune의 Windows 10 장치용 Intune 정책 설정

이 항목에서는 Windows 10 장치 관리에 사용할 수 있는 Intune 정책 설정을 파악하는 데 도움이 되는 정보를 제공합니다. 등록된 Windows 10 Desktop 및 Windows 10 Mobile 장치의 기본 제공 설정과 사용자 지정 설정을 구성하려면 이 항목의 내용과 [Microsoft Intune 정책을 사용하여 장치의 설정 및 기능 관리](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies)에 나와 있는 절차를 함께 확인하세요. [Intune PC 클라이언트 소프트웨어](/intune/get-started/windows-pc-management-capabilities-in-microsoft-intune)를 실행 중인 PC에서는 이러한 정책을 사용할 수 없습니다.

다음의 두 가지 정책 유형 중에서 선택할 수 있습니다.

- **사용자 지정 정책** - 장치의 기능을 제어하는 데 사용할 수 있는 OMA-URI(Open Mobile Alliance Uniform Resource Identifier)를 배포하려면 Windows 10 및 Windows 10 Mobile용 Microsoft Intune **사용자 지정 정책**을 사용합니다. Windows 10에서는 [정책 CSP(구성 서비스 제공자)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers)를 통해 다양한 설정이 제공됩니다.
- **일반 구성 정책** - Microsoft Intune에서 제공되는 기본 제공 목록에서 설정을 선택하려면 이 정책 유형을 사용합니다.

## 사용자 지정 정책 설정

사용자 지정 정책에서는 다음 설정을 제공합니다.

## &nbsp;&nbsp;&nbsp;일반

Intune 콘솔에서 식별할 수 있도록 이 정책의 이름을 입력하고 필요한 경우 설명을 입력합니다.

## &nbsp;&nbsp;&nbsp;OMA URI 설정

추가하려는 각 OMA-URI 설정에 대해 다음 정보를 입력합니다. 사용할 수 있는 설정에 대해 알아보려면 이 항목의 [Windows 10 URI 설정 참조](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune#Windows-10-URI-settings)를 활용하세요. 

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

### 예제
아래 스크린샷에서는 **Conectivity/AllowVPNOverCellular** 설정이 사용하도록 설정되어 있습니다. 따라서 Windows 10 장치는 셀룰러 네트워크에서 VPN 연결을 열 수 있습니다.

> ![VPN 설정을 포함하는 사용자 지정 정책의 예](./media/custom-policy-example.png)

## Windows 10 URI 설정
이 섹션에서는 **Windows 10 사용자 지정 정책**을 사용하여 구성할 수 있는 OMA-URI 설정에 대해 설명합니다.

## &nbsp;&nbsp;&nbsp;정책

|정책 이름 및 URI|세부 정보|
|---------------|------------|-----------|
|**자동 업데이트 허용**<br>./Vendor/MSFT/Policy/Config/Update/AllowAutoUpdate|Desktop에만 해당<br>**데이터 형식:** 정수<br />**값:** **0** - **5**(기본값: **1**)|
|**설치 날짜 예약**<br>./Vendor/MSFT/Policy/Config/Update/ScheduledInstallDay|Mobile에만 해당<br>**데이터 형식:** 정수<br />**값은**<br>**0** - 매일(기본값)<br>**1** - 일요일<br>**2** - 월요일<br>**3** - 화요일<br>**4** - 수요일<br>**5** - 목요일<br>**6** - 금요일<br>**7** - 토요일|
|**설치 시간 예약**<br>./Vendor/MSFT/Policy/Config/Update/ScheduledInstallTime|Desktop 및 Mobile<br />**데이터 형식:** 정수<br />**값:** **0** – **23**시간(**0**: 자정)(기본값: **3**)|
|**DeviceLock/AllowIdleReturnWithoutPassword**<br>./Vendor/MSFT/Policy/Config/DeviceLock/AllowIdleReturnWithoutPassword|Mobile에만 해당<br />**데이터 형식:** 정수<br />**값은**<br>**0** -사용자가 암호 유예 기간 타이머를 설정할 수 없으며 값은 "항상"으로 설정됩니다.<br>**1** - 사용자가 암호 유예 기간 타이머를 설정할 수 있습니다(기본값).|
|**WiFi/AllowWiFi**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowWiFi|Mobile에만 해당<br />**데이터 형식:** 정수<br />**값은**<br>**0** – **Wi-Fi 연결 사용**을 허용하지 않습니다.<br>**1** - **Wi-Fi 연결 사용을 허용합니다**(기본값).|
|**WiFi/AllowInternetSharing**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowInternetSharing|Desktop 및 Mobile<br>**데이터 형식:** 정수<br />**값:** **0** – 인터넷 공유 허용 안 함, **1** – 인터넷 공유 허용(기본값)|
|**WiFi/AllowAutoConnectToWiFiSenseHotspots**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowAutoConnectToWiFiSenseHotspots|Desktop 및 Mobile<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**WiFi/AllowManualWiFiConfiguration**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowManualWiFiConfiguration|Mobile에만 해당<br />**데이터 형식:** 정수<br />**값은**<br>**0** – 프로비전된 MDM 외부의 Wi-Fi 연결이 허용되지 않습니다.<br>**1** – 이미 프로비전된 MDM을 초과하는 새 네트워크 SSID의 추가를 허용합니다(기본값).|
|**System/AllowLocation**<br>./Vendor/MSFT/Policy/Config/System/AllowLocation|Desktop 및 Mobile<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**System/AllowTelemetry**<br>./Vendor/MSFT/Policy/Config/System/AllowTelemetry|Desktop 및 Mobile<br>**데이터 형식:** 정수<br />**값은**<br>**0** – 허용되지 않음(기업 전용 설정)<br>**1** – 제한됨<br>**2** - 전체(기본값)<br>**3** - 전체 및 진단 정보|
|**System/AllowExperimentation**<br>./Vendor/MSFT/Policy/Config/System/AllowExperimentation|Desktop 및 Mobile<br />**데이터 형식:** 정수<br />**값은**<br>**0** – 허용되지 않음<br>**1** - 설정만(기본값)<br>**2** - 설정 및 실험|
|**Security/AntiTheftMode**<br>./Vendor/MSFT/Policy/Config/Security/AntiTheftMode|Mobile에만 해당<br />**데이터 형식:** 정수<br />**값은**<br>**0** - 도난 방지 모드를 허용하지 않음<br>**1** - 사용자 기본 설정(기본값)|
|**Connectivity/AllowUSBConnection**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowUSBConnection|Mobile에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**System/AllowUserToResetPhone**<br>./Vendor/MSFT/Policy/Config/System/AllowUserToResetPhone|Mobile에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**Connectivity/AllowCellularDataRoaming**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowCellularDataRoaming|Desktop 및 Mobile<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**Connectivity/AllowVPNOverCellular**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNOverCellular|Desktop 및 Mobile<br />**데이터 형식:** 정수<br />**값은**<br>**0** - 휴대폰을 통한 VPN이 허용되지 않음<br>**1** - VPN이 휴대폰을 포함한 모든 연결을 사용할 수 있음(기본값)|
|**Connectivity/AllowVPNRoamingOverCellular**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular|Mobile에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**Connectivity/AllowVPNRoamingOverCellular**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular|Mobile에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**Connectivity/AllowBluetooth**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowBluetooth|Desktop 및 Mobile<br />**데이터 형식:** 정수<br />**값은**<br>**0** – 사용자가 Bluetooth를 켜도록 허용하지 않습니다.<br>**1** – 예약됨. 사용자가 Bluetooth를 켜고 구성할 수 있습니다(Windows 10 Mobile 또는 MDM, EAS, Windows 10 Desktop용 Windows Phone 8.1에는 지원되지 않음).<br>**2** - 허용됨. 사용자가 Bluetooth를 켜고 구성할 수 있습니다(기본값).|
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
|**TextInput/AllowIMENetworkAccess**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowIMENetworkAccess|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값은**<br>**0** – 허용하지 않음<br>개방형 확장 사전이 꺼집니다.<br>사용자는 다음 작업을 수행할 수 없습니다.<br>-새 개방형 확장 사전 추가<br />-새 검색 통합 구성 파일 추가<br>-클라우드 후보 기능 사용<br>-사용자 등록 단어 보내기<br>**1** - 허용<br>개방형 확장 사전을 기본적으로 추가하고 사용할 수 있습니다. 또한 검색 통합 기능을 기본적으로 사용할 수 있습니다.<br>사용자는 다음 작업을 수행할 수 있습니다.<br>클라우드 후보 기능 사용|
|**TextInput/AllowIMELogging**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowIMELogging|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값은**<br>**0** - 변환 오류 로깅이 해제됩니다.<br>**1** - 변환 오류 로깅이 설정됩니다(기본값).|
|**TextInput/AllowJapaneseNonPublishingStandardGlyph**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseNonPublishingStandardGlyph|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**TextInput/AllowJapaneseIVSCharacters**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIVSCharacters|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**TextInput/AllowJapaneseUserDictionary**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseUserDictionary|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**TextInput/AllowJapaneseIMESurrogatePairCharacters**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIMESurrogatePairCharacters|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**TextInput/ExcludeJapaneseIMEExceptShiftJIS**<br>./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptShiftJIS|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값은**<br>**0** - 문자가 필터링되지 않음(기본값)<br>**1** - Shift JIS 문자를 제외한 모든 내용이 필터링됨|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208**<br>./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값은**<br />**0** - 문자가 필터링되지 않음(기본값)<br>**1** - JIS0208 문자를 제외한 모든 내용이 필터링됨|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC**<br>./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값은**<br>**0** - 문자가 필터링되지 않음(기본값)<br>**1** - JIS0208 문자 또는 EUDC 문자를 제외한 모든 내용이 필터링됨|
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
|**Search/SafeSearchPermissions**<br>./Vendor/MSFT/Policy/Config/Search/SafeSearchPermissions|Mobile에만 해당<br />**데이터 형식:** 정수<br />**값은**<br>**0** – 엄격, 성인용 콘텐츠에 대한 최고의 필터링<br>**1** – 보통, 성인용 콘텐츠에 대한 보통 필터링(유효한 검색 결과는 필터링되지 않음 - 기본값)|
|**Experience/AllowCopyPaste**<br>./Vendor/MSFT/Policy/Config/Experience/AllowCopyPaste|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**시작 크기 적용**<br>./Vendor/MSFT/Policy/Config/Start/ForceStartSize|Mobile에만 해당<br />**데이터 형식:** 정수<br />**값은**<br>**0** - 사용자가 크기 변경 가능(기본값)<br>**1** - 전체 화면이 아닌 화면 적용<br>**2** - 전체 화면 적용|
|**Update/RequireDeferUpgrade**<br>./Vendor/MSFT/Policy/Config/Update/RequireDeferUpgrade|Desktop 및 Mobile<br />**데이터 형식:** 정수<br />**값은**<br>**0**: 업그레이드를 연기하지 않음(CB(Current Branch) 유지 - 기본값)<br>**1**: 업데이트 및 업그레이드 연기 허용(장치가 CBB(Current Branch for Business) 규칙을 따름)<br />자세한 내용은 다음 항목을 참조하세요.<br>[Windows 10 서비스 소개](https://technet.microsoft.com/library/mt598226.aspx)<br>[Windows 10 배포에 대한 계획](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpdatePeriod**<br>./Vendor/MSFT/Policy/Config/Update/DeferUpdatePeriod|Desktop 및 Mobile<br>**설명:** 최대 4주 동안 소프트웨어 업데이트를 연기하는 정책<br />**데이터 형식:** 정수<br />**값은**<br> **0**: 즉시 업데이트 적용(기본값)<br>**1**-**4**: 소프트웨어 업데이트를 연기할 주 수<br />자세한 내용은 다음 항목을 참조하세요.<br>[Windows 10 서비스 소개](https://technet.microsoft.com/library/mt598226.aspx)<br>[Windows 10 배포에 대한 계획](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpgradePeriod**<br>./Vendor/MSFT/Policy/Config/Update/DeferUpgradePeriod|Desktop 및 Mobile<br>**설명:** 최대 8개월 동안 기능 업그레이드를 연기하는 정책<br />**데이터 형식:** 정수<br />**값은**<br>**0**: 즉시 업데이트 적용(기본값)<br>**1**-**8**: 기능 업그레이드를 연기할 개월 수<br />자세한 내용은 다음 항목을 참조하세요.<br>[Windows 10 서비스 소개](https://technet.microsoft.com/library/mt598226.aspx)<br>[Windows 10 배포에 대한 계획](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/PauseDeferrals**<br>./Vendor/MSFT/Policy/Config/Update/PauseDeferrals|Desktop 및 Mobile<br>**설명:** 장치에서 5주 동안 업데이트 및 업그레이드 수신을 중지하도록 허용합니다.<br />**데이터 형식:** 정수<br />**값은**<br>**0**: 즉시 업데이트 적용(기본값)<br>**1**: 업데이트 및 업그레이드 일시 중지(5주 후에 만료)|

## &nbsp;&nbsp;&nbsp;Windows Defender

|정책 이름 및 URI|세부 정보|
|---------------|-----------|
|**AllowRealtimeMonitoring**<br>./Vendor/MSFT/Policy/Config/Defender/AllowRealtimeMonitoring|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**AllowBehaviorMonitoring**<br>./Vendor/MSFT/Policy/Config/Defender/AllowBehaviorMonitoring|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**AllowIntrusionPreventionSystem**<br>./Vendor/MSFT/Policy/Config/Defender/AllowIntrusionPreventionSystem|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**AllowIOAVProtection**<br>./Vendor/MSFT/Policy/Config/Defender/AllowIOAVProtection|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**AllowScriptScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowScriptScanning|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**AllowOnAccessProtection**<br>./Vendor/MSFT/Policy/Config/Defender/AllowOnAccessProtection|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**RealTimeScanDirection**<br>./Vendor/MSFT/Policy/Config/Defender/RealTimeScanDirection|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값은**<br>**0** – 모든 파일 모니터링(기본값)<br>**1** – 들어오는 파일 모니터링<br>**2** – 나가는 파일 모니터링|
|**DaysToRetainCleanedMalware**<br>./Vendor/MSFT/Policy/Config/Defender/DaysToRetainCleanedMalware|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값은**<br>**0** - **90** – 맬웨어가 유지되는 길이를 나타냄<br>**기본값:** **0** – 격리 폴더를 영구적으로 유지하고 자동으로 제거하지 않음|
|**AllowUserUIAccess**<br>./Vendor/MSFT/Policy/Config/Defender/AllowUserUIAccess|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**ScanParameter**<br>./Vendor/MSFT/Policy/Config/Defender/ScanParameter|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값은**<br>**1** - 빠른 검색(기본값)<br>**2** - 전체 검색|
|**ScheduleScanDay**<br>./Vendor/MSFT/Policy/Config/Defender/ScheduleScanDay|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값은**<br>**0** - 매일(기본값)<br>**1** - 월요일<br>**2** - 화요일<br>**3** - 수요일<br>**4** - 목요일<br>**5** - 금요일<br>**6** - 토요일<br>**7** - 일요일<br>**8** – 예약된 검색 없음|
|**ScheduleScanTime**<br>./Vendor/MSFT/Policy/Config/Defender/ScheduleScanTime|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값은**<br>**0** - 12:00 am<br>**60** ~ 1:00 am<br>**120** – 2:00 am(기본값)<br>**180** ~ 3:00 am<br>**240** ~ 4:00 am<br>**300** ~ 5:00 am<br>**360** ~ 6:00 am<br>**420** ~ 7:00 am<br>**480** ~ 8:00 am<br>**540** ~ 9:00 am<br>**600** ~ 10:00 am<br>**660** ~ 11:00 am<br>**720** ~ 12:00 pm<br>**780** ~ 1:00 pm<br>**840** ~ 2:00 pm<br>**900** ~ 3:00 pm<br>**960** ~ 4:00 pm<br>**1020** ~ 5:00 pm<br>**1080** ~ 6:00 pm<br>**1140** ~ 7:00 pm<br>**1200** ~ 8:00 pm<br>**1260** ~ 9:00 pm<br>**1320** ~ 10:00 pm<br>**1381** – 유지 관리 기간|
|**ScheduleQuickScanTime**<br>./Vendor/MSFT/Policy/Config/Defender/ScheduleQuickScanTime|Desktop에만 해당<br>**데이터 형식:** 정수<br />**값은**<br>**0** - 12:00 am<br>**60** ~ 1:00 am<br>**120** – 2:00 am(기본값)<br>**180** ~ 3:00 am<br>**240** ~ 4:00 am<br>**300** ~ 5:00 am<br>**360** ~ 6:00 am<br>**420** ~ 7:00 am<br>**480** ~ 8:00 am<br>**540** ~ 9:00 am<br>**600** ~ 10:00 am<br>**660** ~ 11:00 am<br>**720** ~ 12:00 pm<br>**780** ~ 1:00 pm<br>**840** ~ 2:00 pm<br>**900** ~ 3:00 pm<br>**960** ~ 4:00 pm<br>**1020** ~ 5:00 pm<br>**1080** ~ 6:00 pm<br>**1140** ~ 7:00 pm<br>**1200** ~ 8:00 pm<br>**1260** ~ 9:00 pm<br>**1320** ~ 10:00 pm<br>**1380** ~ 11:00 pm|
|**AVGCPULoadFactor**<br>./Vendor/MSFT/Policy/Config/Defender/AVGCPULoadFactor|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** - **100**(기본값: **50**)|
|**AllowArchiveScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowArchiveScanning|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**AllowEmailScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowEmailScanning|Desktop에만 해당<br />**데이터 형식:** 정수<br>**값:** **0** – 허용되지 않음(기본값), **1** – 허용됨|
|**AllowFullScanRemovableDriveScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowFullScanRemovableDriveScanning|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음(기본값), **1** – 허용됨|
|**AllowFullScanOnMappedNetworkDrives**<br>./Vendor/MSFT/Policy/Config/Defender/AllowFullScanOnMappedNetworkDrives|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**AllowScanningNetworkFiles**<br>./Vendor/MSFT/Policy/Config/Defender/AllowScanningNetworkFiles|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값) - 허용됨으로 설정하는 경우 RTP가 켜져 있을 때도 실행됨|
|**SignatureUpdateInterval**<br>./Vendor/MSFT/Policy/Config/Defender/SignatureUpdateInterval|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값은**<br>**0** – 일정 간격으로 서명을 확인하지 않음<br>**1** - 매 시간마다 서명 검사<br>**2** – 일정 간격(예: 2시간 등)으로 서명 확인<br>**24** – 매일 서명 확인<br>**기본값:** 8 – 8시간마다 확인|
|**AllowCloudProtection**<br>./Vendor/MSFT/Policy/Config/Defender/AllowCloudProtection|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 허용되지 않음, **1** – 허용됨(기본값)|
|**SubmitSamplesConsent**<br>./Vendor/MSFT/Policy/Config/Defender/SubmitSamplesConsent|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값은**<br>**0** – 항상 메시지 표시(기본값)<br>**1** – 자동으로 안전 샘플 보내기<br>**2** – 보내지 않음<br>**3** – 자동으로 모든 샘플 보내기|
|**ExcludedExtensions**<br>./Vendor/MSFT/Policy/Config/Defender/ExcludedExtensions|Desktop에만 해당<br />**데이터 형식:** 문자열<br />**값은**<br>*&lt;세미콜론으로 구분된 확장자 목록&gt;* 예: **obj;lib**<br>**기본값:** 제외되는 확장 없음|
|**ExcludedPaths**<br>./Vendor/MSFT/Policy/Config/Defender/ExcludedPaths|Desktop에만 해당<br />**데이터 형식:** 문자열<br />**값은**<br />*&lt;세미콜론으로 구분된 경로 목록&gt;*<br />예: **c:\test;c:\test1.exe**<br />**기본값:** 제외되는 경로 없음|
|**ExcludedProcesses**<br>./Vendor/MSFT/Policy/Config/Defender/ExcludedProcesses|Desktop에만 해당<br />**데이터 형식:** 문자열<br />**값은**<br>*&lt;세미콜론으로 구분된 경로 목록&gt;*<br>예: **c:\test.exe;c:\test1.exe**<br>**기본값:** 제외되는 프로세스 없음|

## &nbsp;&nbsp;&nbsp;Edge 브라우저

|정책 이름 및 URI|세부 정보|
|---------------|------------|-----------|
|**브라우저 허용**<br>./Vendor/MSFT/Policy/Config/Browser/AllowBrowser|Mobile에만 해당<br />**데이터 형식:** 정수<br />**값:** **0**: 찾아보기 해제, **1**: 찾아보기 설정(기본값)|
|**AllowSearchSuggestionsinAddressBar**<br>./Vendor/MSFT/Policy/Config/Browser/AllowSearchSuggestionsinAddressBar|Desktop 및 Mobile<br />**데이터 형식:** 정수<br />**값:** **0**: 제안 사항 표시 안 함, **1**: 제안 사항 표시(기본값)|
|**SendIntranetTraffictoInternetExplorer**<br>./Vendor/MSFT/Policy/Config/Browser/SendIntranetTraffictoInternetExplorer|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값은**<br>**0**: 사용 안 함(Edge 브라우저에서 인트라넷 사이트 열기 - 기본값)<br>**1** - 사용(Internet Explorer에서 인트라넷 사이트 열기)|
|**Do Not Track 허용**<br>./Vendor/MSFT/Policy/Config/Browser/AllowDoNotTrack|Desktop 및 Mobile<br />**데이터 형식:** 정수<br />**값:** **0** – 사용 안 함(DNT를 보내지 않음 - 기본값), **1** – 사용(DNT를 보냄)|
|**SmartScreen 구성**<br>./Vendor/MSFT/Policy/Config/Browser/AllowSmartScreen|Desktop 및 Mobile<br />**데이터 형식:** 정수<br />**값:** **0** – 허용하지 않음, **1** – 허용(기본값)|
|**팝업 허용**<br>./Vendor/MSFT/Policy/Config/Browser/AllowPopups|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 팝업 차단(기본값), **1** – 팝업 허용|
|**쿠키 허용**<br>./Vendor/MSFT/Policy/Config/Browser/AllowCookies|Desktop 및 Mobile<br />**데이터 형식:** 정수<br />**값은**<br>**0** - 모든 웹 사이트의 쿠키 허용(기본값)<br>**1** – 타사 쿠키만 차단<br>**2** – 모든 쿠키 차단|
|**암호 저장 허용**<br>./Vendor/MSFT/Policy/Config/Browser/AllowPasswordManager|Desktop 및 Mobile<br />**데이터 형식:** 정수<br />**값은**<br>**0** – 암호 관리자 사용 안 함 <br>**1** – 암호 관리자 사용(기본값)|
|**자동 채우기 허용**<br>./Vendor/MSFT/Policy/Config/Browser/AllowAutofill|Desktop에만 해당<br />**데이터 형식:** 정수<br />**값:** **0** – 사용 안 함(기본값), **1** – 사용|
|**엔터프라이즈 사이트 목록 구성**<br>./Vendor/MSFT/Policy/Config/Browser/EnterpriseModeSiteList|Desktop에만 해당<br />**데이터 형식:** 문자열<br />**값:<br>**0** – 구성되지 않음<br>**1** – 구성되어 있는 경우 IE의 엔터프라이즈 모드 사이트 목록 사용(기본값)<br>**2** – 엔터프라이즈 사이트 목록의 위치 지정|

## 일반 구성 정책 설정

Windows 10용 Microsoft Intune **일반 구성 정책**을 사용하여 등록된 Windows 10 Desktop 및 Windows 10 Mobile 장치에 대한 기본 제공 설정을 구성합니다. 

## &nbsp;&nbsp;&nbsp;암호

|설정 이름|추가 정보(필요 시)|
|----------------|----------------------|
|**장치의 잠금을 해제하는 데 암호 필요**|-|
|**필수 암호 유형**|암호를 숫자로만 입력해야 하는지 아니면 영숫자로 입력할지 여부를 지정합니다.|
|**필수 암호 유형** - **최소 문자 집합 개수**|소문자, 대문자, 숫자, 기호에 해당하는 4가지 문자 집합을 사용할 수 있습니다. 이 설정은 암호에 포함되어야 하는 문자 집합 수를 지정합니다.|
|**최소 암호 길이**|Windows 10 Mobile에만 적용됩니다.|
|**장치를 초기화하기 전까지 허용되는 로그인 반복 오류 횟수**|Windows 10을 실행 중인 장치: 장치에서 BitLocker를 사용하도록 설정된 경우 지정한 횟수만큼 로그인이 실패하면 장치가 BitLocker 복구 모드로 설정됩니다. 장치에서 BitLocker를 사용하지 않도록 설정된 경우에는 이 설정이 적용되지 않습니다.<br>Windows 10 Mobile을 실행 중인 장치: 지정한 횟수만큼 로그인이 실패하면 장치가 초기화됩니다.|
|**화면이 잠기기 전까지 비활성 시간(분)**|화면이 잠기기 전에 장치가 유휴 상태여야 하는 기간을 지정합니다.|
|**암호 만료(일)**|장치 암호를 변경해야 하는 간격을 지정합니다.|
|**암호 기록 기억**|최종 사용자가 이전에 사용했던 암호를 만들지 못하도록 제한할지 여부를 지정합니다.|
|**암호 기록 기억** - **이전 암호 다시 사용 안 함**|장치에서 기억하도록 할 이전에 사용한 암호의 수를 지정합니다.|
|**장치가 유휴 상태에서 되돌아오는 경우 암호 필요**|사용하는 경우 사용자가 암호를 입력해야 장치 잠금을 해제할 수 있습니다. (Windows 10 Mobile에만 해당)|

## &nbsp;&nbsp;&nbsp;암호화

|설정 이름|추가 정보(필요 시)|
|----------------|----------------------|
|**모바일 장치 암호화 필요**|대상 장치에서 암호화를 사용합니다.<br>(Windows 10 Mobile에만 해당)|

## &nbsp;&nbsp;&nbsp;System (시스템)

|설정 이름|추가 정보(필요 시)|
|----------------|----------------------|
|**화면 캡처 허용**|장치 화면을 이미지로 캡처하도록 허용합니다. (Windows 10 Mobile에만 해당)|
|**수동 등록 취소 허용**|장치에서 회사 계정을 수동으로 삭제할 수 있습니다.|
|**루트 인증서 수동 설치 허용**|Windows 10 Mobile에 적용됩니다.|
|**진단 및 사용 현황 데이터를 Microsoft에 보내도록 허용**|가능한 값은 다음과 같습니다.<br><br>**없음** - Microsoft로 데이터가 전송되는 데이터가 없습니다.<br>**기본** - 제한된 정보가 Microsoft로 전송됩니다.<br>**고급** - 고급 진단 데이터가 Microsoft로 전송됩니다.<br>**전체(권장됨)** - **확장됨**과 동일한 데이터 외에, 장치 상태에 대한 추가적인 데이터를 전송합니다.|


## &nbsp;&nbsp;&nbsp;계정 및 동기화

|설정 이름|추가 정보(필요 시)|
|----------------|----------------------|---------------------|
|**Microsoft 계정 허용**|사용자가 Microsoft 계정을 장치와 연결하도록 허용합니다.|
|**Microsoft가 아닌 타사 계정 수동 추가 허용**|사용자가 Microsoft 계정과 연결되지 않은 장치에 전자 메일 계정을 추가하도록 허용합니다.|
|**Microsoft 계정에 대한 설정 동기화 허용**|Microsoft 계정과 연결된 장치 및 앱 설정이 장치 간이 동기화되도록 허용합니다.|

## &nbsp;&nbsp;&nbsp;Microsoft Edge

|설정 이름|추가 정보(필요 시)|
|----------------|----------------------|
|**웹 브라우저 허용**|장치에서 Edge 웹 브라우저 사용을 허용합니다.<br>(Windows 10 Mobile에만 해당)|
|**주소 표시줄에서 검색 제안 허용**|검색 구를 입력할 때 검색 엔진이 사이트를 제안하도록 허용합니다.|
|**인트라넷 트래픽을 Internet Explorer에 전송 허용**|사용자가 Internet Explorer에서 인트라넷 웹 사이트를 열도록 허용합니다.<br>(Windows 10 Desktop에만 해당)|
|**Do Not Track 허용**|사용자가 방문하는 웹 사이트에 Do Not Track 헤더를 보내도록 Edge 브라우저를 구성합니다|
|**SmartScreen 사용**|-|
|**액티브 스크립팅 허용**|Edge 브라우저에서 JavaScript 같은 스크립트가 실행되도록 허용합니다.|
|**팝업 허용**|Windows 10 Desktop에만 적용됩니다.|
|**쿠키 허용**|-|
|**자동 채우기 허용**|사용자가 브라우저에서 자동 완성 설정을 변경하도록 허용합니다.<br>(Windows 10 Desktop에만 해당)|
|**암호 관리자 허용**|Edge 암호 관리자 기능을 사용하거나 사용하지 않습니다.|
|**엔터프라이즈 모드 사이트 목록 위치**|엔터프라이즈 모드에서 열 웹 사이트 목록을 찾을 위치를 지정합니다. 사용자는 이 목록을 편집할 수 없습니다.<br>(Windows 10 Desktop에만 해당)|

## &nbsp;&nbsp;&nbsp;앱

|설정 이름|추가 정보(필요 시)|
|----------------|----------------------|---------------------|
|**앱 스토어 허용**|Windows 10 Mobile에만 적용됩니다.|



## &nbsp;&nbsp;&nbsp;셀룰러

|설정 이름|추가 정보(필요 시)|
|----------------|----------------------|---------------------|
|**데이터 로밍 허용**|데이터 액세스 시 네트워크 간 로밍이 가능합니다.|
|**셀룰러에서 VPN 허용**|셀룰러 네트워크에 연결 시 장치가 VPN 연결에 액세스할 수 있을지 여부를 제어합니다.|
|**셀룰러에서 VPN 로밍 허용**|셀룰러 네트워크에 로밍 시 장치가 VPN 연결에 액세스할 수 있을지 여부를 제어합니다.|

## &nbsp;&nbsp;&nbsp;하드웨어

|설정 이름|추가 정보(필요 시)|
|----------------|----------------------|
|**카메라 허용**|-|
|**이동식 저장소 허용**|장치에 SD 카드와 같은 외부 저장 장치 사용 여부를 지정합니다.|
|**Wi-Fi 허용**|Windows 10 Mobile에만 적용됩니다.|
|**인터넷 공유 허용**|장치에서 인터넷 연결 공유를 사용하도록 허용합니다.|
|**Wi-Fi 수동 구성 허용**|사용자가 스스로 Wi-Fi 연결을 구성할 수 있을지 또는 Wi-Fi 프로필에 의해 구성되는 연결만 사용할 수 있을지를 제어합니다.<br>(Windows 10 Mobile에만 해당)|
|**무료 Wi-Fi 핫스팟에 자동 연결 허용**|장치가 무료 Wi-Fi 핫스폿에 자동으로 연결되고 연결에 대한 사용 약관을 자동으로 수락하도록 허용합니다.|
|**지리적 위치 허용**|장치에서 위치 서비스 정보를 사용할 수 있는지 여부를 지정합니다.|
|**NFC 허용**|장치가 NFC(근거리 통신) 기능을 사용하도록 허용합니다.|
|**Bluetooth 허용**|-|
|**Bluetooth 검색 가능 모드 허용**|Bluetooth를 사용하는 다른 장치에서 이 장치를 검색하도록 허용합니다.|
|**Bluetooth 광고 허용**|장치에서 Bluetooth를 통해 광고를 수신할 수 있도록 허용합니다.|
|**휴대폰 초기화 허용**|사용자가 장치를 출하 시로 초기화할 수 있는지 여부를 제어합니다.|
|**USB 연결 허용**|장치의 USB 연결을 통한 외부 저장 장치 액세스 가능 여부를 제어합니다.|
|**AntiTheft 모드 허용**|Windows Antitheft 모드 사용 여부를 구성합니다.|

## &nbsp;&nbsp;&nbsp;기능

|설정 이름|추가 정보(필요 시)|
|----------------|----------------------|---------------------|
|**복사 및 붙여넣기 허용**|Windows 10 Mobile에만 적용됩니다.|
|**음성 녹음 허용**|Windows 10 Mobile에만 적용됩니다.|
|**Cortana 허용**|Cortana 음성 지원을 허용하거나 허용하지 않습니다.|
|**알림 센터 알림 허용**|장치 잠금 화면에서 알림 센터 알림을 허용하거나 허용하지 않습니다.<br>(Windows 10 Mobile에만 해당)|

## &nbsp;&nbsp;&nbsp;Windows Defender

모든 설정이 Windows 10 Desktop에만 해당됩니다.

|설정 이름|추가 정보(필요 시)|
|-|-|
|**실시간 모니터링 허용**|맬웨어, 스파이웨어 및 기타 사용자 동의 없이 설치되는 소프트웨어에 대한 실시간 모니터링을 허용합니다.|
|**동작 모니터링 허용**|Defender가 장치에서 특정한 알려진 패턴의 의심스러운 활동을 확인하도록 허용합니다.|
|**네트워크 검사 시스템 사용**|NIS(네트워크 검사 시스템)는 Microsoft Endpoint Protection Center의 알려진 취약한 부분에 대한 서명을 사용하여 네트워크 기반의 익스플로잇으로부터 장치를 보호하고 악의적인 트래픽을 차단하는 데 도움을 줍니다.|
|**모든 다운로드 검색**|Defender가 인터넷에서 다운로드한 모든 파일을 검사할지 여부를 제어합니다.|
|**스크립트 검색 허용**|Defender가 Internet Explorer에 사용되는 스크립트를 검색하도록 허용합니다.|
|**파일 및 프로그램 활동 모니터링**|Defender가 장치의 파일 및 프로그램 활동을 모니터링하도록 허용하려면 이 설정을 사용합니다.|
|**해결된 맬웨어를 추적하는 일 수**|이전에 영향을 받은 장치를 수동으로 확인할 수 있도록 Defender가 지정한 일 수 동안 해결된 맬웨어를 추적하도록 허용합니다. 일 수를 **0**으로 설정하면, 맬웨어가 격리 폴더에 유지되며 자동으로 제거되지 않습니다. |
|**클라이언트 UI 액세스 허용**|Windows Defender 사용자 인터페이스를 최종 사용자에게 숨길지 여부를 제어합니다.<br>이 설정이 변경되면, 다음 번 최종 사용자 PC를 다시 시작할 때 적용됩니다.|
|**매일 빠른 검색 예약**|매일 발생하는 빠른 검색을 사용자가 선택한 시간으로 예약하도록 허용합니다.|
|**시스템 검색 예약**|정기적으로 발생하는 전체 또는 빠른 시스템 검색을 사용자가 선택한 날짜와 시간으로 예약하도록 허용합니다.|
|**검색하는 동안 CPU 사용 제한**|검색에 사용하도록 허용하는 CPU 양을 제한하도록 허용합니다(**1**에서 **100**까지).|
|**보관 파일 검색**|Defender가 Zip 또는 Cab 파일로 보관된 파일을 검색하도록 허용합니다.|
|**전자 메일 메시지 검색**|Defender가 전자 메일 메시지가 장치에 도착하면 검색하도록 허용합니다.|
|**이동식 드라이브 검색**|Defender가 USB 스틱 같은 이동식 드라이브를 검색하도록 허용합니다.|
|**매핑된 네트워크 드라이브 검색**|Defender가 매핑된 네트워크 드라이브의 파일을 검색하도록 허용합니다.<br>드라이브의 파일이 읽기 전용이면, Defender가 그 안에서 발견한 맬웨어를 제거할 수 없습니다.|
|**네트워크 공유 폴더의 열린 파일 검색**|Defender가 공유 네트워크 드라이브의 파일을(예: UNC 경로를 통해 액세스하는) 검색하도록 허용합니다.<br>드라이브의 파일이 읽기 전용이면, Defender가 그 안에서 발견한 맬웨어를 제거할 수 없습니다.|
|**서명 업데이트 간격**|Defender가 새로운 서명 파일을 확인하는 간격을 지정합니다.|
|**클라우드 보호 허용**|사용자가 관리하는 장치의 맬웨어 활동에 대한 정보를 Microsoft Active Protection Service가 수신하도록 허용하거나 차단합니다. 이 정보는 향후 서비스를 개선하는 데 사용됩니다.|
|**사용자에게 샘플 제출 확인**|파일이 악성 파일인지 판단하기 위해 Microsoft의 자세한 분석이 필요할 수 있는 파일을 Microsoft에 자동으로 보낼지를 제어합니다.|
|**사용자 동의 없이 설치된 응용 프로그램 검색**|이 설정을 사용하여 Windows Defender에서 사용자 동의 없이 설치된 소프트웨어로 분류된 프로그램에 대해 등록된 Windows 데스크톱 장치를 보호할 수 있습니다. 실행 중인 이러한 응용 프로그램으로부터 보호하거나 감사 모드를 사용하여 사용자 동의 없이 응용 프로그램이 설치될 때 보고할 수 있습니다.|
|**검색을 실행하거나 실시간 보호를 사용할 때 제외할 파일 및 폴더**|제외 목록에 **C:\Path** 또는 **%ProgramFiles%\Path\filename.exe** 같은 파일과 폴더를 하나 이상 추가합니다. 이러한 파일과 폴더는 실시간 또는 예약된 검색에 포함되지 않습니다.|
|**검색을 실행하거나 실시간 보호를 사용할 때 제외할 파일 확장명**|제외 목록에 **jpg** 또는 **txt** 같은 파일과 확장명을 하나 이상 추가합니다. 이러한 확장명의 파일은 실시간 또는 예약된 검색에 포함되지 않습니다.|
|**검색을 실행하거나 실시간 보호를 사용할 때 제외할 프로세스**|제외 목록에 **.exe**, **.com**, 또는 **.scr** 같은 유형의 프로세스를 하나 이상 추가합니다. 이러한 프로세스는 실시간 또는 예약된 검색에 포함되지 않습니다.| 


## &nbsp;&nbsp;&nbsp;Updates

|설정 이름|추가 정보(필요 시)|
|----------------|---------------|
|**자동 업데이트 허용**|자동 업데이트를 허용하려면 이 설정을 사용합니다. 그런 후에 다음 설정 중 하나를 구성하여 업데이트 동작을 제어합니다.<br />**다운로드 알림**<br />**유지 관리 시 자동 설치**<br />**유지 관리 시 자동 설치 및 다시 부팅**<br />**예약 시간에 자동 설치 및 다시 부팅** **참고:** 이 옵션을 선택하면 다음 설정을 구성할 수 있습니다. **최종 사용자에게 알림 표시 안 함** 및 **예약된 업데이트의 설치 날짜 지정**<br>(Windows 10 Desktop에만 해당)|
|**시험판 기능 허용**|Microsoft에서 Windows 10 장치에 시험판 설정 및 기능을 배포할 수 있습니다. 설정만 설치하거나, 모든 시험판 설정 및 기능을 설치할 수 있도록 선택할 수 있습니다.|

### 참고 항목
[Microsoft Intune 정책을 사용하여 장치의 설정 및 기능 관리](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)





<!--HONumber=Aug16_HO5-->


