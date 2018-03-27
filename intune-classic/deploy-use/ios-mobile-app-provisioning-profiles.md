---
title: 앱 프로비전 프로필
description: Intune은 만료일이 다가오는 앱이 있는 장치에 새 프로비전 프로필 정책을 미리 배포하기 위한 도구를 제공합니다.
keywords: ''
author: mattbriggs
ms.author: mabrigg
manager: dougeby
ms.date: 12/27/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 86fbe736-7bdb-4f5e-ae21-13c91eb2462c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: cadd7070e8e3c7c0c5aca42324635af627f91e14
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2018
---
# <a name="use-ios-mobile-provisioning-profile-policies-to-prevent-your-apps-from-expiring"></a>iOS 프로비전 프로필 정책을 사용하여 모바일 앱이 만료되지 않도록 방지

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

iPhone 및 iPad에 배포된 Apple iOS LOB(기간 업무) 앱은 포함된 프로비전 프로필과 인증서로 서명된 코드로 빌드됩니다. 앱이 실행되면 iOS는 iOS 앱의 무결성을 확인하고 프로비전 프로필에 정의된 정책을 적용합니다. 다음 유효성 검사가 수행됩니다.

- **설치 파일 무결성** - iOS는 엔터프라이즈 서명 인증서의 공개 키와 앱 세부 정보를 비교합니다. 두 내용이 다르면 앱 콘텐츠가 변경되었을 수 있으므로 앱 실행이 허용되지 않습니다.
- **기능 적용** - iOS는 앱 설치(.ipa) 파일에 포함된 엔터프라이즈 프로비전 프로필(개별 개발자 프로비전 프로필이 아님)에서 앱 기능을 적용하려고 합니다.


일반적으로 앱에 서명하기 위해 사용하는 엔터프라이즈 서명 인증서는 3년 동안 유지됩니다. 그러나 프로비전 프로필은 1년 후에 만료됩니다. Intune은 인증서가 여전히 유효한 동안 만료일이 다가오는 앱이 있는 장치에 새 프로비전 프로필 정책을 미리 배포하기 위한 도구를 제공합니다.
인증서가 만료되면 새 인증서로 앱을 다시 서명하고 새 인증서의 키에 새 프로비전 프로필을 포함해야 합니다.



## <a name="how-to-find-out-when-a-line-of-business-app-will-expire"></a>LOB(기간 업무) 앱이 만료되는 시기를 확인하는 방법

1. [Microsoft Intune 관리 콘솔](https://manage.microsoft.com)에서 **앱** > **앱**을 선택합니다.
2. 앱 목록에서 **만료 날짜** 열을 찾아 앱의 만료 날짜를 확인합니다. **필터** 드롭다운 목록을 **만료됨/곧 만료됨**으로 설정하여 사용자의 조치가 필요한 앱만 표시할 수도 있습니다.

## <a name="how-to-create-an-ios-mobile-provisioning-profile-policy"></a>IOS 모바일 프로비전 프로필 정책을 만드는 방법


1. [Microsoft Intune 관리 콘솔](https://manage.microsoft.com)에서 **정책** > **개요** > **정책 추가**를 선택합니다.
2. **새 정책 만들기** 대화 상자에서 **iOS** > **모바일 프로비전 프로필 정책**을 선택한 후 **정책 만들기**를 선택합니다.
3. **일반** 페이지에서 다음 값을 구성합니다.
    - **이름** - 이 모바일 프로비전 프로필 정책의 이름을 제공합니다.
    - **설명** - 필요에 따라 정책에 대한 설명을 제공합니다.
    - **구성 프로필 파일** - **가져오기**를 클릭하고 Apple 개발자 웹 사이트에서 다운로드한 Apple 모바일 구성 프로필 파일(확장명 **.mobileprovision**)을 선택합니다.
4. 작업이 끝나면 **정책 저장**을 선택합니다.
5. 이제 필요한 iOS 장치에 정책을 배포합니다. 자세한 내용은 [Microsoft Intune 정책을 사용하여 장치의 설정 및 기능 관리](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) 항목을 참조하세요.
