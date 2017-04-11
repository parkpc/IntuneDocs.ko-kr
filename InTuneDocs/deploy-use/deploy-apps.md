---
title: "앱 배포 | Microsoft 문서"
description: "이 항목에서는 Intune을 사용하여 앱을 배포하기 전에 이해해야 하는 개념을 설명합니다."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ad5ea85c-aa2e-4110-a184-172cd0b8f270
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: e7d1760a10e63233fe7cc7f6fd57a68c5283647c
ms.openlocfilehash: efa8245020b961797405a6f8b90df7e7b172b4c3


---

# <a name="deploy-apps-with-microsoft-intune"></a>Microsoft Intune을 사용하여 앱 배포

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

이 항목에서는 Microsoft Intune을 사용하여 앱을 배포하기 전에 이해해야 하는 개념을 설명합니다.


## <a name="app-deployment-actions"></a>앱 배포 작업
앱을 배포할 때 다음과 같은 배포 작업 중 하나를 선택할 수 있습니다.

-   **필수 설치** – 사용자 개입 없이 앱이 장치에 설치됩니다.

    > [!TIP]
    > 감독 모드로 설정되지 않은 iOS 장치 및 모든 Android 장치의 경우 사용자가 앱을 허용해야 앱이 설치됩니다.
    >
    >  필수 설치로 배포한 앱을 사용자가 제거하는 경우 Intune은 일반적으로 7일마다 발생하는 다음 인벤토리 주기 이후에 해당 앱을 자동으로 다시 설치합니다.

-   **사용 가능한 설치** – 앱이 회사 포털에 표시되고 사용자가 요청하는 경우 앱을 설치할 수 있습니다.

-   **제거** - 앱이 장치에서 제거됩니다.

-   **해당 사항 없음** – 앱이 회사 포털에 표시되지 않으며 모든 장치에 설치되지 않습니다.

#### <a name="understand-which-deployment-actions-are-available-for-each-installer-type"></a>각 설치 관리자 유형에 사용할 수 있는 배포 작업 이해

|설치 관리자 유형|필수 설치|사용 가능한 설치|제거|해당 없음|
|------------------|--------------------|---------------------|-------------|------------------|
|Windows 앱 패키지(사용자 그룹에 배포)|예|예|예|예|
|Windows 앱 패키지(장치 그룹에 배포)|예|아니요|예|예|
|모바일 장치용 앱 패키지(사용자 그룹에 배포)|예|예|예|예|
|모바일 장치용 앱 패키지(장치 그룹에 배포)|예|아니요|예|예|
|Windows Installer(사용자 그룹에 배포)|아니요|예|아니요|예|
|Windows Installer(장치 그룹에 배포)|예|아니요|예|예|
|외부 링크(사용자 그룹에 배포)|아니요|예|아니요|예|
|외부 링크(장치 그룹에 배포)|아니요|아니요|아니요|아니요|
|앱 스토어에서 관리되는 iOS 앱(사용자 그룹에 배포)|예|예|예|예|
|앱 스토어에서 관리되는 iOS 앱(장치 그룹에 배포)|예|아니요|예|예|
> [!TIP]
> 앱을 배포할 때 사용자 및 장치 그룹을 둘 다 선택하는 경우 앱을 **사용 가능한 설치**로만 배포할 수 있습니다.

## <a name="deployment-conflicts"></a>배포 충돌
배포 작업이 동일한 두 개의 배포가 장치에서 수신되면 다음 규칙이 적용됩니다.

-   장치 그룹에 대한 배포가 사용자 그룹에 대한 배포보다 우선합니다. 그러나 앱이 **사용 가능** 배포 작업으로 사용자 그룹에 배포되고, 동일한 앱이 **해당 없음**배포 작업으로 장치 그룹에도 배포되는 경우 사용자는 회사 포털에서 해당 앱을 설치할 수 있습니다.

-   설치 작업이 제거 작업보다 우선합니다.

-   장치에서 필수 설치와 사용 가능한 설치를 모두 수신하면 두 작업이 결합됩니다. 즉 필수 설치가 시작되기 전에 사용자가 회사 포털에서 앱을 설치할 수 있습니다.


## <a name="next-steps"></a>다음 단계

[Microsoft Intune에서 앱 배포](deploy-apps-in-microsoft-intune.md) 방법을 알아봅니다.



<!--HONumber=Dec16_HO5-->


