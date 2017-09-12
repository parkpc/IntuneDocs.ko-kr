---
title: "iOS 업데이트 정책 구성"
titlesuffix: Azure portal
description: "감독된 iOS 장치에서 사용 가능한 최신 소프트웨어 업데이트를 강제로 자동 설치하기 위한 iOS의 업데이트 정책을 구성합니다."
keywords: 
author: dougeby
manager: dougeby
ms.date: 08/02/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e6334421-85e1-4457-9c44-e5db8d4ee00e
ms.openlocfilehash: a119f00cc8a92aa6cf7a1009f910df817593e0e8
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/09/2017
---
# <a name="configure-ios-update-policies"></a>iOS 업데이트 정책 구성
감독된 iOS 장치에서 사용 가능한 최신 소프트웨어 업데이트를 강제로 자동 설치할 수 있는 iOS의 업데이트 정책입니다. 장치에서 업데이트를 설치하지 않게 할 날짜와 시간을 구성하는 옵션이 있습니다.

## <a name="configure-the-ios-update-policy"></a>iOS 업데이트 정책 구성
1. Azure 포털에서 Intune 블레이드로 이동합니다.
2. **Intune** 블레이드에서 **소프트웨어 업데이트** > **iOS 업데이트 정책**을 선택합니다.
4. 정책 블레이드에서 **만들기**를 선택한 다음 정책의 이름과 설명을 입력합니다.
5. **설정** > **구성**을 선택하고 iOS 장치가 강제로 최신 업데이트를 설치하지 않는 경우에 대한 세부 정보를 입력합니다.
6. **확인**을 선택하여 이 구성을 저장합니다. 이제 **업데이트 정책 만들기** 블레이드로 돌아갑니다. **만들기**를 클릭하여 정책을 만들고 설정을 저장합니다.

프로필이 생성되어 iOS 업데이트 정책 목록 블레이드에 표시됩니다.

## <a name="assign-an-ios-update-policy-to-users"></a>사용자에게 iOS 업데이트 정책 할당
iOS 업데이트 정책을 사용자에게 할당하려면 구성된 정책을 선택합니다. **소프트웨어 업데이트** > **iOS 업데이트 정책** 블레이드에 기존 정책이 있습니다.
1. 사용자에게 할당할 정책을 선택한 다음 **할당**을 선택합니다. Azure Active Directory 보안 그룹을 선택하고 정책에 할당할 수 있는 블레이드가 열립니다.
2. **그룹 선택**을 선택하여 Azure AD 보안 그룹을 표시하는 블레이드를 엽니다. **선택**을 선택하여 사용자에게 정책을 배포합니다.

사용자에게 정책을 적용했습니다. 정책의 대상 사용자가 사용하는 장치에 대해 업데이트 준수 여부가 평가됩니다.

## <a name="change-the-restricted-days-for-the-policy"></a>정책의 제한된 날짜 변경
1. **소프트웨어 업데이트** 블레이드에서 **iOS 업데이트 정책**을 선택합니다.
2. 업데이트할 iOS 업데이트 정책을 선택합니다.
3. **속성**을 선택하고 제한된 날짜 정보를 업데이트합니다.
