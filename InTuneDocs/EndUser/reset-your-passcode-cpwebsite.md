---
title: "회사 포털 웹 사이트에서 암호를 재설정하는 방법 | Microsoft 문서"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 01/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4fa3255b-9d1e-42d5-bd8b-70963dcf2d86
searchScope:
- Company Portal
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a87fe0cf9591040f1455d71b1f40cd0705ba8abf
ms.openlocfilehash: a8ce59755a74199eda6865feda68c0613d10c2a7


---

# <a name="how-to-reset-your-device-passcode-from-the-company-portal-website"></a>회사 포털 웹 사이트에서 장치 암호를 재설정하는 방법

Intune에서 등록한 장치의 장치 PIN 또는 암호를 분실할 경우 [회사 포털 웹 사이트](http://portal.manage.microsoft.com)를 사용하여 암호를 재설정할 수 있습니다. 회사 포털 웹 사이트에서 Intune에 등록한 컴퓨터 및 장치를 관리하고 회사 포털 앱을 사용할 때 수행할 수 있는 동일한 작업을 대부분 수행할 수 있습니다.

> [!NOTE]
> 회사 포털 웹 사이트에 **암호 재설정** 단추가 표시되지 않을 수도 있습니다. 표시되지 않을 경우 회사 포털 웹 사이트를 통해 IT 관리자에게 지원을 요청해야 합니다.

암호를 재설정하려면

1.  [회사 포털 웹 사이트](http://portal.manage.microsoft.com)를 열고 암호를 재설정하려는 장치를 선택합니다.

2.  **암호 초기화**를 선택합니다.

    ![암호 재설정 단추가 있는 장치 세부 정보](./media/iwp-screen-with-all-options.png)

3.  **로그아웃**을 선택하고 회사 또는 학교 자격 증명을 사용하여 다시 로그인합니다. 5분 내에 다시 로그인해야 합니다.

    ![로그아웃 단추가 있는 재설정 메시지](./media/iwp-2-sign-out.png)

4.  **암호 초기화**를 선택합니다.

    ![암호를 재설정할 때 나타나는 결과를 설명하는 메시지](./media/iwp-3-tap-reset-passcode-after-signin.png)

    장치에서 **암호 재설정**이 작동하는 방식을 보려면 표를 확인하세요.

    |장치 유형|다시 설정하는 경우 어떻게 되나요?|
    |------------|-----------|
    |Android|기존 암호를 제거하고 문자와 숫자를 사용하여 임시 암호를 만듭니다.|
    |iOS|기존 암호를 제거하고 임시 암호를 만들지 않습니다. 장치를 열거나 구매를 위해 Touch ID 지문 스캐너를 사용하는 경우 암호를 다시 설정해야 합니다.|
    |Windows 10 Mobile|기존 암호를 제거하고 문자와 숫자를 사용하여 임시 암호를 만듭니다. 로그인하는 데 Windows Hello의 안면 인식을 사용 중인 경우에는 이후에도 계속 지원됩니다.|
    |Windows Phone 8.1|기존 암호를 제거하고 숫자를 사용하여 임시 암호를 만듭니다.|

    5.  장치의 잠금을 해제한 후 장치 **설정**으로 이동하여 새 암호를 설정하거나 임시 암호를 변경합니다.

    암호가 재설정되었는지 확인하는 알림을 보려면 회사 포털 웹 사이트의 오른쪽 맨 위에 있는 알림 플래그를 클릭합니다.

여전히 도움이 필요하세요? IT 관리자에게 문의하세요. 연락처 정보는 [회사 포털 웹 사이트](http://portal.manage.microsoft.com)를 참조하세요.



<!--HONumber=Jan17_HO4-->


