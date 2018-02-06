---
title: "Windows AutoPilot Deployment 프로그램을 사용하여 Windows 장치 등록"
description: "Windows AutoPilot Deployment 프로그램을 사용하여 새 Windows 10 장치를 등록하는 방법을 알아봅니다."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 11/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a2dc5594-a373-48dc-ba3d-27aff0c3f944
ms.openlocfilehash: 56d585c52d3704e64c658cedb48cad7270ceeccf
ms.sourcegitcommit: 2c7794848777e73d6a9502b4e1000f0b07ac96bc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2018
---
# <a name="enroll-windows-devices-using-windows-autopilot-deployment-program"></a>Windows AutoPilot Deployment 프로그램을 사용하여 Windows 장치 등록
Windows AutoPilot Deployment 프로그램은 장치 프로비전을 간소화합니다. 사용자 지정 운영 체제 이미지 빌드 및 유지 관리는 시간이 오래 걸리는 프로세스입니다. 또한 최종 사용자에게 제공하기 전에 이러한 사용자 지정 운영 체제 이미지를 새 장치에 적용하여 사용 준비를 하는 데에도 시간이 걸릴 수 있습니다. Microsoft Intune 및 AutoPilot을 사용하면 사용자 지정 운영 체제 이미지를 빌드 및 유지 관리하고 장치에 적용할 필요 없이 최종 사용자에게 새 장치를 제공할 수 있습니다. Intune을 사용하여 AutoPilot 장치를 관리하는 경우 장치를 등록한 후에 정책, 프로필, 앱 등을 관리할 수 있습니다. 이점, 시나리오 및 필수 구성 요소에 대한 개요는 [Windows AutoPilot 개요](https://docs.microsoft.com/windows/deployment/windows-10-auto-pilot)를 참조하세요.

## <a name="prerequisites"></a>전제 조건
- [조직에 장치 등록](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot#device-registration-and-oobe-customization)
- [Windows 자동 등록 사용](https://docs.microsoft.com/intune-classic/deploy-use/set-up-windows-device-management-with-microsoft-intune#enable-windows-10-automatic-enrollment)
- [Azure Active Directory Premium 구독](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) <!--&#40;[trial subscription](http://go.microsoft.com/fwlink/?LinkID=816845)&#41;-->

## <a name="synchronize-devices"></a>장치 동기화
등록한 장치를 Intune으로 동기화하여 구성할 수 있습니다.

1. [Azure](https://portal.azure.com/)에 로그인합니다.
2. **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
3. **Intune** 아래에서 **장치 등록**을 선택합니다.
4. **Windows 등록** 아래의 **Windows AutoPilot Deployment 프로그램** 섹션에서 **장치**를 선택합니다.
5. **동기화**를 클릭하여 등록한 장치를 가져옵니다. 동기화가 진행 중이라는 메시지가 표시됩니다.
6. 보기를 새로 고쳐 새 장치를 확인합니다. 동기화되는 장치의 수에 따라 프로세스가 완료되는 데 몇 분 정도 걸릴 수 있습니다.  

## <a name="create-an-autopilot-deployment-profile"></a>AutoPilot 배포 프로필 만들기
AutoPilot 배포 프로필은 AutoPilot 장치를 구성하는 데 사용됩니다.
1. [Azure](https://portal.azure.com/)에 로그인합니다. 
2. **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
3. **Intune** 아래에서 **장치 등록**을 선택합니다.
4. **Windows 등록** 아래의 **Windows AutoPilot Deployment 프로그램** 섹션에서 **배포 프로필**을 선택합니다.
5. **프로필 만들기**를 클릭하고 이름과 설명(선택 사항)을 선택합니다. 
6. **조인 유형**에 대해 **Azure AD 조인됨**을 선택합니다.
7. **OOBE(첫 실행 경험)**에 대해 다음 옵션을 구성한 다음 **확인**을 클릭합니다. 
   - **개인 정보 설정**: 사용자에게 개인 정보 설정을 표시할지 여부를 선택합니다. 
   - **EULA(최종 사용자 사용권 계약)**: 사용자에게 EULA를 표시할지 여부를 선택합니다.
   - **사용자 계정 유형**: 사용자 계정 유형이 **관리자** 또는 **표준** 사용자인지 여부를 선택합니다.

     > [!Note]    
     > 전역 관리자 또는 회사 관리자 계정에는 이 설정이 적용되지 않습니다. 이러한 계정은 Azure AD의 모든 관리 기능에 액세스할 수 있으므로 표준 사용자가 될 수 없습니다.
8. **만들기**를 클릭하여 프로필을 만듭니다. 이제 AutoPilot 배포 프로필을 장치에 할당할 수 있습니다.
     
> [!Note]    
> 다음 설정은 모든 AutoPilot 배포 프로필을 사용하여 구성됩니다.
> - Cortana, OneDrive 및 OEM 등록 설정 페이지 건너뛰기
> - 회사 또는 학교에 자동으로 설정
> - 회사 또는 학교 브랜드가 있는 환경에 로그인    

## <a name="alerts-for-windows-autopilot-unassigned-devices-----163236---"></a>Windows AutoPilot 할당되지 않은 장치에 대한 경고 <!-- 163236 -->
Windows AutoPilot 할당되지 않은 장치에 대한 경고에서 AutoPilot 프로그램의 장치 중 AutoPilot 배포 프로필이 없는 장치의 수를 확인할 수 있습니다. 경고의 정보를 사용하여 프로필을 만들어서 할당되지 않은 장치에 할당하십시오. 경고를 클릭하면 Windows AutoPilot 장치의 전체 목록과 해당 장치에 대한 자세한 정보가 표시됩니다. 
1. [Azure](https://portal.azure.com/)에 로그인합니다. 
2. **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
3. **Intune** 아래에서 **장치 등록**을 선택합니다.
4. 경고를 보려면 **개요**를 선택합니다. 경고를 클릭하여 AutoPilot 장치 목록을 봅니다.  

## <a name="assign-an-autopilot-deployment-profile"></a>AutoPilot 배포 프로필 할당
AutoPilot 배포 프로필을 만든 후에는 해당 프로필을 선택한 장치에 할당할 수 있습니다.

1. [Azure](https://portal.azure.com/)에 로그인합니다. 
2. **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
3. **Intune** 아래에서 **장치 등록**을 선택합니다.
4. **Windows 등록** 블레이드의 **Windows AutoPilot Deployment 프로그램** 섹션에서 **장치**를 선택합니다.
5. 배포 프로필을 할당하려는 장치를 선택합니다. **상태** 열을 필터링하여 할당된 프로필이 없는 장치를 쉽게 찾을 수 있습니다. 
6. **프로필 할당**을 클릭하고 AutoPilot 배포 프로필을 선택한 다음 **할당**을 클릭합니다. 할당이 진행 중이라는 메시지가 표시됩니다.
7. 보기를 새로 고쳐 프로필이 장치에 할당되었는지 확인합니다. 선택한 장치의 수에 따라 프로세스가 완료되는 데 몇 분 정도 걸릴 수 있습니다. 

> [!Note]
> 새 프로필이 장치에 할당됩니다. Intune에 이미 등록된 장치의 경우 장치를 초기화하고 다시 등록하면 프로필이 적용됩니다.

### <a name="assign-a-different-autopilot-deployment-profile"></a>다른 AutoPilot 배포 프로필 할당
AutoPilot 배포 프로필을 장치에 할당한 후에 다른 프로필을 할당하려는 경우 새 프로필을 장치에 할당합니다.  

## <a name="edit-an-autopilot-deployment-profile"></a>AutoPilot 배포 프로필 편집 
AutoPilot 배포 프로필을 만든 후에는 배포 프로필의 특정 부분을 편집할 수 있습니다.   
1. [Azure](https://portal.azure.com/)에 로그인합니다. 
2. **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
3. **Intune** 아래에서 **장치 등록**을 선택합니다.
4. **Windows 등록** 아래의 **Windows AutoPilot Deployment 프로그램** 섹션에서 **배포 프로필**을 선택합니다. 
5. 편집하려는 프로필을 선택합니다. 
6. 왼쪽에 있는 **속성**을 클릭하여 배포 프로필의 이름이나 설명을 변경합니다. 변경한 후에 **저장**을 클릭합니다. 
7. OOBE 설정을 변경하려면 **설정**을 클릭합니다. 변경한 후에 **저장**을 클릭합니다. 

> [!NOTE]
> 업데이트된 프로필은 장치에 할당됩니다. 그러나 장치를 다시 설정하고 다시 등록할 때까지는 Intune에 이미 등록되어 있는 장치에 업데이트된 프로필이 적용되지 않습니다. 

## <a name="using-autopilot-in-other-portals"></a>다른 포털에서 AutoPilot 사용
모바일 장치 관리에 관심이 없는 경우 스토어(예: 비즈니스용 Microsoft 스토어)에서 AutoPilot을 사용할 수 있습니다. 다른 포털을 옵션으로 사용할 수 있지만, Intune만 사용하여 AutoPilot 배포를 관리하는 것이 좋습니다. Intune과 다른 포털을 사용하는 경우 Intune에서 수행할 수 없는 작업은 다음과 같습니다.
- Intune에서 만들었지만 다른 포털에서 편집한 프로필에 대한 변경 내용 표시
- 다른 포털에서 만든 프로필 동기화
- 다른 포털에서 수행한 프로필 할당에 대한 변경 내용 표시
- 다른 포털에서 수행한 프로필 할당 동기화
- 다른 포털에서 만든 장치 목록에 대한 변경 내용 표시

## <a name="next-steps"></a>다음 단계
등록한 Windows 10 장치에 대해 Windows AutoPilot을 구성한 후에는 이러한 장치를 관리하는 방법을 알아봅니다. 자세한 내용은 [Microsoft Intune 장치 관리란?](https://docs.microsoft.com/intune/device-management)을 참조하세요.