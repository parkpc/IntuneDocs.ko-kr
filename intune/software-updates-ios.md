---
title: "Microsoft Intune에서 iOS 업데이트 정책 구성"
titlesuffix: 
description: "감독된 iOS 장치에서 사용 가능한 최신 소프트웨어 업데이트를 강제로 자동 설치하기 위한 iOS의 업데이트 정책을 구성합니다."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.openlocfilehash: 6ba354fb3b39544f09363651abfd9e1a5c0f6154
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/08/2018
---
# <a name="configure-ios-update-policies-in-microsoft-intune"></a>Microsoft Intune에서 iOS 업데이트 정책 구성
감독된 iOS 장치에서 사용 가능한 최신 소프트웨어 업데이트를 강제로 자동 설치할 수 있는 iOS의 업데이트 정책입니다. 장치에서 업데이트를 설치하지 않게 할 날짜와 시간을 구성하는 옵션이 있습니다.

## <a name="configure-the-ios-update-policy"></a>iOS 업데이트 정책 구성
1. 로그인은 [Azure 포털](https://portal.azure.com)합니다.
2. **모든 서비스** > **Intune**을 선택합니다. Intune은 **모니터링 + 관리** 섹션에 있습니다.
2. **Intune** 창에서 **소프트웨어 업데이트** > **iOS 업데이트 정책**을 선택합니다.
4. 정책 창에서 **만들기**를 선택한 다음, 정책의 이름과 설명을 입력합니다.
5. **설정** > **구성**을 차례로 선택하고, iOS 장치에서 최신 업데이트를 강제로 설치하지 않는 경우에 대한 세부 정보를 입력합니다.
6. **확인**을 선택하여 이 구성을 저장합니다. 이제 **업데이트 정책 만들기** 창으로 다시 전환됩니다. **만들기**를 클릭하여 정책을 만들고 설정을 저장합니다.

프로필이 생성되어 iOS 업데이트 정책 목록 창에 표시됩니다.

## <a name="assign-an-ios-update-policy-to-users"></a>사용자에게 iOS 업데이트 정책 할당
iOS 업데이트 정책을 사용자에게 할당하려면 구성된 정책을 선택합니다. **소프트웨어 업데이트** > **iOS 업데이트 정책** 창에 기존 정책이 있습니다.
1. 사용자에게 할당할 정책을 선택한 다음 **할당**을 선택합니다. Azure Active Directory 보안 그룹을 선택하고 정책에 할당할 수 있는 창이 열립니다.
2. **선택된 그룹**을 선택하여 Azure AD 보안 그룹을 표시하는 창을 엽니다.
3. **저장**을 선택하여 사용자에게 정책을 배포합니다.

사용자에게 정책을 적용했습니다. 정책의 대상이 되는 사용자가 사용하는 장치에 대한 업데이트 준수 여부가 평가됩니다.

## <a name="change-the-restricted-days-for-the-policy"></a>정책의 제한된 날짜 변경
1. **소프트웨어 업데이트** 창에서 **iOS 업데이트 정책**을 선택합니다.
2. 업데이트할 iOS 업데이트 정책을 선택합니다.
3. **속성** > **설정**을 선택하여 제한된 날짜 정보를 업데이트합니다.

## <a name="monitor-ios-devices-with-older-ios-versions"></a>이전 iOS 버전으로 iOS 장치 모니터링
<!-- 1352223 -->
**오래된 iOS 장치** 보고서는 **소프트웨어 업데이트** > **iOS 업데이트 정책** 창에서 사용할 수 있습니다. 보고서에는 iOS 업데이트 정책의 대상이었고 업데이트할 수 없었던 감독된 iOS 장치의 목록이 표시됩니다. 장치가 자동으로 업데이트되지 않은 이유를 나타내는 각 장치의 상태를 볼 수 있습니다.
