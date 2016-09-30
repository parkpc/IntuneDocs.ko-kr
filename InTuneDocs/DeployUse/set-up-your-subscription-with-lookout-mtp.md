---
title: "Lookout MTP 구독 설정 | Microsoft Intune"
description: "이 항목에서는 Lookout MTP를 구성하는 방법을 자세히 설명합니다."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 8477a2f1-2e1d-4d42-8bcb-e1181cc900bb
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ba2196ff03975df1f8969e1522f7af459343694d
ms.openlocfilehash: 530a34c7c75a4fa73cbb62873e2d28883b91b57e


---

# Lookout Mobile Threat Protection 구독 설정
Lookout MTP 서비스 구독을 준비하기 위해 Lookout 지원 팀(enterprisesupport@lookout.com)은 다음과 같은 Azure AD(Azure Active Directory) 구독 정보가 필요합니다. 

* **Azure AD 테넌트 ID**
* Lookout MTP 콘솔에 **전체** 액세스를 하기 위한 **Azure AD 그룹 개체 ID**
* Lookout MTP 콘솔에 **제한된** 액세스를 하기 위한 **Azure AD 그룹 개체 ID**(선택 사항)

다음 섹션에 따라 Lookout 지원 팀이 지원에 필요한 정보를 모읍니다.  

## Azure AD 정보 가져오기
### Azure AD 테넌트 ID
[Azure AD 관리 포털](https://manage.windowsazure.com)에 로그인한 후 구독을 선택합니다. 

![테넌트 이름이 나타난 Azure AD 페이지의 스크린샷](../media/mtp/aad_tenant_name.png) 구독 이름을 선택하면 결과로 표시되는 URL에 구독 ID가 포함됩니다.  구독 ID를 찾는 데 문제가 있으면 [Microsoft 지원 문서](https://support.office.com/en-us/article/Find-your-Office-365-tenant-ID-6891b561-a52d-4ade-9f39-b492285e2c9b?ui=en-US&rs=en-US&ad=US)ID를 찾는 방법에 대한 팁을 확인하세요.   
### Azure AD 그룹 ID 가져오기
Lookout MTP 콘솔은 두 가지 수준의 액세스를 지원합니다.  
* **모든 권한:** Azure AD 관리자는 모든 권한을 가질 사용자 그룹을 만들 수 있으며 경우에 따라 제한된 권한을 가질 사용자 그룹도 만들 수 있습니다.  이러한 그룹의 사용자만 **Lookout MTP 콘솔**에 로그인할 수 있습니다.
* **제한된 액세스:** 이 그룹의 사용자는 Lookout MTP 콘솔에서 구성 및 등록과 관련된 몇몇 모듈에 액세스할 수 없고 Lookout MTP 콘솔의 **보안 정책** 모듈에 읽기 전용으로 액세스할 수 있습니다.  

권한에 대한 자세한 내용은 Lookout 웹 사이트의 [이 문서](https://personal.support.lookout.com/hc/en-us/articles/114094105653)를 참조하세요.

**그룹 개체 ID**는 **Azure AD 관리 콘솔**에서 해당 그룹의 **속성** 페이지에 있습니다.

![GroupID 필드가 강조 표시된 속성 페이지의 스크린샷](../media/mtp/aad_group_object_id.png)

이 정보를 수집했으면 Lookout 지원 팀(메일: enterprisesupport@lookout.com)에 문의합니다.

Lookout 지원 팀은 주요 담당자와 함께 수집한 정보를 사용하여 구독을 등록하고 Lookout MTP 엔터프라이즈 계정을 만듭니다.


## Lookout MTP 구독 구성
### 1 단계: MTP 설정
Lookout 지원 팀이 Lookout MTP 엔터프라이즈 계정을 만들면 Lookout MTP 콘솔에 로그인할 수 있습니다.   Lookout에서 사용자 회사의 주요 담당자에게 로그인 링크(url:https://aad.lookout.com/les?action=consent)가 담긴 메일이 전송됩니다.

처음 Lookout MTP 콘솔에 로그인할 때는 Azure AD 역할이 전역 관리자인 사용자 계정을 사용해야 합니다. Lookout MTP에서 Azure AD 테넌트를 등록하려면 이 역할이 필요하기 때문입니다.   이후 로그인에서 사용자는 이 수준의 Azure AD 권한이 필요하지 않습니다.  이번에 처음 로그인할 때 동의 페이지가 표시됩니다. **동의**를 선택하여 등록을 완료합니다.

![Lookout MTP 콘솔에 처음 로그인할 때의 페이지 스크린샷](../media/mtp/lookout_mtp_initial_login.png) 수락하고 동의하면 사용자가 Lookout MTP 콘솔로 리디렉션됩니다. 처음 등록한 이후부터는 URL https://aad.lookout.com에서 로그인할 수 있습니다.

로그인 문제가 발생하면 [문제 해결 문서](https://docs.microsoft.com/en-us/intune/troubleshoot/troubleshooting-lookout-integration)를 참조하세요.

다음 단계에서는 [Lookout MTP 콘솔](https://aad.lookout.com)에서 Lookout MTP를 설정하기 위해 수행해야 하는 작업을 간략하게 설명합니다.

### 2단계: Intune Connector 구성

1.  Lookout MTP 콘솔에서 **시스템** 모듈로 이동한 후 **커넥터** 탭과 **Intune**을 차례로 선택합니다.

  ![Connector 탭이 열려 있고 Intune 옵션이 강조 표시된 Lookout MTP 콘솔의 스크린샷](../media/mtp/lookout_mtp_setup-intune-connector.png)

2.  연결 설정 옵션에서 하트비트 주기(단위: 분)를 구성합니다.  Intune Connector가 이제 준비되었습니다.  

  ![구성된 하트비트 주기를 보여 주는 연결 설정 탭의 스크린샷](../media/mtp/lookout-mtp-connection-settings.png)

### 3단계: 등록 그룹 구성
**등록 관리** 옵션에서 Lookout에 등록해야 하는 장치 소유자를 지정합니다. 처음에는 소규모의 사용자를 테스트하여 통합 과정에 익숙해지는 것이 좋습니다.  테스트 결과에 만족한다면 사용자 그룹을 더 등록하여 확장할 수 있습니다.

그룹을 등록하려면 먼저 Azure AD 보안 그룹을 정의합니다. 이 그룹을 Lookout MTP에 가장 먼저 등록하는 것이 좋습니다. Lookout MTP 콘솔에서 Azure AD에 그룹을 만들었으면 등록할 Azure AD 보안 그룹 **표시 이름**을 **등록 관리** 옵션에서 추가합니다.

사용자가 등록 그룹에 속해 있으면 Azure AD에서 식별되고 지원되는 장치는 모두 등록되어 Lookout MTP에서 활성화할 수 있습니다.  지원되는 장치에서 처음으로 Lookout for Work 앱을 열면 장치가 Lookout MTP에서 활성화됩니다.
![Intune Connector 등록 페이지의 스크린샷](../media/mtp/lookout-mtp-enrollment.png)

가장 좋은 방법은 새 장치의 확인 간격을 기본값(5분)으로 하는 것입니다.

>[!IMPORTANT]
> 표시 이름은 대/소문자를 구분합니다.  Azure Portal에서 보안 그룹의 **속성** 페이지에 나타난 **표시 이름**을 사용합니다. 유의할 점은 아래 그림에서 보안 그룹의 **속성** 페이지에 나온 표시 이름이 캐멀(camel) 문자라는 것입니다.  그러나 제목이 모두 소문자로 표시되기 때문에 Lookout MTP 콘솔에 입력해서는 안 됩니다.
>![Azure Portal의 Azure Active Directory 서비스 속성 페이지의 스크린샷](../media/mtp/aad-group-display-name.png)

현재 릴리스에는 다음과 같은 제한 사항이 있습니다.  
* 그룹 표시 이름이 유효한지 검사하지 않습니다.  Azure AD 보안 그룹 값으로는 Azure Portal의 **표시 이름** 필드의 값을 사용하세요.
* 그룹 내에 또 다른 그룹을 만드는 것은 현재 지원되지 않습니다.  지정된 Azure AD 보안 그룹에는 사용자만 포함할 수 있으며 중첩된 그룹을 포함할 수 없습니다.


### 4단계: 상태 동기화 구성
**상태 동기화** 옵션에서 Intune에 전송해야 할 데이터 유형을 지정합니다.  이제 Lookout Intune 통합이 제대로 작동하도록 장치 상태와 위협 상태를 사용하도록 올바로 설정해야 합니다.  기본적으로 모두 사용하도록 설정됩니다.
### 5단계: 오류 보고서를 메일로 받는 사람의 정보 구성
**오류 관리** 옵션에서 오류 보고서를 받아야 하는 메일 주소를 입력합니다.

![Intune Connector 오류 관리 페이지의 스크린샷](../media/mtp/lookout-mtp-connector-error-notifications.png)

### 6단계: 메일 알림 구성
위협 경고를 메일로 받으려면 알림을 받아야 하는 사용자 계정으로 [Lookout MTP 콘솔](https://aad.lookout.com)에 로그인합니다. **시스템** 모듈의 **기본 설정** 탭에서 원하는 알림을 선택한 후 **켬**으로 설정합니다. 변경 내용을 저장합니다.

![사용자 계정이 표시된 기본 설정 페이지의 스크린샷](../media/mtp/lookout-mtp-email-notifications.png) 이제 메일 알림을 받지 않으려면 알림을 **끔**으로 설정하고 변경 내용을 저장합니다.
### 7단계: 위협 분류 구성
Lookout MTP는 다양한 종류의 모바일 위협을 분류합니다. [Lookout MTP 위협 분류](http://personal.support.lookout.com/hc/en-us/articles/114094130693)에는 기본 위험 수준이 지정되어 있습니다. 이 수준은 언제든지 회사 요구 사항에 맞게 변경할 수 있습니다.

![위협 및 분류를 보여 주는 정책 페이지의 스크린샷](../media/mtp/lookout-mtp-threat-classification.png)

>[!IMPORTANT]
> 여기에 지정된 위험 수준은 MTP의 중요한 측면으로, 런타임 시 이러한 위험 수준에 따라 Intune 통합에서 장치 규정 준수를 측정하기 때문입니다. 즉, Intune 관리자가 장치에 최소 수준의 활성 위협(높음, 중간 또는 낮음)이 있다면 장치가 규정을 준수하지 않는 것으로 식별하도록 정책 규칙을 설정할 수 있습니다. MTP의 위협 분류 정책을 통해 장치의 규정 준수 여부가 Intune에서 바로 측정됩니다.

## 등록 점검
설치가 끝나면 Lookout MTP가 지정된 등록 그룹에 해당하는 장치에 Azure AD를 폴링하기 시작합니다.  등록된 장치에 대한 정보는 장치 모듈에서 찾을 수 있습니다.  장치의 초기 상태는 보류 중으로 표시됩니다.  장치 상태는 Lookout for Work 앱을 장치에서 설치한 후 열고 활성화하면 변경됩니다.  Lookout for Work 앱을 장치에 푸시하는 방법에 대한 내용은 [Lookout for work 앱 구성 및 배포](configure-and-deploy-lookout-for-work-apps.md) 항목을 참조하세요.
## 다음 단계
[Intune에서 Lookout MTP 연결](enable-lookout-mtp-connection-in-intune.md)



<!--HONumber=Sep16_HO3-->

