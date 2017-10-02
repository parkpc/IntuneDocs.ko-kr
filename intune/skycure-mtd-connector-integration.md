---
title: "Intune과 Skycure 통합 설정"
titlesuffix: Azure portal
description: "Microsoft Intune과 Skycure의 통합을 설정하는 방법을 설명합니다."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 359448d9-2384-42ac-a21c-a25148c20a7b
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d495046a990817e73fcee385b3a1482229aac721
ms.sourcegitcommit: d434dfab7ef7a6c4082d675717fa22d5581b4f51
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/19/2017
---
# <a name="set-up-the-skycure-integration-with-intune"></a>Intune과 Skycure 통합 설정

Single Sign-On 기능을 보유하려면 Azure AD에 Skycure 앱을 추가해야 합니다.

## <a name="before-you-begin"></a>시작하기 전에

### <a name="azure-ad-account-used-to-integrate-intune-and-skycure"></a>Intune과 Skycure를 통합하는 데 사용되는 Azure AD 계정

-   Skycure 기본 설정 프로세스를 시작하려면 [Skycure 관리 콘솔](https://aad.skycure.com)에 Azure AD 계정이 제대로 구성되어 있어야 합니다.

### <a name="full-integration-vs-read-only"></a>전체 통합 및 읽기 전용

Skycure는 Intune과의 통합을 두 가지 모드로 지원합니다.

-   **읽기 전용 통합(기본 설정):** Azure Active Directory에서 장치를 인벤토리에 포함하고 Skycure 콘솔에서 해당 정보를 채우기만 합니다.
<br>
    -   Skycure 관리 콘솔에서 **Intune에 장치 상태 및 위험 보고** 및 **Intune에 보안 문제도 보고** 상자가 선택되지 않은 경우 통합은 읽기 전용이므로 Intune에서 장치 상태(준수 또는 미준수)가 변경되지 않습니다.
<br></br>
-   **전체 통합:** 장치의 위험 및 보안 문제 세부 정보에 대해 Skycure에서 보고하도록 허용합니다. 이렇게 하면 두 클라우드 서비스 간 양방향 통신이 이루어집니다.

### <a name="how-the-skycure-apps-are-used-with-azure-ad-and-intune"></a>Skycure 앱을 Azure AD 및 Intune과 함께 사용하는 방법은 무엇인가요?

-   **iOS 앱:** 최종 사용자가 iOS 앱을 사용하여 Azure AD에 로그인할 수 있습니다.

-   **Android 앱:** 최종 사용자가 Android 앱을 사용하여 Azure AD에 로그인할 수 있습니다.

-   **관리 앱:** Intune과의 서비스 간 통신을 사용하도록 설정하는 Skycure Azure AD 다중 테넌트 앱입니다.

## <a name="to-set-up-the-read-only-integration-between-intune-and-skycure"></a>Intune과 Skycure 간의 읽기 전용 통합을 설정하려면

> [!IMPORTANT]
> Skycure 관리자 자격 증명은 Azure Active Directory에서 유효한 사용자에 속해 있는 전자 메일입니다. 이에 속해 있지 않으면 로그인에 실패합니다. Skycure는 SSO(Single Sign-On)로 해당 관리자를 인증하는 데 Azure Active Directory를 사용합니다.

1.  [Skycure 관리 콘솔](https://aad.skycure.com)로 이동합니다.

2.  **Skycure 관리자 자격 증명**을 입력한 다음 **계속**을 클릭합니다.

3.  **설정**으로 이동하고 **Intune 통합**에서 **기본 설정**을 선택합니다.

4.  **iOS 앱** 레이블에서 **Active Directory에 추가**를 클릭합니다.

    ![Skycure 관리 콘솔에서 iOS 앱](./media/skycure-setup-1.png)

5.  로그인 페이지가 열리면 Intune 자격 증명을 입력한 다음 **동의**를 클릭합니다.

    ![iOS 앱 Intune 로그인 프롬프트](./media/skycure-setup-2.png)

6.  Azure AD에 앱이 추가되면 Skycure 관리 콘솔에서 Azure AD에 앱이 추가되었음을 알리는 메시지가 나타납니다.

    ![iOS 앱 완료 화면](./media/skycure-setup-3.png)

> [!NOTE]
> **Skycure Android** 및 **관리** 앱에 대해 동일한 프로세스를 반복합니다.

### <a name="add-an-azure-ad-security-group-into-skycure"></a>Skycure에 Azure AD 보안 그룹 추가

Skycure를 실행하는 모든 장치가 포함된 Azure AD 보안 그룹을 추가해야 합니다.

1.  Skycure를 실행하는 장치의 보안 그룹을 모두 입력하여 선택한 다음 **변경 내용 적용**을 클릭합니다.

    ![보안 그룹 Skycure 관리 콘솔 구성](./media/skycure-setup-4.png)

Skycure는 Mobile Threat Defense 서비스를 실행하는 장치를 Azure AD 보안 그룹과 동기화합니다.

![Skycure 관리 콘솔에서 완료된 보안 그룹 구성](./media/skycure-setup-5.png)

## <a name="set-up-the-full-integration-between-intune-and-skycure"></a>Intune과 Skycure 간의 전체 통합 설정

1.  [Skycure 관리 콘솔](https://aad.skycure.com)로 이동합니다.

2.  **Skycure 관리자 자격 증명**을 입력한 다음 **계속**을 클릭합니다.

3.  **설정**으로 이동하고 **Intune 통합**에서 **전체 통합**을 선택합니다.

4.  다음 설정을 확인합니다.

    a.  Intune에 장치 상태 및 위험 보고

    b.  Intune에 보안 문제도 보고

5.  **변경 내용 적용**을 클릭합니다.

    ![Skycure 전체 통합 완료](./media/skycure-setup-6.png)

## <a name="next-steps"></a>다음 단계

[Skycure 앱 설정](mtd-apps-ios-app-configuration-policy-add-assign.md)
