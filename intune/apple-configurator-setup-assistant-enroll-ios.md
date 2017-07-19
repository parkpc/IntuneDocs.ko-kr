---
title: "iOS 장치 등록 - Apple Configurator 설정 도우미"
titleSuffix: Intune on Azure
description: "Apple Configurator를 사용하여 설정 도우미를 통해 회사 소유 iOS 장치를 등록하는 방법을 알아봅니다.\""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6d384cd0-b662-41e7-94f5-0c96790ab20a
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1d74fbcebfe89bbafc545d11dd6316cb602db8ee
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2017
---
# <a name="enroll-ios-devices-with-apple-configurator"></a>Apple Configurator를 사용한 iOS 장치 등록

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune은 Mac 컴퓨터에서 실행되는 [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)를 사용하여 회사 소유의 iOS 장치를 등록하도록 지원합니다. Apple Configurator를 사용하여 장치를 등록하려면 각 iOS 장치를 USB로 Mac 컴퓨터에 연결하여 회사 등록을 설정해야 합니다. 다음 두 가지 방법으로 Apple Configurator를 사용하여 Intune에 장치를 등록할 수 있습니다.
- **설정 도우미 등록** - 장치를 초기화하고 설정 도우미를 실행할 수 있도록 준비하여 장치의 새 사용자용으로 회사 정책을 설치합니다. 대부분의 시나리오는 Intune 회사 포털 앱을 활성화하기 위해 iOS 장치에 적용되는 정책에 사용자 선호도를 포함해야 합니다.
- **직접 등록** - 장치를 초기화하지 않고 미리 정의된 정책을 사용하여 장치를 등록합니다. 이 방법은 **사용자 선호도가 없는** 장치용입니다.

>[!NOTE]
>이 등록 방법을 [장치 등록 관리자](device-enrollment-manager-enroll.md) 방법과 함께 사용할 수 없습니다.

iOS 장치를 등록하는 다른 방법은 [Intune에서 iOS 장치를 등록하는 방법 선택](enrollment-method-choose-ios.md)에 설명되어 있습니다.

## <a name="prerequisites"></a>전제 조건

iOS 장치 등록을 설정하기 전에 다음 필수 구성 요소를 완료합니다.

- [Apple MDM push certificate](apple-mdm-push-certificate-get.md)
- IOS 장치에 대한 실제 액세스
- 장치 일련 번호 [iOS 일련 번호를 가져오는 방법](https://support.apple.com//HT204308) 참조)
- USB 연결 케이블
- [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)이 설치된 Mac PC
- [Apple Configurator 일련 번호 추가](apple-configurator-serial-numbers-add.md)

## <a name="setup-assistant-enrollment"></a>설치 도우미 등록

### <a name="create-an-apple-configurator-profile-for-devices"></a>장치에 대한 Apple Configurator 프로필 만들기

장치 등록 프로필은 장치 그룹에 적용되는 설정을 정의합니다. 다음 단계는 Apple Configurator를 사용하여 등록된 iOS 장치에 대한 장치 등록 프로필을 만드는 방법을 보여 줍니다.

1. Intune 포털에서 **장치 등록**을 선택한 다음 **Apple 등록**을 선택합니다.
2. **Apple Configurator 등록 설정 관리**에서 **AC 프로필**을 선택합니다.
3. **Apple Configurator 등록 프로필** 블레이드에서 **만들기**를 선택합니다.
4. **등록 프로필 만들기** 블레이드에서 프로필에 대한 이름 및 설명을 입력합니다.
5. **사용자 선호도**에서 이 프로필을 가진 장치가 사용자 선호도를 사용하여 등록되는지 사용하지 않고 등록되는지 선택합니다.

   - **사용자 선호도를 사용하여 등록** - 초기 설치 작업을 진행할 때 장치에 사용자 정보를 등록해야 합니다. 그러면 회사 데이터와 메일에 액세스하도록 허용할 수 있습니다. 사용자에게 속하고 앱 설치 같은 서비스에 회사 포털을 사용해야 하는 관리 장치에 대한 사용자 선호도를 설정해야 합니다.
   - **사용자 선호도를 사용하지 않고 등록**: 장치에 사용자 정보를 등록하지 않습니다. 로컬 사용자 데이터에 액세스하지 않고도 작업을 수행하는 장치에 대해 이 정보를 사용합니다. 기간 업무 앱을 설치하는 데 사용하는 회사 포털 앱 등 사용자 정보가 필요한 앱은 작동하지 않습니다.

6. **만들기**를 선택하여 프로필을 저장합니다.

### <a name="add-apple-configurator-serial-numbers"></a>Apple Configurator 일련 번호 추가

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

[설정 도우미와 함께 Apple Configurator를 사용하여 회사 소유 iOS 장치를 등록](apple-configurator-setup-assistant-enroll-ios.md)하려는 경우 다음 단계를 통해 Intune에 일련 번호를 추가할 수 있습니다. 일련 번호를 한 번에 하나씩 추가하거나, 일련 번호의 쉼표로 구분된 값(CSV) 파일을 업로드할 수 있습니다. 일련 번호를 추가한 후 프로필을 할당할 수 있습니다. 프로필에는 장치에 적용할 특정 관리 설정이 포함되어 있습니다.

iOS 장치를 등록하는 다른 방법은 [Intune에서 iOS 장치를 등록하는 방법 선택](enrollment-method-choose-ios.md)에 설명되어 있습니다.

**Intune에 Apple Configurator 일련 번호를 추가하려면**

1. 헤더 없이 2열로 구성된 쉼표로 구분된 값(.csv) 목록을 만듭니다. 왼쪽 열에 IMEI 식별자를 추가하고 오른쪽 열에 세부 정보를 추가합니다. 현재 목록의 최대값은 500개 행입니다. 텍스트 편집기에 .csv 목록이 다음과 같이 표시됩니다.

    F7TLWCLBX196,장치 세부 정보</br>
    DLXQPCWVGHMJ,장치 세부 정보

2. Azure Portal에서 **장치 등록**을 선택한 다음 **Apple 등록**을 선택합니다.
3. **Apple Configurator 등록 설정 관리**에서 **Apple Configurator 일련 번호**를 선택합니다.
4. **Apple Configurator 일련 번호** 블레이드에서 **추가**를 선택합니다.
5. **일련 번호 추가** 블레이드에서 가져오려는 일련 번호에 적용할 프로필을 선택합니다. 기존 세부 정보를 덮어쓰는 새로운 세부 정보가 포함된 파일을 가져오려면 ‘기존 식별자에 대한 세부 정보를 덮어씁니다’를 선택하여 기존 세부 정보를 새로운 세부 정보로 바꿉니다.
6. 일련 번호의 .csv 파일로 이동하여 **추가**를 선택합니다.

### <a name="assign-a-profile-to-specific-serial-numbers"></a>특정 일련 번호에 프로필 할당

Intune을 사용하면 Azure Portal의 두 군데에서 프로필을 할당할 수 있습니다. Apple Configurator 프로필 또는 장치를 기준으로 할당할 수 있습니다.

#### <a name="assign-by-devices"></a>장치 기준 할당
1. Intune 포털에서 **장치 등록**을 선택한 다음 **Apple 등록**을 선택합니다.
3. **Apple Configurator 장치** 블레이드에서 프로필을 할당할 일련 번호를 선택한 다음 **프로필 할당**을 선택합니다.
4. **프로필 할당** 블레이드에서 할당할 프로필을 선택한 다음 **할당**을 선택합니다.

#### <a name="assign-by-profiles"></a>프로필 기준 할당
1. Intune 포털에서 **장치 등록**을 선택한 다음 **Apple 등록**을 선택합니다.
2. **AC 프로필**을 선택하고 일련 번호를 할당할 프로필을 선택합니다.
3. 프로필에 대해 명명된 블레이드에서 **일련 번호** > **할당**을 선택합니다.
4. 프로필에 할당할 일련 번호를 선택한 다음 **할당** 단추를 선택합니다.

### <a name="export-the-profile-to-ios-devices"></a>iOS 장치로 프로필 내보내기
프로필을 만들고 일련 번호를 할당한 후에는 Intune에서 아래 설명된 형식의 파일 또는 URL로 프로필을 내보내야 합니다. 그런 다음 수동으로 Mac의 Apple Configurator 프로그램으로 가져오면 Apple Configurator 프로그램이 이를 장치에 배포합니다.

1. Intune 포털에서 **Apple Configurator 등록 프로필** 블레이드를 선택하고 내보낼 프로필을 선택합니다.
2. 프로필에 대한 블레이드에서 **프로필 내보내기**를 선택합니다.
3. iOS 장치를 연결한 상태에서 [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)에 프로필 URL을 복사합니다. iOS 장치에서 사용하는 Intune 프로필을 정의하기 위해 나중에 Apple Configurator에서 업로드합니다.

  다음 절차에서는 Apple Configurator를 통해 Apple 서비스에 이 프로필 URL을 업로드하여 iOS 장치에서 사용하는 Intune 프로필을 정의합니다.
4. Apple Configurator를 통해 Apple 서비스에 이 프로필 URL을 업로드하여 iOS 장치에서 사용하는 Intune 프로필을 정의합니다.
 1.  Mac 컴퓨터에서 **Apple Configurator 2**를 엽니다. 메뉴 모음에서 **Apple Configurator 2**를 선택한 후 **기본 설정**을 선택합니다.
  > [!WARNING]
  > 장치는 등록 프로세스 중에 공장 설정으로 다시 복원됩니다. 장치를 초기화하고 전원을 켜는 것이 좋습니다. 장치를 연결할 때 장치가 **Hello** 화면에 있어야 합니다.
  2. **기본 설정** 창에서 **서버**를 선택하고 더하기 기호(+)를 선택하여 MDM 서버 마법사를 시작합니다. **다음**을 선택합니다.
  3. Microsoft Intune을 사용한 iOS 장치용 설정 도우미 등록 아래 MDM 서버에 대한 **호스트 이름 또는 URL** 및 **등록 URL**을 입력합니다. 등록 URL에 Intune에서 내보낸 등록 프로필 URL을 입력합니다. **다음**을 선택합니다.  

    "서버 URL이 확인되지 않음"을 알리는 경고는 무시해도 안전합니다. 계속하려면 마법사가 완료될 때까지 **다음**을 선택합니다.
  4.  USB 어댑터를 사용하여 Mac 컴퓨터에 iOS 모바일 장치를 연결합니다.
  > [!WARNING]
  > 장치는 등록 프로세스 중에 공장 설정으로 다시 복원됩니다. 장치를 초기화하고 전원을 켜는 것이 좋습니다. 설정 도우미를 시작할 때 장치는 **Hello** 화면에 있어야 합니다.
  5.  **준비**를 선택합니다. **iOS 장치 준비** 창에서 **수동**을 선택하고 **다음**을 선택합니다.
  6. **MDM 서버에 등록** 창에서 만든 서버 이름을 선택하고 **다음**을 선택합니다.
  7. **장치 감독** 창에서 감독 수준을 선택하고 **다음**을 선택합니다.
  8. **조직 만들기** 창에서 **조직**을 선택하거나 새 조직을 만들고 **다음**을 선택합니다.
  9. **iOS 설정 도우미 구성** 창에서 사용자에게 제공되는 단계를 선택하고 **준비**를 선택합니다. 메시지가 표시되면 신뢰 설정을 업데이트하도록 인증합니다.  
  10. iOS 장치 준비가 완료되면 USB 케이블을 분리합니다.  
6.  **장치 배포**.
    이제 장치를 회사에 등록할 준비가 되었습니다. 장치를 끈 다음 사용자에게 배포합니다. 사용자가 장치를 켜면 설정 도우미가 시작됩니다.

## <a name="direct-enrollment"></a>직접 등록
Apple Configurator를 사용하여 iOS 장치를 직접 등록하는 경우 장치의 일련 번호를 몰라도 장치를 등록할 수 있습니다. 또한 등록 중에 Intune에서 장치 이름을 확인하기 전에 식별을 위해 장치에 이름을 지정할 수도 있습니다. 직접 등록된 장치의 경우 회사 포털 앱이 지원되지 않습니다. 이 설명서는 Mac 컴퓨터에서 Apple Configurator 2.0을 사용하고 있다고 가정합니다.

1. Intune 포털에서 **장치 등록**, **Apple 등록**, **AC 프로필**을 차례로 선택합니다.
2. **Apple Configurator 등록 프로필** 블레이드에서 **만들기**를 선택합니다.
3. **등록 프로필 만들기** 블레이드에서 프로필에 대한 이름 및 설명을 입력합니다.
4. **사용자 선호도**에서 **사용자 선호도를 사용하지 않고 등록**을 선택하여 장치에 사용자 정보를 등록하지 않도록 합니다. 로컬 사용자 데이터에 액세스하지 않고도 작업을 수행하는 장치에 대해 이 정보를 사용합니다. 기간 업무 앱을 설치하는 데 사용하는 회사 포털 앱 등 사용자 정보가 필요한 앱은 작동하지 않습니다.
5. **만들기**를 선택하여 프로필을 저장합니다.

### <a name="export-the-profile-as-mobileconfig-to-ios-devices"></a>프로필을 .mobileconfig로 iOS 장치에 내보내기

1. **프로필 내보내기** 블레이드에서 [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)로 등록 프로필을 다운로드하여 연결된 iOS 장치에 관리 프로필로 직접 푸시합니다. 이 방법을 사용하면 장치를 초기화하지 않아도 됩니다.
2. 다음 단계를 사용하여 Apple Configurator로 장치를 준비합니다.
  1. Mac 컴퓨터에서 Apple Configurator 2.0을 엽니다.
  2. USB 코드를 사용하여 iOS 장치를 Mac 컴퓨터에 연결합니다. 사진, iTunes 및 장치를 검색할 때 장치에 대해 열려 있는 기타 앱을 닫습니다.
  3. Apple Configurator에서 연결된 iOS 장치를 한 번 선택한 다음 **추가** 단추를 선택합니다. 장치에 추가할 수 있는 옵션이 드롭다운 목록에 나타납니다. **프로필**을 선택합니다.
  4. 파일 선택기를 사용하여 Intune에서 내보낸 .mobileconfig 파일을 선택하고 **추가**를 선택합니다. 프로필이 장치에 추가됩니다. 장치가 감독되지 않음인 경우 장치에서 설치에 동의해야 합니다.
3. 다음 단계를 사용하여 iOS 장치에 프로필을 설치합니다. 장치가 설정 도우미를 이미 완료했으며 사용할 준비가 된 상태여야 합니다. 등록 시 앱을 배포해야 하는 경우 앱 배포 시 Apple ID로 앱 스토어에 로그인해야 하기 때문에 장치에 Apple ID가 설정되어 있어야 합니다.
   1. iOS 장치 잠금을 해제합니다.
   2. **관리 프로필**에 대한 **프로필 설치** 대화 상자에서 **설치**를 선택합니다.
   3. 장치 암호 또는 Apple ID를 제공합니다(필요한 경우).
   4. **경고**를 수락하고 **설치**를 선택합니다.
   5. **원격 경고**를 수락하고 **신뢰**를 선택합니다.
   6. **프로필 설치됨** 상자에서 프로필이 설치됨 상태임을 확인하면 **완료**를 선택합니다.

    4. iOS 장치에서 **설정**을 열고 **일반** > **장치 관리** > **관리 프로필**로 이동합니다. 프로필 설치가 나열되는지 확인하고 iOS 정책 제한 및 설치된 앱을 확인합니다. 정책 제한 및 앱이 장치에 표시되는 데 최대 10분 정도 걸릴 수 있습니다.

    5. 장치를 배포합니다. 이제 iOS 장치가 Intune에 등록되고 관리됩니다.


## <a name="how-users-install-and-use-the-company-portal-on-their-devices"></a>사용자가 자신의 장치에서 회사 포털을 설치 및 사용하는 방법

사용자 선호도로 구성한 장치에서 회사 포털 앱을 설치하고 실행하여 앱을 다운로드하고 장치를 관리할 수 있습니다. 사용자는 장치를 받은 후 아래 설명된 추가 단계를 완료하여 설정 도우미를 완료하고 회사 포털 앱을 설치해야 합니다.
