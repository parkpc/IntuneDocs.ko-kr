---
title: "Android for Work 장치에 앱 할당"
titlesuffix: Azure portal
description: "이 항목의 정보를 참조 앱을 동기화한 다음 Google Play for Work 스토어에서 Android for Work 장치에 할당합니다.\""
keywords: 
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 06/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2f6c06bf-e29a-4715-937b-1d2c7cf663d4
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 248dcc978b5324733d5d640230aba2b6db1a2c62
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2018
---
# <a name="how-to-assign-apps-to-android-for-work-devices-with-intune"></a>Intune으로 Android for Work 장치에 앱을 할당하는 방법

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

표준 Android 장치에 할당하던 방식과 다른 방법으로 Android for Work 장치에 앱을 할당합니다. Android for Work에 대해 설치하는 모든 앱은 Google Play for Work 스토어에서 받습니다. 스토어에 로그온하여 원하는 앱을 찾아본 다음 승인합니다.
그러면 앱이 Azure Portal의 **사용이 허가된 앱** 노드에 나타납니다. 여기에서 다른 앱을 할당하는 방식과 동일하게 앱 할당을 관리할 수 있습니다.

또한 고유한 LOB(기간 업무) 앱을 만든 경우 다음과 같이 할당할 수 있습니다.
- Google Play 스토어의 개인 영역에 앱을 게시할 수 있는 Google 개발자 계정에 등록합니다.
- Intune과 앱을 동기화합니다.

## <a name="before-you-start"></a>시작하기 전에

Intune과 Android for Work가 Azure Portal의 **장치 등록** 워크로드에서 함께 작업할 수 있도록 구성했는지 확인합니다.

## <a name="synchronize-an-app-from-the-google-play-for-work-store"></a>Google Play for Work 스토어에서 앱 동기화

1. [Google Play for Work 스토어](https://play.google.com/work)로 이동합니다. Intune과 Android for Work 간 연결을 구성하는 데 사용한 동일한 계정으로 로그인합니다.
2. Intune을 사용하여 할당할 앱에 대한 스토어를 검색합니다.
3. 선택한 앱 페이지에서 **승인**을 선택합니다. 이 예제에서는 Microsoft Excel 앱을 선택했습니다.<br>
  ![앱 승인 예제](media/approve.png)
4. 앱 창이 열리면서 앱에서 다양한 작업을 수행할 수 있는 권한을 부여하라는 메시지가 표시됩니다. 계속하려면 **승인**을 선택합니다.<br>
  ![앱 사용 권한 승인 예제](media/approve-app-permissions.png)
5. 앱이 승인되어 IT 관리자 콘솔에 표시됩니다.

## <a name="publish-then-synchronize-a-line-of-business-app-from-the-google-play-for-work-store"></a>Google Play for Work 스토어에서 기간 업무 앱 게시 후 동기화

1. Google Play Developer 콘솔 [play.google.com/apps/publish](https://play.google.com/apps/publish)로 이동합니다.
2. Intune과 Android for Work 간 연결을 구성하는 데 사용한 동일한 계정으로 로그인합니다. 처음으로 로그인하는 경우 Google Developer 프로그램 구성원이 되도록 등록하고 요금을 지불해야 합니다.
3. 콘솔에서 **새 응용 프로그램 추가**를 선택합니다.
4. Google Play 스토어에 앱을 게시한 것과 동일한 방법으로 앱에 대한 정보를 업로드하고 제공합니다. 단, **이 응용 프로그램을 내 조직만 사용(<*조직 이름*>)** 설정을 선택해야 합니다.<br>
  ![내 조직에서만 앱 사용 가능 옵션](media/restrict.png)<br>
이 작업을 수행하면 앱은 해당 조직에서만 사용할 수 있고 공개 Google Play 스토어에서 사용할 수 없게 됩니다.
Android 앱 업로드 및 게시하는 방법에 대한 자세한 내용은 [Google Developer Console Help](https://support.google.com/googleplay/android-developer/answer/113469)(Google Developer 콘솔 도움말)를 참조하세요.
5. 앱을 게시한 후에는 [Google Play for Work 스토어](https://play.google.com/work)로 이동합니다. Intune과 Android for Work 간 연결을 구성하는 데 사용한 동일한 계정으로 로그인합니다.
6. 스토어의 **앱** 노드에서 게시한 앱을 볼 수 있는지 확인합니다. 앱이 Intune와 동기화되도록 자동으로 승인됩니다.

## <a name="assign-an-android-for-work-app"></a>Android for Work 앱 할당

스토어에서 앱을 승인했지만 **모바일 앱** 워크로드의 **사용이 허가된 앱** 노드에 표시되지 않으면 다음과 같이 강제로 즉시 동기화합니다.

1. Azure 포털에 로그인합니다.
2. **Intune** 블레이드에서 **Mobile Apps**를 선택합니다.
3. **모바일 앱** 워크로드에서 **설정** > **Android for Work**를 선택합니다.
4. Android for Work 블레이드에서 **지금 동기화**를 선택합니다.
5. 페이지에 마지막 동기화의 시간 및 상태도 표시됩니다.

앱이 **모바일 앱** 워크로드의 **사용이 허가된 앱** 노드에 표시되면 [다른 앱을 할당하는 것과 마찬가지 방법으로 할당](/intune-azure/manage-apps/deploy-apps)할 수 있습니다. 앱은 사용자의 그룹에만 할당할 수 있습니다.

앱을 할당하고 나면 대상으로 지정한 장치에 설치됩니다. 장치 사용자에게 설치 승인을 요청하지 않습니다.

## <a name="manage-android-for-work-app-permissions"></a>Android for Work 앱 권한 관리
Android for Work를 사용하려면 관리되는 Google Play 웹 콘솔에서 앱을 승인한 후 Intune에 동기화하고 사용자에게 할당해야 합니다.  Android for Work를 사용하여 이러한 앱을 사용자의 장치에 자동으로 푸시할 수 있으므로 모든 사용자를 대신해 앱 권한을 허용해야 합니다.  최종 사용자가 앱을 설치할 때는 앱 권한이 표시되지 않으므로 이러한 권한을 읽고 이해해야 합니다.

앱 개발자가 권한이 업데이트된 새 버전의 앱을 게시한 경우 이러한 권한은 자동으로 허용되지 않으며, 이는 이전 권한을 승인한 경우에도 마찬가지입니다. 이전 버전의 앱을 실행하는 장치는 해당 앱을 계속 사용할 수 있습니다. 그러나 새 권한을 승인할 때까지는 앱이 업그레이드되지 않습니다. 앱이 설치되지 않은 장치는 앱의 새 권한을 승인할 때까지 앱을 설치하지 않습니다.

### <a name="how-to-update-app-permissions"></a>앱 권한을 업데이트하는 방법

관리되는 Google Play 콘솔을 주기적으로 방문하여 새 권한을 확인합니다. 승인된 앱에 대해 새 권한이 필요할 때 자신이나 다른 사용자에게 전자 메일을 전송하도록 Google Play를 구성할 수 있습니다. 앱을 할당할 때 장치에 설치되지 않은 것을 발견한 경우 다음 단계에 따라 새 권한을 확인하세요.

1. http://play.google.com/work를 방문합니다.
2. 앱을 게시하고 승인하는 데 사용한 Google 계정으로 로그인합니다.
3. **업데이트** 탭을 방문하여 업데이트가 필요한 앱이 있는지 확인합니다.  나열된 모든 앱은 새 권한이 필요하므로 새 권한이 적용될 때까지 할당되지 않습니다.  

앱별로 앱 권한을 자동으로 다시 승인하도록 Google Play를 구성할 수도 있습니다. 



