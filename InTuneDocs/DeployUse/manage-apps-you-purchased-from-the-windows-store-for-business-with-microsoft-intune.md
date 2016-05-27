---
# required metadata

title: 비즈니스용 Windows 스토어에서 구입한 앱 관리| Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8e38d47d-0c5e-40ce-b379-29d3657f5c28

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune을 사용하여 비즈니스용 Windows 스토어에서 구입한 앱 관리
[비즈니스용 Windows 스토어](https://www.microsoft.com/business-store)는 개별적으로 또는 대량으로 조직에 대한 앱을 찾고 구입할 수 있는 위치를 제공합니다. 저장소를 Microsoft Intune에 연결하여 Intune 콘솔에서 대용량 구입 앱을 관리할 수 있습니다. 예를 들어 다음과 같습니다.
* Intune을 사용하여 저장소에서 구입한 앱 목록을 동기화할 수 있습니다.
* 동기화되는 앱은 Intune 관리 콘솔에 나타나고 다른 앱처럼 배포할 수 있습니다.
* Intune 관리 콘솔에서 사용 가능한 라이선스 수 및 사용되는 라이선스 수를 추적할 수 있습니다.
* Intune은 사용 가능한 충분한 라이선스가 없는 경우 앱의 배포 및 설치를 차단합니다.

## 시작하기 전에
비즈니스용 Windows 스토어에서 앱 동기화 및 배포를 시작하기 전에 다음 정보를 검토합니다.
* Intune을 조직에 대한 모바일 장치 관리 기관으로 구성해야 합니다. 자세한 내용은 [Microsoft Intune에 장치를 등록하도록 준비](get-ready-to-enroll-devices-in-microsoft-intune.md)를 참조하세요.
* 비즈니스용 Windows 스토어의 계정에 등록해야 합니다.
* Windows 업무용 스토어 계정을 Intune과 연결한 후 나중에 다른 계정으로 변경할 수 없습니다.
* 스토어에서 구입한 앱을 Intune에 수동으로 추가하거나 Intune에서 삭제할 수 없습니다. 비즈니스용 Windows 스토어와만 동기화할 수 있습니다.
* Intune은 비즈니스용 Windows 스토어에서 구입한 온라인 사용이 허가된 앱만을 동기화합니다.

## 비즈니스용 Windows 스토어 계정을 Intune에 연결
Intune 콘솔에서 동기화를 사용하기 전에 관리 도구로 Intune을 사용하도록 스토어 계정을 구성해야 합니다.
1. Intune에 로그인하는 데 사용하는 동일한 테넌트 계정을 사용하여 업무용 스토어에 로그인해야 합니다.
2. 업무용 스토어에서 **설정** > **관리 도구**를 선택합니다..
3. 관리 도구 페이지에서 **관리 도구 추가**를 선택하고 Microsoft Intune을 선택합니다.

이제 계속하고 Intune 콘솔에서 동기화를 설정할 수 있습니다.

## 동기화 구성

1. [Microsoft Intune 관리 콘솔](https://manage.microsoft.com)에서 **관리**를 클릭합니다..
2. **관리** 작업 영역에서 **모바일 장치 관리**를 확장한 후 **비즈니스용 스토어**를 클릭합니다..
3. **비즈니스용 Windows 스토어** 페이지에서 다음을 수행합니다.
* 아직 수행하지 않은 경우 링크를 클릭하여 비즈니스용 Windows 스토어에 등록합니다.
* 등록했으면 **동기화 구성**을 클릭합니다.
4. **비즈니스 앱 동기화에 대한 Windows 스토어 구성** 대화 상자에서 **비즈니스 동기화에 대한 Windows 스토어 활성화**를 선택합니다..
5. **언어** 드롭다운 목록에서 Intune 콘솔에 표시될 비즈니스용 Windows 스토어에서 앱의 언어를 선택합니다. 표시되는 언어에 관계 없이 사용 가능한 경우 최종 사용자의 언어로 설치됩니다.
6. **확인**을 클릭합니다..

## 앱 동기화

1. **비즈니스용 Windows 스토어** 페이지에서 **지금 동기화**를 클릭하여 Intune을 사용하여 스토어에서 구입한 앱을 동기화합니다.
2. **앱** 작업 영역에서 **관리 소프트웨어** > **사용이 허가된 소프트웨어**를 클릭하여 사용 가능한 앱을 보고 구매한 앱을 올바르게 가져왔는지 확인합니다.
이 노드의 앱은 사용 가능한 라이선스의 수와 함께 소유하고 있는 총 라이선스의 수로 표시됩니다.

## 앱 배포

다른 Intune 앱을 배포하는 방법과 마찬가지로 스토어에서 앱을 배포합니다. 자세한 내용은 [Microsoft Intune에서 앱 배포](deploy-apps-in-microsoft-intune.md)를 참조하세요..
업무용 앱에 대한 Windows 스토어를 배포할 때 앱을 설치하는 각 사용자에서 라이선스가 사용됩니다. 배포된 앱에 대한 모든 사용 가능한 라이선스를 사용하는 경우 복사본을 더 이상 배포할 수 없습니다. 다음 작업 중 하나를 수행해야 합니다.
* 일부 장치에서 앱을 제거합니다.
* 충분한 라이선스를 보유한 사용자만을 대상으로 하도록 현재 배포 범위를 줄입니다.
* 비즈니스용 Windows 스토어에서 더 많은 앱 사본을 구입합니다.


### 참고 항목
[Microsoft Intune에서 모바일 장치에 앱 추가](add-apps-for-mobile-devices-in-microsoft-intune.md)




<!--HONumber=May16_HO1-->

