---
title: "IOS 장치용 Apple School Manager 프로그램 등록 설정"
titleSuffix: Intune on Azure
description: "Intune을 사용하여 회사 소유 iOS 장치에 대해 Apple School Manager 프로그램 등록을 설정하는 방법을 알아봅니다.\""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 73556209c88759ffe0747d9927cbcbb49600e0c0
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2017
---
# <a name="enable-ios-device-enrollment-with-apple-school-manager"></a>Apple School Manager를 통해 iOS 장치 등록 기능 사용

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

IT 관리자는 이 항목의 정보를 참조하여 [ASM(Apple School Manager)](https://school.apple.com/) 프로그램을 통해 구매한 iOS 장치를 등록할 수 있습니다. Microsoft Intune은 ASM 장치를 관리에 등록하는 등록 프로필을 "무선"으로 배포할 수 있습니다. 따라서 관리자가 각 관리 장치를 직접 조작할 필요가 없습니다. ASM 프로필에는 설정 도우미 옵션을 비롯하여 등록 중 장치에 적용되는 관리 설정이 포함되어 있습니다.

**ASM 등록 단계**
1. [ASM 토큰을 가져오고 장치 할당](#get-the-asm-token-and-assign-devices)
2. [등록 프로필 만들기](#create-an-apple-enrollment-profile)
3. [학교 데이터 동기화 연결](#connect-school-data-sync)(선택 사항)
4. [ASM 관리 장치 동기화](#sync-asm-managed-devices)
5. [장치에 ASM 프로필 할당](#assign-an-asm-profile-to-devices)
6. [사용자에게 장치 배포](#distribute-devices-to-users)

>[!NOTE]
>ASM 등록을 Apple의 [DEP(장치 등록 프로그램)](device-enrollment-program-enroll-ios.md) 또는 Intune의 [장치 등록 관리자](device-enrollment-manager-enroll.md) 계정과 함께 사용할 수는 없습니다.

## <a name="get-the-apple-asm-token-and-assign-devices"></a>ASM 토큰을 가져오고 장치 할당

회사 소유 iOS 장치를 ASM(Apple School Manager)에 등록하려면 Apple의 ASM 토큰(.p7m) 파일이 필요합니다. Intune에서는 이 토큰을 통해 ASM 참가 장치에 대한 정보를 동기화할 수 있습니다. 또한 Apple에 등록 프로필을 업로드하고 이러한 프로필에 장치를 할당할 수 있습니다. Apple 포털을 사용하는 동안 관리할 장치 일련 번호를 할당할 수도 있습니다.

**전제 조건**
- [Apple MDM Push Certificate](apple-mdm-push-certificate-get.md)
- [Apple School Management](http://school.apple.com)에 등록

**1단계. Apple ASM 토큰을 만드는 데 필요한 Intune 공개 키 인증서를 다운로드합니다.**<br>
1. Azure [Intune 포털](https://aka.ms/intuneportal)에서 **장치 등록**을 선택한 다음 **등록 프로그램 토큰**을 선택합니다.
2. **등록 프로그램 토큰** 블레이드에서 **공개 키 다운로드**를 선택하여 암호화 키(.pem) 파일을 다운로드하고 로컬로 저장합니다. .pem 파일은 Apple School Manager 포털에서 트러스트 관계 인증서를 요청하는 데 사용됩니다.

**2단계. ASM 토큰을 다운로드하오고 장치를 할당합니다.**<br>
**Apple School Manager를 통해 토큰 만들기**를 선택하고 회사 Apple ID로 로그인합니다. 이 Apple ID를 사용하여 ASM 토큰을 갱신할 수 있습니다.

   1.  [Apple School Manager 포털](https://school.apple.com)에서 **MDM 서버**로 이동한 다음 오른쪽 위에 있는 **MDM 서버 추가**를 선택합니다.
   2.  **MDM 서버 이름**을 입력합니다. 서버 이름은 참조용으로 MDM(모바일 장치 관리) 서버를 식별하기 위한 것으로, Microsoft Intune 서버의 이름 또는 URL이 아닙니다.
   3.  Apple 포털에서 **파일 업로드...** 를 선택하고 .pem 파일이 있는 위치로 이동한 다음 오른쪽 아래에 있는 **MDM 서버 저장**을 선택합니다.
   4.  **토큰 가져오기**를 선택하고 컴퓨터에 서버 토큰(.p7m) 파일을 다운로드합니다.
   5. **장치 할당**으로 이동한 다음 **장치 선택**에서 **일련 번호**, **주문 번호**를 수동으로 입력하거나 **CSV 파일 업로드**를 선택합니다.
   6.   **서버에 할당** 작업을 선택하고 작성한 **MDM 서버**를 선택합니다.
   7. **장치 선택**방법을 지정하고, 장치 정보를 제공한 다음, 장치 **일련번호**, **주문 번호**또는 **CSV 파일 업로드**에 따라 세부 정보를 지정합니다.
   8. **서버에 할당**을 선택하고 Microsoft Intune에 대해 지정된 &lt;ServerName&gt;을 선택한 다음 **확인**을 선택합니다.

**3단계. ASM 토큰을 만드는 데 사용되는 Apple ID를 입력합니다.**<br>이 ID는 Apple ASM 토큰을 갱신하는 데 사용해야 하며, 나중에 참조할 수 있도록 저장됩니다.

**4단계. 토큰을 찾아서 업로드합니다.**<br>
인증서(.p7m) 파일로 이동한 후 **열기**를 선택하고 **업로드**를 선택합니다. Intune은 Apple에서 ASM 장치를 자동으로 동기화합니다.

## <a name="create-an-apple-enrollment-profile"></a>Apple 등록 프로필 만들기
장치 등록 프로필은 등록 중에 장치 그룹에 적용되는 설정을 정의합니다.

1. Intune 포털에서 **장치 등록**을 선택한 다음 **Apple 등록**을 선택합니다.
2. **등록 프로그램** 아래에서 **등록 프로그램 프로필**을 선택합니다.
3. **등록 프로그램 프로필** 블레이드에서 **만들기**를 선택합니다.
4. **등록 프로필 만들기** 블레이드에서 Intune 포털에 표시되는 프로필에 대한 **이름** 및 **설명**을 입력합니다.
5. **사용자 선호도**에서 이 프로필을 가진 장치가 사용자 선호도를 사용하여 등록되는지 사용하지 않고 등록되는지 선택합니다.

 - **사용자 선호도를 사용하여 등록** - 초기 설치 작업을 진행할 때 장치에 사용자 정보를 등록해야 합니다. 그러면 회사 데이터와 메일에 액세스하도록 허용할 수 있습니다. 사용자가 관리되는 Apple ID를 사용하여 로그인하는 ASM 관리 장치에 대한 사용자 선호도를 선택합니다.

 >[!NOTE]
 >MFA(다단계 인증)는 사용자 선호도가 있는 ASM 장치에 등록하는 동안 작동하지 않습니다. 등록 후 MFA는 이러한 장치에서 예상대로 작동합니다.

  Apple School Manager의 공유 iPad 모드에서는 사용자가 사용자 선호도를 사용하여 등록해야 합니다.

 >[!NOTE]
    >사용자 선호도를 사용하는 ASM에서는 사용자 토큰을 요청하려면 [WS-Trust 1.3 사용자 이름/혼합 끝점](https://technet.microsoft.com/library/adfs2-help-endpoints)을 사용하도록 설정해야 합니다. [WS-Trust 1.3에 대해 자세히 알아보세요](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

 - **사용자 선호도를 사용하지 않고 등록**: 장치에 사용자 정보를 등록하지 않습니다. 로컬 사용자 데이터에 액세스하지 않고도 작업을 수행하는 장치에 대해 이 정보를 사용합니다. 기간 업무 앱을 설치하는 데 사용하는 회사 포털 앱 등 사용자 선호도가 필요한 앱은 작동하지 않습니다.

6. **장치 관리 설정**을 선택합니다. 이러한 항목은 활성화 중에 설정되며, 변경하려면 장치를 초기화해야 합니다. 다음 프로필 설정을 구성한 후 **저장**을 선택합니다.

    - **감독됨** - 더 많은 관리 옵션을 사용할 수 있으며 기본적으로 활성화 잠금이 해제된 관리 모드입니다. 이 확인란을 비워 두면 관리 기능이 제한됩니다.

    - **등록 잠김** - (관리 모드 = 감독됨이어야 함) 관리 프로필 제거를 허용하는 iOS 설정이 해제됩니다. 이 확인란을 비워 두면 설정 메뉴에서 관리 프로필을 제거할 수 있습니다.

  - **공유 iPad** - (**사용자 선호도를 사용하여 등록** 및 **감독됨** 모드를 사용해야 함) 여러 사용자가 관리되는 Apple ID를 사용하여 등록된 iPad에 로그온할 수 있습니다. 관리되는 Apple ID는 Apple School Manager 포털에서 작성됩니다.

  >[!NOTE]
  >프로필에서 **공유 iPad** 모드를 사용하도록 설정한 후 **사용자 선호도** 또는 **감독됨** 모드를 **해제**로 설정하면 등록 프로필에 대해 공유 iPad 모드가 사용하지 않도록 설정됩니다.

  - **최대 캐시된 사용자 수** - (**공유 iPad** = **예**를 설정해야 함) 각 사용자에 대해 장치에 파티션을 만듭니다. 일정 기간 동안 장치를 사용할 가능성이 높은 학생 수를 값으로 설정하는 것이 좋습니다. 예를 들어 주당 학생 6명이 장치를 정기적으로 사용하는 경우 이 수를 6으로 설정합니다.  

    - **연결 허용** - iOS 장치를 컴퓨터와 동기화할 수 있는지 여부를 지정합니다. **인증서로 Apple Configurator 허용**을 선택한 경우 **Apple Configurator 인증서** 아래에서 인증서를 선택해야 합니다.

    - **Apple Configurator 인증서** - **연결 허용** 아래에서 **인증서로 Apple Configurator 허용**을 선택한 경우 가져올 Apple Configurator 인증서를 선택합니다.

7. **설정 도우미 설정**을 선택하고 다음 프로필 설정을 구성한 후 **저장**을 선택합니다.

    - **부서 이름** - 정품 인증을 하는 동안 사용자가 **구성 정보**를 탭하면 표시됩니다.

    - **부서 전화** - 정품 인증을 하는 동안 사용자가 도움 필요 단추를 클릭하면 표시됩니다.
    - **설정 도우미 옵션** - 이러한 설정은 설정 도우미 옵션에서 제외하는 경우 나중에 iOS **설정** 메뉴에서 지정할 수 있습니다.
        - **암호** - 정품 인증을 하는 동안 암호를 묻는 메시지가 표시됩니다. 장치가 보안된 상태가 아니거나 다른 방식으로 액세스가 제어된 상태(즉, 하나의 앱만 사용할 수 있도록 장치를 제한하는 키오스크 모드)가 아니면 항상 암호를 요구합니다.
        - **위치 서비스** - 이를 설정하면 정품 인증을 하는 동안 설치 도우미에서 서비스를 사용할지 묻는 메시지를 표시합니다.
        - **복원** - 이를 설정하면 정품 인증을 하는 동안 설치 도우미에서 iCloud 백업을 사용할지 묻는 메시지를 표시합니다.
        - **Apple ID** - 이 설정을 지정하면 Intune에서 ID 없이 앱을 설치하려고 할 때 iOS가 사용자에게 Apple ID를 묻습니다. Intune을 통해 설치한 앱을 비롯하여 iOS 앱 스토어 앱을 다운로드하려면 Apple ID가 필요합니다.
        - **사용 약관** - 이를 설정하면 정품 인증을 하는 동안 설치 도우미가 Apple의 약관에 동의하라는 메시지를 표시합니다.
        - **터치 ID** - 이 옵션을 사용하도록 설정하면 활성화하는 동안 설정 도우미에서 이 서비스를 확인하는 메시지가 표시됩니다.
        - **Apple Pay** - 이 옵션을 사용하도록 설정하면 활성화하는 동안 설정 도우미에서 이 서비스를 확인하는 메시지가 표시됩니다.
        - **확대/축소** - 이 옵션을 사용하도록 설정하면 활성화하는 동안 설정 도우미에서 이 서비스를 확인하는 메시지가 표시됩니다.
        - **Siri** - 이 옵션을 사용하도록 설정하면 활성화하는 동안 설정 도우미에서 이 서비스를 확인하는 메시지가 표시됩니다.
        - **진단 데이터** - 이 옵션을 사용하도록 설정하면 활성화하는 동안 설정 도우미에서 이 서비스를 확인하는 메시지가 표시됩니다.

8. 프로필 설정을 저장하려면 **등록 프로필 만들기** 블레이드에서 **만들기**를 선택합니다.

## <a name="connect-school-data-sync"></a>학교 데이터 동기화 연결
(선택 사항)ASM에서는 Microsoft SDS(학교 데이터 동기화)를 사용하여 학급 명단 데이터를 Azure AD(Active Directory)에 동기화할 수 있습니다. SDS를 사용하여 학교 데이터를 동기화하려면 다음 단계를 완료하세요.

1. **등록 프로그램 토큰** 블레이드에서 파란색 정보 배너 또는 **SDS 연결**을 선택합니다.
2. **Microsoft School Data Sync에서 이 토큰을 사용하도록 허용**을 선택하여 **허용**으로 설정합니다. Intune은 이 설정을 통해 Office 365에서 SDS와 연결할 수 있습니다.
3. ASM와 Azure AD 간의 연결을 사용하도록 설정하려면 **Microsoft School Data Sync 설정**을 선택합니다. [학교 데이터 동기화를 설정하는 방법](https://support.office.com/article/Install-the-School-Data-Sync-Toolkit-8e27426c-8c46-416e-b0df-c29b5f3f62e1)에 대해 자세히 알아보세요.
4. **확인**을 클릭하여 작업 내용을 저장하고 계속 진행합니다.

## <a name="sync-asm-managed-devices"></a>ASM 관리 장치 동기화
이제 Intune에 ASM 장치 관리 권한이 할당되었으므로 Intune을 ASM 서비스와 동기화하여 Intune 포털에서 관리 장치를 확인할 수 있습니다.

1. Intune 포털에서 **장치 등록**을 선택한 다음 **Apple 등록**을 선택합니다.
2. **등록 프로그램 장치** 아래에서 **동기화**를 선택합니다. 진행률 표시줄에 동기화를 다시 요청하기 전에 대기해야 하는 시간이 표시됩니다.

    허용 가능한 ASM 트래픽에 대한 Apple의 약관을 준수하기 위해 Intune에서는 다음과 같은 제한 사항을 적용합니다.
     -  전체 ASM 동기화는 7일마다 한 번씩만 실행할 수 있습니다. 전체 동기화 중 Intune은 Apple에서 일련 번호가 이전에 동기화되었는지 여부를 Intune에 할당한 모든 일련 번호를 새로 고칩니다. 전체 동기화를 이전 전체 동기화의 7일 이내에 시도하는 경우 Intune은 Intune에 나열되지 않은 일련 번호만 새로 고칩니다.
     -  모든 동기화 요청은 완료하는 데 15분이 주어집니다. 이 시간 동안 또는 요청이 성공될 때까지 **동기화** 단추는 비활성화됩니다.

>[!NOTE]
>**등록 프로그램 장치** 블레이드에서 프로필에 ASM 일련 번호를 할당할 수도 있습니다.

## <a name="assign-an-asm-profile-to-devices"></a>장치에 ASM 프로필 할당
Intune에서 관리하는 ASM 장치를 등록하려면 ASM 프로필을 할당해야 합니다.

1. Intune 포털에서 **장치 등록** > **Apple 등록**을 선택한 다음 **등록 프로그램 프로필**을 선택합니다.
2. **등록 프로그램 프로필** 목록에서 장치에 할당할 프로필을 선택한 다음 **장치 할당**을 선택합니다.
3. **할당**을 선택한 다음 이 프로필을 할당할 ASM 장치를 선택합니다. 다음 기준을 사용하여 필터링하면 ASM 사용 가능 장치를 확인할 수 있습니다.
  - **할당되지 않음**
  - **임의**
  - **&lt;ASM 프로필 이름&gt;**
4. 프로필을 할당할 장치를 선택합니다. 열 위의 확인란을 사용하면 나열된 장치를 1,000개까지 선택할 수 있습니다. **할당**을 클릭합니다. 1,000개보다 많은 장치를 등록하려면 할당 단계를 반복하여 모든 장치에 ASM 프로필을 할당합니다.

## <a name="distribute-devices-to-users"></a>사용자에게 장치 배포

이제 회사 소유 장치를 사용자에게 배포할 수 있습니다. 켜져 있는 iOS ASM 장치는 Intune에서 관리하도록 등록됩니다. 장치가 활성화되었으며 사용 중인 경우에는 장치를 초기화할 때까지 프로필을 적용할 수 없습니다.

### <a name="how-users-install-and-use-the-company-portal-on-their-devices"></a>사용자가 자신의 장치에서 회사 포털을 설치 및 사용하는 방법

사용자 선호도로 구성한 장치에서 회사 포털 앱을 설치하고 실행하여 앱을 다운로드하고 장치를 관리할 수 있습니다. 사용자는 장치를 받은 후 설정 도우미를 실행하고 회사 포털 앱을 설치해야 합니다.
