---
title: "Intune에서 비즈니스용 Windows 업데이트 설정 구성"
titleSuffix: Azure portal
description: "Windows 10 장치에 대한 업데이트를 제어하도록 Intune에서 비즈니스용 Windows 업데이트 설정을 구성하는 방법을 알아봅니다.\""
keywords: 
author: dougeby
ms.author: dougeby
manager: angrobe
ms.date: 08/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 08f659cf-715e-4e10-9ab2-1bac3c6f2366
ms.reviewer: coryfe
ms.suite: ems
ms.openlocfilehash: 71dad71cdfa9f503a47e301f0b5d3fef2567f886
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/09/2017
---
# <a name="manage-software-updates"></a>소프트웨어 업데이트 관리

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Windows as a Service는 Windows 10 장치를 업데이트하는 방법입니다. Windows 10에서는 새로운 기능 업데이트 및 품질 업데이트에 모든 이전 업데이트의 내용이 포함됩니다. 따라서 최신 업데이트를 설치하면 Windows 10 장치가 완전히 최신 상태가 됩니다. 이전 버전의 Windows와 달리, 이제는 일부 업데이트가 아니라 전체 업데이트를 설치해야 합니다.

비즈니스용 Windows 업데이트를 사용하면 장치 그룹의 개별 업데이트를 승인할 필요가 없도록 업데이트 관리 환경을 단순화할 수 있습니다. 업데이트 출시 전략을 구성하여 현재 환경의 위험을 관리할 수 있으며 Windows 업데이트를 통해 적시에 업데이트가 설치됩니다. Microsoft Intune에서는 장치에서 업데이트 설정을 구성하는 기능 및 업데이트 설치를 지연하는 기능을 제공합니다. Intune에서는 업데이트를 저장하지 않고 업데이트 정책 할당만 저장합니다. 장치는 업데이트를 위해 Windows 업데이트에 직접 액세스합니다. Intune을 사용하여 **Windows 10 업데이트 링**을 구성 및 관리합니다. 업데이트 링에는 Windows 10 업데이트 설치 시기와 방법을 구성하는 설정 그룹이 포함됩니다. 예를 들어 다음을 구성할 수 있습니다.

- **Windows 10 서비스 분기**: 장치 그룹이 현재 분기나 비즈니스용 현재 분기 중 어느 쪽에서 업데이트를 수신하도록 할지 선택합니다.  
- **지연 설정**: 장치 그룹의 업데이트 설치를 연기하도록 업데이트 지연 설정을 구성합니다. 그러면 단계별 업데이트 출시에 따른 진행 과정을 검토할 수 있습니다.
- **일시 중지**: 업데이트 출시 과정에서 언제든지 문제를 발견하는 경우 업데이트의 설치를 연기합니다.
- **유지 관리 기간**: 업데이트를 설치할 수 있는 시간을 구성합니다.
- **업데이트 형식**: 설치되는 업데이트의 형식을 선택합니다. 예를 들어 품질 업데이트, 기능 업데이트 또는 드라이버가 있습니다.
- **설치 동작**: 업데이트가 설치되는 방법을 구성합니다. 예를 들어 설치 후 장치가 자동으로 다시 시작되도록 할지 설정합니다.
- **피어 다운로드**: 피어 다운로드를 구성할지 여부를 지정할 수 있습니다. 구성하는 경우, 한 장치가 업데이트 다운로드를 마치면 다른 장치가 이 장치로부터 업데이트를 다운로드할 수 있습니다. 그러면 다운로드 프로세스 속도가 향상됩니다.

업데이트 링을 만든 후에 위의 설정을 장치 그룹에 할당합니다. 업데이트 링을 사용하여 비즈니스 요구 사항을 반영하는 업데이트 전략을 만들 수 있습니다. 자세한 내용은 [비즈니스용 Windows 업데이트를 사용하여 업데이트 관리](https://technet.microsoft.com/itpro/windows/manage/waas-manage-updates-wufb)를 참조하세요.

## <a name="before-you-start"></a>시작하기 전에

- Windows 10 PC를 업데이트하려면 Windows Anniversary 업데이트가 포함된 Windows 10 Pro 이상을 실행 중이어야 합니다.

- Windows 업데이트는 다음 Windows 10 버전을 지원합니다.
    - Windows 10
    - Windows 10 Team(Surface Hub 장치용)

 Windows 10 Mobile 및 Windows 10 Holographic을 실행하는 장치는 지원되지 않습니다.

- Windows 장치에서 **피드백 및 진단** > **진단 및 사용 현황 데이터**를 **기본** 이상으로 설정해야 합니다.

    ![Windows의 진단 및 사용 현황 데이터 설정](./media/telemetry-basic.png)

    이 설정을 수동으로 구성할 수 있습니다. 아니면 Windows 10 이상에 대한 Intune 장치 제한 프로필을 사용할 수도 있습니다. 이렇게 하려면 **일반** > **진단 데이터 전송** 설정을 **기본** 이상으로 구성합니다. 장치 프로필에 대한 자세한 내용은 [장치 제한 설정을 구성하는 방법](device-restrictions-configure.md)을 참조하세요.

- Intune 관리 콘솔에는 소프트웨어 업데이트 동작을 제어하는 설정이 4가지 있습니다. 이 설정은 Windows 10 Desktop 및 Mobile 장치에 대한 일반 구성 정책의 일부입니다.
    - **자동 업데이트 허용**
    - **시험판 기능 허용**
    - **예약된 설치 날짜**
    - **예약된 설치 시간**

  클래식 포털에는 장치 구성 프로필에 제한된 개수의 다른 Windows 10 업데이트 설정도 있습니다. Azure Portal로 마이그레이션할 때 이러한 설정이 Intune 관리 콘솔에서 구성되어 있는 경우 다음을 수행하는 것이 좋습니다.

1. 필요한 설정을 사용하여 Azure Portal에서 Windows 10 업데이트 링을 만듭니다. **시험판 기능 허용** 설정은 더 이상 최신 Windows 10 빌드에 적용할 수 없기 때문에 Azure Portal에서 지원되지 않습니다. 업데이트 링을 만들 때 나머지 3개 설정뿐만 아니라 다른 Windows 10 업데이트 설정도 구성할 수 있습니다.

  > [!NOTE]
  > 클래식 포털에서 만든 Windows 10 업데이트 설정은 마이그레이션 후 Azure Portal에서 표시되지 않습니다. 그러나 이 설정은 계속 적용됩니다. 이러한 설정을 마이그레이션한 후 Azure Portal에서 마이그레이션된 정책을 편집하는 경우 해당 설정은 정책에서 제거됩니다.

2. 클래식 포털에서 업데이트 설정을 삭제합니다. Azure Portal로 마이그레이션하고 동일한 설정을 업데이트 링에 추가한 후에는 잠재적인 정책 충돌을 방지하기 위해 클래식 포털에서 설정을 삭제해야 합니다. 예를 들어, 서로 다른 값을 사용하여 동일한 설정이 구성된 경우 충돌이 생기며 클래식 포털에서 구성된 설정은 Azure Portal에 표시되지 않으므로 충돌을 쉽게 파악할 수 없습니다.

## <a name="how-to-create-and-assign-update-rings"></a>업데이트 링 만들기 및 할당 방법

1. Azure 포털에 로그인합니다.
2. **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
3. **Intune** 블레이드에서 **소프트웨어 업데이트**를 선택합니다.
4. **소프트웨어 업데이트** 블레이드에서 **관리** > **Windows 10 업데이트 링**을 선택합니다.
5. 업데이트 링 목록이 표시된 블레이드에서 **만들기**를 선택합니다.
6. **업데이트 링 만들기** 블레이드에서 업데이트 링의 이름과 선택적으로 설명을 입력한 다음 **설정**을 선택합니다.
7. **설정** 블레이드에서 다음 정보를 구성합니다.
    - **서비스 분기**: 장치가 Windows 업데이트를 수신할 분기(현재 분기 또는 비즈니스용 현재 분기)를 설정합니다.
    - **Microsoft 업데이트**: Microsoft Update에서 앱 업데이트를 검색할지 여부를 선택합니다.
    - **Windows 드라이버**: 업데이트 도중에 Windows 업데이트 드라이버를 제외할지 여부를 선택합니다.
    - **자동 업데이트 동작**: 업데이트를 검색, 다운로드 및 설치하도록 자동 업데이트 동작을 관리하는 방법을 선택합니다. 자세한 내용은 [Update/AllowAutoUpdate](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#update-allowautoupdate)를 참조하세요.
    - **품질 업데이트 지연 기간(일)**: 품질 업데이트를 연기할 일수를 지정합니다. 이러한 품질 업데이트는 릴리스된 지 최대 30일 동안 수신을 연기할 수 있습니다.  

    품질 업데이트는 일반적으로 기존 Windows 기능에 대한 수정 및 개선 사항이며 대체로 매월 첫 번째 화요일에 게시되지만 Microsoft의 재량에 따라 언제든지 릴리스될 수 있습니다. 사용 가능성에 따라 품질 업데이트 수신을 연기할지 여부 및 기간을 정의할 수 있습니다.
    - **기능 업데이트 지연 기간(일)**: 기능 업데이트를 연기할 일수를 지정합니다. 이러한 기능 업데이트는 릴리스된 지 180일 동안 수신을 연기할 수 있습니다.

    기능 업데이트는 일반적으로 Windows의 새로운 기능입니다. **서비스 분기** 설정을 **CB** 또는 **CBB**로 구성한 후, Microsoft의 Windows 업데이트를 통한 사용 가능성에 따라 기능 업데이트 수신의 연기 여부와 기간을 정의할 수 있습니다.

    예를 들면 다음과 같습니다.  
    **서비스 분기가 CB로 설정되고 지연 기간이 30일인 경우**: 기능 업데이트 X가 Windows 업데이트에서 1월에 CB로 처음으로 공개적으로 제공된다고 가정하겠습니다. 장치는 2월, 즉 30일 이후까지 업데이트를 수신하지 않습니다.

    **서비스 분기가 CBB로 설정되고 지연 기간이 30일인 경우**: 기능 업데이트 X가 Windows 업데이트에서 1월에 CB로 처음으로 공개적으로 제공된다고 가정하겠습니다. 4개월 후 4월에 기능 업데이트 X는 CBB로 릴리스됩니다. 장치는 이 CBB 릴리스 후 30일 후에 기능 업데이트를 수신하며 5월에 업데이트됩니다.

    - **배달 최적화**: 장치가 Windows 업데이트를 다운로드하는 방법을 선택합니다. 자세한 내용은 [DeliveryOptimization/DODownloadMode](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#deliveryoptimization-dodownloadmode)를 참조하세요.
8. 마치면 **확인**을 클릭한 다음 **업데이트 링 만들기** 블레이드에서 **만들기**를 클릭합니다.

새 업데이트 링이 업데이트 링 목록에 표시됩니다.

1. 링을 할당하려면 업데이트 링 목록에서 링을 선택한 다음 <*링 이름*> 탭에서 **할당**을 선택합니다.
2. 다음 탭에서 **그룹 선택**을 선택한 후 이 링을 할당할 그룹을 선택합니다.
3. 마치면 **선택**을 선택하여 할당을 완료합니다.



## <a name="update-compliance-reporting"></a>업데이트 준수 보고
OMS(Operations Management Suite)에서 Update Compliance라는 무료 솔루션을 사용하여 Windows 10 업데이트 출시를 모니터링할 수 있습니다. 자세한 내용은 [Monitor Windows Updates with Update Compliance(Update Compliance를 사용하여 Windows 업데이트 모니터링)](https://technet.microsoft.com/itpro/windows/manage/update-compliance-monitor)를 참조하세요. 이 솔루션을 사용하면 업데이트 준수를 보고할 Intune 관리 Windows 10 장치에 상용 ID를 배포할 수 있습니다.

Intune 콘솔에서 사용자 지정 정책의 OMA-URI 설정을 사용하여 상용 ID를 구성할 수 있습니다. 자세한 내용은 [Microsoft Intune의 Windows 10 장치용 Intune 정책 설정](https://docs.microsoft.com/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune)을 참조하세요.   

상용 ID 구성을 위한 OMA-URI 경로(대/소문자 구분): ./Vendor/MSFT/DMClient/Provider/ProviderID/CommercialID

예를 들어 **OMA-URI 설정 추가 또는 편집**에서 다음 값을 사용할 수 있습니다.

- **설정 이름**: Windows 분석 상용 ID
- **설정 설명**: Windows 분석 솔루션에 대 한 상용 ID 구성
- **데이터 형식:** 문자열
- **OMA-URI**(대/소문자 구분): ./Vendor/MSFT/DMClient/Provider/MS DM Server/CommercialID
- **값**: <*OMS 작업 영역에서 Windows 원격 분석 탭에 표시되는 GUID 사용*>

![Windows의 진단 및 사용 현황 데이터 설정](./media/commID.png)

<!--
1. Sign into the Azure portal.
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose **Software Updates**.
4. On the **Software Updates** blade, choose **Overview**. From here you can see general information about the status of any update rings you assigned.
4. On the **Windows 10 Updates** blade, choose **Monitor** > **Update ring deployment for devices**, **Update ring deployment for users**, or **Per-setting deployment state** to view more detailed information about update ring assignments.
-->





## <a name="how-to-pause-updates"></a>업데이트를 일시 중지하는 방법
업데이트를 일시 중지하는 시점부터 최대 35일 동안 장치가 기능 업데이트나 품질 업데이트를 수신하지 않게 일시 중지할 수 있습니다. 최대 일수가 경과하고 나면 일시 중지 기능은 자동으로 만료되고 장치가 Windows 업데이트에서 적용되는 업데이트를 검색합니다. 이 검색 이후 다시 업데이트를 일시 중지할 수 있습니다.
1. Azure 포털에 로그인합니다.
2. **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
3. **Intune** 블레이드에서 **소프트웨어 업데이트**를 선택합니다.
4. **소프트웨어 업데이트** 블레이드에서 **관리** > **Windows 10 업데이트 링**을 선택합니다.
5. 업데이트 링 목록이 표시된 블레이드에서 일시 중지할 링을 선택한 후 일시 중지하려는 업데이트의 유형에 따라 **...** > **품질 업데이트 일시 중지** 또는 **기능 업데이트 일시 중지**를 선택합니다.

> [!IMPORTANT]
> 일시 중지 명령을 실행하면 장치는 다음에 서비스에 체크 인할 때 이 명령을 수신합니다. 체크 인 이전에 예약된 업데이트가 설치될 수도 있습니다.
> 또한 일시 중지 명령을 실행할 때 대상 장치가 꺼져 있었던 경우 장치를 켜면 장치가 Intune을 사용해 체크 인하기 전에 예약된 업데이트를 다운로드 및 설치할 수도 있습니다.
