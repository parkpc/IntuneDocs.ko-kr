---
# required metadata

title: 인증서 프로필 구성 | Microsoft Intune
description:
keywords:
author: nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 679a20a1-e66f-4b6b-bd8f-896daf1f8175

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Intune 인증서 프로필 구성
[인증서 인프라 구성](configure-certificate-infrastructure.md)에 설명한 대로 인프라 및 인증서를 구성한 후에는 인증서 프로필을 구성할 수 있습니다.

**작업 1** - 신뢰할 수 있는 루트 CA 인증서 내보내기
**작업 2** - 신뢰할 수 있는 CA 인증서 프로필 만들기
**작업 3** - 다음 중 한 가지 수행:

SCEP 인증서 프로필 만들기

.PFX 인증서 프로필 만들기

### 작업 1 - 신뢰할 수 있는 루트 인증서 내보내기
발급 CA 또는 발급 CA를 신뢰하는 장치에서 신뢰할 수 있는 루트 CA 인증서를 **.cer** 파일로 내보냅니다. 개인 키는 내보내지 않습니다.

신뢰할 수 있는 인증서 프로필을 구성할 때 이 인증서를 가져옵니다.

### 작업 2 - 신뢰할 수 있는 인증서 프로필 만들기
SCEP 또는 .PFX 인증서 프로필을 만들기 전에 **신뢰할 수 있는 인증서 프로필**을 구성해야 합니다. 각 모바일 장치 플랫폼에 신뢰할 수 있는 인증서 프로필 및 SCEP 또는 .PFS 프로필이 필요합니다.

##### 신뢰할 수 있는 인증서 프로필을 만들려면

1.  [Intune 관리 콘솔](https://manage.microsoft.com)을 열고 **정책** &gt; **정책 추가**를 클릭합니다..

2.  다음 정책 유형 중 하나를 구성합니다.

    **Android &gt; 신뢰할 수 있는 인증서 프로필(Android 4 이상)**

    **iOS &gt; 신뢰할 수 있는 인증서 프로필(iOS 7.1 이상)**

    **Mac OS X &gt; 신뢰할 수 있는 인증서 프로필(Mac OS X 10.9 이상)**

    **Windows &gt; 신뢰할 수 있는 인증서 프로필(Windows 8.1 이상)**

    **Windows &gt; 신뢰할 수 있는 인증서 프로필(Windows Phone 8.1 이상)**

    자세한 정보: [Microsoft Intune 정책을 사용하여 장치의 설정 및 기능 관리](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

3.  요청한 정보를 제공하여 Android, iOS, Mac OS X, Windows 8.1 또는 Windows Phone 8.1에 신뢰할 수 있는 인증서 프로필 설정을 구성합니다. **인증서 파일**에서 발급한 CA에서 내보낸 신뢰할 수 있는 루트 CA 인증서(**.cer**)를 가져옵니다. 장치에 둘 이상의 인증서 저장소가 있는 경우 **대상 저장소** 설정은 Windows 8.1 이상을 실행하는 장치에만 적용됩니다.


4.  작업이 끝나면 **정책 저장**을 클릭합니다..

새 정책에 **정책** 작업 영역이 표시됩니다. 이제 정책을 배포할 수 있습니다.

### 작업 3 – SCEP 또는 .PFX 인증서 프로필 만들기
신뢰할 수 있는 CA 인증서 프로필을 만든 후에는 사용하려는 각 플랫폼에 대해 SCEP 또는 .PFX 인증서 프로필을 만듭니다. SCEP 인증서 프로필을 만들 때는 같은 플랫폼에 대해 신뢰할 수 있는 인증서 프로필을 지정해야 합니다. 그러면 두 인증서 프로필이 연결되기는 하지만 각 프로필을 개별적으로 배포해야 합니다.

##### SCEP 인증서 프로필을 만들려면

1.  [Intune 관리 콘솔](https://manage.microsoft.com)에서 **정책** &gt; **정책 추가**를 클릭합니다..

2.  다음 정책 유형 중 하나를 구성합니다.

    **Android &gt; SCEP 인증서 프로필(Android 4 이상)**

    **iOS &gt; SCEP 인증서 프로필(iOS 7.1 이상)**

    **Mac OS X &gt; SCEP 인증서 프로필(Mac OS X 10.9 이상)**

    **Windows &gt; SCEP 인증서 프로필(Windows 8.1 이상)**

    **Windows &gt; SCEP 인증서 프로필(Windows Phone 8.1 이상)**

    자세한 정보: [Microsoft Intune 정책을 사용하여 장치의 설정 및 기능 관리](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

3.  SCEP 인증서 프로필 설정을 구성하려면 프로필 구성 페이지의 지침을 따릅니다.

4.  작업이 끝나면 **정책 저장**을 클릭합니다..

새 정책에 **정책** 작업 영역이 표시됩니다. 이제 정책을 배포할 수 있습니다.

##### .PFX 인증서 프로필을 만들려면

1.  [Intune 관리 콘솔](https://manage.microsoft.com)에서 **정책** &gt; **정책 추가**를 클릭합니다..

2.  다음 정책 유형 중 하나를 구성합니다.



-   **Android &gt; .PFX 인증서 프로필(Android 4 이상)**

    -   **Windows &gt; PKCS #12(.PFX) 인증서 프로필(Windows 10 이상)**

    -   **Windows &gt; PKCS #12(.PFX) 인증서 프로필(Windows Phone 10 이상)**

    -    **iOS > PKCS #12(.PFX) 인증서 프로필(iOS 7.1 이상)**    

    자세한 정보: [Microsoft Intune 정책을 사용하여 장치의 설정 및 기능 관리](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

3.  정책 형식에서 요청하는 정보를 입력합니다.

4.  작업이 끝나면 **정책 저장**을 클릭합니다..

새 정책에 **정책** 작업 영역이 표시됩니다. 이제 정책을 배포할 수 있습니다.

## 인증서 프로필 배포
인증서 프로필을 배포할 때는 신뢰할 수 있는 CA 인증서 프로필의 인증서 파일이 장치에 설치됩니다. 장치에서는 SCEP 또는 .PFX 인증서 프로필을 사용하여 장치의 인증서 요청을 작성합니다.

인증서 프로필은 프로필 작성 시 사용하는 플랫폼에 따라 적용 가능한 장치에만 설치됩니다.

-   사용자 컬렉션 또는 장치 컬렉션에 인증서 프로필을 배포할 수 있습니다.

    > [!TIP]
    > 장치를 등록한 후 인증서를 장치에 빠르게 게시하려면 인증서 프로필을 장치 그룹이 아닌 사용자 그룹에 배포합니다. 장치 그룹에 프로필을 배포하는 경우에는 장치에서 정책을 수신하기 전에 전체 장치 등록을 수행해야 합니다.

-   각 프로필은 개별적으로 배포되지만 신뢰할 수 있는 루트 프로필과 SCEP/.PFX 프로필을 둘 다 배포해야 하며, 그렇지 않으면 SCEP/.PFX 인증서 정책에서 오류가 발생합니다.

다른 Intune에 정책을 배포하는 것과 같은 방식으로 인증서 프로필을 배포합니다.

1.  **정책** 작업 영역에서 배포할 정책을 선택하고 **배포 관리**를 클릭합니다..

2.   **배포 관리** 대화 상자에서

    -   **정책을 배포하려면** - 정책을 배포하려는 그룹을 하나 이상 선택하고 **추가** &gt; **확인**을 클릭합니다..

    -   **정책을 배포하지 않고 대화 상자를 닫으려면** - **취소**를 클릭합니다..

배포한 정책을 선택하면 정책 목록 아래쪽에서 배포에 대한 추가 정보를 볼 수 있습니다.
###  다음 단계

이제 인증서를 사용하여 전자 메일, Wi-Fi 및 VPN 프로필을 보호할 수 있습니다.

-  [메일 프로필을 사용하여 회사 메일에 대한 액세스 구성](configure-access-to-corporate-email-using-email-profiles-with-Microsoft-Intune.md)
-  [Microsoft Intune에서 Wi-Fi 연결](wi-fi-connections-in-microsoft-intune.md)
-  [Microsoft Intune에서 VPN 연결](vpn-connections-in-microsoft-intune.md)


<!--HONumber=May16_HO1-->


