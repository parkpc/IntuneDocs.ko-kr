---
title: "Apple Configurator 및 직접 등록을 사용하여 iOS 장치 등록"
titleSuffix: Intune Azure preview
description: "Intune Azure 미리 보기: Apple Configurator를 사용하여 직접 등록을 통해 회사 소유 iOS 장치를 등록하는 방법을 알아봅니다."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e6c0a430-1851-4108-812a-87e0fc2623b5
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 3758df744311392528be01c826527c2a9d879975
ms.openlocfilehash: 02675b6fe9872cb634d0515172f696cedc7e6463
ms.contentlocale: ko-kr
ms.lasthandoff: 05/10/2017


---

# <a name="enroll-ios-devices-with-apple-configurator-and-direct-enrollment"></a>Apple Configurator 및 직접 등록을 사용하여 iOS 장치 등록 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Intune은 Mac 컴퓨터에서 실행되는 [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)를 사용하여 회사 소유의 iOS 장치를 등록하도록 지원합니다. 이 프로세스는 장치를 초기화하지 않고 미리 정의된 정책을 사용하여 장치를 등록합니다. 이 방법은 **사용자 선호도 없음**이 지정된 장치용이며, iOS 장치를 Mac 컴퓨터에 USB로 연결하여 회사 등록을 설정해야 합니다.

>[!NOTE]
>이 등록 방법을 [장치 등록 관리자](enroll-devices-using-device-enrollment-manager.md) 방법과 함께 사용할 수 없습니다.

iOS 장치를 직접 등록하는 경우 장치의 일련 번호를 몰라도 장치를 등록할 수 있습니다. 또한 등록 중에 Intune에서 장치 이름을 확인하기 전에 식별을 위해 장치에 이름을 지정할 수도 있습니다. 직접 등록된 장치의 경우 회사 포털 앱이 지원되지 않습니다. 이 설명서는 Mac 컴퓨터에서 Apple Configurator 2.0을 사용하고 있다고 가정합니다.

iOS 장치를 등록하는 다른 방법은 [Intune에서 iOS 장치를 등록하는 방법 선택](choose-ios-enrollment-method.md)에 설명되어 있습니다.


## <a name="prerequisites"></a>전제 조건

iOS 장치 등록을 설정하기 전에 다음 필수 구성 요소를 완료합니다.

- [도메인 구성](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2)
- [MDM 기관 설정](set-mdm-authority.md)
- [그룹 만들기](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [회사 포털 구성](../manage-apps/company-portal-app.md)
- [Office 365 포털](http://go.microsoft.com/fwlink/p/?LinkId=698854)에서 사용자 라이선스 할당
- [Apple MDM Push Certificate 가져오기](get-an-apple-mdm-push-certificate.md)
- iOS 장치에 대한 실제 액세스 확인
- 장치 일련 번호([iOS 일련 번호를 가져오는 방법](https://support.apple.com//HT204308) 참조)
- USB 연결 케이블 준비
- [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)이 설치된 Mac PC가 있는지 확인

## <a name="create-an-apple-configurator-profile-for-devices"></a>장치에 대한 Apple Configurator 프로필 만들기

장치 등록 프로필은 장치 그룹에 적용되는 설정을 정의합니다. 다음 단계는 Apple Configurator를 사용하여 등록된 iOS 장치에 대한 장치 등록 프로필을 만드는 방법을 보여 줍니다.

1. Azure Portal에서 **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.

2. Intune 블레이드에서 **장치 등록**을 선택한 다음 **Apple 등록**을 선택합니다.

3. **Apple Configurator 등록 설정 관리**에서 **AC 프로필**을 선택합니다.

4. **Apple Configurator 등록 프로필** 블레이드에서 **만들기**를 선택합니다.

5. **등록 프로필 만들기** 블레이드에서 프로필에 대한 이름 및 설명을 입력합니다.

6. **사용자 선호도**에서 **사용자 선호도를 사용하지 않고 등록**을 선택하여 장치에 사용자 정보를 등록하지 않도록 합니다. 로컬 사용자 데이터에 액세스하지 않고도 작업을 수행하는 장치에 대해 이 정보를 사용합니다. 기간 업무 앱을 설치하는 데 사용하는 회사 포털 앱 등 사용자 정보가 필요한 앱은 작동하지 않습니다.

7. **만들기**를 선택하여 프로필을 저장합니다.

## <a name="export-the-profile-as-mobileconfig-to-ios-devices"></a>프로필을 .mobileconfig로 iOS 장치에 내보내기

1. **프로필 내보내기** 블레이드에서 [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)로 등록 프로필을 다운로드하여 연결된 iOS 장치에 관리 프로필로 직접 푸시합니다. 이 방법을 사용하면 장치를 초기화하지 않아도 됩니다.

2. 다음 단계를 사용하여 Apple Configurator로 장치를 준비합니다.

   a. Mac 컴퓨터에서 Apple Configurator 2.0을 엽니다.

   b. USB 코드를 사용하여 iOS 장치를 Mac 컴퓨터에 연결합니다. 사진, iTunes 및 장치를 검색할 때 장치에 대해 열려 있는 기타 앱을 닫습니다.

   c. Apple Configurator에서 연결된 iOS 장치를 한 번 선택한 다음 **추가** 단추를 선택합니다. 장치에 추가할 수 있는 옵션이 드롭다운 목록에 나타납니다. **프로필**을 선택합니다.

   d. 파일 선택기를 사용하여 Intune에서 내보낸 .mobileconfig 파일을 선택하고 **추가**를 선택합니다. 프로필이 장치에 추가됩니다. 장치가 감독되지 않음인 경우 장치에서 설치에 동의해야 합니다.

3. 다음 단계를 사용하여 iOS 장치에 프로필을 설치합니다. 장치가 설정 도우미를 이미 완료했으며 사용할 준비가 된 상태여야 합니다. 등록 시 앱을 배포해야 하는 경우 앱 배포 시 Apple ID로 앱 스토어에 로그인해야 하기 때문에 장치에 Apple ID가 설정되어 있어야 합니다.

   a. iOS 장치 잠금을 해제합니다.

   b. **관리 프로필**에 대한 **프로필 설치** 대화 상자에서 **설치**를 선택합니다.

   c. 장치 암호 또는 Apple ID를 제공합니다(필요한 경우).

   d. **경고**를 수락하고 **설치**를 선택합니다.

   e. **원격 경고**를 수락하고 **신뢰**를 선택합니다.

   f. **프로필 설치됨** 상자에서 프로필이 설치됨 상태임을 확인하면 **완료**를 선택합니다.

4. iOS 장치에서 **설정**을 열고 **일반** > **장치 관리** > **관리 프로필**로 이동합니다. 프로필 설치가 나열되는지 확인하고 iOS 정책 제한 및 설치된 앱을 확인합니다. 정책 제한 및 앱이 장치에 표시되는 데 최대 10분 정도 걸릴 수 있습니다.

5. 장치를 배포합니다. 이제 iOS 장치가 Intune에 등록되고 관리됩니다.

