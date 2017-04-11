---
title: "Intune 교육 설정 구성"
titleSuffix: Intune Azure preview
description: "Intune Azure 미리 보기: 관리하는 장치에서 교육 설정을 구성하도록 Intune을 사용하는 방법을 알아봅니다."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f4de4bd-3dde-4a8d-8e22-46c5d06c3eea
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: ca4f1adc5704ecd66d2af7823f95ca63ec20469e
ms.openlocfilehash: 5c73719c4fd2805f91c6af3ba48c39f5d798aaeb
ms.lasthandoff: 03/17/2017


---

# <a name="how-to-configure-education-settings-in-microsoft-intune"></a>Microsoft Intune에서 교육 설정을 구성하는 방법

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

교육 프로필을 사용하면 계정 세부 정보 및 테스트 URL을 포함하여 Windows 시험 응시(Windows Take a Test) 앱을 구성하는 세부 정보를 지정할 수 있습니다. 이 설정을 구성할 경우 지정한 테스트와 함께 시험 응시(Take a Test) 앱이 열립니다. 테스트가 완료될 때까지 장치에서 다른 앱을 실행할 수 없습니다.

이 항목의 정보를 사용하여 장치 제한 프로필 구성에 대한 기본 사항을 알아본 다음 각 플랫폼에 대한 추가 항목을 통해 장치에 특정한 정보를 확인할 수 있습니다.

## <a name="create-a-device-profile-containing-education-profile-settings"></a>교육 프로필 설정을 포함하는 장치 프로필 만들기

1. Azure 포털에 로그인합니다.
2. **추가 서비스** > **기타** > **Intune**을 선택합니다.
3. **Intune** 블레이드에서 **장치 구성**을 선택합니다.
2. **장치 구성** 블레이드에서 **관리** > **프로필**을 선택합니다.
3. 프로필 블레이드에서 **프로필 만들기**를 선택합니다.
4. **프로필 만들기** 블레이드에서 장치 제한 프로필에 대한 **이름** 및 **설명**을 입력합니다.
5. **플랫폼** 드롭다운 목록에서 **Windows 10 이상**을 선택합니다.
6. **프로필 유형** 드롭다운 목록에서 선택 **교육 프로필**을 선택합니다. 
7. 설정 > 구성을 선택한 다음 **시험 응시** 블레이드에서 다음을 구성합니다.
    - **계정 사용자 이름** - 시험 응시에 사용한 계정의 사용자 이름을 입력합니다. 이름은 도메인 계정, AAD(Azure Active Directory) 계정 또는 로컬 컴퓨터 계정일 수 있습니다.
    - **평가 URL** - 사용자가 수행해야 할 테스트의 URL을 제공합니다. 자세한 내용은 시험 응시 설명서를 참조하세요.
    - **화면 모니터링** - 사용자가 테스트를 수행하는 동안 화면 활동을 모니터링할 수 있는지 여부를 지정합니다.
    - **텍스트 제안** - 사용자가 테스트를 수행하는 동안 텍스트 제안을 허용하거나 차단합니다.
8. 완료되면 **프로필 만들기** 블레이드로 돌아가서 **만들기**를 누릅니다.

프로필이 만들어지고 프로필 목록 블레이드에 표시됩니다.
계속해서 이 프로필을 그룹에 할당하려면 [장치 프로필을 할당하는 방법](how-to-assign-device-profiles.md)을 참조하세요.




