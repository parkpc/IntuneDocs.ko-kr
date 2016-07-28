---
title: "PSK를 사용한 Wi-Fi | Microsoft Intune"
description: "사용자 지정 구성을 사용하여 미리 공유한 키로 Wi-Fi 프로필을 만듭니다."
keywords: 
author: nbigman
manager: Arob98
ms.date: 07/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e977c7c7-e204-47a6-b851-7ad7673ceaab
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 72288296d966b9b9fae4fd721b4460528213f626
ms.openlocfilehash: afdd0c3569c0c294a9bef47755de2d9e77e7507d



---
# 미리 공유한 키를 사용하여 Wi-Fi 프로필 만들기
Intune의 **사용자 지정 구성**을 사용하여 미리 공유한 키로 Wi-Fi 프로필을 만드는 방법은 다음과 같습니다. 이 항목에서는 EAP 기반 Wi-Fi 프로필을 만드는 방법에 대한 예도 포함합니다.

참고:
-   아래 설명된 대로 네트워크에 연결된 컴퓨터에서 코드를 손쉽게 복사할 수 있음을 알 수 있습니다.
- Android의 경우 Johnathon Biersack이 제공하는 이 [Android PSK 생성기](http://johnathonb.com/2015/05/intune-android-pre-shared-key-generator/)를 사용하는 옵션도 포함합니다.
-   더 많은 OMA-URI 설정을 추가하여 여러 네트워크와 키를 추가할 수 있습니다.
-  iOS의 경우 Mac 스테이션에서 프로필을 구성하는 데 Apple Configurator를 사용합니다. 또는 Johnathon Biersack이 제공하는 이 [iOS PSK Mobile Config Generator](http://johnathonb.com/2015/05/intune-ios-psk-mobile-config-generator/)를 사용합니다.


1.  Android 또는 Windows에 대해 미리 공유한 키를 사용하여 Wi-Fi 프로필을 만들거나 EAP 기반 Wi-Fi 프로필을 만들려면 정책을 만들 때 Wi-Fi 프로필보다는 해당 장치 플랫폼에 대한 **사용자 지정 구성**을 선택합니다.

2.  이름 및 설명을 제공합니다.
3.  새 OMA-URI 설정을 추가합니다.

   a.   이 Wi-Fi 네트워크 설정에 대한 이름을 입력합니다.

   b.   OMA-URI 설정에 대한 설명을 입력하거나 비워 둡니다.

   c.   **데이터 형식**: "String(XML)"으로 설정합니다.

   d.   **OMA-URI**: ./Vendor/MSFT/Wi-Fi /Profile/<SSID>/Settings

참고: 시작 부분에 점 문자를 포함해야 합니다.

SSID는 정책을 만들고 있는 SSID입니다. 예:
`./Vendor/MSFT/Wi-Fi/Profile/Hotspot-1/Settings`

  e.    값 필드: XML 코드를 붙여 넣을 위치입니다. 아래 예를 살펴보세요. 각 값을 네트워크 설정에 맞게 조정해야 합니다. 일부 포인터에 대해서는 코드의 주석 섹션을 참조하세요.


    <!--
    <Name of wifi profile> = Name of profile
    <SSID of wifi profile> = Plain text of SSID. Does not need to be escaped, could be <name>Your Company's Network</name>
    <nonBroadcast><true/false></nonBroadcast>
    <Type of authentication> = Type of authentication used by the network, such as WPA2PSK.
    <Type of encryption> = Type of encryption used by the network
    <protected>false</protected> do not change this value, as true could cause device to expect an encrypted password and then try to decrypt it, which may result in a failed connection.
    <password> = Password to connect to the network
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

## EAP 기반 Wi-Fi 프로필
EAP 기반 Wi-Fi 프로필에 대한 XML 코드 예제는 다음과 같습니다.

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

4.  확인을 클릭한 후 정책을 저장 및 배포합니다.
참고. 이 정책은 사용자 그룹에만 배포할 수 있습니다.

다음에 각 장치가 체크인되면 정책이 적용되고 해당 장치에 Wi-Fi 프로필이 만들어집니다. 장치를 네트워크에 자동으로 연결할 수 있게 됩니다.
## 기존 Wi-Fi 연결에서 XML 파일 만들기
기존 Wi-Fi 연결에서 XML 파일을 만들 수도 있습니다.
1.     무선 네트워크에 연결되어 있거나 최근에 연결된 컴퓨터에서 C:\ProgramData\Microsoft\Wlansvc\Profiles\Interfaces\{guid} 폴더를 엽니다. 적합한 것을 찾기 위해 각 프로필을 통해 검색해야 하므로 여러 무선 네트워크에 연결되지 않은 컴퓨터를 사용하는 것이 좋습니다.
3.     XML 파일을 검색하여 올바른 이름의 항목을 찾습니다.
4.     올바른 XML 파일을 찾았으면 XML 코드를 복사하여 OMA-URI 설정 페이지의 데이터 필드에 붙여 넣습니다.

## 정책 배포

1.   **정책** 작업 영역에서 배포할 정책을 선택하고 **배포 관리**를 클릭합니다.

2.   **배포 관리** 대화 상자에서

    -   **정책을 배포하려면** - 정책을 배포하려는 그룹을 하나 이상 선택한 후 **추가** &gt; **확인**을 클릭합니다.

    -   **정책을 배포하지 않고 대화 상자를 닫으려면** - **취소**를 클릭합니다.

배포한 정책을 선택하면 정책 목록 아래쪽에서 배포에 대한 추가 정보를 볼 수 있습니다.

### 참고 항목
[Microsoft Intune에서 Wi-Fi 연결](wi-fi-connections-in-microsoft-intune.md)



<!--HONumber=Jul16_HO3-->


