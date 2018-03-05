---
title: "TeamViewer를 사용하여 장치를 원격으로 관리하는 방법"
titlesuffix: Azure portal
description: "TeamViewer를 사용하여 장치를 원격으로 관리하는 방법을 알아봅니다."
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 2/14/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 72cdd888-efca-46e6-b2e7-fb9696bb2fba
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0219993e0322be06dbf9b26707789332039001f1
ms.sourcegitcommit: cccbb6730a8c84dc3a62093b8910305081ac9d24
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2018
---
# <a name="provide-remote-assistance-for-intune-managed-devices"></a>Intune에서 관리하는 장치에 대한 원격 지원 제공

Intune에서는 [TeamViewer](https://www.teamviewer.com) 소프트웨어(별매)를 사용하여 관리하는 장치의 사용자에게 원격 지원을 제공할 수 있습니다. 이 항목의 정보를 사용하여 시작합니다.

## <a name="before-you-start"></a>시작하기 전에

### <a name="supported-devices"></a>지원되는 장치

Intune 관리 Android 및 Windows 장치는 원격 관리를 지원합니다.

>[!NOTE]
>Windows Holographic(HoloLens), Windows 팀(Surface Hub) 및 Windows 10 S는 TeamViewer 소프트웨어에서 지원되지 않습니다.



### <a name="required-permissions"></a>필수 사용 권한

Azure 포털의 사용자에게 다음 권한이 [Intune 역할](https://docs.microsoft.com/intune-azure/access-control/role-based-access-control)로 할당되어 있는지 확인합니다.
- 관리자가 TeamViewer 커넥터 설정을 수정할 수 있도록 하려면 **원격 지원 업데이트** 권한을 부여합니다.
- 관리자가 새 원격 지원 요청을 시작할 수 있도록 하려면 **원격 지원 요청** 권한을 부여합니다. **원격 지원 요청** 권한이 있는 사용자가 모든 사용자의 세션을 시작하도록 요청할 수 있습니다. 임의 Intune 역할 할당 범위에 따라 제한되지 않습니다. Intune 역할 할당 범위에서는 원격 지원 요청을 시작할 수 있는 장치나 사용자를 제한하지 않습니다.

>[!NOTE]
>TeamViewer를 사용도록 설정하면 Intune Connector용 TeamViewer가 TeamViewer 세션을 만들고, Active Directory 데이터를 읽고, TeamViewer 계정 액세스 토큰을 저장할 수 있습니다.

### <a name="configure-the-intune-teamviewer-connector"></a>Intune TeamViewer 커넥터 구성

장치에 대한 원격 지원을 제공하려면 먼저 다음 단계에 따라 Intune TeamViewer 커넥터를 구성해야 합니다.


1. Azure 포털에 로그인합니다.
2. **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
3. **Intune** 블레이드에서 **장치**를 선택합니다.
4. **장치 및 그룹** 블레이드에서 **설정** > **TeamViewer 커넥터**를 선택합니다.
5. **TeamViewer 커넥터** 블레이드에서 **사용**을 클릭하고 TeamViewer 서비스 사용권 계약을 확인한 다음 동의합니다.
6. **권한을 부여하려면 TeamViewer에 로그인합니다.**를 선택합니다.
7. TeamViewer 사이트 웹 페이지가 열립니다. TeamViewer 라이선스 자격 증명을 입력하고 **로그인**을 클릭합니다.


## <a name="how-to-remotely-administer-a-device"></a>장치를 원격으로 관리하는 방법

1. Azure 포털에 로그인합니다.
2. **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
3. **Intune** 블레이드에서 **장치**를 선택합니다.
4. **장치** 블레이드에서 **관리** > **모든 장치**를 선택합니다.
5. 원격으로 관리할 장치를 선택한 다음 장치 속성 블레이드에서 **자세히** > **새 원격 지원 세션**을 선택합니다.
6. Intune이 TeamViewer 서비스에 연결되면 장치에 대한 정보를 확인할 수 있습니다. **연결**을 선택하여 원격 세션을 시작합니다.

![Android TeamViewer 예](./media/android-teamviewer.png)

TeamViewer 창에서는 장치에 대한 원격 제어를 포함하여 장치서 다양한 원격 작업을 수행할 수 있습니다. 수행할 수 있는 동작에 대한 전체 세부 정보는 [TeamViewer 설명서](https://www.teamviewer.com/support/documents/)를 참조하세요.

작업이 완료되면 TeamViewer 창을 닫습니다.

## <a name="next-steps"></a>다음 단계

최종 사용자 장치의 회사 포털 앱 아이콘에 알림 플래그가 표시되며, 앱을 열 때도 알림이 표시됩니다. 그러면 사용자는 원격 지원 요청을 수락할 수 있습니다.
