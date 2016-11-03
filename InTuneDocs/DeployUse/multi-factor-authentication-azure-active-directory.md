---
title: "Azure AD를 사용하여 다단계 인증 | Microsoft Intune"
description: "Azure AD에서 장치를 등록하기 위해 다단계 인증을 요구하는 방법입니다."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angerobe
ms.date: 09/22/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 47abdabd-dcd6-48d8-aade-3f3eefb92ee1
ROBOTS: NOINDEX,NOFOLLOW
translationtype: Human Translation
ms.sourcegitcommit: a7cced90c482498b5f5af424165f8dcf77b79b75
ms.openlocfilehash: ccd55cc8637ebccfdbddd05c4f6b182c7923a2ab


---

# <a name="multifactor-authentication-for-microsoft-intune"></a>Microsoft Intune의 다단계 인증

Intune은 장치 등록을 위해 Azure AD MFA(다단계 인증)을 통합하여 회사 리소스를 보호할 수 있게 합니다. MFA를 사용하려면 사용자 이름 및 암호 외에도 텍스트 인증과 같은 인증 요소가 필요합니다. iOS, Android, Windows 8.1 이상 또는 Windows Phone 8.1 이상의 장치에서 지원됩니다.

> [!NOTE]
>
> Configuration Manager의 이전 버전(릴리스 1610 이전)에서는 Configuration Manager 관리자 콘솔에서 MFA 설정을 계속 볼 수 있습니다. Configuration Manager 관리자 콘솔은 더 이상 작동하지 않으므로 MFA를 구성하려 하지 마세요. 이 항목에 설명된 대로 MFA를 구성합니다.

### <a name="configuring-intune-to-require-multifactor-authentication-at-device-enrollment"></a>장치 등록 단계에서 다단계 인증을 요구하도록 Intune 구성
장치 등록 시 MFA를 요구하려면 다음 단계를 수행합니다.

1. 관리자 자격 증명으로 [Microsoft Azure 포털](https://manage.windowsazure.com)에 로그인합니다.
2. 테넌트를 선택합니다.
2. **응용 프로그램** 탭을 선택합니다. Azure AD 보안 기능을 구성할 수 있는 서비스 목록이 표시됩니다.
3. **Microsoft Intune 등록**을 선택합니다.
4. **구성**을 선택합니다. 
5. **다단계 인증 및 위치 기반 액세스 규칙** 아래에서 다음을 수행할 수 있습니다.
    -  액세스 규칙 사용
    -  모든 사용자에게 규칙을 적용할지 특정 Azure AD 보안 그룹에 적용할지를 선택합니다.
    -  모든 장치 등록에 다단계 인증이 필요합니다.
    -  장치가 회사에 없는 경우 등록 시 다단계 인증이 필요합니다.
    -  **회사 리소스에 대한 액세스 차단**을 선택하여 장치가 회사 네트워크에 등록되지 않은 경우 장치 등록을 차단합니다. 
4. 또한 **회사 네트워크 위치 정의/편집** 링크를 클릭하여 장치 등록에 대한 네트워크 연결 요구 사항을 구성할 수도 있습니다.

> [!IMPORTANT]
> 
> Microsoft Intune 등록에 대한 **장치 기반 액세스 규칙**을 구성하지 마세요.



<!--HONumber=Sep16_HO4-->


