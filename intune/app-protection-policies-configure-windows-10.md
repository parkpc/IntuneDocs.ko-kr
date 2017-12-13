---
title: "Windows 10용 앱 보호 정책 구성 준비"
titlesuffix: Azure portal
description: "Azure AD에서 MAM(모바일 응용 프로그램 관리) 공급자 설치"
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 10/25/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 949fddec-5318-4c9a-957e-ea260e6e05be
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 91e26256d220ba70e5ad6daa3910d34eea8bb5ed
ms.sourcegitcommit: 67ec0606c5440cffa7734f4eefeb7121e9d4f94f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/08/2017
---
# <a name="get-ready-to-configure-app-protection-policies-for-windows-10"></a>Windows 10용 앱 보호 정책 구성 준비

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Azure AD에서 MAM 공급자를 설정하여 Windows 10용 MAM(모바일 응용 프로그램 관리)을 사용하도록 설정합니다. Azure AD에서 MAM 공급자를 설정하면 Intune을 사용하여 새 WIP(Windows Information Protection) 정책을 만들 때 등록 상태를 정의할 수 있습니다. 등록 상태는 MAM 또는 MDM(모바일 장치 관리)일 수 있습니다.

> [!NOTE]
> MAM 등록 상태의 장치는 Azure AD와 조인되어야 합니다.

## <a name="to-configure-the-mam-provider"></a>MAM 공급자를 구성하려면

1. Azure Portal에 로그인하고 **Azure Active Directory**를 선택합니다.

2. **관리** 그룹에서 **이동성(MDM 및 MAM)**을 선택합니다.

3. **Microsoft Intune**을 클릭합니다.

4. **구성** 블레이드의 **기본 MAM URL 복원** 그룹에서 설정을 구성합니다.

    **MAM 사용자 범위**  
      MAM 자동 등록을 사용하여 직원의 Windows 장치에서 엔터프라이즈 데이터를 관리합니다. MAM 자동 등록은 Bring Your Own Device 시나리오용으로 구성됩니다.<ul><li>**없음**<br>모든 사용자가 MAM에 등록될 수 있는 경우 선택합니다.</li><li>**일부**<br>MAM에 등록될 사용자가 포함된 Azure AD 그룹을 선택합니다.</li><li>**모두**<br>모든 사용자가 MAM에 등록될 수 있는 경우 선택합니다.</li></ul>

    **MAM 사용 약관 URL**  
     MAM 서비스 사용 약관 끝점의 URL입니다. 사용 약관 끝점은 관리를 위해 장치를 등록하기 전에 최종 사용자에게 서비스 약관을 표시하는 데 사용됩니다. 사용 약관 텍스트는 모바일 장치에 적용되는 정책에 대해 사용자에게 알려줍니다.

    **MAM 검색 URL**  
    MAM 서비스 등록 끝점의 URL입니다. 등록 끝점은 MAM 서비스에서 관리할 장치를 등록하는 데 사용됩니다.

    **MAM 준수 URL**  
      MAM 서비스 준수 끝점의 URL입니다. 사용자가 비준수 장치에서 리소스에 액세스하는 것을 거부당하면 준수 URL 링크가 해당 사용자에게 표시됩니다. 사용자는 MAM 서비스에서 호스트하는 이 URL로 이동하여 해당 장치가 비준수 상태로 간주되는 이유를 알아볼 수 있습니다. 사용자는 장치가 준수 상태가 되어 리소스에 계속 액세스할 수 있도록 셀프 서비스 수정을 시작할 수도 있습니다.

5.  **Save**을 클릭합니다.

## <a name="next-steps"></a>다음 단계

[WIP 앱 보호 정책 만들기](windows-information-protection-policy-create.md)
