---
title: "미리 공유한 키를 사용하여 Wi-Fi 프로필 만들기 | Intune Azure 미리 보기 | Microsoft Docs"
description: "Intune Azure 미리 보기: Intune 사용자 지정 프로필을 사용하여 미리 공유한 키로 Wi-Fi 프로필을 만듭니다."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c6fd72a6-7dc8-48fc-9df1-db5627a51597
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: 009fa0f9ab097d57389f96d2d86a88b0811fef4e
ms.lasthandoff: 02/16/2017



---
# <a name="use-a-microsoft-intune-custom-device-profile-to-create-a-wi-fi-profile-with-a-pre-shared-key"></a>Microsoft Intune 사용자 지정 장치 프로필을 사용하여 미리 공유한 키로 Wi-Fi 프로필 만들기
[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Intune의 **사용자 지정 장치 프로필**을 사용하여 미리 공유한 키로 Wi-Fi 프로필을 만드는 방법은 다음과 같습니다. 이 항목에서는 EAP 기반 Wi-Fi 프로필을 만드는 방법에 대한 예도 포함합니다.

> [!NOTE]
-    아래 설명된 대로 네트워크에 연결하는 컴퓨터에서 코드를 복사하면 작업을 좀 더 쉽게 수행할 수 있습니다.
- Android의 경우 Johnathon Biersack이 제공하는 이 [Android PSK 생성기](http://johnathonb.com/2015/05/intune-android-pre-shared-key-generator/)를 사용하는 옵션도 포함합니다.
-    더 많은 OMA-URI 설정을 추가하여 여러 네트워크와 키를 추가할 수 있습니다.
-  iOS의 경우 Mac 스테이션의 Apple Configurator를 사용하여 프로필을 설정합니다. 또는 Johnathon Biersack이 제공하는 이 [iOS PSK Mobile Config Generator](http://johnathonb.com/2015/05/intune-ios-psk-mobile-config-generator/)를 사용합니다.


1.    Android 또는 Windows용으로 미리 공유한 키를 사용하여 Wi-Fi 프로필을 만들거나 EAP 기반 Wi-Fi 프로필을 만들려면 장치 프로필을 만들 때 해당 장치 플랫폼에 대해 Wi-Fi 프로필 대신 **사용자 지정**을 선택합니다.

2.    이름 및 설명을 제공합니다.
3.    새 OMA-URI 설정을 추가합니다.

   a.    이 Wi-Fi 네트워크 설정에 대한 이름을 입력합니다.

   b.    OMA-URI 설정에 대한 설명을 입력하거나 비워 둡니다.

   c.    **데이터 형식**: **문자열**로 설정합니다.

   d.    **OMA URI**

    - **Android용**: ./Vendor/MSFT/WiFi/Profile/<SSID>/Settings
    - **Windows용**: ./Vendor/MSFT/WiFi/Profile/MyNetwork/WlanXml

    > [!NOTE]
시작 부분에 점 문자를 포함해야 합니다.

    SSID는 정책을 만들고 있는 SSID입니다. `./Vendor/MSFT/WiFi/Profile/Hotspot-1/Settings`).

  e. **값 필드**에 XML 코드를 붙여넣습니다. 아래 예를 살펴보세요. 각 값을 네트워크 설정에 맞게 조정해야 합니다. 일부 포인터에 대해서는 코드의 주석 섹션을 참조하세요.
4. **확인**을 선택하고 정책을 저장한 다음 할당합니다.

    > [!NOTE]
    > 이 정책은 사용자 그룹에만 배포할 수 있습니다.

다음에 각 장치가 체크인되면 정책이 적용되고 해당 장치에 Wi-Fi 프로필이 만들어집니다. 장치를 네트워크에 자동으로 연결할 수 있게 됩니다.

## <a name="android-or-windows-wi-fi-profile"></a>Android 또는 Windows Wi-Fi 프로필

Android 또는 Windows Wi-Fi 프로필의 XML 코드 예제는 다음과 같습니다.

> [!IMPORTANT]
>
> `<protected>false</protected>`는 **false**로 설정해야 합니다. **true**로 설정하면 장치가 암호화된 암호를 요구한 다음 암호를 해독하려 할 수 있습니다. 이로 인해 연결에 실패할 수 있습니다.
>
>  `<hex>53534944</hex>`는 `<name><SSID of wifi profile></name>`의&16;진수 값으로 설정해야 합니다.
>  Windows 10 장치는 잘못된 *0x87D1FDE8 재구성 실패* 오류를 반환할 수 있지만, 계속 프로필로 프로비전됩니다.

```
<!--
<Name of wifi profile> = Name of profile
<SSID of wifi profile> = Plain text of SSID. Does not need to be escaped, could be <name>Your Company's Network</name>
<nonBroadcast><true/false></nonBroadcast>
<Type of authentication> = Type of authentication used by the network, such as WPA2PSK.
<Type of encryption> = Type of encryption used by the network
<protected>false</protected> do not change this value, as true could cause device to expect an encrypted password and then try to decrypt it, which may result in a failed connection.
<password> = Password to connect to the network
x>53534944</hex> should be set to the hexadecimal value of <name><SSID of wifi profile></name>
-->
<WLANProfile
xmlns="http://www.microsoft.com/networking/WLAN/profile/v1">
  <name><Name of wifi profile></name>
  <SSIDConfig>
    <SSID>
      <hex>53534944</hex>
 <name><SSID of wifi profile></name>
    </SSID>
    <nonBroadcast>false</nonBroadcast>
  </SSIDConfig>
  <connectionType>ESS</connectionType>
  <connectionMode>auto</connectionMode>
  <autoSwitch>false</autoSwitch>
  <MSM>
    <security>
      <authEncryption>
        <authentication><Type of authentication></authentication>
        <encryption><Type of encryption></encryption>
        <useOneX>false</useOneX>
      </authEncryption>
      <sharedKey>
        <keyType>networkKey</keyType>
        <protected>false</protected>
        <keyMaterial>MyPassword</keyMaterial>
      </sharedKey>
      <keyIndex>0</keyIndex>
    </security>
  </MSM>
</WLANProfile>
```

## <a name="eap-based-wi-fi-profile"></a>EAP 기반 Wi-Fi 프로필
EAP 기반 Wi-Fi 프로필에 대한 XML 코드 예제는 다음과 같습니다.

```
    <WLANProfile xmlns="http://www.microsoft.com/networking/WLAN/profile/v1">
      <name>testcert</name>
      <SSIDConfig>
        <SSID>
          <hex>7465737463657274</hex>
          <name>testcert</name>
        </SSID>
        <nonBroadcast>true</nonBroadcast>
      </SSIDConfig>
      <connectionType>ESS</connectionType>
      <connectionMode>auto</connectionMode>
      <autoSwitch>false</autoSwitch>
      <MSM>
        <security>
          <authEncryption>
            <authentication>WPA2</authentication>
            <encryption>AES</encryption>
            <useOneX>true</useOneX>
            <FIPSMode     xmlns="http://www.microsoft.com/networking/WLAN/profile/v2">false</FIPSMode>
          </authEncryption>
          <PMKCacheMode>disabled</PMKCacheMode>
          <OneX xmlns="http://www.microsoft.com/networking/OneX/v1">
            <cacheUserData>false</cacheUserData>
            <authMode>user</authMode>
            <EAPConfig>
              <EapHostConfig     xmlns="http://www.microsoft.com/provisioning/EapHostConfig">
                <EapMethod>
                  <Type xmlns="http://www.microsoft.com/provisioning/EapCommon">13</Type>
                  <VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorId>
                  <VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorType>
                  <AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</AuthorId>
                </EapMethod>
                <Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig">
                  <Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1">
                    <Type>13</Type>
                    <EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1">
                      <CredentialsSource>
                        <CertificateStore>
                          <SimpleCertSelection>true</SimpleCertSelection>
                        </CertificateStore>
                      </CredentialsSource>
                      <ServerValidation>
                        <DisableUserPromptForServerValidation>false</DisableUserPromptForServerValidation>
                        <ServerNames></ServerNames>
                      </ServerValidation>
                      <DifferentUsername>false</DifferentUsername>
                      <PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">false</PerformServerValidation>
                      <AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">false</AcceptServerName>
                      <TLSExtensions xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">
                        <FilteringInfo xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV3">
                          <AllPurposeEnabled>true</AllPurposeEnabled>
                          <CAHashList Enabled="true">
                            <IssuerHash>75 f5 06 9c a4 12 0e 9b db bc a1 d9 9d d0 f0 75 fa 3b b8 78 </IssuerHash>
                          </CAHashList>
                          <EKUMapping>
                            <EKUMap>
                              <EKUName>Client Authentication</EKUName>
                              <EKUOID>1.3.6.1.5.5.7.3.2</EKUOID>
                            </EKUMap>
                          </EKUMapping>
                          <ClientAuthEKUList Enabled="true"/>
                          <AnyPurposeEKUList Enabled="false">
                            <EKUMapInList>
                              <EKUName>Client Authentication</EKUName>
                            </EKUMapInList>
                          </AnyPurposeEKUList>
                        </FilteringInfo>
                      </TLSExtensions>
                    </EapType>
                  </Eap>
                </Config>
              </EapHostConfig>
            </EAPConfig>
          </OneX>
        </security>
      </MSM>
    </WLANProfile>
```

## <a name="create-the-xml-file-from-an-existing-wi-fi-connection"></a>기존 Wi-Fi 연결에서 XML 파일 만들기
기존 Wi-Fi 연결에서 XML 파일을 만들 수도 있습니다.
1. 무선 네트워크에 연결되어 있거나 최근에 연결된 컴퓨터에서 C:\ProgramData\Microsoft\Wlansvc\Profiles\Interfaces\{guid} 폴더를 엽니다.

    각 프로필을 검색하여 적합한 프로필을 찾아야 하므로 여러 무선 네트워크에 연결되지 않은 컴퓨터를 사용하는 것이 가장 좋습니다.
3.     XML 파일을 검색하여 올바른 이름의 항목을 찾습니다.
4.     올바른 XML 파일을 찾았으면 XML 코드를 복사하여 OMA-URI 설정 페이지의 데이터 필드에 붙여넣습니다.

