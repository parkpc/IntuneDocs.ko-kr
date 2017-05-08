---
title: "iOS 장치용 Apple DEP 관리 | Microsoft 문서"
description: "“무선으로” iOS DEP(장비 등록 프로그램)를 통해 구매한 iOS 장치를 등록하는 등록 프로필을 배포하여 Apple 장치를 관리할 수 있습니다."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8ff9d9e7-eed8-416c-8508-efc20fca8578
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: c8715f96f532ee6bacda231e1147d03226ecbb48
ms.openlocfilehash: 81f5b33bc344cd6ed305d72178c7eb4cac315a13
ms.contentlocale: ko-kr
ms.lasthandoff: 04/26/2017


---

# <a name="enroll-corporate-owned-device-enrollment-program-ios-devices"></a>회사 소유 장치 등록 프로그램 iOS 장치 등록

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune은 “무선으로” DEP(장치 등록 프로그램)를 통해 구매한 iOS 장치를 등록하는 등록 프로필을 배포할 수 있습니다. 등록 패키지는 장치에 대한 설정 도우미 옵션을 포함할 수 있습니다.

>[!NOTE]
>DEP 등록은 [장치 등록 관리자](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md) 방법과 함께 사용할 수 없습니다.
>또한 사용자가 iOS 장치를 등록(즉, 회사 포털 앱을 사용하여)한 후 해당 장치의 일련 번호를 가져오고 DEP 프로필을 할당한 경우 장치가 Intune에서 등록 취소됩니다.

## <a name="prerequisites-for-enrolling-ios-devices-by-using-apple-dep-management"></a>Apple DEP 관리를 사용하여 iOS 장치를 등록하기 위한 필수 조건

- [APNs 인증서 설치](set-up-ios-and-mac-management-with-microsoft-intune.md)

- 조직에서 Apple DEP에 가입하고 그 프로그램을 통해 장치를 가져와야 합니다. 해당 프로세스의 세부 정보는  [https://deploy으로 관리할 수 있습니다.apple으로 관리할 수 있습니다.com](https://deploy.apple.com)으로 관리할 수 있습니다. 이 프로그램의 이점 중 하나는 USB 케이블을 사용해서 각 장치를 컴퓨터에 연결하지 않고도 장치를 자동 설치할 수 있다는 것입니다.

- 회사 소유의 iOS 장치를 DEP에 등록하려면 Apple의 DEP 토큰이 필요합니다. Intune에서는 이 토큰을 통해 회사에서 소유한 DEP 참가 장치에 대한 정보를 동기화할 수 있습니다. 또한 Apple에 등록 프로필을 업로드하고 이러한 프로필에 장치를 할당할 수 있습니다.

## <a name="steps-to-enroll-ios-devices-by-using-apple-dep-management"></a>Apple DEP 관리를 사용하여 iOS 장치를 등록 하는 단계

다음 단계에서는 Apple DEP 관리를 사용하여 "0일"에 iOS 장치를 등록하는 방법을 설명합니다. 조직에서 장치를 추가 및 제거하는 동안, 아래에 설명된 대로 일련 번호 추가 또는 제거와 같은 일부 단계를 반복할 가능성이 큽니다.

### <a name="get-an-encryption-key"></a>암호화 키 가져오기

1. 관리 사용자는 [Microsoft Intune 관리 콘솔](https://manage.microsoft.com)을 열고 **관리** &gt; **모바일 장치 관리** &gt; **iOS** &gt; **장치 등록 프로그램**으로 이동한 후 **암호화 키 다운로드**를 선택합니다.

2. 암호화 키(.pem) 파일을 로컬로 저장합니다. .pem 파일은 Apple 장치 등록 프로그램 포털에서 트러스트 관계 인증서를 요청하는 데 사용됩니다.

![장치 등록 프로그램 토큰 업데이트](../media/dev-sa-ios-dep.png)

### <a name="get-a-device-enrollment-program-token"></a>장치 등록 프로그램 토큰 가져오기

1. [장치 등록 프로그램 포털](https://deploy.apple.com) (https://deploy.apple.com) 로 이동한 다음 회사 Apple ID로 로그인합니다. 나중에 DEP 토큰을 갱신하려면 이 Apple ID를 사용해야 합니다.

2.  장치 등록 프로그램 포털에서 **장치 등록 프로그램** &gt; **서버 관리**로 이동한 후 **MDM 서버 추가**를 선택합니다.

3.  **MDM 서버 이름**을 입력하고 **다음**을 선택합니다. 서버 이름은 참조용으로 MDM(모바일 장치 관리) 서버를 식별하기 위한 것으로, Microsoft Intune 서버의 이름 또는 URL이 아닙니다.

4.  **&lt;ServerName&gt; 추가** 대화 상자가 열립니다. **파일 선택...**을 선택하여 .pem 파일을 업로드하고 **다음**을 선택합니다.

5.  **&lt;ServerName&gt; 추가** 대화 상자에 **내 서버 토큰** 링크가 표시됩니다. 컴퓨터에 서버 토큰(.p7m) 파일을 다운로드한 다음 **완료**를 선택합니다.

   이 인증서(.p7m) 파일은 Intune과 Apple 장치 등록 프로그램 서버 간에 트러스트 관계를 설정하는 데 사용됩니다.

### <a name="add-the-dep-token-to-intune"></a>Intune에 DEP 토큰 추가

1. [Microsoft Intune 관리 콘솔](https://manage.microsoft.com)에서 **관리** &gt; **모바일 장치 관리** &gt; **iOS** &gt; **장치 등록 프로그램**으로 이동합니다.

2. **DEP 토큰 업로드**를 선택합니다. 인증서(.p7m) 파일을**찾아** **Apple ID**를 입력한 다음 **업로드**를 선택합니다.

### <a name="add-the-corporate-device-enrollment-policy"></a>회사 장치 등록 정책 추가

1. [Microsoft Intune](https://manage.microsoft.com) 관리 콘솔에서 **정책** &gt; **회사 장치 등록**으로 이동한 후 **추가**를 선택합니다.

2. **이름** 및 **설명**을 포함한 **일반** 세부 정보를 제공하고, 프로필에 할당된 장치에 사용자 선호도가 있는지 또는 장치가 그룹에 속해 있는지를 지정합니다.

   - **사용자 선호도 확인**: 초기 설치 작업을 진행할 때 먼저 장치에 사용자 정보를 등록해야만 해당 사용자로 회사 데이터와 메일에 액세스하도록 허용할 수 있습니다. 사용자에게 속해 있으며 회사 포털을 사용해야 하는(즉, 앱을 설치해야 하는) DEP 관리 장치에 대한 **사용자 선호도**를 설정해야 합니다. MFA(다단계 인증)는 사용자 선호도가 있는 DEP 장치에 등록하는 동안 작동하지 않습니다. 등록 후 MFA는 이러한 장치에서 예상대로 작동합니다. DEP 장치에서는 처음 로그인할 때 자신의 암호를 변경해야 하는 새 사용자에게 등록 중에 메시지를 표시할 수 없습니다. 또한 암호가 만료된 사용자는 DEP 등록 중에 암호를 다시 설정하라는 메시지가 표시되지 않으며, 다른 장치에서 암호를 다시 설정해야 합니다.

   > [!NOTE]
   > 사용자 선호도가 있는 DEP에서는 사용자 토큰을 요청하기 위해 WS-Trust 1.3 사용자 이름/혼합 끝점이 사용 가능하게 설정되어야 합니다.

   - **사용자 선호도 없음**: 장치에 사용자 정보를 등록하지 않습니다. 로컬 사용자 데이터에 액세스하지 않고도 작업을 수행하는 장치에 대해 이 정보를 사용합니다. 기간 업무 앱을 설치하는 데 사용하는 회사 포털 앱 등 사용자 선호도가 필요한 앱은 작동하지 않습니다.

   **다음 그룹에 장치를 할당**할 수도 있습니다. **선택...**을 선택하여 그룹을 선택합니다.

   > [!Important]
   > 그룹 할당이 Intune에서 Azure Active Directory로 이동됩니다. Intune 계정에서 해당 업데이트를 받고 나면 **다음 그룹에 장치 할당** 옵션이 표시되지 않습니다. [자세히 알아봅니다](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune#changes-to-intune-group-assignments).

3. **이 정책에 대한 장치 등록 프로그램 설정을 구성합니다.**를 사용하도록 설정하여 DEP를 지원합니다.

      ![설정 도우미 창](../media/pol-sa-corp-enroll.png)

   DEP 관리 장치에서는 다음 설정을 지정할 수 있습니다.

   - **부서** - 정품 인증을 하는 동안 사용자가 **구성 정보**를 탭하면 나타남
   - **지원 전화 번호** - 정품 인증을 하는 동안 사용자가 **도움 필요** 단추를 클릭하면 표시됨
   - **준비 모드** - 정품 인증을 하는 동안 설정되고 장치를 초기화해야 변경할 수 있음
       - **감독되지 않음** - 제한된 관리 기능
       - **감독됨** - 더 많은 관리 옵션을 사용할 수 있고 기본적으로 활성화 잠금을 비활성화합니다.
   - **장치에 등록 프로필 잠금** - 정품 인증을 하는 동안 설정되고 장치를 초기화해야 변경할 수 있음
       - **사용 안 함** - 관리 프로필을 **설정** 메뉴에서 제거할 수 있습니다.
       - **사용** - (**준비 모드** = **감독됨**이어야 함) 관리 프로필을 제거하는 iOS 설정 메뉴를 비활성화합니다.
   - **설치 도우미 옵션** - 이러한 선택적 설정은 나중에 iOS **설정** 메뉴에서 지정할 수 있습니다.
        - **암호** - 정품 인증을 하는 동안 암호를 묻는 메시지가 표시됩니다. 장치가 보안된 상태가 아니거나 다른 방식으로 액세스가 제어된 상태(즉, 하나의 앱만 사용할 수 있도록 장치를 제한하는 키오스크 모드)가 아니면 항상 암호를 요구합니다.
       - **위치 서비스** - 이를 설정하면 정품 인증을 하는 동안 설치 도우미에서 서비스를 사용할지 묻는 메시지를 표시합니다.
       - **복원** - 이를 설정하면 정품 인증을 하는 동안 설치 도우미에서 iCloud 백업을 사용할지 묻는 메시지를 표시합니다.
       - **Apple ID** - 이 설정을 지정하면 Intune에서 ID 없이 앱을 설치하려고 할 때 iOS가 사용자에게 Apple ID를 묻습니다. Intune을 통해 설치한 앱을 비롯하여 iOS App Store 앱을 다운로드하려면 Apple ID가 필요합니다.
       - **사용 약관** - 이를 설정하면 정품 인증을 하는 동안 설치 도우미가 Apple의 약관에 동의하라는 메시지를 표시합니다.
       - **터치 ID** - 이 옵션을 사용하도록 설정하면 활성화하는 동안 설정 도우미에서 이 서비스를 확인하는 메시지가 표시됩니다.
       - **Apple Pay** - 이 옵션을 사용하도록 설정하면 활성화하는 동안 설정 도우미에서 이 서비스를 확인하는 메시지가 표시됩니다.
       - **확대/축소** - 이 옵션을 사용하도록 설정하면 활성화하는 동안 설정 도우미에서 이 서비스를 확인하는 메시지가 표시됩니다.
       - **Siri** - 이 옵션을 사용하도록 설정하면 활성화하는 동안 설정 도우미에서 이 서비스를 확인하는 메시지가 표시됩니다.
       - **Apple에 진단 데이터 보내기** - 이를 설정하면 정품 인증을 하는 동안 설치 도우미가 이 서비스를 사용할지 묻는 메시지를 표시합니다.
   -  **추가 Apple Configurator 관리를 사용하도록 설정** - 파일을 iTunes와 동기화하지 않도록 하거나 Apple Configurator를 통해 관리 작업을 하지 못하게 하려면 **허용 안 함**으로 설정합니다. 이 설정을 사용하여 인증서 유무와 관계없이 수동 배포를 허용하는 것보다, **허용 안 함**으로 설정하고 Apple Configurator에서 모든 추가 구성을 내보낸 다음, Intune을 통해 사용자 지정 iOS 구성 프로필 형태로 배포하는 것이 좋습니다.
       - **허용 안 함** - USB를 통해 장치가 통신할 수 없음(연결을 비활성화함)
       - **허용** - 모든 PC 또는 Mac을 대상으로 장치가 USB 연결을 통해 통신할 수 있음
       - **인증서 필요** - 등록 프로필에 가져온 인증서를 사용하여 Mac과 연결할 수 있음

### <a name="assign-the-profile-to-devices"></a>장치에 프로필 할당

1. [Microsoft Intune 관리 콘솔](https://manage.microsoft.com)에서 **정책** &gt; **회사 장치 등록**으로 이동한 후 **할당**을 선택합니다.

2. 만든 프로필을 할당할 장치를 선택합니다. **모든 장치** 또는 특정 장치를 선택한 다음 **추가**를 선택할 수 있습니다.

> [!Important]
> 현재 Intune에서는 "기본" 장치 등록 프로필을 지정할 수 있으며, 이 경우 새 일련 번호를 Apple DEP 서비스로 동기화할 때 해당 기본 프로필에 새 일련 번호가 자동으로 할당됩니다. 곧 테넌트가 새 Azure 포털로 마이그레이션되면 더 이상 기본 프로필을 지정하고 그 프로필에 일련 번호를 자동으로 할당할 수 없습니다. 대신 특정 프로필에 일련 번호를 할당해야 합니다. [자세한 정보](https://docs.microsoft.com/intune-azure/enroll-devices/enroll-ios-devices-using-device-enrollment-program)

### <a name="assign-dep-devices-for-management"></a>관리를 위해 DEP 장치 할당

1. [장치 등록 프로그램 포털](https://deploy.apple.com) (https://deploy.apple.com) 로 이동한 다음 회사 Apple ID로 로그인합니다.

2. **배포 프로그램** &gt; **장치 등록 프로그램** &gt; **장치 관리**로 이동합니다.

3. **장치 선택**방법을 지정하고, 장치 정보를 제공한 다음 장치 **일련번호**, **주문 번호**또는 **CSV 파일 업로드**에 따라 세부 정보를 지정합니다.

4. **서버에 할당**을 선택하고 Microsoft Intune에 대해 지정된 &lt;ServerName&gt;을 선택한 다음 **확인**을 선택합니다.

### <a name="synchronize-dep-managed-devices"></a>DEP 관리 장치 동기화

이 단계에서는 장치를 Apple DEP 서비스와 동기화하고 장치를 Intune 콘솔에 표시합니다.

1. 관리자 권한으로 [Microsoft Intune 관리 콘솔](https://manage.microsoft.com)을 열고 **관리** &gt; **모바일 장치 관리** &gt; **iOS** &gt; **장치 등록 프로그램**으로 이동한 후 **지금 동기화**를 선택합니다. 동기화 요청이 Apple에 전송됩니다.

2. 동기화 후에 DEP 관리 장치를 보려면 [Microsoft Intune 관리 콘솔](https://manage.microsoft.com)에서 **그룹** &gt; **모든 장치** &gt; **회사에서 사전 등록한 장치** &gt; **iOS 일련 번호 기준**으로 이동합니다. **iOS 일련 번호 기준** 작업 영역에서는 장치를 켜고 설치 도우미를 실행하여 장치를 등록할 때까지 관리되는 장치 **상태**가 "연결되지 않음"으로 표시됩니다.

   허용 가능한 DEP 트래픽에 대한 Apple의 약관을 준수하려면 Intune에서는 다음과 같은 제한 사항을 적용합니다.

   - 전체 DEP 동기화는 7일마다 한 번 이상 실행할 수 없습니다. 전체 동기화 중 Intune은 Apple에서 일련 번호가 이전에 동기화되었는지 여부를 Intune에 할당한 모든 일련 번호를 새로 고칩니다. 전체 동기화를 이전 전체 동기화의 7일 이내에 시도하는 경우 Intune은 Intune에 나열되지 않은 일련 번호만 새로 고칩니다.

   - 모든 동기화 요청은 완료하는 데 10분이 주어집니다. 이 시간 동안 또는 요청이 성공될 때까지 **동기화** 단추는 비활성화됩니다.

### <a name="distribute-devices-to-users"></a>사용자에게 장치 배포

이제 회사 소유 장치를 사용자에게 배포할 수 있습니다. IOS 장치를 설정하는 경우에 Intune에 관리용으로 등록됩니다. 사용자 장치 제한은 DEP 관리 장치에 적용됩니다.

>[!NOTE]
>사용자가 DEP 장치를 등록하려고 하지만, 장치 제한을 초과한 경우 사용자에게 경고 없이 등록이 자동으로 실패합니다.

## <a name="changes-to-intune-group-assignments"></a>Intune 그룹 할당 변경

2017년 4월부터 장치 그룹 관리가 Azure Active Directory로 이동됩니다. Azure Active Directory 그룹으로 전환된 후에는 그룹 할당이 회사 등록 프로필 옵션에 나타나지 않습니다. 이 변경은 몇 달에 걸쳐 진행될 예정이므로 당장 변경 내용이 확인되지 않을 수 있습니다. 새 포털로 이동하고 나면 회사 등록 프로필 이름에 따라 동적 장치 그룹 할당을 정의할 수 있습니다.

마이그레이션할 때 회사 장치 등록 프로필에서 미리 할당된 모든 Intune 장치 그룹마다 회사 장치 등록 프로필 이름을 기반으로 Azure AD에 해당 동적 장치 그룹이 생성됩니다. 새 프로필 이름은 *EnrollmentProfile:&lt;연결된 프로필의 이름&gt;* 형식입니다. 새 동적 장치 그룹 할당을 정의하면 장치 그룹에 미리 할당된 장치가 정책과 앱이 배포된 상태에서 그룹에 자동으로 등록됩니다.

이 자동 그룹 만들기는 그룹 마이그레이션 중에 한 번만 발생합니다. 마이그레이션 후 Intune 관리자는 Azure Portal을 사용하여 그룹을 만들어야 합니다. 회사 소유의 iOS 장치 등록에 미치는 영향에 대한 자세한 내용은 [회사 사전 등록 iOS 장치에 대한 자동 그룹화에 대한 변경 내용](https://blogs.technet.microsoft.com/intunesupport/2017/04/19/changes-to-automatic-grouping-for-corporate-pre-enrolled-ios-devices/)을 참조하세요.

[Azure Active Directory 그룹에 대한 자세한 정보](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-manage-groups/)도 참조할 수 있습니다.

### <a name="see-also"></a>참고 항목
[장치 등록을 위한 필수 구성 요소](prerequisites-for-enrollment.md)

