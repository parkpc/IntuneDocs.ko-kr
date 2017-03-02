---
title: "Samsung KNOX에 대한 앱 허용/차단 Intune 정책 | Intune Azure 미리 보기 | Microsoft Docs"
description: "Intune Azure 미리 보기: Samsung KNOX Standard 장치에 대해 앱을 허용하거나 차단하는 사용자 지정 프로필을 만듭니다."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d035ebf5-85f4-4001-a249-75d24325061a
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: f5267d2e06f1cd7ec471fd1782bfd965843d1c7e
ms.lasthandoff: 02/16/2017



---
# <a name="use-custom-policies-to-allow-and-block-apps-for-samsung-knox-standard-devices-in-microsoft-intune"></a>Microsoft Intune에서 사용자 지정 정책을 사용하여 Samsung KNOX Standard 장치에 대해 앱 허용 및 차단
[!INCLUDE[azure_preview](../includes/azure_preview.md)] 이 항목의 절차를 사용하여 다음 중 하나를 만들 수 있는 Microsoft Intune 사용자 지정 정책을 만듭니다.

- 장치에서 실행이 차단된 앱 목록입니다. 이 목록에 있는 앱은 정책을 적용했을 때 이미 설치되어 있었더라도 실행이 차단됩니다.
- 장치 사용자가 Google Play 스토어에서 설치할 수 있도록 허용된 앱 목록. 나열된 앱만 설치할 수 있습니다. 다른 앱은 스토어에서 설치할 수 없습니다.

이러한 설정은 삼성 KNOX Standard를 실행하는 장치에서만 사용할 수 있습니다.

## <a name="create-an-allowed-or-blocked-app-list"></a>허용되거나 차단된 앱 목록 만들기

1. Azure 포털에 로그인합니다.
2. **추가 서비스** > **기타** > **Intune**을 선택합니다.
3. **Intune** 블레이드에서 **장치 구성**을 선택합니다.
2. **장치 구성** 블레이드에서 **관리** > **프로필**을 선택합니다.
2. 프로필 목록 블레이드에서 **프로필 만들기**를 선택합니다.
3. **프로필 만들기** 블레이드에서 이 장치 프로필에 대한 **이름** 및 선택적 **설명**을 입력합니다.
2. **플랫폼 유형**에서 **Android**를 선택하고 프로필 유형에서 **사용자 지정**을 선택합니다.
3. **설정**을 클릭합니다.
3. **사용자 지정 OMA-URI 설정** 블레이드에서 **추가**를 선택합니다.
4. **OMA URI 설정 추가 또는 편집** 대화 상자에서 다음을 지정합니다.

### <a name="for-a-list-of-apps-that-are-blocked-from-running-on-the-device"></a>장치에서 실행이 차단된 앱 목록의 경우

- **이름** - **PreventStartPackages**를 입력합니다.
- **설명** - ‘실행이 차단된 앱 목록’과 같이 설명을 선택적으로 입력합니다.
-     **데이터 형식** - 드롭다운 목록에서 **문자열**을 선택합니다.
-     **OMA-URI** - **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/PreventStartPackages**를 입력합니다.
-     **값** - 허용할 앱 패키지 이름 목록을 입력합니다. 구분 기호로 **;:,** 또는 **|**를 사용할 수 있습니다. (예: package1, package2;)

### <a name="for-a-list-of-apps-that-users-are-allowed-to-install-from-the-google-play-store-while-excluding-all-other-apps"></a>사용자가 다른 앱을 모두 제외하는 반면 Google Play 스토어에서 설치할 수 있도록 허용된 앱 목록의 경우
- **이름** - **AllowInstallPackages**를 입력합니다.
- **설명** - ‘사용자가 Google Play 스토어에서 설치할 수 있는 앱 목록’과 같이 설명을 선택적으로 입력합니다.
- **데이터 형식** - 드롭다운 목록에서 **문자열**을 선택합니다.
- **OMA-URI** - **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/AllowInstallPackages**를 입력합니다.
- **값** - 허용할 앱 패키지 이름 목록을 입력합니다. 구분 기호로 **;:,** 또는 **|**를 사용할 수 있습니다. (예: package1, package2;)

4. **확인**을 클릭한 다음 **프로필 만들기** 블레이드에서 **만들기**를 선택합니다.

>[!TIP]
> Google Play 스토어에서 앱을 탐색하여 앱의 패키지 ID를 찾을 수 있습니다. 패키지 ID는 앱 페이지의 URL에 포함되어 있습니다. 예를 들어 Microsoft Word 앱의 패키지 ID는 **com.microsoft.office.word**입니다.

다음에 대상이 지정된 각 장치가 체크인되면 앱 설정이 적용됩니다.


<!---## Assign the custom profile--->

