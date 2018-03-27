---
title: 비즈니스용 Microsoft 스토어 앱 관리
description: Intune 콘솔에서 대량 구매 앱을 관리 및 배포하려는 경우 Microsoft Intune을 비즈니스용 Microsoft 스토어에 연결
keywords: ''
author: mattbriggs
ms.author: mabrigg
manager: dougeby
ms.date: 02/02/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 8e38d47d-0c5e-40ce-b379-29d3657f5c28
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: coryfe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 50fc27efc34ab6c13fad714e41be0d87c5ab0df9
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2018
---
# <a name="manage-apps-you-purchased-from-the-microsoft-store-for-business-with-microsoft-intune"></a>Microsoft Intune을 사용하여 비즈니스용 Microsoft 스토어에서 구입한 앱 관리

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

[비즈니스용 Microsoft 스토어](https://www.microsoft.com/business-store)는 개별적으로 또는 대량으로 조직에 대한 앱을 찾고 구입할 수 있는 위치를 제공합니다. 저장소를 Microsoft Intune에 연결하여 Intune 콘솔에서 대용량 구입 앱을 관리할 수 있습니다. 예를 들면 다음과 같습니다.
* Intune을 사용하여 저장소에서 구입한 앱 목록을 동기화할 수 있습니다.
* 동기화되는 앱은 Intune 관리 콘솔에 나타나고 다른 앱처럼 배포할 수 있습니다.
* Intune 관리 콘솔에서 사용 가능한 라이선스 수 및 사용되는 라이선스 수를 추적할 수 있습니다.
* Intune은 사용 가능한 라이선스가 부족한 경우에 앱의 배포 및 설치를 차단합니다.

## <a name="before-you-start"></a>시작하기 전에
비즈니스용 Microsoft 스토어에서 앱 동기화 및 배포를 시작하기 전에 다음 정보를 검토합니다.
* Intune을 조직에 대한 모바일 장치 관리 기관으로 구성해야 합니다. 자세한 내용은 [Microsoft Intune에서 장치 등록을 위한 필수 조건](prerequisites-for-enrollment.md)을 참조하세요.
* 비즈니스용 Microsoft 스토어에서 계정을 등록해야 합니다.
* Windows 업무용 스토어 계정을 Intune과 연결한 후 나중에 다른 계정으로 변경할 수 없습니다.
* 스토어에서 구입한 앱을 Intune에 수동으로 추가하거나 Intune에서 삭제할 수 없습니다. 비즈니스용 Microsoft 스토어와만 동기화할 수 있습니다.
* Intune은 비즈니스용 Microsoft 스토어에서 구입한 온라인 사용이 허가된 앱만을 동기화합니다.
* 장치가 Active Directory 도메인 서비스에 가입하거나 작업 공간에 연결되어 있어야 이 기능을 사용할 수 있습니다.
* 등록된 장치가 1511 릴리스의 Windows 10을 사용 중이어야 합니다.

## <a name="associate-your-microsoft-store-for-business-account-with-intune"></a>비즈니스용 Microsoft 스토어 계정을 Intune에 연결
Intune 콘솔에서 동기화를 사용하기 전에 관리 도구로 Intune을 사용하도록 스토어 계정을 구성해야 합니다.
1. Intune에 로그인하는 데 사용하는 동일한 테넌트 계정을 사용하여 업무용 스토어에 로그인해야 합니다.
2. 업무용 스토어에서 **설정** > **관리 도구**를 선택합니다.
3. 관리 도구 페이지에서 **관리 도구 추가**를 선택하고 **Microsoft Intune**을 선택합니다.

> [!NOTE]
> 둘 이상의 관리 도구를 사용하여 비즈니스용 Microsoft 스토어 앱을 배포하는 경우, 이전에는 그 중에 하나만 비즈니스용 Microsoft 스토어에 연결할 수 있었습니다. 이제 Intune 및 Configuration Manager와 같은 여러 관리 도구를 스토어에 연결할 수 있습니다.

이제 계속하고 Intune 콘솔에서 동기화를 설정할 수 있습니다.

## <a name="configure-synchronization"></a>동기화 구성

1. [Microsoft Intune 관리 콘솔](https://manage.microsoft.com)에서 **관리자**를 선택합니다.
2. **관리** 작업 영역에서 **모바일 장치 관리**  >  **Windows**를 확장한 후 **비즈니스용 스토어**를 클릭합니다.
3. **비즈니스용 Microsoft 스토어** 페이지에서 다음을 수행합니다.
 * 아직 수행하지 않은 경우에는 링크를 클릭하여 비즈니스용 Microsoft 스토어에 등록합니다.
 * 등록했으면 **동기화 구성**을 선택합니다.
4. **비즈니스용 Microsoft 스토어 앱 동기화 구성** 대화 상자에서 **비즈니스용 Microsoft 스토어 동기화 사용**을 선택합니다.
5. **언어** 드롭다운 목록에서 Intune 콘솔에 표시될 비즈니스용 Microsoft 스토어에서 앱의 언어를 선택합니다. 표시되는 언어에 관계 없이 사용 가능한 경우 최종 사용자의 언어로 설치됩니다.
6. **확인**을 클릭합니다.

## <a name="synchronize-apps"></a>앱 동기화

1. **비즈니스용 Microsoft 스토어** 페이지에서 **지금 동기화**를 선택하여 Intune을 사용하여 스토어에서 구입한 앱을 동기화합니다.
2. **앱** 작업 영역에서 **앱** > **대량 구매 앱**을 선택하여 배포 가능한 앱을 보고 구매한 앱을 올바르게 가져왔는지 확인합니다. 이 노드의 앱은 소유하고 있는 총 라이선스의 수와 사용 가능한 라이선스의 수로 표시됩니다.
예를 들어 비즈니스용 Microsoft 스토어에서 온라인 사용이 허가된 회사 포털 앱을 구입하여 Intune 콘솔에 동기화한 다음 필요한 Windows 10 장치에 필수 앱으로 배포할 수 있습니다. 


## <a name="deploy-apps"></a>앱 배포

다른 Intune 앱을 배포하는 방법과 마찬가지로 스토어에서 앱을 배포합니다. 자세한 내용은 [Microsoft Intune에서 앱 배포](deploy-apps-in-microsoft-intune.md) 항목을 참조하세요.
비즈니스용 Microsoft 스토어를 배포할 때 앱을 설치하는 각 사용자에서 라이선스가 사용됩니다. 배포된 앱에 대한 모든 사용 가능한 라이선스를 사용하는 경우에는 복사본을 더 이상 배포할 수 없습니다. 다음 작업 중 하나를 수행해야 합니다.
* 일부 장치에서 앱을 제거합니다.
* 충분한 라이선스를 보유한 사용자만을 대상으로 하도록 현재 배포 범위를 줄입니다.
* 비즈니스용 Microsoft 스토어에서 더 많은 앱 사본을 구입합니다.

> [!Important]
> 배포된 앱은 장치를 등록한 사용자만 사용할 수 있습니다. 다른 사용자는 앱에 액세스할 수 없습니다.


### <a name="see-also"></a>참고 항목
[Microsoft Intune에서 모바일 장치에 앱 추가](add-apps-for-mobile-devices-in-microsoft-intune.md)
