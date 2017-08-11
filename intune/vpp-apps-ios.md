---
title: "iOS 대량 구매 앱 관리"
titleSuffix: Intune on Azure
description: "iOS 스토어에서 대량 구매한 앱을 Intune에 동기화하고 해당 사용을 추적 및 관리하는 방법을 알아봅니다.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/26/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 51d45ce2-d81b-4584-8bc4-568c8c62653d
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 433cec8e0bc2012090e680e0a28a9a77d7b13a38
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/03/2017
---
# <a name="how-to-manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune"></a>Microsoft Intune을 사용하여 대량 구매 프로그램을 통해 구매한 iOS 앱을 관리하는 방법


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

iOS 앱 스토어는 회사에서 실행하려는 앱의 라이선스를 여러 개 구매하는 기능을 제공합니다. 앱의 여러 복사본을 구매할 경우 구매한 앱의 여러 복사본을 추적하는 관리 오버헤드를 줄일 수 있습니다.

Microsoft Intune에서는 다음을 수행하여 이 프로그램을 통해 구매한 앱을 관리할 수 있습니다.

- 앱 스토어에서 라이선스 정보 가져오기
- 사용한 라이선스 수 추적
- 소유한 것보다 많은 앱 복사본을 설치하지 않도록 방지

대량 구매 앱을 할당하는 데 사용할 수 있는 방법은 다음 두 가지입니다.

### <a name="device-licensing"></a>장치 라이선싱

장치에 앱을 할당하면 하나의 앱 라이선스가 사용되고 사용자가 할당한 장치와 연결된 상태로 남아 있습니다.
장치에 대량 구매 앱을 할당하면 장치의 최종 사용자가 Store에 액세스하기 위해 Apple ID를 제공하지 않아도 됩니다. 

### <a name="user-licensing"></a>사용자 라이선스

사용자에게 앱을 할당하면 하나의 앱 라이선스가 사용되고 해당 사용자와 연결됩니다. 앱은 사용자가 소유한 여러 장치에서 실행될 수 있습니다.
사용자에게 대량 구매 앱을 할당하면, 각 최종 사용자가 App Store에 액세스하기 위해 유효한 Apple ID가 있어야 합니다.


또한 Apple Volume Purchase Program Store에서 구매한 책을 Intune과 동기화, 관리 및 할당할 수 있습니다. Intune 포털에서 **책** 워크로드를 사용하여 책을 관리합니다. 책 관리 절차는 앱을 관리하는 데 사용하는 절차와 동일합니다.
시작하기 전에 Apple Volume Purchase Program 토큰을 업로드해야 합니다. 현재 책은 **필수** 설치로만 할당할 수 있습니다.
장치에 책을 할당할 때 해당 장치에는 기본 제공 iBooks 앱이 설치되어 있어야 합니다. 없는 경우 최종 사용자는 이 책을 읽기 위해 앱을 다시 설치해야 합니다. 현재로는 Intune을 사용하여 제거된 기본 제공 앱을 복원할 수 없습니다.


## <a name="manage-volume-purchased-apps-for-ios-devices"></a>iOS 장치용 대량 구매 앱 관리
[비즈니스용 Apple Volume Purchase Program](http://www.apple.com/business/vpp/) 또는 [교육용 Apple Volume Purchase Program](http://volume.itunes.apple.com/us/store)을 통해 iOS 앱의 라이선스를 여러 개 구매합니다. 이 프로세스에서는 Apple 웹 사이트에서 Apple VPP 계정을 설정하고 Apple VPP 토큰을 Intune에 업로드합니다.  그런 다음 대량 구매 정보를 Intune과 동기화하고 대량 구매 앱 사용을 추적할 수 있습니다.

## <a name="before-you-start"></a>시작하기 전에
시작하기 전에 Apple에서 VPP 토큰 하나를 가져와 Intune 계정에 업로드해야 합니다. 또한 다음 조건을 이해해야 합니다.

* 여러 대량 구매 프로그램 토큰을 Intune 계정과 연결할 수 있습니다.
* 이전에 VPP 토큰을 다른 제품에 사용한 경우 Intune에 사용할 토큰을 새로 생성해야 합니다.
* 각 토큰은 1년 동안 유효합니다.
* 기본적으로 Intune에서는 하루에 두 번 Apple VPP 서비스와 동기화합니다. 언제든지 수동 동기화를 시작할 수 있습니다.
* VPP 토큰을 Intune으로 가져온 후 같은 토큰을 다른 장치 관리 솔루션으로 가져오지 마세요. 가져오면 라이선스 할당과 사용자 레코드가 손실될 수 있습니다.
* Intune과 함께 iOS VPP를 사용하기 전에 다른 MDM(모바일 장치 관리) 공급업체를 사용하여 만든 기존 VPP 사용자 계정을 제거합니다. Intune은 보안 조치로 해당 사용자 계정을 Intune에 동기화하지 않습니다. Intune은 Intune에서 만든 Apple VPP 서비스의 데이터만 동기화합니다.
* Intune은 최대 256개의 VPP 토큰 추가를 지원합니다.
* 장치 등록 프로필 또는 Apple Configurator를 통해 등록된 장치에 대해 대량 구매 앱을 할당하는 경우 장치를 대상으로 하는 앱만 작동합니다. 대량 구매 앱의 대상을 사용자 선호도가 없는 DEP 장치의 사용자로 지정할 수 없습니다.
* VPP 토큰은 한 번에 하나의 Intune 계정에만 사용할 수 있습니다. 여러 Intune 테넌트에 대해 동일한 VPP 토큰을 다시 사용하지 마세요.
* 사용자 라이선스 모델을 사용하는 VPP 앱을 사용자 또는 장치(사용자 선호도 있음)에 할당하는 경우 해당 장치에서 Apple 계약조건에 동의할 때 각 Intune 사용자를 고유 Apple ID 또는 메일 주소와 연결해야 합니다.
새 Intune 사용자에 대해 장치를 설정하는 경우 해당 사용자의 고유한 Apple ID 또는 메일 주소로 구성해야 합니다. Apple ID 또는 메일 주소와 Intune 사용자는 고유한 쌍을 생성하며 최대 5개 장치에서 사용할 수 있습니다.


## <a name="to-get-and-upload-an-apple-vpp-token"></a>Apple VPP 토큰을 가져와 업로드하려면

1. Azure 포털에 로그인합니다.
2. **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
3. **Intune** 블레이드에서 **Mobile Apps**를 선택합니다.
1.  **Mobile Apps** 워크로드에서 **설정** > **iOS VPP 토큰**을 선택합니다.
2.  VPP 토큰 목록 블레이드에서 **추가**를 클릭합니다.
3.  **새 VPP 토큰** 블레이드에서 다음 정보를 지정합니다.
    - **VPP 토큰 파일** - 아직 수행하지 않은 경우 비즈니스용 Volume Purchase Program 또는 교육용 Volume Purchase Program에 등록합니다. 등록한 후 계정에 대한 Apple VPP 토큰을 다운로드하여 선택합니다.
    - **Apple ID** - 대량 구매 프로그램과 연결된 계정의 Apple ID를 입력합니다.
    - **VPP 계정 유형** - **비즈니스** 또는 **교육**을 선택합니다.
4. 작업이 끝나면 **업로드**를 클릭합니다.

토큰은 토큰 목록 블레이드에 표시됩니다.


언제든지 **지금 동기화**를 선택하여 Apple에 보관된 데이터를 Intune과 동기화할 수 있습니다.

> [!NOTE]
> Microsoft Intune은 iTunes Store에서 공개적으로 제공되는 앱의 정보만 동기화합니다. **iOS용 사용자 지정 B2B 앱**은 아직 지원되지 않습니다. 시나리오의 대상이 이러한 앱이라면 앱 정보가 동기화되지 않습니다.

## <a name="to-assign-a-volume-purchased-app"></a>대량 구매 앱을 할당하려면

1.  **모바일 앱** 워크로드에서 **관리** > **앱 라이선스**를 선택합니다.
2.  앱 목록 블레이드에서 할당할 앱을 선택한 다음 '**...**' > **그룹 할당**을 선택합니다.
3.  *<app name>* - **할당** 블레이드에서 **관리** > **할당**을 선택합니다.
4.  **그룹 선택**을 선택하고 **그룹 선택** 블레이드에서 앱을 할당할 Azure AD 사용자 또는 장치 그룹을 선택합니다.
5.  선택한 각 그룹에 대해 다음 설정을 선택합니다.
    - **형식** - 앱이 **사용 가능**(최종 사용자가 회사 포털에서 앱 설치 가능)인지 아니면 **필수**(최종 사용자 장치가 자동으로 앱을 설치)인지 선택합니다.
VPP 앱을 **사용 가능**으로 할당한 경우 앱 콘텐츠 및 라이선스가 앱 스토어에서 직접 할당됩니다.
    - **라이선스 형식** - **사용자 라이선싱** 또는 **장치 라이선싱**을 선택합니다.
6.  작업이 끝나면 **저장**을 선택합니다.


>[!NOTE]
>표시되는 앱 목록은 토큰과 관련이 있습니다. 여러 개의 VPP 토큰과 연결된 앱이 있을 경우 동일한 앱이 각 토큰마다 한 번씩, 여러 번 표시됩니다.

## <a name="further-information"></a>추가 정보

라이선스를 회수하려면 할당 작업을 제거로 변경해야 합니다. 앱이 제거된 후에는 라이선스가 회수됩니다.

적합한 장치를 가진 사용자가 VPP 앱을 처음 설치하려고 하면 Apple Volume Purchase Program에 가입하라는 메시지가 표시됩니다. 가입해야만 앱 설치가 진행됩니다. Apple 대량 구매 프로그램 참여 초대를 받으려면 사용자가 iOS 장치에서 iTunes 앱을 사용할 수 있어야 합니다. iTunes Store 앱을 사용하지 않도록 하는 정책을 설정한 경우에는 VPP 앱용 사용자 기반 라이선싱이 적용되지 않습니다. 이 경우에는 정책을 제거하여 iTunes 앱을 허용하거나, 장치 기반 라이선싱을 사용하면 됩니다.



## <a name="next-steps"></a>다음 단계

앱 할당을 모니터링하는 데 유용한 정보는 [앱을 모니터링하는 방법](apps-monitor.md)을 참조하세요.