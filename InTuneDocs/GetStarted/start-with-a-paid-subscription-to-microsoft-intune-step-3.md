---
title: "Active Directory를 동기화하고 Intune에 사용자 추가 | Microsoft Intune"
description: "Azure AD와 온-프레미스 사용자를 동기화하고 Intune 구독에 대한 관리자 권한을 부여하는 방법을 설명합니다."
keywords: 
author: Staciebarker
manager: arob98
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6e9ec662-465b-4ed4-94c1-cff0fe18f126
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 376e6c1ae229187ab8ec73390f091f1d534365dd
ms.openlocfilehash: 8aeb23b709b50ccb8ad29868b4bc5ab96faf950f


---


# Active Directory를 동기화하고 Intune에 사용자 추가
온-프레미스 Active Directory에서 Microsoft Azure Active Directory(Azure AD)로 사용자 계정을 가져오도록 디렉터리 동기화를 구성할 수 있습니다. 온-프레미스 Active Directory 서비스를 모든 Azure Active Directory 기반 서비스와 연결하면 사용자 ID를 훨씬 간편하게 관리할 수 있습니다. 사용자에게 친숙하고 간편한 인증 환경을 제공하도록 Single Sign-On 기능을 구성할 수도 있습니다.

훨씬 간편한 작업을 위해, 같은 [Azure AD 테넌트](http://technet.microsoft.com/library/jj573650.aspx#BKMK_WhatIsAnAzureADTenant)로 여러 가지 서비스를 사용하는 경우, 이전에 동기화한 사용자 계정을 동일한 Azure AD 테넌트 구독을 공유하는 모든 클라우드 기반 서비스에 사용할 수 있습니다.

## Azure AD와 온-프레미스 사용자 동기화
Azure AD와 사용자 계정을 동기화하기 위해 필요한 유일한 도구는 [Azure AD Connect 마법사](https://www.microsoft.com/download/details.aspx?id=47594)입니다. Azure AD Connect 마법사는 온-프레미스 ID 인프라를 클라우드에 연결하도록 안내하는 간단한 환경을 제공합니다.  토폴로지 및 요구 사항(디렉터리 하나/여러 개, 암호 동기화 또는 페더레이션)을 선택하면 마법사에서 연결을 작동하고 실행하는 데 필요한 모든 구성 요소를 배포하고 구성합니다. 여기에는 동기화 서비스, AD FS(Active Directory Federation Services) 및 Azure AD PowerShell 모듈이 포함됩니다.

> [!TIP]
> Azure AD Connect에는 이전에 Dirsync 및 Azure AD Sync로 출시된 기능이 포함됩니다. [디렉터리 통합](http://technet.microsoft.com/library/jj573653.aspx)에 대해 자세히 알아봅니다. 로컬 디렉터리에서 Azure AD로 사용자 계정을 동기화하는 이점에 대한 자세한 내용은 [Active Directory와 Azure AD의 유사성](http://technet.microsoft.com/library/dn518177.aspx)을 참조하세요.

## 관리자 권한 부여
Intune 구독에 사용자를 추가한 후에는 몇 개의 사용자 계정에 [관리 자격 증명](administrative-accounts-websites-perms.md)을 부여하는 것이 좋습니다. 관리 자격 증명을 할당하기 위해 사용하는 콘솔은 할당할 관리자 유형에 따라 달라집니다.

-   **테넌트 관리자**: 대금 청구, 클라우드 저장소, [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]을 사용할 수 있는 사용자 관리 등 구독을 관리하는 데 이러한 유형의 관리자를 할당하려면 **[!INCLUDE[wit_icp_1](../includes/wit_icp_1_md.md)]**을 사용합니다.

-   **서비스 관리자**: 모바일 장치 또는 컴퓨터 관리, 정책 또는 소프트웨어의 배포, 보고서 실행 등 일상적인 작업에 이러한 유형의 관리자를 할당하려면 **[!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)]**을 사용합니다.


### 다음 단계
축하합니다. *Intune 빠른 시작 가이드*의 3단계를 완료했습니다.

>[!div class="step-by-step"]

>[&larr;**도메인 설정**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**Intune 라이선스 관리** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-4.md)  



<!--HONumber=Jul16_HO3-->


