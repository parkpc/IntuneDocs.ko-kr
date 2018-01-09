---
title: "Intune에서 사용할 Skycure iOS 앱 구성 정책 다운로드"
titlesuffix: Azure portal
description: "Intune에서 사용할 Skycure iOS 앱 구성 정책을 다운로드합니다."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 12/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1bdc2ecf-32d0-4b6a-80b4-dbcdb9909010
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: cbf26b44725f1fa08fbc6766f0560fe91d63d6ca
ms.sourcegitcommit: a3a744ea55f38a360ca9f788c77a5b3018d1add5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/30/2017
---
# <a name="download-skycure-ios-app-configuration-policy"></a>Skycure iOS 앱 구성 정책 다운로드

## <a name="before-you-begin"></a>시작하기 전에

다음 단계를 수행하려면 Skycure 관리 콘솔에 로그인해야 합니다.

> [!TIP] 
> Microsoft Internet Explorer 11 또는 Edge를 사용하는 경우에는 개인 모드를 사용하여 Skycure 관리 콘솔을 열어야 합니다.

## <a name="to-download-the-ios-app-configuration-policy"></a>iOS 앱 구성 정책을 다운로드하려면

1.  [Skycure 관리 콘솔](https://aad.skycure.com)로 이동합니다.

2.  **Skycure 관리자 자격 증명**을 입력한 다음 **계속**을 클릭합니다.

    ![Skycure 관리 콘솔 로그인](./media/skycure-ios-app-1.png)

    > [!IMPORTANT] 
    > Skycure 관리자의 사용자 이름은 Azure Active Directory에서 유효한 사용자 계정인 전자 메일 계정입니다. 그렇지 않으면 로그인에 실패합니다. Skycure는 SSO(Single Sign-On)로 해당 관리자 사용자 이름을 인증하는 데 Azure Active Directory를 사용합니다.

3.  **설정** &gt; **장치 관리 통합** &gt; **EMM 통합 선택**으로 이동하고 **Microsoft Intune**을 선택한 다음 선택한 항목을 저장합니다.

4.  **통합 설치 파일** 링크를 클릭하고 생성된 \*.zip 파일을 저장합니다. .zip 파일에는 **skycure\_configuration.plist** 파일이 포함되어 있으며 이 파일은 Intune 클래식 포털에서 iOS 앱 구성 정책을 만드는 데 사용됩니다.

![Skycure 통합 설정 파일](./media/skycure-ios-app-2.png)

## <a name="next-steps"></a>다음 단계

[Skycure 앱, Microsoft Authenticator 앱 및 iOS 구성 정책 추가 및 할당](mtd-apps-ios-app-configuration-policy-add-assign.md)
