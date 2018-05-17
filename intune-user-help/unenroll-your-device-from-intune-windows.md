---
title: Intune에서 Windows 장치 제거
description: Intune에서 Windows 장치를 제거하는 방법 설명
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 05/08/2018
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
ms.openlocfilehash: 1dd64250c1996c6b13c62f80572282d639112ba6
ms.sourcegitcommit: 8ee543c864097dc195b6f440471dca713fc21ed2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/09/2018
---
# <a name="remove-your-windows-device-from-intune-management"></a>Intune 관리에서 Windows 장치 제거

더 이상 다음이 필요하지 않을 경우 Intune에서 등록된 Windows 장치를 제거합니다.  
* 회사 또는 학교용 장치 사용 
* 회사 또는 학교 메일, 앱 또는 기타 리소스에 액세스

제거된 후에는 장치에서 학교 또는 회사 리소스에 액세스할 수 없습니다. Intune에서 제거할 수 있는 Windows 장치는 다음과 같습니다.  
* Windows 10 장치 
* Windows 8.1 컴퓨터
* Windows 8.1 모바일 장치
 
Intune 관리에서 장치를 제거한 후 발생하는 상황에 대한 자세한 내용은 [Intune에서 장치를 제거하면 어떻게 되나요?](what-happens-if-you-unenroll-your-device-from-intune-windows.md)를 참조하세요.

## <a name="remove-your-windows-10-device"></a>Windows 10 장치 제거
Intune에서 Windows 10 장치를 제거하려면 다음 단계를 완료합니다.

### <a name="via-the-company-portal-app"></a>회사 포털 앱을 통해

1. 회사 포털 앱을 엽니다.
2. 회사 또는 학교 자격 증명을 사용하여 로그인합니다.
3. **내 장치**에서 제거할 장치를 선택합니다.
4. 앱 오른쪽 위 모서리에서 **자세히 보기** 아이콘을 선택합니다.
5. **제거**를 선택합니다. 
6. 장치 제거를 확인하려면 **장치 제거**를 선택합니다.

### <a name="via-device-settings-app"></a>장치 설정 앱을 통해
1. 설정 앱을 엽니다. 
2. **계정** > **회사 또는 학교 액세스**를 선택합니다.
3. 제거할 연결된 계정을 선택한 다음, **연결 끊기**를 선택합니다.
4. 장치 제거를 확인하려면 **예**를 선택합니다.

## <a name="remove-your-windows-81-computer"></a>Windows 8.1 컴퓨터 제거
Intune에서 Windows 8.1 컴퓨터를 제거하려면 다음 단계를 완료합니다.

1.  **PC 설정** > **네트워크** > **작업 공간**으로 이동합니다.
2.  **작업 공간 연결**에서 **나가기**를 선택합니다.
3.  **장치 관리 설정**에서 **끄기**를 선택합니다.
4.  팝업 창이 열리면 **해제**를 선택합니다.

## <a name="remove-your-windows-81-mobile-device"></a>Windows 8.1 모바일 장치 제거
Intune에서 Windows 8.1 모바일 장치를 제거하려면 다음 단계를 완료합니다.

1.  **설정** > **작업 공간**으로 이동합니다.
2.  등록을 취소할 작업 공간 계정을 탭합니다.
3.  화면 맨 아래에서 **삭제**를 탭합니다.
4.  **계정 삭제** 대화 상자에서 **삭제**를 탭합니다.  
## <a name="removing-your-personal-information-after-removing-the-company-portal"></a>회사 포털을 제거한 후 개인 정보 제거
회사 포털이 Windows 장치에 저장하는 두 종류의 데이터가 있습니다.

-   **진단 로그**: 회사 포털에서 장치를 제거하는 경우 Microsoft에서 수집하는 표준 앱 활동 데이터가 자동으로 지워집니다. 예를 들어 앱 활동 데이터는 앱이 얼마나 오래 열려 있었는지 또는 작동 중단되었는지에 대한 데이터입니다.
-   **응용 프로그램 캐시**: 아이콘 및 설정과 같이 앱 작동에 필요한 지원 파일입니다.

이 정보를 완전히 삭제하려면 수행해야 할 몇 가지 단계가 있습니다.

1. 회사 포털을 제거합니다. [회사 포털 앱 제거](https://support.microsoft.com/help/4028003/windows-10-uninstall-apps-and-programs)는 장치에 저장된 앱 데이터의 일부를 제거합니다.  

2. 회사 포털을 다시 설정하여 저장된 앱 데이터를 초기화합니다. **설정** 앱을 열고 **앱** > **회사 포털** > **고급 옵션** > **초기화**를 선택합니다. 

여전히 도움이 필요하세요? 회사 지원 부서에 문의하세요. 연락처 정보는 [회사 포털 웹 사이트](https://portal.manage.microsoft.com#HelpDeskDialog)를 참조하세요.