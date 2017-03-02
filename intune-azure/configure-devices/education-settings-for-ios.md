---
title: "iOS용 Intune 교육 설정 구성"
titleSuffix: Intune Azure preview
description: "Intune Azure 미리 보기: iOS 장치에서 교육 설정을 제어하는 데 사용할 수 있는 설정을 알아봅니다."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 44c427f8-0f22-43c2-8c29-e0f9fa533b1f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 8d801c0b264e95348f55b1d4046c00e43ead5d10
ms.lasthandoff: 02/18/2017


---

# <a name="how-to-configure-intune-education-settings-for-ios-devices-in-intune-azure-preview"></a>Intune Azure 미리 보기에서 iOS 장치에 대한 Intune 교육 설정을 구성하는 방법

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


## <a name="create-a-device-profile-containing-ios-education-settings"></a>iOS 교육 설정을 포함하는 장치 프로필 만들기

1. Azure 포털에 로그인합니다.
2. **추가 서비스** > **기타** > **Intune**을 선택합니다.
3. **Intune** 블레이드에서 **장치 구성**을 선택합니다.
2. **장치 구성** 블레이드에서 **관리** > **프로필**을 선택합니다.
3. 프로필 블레이드에서 **프로필 만들기**를 선택합니다.
4. **프로필 만들기** 블레이드에서 버전 업그레이드 프로필에 대한 **이름** 및 **설명**을 입력합니다.
5. **플랫폼** 드롭다운 목록에서 **iOS**를 선택합니다.
6. **프로필** 유형 드롭다운 목록에서 선택 **교육**을 선택합니다.
7. **교육** 블레이드에서 다음을 선택합니다.
    - **교사 루트 인증서 파일**
    - **교사 PKCS12/PFX 프로필**
    - **학생 루트 인증서 파일**
    - **학생 PKCS12/PFX 프로필**
8. 완료되면 **프로필 만들기** 블레이드로 돌아가서 **만들기**를 누릅니다.

프로필이 만들어지고 프로필 목록 블레이드에 표시됩니다.

