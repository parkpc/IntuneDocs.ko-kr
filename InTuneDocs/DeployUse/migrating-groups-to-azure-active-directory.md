---
title: "Azure Active Directory 그룹으로 마이그레이션 | Microsoft Intune"
description: "Intune에서 Azure AD로 그룹을 마이그레이션하는 방법"
keywords: 
author: nbigman
ms.author: nbigman
manager: angerobe
ms.date: 10/10/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 03b69afa-3548-4033-9039-191528f3fd99
translationtype: Human Translation
ms.sourcegitcommit: d92c9ffe42b36770a32c28941de3c402aec9dd68
ms.openlocfilehash: 08bcc258f64e6385ae6fa648ddb8f2b5fe68942e


---

## 새로운 그룹 관리 환경
    
Enterprise Mobility + Security 전체에서 한 번의 그룹화 및 대상 지정 경험에 대한 사용자 피드백을 반영하여 Microsoft는 Intune 그룹을 Azure Active Directory 기반 보안 그룹으로 변환하고 있습니다. 이 변환 작업을 통해 Intune과 Azure AD(Azure Active Directory) 전체의 그룹 관리가 통합될 예정입니다. 이 새로운 환경은 서비스 간에 그룹을 복제할 필요를 없애주고 PowerShell 및 Graph를 사용하여 확장성을 제공합니다. 

### 언제, 어떻게 새 그룹 환경으로 마이그레이션하나요?
현재 고객은 충분한 시간을 두고 마이그레이션됩니다. 2016 년 12 월 이후에 시작될 예정입니다. 해당 그룹은 마이그레이션되기 전에 공지를 받게 됩니다. 마이그레이션 관련 질문이 있는 경우에는 마이그레이션 팀([intunegrps@microsoft.com](mailto:intunegrps@microsoft.com))에 문의 하세요.

### 어떤 새로운 기능을 사용할 수 있나요?
새로 도입되는 기능은 다음과 같습니다. 
 
-    모든 배포 형식에 대해 Intune에서 Azure AD 보안 그룹이 지원됩니다. 
-    Azure AD 보안 그룹에서 사용자와 함께 장치 그룹화를 지원합니다.
-    Azure AD 보안 그룹에서 Intune 장치 특성을 사용하여 동적 그룹을 지원합니다. 예를 들어 iOS와 같은 플랫폼을 기반으로 하는 장치를 동적으로 그룹화할 수 있게 됩니다. 이러한 방식으로 새 iOS 장치가 조직에 등록되면 iOS 동적 장치 그룹에 자동으로 추가됩니다.
-    Azure AD와 Intune 전체에서 그룹 관리에 대한 관리자 환경이 공유됩니다.
- *Intune 서비스 관리자 역할*이 Azure AD에 추가되어 Intune 서비스 관리자가 Azure AD에서 그룹 관리 작업을 수행할 수 있습니다.

 
### 사용할 수 없게 되는 Intune 기능은 무엇인가요?
그룹 경험이 개선되긴 하지만 마이그레이션 후 제공되지 않는 일부 Intune 기능이 있습니다.

#### 그룹 관리 기능

-   새 그룹을 만들 때 구성원 또는 그룹을 제외할 수 없습니다. 그러나 Azure AD 동적 그룹을 사용하면 고급 규칙을 만들 수 있는 특성으로 조건에 따라 멤버를 제외할 수 있습니다. 예를 들어 보안 그룹에 Sales 부서에 속한 모든 사람을 포함하되 직함에 "Assistant"라는 단어가 포함된 사람은 제외하는 고급 규칙을 만들 수 있습니다. 이 고급 규칙은 `(user.department -eq "Sales") -and -not (user.jobTitle -contains "Assistant")`입니다. 자세한 내용은 [특성을 사용하여 고급 규칙 만들기](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/)를 참조하세요.
-   **그룹화되지 않은 사용자** 및 **그룹화되지 않은 장치** 그룹에 대한 지원이 제공되지 않습니다. 이 그룹들은 마이그레이션되지 않습니다.

#### 그룹 종속 기능

-   서비스 관리자 역할에 **그룹 관리** 권한이 없게 됩니다.
-   Exchange ActiveSync 장치를 그룹화할 수 없습니다.  **모든 EAS 관리 장치** 그룹이 그룹에서 보고서 보기로 변환됩니다.
-  보고서에서 그룹으로 피벗하는 기능을 사용할 수 없습니다.
-  사용자 지정 그룹을 알림 규칙의 대상으로 지정하는 기능을 사용할 수 없습니다.

### 이러한 변경에 대해 준비하려면 어떻게 해야 하나요?
 이러한 전환을 용이하게 할 수 있도록 다음 작업을 권장합니다.
 
- 마이그레이션 전에 원치 않거나 필요하지 않은 Intune 그룹 정리.
- 그룹에서 제외 사용을 평가하고 제외를 사용할 필요가 없도록 또는 고급 규칙을 사용하여 같은 목적을 달성할 수 있도록 그룹을 다시 설계하는 방법을 고려.
-  Azure AD에서 그룹을 만들 수 있는 권한이 없는 관리자인 경우에는 Azure AD 관리자에게 **Intune 서비스 관리자** Azure AD 역할에 권한을 추가할 것을 요청.

또한 다음과 같이 Azure AD 보안 그룹에 대해 자세히 알아볼 수 있습니다.
-  개요는 [Azure Active Directory 그룹을 사용하여 리소스에 대한 액세스 관리](https://azure.microsoft.com/en-us/documentation/articles/active-directory-manage-groups/)를 참조하세요.
-  Azure AD 그룹을 만들고 관리하는 방법에 대한 자세한 내용은 [Azure Active Directory에서 그룹 관리](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-manage-groups/)를 참조하세요.
-  보안 그룹에 대한 고급 규칙과 관련한 자세한 내용은 [특성을 사용하여 고급 규칙 만들기](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/)를 참조하세요.

> [!NOTE]
Azure AD 보안 그룹 설명서에서는 장치에 대한 그룹을 만드는 내용은 설명하지 않는다는 점을 알 수 있을 것입니다. 해당 기능은 Intune 그룹 마이그레이션이 시작되기 전에 Azure AD에서 사용하도록 설정됩니다.

## 마이그레이션 세부 정보
다음은 Intune 그룹을 Azure AD 보안 그룹으로 마이그레이션하는 방법에 대한 세부 정보입니다.

### 기존 그룹 마이그레이션

| 마이그레이션되는 Intune 그룹...|...마이그레이션된 Azure AD 보안 그룹|
|-----------------------------------------------------------------------|-------------------------------------------------------------|
|Intune 정책에서 대상으로 하는 정적 사용자 그룹|동일한 사용자를 포함하는 정적 Azure AD 보안 그룹|
|Intune 정책에서 대상으로 하는 동적 사용자 그룹|Azure AD 보안 그룹 계층 구조가 있는 정적 Azure AD 보안 그룹|
|Intune 정책에서 대상으로 하는 정적 장치 그룹|장치가 포함된 정적 Azure AD 보안 그룹|
|Intune 정책에서 대상으로 하는 장치 특성이 있는 동적 장치 그룹|장치 특성이 있는 동적 Azure AD 보안 그룹|
|포함 조건이 있는 그룹|그룹 + 포함 조건이 Intune에서 허용한 정적/동적 멤버를 포함하는 별도의 정적 Azure AD 보안 그룹|
|제외 조건이 있는 그룹|이러한 그룹은 마이그레이션되지 않습니다. Azure AD에서 정적 그룹을 만드는 동안 제외 조건은 지원되지 않습니다. 제외 조건은 Azure AD에서 동적 그룹을 만들 때 사용할 수 있습니다.|
|Intune 정책에서 사용하는 기본 그룹 **모든 사용자**, **그룹화되지 않은 사용자**, **모든 장치**, **그룹화되지 않은 장치**, **모든 컴퓨터**, **모든 모바일 장치**, **모든 MDM 관리 장치** 및 **모든 EAS 관리 장치**  |Azure AD 보안 그룹. 사용되지 않는 기본 그룹은 고객이 필요한 경우 동적 그룹을 사용하여 만들어야 합니다.|

### 계층 구조 보기의 변경 내용
Intune의 Intune 부모-자식 관계에서 그룹의 계층 구조 보기가 상위 집합-하위 집합 관계였지만, Azure AD에서는 그렇지 않습니다. 자식은 부모에게 없는 멤버를 가질 수 있습니다. 또한 그룹은 Azure AD에서 본질적으로 순환될 수 있습니다. 즉, 부모 그룹이 자식 그룹의 자식일 수 있습니다.

### 마이그레이션 중 특성 변환
특성은 그룹을 정의하는 데 사용될 수 있는 장치 속성입니다. 이 표에는 이러한 조건이 Azure AD 보안 그룹으로 마이그레이션되는 방법이 설명되어 있습니다.

| Intune 특성|Azure AD 특성|
|-----------------------------------------------------------------------|-------------------------------------------------------------|
|장치 그룹에 대한 OU(조직 구성 단위) 특성|동적 그룹에 대한 OU 특성. 특성 값은 보기 위한 테넌트 구성 요소 중 하나로 추가하여 각 테넌트와 관련된 관리자에게 제공됩니다.|
|장치 그룹에 대한 도메인 이름 특성|동적 그룹에 대한 도메인 이름 특성. 특성 값은 보기 위한 테넌트 구성 요소 중 하나로 추가하여 각 테넌트와 관련된 관리자에게 제공됩니다.|
|사용자 그룹에 대한 특성으로서의 보안 그룹|그룹은 Azure AD 동적 쿼리에서 특성일 수 없습니다. 동적 그룹은 사용자 관련 특성 또는 장치별 특성만 포함할 수 있습니다.|
|사용자 그룹에 대한 관리자 특성|동적 그룹의 *관리자* 특성에 대한 고급 규칙|
|부모 사용자 그룹의 모든 사용자|해당 그룹을 멤버로 포함하는 정적 그룹|
|부모 장치 그룹의 모든 모바일 장치|해당 그룹을 멤버로 포함하는 정적 그룹|
|Microsoft Intune 직접 관리를 통해 관리하는 모든 모바일 장치|동적 그룹에 대한 값으로 'MDM'을 포함하는 관리 유형 특성|
|EAS에서 관리하는 모든 모바일 장치|Azure AD에서 EAS 장치는 그룹화할 수 없습니다. **모든 EAS 관리 장치** 그룹이 그룹에서 보고서 보기로 변환됩니다.|
|정적 그룹 내의 중첩 그룹 |정적 그룹 내의 중첩 그룹|
|동적 그룹 내의 중첩 그룹|중첩 수준이 하나인 동적 그룹|


## 정책 마이그레이션
그룹 마이그레이션이 수행되는 동안 Intune 콘솔에서 정책 관리를 계속합니다. Intune 콘솔에는 그룹을 관리하는 Azure 관리 콘솔에 연결되는 링크가 있습니다. 정책은 이전 Intune 그룹과 병렬 구조를 이루는 마이그레이션된 Azure AD 보안 그룹에 계속 배포됩니다.

모든 Intune 기능이 Azure 관리 포털로 마이그레이션되면(대략 2017년 1분기) Azure 관리 포털에서 정책 및 그룹을 관리하게 됩니다.

     
### 참고 항목
[Azure Active Directory 그룹을 사용하여 리소스에 대한 액세스 관리](https://azure.microsoft.com/en-us/documentation/articles/active-directory-manage-groups/)

[Azure Active Directory에서 그룹 관리](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-manage-groups/)

[특성을 사용하여 고급 규칙 만들기](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/)



<!--HONumber=Oct16_HO2-->


