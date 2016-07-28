---
title: "관리자 계정, 웹 사이트 및 권한 | Microsoft Intune"
description: "관리자 계정 권한 웹 사이트"
keywords: 
author: Staciebarker
manager: arob98
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: db3075e7-38fd-4dfe-b266-26aed10ac8ea
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 376e6c1ae229187ab8ec73390f091f1d534365dd
ms.openlocfilehash: 88bd3f329a6b0d137f8cf02f5221263b64a33141


---

# Microsoft Intune의 관리자 계정, 웹 사이트 및 권한

Microsoft Intune을 설정하기 전에, 이 항목과 [Microsoft Intune을 시작하기 전에 알아두어야 할 사항](what-to-know-before-you-start-microsoft-intune.md) 항목에 나열된 요구 사항을 검토합니다.

Intune을 관리하려면 다음을 사용합니다.
- 두 가지 유형의 관리자 계정
- 추가 사용 권한이 있는 사용자 계정
- 관리자가 관리해야 하는 항목에 대한 액세스 권한을 해당 관리자에게 부여하는 두 개의 웹 기반 관리 콘솔/포털

다음 섹션에서는 이러한 계정 및 포털을 설명합니다.

## 관리자 계정 및 특수한 권한을 가진 사용자 계정

다음은 Intune에 사용할 계정 및 사용 권한입니다.

### 테넌트 관리자
|권한 수준|추가 정보|
|--------------------------|-------------------------|
|테넌트 관리자에게는 관리할 수 있는 해당 사용자 및 작업에 대한 관리 범위를 정의하는 관리자 역할이 할당됩니다.<br /><br />일부 서비스에서 일부 역할을 지원하지 않을 수 있지만 관리자 역할은 여러 Microsoft 클라우드 서비스 간에 공통적입니다.<br /><br /> Microsoft Intune에서는 다음 역할을 사용합니다.<br /><br />- 전역 관리자<br />- 대금 청구 관리자<br />- 암호 관리자<br />- 서비스 지원 관리자<br />- 사용자 관리 관리자|기본적으로 Microsoft Intune 구독을 생성하는 데 사용하는 계정은 전역 관리자 역할이 있는 테넌트 관리자입니다.<br /></br>  테넌트 관리자는 [!INCLUDE[wit_icp_1](../includes/wit_icp_1_md.md)]을 사용하여 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]에 대한 구독을 관리하고 [!INCLUDE[wit_icp_2](../includes/wit_icp_2_md.md)]에서 테넌트 관리자를 할당합니다.<br /><br />첫 번째 서비스 관리자를 할당하려면 전역 관리자 역할이 있는 테넌트 관리자를 사용하여 [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)]에 액세스합니다. 일상적인 관리 작업에는 테넌트 관리자를 사용하지 않는 것이 가장 좋습니다. 테넌트 관리자는 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]에 액세스하는 데 [!INCLUDE[wit_icp_2](../includes/wit_icp_2_md.md)]의 라이선스가 필요하지 않습니다.<br /><br />테넌트 관리자는 Microsoft 클라우드 서비스 간에 일반적인 개념입니다. [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]을 구독할 경우 서비스는 Microsoft Azure AD의 테넌트입니다. [Azure AD 디렉터리란?](http://technet.microsoft.com/library/jj573650.aspx)에서 Azure AD 테넌트 섹션을 참조하세요.|


### 서비스 관리자
|권한 수준|추가 정보|
|--------------------------|-------------------------|
|서비스 관리자에게는 다음 사용 권한 중 하나가 할당됩니다.<br /><br />**모든 권한**: [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)]의 모든 영역에 대해 제한 없는 액세스 권한을 부여합니다. 다른 서비스 관리자를 추가하고 관리할 수도 있습니다.<br /><br />**읽기 전용 권한**: [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)]의 모든 영역에 대한 읽기 권한을 부여합니다. 읽기 전용 권한이 있는 서비스 관리자는 데이터를 수정할 수 없지만 보고서를 실행할 수는 있습니다.<br /><br />**기술 지원팀 - 그룹 노드**: 서비스 관리자가 기술 지원팀 시나리오와 공통적으로 관련된 작업 집합만 수행할 수 있도록 하는 권한을 부여합니다. 이 사용 권한에 대한 정보는 [관리자 역할에 따라 Intune 콘솔 보기 사용자 지정](/intune/deploy-use/control-what-admins-can-see-in-the-microsoft-intune-admin-console)을 참조하세요.|기본적으로 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]에서는 서비스 관리자를 할당하지 않습니다. 대신 구독에 대한 첫 번째 서비스 관리자를 할당하려면 전역 관리자 역할이 있는 테넌트 관리자를 사용해야 합니다. </br></br> 서비스 관리자는 [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)]을 사용하여 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]의 일상적인 작업을 관리합니다.<br /><br />관리자 콘솔에서 서비스 관리자를 할당합니다. 계정이 관리 콘솔에 액세스할 수 있기 전에 서비스 관리자는 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]에 대한 라이선스가 필요합니다.|



### 장치 등록 관리자
|권한 수준|추가 정보|
|--------------------------|-------------------------|
|장치 등록 관리자는 5개가 넘는 장치를 등록할 수 있는 추가 권한이 있는 표준 사용자 계정입니다.|기본적으로 각 [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] 사용자는 최대 5개의 장치를 등록할 수 있습니다. 그러나 사용자 계정에 장치 등록 관리자 권한을 부여한 후 해당 계정을 사용하여 대규모 회사 소유 장치 그룹을 등록할 수 있습니다. 이러한 기능은 일시적으로 사용자에게 장치를 할당하거나, 사용자와 장치 간 연결이 필요하지 않은 키오스크 모드로 작업할 때 유용합니다.|


## Intune의 관리 웹 사이트
 여러 관리 작업을 사용하려면 [지원되는 웹 브라우저](supported-web-browsers.md)를 사용하여 액세스할 수 있는 다음 관리 웹 사이트 중 하나를 사용해야 합니다.

- [Office 365 포털](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Microsoft Intune 관리자 콘솔](https://admin.manage.microsoft.com/)

### [Office 365 포털](http://go.microsoft.com/fwlink/p/?LinkId=698854)

**테넌트 관리자는 이 포털을 사용하여 구독을 관리하며**, 관리자 역할에서 허용할 경우 다음 작업도 수행합니다.

- 구독에 대한 사용자 계정을 관리하고 온-프레미스 Active Directory에서의 디렉터리 동기화를 구성합니다.
- 보안 그룹이라는 사용자 그룹을 관리합니다.
- [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]을 사용할 수 있는 라이선스를 사용자에게 할당합니다.
- 구독에 사용하는 도메인 이름을 구성합니다. 도메인 이름은 사용자가 로그인하는 데 사용하는 계정을 정의합니다.
- 보유한 라이선스 수 또는 사용할 수 있는 클라우드 저장소 공간의 양을 비롯하여 구독에 대한 대금 청구 및 구매 정보를 관리합니다.
- [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] 서비스의 상태를 확인할 수 있는 링크를 찾습니다.
- 테넌트 관리자는 계정에 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]을 사용할 수 있는 라이선스가 할당되지 않은 경우에도 Office 365 포털에 로그인하여 구독을 관리할 수 있습니다.
- Intune에 대한 라이선스가 있지만 관리자가 아닌 사용자는 이 포털을 사용하여 계정 암호를 재설정하고 프로필을 편집할 수 있습니다.
- Office 365 포털에 액세스하려면 계정의 로그인 상태가 **허용**이어야 합니다. 이 상태는 구독에 대한 라이선스 보유와는 다른 문제입니다. 기본적으로 모든 사용자 계정은 **허용**됩니다.


### [Microsoft Intune 관리자 콘솔](https://admin.manage.microsoft.com/)

**서비스 관리자는 이 포털을 사용하여 일상적인 작업을 관리**하며, 다음과 같은 작업이 포함됩니다.

- 컴퓨터 및 모바일 장치에 대한 정책을 설정합니다.
- 소프트웨어 업데이트 및 앱과 같은 소프트웨어를 업로드 및 배포합니다.
- 컴퓨터에서 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] Endpoint Protection을 관리합니다.
- 장치 상태를 확인하고 보고서를 실행합니다.
- 이 포털에 로그인합니다. 이 포털에 로그인하려면 서비스 관리자 권한이 있거나전역 관리자 역할이 있는 테넌트 관리자여야 합니다.


서비스 관리자 권한이 있는 사용자이거나 전역 관리자 역할이 있는 테넌트 관리자만이 이 포털에 로그인할 수 있습니다. 관리 콘솔에 액세스하려면 계정에 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]을 사용할 수 있는 라이선스가 있어야 하며 계정의 로그인 상태가 **허용**이어야 합니다.

[구독에 사용자 추가](start-with-a-paid-subscription-to-microsoft-intune-step-3.md) 및 [구독에 라이선스 할당](start-with-a-paid-subscription-to-microsoft-intune-step-4.md)에 대해 자세히 알아봅니다.

 ### 참고 항목
 [Microsoft Intune을 시작하기 전에 알아두어야 할 사항](what-to-know-before-you-start-microsoft-intune.md)



<!--HONumber=Jul16_HO3-->


