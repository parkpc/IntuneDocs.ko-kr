---
title: "Android에서 사용자가 볼 수 있는 회사 포털 메시지 | Microsoft Docs"
description: "Intune 최종 사용자가 볼 수 있는 회사 포털 앱 메시지를 설명합니다."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 03/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3df993aa-48c5-4799-b68d-c85fe4f7b02c
ms.reviewer: jeffgilb
ms.suite: ems
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 81b85ea73759faaa71cbc404e14e8196e9455fb4
ms.contentlocale: ko-kr
ms.lasthandoff: 05/23/2017


---

# <a name="help-end-users-understand-company-portal-app-messages"></a>최종 사용자가 회사 포털 앱 메시지를 이해할 수 있도록 지원

> [!NOTE]
> 다음 정보는 Android 6.0 이상 장치에만 적용됩니다.

등록 프로세스의 서로 다른 시점에 문제의 원인일 수 있는 두 가지 메시지가 최종 사용자에게 표시됩니다.

- __회사 포털에서 통화를 하고 전화 통화를 관리하도록 허용하시나요?__
- __회사 포털에서 장치의 사진, 미디어 및 파일에 액세스하도록 허용하시겠습니까?__

## <a name="allow-company-portal-to-make-and-manage-phone-calls"></a>회사 포털에서 통화를 하고 전화 통화를 관리하도록 허용하시겠습니까?

### <a name="where-it-appears"></a>표시되는 곳
**회사 포털에서 통화를 하고 전화 통화를 관리하도록 허용하시겠습니까?**라는 메시지는 사용자가 장치를 등록하는 동안 회사 포털 앱에서 **등록**을 탭하면 표시됩니다.

### <a name="what-it-means"></a>의미
이 메시지를 수락하면 장치의 전화 및 IMEI 번호를 Intune 서비스에 보낼 수 있습니다. 이러한 번호는 관리 콘솔의 __하드웨어__ 페이지에 표시됩니다.

> [!NOTE]
> **회사 포털 앱에서 통화를 하거나 전화 통화를 관리하지 못합니다!** 메시지 텍스트는 Google에서 제어하므로 변경할 수 없습니다.

**하드웨어 페이지**를 표시하려면 **그룹** > **모든 모바일 장치** > **장치**로 이동합니다. 사용자의 장치를 선택하고 **속성 보기** > **하드웨어**로 이동합니다.

### <a name="what-happens-if-users-deny-access"></a>사용자가 액세스를 거부하는 경우 발생되는 작업
사용자가 액세스를 거부하는 경우 계속해서 회사 포털 앱을 사용하고 장치를 등록할 수 있습니다. 그러나 장치 전화 번호와 IMEI 번호가 관리 콘솔의 __하드웨어__ 페이지에 비어 있게 됩니다. 사용자가 액세스 거부 후 두 번째로 회사 포털 앱에 로그인할 때 메시지 표시를 중지할 수 있는 **다시 묻지 않음** 확인란이 메시지에 표시됩니다.

사용자가 액세스를 허용하지만 나중에 거부하는 경우 등록 후 다음에 사용자가 회사 포털 앱에 로그인할 때 메시지가 표시됩니다.

사용자가 나중에 액세스를 허용하려는 경우 **설정** > **앱** > **회사 포털** > **사용 권한** > **전화**로 이동하면 됩니다.

### <a name="how-to-explain-this-to-your-users"></a>사용자에게 이를 설명하는 방법
사용자에게 [Intune에서 Android 장치 등록](/intune-user-help/enroll-your-device-in-intune-android) 항목에서 자세한 내용을 참조하라고 합니다.

## <a name="allow-company-portal-to-access-your-contacts"></a>회사 포털에 연락처에 대한 액세스를 허용하시겠습니까?

### <a name="where-it-appears"></a>표시되는 곳
**회사 포털에서 연락처에 액세스하도록 허용하시겠습니까?**라는 메시지는 사용자가 장치를 등록하는 동안 회사 포털 앱에서 **등록**을 탭하면 표시됩니다.

### <a name="what-it-means"></a>의미
Intune이 회사 계정을 만들어 해당 장치에 등록된 사용자의 Azure Active Directory ID를 관리하도록 허용하려면 이 메시지에 동의합니다.

> [!NOTE]
> **Microsoft는 사용자의 연락처에 액세스하지 않습니다.** 메시지 텍스트는 Google에서 제어하므로 변경할 수 없습니다.

### <a name="what-happens-if-users-deny-access"></a>사용자가 액세스를 거부하는 경우 발생되는 작업
사용자가 액세스를 거부하면 장치가 Intune에 등록되지 않고 관리되지도 않습니다. 사용자가 액세스 거부 후 두 번째로 회사 포털 앱에 로그인할 때 메시지 표시를 중지할 수 있는 **다시 묻지 않음** 확인란이 메시지에 표시됩니다.

사용자가 액세스를 허용하지만 나중에 거부하는 경우 등록 후 다음에 사용자가 회사 포털 앱에 로그인할 때 메시지가 표시됩니다.

사용자가 나중에 액세스를 허용하려는 경우 **설정** > **앱** > **회사 포털** > **사용 권한** > **전화**로 이동하면 됩니다.

### <a name="how-to-explain-this-to-your-users"></a>사용자에게 이를 설명하는 방법
사용자에게 [Intune에서 Android 장치 등록](/intune-user-help/enroll-your-device-in-intune-android) 항목에서 자세한 내용을 참조하라고 합니다.

## <a name="allow-company-portal-to-access-photos-media-and-files-on-your-device"></a>회사 포털에서 장치의 사진, 미디어 및 파일에 액세스하도록 허용하시겠습니다?

### <a name="where-it-appears"></a>표시되는 곳
**회사 포털에서 장치의 사진, 미디어 및 파일에 액세스하도록 허용하시겠습니까?** 메시지는 사용자가 IT 관리자에게 로그를 보내기 위해 **데이터 전송**을 탭하면 표시됩니다.

### <a name="what-it-means"></a>의미
해당 장치에서 데이터 로그를 장치의 SD 카드에 기록하고 USB 케이블을 사용하여 이러한 로그를 이동하도록 허용하려면 이 메시지에 동의합니다.   

> [!NOTE]
> **회사 포털 앱에서 사용자의 사진, 미디어 및 파일에 액세스하지 못합니다.** 메시지 텍스트는 Google에서 제어하므로 변경할 수 없습니다.

### <a name="what-happens-if-users-deny-access"></a>사용자가 액세스를 거부하는 경우 발생되는 작업
사용자가 액세스를 거부하는 경우 메일을 통해 계속 로그 데이터를 보낼 수 있지만 로그가 장치의 SD 카드에 복사되지는 않습니다.

사용자가 액세스 거부 후 두 번째로 회사 포털 앱에 로그인할 때 메시지가 다시 표시되지 않도록 선택할 수 있는 **다시 묻지 않음** 확인란이 메시지에 표시됩니다. 사용자가 액세스를 허용하지만 나중에 거부하는 경우 다음에 로그를 보내려고 시도할 때 메시지가 표시됩니다. 사용자가 나중에 액세스를 허용할 경우 **설정** > **앱** > **회사 포털** > **사용 권한** > **저장소**로 이동한 다음 사용 권한을 설정합니다.


### <a name="how-to-explain-this-to-your-users"></a>사용자에게 이를 설명하는 방법
사용자에게 [메일을 통해 IT 관리자에게 로그 보내기](/intune-user-help/send-logs-to-your-it-admin-by-email-android) 항목을 참조하라고 합니다. 두 방법을 비교할 수 있도록 하려는 경우 [유선으로 IT 관리자에게 로그 보내기](/intune-user-help/send-logs-to-your-it-admin-by-cable-android)도 참조하라고 할 수 있습니다.


### <a name="see-also"></a>참고 항목
[Intune 사용 방법에 대해 최종 사용자에게 알릴 내용](/intune-classic/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune)
