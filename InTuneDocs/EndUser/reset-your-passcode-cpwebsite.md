---
title: "회사 포털 웹 사이트에서 장치 암호 재설정 | Microsoft Intune"
description: 
keywords: 
author: Staciebarker
ms.author: stabar
manager: angrobe
ms.date: 09/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4fa3255b-9d1e-42d5-bd8b-70963dcf2d86
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
<<<<<<< HEAD
ms.sourcegitcommit: bff97f79c6e88bbf55c2c3a259891bb6206b690b
ms.openlocfilehash: 57e3175af6364e7dacbf8941f10292fc9dc58b15
||||||| merged common ancestors
ms.sourcegitcommit: 08eeb1f330ed8fcea5da41f71ded0ccf124da7c5
ms.openlocfilehash: 552217a59b7bfd9d75f8be1ce4c401d015ba84f7
=======
ms.sourcegitcommit: 2aea845bc00c153f070e04abb67582a5d5a726ca
ms.openlocfilehash: 47b36616f7a8ee23d4d47b41a1db2c41c185c6f5
>>>>>>> 359d4f486355df1be118d8fdb698694ae632df85


---


# 회사 포털 웹 사이트에서 장치 암호 재설정

Intune에서 등록한 장치의 장치 PIN 또는 암호를 분실할 경우 [회사 포털 웹 사이트](http://portal.manage.microsoft.com)를 사용하여 암호를 재설정할 수 있습니다. 회사 포털 웹 사이트에서 Intune에 등록한 컴퓨터 및 장치를 관리하고 회사 포털 앱을 사용할 때 수행할 수 있는 동일한 작업을 대부분 수행할 수 있습니다.

> [!NOTE]
> IT 관리자가 Intune을 구성한 방법에 따라 회사 포털 웹 사이트에 **암호 재설정** 단추가 표시되지 않을 수도 있습니다. 암호 재설정은 Windows 8.1 장치에서 지원되지 않습니다.

암호를 재설정하려면

1.  [회사 포털 웹 사이트](http://portal.manage.microsoft.com)를 열고 암호를 재설정하려는 장치를 선택합니다.

2.  **암호 초기화**를 선택합니다.

    ![암호 재설정 단추가 있는 장치 세부 정보](./media/iwp-screen-with-all-options.png)

3.  **로그아웃**을 선택하고 회사 또는 학교 자격 증명을 사용하여 다시 로그인합니다. 5분 내에 다시 로그인해야 합니다.

    ![로그아웃 단추가 있는 재설정 메시지](./media/iwp-2-sign-out.png)

4.  **암호 초기화**를 선택합니다.

    ![암호를 재설정할 때 나타나는 결과를 설명하는 메시지](./media/iwp-3-tap-reset-passcode-after-signin.png)

    장치에서 **암호 재설정**이 작동하는 방식을 보려면 표를 확인하세요.

    |플랫폼|Support|
    |------------|-----------|
    |Android|임시 영숫자 암호를 만듭니다.|
    |iOS|장치에서 암호를 제거하고 임시 암호를 만들지 않습니다. Touch ID를 사용하는 경우 암호를 재설정할 때 제거되기 때문에 장치에서 다시 설정해야 합니다.|
    |Windows 10(모바일 장치에만 해당)|임시 영숫자 암호를 만듭니다. Windows Hello는 지원되지 않습니다.|
    |Windows Phone 8.1|임시 숫자 암호를 만듭니다.|
    장치의 잠금을 해제한 후 장치의 **설정**으로 이동하여 새 암호를 설정할 수 있습니다.

5.  장치의 잠금을 해제한 후 장치의 **설정**으로 이동하여 새 암호를 설정하거나 임시 암호를 변경합니다.

    암호가 재설정되었는지 확인하는 알림을 보려면 회사 포털 웹 사이트의 오른쪽 맨 위에 있는 알림 플래그를 클릭합니다.

여전히 도움이 필요하세요? IT 관리자에게 문의하세요. IT 관리자의 연락처 정보는 [회사 포털 웹 사이트](http://portal.manage.microsoft.com)를 참조하세요.



<<<<<<< HEAD
<!--HONumber=Sep16_HO3-->
||||||| merged common ancestors
<!--HONumber=Aug16_HO5-->
=======
<!--HONumber=Oct16_HO3-->
>>>>>>> 359d4f486355df1be118d8fdb698694ae632df85


