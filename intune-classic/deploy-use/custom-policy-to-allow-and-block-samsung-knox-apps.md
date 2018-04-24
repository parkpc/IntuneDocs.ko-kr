---
title: KNOX에 대해 허용된 앱 및 차단된 앱
description: KNOX에 대해 허용되거나 차단되는 앱 목록을 만들 수 있도록 프로필을 사용자 지정합니다.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 11/02/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: bbc8e0df-7bf3-494e-8bc4-dac59a98ab41
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 22018a241664a02aa99b9a3b1a53aa559ab42db5
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="use-custom-policies-to-allow-and-block-apps-for-samsung-knox-standard-devices"></a>사용자 지정 정책을 사용하여 Samsung KNOX Standard 장치에 대해 앱을 허용하거나 차단

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

이 항목의 절차를 사용하여 다음 중 하나를 만들 수 있는 Microsoft Intune 사용자 지정 정책을 만듭니다.

- 장치에서 실행되지 않도록 차단할 앱 목록. 이 목록에 있는 앱은 정책을 적용했을 때 이미 설치되어 있었더라도 실행이 차단됩니다.
- 장치 사용자가 Google Play 스토어에서 설치할 수 있도록 허용된 앱 목록. 나열된 앱만 설치할 수 있습니다. 다른 앱은 스토어에서 설치할 수 없습니다.

이러한 설정은 Samsung KNOX Standard를 실행하는 장치에서만 사용할 수 있습니다.

## <a name="to-create-an-allowed-or-blocked-app-list"></a>허용되거나 차단된 앱 목록을 만들려면

1. [Microsoft Intune 관리 콘솔](https://manage.microsoft.com/)에서 **정책** &gt; **구성 정책** &gt; **추가**를 선택합니다.
2. **새 정책 만들기** 대화 상자에서 **Android**를 확장하고 **사용자 지정 구성** 선택한 다음 **정책 만들기**를 선택합니다.
3. 정책에 대한 다음 이름 및 선택적 설명을 제공한 다음 **OMA-URI 설정** 섹션에서 **추가**를 선택합니다.
4. **OMA URI 설정 추가 또는 편집** 대화 상자에서 다음을 지정합니다. 장치에서 실행이 차단된 앱 목록의 경우
    
   - **설정 이름.** **PreventStartPackages**를 입력합니다.
   - **설정 설명.** ‘실행이 차단된 앱 목록’과 같이 설명을 선택적으로 입력합니다.
   - **데이터 형식.** 드롭다운 목록에서 **문자열**을 선택합니다.
   - **OMA-URI.** **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/PreventStartPackages**를 입력합니다.
   - **값.** 차단할 앱 패키지 이름 목록을 입력합니다. 구분 기호로 **;:,** 또는 **|** 를 사용할 수 있습니다. (예: package1, package2;)

     사용자가 다른 앱을 모두 제외하는 반면 Google Play 스토어에서 설치할 수 있도록 허용된 앱 목록의 경우

   - **설정 이름.** **AllowInstallPackages**를 입력합니다.
   - **설정 설명.** ‘사용자가 Google Play 스토어에서 설치할 수 있는 앱 목록’과 같이 설명을 선택적으로 입력합니다.
   - **데이터 형식.** 드롭다운 목록에서 **문자열**을 선택합니다.
   - **OMA-URI.** **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/AllowInstallPackages**를 입력합니다.
   - **값.** 허용할 앱 패키지 이름 목록을 입력합니다. 구분 기호로 **;:,** 또는 **|** 를 사용할 수 있습니다. (예: package1, package2;)

5. **확인**을 클릭한 다음 **정책 저장**을 클릭합니다. 

>[!TIP]
> Google Play 스토어에서 앱을 탐색하여 앱의 패키지 ID를 찾을 수 있습니다. 패키지 ID는 앱 페이지의 URL에 포함되어 있습니다. 예를 들어 Microsoft Word 앱의 패키지 ID는 **com.microsoft.office.word**입니다.

다음에 대상이 지정된 각 장치가 체크인되면 앱 설정이 적용됩니다.


## <a name="deploy-the-policy"></a>정책 배포

1.  **정책** 작업 영역에서 배포할 정책을 선택하고 **배포 관리**를 클릭합니다.

2.  **배포 관리** 대화 상자에서 정책을 배포하려는 그룹을 하나 이상 선택하고 **추가** &gt; **확인**을 클릭합니다.

 
배포한 정책을 선택하면 정책 목록 아래쪽에서 배포에 대한 추가 정보를 볼 수 있습니다.

### <a name="see-also"></a>참고 항목
[Microsoft Intune의 Android 및 Samsung KNOX 정책 설정](android-policy-settings-in-microsoft-intune.md)
