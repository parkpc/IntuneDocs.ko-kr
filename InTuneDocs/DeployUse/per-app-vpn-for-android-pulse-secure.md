---
# required metadata

title: Pulse Secure를 사용한 Android용 앱별 VPN | Microsoft Intune
description:
keywords:
author: nbigman
manager: jeffgilb
ms.date: 05/08/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: ac65e906-3922-429f-8d9c-d313d3126645

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: chrisbal
#ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# 사용자 지정 정책을 사용하여 Android 장치용 앱별 VPN 프로필 만들기

Intune으로 관리되는 Android 장치용 앱별 VPN 프로필을 만들 수 있습니다. 먼저 Pulse Secure 연결 형식을 사용하는 VPN 프로필을 만든 후 해당 프로필을 특정 앱과 연결하는 사용자 지정 구성 정책을 만듭니다. 이러한 정책을 Android 장치 또는 사용자 그룹에 배포한 후 장치에서 지정된 앱 중 하나를 열면 해당 앱에 대한 VPN 연결이 열립니다. 

### 1단계: VPN 프로필 만들기

1. [Microsoft Intune 관리 콘솔](https://manage.microsoft.com)에서 **정책** > **정책 추가**를 클릭합니다.
2. **Android**를 확장하여 새 정책에 대한 템플릿을 선택한 후 **VPN 프로필(Android 4 이상)**을 선택합니다.

3. 템플릿에서 **연결 형식**으로 **Pulse Secure**를 선택합니다.
4. 완료하고 VPN 프로필을 저장합니다. VPN 프로필에 대한 자세한 내용은 [VPN 프로필](Help%20users%20connect%20to%20their%20work%20using%20VPN%20profiles%20with%20Microsoft%20Intune.md)을 참조하세요.

> [!NOTE]
다음 단계에서 사용할 수 있도록 VPN 프로필 이름을 기록해 두세요. 예를 들면 **MyAppVpnProfile**입니다.
   
### 2단계: 사용자 지정 구성 정책 만들기
    
   1. Intune 관리 콘솔에서 **정책** -> **정책 추가** -> **Android** -> **사용자 지정 구성** -> **정책 만들기**를 선택합니다.
   2. 정책의 이름을 제공합니다.
   3. **OMA-URI 설정**에서 **추가**를 클릭합니다.
   4. 설정 이름을 지정합니다.
   5. **데이터 형식**으로 **문자열**을 지정합니다.
   6. **OMA-URI**로 **./Vendor/MSFT/VPN/Profile/*Name*/PackageList** 문자열을 지정합니다. 여기서 *Name*은 1단계에서 적어둔 VPN 프로필 이름입니다. 이 예제에서 문자열은 **./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/PackageList**입니다.
   7.   **값**에는 프로필과 연결해야 하는 패키지 목록을 세미콜론으로 구분하여 지정합니다.  예를 들어 Excel 및 Google Chrome 브라우저에서 VPN 연결을 사용하려면 **com.microsoft.office.excel;com.android.chrome**과 같이 입력합니다.
  

   ![Android 앱별 VPN 사용자 지정 정책의 예](..\media\android_per_app_vpn_oma_uri.png) 
#### 앱 목록을 블랙리스트 또는 허용 목록으로 설정(옵션)
앱 목록이 VPN 연결을 사용하지 *못하게* **블랙리스트** 값을 사용하여 지정할 수 있습니다.  다른 모든 앱은 VPN을 통해 연결됩니다.

또는 *오직* 지정한 앱에서만 VPN 연결을 사용할 수 있도록 **허용 목록** 값을 사용하여 지정할 수 있습니다.
 

1.  OMA-URI 설정에서 **추가**를 클릭합니다.
2.  설정 이름을 지정합니다.
3.  **데이터 형식**으로 **문자열**을 지정합니다.
4.  **OMA-URI**로 **./Vendor/MSFT/VPN/Profile/*Name*/Mode** 문자열을 지정합니다. 여기서 *Name*은 1단계에서 적어둔 VPN 프로필 이름입니다. 이 예제에서 문자열은 **./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/Mode**입니다.
5.  **값**에 **블랙리스트** 또는 **허용 목록**을 입력합니다. 


   
### 3단계: 두 정책 모두 배포

두 정책은 *모두* *동일한* Intune 그룹에 배포해야 합니다.

   1.   **정책** 작업 영역에서 배포할 정책을 선택하고 **배포 관리**를 클릭합니다.

2.   **배포 관리** 대화 상자에서

    -   **정책을 배포하려면** - 정책을 배포하려는 그룹을 하나 이상 선택한 후 **추가** &gt; **확인**을 클릭합니다.

    -   **정책을 배포하지 않고 대화 상자를 닫으려면** - **취소**를 클릭합니다.

**정책** 작업 영역의 **개요** 페이지에 있는 상태 요약 및 경고는 주의가 필요한 정책 문제를 식별합니다. 또한 상태 요약은 대시보드 작업 영역에 표시됩니다.



<!--HONumber=Jun16_HO1-->


