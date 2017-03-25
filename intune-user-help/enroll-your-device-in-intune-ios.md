---
title: "Intune에서 iOS 장치 등록 | Microsoft 문서"
description: "Intune에서 iOS 장치를 등록하는 방법을 설명합니다."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 03/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6eeec7aa-1b07-4ce3-894c-13e09b89bdd4
searchScope:
- User help
ROBOTS: 
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
translationtype: Human Translation
ms.sourcegitcommit: 1ba0dab35e0da6cfe744314a4935221a206fcea7
ms.openlocfilehash: af3313e6ba5cbf9184aaaa9b197f7a3b2b9d4c3e
ms.lasthandoff: 03/13/2017


---


# <a name="enroll-your-ios-device-in-intune"></a>Intune에서 iOS 장치 등록

회사 또는 학교에서 Microsoft Intune을 사용하는 경우 iOS 장치를 등록하여 회사 전자 메일, 파일 및 기타 리소스에 액세스 권한을 얻을 수 있습니다. 장치를 등록하면 IT 부서에서 해당 회사 또는 학교 리소스를 관리하고 보안을 유지하여 선호하는 장치를 자유롭게 사용하여 작업을 완료할 수 있습니다. 등록에 대해 자세히 알아보려면 [Intune에서 회사 포털 앱을 설치하고 장치를 등록하면 어떤 일이 생기나요?](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios.md)

<iframe src="https://channel9.msdn.com/Series/IntuneEnrollment/iOS-Enrollment/player" width="960" height="540" allowFullScreen frameBorder="0"></iframe>

> [!NOTE]
> 실제로 MacBook Pro 또는 iMac 같은 macOS 장치를 등록하려면 [대신 이 지침을 따르세요](enroll-your-device-in-intune-macos.md).

**시작하기 전에:**

- 단계를 시작한 후 등록이 완료되었는지 확인합니다. 몇 분 이상 일시 중지되면 일반적으로 프로세스가 중지되며 다시 시작해야 합니다.
- 어떤 이유로든 등록에 실패하면 회사 포털 앱으로 돌아가 다시 시도해야 합니다.
- Wi-Fi가 작동 중인지 확인합니다. 그렇지 않은 경우 등록이 실패합니다.
- 장치에서 Safari를 차단하는 경우 차단 해제합니다. 등록하려면 Safari를 사용해야 합니다.


**iOS 장치를 등록하려면:**

1.  [Intune 회사 포털 앱 설치 및 로그인](install-and-sign-in-to-the-intune-company-portal-app-ios.md)의 단계를 따르세요.

2. **회사 액세스 설정** 페이지에서 **시작**을 탭합니다.

    ![ios-enroll-comp-access-setup-begin](./media/ios-enroll-1a-comp-access-setup.png)

3. **왜 장치를 등록하나요?** 화면에서 장치를 등록할 때 수행할 수 있는 작업을 확인하고 **계속**을 탭합니다.

    ![ios-enroll-why-enroll](./media/ios-enroll-1b-why-enroll.png)

> [!NOTE]
> 노란색 삼각형은 이미 오류가 발생했음을 의미하지 않습니다. 이 아이콘은 등록 프로세스에서 완료해야 할 단계가 여전히 남아 있음을 나타냅니다.

4. IT 관리자가 등록된 장치에서 볼 수 있는 사항과 볼 수 없는 사항의 목록을 검토하고 **계속**을 탭합니다.

    ![ios-enroll-what-it-can-see](./media/ios-enroll-1c-we-care-privacy.png)

5.  **다음 단계는?** 화면에서 등록하는 동안 발생하는 상황을 확인하고 **등록**을 탭합니다.

     ![ios-enroll-what-comes-next](./media/ios-enroll-1d-what-comes-next.png)

6.  **프로필 설치** 화면에서 **I설치**를 탭하고 메시지가 표시되면 암호를 입력합니다.

    ![ios-enroll-install-profile](./media/ios-enroll-2-mgt-profile-install.png)

7.  **설치**를 탭합니다.

    ![ios-enroll-tap-install](./media/ios-enroll-3-mgt-profile-install-2.png)    

8.  **설치**를 탭하여 경고를 읽었음을 나타냅니다.

       ![ios-enroll-tap-install-after-warning](./media/ios-enroll-4-warning.png)

9.  **신뢰**를 탭합니다.

       ![ios-enroll-tap-trust](./media/ios-enroll-5-trust.png)

10.  프로필 설치를 완료했다고 표시하도록 화면이 변경되면 **완료**를 탭합니다.

     ![ios-enroll-tap-done](./media/ios-enroll-6-done.png)

    화면에는 "등록 장치" 메시지가 표시됩니다.

11.  회사 포털에서 페이지를 열지 묻는 메시지가 표시되는 경우 **열기**를 탭합니다.

    ![ios-enroll-open-comp-portal](./media/ios-enroll-7-open-cp.png)

12. **회사 액세스 설정** 화면에서 **계속**을 탭합니다. IT 관리자가 암호를 설정하는 등 추가 보안 요구 사항을 설정하는 경우 준수 요구 사항을 만족하고 회사 액세스 설정 화면으로 돌아갈 때까지 화면에 나타나는 지침에 따른 다음 **계속**을 탭합니다.

    ![ios-enroll-comp-access-tap-continue](./media/ios-enroll-8-comp-access-setup-compliance.png)

13. **완료**를 탭합니다.

    ![ios-enroll-tap-done](./media/ios-enroll-9-comp-access-setup-complete.png)

이제 Intune에 장치를 등록했으므로 회사 포털 앱으로 다시 이동합니다.

> [!Note]
> 조직에서 TEM(Telecom Expense Management) 소프트웨어를 사용하는 경우 몇 가지 추가 단계를 완료해야 장치가 완전히 등록됩니다. 자세한 내용은 [여기](enroll-your-device-with-telecom-expense-management-ios.md)를 참조하세요.

여전히 도움이 필요하세요? IT 관리자에게 문의하세요. 연락처 정보는 [회사 포털 웹 사이트](http://portal.manage.microsoft.com)를 참조하세요.

