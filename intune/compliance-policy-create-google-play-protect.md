---
title: "Intune에서 Google Play 보호 준수 사용"
titleSuffix: Azure portal
description: "Google Play 보호를 사용하도록 설정하기 위해 Android 장치에 대한 준수 정책을 만드는 방법을 알아봅니다."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: E9810BEB-000A-4DFB-B5C7-A22A92082B22
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 13aa627515b74d3c9fe6d091c44dd5147bd786bd
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2018
---
# <a name="how-to-create-a-device-compliance-policy-to-enable-google-play-protect"></a>Google Play 보호를 사용하도록 설정하기 위해 장치 준수 정책을 만드는 방법

GPP(Google Play 보호) 준수를 확인하기 위해 Android 플랫폼에 대한 새로운 준수 정책을 만들 수 있습니다.

이러한 설정이 필요한 준수 정책은 Android 사용자 또는 장치 그룹을 대상으로 할 수 있습니다. 장치에 이러한 설정이 사용하도록 설정되어 있지 않은 경우 해당 장치는 준수하지 않는 것입니다.

## <a name="create-a-compliance-policy"></a>규정 준수 정책 만들기

1. Azure Portal에 로그인합니다. **추가 서비스** > **모니터링 + 관리** + **Intune**을 선택합니다.
2. **관리** 그룹에서 **장치 준수**를 선택합니다. 
3. **정책**을 선택하고 **정책 만들기**를 선택합니다.
4. 정책 **이름** 및 **설명**을 입력합니다.
5. 플랫폼으로 **Android**를 선택합니다.
6. **설정** > **장치 상태**를 선택합니다.
7. **Google Play 보호** 설정을 구성합니다.
8. Google Play 보호 설정을 지정했으면 **보안** 및 **장치 속성** 설정을 지정합니다. 작업이 끝나면 **확인**을 선택합니다.

## <a name="configure-the-google-play-protect-settings"></a>Google Play 보호 설정 구성

 - **Google Play 서비스가 구성되었습니다.**  
   Google Play 서비스 앱을 설치하고 사용하도록 설정해야 합니다. Google Play 서비스는 보안 업데이트를 허용하며, 인증된 Google 장치의 많은 보안 기능에 대한 기본 수준 종속성입니다.
 - **최신 보안 공급자**  
   최신 보안 공급자가 알려진 취약성으로부터 장치를 보호할 수 있도록 합니다.
 - **앱에서 위협 검색**  
   Android **앱 확인** 기능을 사용하도록 설정해야 합니다.
    > [!Note]  
    > 레거시 Android 플랫폼에서 이 기능은 준수 설정입니다. Intune에서는 장치 수준에서 이 설정이 사용하도록 설정되어 있는지만 확인할 수 있습니다. 회사 프로필(이전의 Android for Work)이 있는 장치에서 이 설정은 구성 정책 설정으로 찾을 수 있습니다. 이를 통해 관리자는 장치에 대한 설정을 사용하도록 설정할 수 있습니다.

    엔터프라이즈에서 Android 회사 프로필을 사용하는 경우 등록된 장치에 대해 **앱에서 위협 검색**을 사용하도록 설정할 수 있습니다. 장치 프로필을 설정하고 시스템 보안 설정이 필요합니다. 자세한 내용은 [Microsoft Intune의 Android for Work 장치 제한 설정](device-restrictions-android-for-work.md)을 참조하세요.

 - **SafetyNet 장치 증명**  
   충족해야 하는 SafetyNet 장치 증명 무결성 수준을 설정합니다. 수준으로는 **구성되지 않음**, **기본 무결성 검사** 및 **기본 무결성 및 인증 장치 검사**가 있습니다.




## <a name="next-steps"></a>다음 단계

Intune 장치 준수 정책 작업에 대한 자세한 내용은 [Intune 장치 준수 정책 시작](device-compliance-get-started.md)을 참조하세요.