---
title: "Android for Work 장치에 앱 배포 | Microsoft Intune"
description: "이 항목을 사용하여 앱을 동기화한 다음 Google Play for Work 스토어에서 Android for Work 장치로 배포합니다."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/6/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd0bbd90-d3fe-4efc-83fd-d1f3f86800d4
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 35ee89248e42c67f48d4607f5d415896e35b90e9


---

# <a name="how-to-deploy-apps-to-android-for-work-devices-with-intune"></a>Intune으로 Android for Work 장치에 앱을 배포하는 방법

[!INCLUDE[wit_nextref](../includes/afw_rollout_disclaimer.md)]

표준 Android 장치에 배포하던 방식과 다른 방법으로 Android for Work 장치에 앱을 배포합니다. Android for Work에 대해 설치하는 모든 앱은 Google Play for Work 스토어에서 받습니다. 스토어에 로그인하고 원하는 앱을 찾아본 다음 승인합니다.
그러면 Intune 콘솔의 **대량 구매 앱** 노드에 나타납니다. 여기에서 다른 앱을 배포하는 방식과 동일하게 앱 배포를 관리할 수 있습니다.
또한 고유한 LOB(기간 업무) 앱을 만든 경우 배포할 수 있습니다. 이렇게 하려면 Google Play 스토어의 개인 영역에 앱을 게시할 수 있는 Google Developer 계정에 가입한 다음 Intune과 동기화해야 합니다.

## <a name="before-you-start"></a>시작하기 전에

1. Intune과 Android for Work가 Intune 콘솔의 **관리** 탭에서 함께 작업할 수 있도록 구성했는지 확인합니다.

## <a name="synchronize-an-app-from-the-google-play-for-work-store"></a>Google Play for Work 스토어에서 앱 동기화


1. [Google Play for Work 스토어](https://play.google.com/work)로 이동합니다. Intune과 Android for Work 간 연결을 구성하는 데 사용한 동일한 계정으로 로그인합니다.
2. Intune을 사용하여 배포할 앱에 대한 스토어를 검색합니다.
3. 선택한 앱 페이지에서 **승인**을 선택합니다. 이 예제에서는 Microsoft Excel 앱을 선택했습니다.<br>
  ![앱 승인 예제](/intune/deploy-use/media/approve.png)
4. 앱 창이 열리면서 앱에서 다양한 작업을 수행할 수 있는 권한을 부여하라는 메시지가 표시됩니다. 계속하려면 **승인**을 선택해야 합니다.<br>
  ![앱 사용 권한 승인 예제](/intune/deploy-use/media/approve-app-permissions.png)
5. 잠시 후 앱이 승인되고 IT 관리 콘솔에서 사용할 수 있음을 알리는 확인 메시지가 표시됩니다.

## <a name="publish-then-synchronize-a-line-of-business-app-from-the-google-play-for-work-store"></a>Google Play for Work 스토어에서 LOB(기간 업무) 앱 게시 후 동기화

1. Google Play Developer 콘솔 [play.google.com/apps/publish](https://play.google.com/apps/publish)로 이동합니다.
2. Intune과 Android for Work 간 연결을 구성하는 데 사용한 동일한 계정으로 로그인합니다. 처음으로 로그인하는 경우 Google Developer 프로그램 구성원이 되도록 등록하고 요금을 지불해야 합니다.
3. 콘솔에서 **새 응용 프로그램 추가**를 선택합니다.
4. Google Play 스토어에 앱을 게시한 것과 동일한 방법으로 앱에 대한 정보를 업로드하고 제공합니다. 하지만 아래와 같이 **Only make this application available to my organization (<*organization name*>)(이 응용 프로그램을 내 조직만 사용)** 설정을 선택해야 합니다.<br>
  ![내 조직에서만 앱 사용 가능 옵션](/intune/deploy-use/media/restrict.png)<br>
이렇게 하면 앱은 해당 조직에서만 사용할 수 있고 공개 Google Play 스토어에서 사용할 수 없게 됩니다.
Android 앱 업로드 및 게시하는 방법에 대한 자세한 내용은 [Google Developer Console Help](https://support.google.com/googleplay/android-developer/answer/113469)(Google Developer 콘솔 도움말)를 참조하세요.
5. 앱을 게시한 후에는 [Google Play for Work 스토어](https://play.google.com/work)로 이동합니다. Intune과 Android for Work 간 연결을 구성하는 데 사용한 동일한 계정으로 로그인합니다.
6. 스토어의 **앱** 노드에서 게시한 앱을 볼 수 있는지 확인합니다. Intune와 동기화되도록 자동으로 승인됩니다.

## <a name="deploy-an-android-for-work-app"></a>Android for Work 앱 배포

일반적으로 Intune에서는 하루에 두 번 Google Play for Work 스토어와 동기화됩니다. 스토어에서 앱을 승인했지만 **앱** 작업 영역의 **대량 구매 앱** 노드에 표시되지 않으면 다음과 같이 강제로 즉시 동기화할 수 있습니다.

1. [Intune 관리자 콘솔](https://manage.microsoft.com)에서 **관리** > **모바일 장치 관리** > **Android for Work**를 선택합니다.
2. **Android for Work모바일 장치 관리 설치** 페이지에서 **지금 동기화**를 클릭합니다.
3. 페이지에 마지막 동기화의 시간 및 상태도 표시됩니다.

앱이 **앱** 작업 영역의 **대량 구매 앱** 노드에 표시되면 [다른 앱과 마찬가지 방법으로 배포](deploy-apps-in-microsoft-intune.md)할 수 있습니다. 앱은 사용자의 그룹에만 배포할 수 있습니다. 현재 **필수**와 **제거** 작업 중에서만 선택할 수 있습니다. 2016년 10월부터 **사용 가능한** 배포 작업을 새 테넌트에 추가할 예정입니다.

앱을 배포하고 나면 대상으로 지정한 장치에 설치됩니다. 사용자의 장치에 승인할지 묻는 메시지가 표시됩니다.



<!--HONumber=Dec16_HO2-->


