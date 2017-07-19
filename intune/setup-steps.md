---
title: "Intune 설정"
description: "Intune 구독 사용을 시작하기 위한 요구 사항 및 필수 구성 요소"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/05/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d158503c-1276-422b-ab81-5f66c1cd7e7a
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 966183f0da7a48148a193a1823f74b9e416f4004
ms.sourcegitcommit: bee30f4c9e04129d70305fcafc4152c6e062a8b0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2017
---
# <a name="set-up-intune"></a>Intune 설정

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

설정 단계에서는 모바일 장치 관리용 환경을 준비합니다.  

현재 Microsoft System Center Configuration Manager를 사용하여 컴퓨터와 서버를 관리하는 경우에는 [Configuration Manager를 확장하여 모바일 장치를 관리](https://docs.microsoft.com/sccm/mdm/understand/choose-between-standalone-intune-and-hybrid-mobile-device-management)할 수 있습니다.

>[!TIP]
>적격 플랜을 통해 Intune에 대한 라이선스를 150개 이상 구매하는 경우 *FastTrack 센터 혜택*을 사용할 수 있습니다. 이 서비스를 통해 Microsoft 전문가는 사용자와 협력하여 Intune에 맞게 사용자 환경을 준비합니다. [EMS(Enterprise Mobility + Security)에 대한 FastTrack 센터 혜택](https://docs.microsoft.com/enterprise-mobility-security/Solutions/enterprise-mobility-fasttrack-program)을 참조하세요.

| 단계 | 상태  |
| ------------- |-------------|
| 1  | [필수 조건](supported-devices-browsers.md) - 시작하기 전에 정보를 알고 있어야 합니다.|
| 2 |  [Intune에 로그인](account-sign-up.md) - 평가판 구독에 로그인하거나 새 구독을 만듭니다. |  
| 3 | [도메인 이름 구성](custom-domain-name-configure.md) - DNS 등록을 설정하여 회사의 도메인 이름을 Intune과 연결합니다.  |
| 4 | [사용자 추가](users-add.md) - 수동으로 사용자를 추가하거나 Active Directory를 연결하여 사용자를 Intune과 동기화합니다.  |
| 5 | [라이선스 할당](licenses-assign.md) - 사용자에게 Intune 사용 권한을 부여합니다.|
| 6 |  [그룹 추가](groups-add.md) - 사용자 및 장치 그룹을 사용하여 관리 작업을 단순화합니다. |
| 7 | [앱 추가](apps-add.md) - 사용자에게 배포할 수 있는 설정 및 앱을 사용하도록 설정합니다. |
| 8 | [장치 구성](device-profiles.md) - 장치 및 회사 리소스에 대한 액세스를 관리하는 프로필을 설정합니다. |
| 9 | [회사 포털 사용자 지정](company-portal-app.md) - Intune 회사 포털을 사용자 지정합니다.   |
| 10 | [장치 등록 사용](mdm-authority-set.md) - iOS, Windows, Android 및 Mac 장치의 Intune 관리를 사용하도록 설정합니다. |
