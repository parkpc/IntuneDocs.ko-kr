---
title: "iOS 대량 구매 앱 관리 | Microsoft 문서"
titlesuffix: Azure portal
description: "iOS 스토어에서 대량 구매한 앱을 Intune에 동기화하고 해당 사용을 추적 및 관리하는 방법을 알아봅니다.\""
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 09/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 51d45ce2-d81b-4584-8bc4-568c8c62653d
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 76764155e66ab69b5428712dae8a860233acaeb6
ms.sourcegitcommit: 751587b1c6ed15877152d770772748e042c1e3ff
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/13/2017
---
# <a name="how-to-manage-ios-apps-purchased-through-a-volume-purchase-program-with-microsoft-intune"></a>Microsoft Intune을 사용하여 대량 구매 프로그램을 통해 구매한 iOS 앱을 관리하는 방법


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

iOS 앱 스토어는 회사에서 실행하려는 앱의 라이선스를 여러 개 구매하는 기능을 제공합니다. 앱의 여러 복사본을 구매할 경우 구매한 앱의 여러 복사본을 추적하는 관리 오버헤드를 줄일 수 있습니다.

Microsoft Intune에서는 다음을 수행하여 이 프로그램을 통해 구매한 앱을 관리할 수 있습니다.

- 앱 스토어의 라이선스 정보 보고
- 사용한 라이선스 수 추적
- 소유한 것보다 많은 앱 복사본을 설치하지 않도록 도움

대량 구매 앱을 할당하는 데 사용할 수 있는 방법은 다음 두 가지입니다.

### <a name="device-licensing"></a>장치 라이선싱

장치에 앱을 할당하면 하나의 앱 라이선스가 사용되고 사용자가 할당한 장치와 연결된 상태로 남아 있습니다.
장치에 대량 구매 앱을 할당하면 장치의 최종 사용자가 Store에 액세스하기 위해 Apple ID를 제공하지 않아도 됩니다. 



### <a name="user-licensing"></a>사용자 라이선스

사용자에게 앱을 할당하면 하나의 앱 라이선스가 사용되고 해당 사용자와 연결됩니다. 앱은 사용자가 소유한 여러 장치에서 실행될 수 있습니다(단, Apple에서 제어하는 제한이 적용됨).
사용자에게 대량 구매 앱을 할당하면, 각 최종 사용자에게 App Store에 액세스하기 위한 유효하고 고유한 Apple ID가 있어야 합니다.

또한 Apple Volume Purchase Program Store에서 구매한 책을 Intune과 동기화, 관리 및 할당할 수 있습니다. 자세한 내용은 [대량 구매 프로그램을 통해 구매한 iOS 전자책을 관리하는 방법](vpp-ebooks-ios.md)을 참조하세요.

## <a name="manage-volume-purchased-apps-for-ios-devices"></a>iOS 장치용 대량 구매 앱 관리

### <a name="supports-apple-volume-purchase-program-volume-purchased-apps-for-ios-devices"></a>iOS 장치용 Apple Volume Purchase Program 대량 구매 앱 지원

[비즈니스용 Apple Volume Purchase Program](http://www.apple.com/business/vpp/) 또는 [교육용 Apple Volume Purchase Program](http://volume.itunes.apple.com/us/store)을 통해 iOS 앱의 라이선스를 여러 개 구매합니다. 이 프로세스에서는 Apple 웹 사이트에서 Apple VPP 계정을 설정하고 Apple VPP 토큰을 Intune에 업로드합니다.  그런 다음 대량 구매 정보를 Intune과 동기화하고 대량 구매 앱 사용을 추적할 수 있습니다.

### <a name="supports-business-to-business-volume-purchased-apps-for-ios-devices"></a>iOS 장치의 기업 간 대량 구매 앱 지원

또한 타사 개발자가 iTunes Connect에서 지정된 권한 있는 Volume Purchase Program for Business 멤버에 대해 개인적으로 앱을 배포할 수도 있습니다. 이러한 VPP for Business 멤버는 Volume Purchase Program 앱 스토어에 로그인하고 해당 앱을 구입할 수 있습니다. 최종 사용자가 구매한 VPP for Business 앱은 Intune 테넌트에 동기화됩니다.

## <a name="before-you-start"></a>시작하기 전에
시작하기 전에 Apple에서 VPP 토큰 하나를 가져와 Intune 계정에 업로드해야 합니다. 또한 다음 조건을 이해해야 합니다.

* 여러 대량 구매 프로그램 토큰을 Intune 계정과 연결할 수 있습니다.
* 이전에 VPP 토큰을 다른 제품에 사용한 경우 Intune에 사용할 토큰을 새로 생성해야 합니다.
* 각 토큰은 1년 동안 유효합니다.
* 기본적으로 Intune에서는 하루에 두 번 Apple VPP 서비스와 동기화합니다. 언제든지 수동 동기화를 시작할 수 있습니다.
* Intune과 함께 iOS VPP를 사용하기 전에 다른 MDM(모바일 장치 관리) 공급업체를 사용하여 만든 기존 VPP 사용자 계정을 제거합니다. Intune은 보안 조치로 해당 사용자 계정을 Intune에 동기화하지 않습니다. Intune은 Intune에서 만든 Apple VPP 서비스의 데이터만 동기화합니다.
* Intune은 최대 256개의 VPP 토큰 추가를 지원합니다.
* Apple DEP(장치 등록 프로필) 프로그램은 MDM(모바일 장치 관리) 등록을 자동화합니다. DEP를 사용하여 터치하지 않고도 엔터프라이즈 장치를 구성할 수 있습니다. Apple의 VPP에서 사용한 것과 동일한 프로그램 에이전트 계정을 사용하여 DEP 프로그램에서 등록할 수 있습니다. Apple 배포 프로그램 ID는 [Apple 배포 프로그램](https://deploy.apple.com) 웹 사이트 아랭 나열된 프로그램에 대해 고유하고 iTunes 스토어와 같은 Apple 서비스에 로그인하는 데 사용할 수 없습니다. 
* 사용자 라이선스 모델을 사용하는 VPP 앱을 사용자 또는 장치(사용자 선호도 있음)에 할당하는 경우 해당 장치에서 Apple 계약조건에 동의할 때 각 Intune 사용자를 고유 Apple ID 또는 메일 주소와 연결해야 합니다. 새 Intune 사용자에 대해 장치를 설정하는 경우 해당 사용자의 고유한 Apple ID 또는 메일 주소로 구성해야 합니다. Apple ID 또는 메일 주소와 Intune 사용자는 고유한 쌍을 생성하며 최대 5개 장치에서 사용할 수 있습니다.
* VPP 토큰은 한 번에 하나의 Intune 계정에만 사용할 수 있습니다. 여러 Intune 테넌트에 대해 동일한 VPP 토큰을 다시 사용하지 마세요.

>[!IMPORTANT]
>VPP 토큰을 Intune으로 가져온 후 같은 토큰을 다른 장치 관리 솔루션으로 가져오지 마세요. 가져오면 라이선스 할당과 사용자 레코드가 손실될 수 있습니다.

## <a name="to-get-and-upload-an-apple-vpp-token"></a>Apple VPP 토큰을 가져와 업로드하려면

1. Azure 포털에 로그인합니다.
2. **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
2.  VPP 토큰 목록 블레이드에서 **만들기**를 클릭합니다.
4. **VPP 토큰 만들기** 블레이드에서 다음 정보를 지정합니다.
    - **VPP 토큰 파일** - 아직 수행하지 않은 경우 비즈니스용 Volume Purchase Program 또는 교육용 Volume Purchase Program에 등록합니다. 등록한 후 계정에 대한 Apple VPP 토큰을 다운로드하여 선택합니다.
    - **자동 앱 업데이트** - **켜기**를 **끄기**로 선택하여 자동 업데이트를 사용하도록 설정합니다. 이 기능을 사용하면 장치가 검사할 때 Intune은 Intune 서비스를 통해 지정된 토큰에서 구입한 모든 앱을 업데이트합니다. 또한 앱 스토어 내의 VPP 앱 업데이트를 검색하고 장치가 체크 인하면 자동으로 장치에 푸시합니다.
4. 작업이 끝나면 **업로드**를 클릭합니다.

토큰은 토큰 목록 블레이드에 표시됩니다.

언제든지 **지금 동기화**를 선택하여 Apple에 보관된 데이터를 Intune과 동기화할 수 있습니다.

> [!NOTE]
> Microsoft Intune은 iTunes Store에서 공개적으로 제공되는 앱의 정보만 동기화합니다. **iOS용 사용자 지정 B2B 앱**은 아직 지원되지 않습니다. 시나리오의 대상이 이러한 앱이라면 앱 정보가 동기화되지 않습니다.

## <a name="to-assign-a-volume-purchased-app"></a>대량 구매 앱을 할당하려면

1.  **Intune** 블레이드의 **관리** 아래에서 **Mobile Apps** > **앱**을 선택합니다.
2.  앱 목록 블레이드에서 할당할 앱을 선택한 다음 **할당**을 선택합니다.
3.  ***앱 이름*** - **할당**에서 **그룹 선택**을 선택하고 **그룹 선택** 블레이드에서 앱을 할당할 Azure AD 사용자 또는 장치 그룹을 선택합니다.
5.  선택한 각 그룹에 대해 다음 설정을 선택합니다.
    - **형식** - 앱이 **사용 가능**(최종 사용자가 회사 포털에서 앱 설치 가능)인지 아니면 **필수**(최종 사용자 장치가 자동으로 앱을 설치)인지 선택합니다.
    - **라이선스 형식** - **사용자 라이선싱** 또는 **장치 라이선싱**을 선택합니다.
6.  작업이 끝나면 **저장**을 선택합니다.


>[!NOTE]
>표시되는 앱 목록은 토큰과 관련이 있습니다. 여러 개의 VPP 토큰과 연결된 앱이 있을 경우 동일한 앱이 각 토큰마다 한 번씩, 여러 번 표시됩니다.

## <a name="further-information"></a>추가 정보

라이선스를 회수하려면 할당 작업을 제거로 변경해야 합니다. 앱이 제거된 후에는 라이선스가 회수됩니다. 사용자에게 할당된 앱을 제거하면 Intune에서 해당 사용자와 연결되었던 모든 앱 라이선스를 회수하려고 합니다.

적합한 장치를 가진 사용자가 장치에 VPP 앱을 처음 설치하려고 하면 Apple Volume Purchase Program에 가입하라는 메시지가 표시됩니다. 가입해야만 앱 설치가 진행됩니다. Apple 대량 구매 프로그램 참여 초대를 받으려면 사용자가 iOS 장치에서 iTunes 앱을 사용할 수 있어야 합니다. iTunes Store 앱을 사용하지 않도록 하는 정책을 설정한 경우에는 VPP 앱용 사용자 기반 라이선싱이 적용되지 않습니다. 이 경우에는 정책을 제거하여 iTunes 앱을 허용하거나, 장치 기반 라이선싱을 사용하면 됩니다.



## <a name="next-steps"></a>다음 단계

앱 할당을 모니터링하는 데 유용한 정보는 [앱을 모니터링하는 방법](apps-monitor.md)을 참조하세요.