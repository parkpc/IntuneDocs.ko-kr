---
title: "Intune으로 Windows 10 버전 업그레이드 구성"
titlesuffix: Azure portal
description: "Intune을 사용하여 관리하는 Windows 10 장치를 다른 버전으로 업그레이드하는 방법을 알아봅니다.\""
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 12/17/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ae8b6528-7979-47d8-abe0-58cea1905270
ms.reviewer: coryfe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8581aea9db4c04efda5fe9f3281be95330bcd2e2
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2018
---
# <a name="how-to-configure-windows-10-edition-upgrades-in-microsoft-intune"></a>Microsoft Intune에서 Windows 10 버전 업그레이드를 구성하는 방법
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

이 문서에서는 Windows 10 버전 업그레이드 프로필을 구성하는 방법을 알아봅니다. 이 프로필을 사용하면 Windows 10 버전을 실행하는 장치를 다른 버전으로 자동으로 업그레이드할 수 있습니다. 

## <a name="before-you-start"></a>시작하기 전에
장치를 최신 버전으로 업그레이드하기 전에 다음 중 하나가 있어야 합니다.

- Windows 10 Desktop 버전용 정책에서 대상으로 지정하는 모든 장치에 새 버전의 Windows를 설치하는 데 유효한 제품 키 정책에서 대상으로 지정하는 모든 장치에 새 Windows 버전을 설치하기 위한 라이선스 정보가 포함된 Microsoft의 라이선스 파일 또는 KMS(Key Management Server) 또는 MAK(Multiple Activation Keys)를 사용할 수 있습니다(Windows 10 Mobile 및 Windows 10 Holographic 버전용).
- 정책을 지정한 Windows 10 장치를 Microsoft Intune에 등록해야 합니다. Intune PC 클라이언트 소프트웨어를 실행하는 PC에는 버전 업그레이드 정책을 사용할 수 없습니다.

## <a name="supported-upgrade-paths-for-the-windows-10-edition-upgrade-profile"></a>Windows 10 버전 업그레이드 프로필에 대해 지원되는 업그레이드 경로
다음은 Windows 10 버전 업그레이드 프로필에 대해 지원되는 업그레이드 경로 목록입니다. 업그레이드 후의 Windows 10 버전이 굵게 표시되고, 그 다음에 업그레이드가 지원되는 기존 버전 목록이 나와 있습니다.

**Windows 10 Education**
- Windows 10 Pro
- Windows 10 Pro Education
- Windows 10 Cloud
- Windows 10 Enterprise
- Windows 10 Core
    
**Windows 10 Education N 버전**    
- Windows 10 Pro N 버전
- Windows 10 Pro Education N 버전
- Windows 10 Cloud N 버전
- Windows 10 Enterprise N 버전
- Windows 10 Core N 버전
    
**Windows 10 Enterprise**
- Windows 10 Pro
- Windows 10 Cloud
- Windows 10 Core
    
**Windows 10 Enterprise N 버전**
- Windows 10 Pro N 버전
- Windows 10 Cloud N 버전
- Windows 10 Core N 버전
    
**Windows 10 Pro**
- Windows 10 Cloud
    
**Windows 10 Pro N 버전**
- Windows 10 Cloud N 버전
    
**Windows 10 Pro Education**
- Windows 10 Pro
- Windows 10 Cloud
- Windows 10 Core
    
**Windows 10 Pro Education N 버전**
- Windows 10 Pro N 버전
- Windows 10 Cloud N 버전
- Windows 10 Core N 버전

**Windows 10 Holographic for Business**
- Windows 10 Holographic

**Windows 10 Mobile Enterprise**
- Windows 10 Mobile

<!--The following table provides information about the supported upgrade paths for Windows 10 editions in this policy:

![supported](./media/check_grn.png)  (X) = not supported    
![unsupported](./media/x_blk.png)    (green checkmark) = supported    

|Upgrade from edition\Upgrade to edition|Education|Education N|Pro Education|Pro Education N|Enterprise|Enterprise N|Professional|Professional N|Mobile Enterprise|Holographic for Business|
|--------|--------|--------|--------|--------|--------|--------|--------|--------|--------|--------|--------|
|Pro|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Pro N|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Pro Education|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Pro Education N|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Cloud|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Cloud N|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Enterprise|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Enterprise N|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Core|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)   |![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Core N|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Mobile|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|
|Holographic|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png) -->

## <a name="create-a-device-profile-containing-device-restriction-settings"></a>장치 제한 설정을 포함하는 장치 프로필 만들기
1. Azure 포털에 로그인합니다.
2. **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
3. **Intune** 블레이드에서 **장치 구성**을 선택합니다.
2. **장치 구성** 블레이드에서 **관리** > **프로필**을 선택합니다.
3. 프로필 블레이드에서 **프로필 만들기**를 선택합니다.
4. **프로필 만들기** 블레이드에서 버전 업그레이드 프로필에 대한 **이름** 및 **설명**을 입력합니다.
5. **플랫폼** 드롭다운 목록에서 **Windows 10 이상**을 선택합니다.
6. **프로필** 유형 드롭다운 목록에서 선택 **버전 업그레이드**를 선택합니다.
7. **버전 업그레이드** 블레이드에서 다음 설정을 구성합니다.
    - **업그레이드할 대상 버전** - 드롭다운 목록에서 대상 장치를 업그레이드할 Windows 10 Desktop, Windows 10 Holographic 또는 Windows 10 Mobile 버전을 선택합니다.
    - **제품 키** - 대상으로 지정된 모든 Windows 10 Desktop 장치를 업그레이드하는 데 사용할 수 있는 Microsoft에서 가져온 제품 키를 지정합니다.<br>제품 키가 포함된 정책을 만든 후에는 나중에 제품 키를 편집할 수 없습니다. 보안상 키가 가려지기 때문입니다. 제품 키를 변경하려면 전체 키를 다시 입력해야 합니다.
    - **라이선스 파일** - **찾아보기**를 선택하여 대상으로 지정된 장치를 업그레이드하려는 Windows Holographic 또는 Windows 10 Mobile 버전에 대한 라이선스 정보를 포함하는 Microsoft에서 가져온 라이선스 파일을 선택합니다.
8. 완료되면 **프로필 만들기** 블레이드로 돌아가서 **만들기**를 누릅니다.

프로필이 만들어지고 프로필 목록 블레이드에 표시됩니다.

## <a name="next-steps"></a>다음 단계

계속해서 이 프로필을 그룹에 할당하려면 [장치 프로필을 할당하는 방법](device-profile-assign.md)을 참조하세요.

>[!NOTE]
>나중에 정책 할당을 제거해도 장치의 Windows 버전을 되돌리지 않고 계속 정상적으로 작동합니다.

