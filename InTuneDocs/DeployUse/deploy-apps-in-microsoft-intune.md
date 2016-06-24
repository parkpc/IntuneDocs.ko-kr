---
# required metadata

title: 앱 배포 | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 3b42019e-73da-4538-a496-212f11d5bf9b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: mghadial
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:
---
# Microsoft Intune에서 앱 배포

이 항목의 정보를 사용하여 Microsoft Intune 앱을 배포할 수 있습니다.


## 앱 배포
이 절차에서는 선택한 장치 또는 사용자에 대해 앱을 배포합니다.

### 앱을 배포하려면

1. [Microsoft Intune 관리자 콘솔](https://manage.microsoft.com)에서 **앱** &gt; **앱**을 클릭하여 관리 대상 앱 목록을 표시합니다.

2.  배포할 앱을 선택하고 **배포 관리**를 클릭합니다.

3.  먼저 *&lt;앱 이름&gt;*대화 상자의 **그룹 선택** 페이지에서 앱을 배포할 사용자 또는 장치 그룹을 선택합니다.

4.  **배포 작업** 페이지에서 다음 항목을 구성합니다.

    - **승인** - 배포가 다음에 해당하는지의 여부를 선택합니다.
        - **필수**(필수 설치)
        - **사용 가능**(필요에 따라 회사 포털에서 사용자가 설치)
        - **해당 사항 없음**(앱이 설치되거나 회사 포털에 표시되지 않음)
        - **제거**(대상 장치에서 앱이 제거됨)
    - **마감일** - 필수 설치의 경우 앱을 배포할 마감일을 선택합니다. 미리 정의된 값에서 선택하거나 **사용자 지정**을 선택하여 마감일을 직접 구성할 수 있습니다.

5. 모바일 응용 프로그램 관리 정책을 통해 배포 중인 앱을 구성할 수 있는 경우 **모바일 앱 관리** 페이지가 표시됩니다. 이 페이지에서 이 앱과 연결할 모바일 응용 프로그램 관리 정책을 선택합니다.

    [모바일 응용 프로그램 관리 정책과 호환되는 Microsoft 앱을 참조하세요.](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx)

6. 배포 중인 앱이 Intune VPN 프로필과 호환되는 경우 **VPN 프로필** 페이지가 표시됩니다. 이 페이지에서 배포한 VPN 프로필을 iOS 앱과 연결하도록 선택할 수 있습니다. 앱이 시작되면 VPN 연결이 자동으로 열립니다. VPN 프로필을 사용할 수 있도록 하려면, 사용하도록 설정된 **앱별 VPN** 프로필 설정이 있어야 합니다.
 프로필과 앱의 연결에 대한 지원을 비롯하여, VPN 프로필을 구성하는 방법에 대한 자세한 내용은 [사용자가 Microsoft Intune에서 VPN 프로필을 사용하여 회사에 연결하도록 지원](vpn-connections-in-microsoft-intune.md) 항목을 참조하세요.

## 예제

이 예제에서는 iOS 장치에 **사용 가능**한 앱을 배포했습니다.
앱은 사용자가 앱을 설치할 수 있는 사용자 장치의 회사 포털에 표시됩니다. 예를 들어 왼쪽 스크린샷에서는 iOS용 Bing 앱이 **외부 링크** 설치 유형을 사용하여 배포되었고, 사용자 지정 아이콘이 사용되었으며, **회사 포털에서 이 항목을 추천 앱 및 하이라이트로 표시합니다.** 옵션이 선택되었습니다.
    ![iOS 사용 가능한 앱](./media/available-install-on-iOS.png)

iOS 장치에 **필요한** 앱을 배포한 경우 사용자는 앱을 설치할 준비가 되었다는 알림을 받게 됩니다. 예를 들어 왼쪽 스크린샷에서는 **앱 스토어에서 관리되는 iOS 앱** 설치 유형을 사용하여 iOS용 작업 폴더 앱을 배포한 상태입니다.
    ![iOS 필수 앱](./media/iOS-Required-install.PNG)

## 다음 단계

앱을 배포한 후에 진행 상태를 모니터링하려고 합니다. 자세한 내용은 [Monitor apps in Microsoft Intune](monitor-apps-in-microsoft-intune.md)(Microsoft Intune에서 앱 모니터링) 항목을 참조하세요.


<!--HONumber=Jun16_HO2-->


