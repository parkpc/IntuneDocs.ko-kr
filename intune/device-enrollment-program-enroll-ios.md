---
title: "iOS 장치 등록 - 장비 등록 프로그램"
titlesuffix: Azure portal
description: "장비 등록 프로그램을 사용하여 회사 소유 iOS 장치를 등록하는 방법을 알아봅니다.\""
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/08/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b56907217b45ddb2bfe869f23abc34c0508bdbd7
ms.sourcegitcommit: 9bd6278d129fa29f184b2d850138f8f65f3674ea
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2018
---
# <a name="automatically-enroll-ios-devices-with-apples-device-enrollment-program"></a>Apple 장치 등록 프로그램을 통해 iOS 장치를 자동으로 등록

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

> [!NOTE]
> ### <a name="temporary-user-interface-differences"></a>임시 사용자 인터페이스 차이점
>
>이 페이지에 설명된 기능의 사용자 인터페이스는 업데이트 중입니다. 이러한 업데이트는 4월 말까지 모든 사용자 계정에 배포됩니다.
>
>**장치 등록** 페이지가 아래 이미지와 같은 경우 계정이 아직 새 사용자 인터페이스로 업데이트되지 않은 것이며, 이 도움말 페이지를 사용할 수 있습니다.
>
>![이전 사용자 인터페이스](./media/appleenroll-oldui.png)
>
>**장치 등록** 페이지가 아래 이미지와 같은 경우 업데이트된 사용자 인터페이스가 있는 것입니다.  [이 도움말 페이지](device-enrollment-program-enroll-ios-newui.md)로 이동하세요.
>
>![새 사용자 인터페이스](./media/appleenroll-newui.png)

이 항목의 정보를 참조하여 Apple의 [DEP(장비 등록 프로그램)](https://deploy.apple.com)를 통해 구매한 장치에 대해 iOS 장치 등록을 사용할 수 있습니다. 장치를 건드리지 않고 다수의 장치에 대한 DEP 등록을 사용할 수 있습니다. iPhones 및 iPads와 같은 장치를 직접 사용자에게 제공할 수 있습니다. 사용자가 장치를 켜면 설정 도우미가 미리 구성된 설정을 사용하여 실행되고 장치가 관리용으로 등록됩니다.

DEP 등록을 사용하도록 설정하려면 Intune과 Apple DEP 포털을 둘 다 사용합니다. 관리용으로 Intune에 장치를 할당할 수 있으려면 일련 번호 또는 구매 주문 번호 목록이 필요합니다. 등록 중에 장치에 적용된 설정을 포함하는 DEP 등록 프로필을 만듭니다.

그러나 DEP 등록은 [장치 등록 관리자](device-enrollment-manager-enroll.md)에서 작동할 수 없습니다.

## <a name="what-is-supervised-mode"></a>감독됨 모드란?
Apple은 iOS 5에서 감독됨 모드를 도입했습니다. 감독됨 모드에서 iOS 장치를 더 세밀하게 관리할 수 있습니다. 이와 같이 회사 소유 장치에 특히 유용합니다. Intune은 Apple DEP(장치 등록 프로그램)의 일부로 감독됨 모드의 장치를 구성하도록 지원합니다. 

<!--
**Steps to enable enrollment programs from Apple**
1. [Get an Apple DEP token and assign devices](#get-the-apple-dep-token)
2. [Create an enrollment profile](#create-an-apple-enrollment-profile)
3. [Synchronize DEP-managed devices](#sync-managed-device)
4. [Assign DEP profile to devices](#assign-an-enrollment-profile-to-devices)
5. [Distribute devices to users](#end-user-experience-with-managed-devices)
-->
## <a name="prerequisites"></a>전제 조건
- [Apple의 장치 등록 프로그램](http://deploy.apple.com)에서 구매한 장치
- [MDM 기관](mdm-authority-set.md)
- [Apple MDM Push certificate](apple-mdm-push-certificate-get.md)

> [!NOTE]
> MFA(다단계 인증)는 사용자 선호도를 위한 DEP 등록 설정 중에는 동안 작동하지 않습니다. 등록 후 MFA는 장치에서 예상대로 작동합니다. 처음 로그인할 때 암호를 변경해야 하는 사용자에게 장치가 메시지를 표시할 수 없습니다. 또한 암호가 만료된 사용자는 등록 중에 암호를 재설정하라는 메시지가 표시되지 않습니다. 사용자가 다른 장치를 사용하여 암호를 재설정해야 합니다.

## <a name="get-the-apple-dep-token"></a>Apple DEP 토큰 가져오기

iOS 장치를 DEP에 등록하려면 Apple의 DEP 토큰(.p7m) 파일이 필요합니다. Intune에서는 이 토큰을 통해 회사에서 소유한 DEP 장치에 대한 정보를 동기화할 수 있습니다. 또한 Apple에 등록 프로필을 업로드하고 이러한 프로필에 장치를 할당할 수 있습니다.

Apple DEP 포털을 사용하여 DEP 토큰을 만듭니다. 관리용으로 Intune에 장치를 할당하는 데도 DEP 포털을 사용할 수 있습니다.

> [!NOTE]
> Azure로 마이그레이션하기 전에 Intune 클래식 포털에서 토큰을 삭제하면 Intune이 삭제된 Apple DEP 토큰을 복원할 수 있습니다. Azure Portal에서 DEP 토큰을 다시 삭제할 수 있습니다. Azure Portal에서 DEP 토큰을 다시 삭제할 수 있습니다.

**1단계. Apple DEP 토큰을 만드는 데 필요한 Intune 공개 키 인증서를 다운로드합니다.**<br>

1. Azure 포털의 Intune에서 **장치 등록** > **Apple 등록** > **등록 프로그램 토큰**을 선택합니다.

  ![Apple 인증서 작업 영역의 등록 프로그램 토큰 창 스크린샷](./media/enrollment-program-token-add.png)

2. **공개 키 다운로드**를 선택하여 암호화 키(.pem) 파일을 다운로드하고 로컬로 저장합니다. .pem 파일은 Apple 장비 등록 프로그램 포털에서 트러스트 관계 인증서를 요청하는 데 사용됩니다.

  ![공개 키를 다운로드하기 위한 Apple 인증서 작업 영역의 등록 프로그램 토큰 창 스크린샷](./media/enrollment-program-token-download.png)

**2단계. Apple DEP 토큰을 만들고 다운로드합니다.**<br>
1. **Apple 장비 등록 프로그램을 통해 토큰 만들기**를 선택하여 Apple 배포 프로그램 포털을 열고 회사 Apple ID로 로그인합니다. 이 Apple ID를 사용하여 DEP 토큰을 갱신할 수 있습니다.
2.  Apple [배포 프로그램 포털](https://deploy.apple.com)에서 **장비 등록 프로그램**에 대해 **시작**을 선택합니다.

3. **서버 관리** 페이지에서 **MDM 서버 추가**를 선택합니다.
4. **MDM 서버 이름**을 입력하고 **다음**을 선택합니다. 서버 이름은 참조용으로 MDM(모바일 장치 관리) 서버를 식별하기 위한 것으로, Microsoft Intune 서버의 이름 또는 URL이 아닙니다.

   ![DEP에 대해 MDM 서버 이름을 추가하고 다음을 클릭하는 스크린샷](./media/enrollment-program-token-add-server.png)

5. **&lt;ServerName&gt; 추가** 대화 상자가 열리고 **공개 키 업로드**가 표시됩니다. **파일 선택...**을 선택하여 .pem 파일을 업로드하고 **다음**을 선택합니다.  
<<<<<<< HEAD

=======
>>>>>>> e19b417f8bc134dc5a5a9f60354f017ccc42fd88

7. **배포 프로그램** &gt; **장비 등록 프로그램** &gt; **장치 관리**로 이동합니다.
8. **장치 선택 기준**에서 장치를 식별하는 방법을 지정합니다.
    - **일련 번호**
    - **주문 번호**
    - **CSV 파일 업로드**

   ![일련 번호로 장치 선택을 지정하고 작업 선택을 서버에 할당으로 설정한 다음 서버 이름을 선택하는 스크린샷](./media/enrollment-program-token-specify-serial.png)

9. **작업 선택**에서 **서버에 할당**, Microsoft Intune에 지정된 &lt;ServerName&gt; 및 **확인**을 순서대로 선택합니다. Apple Portal에서 관리를 위해 지정된 장치를 Intune 서버에 할당한 다음 **할당 완료**를 표시합니다.

   Apple Portal에서 **배포 프로그램** &gt; **장비 등록 프로그램** &gt; **할당 기록 보기**로 이동하여 장치 목록 및 해당 MDM 서버 할당을 확인합니다.

**3단계. 등록 프로그램 토큰을 만드는 데 사용되는 Apple ID를 입력합니다.**<br>Azure 포털의 Intune에서 나중에 참조할 수 있도록 Apple ID를 제공합니다.

![등록 프로그램 토큰을 만드는 데 사용되는 Apple ID를 지정하고 등록 프로그램 토큰을 찾는 스크린샷](./media/enrollment-program-token-apple-id.png)

**4단계. 업로드할 등록 프로그램 토큰을 찾습니다.**<br>
인증서(.pem) 파일로 이동한 후 **열기**를 선택하고 **업로드**를 선택합니다. Push Certificate가 있으면 Intune에서 등록된 모바일 장치에 정책을 푸시하여 iOS 장치를 등록하고 관리할 수 있습니다. Intune이 Apple과 자동으로 동기화되어 등록 프로그램 계정을 확인합니다.

## <a name="create-an-apple-enrollment-profile"></a>Apple 등록 프로필 만들기

이제 토큰을 설치했으므로 DEP 장치의 등록 프로필을 만들 수 있습니다. 장치 등록 프로필은 등록 중에 장치 그룹에 적용되는 설정을 정의합니다.

1. Azure 포털의 Intune에서 **장치 등록** > **Apple 등록**을 선택합니다.
2. **Apple의 등록 프로그램**에서 **등록 프로그램 프로필** > **만들기**를 선택합니다.
3. **등록 프로필 만들기**에서 관리 목적으로 프로필에 대한 **이름** 및 **설명**을 입력합니다. 사용자는 이러한 세부 정보를 볼 수 없습니다. 이 **이름** 필드를 사용하여 Azure Active Directory에 동적 그룹을 만들 수 있습니다. 이 등록 프로필로 장치를 할당하기 위해 프로필 이름을 사용하여 enrollmentProfileName 매개 변수를 정의합니다. [Azure Active Directory 동적 그룹](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal#using-attributes-to-create-rules-for-device-objects)에 대해 자세히 알아보세요.

  **사용자 선호도**에서 이 프로필이 있는 장치가 할당된 사용자를 사용하여 등록되는지 사용하지 않고 등록되는지 선택합니다.

 - **사용자 선호도를 사용하여 등록** - 사용자에게 속하고 앱 설치 같은 서비스에 회사 포털을 사용해야 하는 장치에 대한 사용자 선호도를 선택합니다. 사용자 선호도에는 [WS-Trust 1.3 사용자 이름/혼합 끝점](https://technet.microsoft.com/library/adfs2-help-endpoints)이 필요합니다. [자세히 알아봅니다](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

 - **사용자 선호도를 사용하지 않고 등록** - 단일 사용자로 등록되지 않은 장치를 선택합니다. 로컬 사용자 데이터에 액세스하지 않고도 작업을 수행하는 장치에 사용합니다. 회사 포털 앱과 같은 앱이 작동하지 않습니다.

4. **장치 관리 설정**을 선택하여 다음 프로필 설정을 구성합니다.

  ![관리 모드 선택 스크린샷 장치는 감독됨, 등록 잠김, 연결 허용과 같은 설정을 모두 거부로 설정했습니다. Apple Configurator 인증서는 새 등록 프로그램 프로필에 대해 회색으로 표시됩니다.](./media/enrollment-program-profile-mode.png)
  - **감독됨** - 더 많은 관리 옵션을 사용할 수 있으며 기본적으로 활성화 잠금이 해제된 관리 모드입니다. 이 확인란을 비워 두면 관리 기능이 제한됩니다. 특히 많은 수의 iOS 장치를 배포하는 조직의 경우 감독됨 모드를 사용하기 위한 메커니즘으로 DEP를 사용하는 것이 좋습니다.

 > [!NOTE]
 > 장치를 등록한 후에 Intune을 사용하여 감독됨 모드에서 장치를 구성할 수 없습니다. 등록 후에 감독됨 모드를 사용하도록 설정하는 유일한 방법은 USB 케이블을 사용하여 Mac에 iOS 장치를 연결하고 Apple Configurator를 사용하는 것입니다. 그러면 이 장치를 다시 설정하고 감독됨 모드에서 구성합니다. 이에 대해 [Apple Configurator 문서](http://help.apple.com/configurator/mac/2.3)에서 자세히 알아보세요. 감독됨 장치는 "이 iPhone은 Contoso에서 관리됩니다."라는 메시지를 잠금 화면에서 표시하고 "이 iPhone은 감독됩니다. Contoso는 사용자의 인터넷 트래픽을 모니터링하고 이 장치를 찾습니다."라는 메시지를 **설정** > **일반** > **정보**에서 표시합니다.

  - **등록 잠김** - (관리 모드 = 감독됨이어야 함) 관리 프로필 제거를 허용하는 iOS 설정이 해제됩니다. 이 확인란을 비워 두면 설정 메뉴에서 관리 프로필을 제거할 수 있습니다. 장치 등록 후 장치를 초기화하지 않고는 이 설정을 변경할 수 없습니다.

  - **공유된 iPad 사용** - Apple의 장비 등록 프로그램은 공유된 iPad를 지원하지 않습니다.

  - **연결 허용** - iOS 장치를 컴퓨터와 동기화할 수 있는지 여부를 지정합니다. **인증서로 Apple Configurator 허용**을 선택한 경우 **Apple Configurator 인증서** 아래에서 인증서를 선택해야 합니다.

  - **Apple Configurator 인증서** - **연결 허용** 아래에서 **인증서로 Apple Configurator 허용**을 선택한 경우 가져올 Apple Configurator 인증서를 선택합니다.

  **저장**을 선택합니다.

5. **설정 도우미 설정**을 선택하여 다음 프로필 설정을 구성합니다.

  ![새 등록 프로그램 프로필에 대한 사용 가능한 설정이 포함된 설정 구성을 선택하는 스크린샷](./media/enrollment-program-profile-settings.png)
  - **부서 이름** - 정품 인증을 하는 동안 사용자가 **구성 정보**를 탭하면 표시됩니다.

  - **부서 전화** - 정품 인증을 하는 동안 사용자가 **도움이 필요하세요?** 단추를 클릭하면 표시됩니다.
    - **설치 도우미 옵션** - 이러한 선택적 설정은 나중에 iOS **설정** 메뉴에서 지정할 수 있습니다.
        - **암호**
        - **위치 서비스**
        - **복원**
        - **Apple ID**
        - **계약조건**
        - **터치 ID**
        - **Apple Pay**
        - **확대/축소**
        - **Siri**
        - **진단 데이터**

    **저장**을 선택합니다.

9. 프로필 설정을 저장하려면 **등록 프로필 만들기** 블레이드에서 **만들기**를 선택합니다. 등록 프로필이 Apple 등록 프로그램 등록 프로필 목록에 나타납니다.

## <a name="sync-managed-devices"></a>관리되는 장치 동기화
이제 Intune에 장치 관리 권한이 있으므로 Intune을 Apple과 동기화하여 Azure 포털의 Intune에서 관리되는 장치를 확인할 수 있습니다.

1. Azure Portal의 Intune에서 **장치 등록** > **Apple 등록** > **등록 프로그램 장치** > **동기화**를 선택합니다. 진행률 표시줄에 동기화를 다시 요청하기 전에 대기해야 하는 시간이 표시됩니다.

  ![등록 프로그램 장치 노드가 선택되고 동기화 링크를 선택하는 스크린샷](./media/enrollment-program-device-sync.png)
  
2. **동기화** 블레이드에서 **동기화 요청**을 선택합니다. 진행률 표시줄에 동기화를 다시 요청하기 전에 대기해야 하는 시간이 표시됩니다.

   ![동기화 요청 링크를 선택하는 동기화 블레이드 스크린샷](./media/enrollment-program-device-request-sync.png)

   허용되는 등록 프로그램 트래픽에 대한 Apple 약관을 준수하기 위해 Intune에서는 다음과 같은 제한 사항을 적용합니다.
     -  전체 동기화는 7일마다 한 번씩만 실행할 수 있습니다. 전체 동기화 동안 Intune은 Intune에 할당된 모든 Apple 일련 번호를 새로 고칩니다. 전체 동기화를 이전 전체 동기화의 7일 이내에 시도하는 경우 Intune은 Intune에 나열되지 않은 일련 번호만 새로 고칩니다.
     -  모든 동기화 요청은 완료하는 데 15분이 주어집니다. 이 시간 동안 또는 요청이 성공될 때까지 **동기화** 단추는 비활성화됩니다.
     - Intune은 24시간마다 새 장치 및 제거된 장치를 Apple과 동기화합니다.

3. 등록 프로그램 장치 작업 영역에서 **새로 고침**을 선택하여 장치를 확인합니다.

## <a name="assign-an-enrollment-profile-to-devices"></a>장치에 등록 프로필 할당
먼저 등록 프로그램 프로필을 장치에 할당해야 장치를 등록할 수 있습니다.

>[!NOTE]
>**Apple 일련 번호** 블레이드에서 프로필에 일련 번호를 할당할 수도 있습니다.

1. Azure 포털의 Intune에서 **장치 등록** > **Apple 등록**을 선택한 다음 **등록 프로그램 프로필**을 선택합니다.
2. **등록 프로그램 프로필** 목록에서 장치에 할당할 프로필을 선택한 다음 **장치 할당**을 선택합니다.

 ![할당을 선택 중인 장치 할당 스크린샷.](./media/enrollment-program-device-assign.png)

3. **할당**을 선택한 다음 이 프로필을 할당할 장치를 선택합니다. 다음 기준을 사용하여 필터링하면 사용 가능한 장치를 확인할 수 있습니다.
  - **할당되지 않음**
  - **임의**
  - **&lt;프로필 이름&gt;**
4. 프로필을 할당할 장치를 선택합니다. 열 위쪽에 있는 확인란을 선택하면 나열된 장치를 1,000개까지 선택할 수 있습니다. 장치를 선택한 후에 **할당**을 클릭합니다. 1,000개보다 많은 장치를 등록하려면 모든 장치에 등록 프로필이 할당될 때까지 할당 단계를 반복합니다.

  ![Intune에서 등록 프로그램 프로필을 할당하는 데 사용되는 할당 단추의 스크린샷](media/dep-profile-assignment.png)

## <a name="distribute-devices"></a>장치 배포
Apple과 Intune 간의 동기화 및 관리를 사용하도록 설정했으며 DEP 장치를 등록할 수 있는 프로필을 할당했습니다. 이제 사용자에게 장치를 배포할 수 있습니다. 사용자 선호도가 있는 장치의 경우 각 사용자에게 Intune 라이선스를 할당해야 합니다. 사용자 선호도를 사용하지 않는 장치에는 장치 라이선스가 필요합니다. 활성화된 장치는 초기화될 때까지 등록 프로필을 적용할 수 없습니다.

[장비 등록 프로그램을 통해 Intune에서 iOS 장치 등록](/intune-user-help/enroll-your-device-dep-ios)을 참조하세요. 


