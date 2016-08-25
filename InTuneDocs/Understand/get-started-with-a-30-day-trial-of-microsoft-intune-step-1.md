---
title: "Microsoft Intune의 30일 평가판 등록 | Microsoft Intune"
description: "Intune 무료 30일 평가판 등록 방법 및 등록 전 고려 사항"
keywords: 
author: lindavr
manager: angrobe
ms.date: 08/09/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dad88d43-0054-4be6-9e5d-ada5a957dd6c
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 51fba2b01d8978bc062c50c4388714609be0fdf0
ms.openlocfilehash: 081d396975473cd605e9619498aef78fb2d0e1dd


---

# Microsoft Intune의 30일 평가판 등록

모바일 장치와 컴퓨터를 관리할 수 있는 Microsoft Intune 30일 평가판을 설치하는 과정은 빠르고 간단합니다. 평가판에서 몇 가지 간단한 단계만 거치면 최대 100명의 사용자와 장치를 추가하고, 그룹을 설정하고, 규정 준수 정책을 구성하고, 모바일 장치 및 컴퓨터를 등록하고 관리할 수 있습니다. 이 항목에서는 Intune 평가판을 실행하는 기본적인 방법과 Intune의 특징과 기능을 평가할 수 있는 서비스의 개요를 알아봅니다.

## 등록하기 전에 고려할 사항

Intune에 등록하거나 로그인하기 전에 다음 사항을 고려해야 합니다.

-   조직에 Microsoft Online Services 회사 또는 학교 계정이 이미 있는지 여부

-   Microsoft와의 기업계약 또는 그와 동등한 볼륨 라이선스 계약이 있는지 여부

-   30일 평가판이 끝나도 Intune 테넌트를 사용할 계획인지 여부

|새 계정을 등록해야 하는 경우|회사 또는 학교 계정으로 로그인해야 하는 경우|
|-----------------------------------------------------------------|------------------------------------------------|
|**회사 또는 학교 계정이 없는 경우.** Microsoft와 볼륨 라이선스 계약을 체결하거나 Office 365에 구독하면 회사 또는 학교 계정이 제공됩니다. 조직이 Microsoft와 체결한 기업계약 또는 이와 동등한 볼륨 라이선싱 계약에 서명(또는 Office 365 계정을 보유)하지 않은 경우 Microsoft Online Services에 로그인하는 데 사용할 수 있는 Microsoft Online Services가 없습니다.<br /><br />**30일 평가판 사용을 완료한 후 Intune 테넌트를 취소하려는 경우.** Intune 무료 평가판 구독을 평가용으로만 사용하며, 평가판을 사용한 후 Intune 서비스 설정 및 장치 프로비전을 다시 실행하려는 경우에는 새 계정을 등록해야 합니다. System Center 2012 Configuration Manager가 통합된 Intune을 사용할 계획일 때 권장되는 옵션입니다.<br /><br />새 사용자 계정을 등록하는 경우 기존 회사 또는 학교 계정 사용하거나 해당 계정을 관리하거나 기존 볼륨 라이선스 계약과 결합하도록 나중에 변경할 수 없습니다.|**볼륨 라이선스 계약 또는 Office 365 구독 시 제공받은 회사 또는 학교 계정이 있고, 이 평가판을 사용하여 Intune을 평가하려는 경우.**<br /><br />기존 계정에 Intune을 설정하는 경우 이 단계를 진행하기 전에 [장치를 관리하는 방법 선택](/intune/get-started/choose-how-to-manage-devices)을 검토해 보는 것이 좋습니다.|

## Intune에 등록 또는 로그인

1.  첫째, [여기를 클릭하여 Intune 등록 페이지를 방문](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20)합니다.

2.  **등록** 페이지에는 다음과 같은 두 옵션이 있습니다.

    -   **Microsoft Online Services 회사 또는 학교 계정을 사용한 구독**: 이미 회사 또는 학교 계정이 있는 경우 **로그인** 을 클릭하여 두 서비스를 구독하는 데 동일한 계정을 사용하고자 할 수 있습니다. 여러 서비스에 동일한 계정을 사용하는 경우 해당 서비스는 동일한 Azure AD 인프라를 사용하며 Azure AD의 테넌트가 됩니다. Azure AD는 Microsoft 클라우드 서비스의 주요 디렉터리 및 ID 관리 기능을 제공합니다.

    -   **Intune에만 가입**: 클라우드 서비스에 아직 가입하지 않은 경우 등록 페이지의 양식을 작성하여 Intune에 가입합니다.

        > [!NOTE]
        > 기본적으로 도메인 이름은 Intune에 추가하는 구독 및 사용자 계정과 연결됩니다. 가입한 후 기존에 가진 사용자 지정 도메인 이름을 추가하여 사용할 수 있으며, **onmicrosoft.com** 무료 도메인을 계속 사용할 수도 있습니다.

등록 양식을 작성하고 Microsoft 온라인 구독 계약에 동의하면 테넌트 관리자 계정으로 Office 365 관리 센터에 자동으로 로그인됩니다. 또한 등록하는 동안 지정한 전자 메일 주소로 계정 정보를 포함한 전자 메일 메시지를 받게 됩니다. 이 전자 메일을 통해 구독이 활성화된 것을 확인할 수 있습니다.

### 다음 단계
축하합니다. *Microsoft Intune 평가판* 연습의 1단계를 완료했습니다.

>[!div class="step-by-step"]

>[&larr; **시작**](get-started-with-a-30-day-trial-of-microsoft-intune.md)     [**사용자 추가** &rarr;](get-started-with-a-30-day-trial-of-microsoft-intune-step-2.md)  



<!--HONumber=Aug16_HO2-->


