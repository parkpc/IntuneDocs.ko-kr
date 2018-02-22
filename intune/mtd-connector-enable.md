---
title: "Intune과 Mobile Threat Defense 커넥터 사용"
titlesuffix: Azure portal
description: "Intune에서 Mobile Threat Defense 커넥터를 사용하도록 설정합니다."
keywords: 
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dbb6a37e-ba47-4b69-922c-d25e66c279f6
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0d5e90cb91032a88830e7dc9af1d66d854ab4963
ms.sourcegitcommit: 468480b61110ca81f737582ebbefd4efda6fd667
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2018
---
# <a name="enable-mobile-threat-defense-in-intune"></a>Intune에서 Mobile Threat Defense 사용

> [!NOTE] 
> 이 항목은 모든 Mobile Threat Defense 파트너에게 적용됩니다.

Intune에서 MTD(Mobile Threat Defense) 연결을 사용하도록 설정하려면 MTD 파트너 콘솔에서 Intune Connector가 이미 구성되어 있어야 합니다.

## <a name="to-enable-the-mtd-connector"></a>MTD 커넥터를 사용하도록 설정하려면

1. [Azure Portal](https://portal.azure.com)로 이동한 다음 Intune 자격 증명을 사용하여 로그인합니다. 정상적으로 로그인되면 **Azure 대시보드**가 표시됩니다.

2. **Azure 대시보드**의 왼쪽 메뉴에서 **추가 서비스**를 선택하고 텍스트 상자 필터에 **Intune**을 입력합니다.

3. **Intune**을 선택합니다. **Intune 대시보드**가 열립니다.

4. **Intune 대시보드**에서 **장치 준수**를 선택하고 **설치** 섹션 아래에서 **Mobile Threat Defense**를 선택합니다.

5. **Mobile Threat Defense** 블레이드에서 **추가**를 선택합니다.

6. 드롭다운 목록에서 **설치할 Mobile Threat Defense 커넥터**로 MTD 솔루션을 선택합니다.

    ![Intune Azure Portal의 MTD 설치](./media/enable-mtd-connector-1.png)

7. 조직의 요구 사항에 따라 전환 옵션을 사용하도록 설정합니다.

## <a name="mtd-toggle-options"></a>MTD 설정/해제 옵션

조직의 요구 사항에 따라 사용하도록 설정해야 하는 MTD 설정/해제 옵션을 결정할 수 있습니다. 자세한 내용은 다음과 같습니다.

- **Android 4.1+ 장치를 [MTD 파트너 이름] for Work MTD에 연결**: 이 옵션을 사용하도록 설정하는 경우 Android 4.1 이상 장치가 보안 위험을 Intune에 다시 보고하도록 지정할 수 있습니다.
    - **데이터를 받지 못한 경우 비규격으로 표시**: Intune이 MTD 파트너로부터 이 플랫폼에 대한 데이터를 받지 못한 경우 해당 장치를 비규격으로 간주합니다.
<br></br>
- **iOS 8.0+ 장치를 [MTD 파트너 이름] for Work MTD에 연결**: 이 옵션을 사용하도록 설정하는 경우 Android 4.1 이상 장치가 보안 위험을 Intune에 다시 보고하도록 지정할 수 있습니다.
    - **데이터를 받지 못한 경우 비규격으로 표시**: Intune이 MTD 파트너로부터 이 플랫폼에 대한 데이터를 받지 못한 경우 해당 장치를 비규격으로 간주합니다.
<br></br>
- **지원되지 않는 OS 버전 차단**: 장치가 지원되는 최소 버전보다 낮은 운영 체제를 실행 중인 경우 차단합니다.

- **파트너가 응답하지 않을 때까지 기간(일)**: 연결이 끊어져서 Intune에서 파트너가 응답하지 않는 것으로 간주할 때까지의 비활성 상태 기간(일)입니다. Intune은 응답하지 않는 MTD 파트너에 대한 준수 상태를 무시합니다.

> [!IMPORTANT] 
> 장치 준수 및 조건부 액세스 정책 규칙을 만들기 전에 MTD 앱을 추가하고 할당해야 합니다. 이렇게 하면 MTD 앱이 최종 사용자가 설치할 수 있는 상태로 준비되어 최종 사용자가 메일과 기타 회사 리소스에 액세스할 수 있게 됩니다.

> [!TIP]
> Mobile Threat Defense 블레이드에서 Intune과 MTD 파트너 간의 **연결 상태** 및 **마지막 동기화** 시간을 확인할 수 있습니다.
