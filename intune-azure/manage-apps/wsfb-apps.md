---
title: "비즈니스용 Windows 스토어에서 앱 관리| Intune Azure 미리 보기 | Microsoft Docs"
description: "Intune Azure 미리 보기: 비즈니스용 Windows 스토어에서 Intune에 앱을 동기화한 다음 할당 및 추적하는 방법을 알아봅니다."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2ed5d3f0-2749-45cd-b6bf-fd8c7c08bc1b
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: b213fcaae8f17af412687d01df6ea27b39b3edb9
ms.lasthandoff: 02/16/2017

---

# <a name="how-to-manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune"></a>Microsoft Intune을 사용하여 비즈니스용 Windows 스토어에서 구입한 앱을 관리하는 방법

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


[비즈니스용 Windows 스토어](https://www.microsoft.com/business-store)는 개별적으로 또는 대량으로 조직에 대한 앱을 찾고 구입할 수 있는 위치를 제공합니다. 스토어를 Microsoft Intune에 연결하여 Intune 포털에서 대용량 구입 앱을 관리할 수 있습니다. 예를 들면 다음과 같습니다.
* Intune을 사용하여 저장소에서 구입한 앱 목록을 동기화할 수 있습니다.
* 동기화되는 앱은 Intune 관리 콘솔에 나타나고 다른 앱처럼 할당할 수 있습니다.
* Intune 관리 콘솔에서 사용 가능한 라이선스 수 및 사용되는 라이선스 수를 추적할 수 있습니다.
* Intune은 사용 가능한 라이선스가 부족한 경우에 앱의 배포 및 설치를 차단합니다.

## <a name="before-you-start"></a>시작하기 전에
비즈니스용 Windows 스토어에서 앱 동기화 및 배포를 시작하기 전에 다음 정보를 검토합니다.
* Intune을 조직에 대한 모바일 장치 관리 기관으로 구성해야 합니다.
* Windows Store for Business에서 계정을 등록해야 합니다.
* Windows 업무용 스토어 계정을 Intune과 연결한 후 나중에 다른 계정으로 변경할 수 없습니다.
* 스토어에서 구입한 앱을 Intune에 수동으로 추가하거나 Intune에서 삭제할 수 없습니다. 비즈니스용 Windows 스토어와만 동기화할 수 있습니다.
* Intune은 비즈니스용 Windows 스토어에서 구입한 온라인 사용이 허가된 앱만을 동기화합니다.
* 이 기능을 사용하려면 장치가 Active Directory 도메인 서비스에 가입하거나 작업 공간에 연결되어 있어야 합니다.
* 등록된 장치가 1511 릴리스의 Windows 10 이상을 사용 중이어야 합니다.

## <a name="associate-your-windows-store-for-business-account-with-intune"></a>비즈니스용 Windows 스토어 계정을 Intune에 연결
Intune 콘솔에서 동기화를 사용하기 전에 관리 도구로 Intune을 사용하도록 스토어 계정을 구성해야 합니다.
1. Intune에 로그인하는 데 사용하는 동일한 테넌트 계정을 사용하여 업무용 스토어에 로그인해야 합니다.
2. 업무용 스토어에서 **설정** > **관리 도구**를 선택합니다.
3. 관리 도구 페이지에서 **관리 도구 추가**를 선택하고 **Microsoft Intune**을 선택합니다.

> [!NOTE]
> 둘 이상의 관리 도구를 사용하여 비즈니스용 Windows 스토어 앱을 배포하는 경우, 이전에는 그 중에 하나만 비즈니스용 Windows 스토어에 연결할 수 있었습니다. 이제 Intune 및 Configuration Manager와 같은 여러 관리 도구를 스토어에 연결할 수 있습니다.

이제 계속하고 Intune 콘솔에서 동기화를 설정할 수 있습니다.

## <a name="configure-synchronization"></a>동기화 구성

1. Azure 포털에 로그인합니다.
2. **추가 서비스** > **기타** > **Intune**을 선택합니다.
3. **Intune** 블레이드에서 **앱 관리**를 선택합니다.
1. **모바일 앱** 블레이드에서 **설치** > **비즈니스용 Windows 스토어**를 선택합니다.
2. **사용**을 클릭합니다.
3. 아직 수행하지 않은 경우에는 링크를 클릭하여 Windows Store for Business에 등록하고 이전에 설명된 대로 계정을 연결합니다.
5. **언어** 드롭다운 목록에서 Intune 포털에 표시될 비즈니스용 Windows 스토어에서 앱의 언어를 선택합니다. 표시되는 언어에 관계 없이 사용 가능한 경우 최종 사용자의 언어로 설치됩니다.
6. **동기화**를 클릭하여 Windows 스토어에서 구입한 앱을 Intune으로 가져옵니다.

## <a name="synchronize-apps"></a>앱 동기화

1. **모바일 앱** 워크로드에서 **설치** > **비즈니스용 Windows 스토어**를 선택합니다.
2. **동기화**를 클릭하여 Windows 스토어에서 구입한 앱을 Intune으로 가져옵니다.

## <a name="assign-apps"></a>앱 할당

다른 Intune 앱을 배포하는 방법과 마찬가지로 스토어에서 앱을 할당합니다. 자세한 내용은 [Microsoft intune을 사용하여 그룹에 앱을 할당하는 방법](deploy-apps.md)을 참조하세요. 그러나 **모든 앱** 페이지에서 앱을 할당하는 대신 **사용이 허가된 앱** 페이지에서 앱을 할당합니다.

업무용 앱에 대한 Windows 스토어를 할당할 때 앱을 설치하는 각 사용자에서 라이선스가 사용됩니다. 배포된 앱에 대한 모든 사용 가능한 라이선스를 사용하는 경우에는 복사본을 더 이상 배포할 수 없습니다. 다음 작업 중 하나를 수행해야 합니다.
* 일부 장치에서 앱을 제거합니다.
* 충분한 라이선스를 보유한 사용자만을 대상으로 하도록 현재 배포 범위를 줄입니다.
* Windows Store for Business에서 더 많은 앱 사본을 구입합니다.

> [!Important]
> 배포된 앱은 장치를 등록한 사용자만 사용할 수 있습니다. 다른 사용자는 앱에 액세스할 수 없습니다.

