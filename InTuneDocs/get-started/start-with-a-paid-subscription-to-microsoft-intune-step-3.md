---
title: "사용자 추가 및 권한 부여 | Microsoft Intune"
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
ms.reviewer: angrobe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 18d31a306549bae6dd44ab78d1dd08649ee71158


---

# <a name="add-users-and-give-administrative-permission-to-intune"></a>Intune에 사용자를 추가하고 관리 권한 부여

관리자는 사용자를 직접 추가할 수도 있고 온-프레미스 Active Directory에서 사용자를 동기화할 수도 있습니다. 추가된 사용자는 장치를 등록하고 회사 리소스에 액세스할 수 있습니다. *테넌트 관리자*, *서비스 관리자*, *장치 등록 관리자 권한* 등의 추가 권한을 사용자에게 제공할 수도 있습니다.

이 항목의 정보를 참조하면 다음 작업을 수행할 수 있습니다.

- [Intune에 사용자 추가](#add-users-to-intune)
- 다음을 비롯한 [추가 Intune 권한 부여](#grant-intune-permissions):
  - [테넌트 관리자](#tenant-administrator)
  - [서비스 관리자](#service-administrator)
  - [장치 등록 관리자](#device-enrollment-managers)

## <a name="add-users-to-intune"></a>Intune에 사용자 추가
[Office 365 포털](http://go.microsoft.com/fwlink/p/?LinkId=698854)을 통해 Intune 구독에 사용자를 수동으로 추가할 수 있으며, 이러한 사용자에게는 Intune 라이선스가 자동으로 할당되지 않습니다. 대신, 나중에 Intune 테넌트 관리자가 Office 365 포털에서 사용자에게 라이선스를 할당하도록 사용자 계정을 편집해야 합니다. 관련 지침은 [Office 365 포털에 개별적으로 또는 대량으로 사용자 추가](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)를 참조하세요.

### <a name="sync-active-directory-and-add-users-to-intune"></a>Active Directory를 동기화하고 Intune에 사용자 추가
온-프레미스 Active Directory에서 Microsoft Azure AD(Azure Active Directory)로 Intune 사용자를 포함한 사용자 계정을 가져오도록 디렉터리 동기화를 구성할 수 있습니다. 온-프레미스 Active Directory 서비스를 모든 Azure Active Directory 기반 서비스와 연결하면 사용자 ID를 훨씬 간편하게 관리할 수 있습니다. 사용자에게 친숙하고 간편한 인증 환경을 제공하도록 Single Sign-On 기능을 구성할 수도 있습니다. 같은 [Azure AD 테넌트](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/)를 여러 서비스와 연결하면 이전에 동기화했던 사용자 계정을 모든 클라우드 기반 서비스에 사용할 수 있습니다.

### <a name="how-to-sync-on-premises-users-with-azure-ad"></a>Azure AD와 온-프레미스 사용자를 동기화하는 방법
Azure AD와 사용자 계정을 동기화하기 위해 필요한 유일한 도구는 [Azure AD Connect 마법사](https://www.microsoft.com/download/details.aspx?id=47594)입니다. Azure AD Connect 마법사는 온-프레미스 ID 인프라를 클라우드에 연결하도록 안내하는 간단한 환경을 제공합니다.  토폴로지 및 요구 사항(디렉터리 하나/여러 개, 암호 동기화 또는 페더레이션)을 선택하면 마법사에서 연결을 작동하고 실행하는 데 필요한 모든 구성 요소를 배포하고 구성합니다. 여기에는 동기화 서비스, AD FS(Active Directory Federation Services) 및 Azure AD PowerShell 모듈이 포함됩니다.

> [!TIP]
> Azure AD Connect에는 이전에 Dirsync 및 Azure AD Sync로 출시된 기능이 포함됩니다. [디렉터리 통합](http://technet.microsoft.com/library/jj573653.aspx)에 대해 자세히 알아봅니다. 로컬 디렉터리에서 Azure AD로 사용자 계정을 동기화하는 이점에 대한 자세한 내용은 [Active Directory와 Azure AD의 유사성](http://technet.microsoft.com/library/dn518177.aspx)을 참조하세요.

## <a name="grant-intune-permissions"></a>Intune 권한 부여

Intune 구독에 사용자를 추가한 후에는 사용자 계정 몇 개에 관리 권한을 부여하는 것이 좋습니다. Intune를 관리하려면 세 가지 유형의 Intune 권한을 사용자에게 부여할 수 있습니다.
-   **테넌트 관리자**: Office 365 포털을 사용하여 이 관리자 유형에게 대금 청구, 클라우드 저장소, Intune을 사용할 수 있는 사용자 관리 등의 구독 관리 권한을 할당합니다.
-   **서비스 관리자**: Microsoft Intune 관리자 콘솔을 사용하여 이 관리자 유형에게 장치/컴퓨터 관리, 정책/앱 배포, 보고서 실행 등의 일상적인 태스크 권한을 할당합니다.
-   **장치 등록 관리자**: Microsoft Intune 관리자 콘솔을 사용하여 이 관리자 유형에게 장치/컴퓨터 관리, 정책/앱 배포, 보고서 실행 등의 일상적인 태스크 권한을 할당합니다.


### <a name="tenant-administrator"></a>테넌트 관리자


테넌트 관리자에게는 관리할 수 있는 해당 사용자 및 작업에 대한 관리 범위를 정의하는 관리자 역할이 할당됩니다. 일부 서비스에서 일부 역할을 지원하지 않을 수 있지만 관리자 역할은 여러 Microsoft 클라우드 서비스 간에 공통적입니다. Intune에서는 다음 역할을 사용합니다.
- **전역 관리자** - Intune의 모든 관리 기능에 액세스할 수 있습니다. 기본적으로는 Intune을 등록하는 사람이 전역 관리자가 됩니다. 다른 관리 역할을 할당할 수 있는 관리자는 전역 관리자뿐입니다. 조직에 전역 관리자가 여러 명 있을 수 있습니다. 하지만 업무상의 위험을 줄이려면 회사에서 이 역할을 소수의 인원에게만 제공하는 것이 좋습니다.
- **대금 청구 관리자** - 구매를 진행하고, 구독 및 지원 티켓을 관리하고, 서비스 상태를 모니터링합니다.
- **암호 관리자** - 암호를 재설정하고, 서비스 요청을 관리하고, 서비스 상태를 모니터링합니다. 암호 관리자는 사용자의 암호 재설정만 수행할 수 있습니다.
- **서비스 지원 관리자** - Microsoft에 대한 지원 요청을 열고 서비스 대시보드와 메시지 센터를 확인합니다. 이 관리자는 지원 티켓을 열고 읽는 권한 외에는 "보기 전용" 권한을 소유합니다.
- **사용자 관리 관리자** - 암호를 재설정하고, 서비스 상태를 모니터링하고, 사용자 계정을 추가/삭제하고, 서비스 요청을 관리합니다. 사용자 관리 관리자는 전역 관리자를 삭제하거나, 다른 관리 역할을 만들거나, 대금 청구/전역/서비스 관리자의 암호를 재설정할 수 없습니다.

기본적으로 Microsoft Intune 구독을 생성하는 데 사용하는 계정은 전역 관리자 역할이 있는 테넌트 관리자입니다. 테넌트 관리자는 Intune 관리자 콘솔을 사용하여 Intune에 대한 구독을 관리하고 [Office 365 포털](http://go.microsoft.com/fwlink/p/?LinkId=698854)에서 테넌트 관리자를 할당합니다. 전역 관리 역할을 소유한 테넌트 관리자로 포털에 액세스한 다음 첫 번째 서비스 관리자를 할당합니다. 일상적인 관리 작업에는 테넌트 관리자를 사용하지 않는 것이 가장 좋습니다. 테넌트 관리자는 Intune 라이선스가 없어도 Intune 관리자 콘솔에 액세스할 수 있습니다. 테넌트 관리자는 Microsoft 클라우드 서비스 간에 일반적인 개념입니다. Intune을 구독할 경우 제공되는 서비스가 Azure AD의 테넌트입니다. 자세한 내용은 [Azure AD 디렉터리란?](http://technet.microsoft.com/library/jj573650.aspx)에서 Azure AD 테넌트 섹션을 참조하세요.

테넌트 관리자는 [Office 365 포털](http://go.microsoft.com/fwlink/p/?LinkId=698854)을 사용하여 구독을 관리하며, 관리자 역할에서 허용할 경우 다음 태스크도 수행합니다.

- 사용자 계정을 관리하고 온-프레미스 Active Directory에서의 디렉터리 동기화를 구성합니다.
- 보안 그룹이라는 사용자 그룹을 관리합니다.
- Intune용 라이선스를 사용자에게 할당합니다.
- 사용자가 로그인할 때 사용하는 구독의 도메인 이름(예: contoso.com)을 구성합니다.
- 라이선스, 클라우드 저장소 공간 등과 관련된 대금 청구 및 구매를 관리합니다.
- Intune 서비스의 상태를 확인할 수 있는 링크를 찾습니다.

Office 365 포털에 액세스하려면 계정의 로그인 상태가 **허용**이어야 합니다. 이 상태는 구독에 대한 라이선스 보유와는 다른 문제입니다. 기본적으로 모든 사용자 계정은 **허용**됩니다. 관리자 권한이 없는 사용자는 Office 365 포털을 사용하여 Intune 암호를 재설정할 수 있습니다.

### <a name="service-administrator"></a>서비스 관리자

기본적으로 Intune에서는 서비스 관리자를 할당하지 않습니다. 대신 구독에 대한 첫 번째 서비스 관리자를 할당하려면 전역 관리자 역할이 있는 테넌트 관리자를 사용해야 합니다. 서비스 관리자는 [Intune 관리자 콘솔](https://manage.microsoft.com/)을 사용하여 Intune의 일상적인 태스크를 관리합니다. 관리자 콘솔에서 서비스 관리자를 할당합니다. 서비스 관리자는 Intune 라이선스가 있어야 관리 콘솔에 액세스할 수 있습니다.

서비스 관리자에게는 다음 사용 권한 중 하나가 할당됩니다.
- **모든 권한**: Intune 관리자 콘솔의 모든 영역에 제한 없이 액세스할 수 있으며 다른 서비스 관리자를 추가/관리할 수 있습니다.
- **읽기 전용 액세스**: Intune 관리자 콘솔의 모든 영역에 대한 읽기 권한이 제공되며 데이터를 수정할 수는 없지만 보고서를 실행할 수는 있습니다.
- **기술 지원팀 - 그룹 노드**: 서비스 관리자가 기술 지원팀 시나리오와 관련된 태스크만 수행할 수 있습니다. [관리자 역할에 따라 Intune 콘솔 보기 사용자 지정](/intune/deploy-use/control-what-admins-can-see-in-the-microsoft-intune-admin-console)을 참조하세요.

서비스 관리자는 이 포털을 사용하여 다음을 비롯한 일상적인 작업을 관리합니다.

- 컴퓨터 및 모바일 장치용 정책 만들기/관리
- 소프트웨어 업데이트 및 앱 업로드/배포
- 컴퓨터에서 Endpoint Protection 관리
- 장치 상태 확인 및 보고서 실행

### <a name="device-enrollment-managers"></a>장치 등록 관리자

장치 등록 관리자는 사용자가 없는 장치를 여러 개 등록할 수 있는 추가 권한이 있는 표준 사용자 계정입니다. 기본적으로 각 Intune 사용자는 최대 15개의 장치를 등록할 수 있습니다. 관리자는 특정 사용자 계정에 장치 등록 관리자 권한을 제공할 수 있습니다. 해당 계정은 많은 회사 소유 장치를 등록할 수 있습니다. 이러한 기능은 일시적으로 사용자에게 장치를 할당하거나, 사용자와 장치 간 연결이 필요하지 않은 키오스크 모드로 작업할 때 유용합니다. 자세한 내용은 [장치 등록 관리자](https://docs.microsoft.com/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)를 참조하세요.

>[!div class="step-by-step"]

>[&larr;**도메인 설정**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**Intune 라이선스 관리** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-4.md)  



<!--HONumber=Dec16_HO2-->


