---
# required metadata

title: 대량 구매 프로그램을 통해 구입한 iOS 앱 관리 | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 1dafc28a-7f8b-4fe0-8619-f977c93d1140

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: mghadial
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune을 사용하여 대량 구매 프로그램을 통해 구입한 iOS 앱 관리
일부 앱 스토어는 회사에서 실행하려는 앱의 라이선스를 여러 개 구입하는 기능을 제공합니다. 이 기능을 사용하면 구입한 앱의 여러 복사본을 추적하는 관리 오버헤드를 줄일 수 있습니다.

Microsoft Intune에서는 앱 스토어에서 라이선스 정보를 가져오고 사용한 라이선스 수를 추적하며 소유한 것보다 많은 앱 복사본을 설치할 수 없도록 차단하여 이러한 프로그램을 통해 구입한 앱의 관리를 지원합니다.

> [!Important]
> 현재 Intune은 iOS VPP 앱 라이선스를 사용자에게 할당하며 장치에 할당하지 않습니다. 이 때문에 최종 사용자가 앱을 설치하려면 Apple ID 암호를 입력해야 합니다.

## iOS 장치용 대량 구매 앱 관리
[Apple 비즈니스용 VPP(대량 구매 프로그램)](http://www.apple.com/business/vpp/)를 통해 iOS 앱의 라이선스를 여러 개 구입합니다. 이 경우 Apple 웹 사이트에서 Apple VPP 계정을 설정하고 Apple VPP 토큰을 Intune에 업로드해야 합니다.  그런 다음 대량 구매 정보를 Intune과 동기화하고 대량 구매 앱 사용을 추적할 수 있습니다.

## 시작하기 전에
시작하기 전에 Apple에서 VPP 토큰 하나를 가져와 Intune 계정에 업로드해야 합니다. 또한 다음 사항을 이해해야 합니다.

* 각 조직은 하나의 VPP 계정 및 토큰만 사용할 수 있습니다.
* Apple VPP 계정을 Intune에 연결한 후에는 다른 계정을 연결할 수 없습니다. 따라서 사용하는 계정의 세부 정보를 여러 사람이 보유하는 것이 중요합니다.
* 이전에 VPP 토큰을 다른 제품에 사용한 경우 Intune에 사용할 토큰을 새로 생성해야 합니다.
* 각 토큰은 1년 동안 유효합니다.
* 기본적으로 Intune에서는 하루에 두 번 Apple VPP 서비스와 동기화합니다. 그러나 언제든지 수동 동기화를 시작할 수 있습니다.
* Intune에서 VPP 토큰을 가져온 후 동일한 토큰을 다른 장치 관리 솔루션으로 가져오지 마세요. 가져오면 라이선스 할당과 사용자 레코드가 손실될 수 있습니다.
* Intune과 함께 iOS VPP를 사용하기 전에 다른 MDM 공급업체를 사용하여 만든 기존 VPP 사용자 계정을 제거합니다. Intune은 보안 조치로 해당 사용자 계정을 Intune에 동기화하지 않습니다. Intune은 Intune에서 만든 Apple VPP 서비스의 데이터만 동기화합니다. 
* DEP(장치 등록 프로토콜)를 사용하여 등록한 장치에는 iOS VPP 앱을 배포할 수 없습니다.

## Apple VPP 토큰을 가져와 업로드하려면

1.  [Microsoft Intune 관리 콘솔](https://manage.microsoft.com)에서 **관리 ** &gt; **iOS 및 Mac OS X** &gt; **Volume Purchase Program**을 선택합니다.

2.  **Apple VPP 계정** 링크를 선택하고, 아직 등록하지 않은 경우 비즈니스용 Volume Purchase Program에 등록합니다. 등록한 후 계정에 대한 Apple VPP 토큰을 다운로드합니다.

3.  Intune 콘솔의 **Apple VPP(Volume Purchase Program) 관리** 페이지에서 **VPP 토큰 업로드**를 선택합니다.

4.  **VPP 토큰 업로드** 대화 상자에서 VPP 토큰 이름과 Apple ID를 입력하거나 붙여넣고 **업로드**를 선택합니다.

5.  경고 대화 상자에서 확인란을 선택하여 나중에 다른 VPP 계정으로 변경할 수 없음을 확인하고 **예**를 선택합니다.

이제 **대량 구매 프로그램** 페이지에서 마지막으로 업데이트된 시간, 예상 만료 시간 및 Intune과 마지막으로 동기화된 시간을 포함하여 Apple VPP 토큰에 대한 정보를 볼 수 있습니다.

언제든지 **지금 동기화**를 선택하여 Apple에 보관된 데이터를 Intune과 동기화할 수 있습니다.

## 대량 구매 앱 배포

1.  [Microsoft Intune 관리 콘솔](https://manage.microsoft.com)에서 **앱** &gt; **관리 소프트웨어** &gt; **대량 구매 앱**을 선택합니다. 이 목록에는 Apple VPP 서비스를 통해 동기화된 모든 앱이 표시됩니다.

2.  배포할 앱을 선택하고 **배포 관리**를 선택한 다음, [Microsoft Intune에서 앱 배포](deploy-apps-in-microsoft-intune.md) 항목의 지침에 따라 앱을 업로드하고 만들고 배포합니다.

앱을 **필수** 설치로 배포하면 앱을 설치하는 각 사용자가 라이선스 하나를 사용합니다.

라이선스를 회수하려면 배포 작업을 **제거**로 변경해야 합니다. 앱을 제거하면 라이선스가 회수됩니다.

적합한 장치를 가진 사용자가 VPP 앱을 처음 설치하려고 하면 Apple 대량 구매 프로그램에 가입하라는 메시지가 표시됩니다. 가입해야만 앱 설치가 진행됩니다.

> [!TIP] **VPP 사용 약관 상태** 열에서 앱이 배포된 각 사용자의 수락 상태를 확인합니다.

사용 가능한 추가 라이선스가 없으면 배포에 실패합니다.

## Apple VPP 앱을 모니터하려면
**관리 소프트웨어** &gt; **대량 구매 앱** 노드의 **앱** 작업 영역에서 배포된 VPP 앱과 사용한 라이선스 수를 모니터링할 수 있습니다.

> [!TIP] 앱 **필터**를 사용하여 각 앱 설치의 상태를 검사할 수도 있습니다.

### 참고 항목
[Microsoft Intune에서 앱 배포](deploy-apps-in-microsoft-intune.md)



<!--HONumber=Jun16_HO2-->


