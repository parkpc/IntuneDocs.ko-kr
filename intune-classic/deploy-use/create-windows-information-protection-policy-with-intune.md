---
title: "Intune을 사용하여 WIP(Windows Information Protection) 앱 보호 정책 만들기 및 배포 | Microsoft Docs"
description: "Intune을 사용하여 WIP 앱 보호 정책 만들기 및 배포"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 04/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 51e53e28-5c34-4d0f-a4b1-6390a337514c
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: ce327a54dc5960a3fdceeb54a5016d90fe252d2b
ms.contentlocale: ko-kr
ms.lasthandoff: 05/23/2017


---

# <a name="create-and-deploy-windows-information-protection-wip-app-protection-policy-with-intune"></a>Intune을 사용하여 WIP(Windows Information Protection) 앱 보호 정책 만들기 및 배포

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Intune 1704 릴리스부터는 등록 시나리오를 진행하지 않고도 MAM(모바일 응용 프로그램 관리)을 통해 Windows 10에서 앱 보호 정책을 사용할 수 있습니다.

## <a name="before-you-begin"></a>시작하기 전에

WIP 정책을 추가할 때 적용되는 몇 가지 개념에 대해 살펴보겠습니다.

### <a name="list-of-allowed-and-exempt-apps"></a>허용되는 앱과 예외 앱 목록

-   **허용되는 앱**: 이 정책을 준수해야 하는 앱입니다.

-   **예외 앱**: 이 정책에서 예외로 설정되며 제한 없이 회사 데이터에 액세스할 수 있는 앱입니다.

### <a name="types-of-apps"></a>앱의 유형

-   **권장 앱:** 관리자가 정책으로 쉽게 가져올 수 있도록 미리 채워진 앱(보통 Microsoft Office) 목록입니다.

-   **스토어 앱:** 관리자가 Windows 스토어의 모든 앱을 정책에 추가할 수 있습니다.

-   **Windows 데스크톱 앱:** 관리자가 기존 Windows 데스크톱 앱을 정책에 추가할 수 있습니다(예: exe, dll 등).

## <a name="pre-requisites"></a>필수 구성 요소

WIP 앱 보호 정책을 만들려면 먼저 MAM 공급자를 구성해야 합니다.

-   [Intune을 사용하여 MAM 공급자를 구성하는 방법](/intune-classic/deploy-use/get-ready-to-configure-app-protection-policies-for-windows-10)에 대해 자세히 알아보세요.

다음과 같은 구성 요소도 필요합니다.

-   [Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) 라이선스
-   [Windows 크리에이터 업데이트](https://blogs.windows.com/windowsexperience/2017/04/11/how-to-get-the-windows-10-creators-update/#o61bC2PdrHslHG5J.97)

> [!IMPORTANT]
> WIP에서는 여러 ID를 사용할 수 없으며 한 번에 하나의 관리 ID만 사용할 수 있습니다.

## <a name="to-add-a-wip-policy"></a>WIP 정책을 추가하려면

조직에 Intune을 설치한 후에는 [Azure Portal](/intune-classic/deploy-use/azure-portal-for-microsoft-intune-mam-policies)을 통해 WIP 관련 정책을 만들 수 있습니다.

1.  **Intune 모바일 응용 프로그램 관리 대시보드**로 이동하여 **모든 설정**, **앱 정책**을 차례로 선택합니다.

2.  **앱 정책** 블레이드에서 **정책 추가**를 선택하고 다음 값을 입력합니다.

    a.  **이름:** 새 정책의 이름(필수)을 입력합니다.

    b.  **설명:** 설명(선택 사항)을 입력합니다.

    c.  **플랫폼:** 앱 보호 정책에 지원되는 플랫폼으로 **Windows 10**을 선택합니다.

    d.  **등록 상태:** 정책의 등록 상태로 **등록 없음**을 선택합니다.

3.  **만들기**를 선택합니다. 정책이 만들어져 **앱 정책** 블레이드의 표에 표시됩니다.

## <a name="to-add-recommended-apps-to-your-allowed-apps-list"></a>허용되는 앱 목록에 권장 앱을 추가하려면

1.  **앱 정책** 블레이드에서 정책의 이름을 선택한 다음 **정책 추가** 블레이드에서 **허용되는 앱**을 선택합니다. **허용되는 앱** 블레이드가 열리고 이 앱 보호 정책의 목록에 이미 포함된 모든 앱이 표시됩니다.

2.  **허용되는 앱** 블레이드에서 **앱 추가**를 선택합니다. **앱 추가** 블레이드가 열리고 이 목록에 포함된 모든 앱이 표시됩니다.

3.  회사 데이터에 액세스하려는 각 앱을 선택한 다음 **확인**을 선택합니다. **허용되는 앱** 블레이드가 업데이트되어 선택한 모든 앱이 표시됩니다.

## <a name="add-a-store-app-to-your-allowed-apps-list"></a>허용되는 앱 목록에 스토어 앱 추가

**스토어 앱을 추가하려면**

1.  **앱 정책** 블레이드에서 정책의 이름을 선택한 다음 이 앱 보호 정책의 목록에 이미 포함된 모든 앱이 표시되는 메뉴가 나타나면 **허용되는 앱**을 선택합니다.

2.  **허용되는 앱** 블레이드에서 **앱 추가**를 선택합니다.

3.  **앱 추가** 블레이드의 드롭다운 목록에서 **스토어 앱**을 선택합니다. 블레이드가 변경되어 **게시자** 및 앱 **이름**을 추가할 수 있는 상자가 표시됩니다.

4.  앱의 이름과 해당 게시자의 이름을 입력하고 **확인**을 선택합니다.

    > [!TIP]
    > 예를 들어 앱의 **게시자**는 *CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US*이고 제품 **이름**은 *Microsoft.MicrosoftAppForWindows*일 수 있습니다.

5.  필드에 정보를 입력한 후 **확인**을 선택하여 **허용되는 앱** 목록에 앱을 추가합니다.

> [!NOTE]
> 여러 스토어 앱을 동시에 추가하려는 경우 앱 행 끝의 메뉴**(...)**를 클릭한 다음 계속해서 앱을 더 추가하면 됩니다. 앱을 모두 추가한 후에 **확인**을 선택합니다.

## <a name="add-a-desktop-app-to-your-allowed-apps-list"></a>허용되는 앱 목록에 데스크톱 앱 추가

**데스크톱 앱을 추가하려면**

1.  **앱 정책** 블레이드에서 정책의 이름을 선택한 다음 **허용되는 앱**을 선택합니다. **허용되는 앱** 블레이드가 열리고 이 앱 보호 정책의 목록에 이미 포함된 모든 앱이 표시됩니다.

2.  **허용되는 앱** 블레이드에서 **앱 추가**를 선택합니다.

3.  **앱 추가** 블레이드의 드롭다운 목록에서 **데스크톱 앱**을 선택합니다.

4.  필드에 정보를 입력한 후 **확인**을 선택하여 **허용되는 앱** 목록에 앱을 추가합니다.

> [!NOTE]
> 여러 **데스크톱 앱**을 동시에 추가하려는 경우 앱 행 끝의 메뉴**(…)**를 클릭한 다음 계속해서 앱을 더 추가하면 됩니다. 앱을 모두 추가한 후에 **확인**을 선택합니다.

## <a name="windows-information-protection-wip-learning"></a>WIP(Windows Information Protection) 학습

WIP를 통해 보호하려는 앱을 추가한 후에는 **WIP 학습**을 사용하여 보호 모드를 적용해야 합니다.

### <a name="before-you-begin"></a>시작하기 전에

WIP(Windows Information Protection) 학습은 관리자가 WIP에서 알 수 없는 앱을 모니터링하는 데 사용할 수 있는 보고서입니다. 알 수 없는 앱은 조직의 IT 부서에서 배포하지 않은 앱입니다. 관리자는 "재정의 숨기기" 모드에서 WIP를 적용하기 전에 생산성 저하를 방지하기 위해 보고서에서 이러한 앱을 내보내 WIP 정책에 추가할 수 있습니다.

먼저 **자동** 또는 **재정의 허용** 모드를 설정해 허용되는 앱 목록에 올바른 앱이 포함된 소규모 그룹부터 확인하는 것이 좋습니다. 이 확인이 완료되면 최종 적용 정책인 **재정의 숨기기**로 변경할 수 있습니다.

#### <a name="what-the-protection-modes-are"></a>보호 모드의 종류

- **재정의 숨기기:**
    - WIP가 부적절한 데이터 공유 사례를 찾아 사용자의 작업 완료를 중지시킵니다.
    - 부적절한 데이터 공유 사례에는 회사에서 보호하지 않는 앱 간에 정보를 공유하는 행위, 조직 외부의 타인과 장치 간에 회사 데이터를 공유하는 행위 등이 포함될 수 있습니다.
<br></br>

- **재정의 허용:**
    - WIP가 부적절한 데이터 공유를 찾은 다음 사용자가 안전하지 않을 수 있는 작업을 수행하면 경고를 표시합니다.
    - 그러나 이 모드에서는 사용자가 정책을 재정의하고 데이터를 공유할 수 있습니다. 그러면 해당 작업이 감사 로그에 로깅됩니다.
<br></br>
- **자동:**
    - 재정의 허용 모드에서 직원 상호 작용을 묻는 메시지를 차단하지 않고도 WIP가 자동으로 실행되어 부적절한 데이터 공유를 로깅합니다.
    - 그러나 네트워크 리소스 또는 WIP로 보호되는 데이터에 대한 앱의 부적절한 액세스 시도와 같은 허용되지 않는 작업은 계속 중지됩니다.
<br></br>
- **해제(권장되지 않음):**
    - WIP가 해제되며 데이터를 보호하거나 감사하지 않습니다.
    - WIP를 해제하고 나면 로컬로 연결된 드라이브에서 WIP 태그가 지정된 파일의 암호 해독이 시도됩니다. WIP 보호를 다시 설정해도 이전의 암호 해독 및 정책 정보는 자동으로 다시 적용되지 않습니다.

### <a name="to-add-a-protection-mode"></a>보호 모드를 추가하려면

1.  **앱 정책** 블레이드에서 정책의 이름을 선택한 다음 **정책 추가** 블레이드에서 **필수 설정**을 클릭합니다.

    ![학습 모드 스크린샷](../media/AppManagement/learning-mode-sc1.png)

1.  **저장**을 선택합니다.

### <a name="to-use-wip-learning"></a>WIP 학습을 사용하려면

1. Azure 대시보드로 이동합니다.

2. 왼쪽 메뉴에서 **More services**(추가 서비스)를 선택한 다음 텍스트 상자 필터에 **Intune**을 입력합니다.

3. **Intune**을 선택하면 열리는 **Intune 대시보드**에서 **Mobile Apps**를 선택합니다.

4. **모니터** 섹션 아래에서 **WIP 학습**을 선택합니다. WIP 학습에서 로깅한 알 수 없는 앱이 표시됩니다.

> [!IMPORTANT]
> WIP 학습 로깅 보고서에 앱이 표시되면 앱 보호 정책에 해당 앱을 추가할 수 있습니다.

## <a name="to-deploy-your-wip-app-protection-policy"></a>WIP 앱 보호 정책을 배포하려면

> [!IMPORTANT]
> 이 섹션의 설명은 등록 시나리오를 수행하지 않고 MAM(모바일 응용 프로그램 관리)을 사용하는 WIP에 적용됩니다.

WIP 앱 보호 정책을 만든 후에는 MAM을 사용하여 조직에 정책을 배포해야 합니다.

1.  **앱 정책** 블레이드에서 새로 만든 앱 보호 정책을 선택하고 **사용자 그룹**, **사용자 그룹 추가**를 차례로 선택합니다.

    **사용자 그룹 추가** 블레이드에서 Azure Active Directory의 모든 보안 그룹이 포함된 사용자 그룹 목록이 열립니다.

1.  정책을 적용할 그룹을 선택하고 **선택**을 클릭하여 정책을 배포합니다.

