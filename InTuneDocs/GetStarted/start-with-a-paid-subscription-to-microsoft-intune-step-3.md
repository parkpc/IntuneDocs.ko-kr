---
title: "Active Directory를 동기화하고 Intune에 사용자 추가 | Microsoft Intune"
description: "Azure AD와 온-프레미스 사용자를 동기화하고 Intune 구독에 대한 관리자 권한 부여"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6e9ec662-465b-4ed4-94c1-cff0fe18f126
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 29b6e5a3d319c741482fcc2b600842e2e42b96e2
ms.openlocfilehash: 33534c685ad3a4ddfd4b605e088132f2b8ff2c36


---


# <a name="sync-active-directory-and-add-users-to-intune"></a>Active Directory를 동기화하고 Intune에 사용자 추가
온-프레미스 Active Directory에서 Microsoft Azure Active Directory(Azure AD)로 사용자 계정을 가져오도록 디렉터리 동기화를 구성할 수 있습니다. 온-프레미스 Active Directory 서비스를 모든 Azure Active Directory 기반 서비스와 연결하면 사용자 ID를 훨씬 간편하게 관리할 수 있습니다. 사용자에게 친숙하고 간편한 인증 환경을 제공하도록 Single Sign-On 기능을 구성할 수도 있습니다.

훨씬 간편한 작업을 위해, 같은 [Azure AD 테넌트](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/)로 여러 가지 서비스를 사용하는 경우, 이전에 동기화한 사용자 계정을 동일한 Azure AD 테넌트 구독을 공유하는 모든 클라우드 기반 서비스에 사용할 수 있습니다.

## <a name="synchronize-on-premises-users-with-azure-ad"></a>Azure AD와 온-프레미스 사용자 동기화
Azure AD와 사용자 계정을 동기화하기 위해 필요한 유일한 도구는 [Azure AD Connect 마법사](https://www.microsoft.com/download/details.aspx?id=47594)입니다. Azure AD Connect 마법사는 온-프레미스 ID 인프라를 클라우드에 연결하도록 안내하는 간단한 환경을 제공합니다.  토폴로지 및 요구 사항(디렉터리 하나/여러 개, 암호 동기화 또는 페더레이션)을 선택하면 마법사에서 연결을 작동하고 실행하는 데 필요한 모든 구성 요소를 배포하고 구성합니다. 여기에는 동기화 서비스, AD FS(Active Directory Federation Services) 및 Azure AD PowerShell 모듈이 포함됩니다.

> [!TIP]
> Azure AD Connect에는 이전에 Dirsync 및 Azure AD Sync로 출시된 기능이 포함됩니다. [디렉터리 통합](http://technet.microsoft.com/library/jj573653.aspx)에 대해 자세히 알아봅니다. 로컬 디렉터리에서 Azure AD로 사용자 계정을 동기화하는 이점에 대한 자세한 내용은 [Active Directory와 Azure AD의 유사성](http://technet.microsoft.com/library/dn518177.aspx)을 참조하세요.

## <a name="grant-administrator-permissions"></a>관리자 권한 부여

Intune을 관리하려면 다음을 사용합니다.
- 두 가지 유형의 관리자 계정
- 추가 사용 권한이 있는 사용자 계정
- 관리자가 관리해야 하는 항목에 대한 액세스 권한을 해당 관리자에게 부여하는 두 개의 웹 기반 관리 콘솔/포털

Intune 구독에 사용자를 추가한 후에는 사용자 계정 몇 개에 관리 자격 증명을 부여하는 것이 좋습니다. 관리 자격 증명을 할당하기 위해 사용하는 콘솔은 할당할 관리자 유형에 따라 달라집니다.

-   **테넌트 관리자**: 대금 청구, 클라우드 저장소, Intune을 사용할 수 있는 사용자 관리 등 구독을 관리하는 데 이러한 유형의 관리자를 할당하려면 **Microsoft Intune 계정 포털**을 사용합니다.

-   **서비스 관리자**: 모바일 장치 또는 컴퓨터 관리, 정책 또는 소프트웨어의 배포, 보고서 실행 등 일상적인 작업에 이러한 유형의 관리자를 할당하려면 **Microsoft Intune 관리자 콘솔**을 사용합니다.

다음 섹션에서는 이러한 계정 및 포털을 설명합니다.

## <a name="administrator-accounts-and-user-accounts-with-special-permissions"></a>관리자 계정 및 특수한 권한을 가진 사용자 계정

다음은 Intune에 사용할 계정 및 사용 권한입니다.

### <a name="tenant-administrator"></a>테넌트 관리자
|권한 수준|추가 정보|
|--------------------------|-------------------------|
|테넌트 관리자에게는 관리할 수 있는 해당 사용자 및 작업에 대한 관리 범위를 정의하는 관리자 역할이 할당됩니다.<br /><br />일부 서비스에서 일부 역할을 지원하지 않을 수 있지만 관리자 역할은 여러 Microsoft 클라우드 서비스 간에 공통적입니다.<br /><br /> Microsoft Intune에서는 다음 역할을 사용합니다.<br /><br />- 전역 관리자<br />- 대금 청구 관리자<br />- 암호 관리자<br />- 서비스 지원 관리자<br />- 사용자 관리 관리자|기본적으로 Microsoft Intune 구독을 생성하는 데 사용하는 계정은 전역 관리자 역할이 있는 테넌트 관리자입니다.<br /></br>  테넌트 관리자는 [!INCLUDE[wit_icp_1](../includes/wit_icp_1_md.md)]을 사용하여 Intune에 대한 구독을 관리하고 [!INCLUDE[wit_icp_2](../includes/wit_icp_2_md.md)]에서 테넌트 관리자를 할당합니다.<br /><br />첫 번째 서비스 관리자를 할당하려면 전역 관리자 역할이 있는 테넌트 관리자를 사용하여 [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)]에 액세스합니다. 일상적인 관리 작업에는 테넌트 관리자를 사용하지 않는 것이 가장 좋습니다. 테넌트 관리자는 [!INCLUDE[wit_icp_2](../includes/wit_icp_2_md.md)]에 액세스하는 데 Intune의 라이선스가 필요하지 않습니다.<br /><br />테넌트 관리자는 Microsoft 클라우드 서비스 간에 일반적인 개념입니다. Intune을 구독할 경우 서비스는 Microsoft Azure AD의 테넌트입니다. [Azure AD 디렉터리란?](http://technet.microsoft.com/library/jj573650.aspx)에서 Azure AD 테넌트 섹션을 참조하세요.|


### <a name="service-administrator"></a>서비스 관리자
|권한 수준|추가 정보|
|--------------------------|-------------------------|
|서비스 관리자에게는 다음 사용 권한 중 하나가 할당됩니다.<br /><br />**모든 권한**: [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)]의 모든 영역에 대해 제한 없는 액세스 권한을 부여합니다. 다른 서비스 관리자를 추가하고 관리할 수도 있습니다.<br /><br />**읽기 전용 권한**: [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)]의 모든 영역에 대한 읽기 권한을 부여합니다. 읽기 전용 권한이 있는 서비스 관리자는 데이터를 수정할 수 없지만 보고서를 실행할 수는 있습니다.<br /><br />**기술 지원팀 - 그룹 노드**: 서비스 관리자가 기술 지원팀 시나리오와 공통적으로 관련된 작업 집합만 수행할 수 있도록 하는 권한을 부여합니다. 이 사용 권한에 대한 정보는 [관리자 역할에 따라 Intune 콘솔 보기 사용자 지정](/intune/deploy-use/control-what-admins-can-see-in-the-microsoft-intune-admin-console)을 참조하세요.|기본적으로 Intune에서는 서비스 관리자를 할당하지 않습니다. 대신 구독에 대한 첫 번째 서비스 관리자를 할당하려면 전역 관리자 역할이 있는 테넌트 관리자를 사용해야 합니다. </br></br> 서비스 관리자는 [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)]을 사용하여 Intune의 일상적인 작업을 관리합니다.<br /><br />관리자 콘솔에서 서비스 관리자를 할당합니다. 계정이 관리 콘솔에 액세스할 수 있기 전에 서비스 관리자는 Intune에 대한 라이선스가 필요합니다.|



### <a name="device-enrollment-managers"></a>장치 등록 관리자
|권한 수준|추가 정보|
|--------------------------|-------------------------|
|장치 등록 관리자는 5개가 넘는 장치를 등록할 수 있는 추가 권한이 있는 표준 사용자 계정입니다.|기본적으로 각 [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] 사용자는 최대 5개의 장치를 등록할 수 있습니다. 그러나 사용자 계정에 장치 등록 관리자 권한을 부여한 후 해당 계정을 사용하여 대규모 회사 소유 장치 그룹을 등록할 수 있습니다. 이러한 기능은 일시적으로 사용자에게 장치를 할당하거나, 사용자와 장치 간 연결이 필요하지 않은 키오스크 모드로 작업할 때 유용합니다.|




>[!div class="step-by-step"]

>[&larr;**도메인 설정**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**Intune 라이선스 관리** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-4.md)  



<!--HONumber=Nov16_HO4-->


