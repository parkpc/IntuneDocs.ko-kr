---
title: "수동으로 Windows 장치 동기화 | Microsoft Intune"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 443c6de7-5187-4dc4-b844-6085a0c659bd
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6adfb7375f9747f64e7037164f48918789bd7ee0
ms.openlocfilehash: 9561cf77e1569a6ab0da5d9b8e90e03ce5c9e998


---


# <a name="sync-your-windows-device-manually"></a>수동으로 Windows 장치 동기화
앱 설치가 너무 오래 걸리면, Windows 장치를 수동으로 동기화해 볼 수 있습니다. 수동으로 동기화하면 설치 속도를 향상할 수 있습니다.

다음 버전만 지원됩니다. 장치가 나열되지 않으면 동기화가 지원되지 않는 것입니다. 사용하는 장치 유형에 해당하는 지침을 사용하세요.

* [Windows 10 Mobile](#windows-10-mobile)
* [Windows 10 Desktop](#windows-10-desktop)
* [Windows Phone 8.1](#windows-phone-81)


## <a name="windows-10-mobile"></a>Windows 10 Mobile
느린 앱 설치 속도를 높이기 위해 Windows 10 모바일 장치를 수동으로 동기화하려면:

1. **모든 앱** > **설정** > **계정**으로 이동합니다.

    ![설정 화면에서 계정 선택](./media/win10m-sync-1-settings-accounts.png)

2. **회사 액세스**를 선택합니다.

    ![계정 유형으로 회사 액세스 선택](./media/win10m-sync-2-work-access.png)

3. **장치 관리에 등록**에서 회사 이름을 탭합니다.

    ![장치 관리에 대한 회사 이름 선택](./media/win10m-sync-3-tap-comp-name.png)

4. **동기화** 아이콘을 선택합니다.

    ![동기화 아이콘 선택](./media/win10m-sync-4-tap-sync.png)

    “We’re synching your account(계정을 동기화 중입니다.)”라는 메시지가 화면 맨 위에 표시됩니다. **동기화** 단추는 장치 동기화를 마칠 때까지 회색으로 표시됩니다.

## <a name="windows-10-desktop"></a>Windows 10 Desktop
Windows 10 버전에는 여러 개가 있으므로 두 가지 방식의 단계가 있습니다. 사용할 단계를 확인하려면 스크린샷을 확인한 후 장치에 표시되는 것과 비슷한 단계를 따릅니다.

1. **시작** 단추를 선택한 다음 **설정**을 선택합니다.

    ![시작 단추](./media/win10pc-sync-1-start-button.png)

2. **설정** 페이지에서 **계정**을 선택합니다.

    ![설정 페이지에서 계정 선택](./media/win10pc-sync-2-settings-accounts.png)

3. 다음의 두 화면 중에서 장치에 표시되는 것과 비슷한 화면을 찾습니다. 장치에 표시되는 화면의 지침을 따릅니다.

    “회사 또는 학교 액세스” 화면이 표시되면 [회사 또는 학교 액세스가 표시되는 경우 따라야 하는 절차](#steps-to-follow-if-you-see-access-work-or-school)의 지침을 따릅니다.

    ![회사 또는 학교 액세스가 표시되는 경우 따라야 하는 동기화 단계](./media/w10-enroll-rs1-connect-to-work-or-school.png)

    “회사 액세스” 화면이 표시되면 [회사 액세스가 표시되는 경우 따라야 하는 절차](#steps-to-follow-if-you-see-your-account)의 단계를 수행합니다.

    ![계정 유형으로 회사 액세스 선택](./media/win10pc-sync-3-work-access.png)

### <a name="steps-to-follow-if-you-see-access-work-or-school"></a>회사 또는 학교 액세스가 표시되는 경우 따라야 하는 절차

1. **계정** 페이지에서 **회사 또는 학교 액세스**를 선택합니다.

    ![회사 또는 학교 액세스 선택](./media/w10-enroll-rs1-connect-to-work-or-school.png)

2. 회사 또는 학교 계정을 선택합니다. IT 관리자가 설정한 방법에 따라 아래에 표시된 예제와 같이 두 개의 계정이 표시될 수 있습니다. 한 계정 옆에는 서류 가방이 표시되고 다른 계정 옆에는 Microsoft 로고가 표시됩니다.

    - 서류 가방이 있는 계정이 있으면 해당 계정을 선택하고 **정보** 단추를 찾습니다.
    - Microsoft 로고가 있는 계정만 보이면 해당 계정을 선택하고 아래에 있는 **정보** 단추를 찾습니다.

    ![서류 가방 또는 Microsoft 로고 옆에 있는 계정 이름 선택](./media/win10pc-rs1-sync-info-button.png)

3. **정보** 단추를 선택합니다. 아래 예제와 비슷한 대화 상자가 열립니다.

    ![서류 가방 또는 Microsoft 로고 옆에 있는 계정 이름 선택](./media/win10pc-rs1-sync-button.png)

4. **동기화** 단추를 선택합니다. 장치가 Intune과 동기화됩니다.

### <a name="steps-to-follow-if-you-see-work-access"></a>회사 액세스가 표시되는 경우 준수할 절차

1. **계정** 페이지에서 **회사 액세스**를 선택합니다.

    ![계정 유형으로 회사 액세스 선택](./media/win10pc-sync-3-work-access.png)

2. **장치 관리에 등록** 섹션에서 회사 이름을 클릭합니다.

    ![장치 관리에 대한 회사 이름 선택](./media/win10pc-sync-4-tap-com-name.png)

3. **동기화** 단추를 선택합니다.

    ![동기화 단추 선택](./media/win10pc-sync-5-tap-sync.png)

   단추는 동기화가 완료될 때까지 회색으로 표시됩니다.

## <a name="windows-phone-81"></a>Windows Phone 8.1
느린 앱 설치 속도를 높이기 위해 Windows Phone 8.1 장치를 수동으로 동기화하려면:

1. **모든 앱** > **설정** > **회사**로 이동합니다.

    ![설정 목록](./media/wp81-1-sync-settings-workplace.png)

2. 회사 이름을 선택합니다.

    ![회사 계정의 회사 이름 선택](./media/wp81-2-sync-tap-compname.png)

3. **동기화** 아이콘을 선택합니다.

    ![동기화 아이콘 선택](./media/wp81-3-sync-tap-sync-button.png)

   장치 동기화를 마칠 때까지 “We’re synching your account(계정을 동기화 중입니다.)”라는 메시지가 화면 맨 위에 표시됩니다.

여전히 도움이 필요하세요? IT 관리자에게 문의하세요. 연락처 정보는 [회사 포털 웹 사이트](http://portal.manage.microsoft.com)를 참조하세요.



<!--HONumber=Dec16_HO2-->


