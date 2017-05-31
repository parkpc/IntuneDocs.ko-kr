---
title: "iOS 장치 등록 - Apple Configurator 설정 도우미"
titleSuffix: Intune Azure preview
description: "Intune Azure 미리 보기: Apple Configurator를 사용하여 설정 도우미를 통해 회사 소유 iOS 장치를 등록하는 방법을 알아봅니다."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 04/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6d384cd0-b662-41e7-94f5-0c96790ab20a
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: e6b0bc51515a2b72c7574a7ca7e29c094f3bdbdb
ms.contentlocale: ko-kr
ms.lasthandoff: 05/23/2017


---

# <a name="enroll-ios-devices-with-apple-configurator-and-setup-assistant"></a>Apple Configurator 및 설정 도우미를 사용하여 iOS 장치 등록

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Intune은 Mac 컴퓨터에서 실행되는 [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)를 사용하여 회사 소유의 iOS 장치를 등록하도록 지원합니다. 이 프로세스는 장치를 공장 설정으로 초기화하고 설정 도우미를 실행할 수 있도록 준비하여 장치의 새 사용자용으로 회사 정책을 설치합니다.

>[!NOTE]
>이 등록 방법을 [장치 등록 관리자](device-enrollment-manager-enroll.md) 방법과 함께 사용할 수 없습니다.

Apple Configurator를 사용하면 iOS 장치를 공장 설정으로 초기화하여 장치의 새 사용자용으로 설정할 수 있도록 준비할 수 있습니다. 이 방법을 사용하려면 iOS 장치를 Mac 컴퓨터에 USB로 연결하여 회사 등록을 설정해야 하며 사용자가 Apple Configurator 2.0을 사용하고 있는 것으로 간주합니다. 대부분의 시나리오는 Intune 회사 포털 앱을 활성화하기 위해 iOS 장치에 적용되는 정책에 사용자 선호도를 포함해야 합니다.

iOS 장치를 등록하는 다른 방법은 [Intune에서 iOS 장치를 등록하는 방법 선택](enrollment-method-choose-ios.md)에 설명되어 있습니다.

## <a name="prerequisites"></a>전제 조건

iOS 장치 등록을 설정하기 전에 다음 필수 구성 요소를 완료합니다.

- [Apple MDM Push Certificate 가져오기](apple-mdm-push-certificate-get.md)
- iOS 장치에 대한 실제 액세스 확인
- 장치 일련 번호([iOS 일련 번호를 가져오는 방법](https://support.apple.com//HT204308) 참조)
- USB 연결 케이블 준비
- [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)이 설치된 Mac PC가 있는지 확인
- [Apple Configurator 일련 번호 추가](apple-configurator-serial-numbers-add.md)


## <a name="create-an-apple-configurator-profile-for-devices"></a>장치에 대한 Apple Configurator 프로필 만들기

장치 등록 프로필은 장치 그룹에 적용되는 설정을 정의합니다. 다음 단계는 Apple Configurator를 사용하여 등록된 iOS 장치에 대한 장치 등록 프로필을 만드는 방법을 보여 줍니다.

1. Azure Portal에서 **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.

2. Intune 블레이드에서 **장치 등록**을 선택한 다음 **Apple 등록**을 선택합니다.

3. **Apple Configurator 등록 설정 관리**에서 **AC 프로필**을 선택합니다.

4. **Apple Configurator 등록 프로필** 블레이드에서 **만들기**를 선택합니다.

5. **등록 프로필 만들기** 블레이드에서 프로필에 대한 이름 및 설명을 입력합니다.

6. **사용자 선호도**에서 이 프로필을 가진 장치가 사용자 선호도를 사용하여 등록되는지 사용하지 않고 등록되는지 선택합니다.

   - **사용자 선호도를 사용하여 등록** - 초기 설치 작업을 진행할 때 장치에 사용자 정보를 등록해야 합니다. 그러면 회사 데이터와 메일에 액세스하도록 허용할 수 있습니다. 사용자에게 속하고 앱 설치 같은 서비스에 회사 포털을 사용해야 하는 관리 장치에 대한 사용자 선호도를 설정해야 합니다.

   - **사용자 선호도를 사용하지 않고 등록**: 장치에 사용자 정보를 등록하지 않습니다. 로컬 사용자 데이터에 액세스하지 않고도 작업을 수행하는 장치에 대해 이 정보를 사용합니다. 기간 업무 앱을 설치하는 데 사용하는 회사 포털 앱 등 사용자 정보가 필요한 앱은 작동하지 않습니다.

7. **만들기**를 선택하여 프로필을 저장합니다.

## <a name="assign-serial-numbers-to-an-apple-configurator-profile"></a>Apple Configurator 프로필에 일련 번호 할당

Apple Configurator 프로필을 만든 후에는 프로필에 장치 일련 번호를 할당할 수 있습니다. 일련 번호를 할당하려면 먼저 [Apple Configurator 일련 번호 추가](apple-configurator-serial-numbers-add.md) 단계에 따라 Intune에 일련 번호를 추가해야 합니다.

### <a name="assign-serial-numbers-to-apple-configurator-profiles"></a>Apple Configurator 프로필에 일련 번호 할당

1. Azure Portal에서 **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.

2. **Apple Configurator 등록 프로필** 블레이드에서 일련 번호를 할당할 프로필을 선택합니다.

3. 프로필에 대해 명명된 블레이드에서 **일련 번호** > **할당**을 선택합니다.

4. 프로필에 할당할 일련 번호를 선택한 다음 **할당** 단추를 선택합니다.

## <a name="export-the-profile-to-ios-devices"></a>iOS 장치로 프로필 내보내기

프로필을 만들고 일련 번호를 할당한 후에는 Intune에서 아래 설명된 형식의 파일 또는 URL로 프로필을 내보내야 합니다. 그런 다음 수동으로 Mac의 Apple Configurator 프로그램으로 가져오면 Apple Configurator 프로그램이 이를 장치에 배포합니다.

### <a name="export-a-profile-using-setup-assistant-enrollment"></a>설정 도우미 등록을 사용하여 프로필 내보내기

1. Azure Portal에서 **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.

2. **Apple Configurator 등록 프로필** 블레이드에서 내보낼 프로필을 선택합니다.

3. 프로필에 대한 블레이드에서 **프로필 내보내기**를 선택합니다.

4. iOS 장치를 연결한 상태에서 [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)에 프로필 URL을 복사합니다. iOS 장치에서 사용하는 Intune 프로필을 정의하기 위해 나중에 Apple Configurator에서 업로드합니다.

  다음 절차에서는 Apple Configurator를 통해 Apple 서비스에 이 프로필 URL을 업로드하여 iOS 장치에서 사용하는 Intune 프로필을 정의합니다.

5. Apple Configurator를 통해 Apple 서비스에 이 프로필 URL을 업로드하여 iOS 장치에서 사용하는 Intune 프로필을 정의합니다.
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

    [Microsoft Intune에 대한 최종 사용자 교육 방법](https://docs.microsoft.com/intune/deploy-use/how-to-educate-your-end-users-about-microsoft-intune)을 참조하세요. 직접 최종 사용자를 [Intune에서 iOS 또는 macOS 장치 사용](https://docs.microsoft.com/intune/deploy-use/how-to-educate-your-end-users-about-microsoft-intune)으로 안내할 수도 있습니다.

## <a name="how-users-install-and-use-the-company-portal-on-their-devices"></a>사용자가 자신의 장치에서 회사 포털을 설치 및 사용하는 방법

사용자 선호도로 구성한 장치에서 회사 포털 앱을 설치하고 실행하여 앱을 다운로드하고 장치를 관리할 수 있습니다. 사용자는 장치를 받은 후 아래 설명된 추가 단계를 완료하여 설정 도우미를 완료하고 회사 포털 앱을 설치해야 합니다.

