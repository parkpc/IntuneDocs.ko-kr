---
title: Intune에서 Windows 장치 제거 | Microsoft Docs
description: Intune에서 Windows 장치를 제거하는 방법 설명
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 03/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 018bda65-7238-41f5-b92a-e5f67b7fe085
searchScope:
- User help
ROBOTS: ''
ms.reviewer: jieyang
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 9f9051fb393c82031d581f7fec731a3b148cbf2e
ms.sourcegitcommit: 7f46e9990797bdfa669ccba2077721f1bc70c07e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/04/2018
---
# <a name="remove-your-windows-device-from-intune"></a>Intune에서 Windows 장치 제거

장치가 Intune에 등록되어 있지만 회사나 학교 이메일, 앱 또는 기타 리소스에 액세스하기 위해 더 이상 Windows 장치를 사용하려 하지 않는 경우 관리에서 장치를 제거해야 합니다. Intune에서 장치를 제거하면 이러한 리소스에 더 이상 액세스할 수 없습니다. 관리에서 장치를 제거할 때 발생하는 상황에 대한 자세한 내용은 [Intune에서 장치 등록을 취소하면 어떻게 되나요?](what-happens-if-you-unenroll-your-device-from-intune-windows.md)를 참조하세요.

## <a name="remove-your-windows-10-device"></a>Windows 10 장치 제거

1.  앱 목록에서 **회사 포털** 앱을 탭합니다.

2.  회사 또는 학교 자격 증명을 사용하여 로그인합니다.

3.  **내 장치**에서 등록을 취소할 장치를 선택합니다.

4.  **제거** &gt; **제거**를 탭합니다.

## <a name="remove-your-windows-81-computer"></a>Windows 8.1 컴퓨터 제거

1.  **PC 설정** &gt; **네트워크** &gt; **작업 공간**으로 이동합니다.

2.  **작업 공간 연결**에서 **나가기**를 선택합니다.

3.  **장치 관리 설정**에서 **끄기**를 선택합니다.

4.  팝업 창이 열리면 **해제**를 선택합니다.

## <a name="remove-your-windows-phone-81-mobile-device"></a>Windows Phone 8.1 모바일 장치 제거

1.  **설정** &gt; **작업 공간**으로 이동합니다.

2.  등록을 취소할 작업 공간 계정을 탭합니다.

3.  화면 맨 아래에서 **삭제**를 탭합니다.

4.  **계정 삭제** 대화 상자에서 **삭제**를 탭합니다.

## <a name="removing-your-personal-information-after-removing-the-company-portal"></a>회사 포털을 제거한 후 개인 정보 제거

회사 포털이 Windows 장치에 저장하는 두 종류의 데이터가 있습니다.

-   **진단 로그**: 회사 포털에서 장치를 제거하는 경우 앱이 얼마나 오래 열려 있었는지 또는 크래시되었는지 등 Microsoft에서 수집하는 표준 앱 활동 데이터가 자동으로 지워집니다.
-   **응용 프로그램 캐시**: 아이콘 및 설정 같이 앱이 작동하는 데 필요한 지원 파일을 저장합니다.

이 정보를 완전히 삭제하려면 수행해야 할 몇 가지 단계가 있습니다.

### <a name="uninstall-the-company-portal"></a>회사 포털 제거  

[회사 포털 앱 제거](https://support.microsoft.com/help/4028003/windows-10-uninstall-apps-and-programs)는 장치에 저장된 앱 데이터의 일부를 제거합니다.  

### <a name="reset-the-company-portal"></a>회사 포털 다시 설정

설정에서 앱을 다시 설정하여 회사 포털 앱 데이터의 나머지 부분을 다시 설정할 수 있습니다. **설정** > **앱 및 기능** > **회사 포털** > **고급 옵션** > **재설정**을 엽니다.

여전히 도움이 필요하세요? 회사 지원 부서에 문의하세요. 연락처 정보는 [회사 포털 웹 사이트](https://portal.manage.microsoft.com#HelpDeskDialog)를 참조하세요.