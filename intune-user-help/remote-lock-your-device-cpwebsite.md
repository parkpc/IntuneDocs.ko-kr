---
title: "회사 포털에서 장치 잠금 | Microsoft 문서"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: adc6af23-b22f-42e5-955a-4dffbdb8b42b
searchScope: User help
ROBOTS: 
ms.reviewer: jieyang
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: a213a46066de4244df23d0cd532b5fb4596ede77
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2017
---
# <a name="remotely-lock-your-device-from-the-company-portal-website"></a>회사 포털 웹 사이트에서 장치 원격 잠금

사고가 발생하여 경우에 따라 장치를 찾지 못할 수도 있습니다. 장치를 분실하거나 도난당한 경우 가장 먼저 드는 걱정은 장치의 위치에 상관없이 누군가가 장치에 있던 정보를 사용할 수 있다는 점입니다.

[!INCLUDE[wit_nextref](includes/end-user-password-guidance.md)]

안전 유지를 위해 [회사 포털 웹 사이트](http://portal.manage.microsoft.com)의 원격 잠금 옵션을 사용하여 장치를 잠글 수 있습니다. 원격 잠금은 다음 장치에 적용됩니다.

* Android
* iOS
* macOS
* Windows 10 Mobile(장치에 암호가 이미 설정된 경우)
* Windows Phone 8.1(장치에 암호가 이미 설정된 경우)

## <a name="to-use-remote-lock-to-lock-your-device"></a>원격 잠금을 사용하여 장치를 잠그려면

1.  [회사 포털 웹 사이트](http://portal.manage.microsoft.com)에서 __메뉴__ 단추 ![세 개의 가로 막대가 병렬로 누적된 메뉴 단추의 작은 이미지](/Intune/whats-new/media/CP_hamburger_menu.png)를 탭한 다음 __내 장치__를 선택합니다.

  ![화면 왼쪽에 홈, 모든 앱, 내 장치, 기술 지원팀 및 로그 아웃 단추가 포함된 확장된 측면 메뉴가 있는 회사 포털 웹 사이트의 이미지](/media/iwp-expanded-sidebar.png)

2. __내 장치__ 페이지에서 잠그려는 장치의 이름을 선택합니다.

  ![목록에 없는 장치를 등록하거나 식별되지 않은 장치를 식별하라는 배너 프롬프트 위에 몇 개의 식별되지 않은 장치가 표시된 내 장치 페이지의 스크린샷](./media/macOS_enroll_002_tap_here_banner.png)

3.  장치가 팝업 창에서 열립니다. **원격 잠금** 단추를 탭합니다.

    ![이름 바꾸기, 제거, 장치 다시 설정, 암호 다시 설정, 원격 잠금 등 회사 포털 웹 사이트에서 선택한 장치에 대한 모든 옵션 ](./media/iwp-screen-with-all-options.png)

4.  장치를 잠그려고 한다는 알림이 표시됩니다. **원격 잠금**을 탭하면 회사 포털 웹 사이트에서 장치 잠금을 시도합니다.

    **원격 잠금**을 선택하면 "원격 잠금 보류 중" 메시지가 표시됩니다.  원격 잠금에 성공하면 상태가 "원격 잠금 성공"으로 변경됩니다.

    원격 잠금 상태는 다음 세 위치에 표시됩니다.

    * 웹 사이트의 알림 영역
    * 장치의 **세부 정보** 페이지
    * 페이지의 **내 장치** 섹션에 장치 이름을 보여 주는 타일

> [!Note]
> "원격 잠금 실패" 알림이 표시되면 몇 분 정도 기다렸다가 장치 잠금을 다시 시도합니다. 다시 시도하면 상태가 다시 “원격 보류 중”으로 변경됩니다. 다시 시도해도 소용이 없으면 IT 관리자에게 문의해야 합니다.

장치를 찾아 원격 잠금을 사용한 후 잠금을 해제하려면 암호를 입력하면 됩니다.

여전히 도움이 필요하세요? IT 관리자에게 문의하세요. 연락처 정보는 [회사 포털 웹 사이트](http://portal.manage.microsoft.com)를 참조하세요.
