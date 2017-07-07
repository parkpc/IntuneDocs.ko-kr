---
title: "Pulse Secure를 사용하는 Android용 앱별 VPN"
description: "Intune으로 관리되는 Android 장치용 앱별 VPN 프로필을 만들 수 있습니다."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ac65e906-3922-429f-8d9c-d313d3126645
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 262cc461d5c1790fdfb162d5453a9cebd48271c4
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2017
---
# <a name="use-a-custom-policy-to-create-a-per-app-vpn-profile-for-android-devices"></a>사용자 지정 정책을 사용하여 Android 장치용 앱별 VPN 프로필 만들기

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune으로 관리되는 Android 5.0 이상 장치용 앱별 VPN 프로필을 만들 수 있습니다. 먼저 Pulse Secure 또는 Citrix 연결 형식을 사용하는 VPN 프로필을 만듭니다. 그런 다음 VPN 프로필을 특정 앱과 연결하는 사용자 지정 구성 정책을 만듭니다. 

Android 장치 또는 사용자 그룹에 정책을 배포한 후에 사용자가 PulseSecure 또는 Citrix VPN을 시작해야 합니다. 그러면 지정한 앱에서 생성되는 트래픽만 열린 VPN 연결을 사용하도록 허용합니다.

> [!NOTE]
>
> 이 프로필에서는 Pulse Secure 및 Citrix 연결 형식만 지원됩니다.


### <a name="step-1-create-a-vpn-profile"></a>1단계: VPN 프로필 만들기

1. [Microsoft Intune 관리 콘솔](https://manage.microsoft.com)에서 **정책** > **정책 추가**를 선택합니다.
2. 새 정책에 대한 템플릿을 선택하려면 **Android**를 확장 한 후 **VPN 프로필(Android 4 이상)**을 선택합니다.
3. 템플릿에서 **연결 형식**으로 **Pulse Secure** 또는 **Citrix**를 선택합니다.
4. 완료하고 VPN 프로필을 저장합니다. VPN 프로필에 대한 자세한 내용은 [VPN 연결](../deploy-use/vpn-connections-in-microsoft-intune.md)을 참조하세요.

> [!NOTE]
>
> VPN 프로필을 만들 때 지정하는 **VPN 연결 이름(사용자에게 표시됨)** 값을 적어 두세요. 다음 단계에서 이 이름이 필요합니다. 예를 들면 **MyAppVpnProfile**입니다.

### <a name="step-2-create-a-custom-configuration-policy"></a>2단계: 사용자 지정 구성 정책 만들기

   1. Intune 관리 콘솔에서 **정책** > **정책 추가** > **Android** > **사용자 지정 구성** > **정책 만들기**를 선택합니다.
   2. 정책의 이름을 입력합니다.
   3. **OMA-URI 설정**에서 **추가**를 선택합니다.
   4. 설정 이름을 입력합니다.
   5. **데이터 형식**으로 **문자열**을 지정합니다.
   6. **OMA-URI**로 **./Vendor/MSFT/VPN/Profile/*Name*/PackageList** 문자열을 지정합니다. 여기서 *Name*은 1단계에서 적어둔 VPN 프로필 이름입니다. 이 예제에서 문자열은 **./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/PackageList**입니다.
   7.   **값**으로 프로필에 연결할 패키지가 세미콜론으로 구분된 목록을 만듭니다. 예를 들어 Excel 및 Google Chrome 브라우저에서 VPN 연결을 사용하려면 **com.microsoft.office.excel;com.android.chrome**과 같이 입력합니다.

![Android 앱별 VPN 사용자 지정 정책의 예](./media/android_per_app_vpn_oma_uri.png)

#### <a name="set-your-app-list-to-blacklist-or-whitelist-optional"></a>앱 목록을 블랙리스트 또는 허용 목록으로 설정(옵션)
  **블랙리스트** 값을 사용하여 VPN 연결을 사용*할 수 없는* 앱 목록을 지정할 수 있습니다. 다른 모든 앱은 VPN을 통해 연결됩니다.
또는 **허용 목록** 값을 사용하여 VPN 연결을 사용*할 수 있는* 앱 목록을 지정할 수 있습니다. 목록에 없는 앱은 VPN을 통해 연결되지 않습니다.
  1.    **OMA URI** 설정에서 **추가**를 선택합니다.
  2.    설정 이름을 입력합니다.
  3.    **데이터 형식**으로 **문자열**을 지정합니다.
  4.    **OMA-URI**로 **./Vendor/MSFT/VPN/Profile/*Name*/Mode** 문자열을 사용합니다. 여기서 *Name*은 1단계에서 적어둔 VPN 프로필 이름입니다. 이 예제에서 문자열은 **./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/Mode**입니다.
  5.    **값**에 **블랙리스트** 또는 **허용 목록**을 입력합니다.



### <a name="step-3-deploy-both-policies"></a>3단계: 두 정책 모두 배포

두 정책은 *모두* *동일한* Intune 그룹에 배포해야 합니다.

1.  **정책** 작업 영역에서 배포할 정책을 선택한 다음 **배포 관리**를 선택합니다.
2.  **배포 관리** 대화 상자에서
    -   **정책을 배포하려면** - 정책을 배포할 그룹을 하나 이상 선택하고 **추가**  >  **확인**을 선택합니다.
    -   **정책을 배포하지 않고 대화 상자를 닫으려면** **취소**를 선택합니다.

**정책** 작업 영역의 **개요** 페이지에 있는 상태 요약 및 경고는 주의가 필요한 정책 문제를 식별합니다. 상태 요약은 **대시보드** 작업 영역에도 표시됩니다.
