---
title: "iOS 및 macOS 장치에 대한 Intune AirPrint 설정"
titlesuffix: Azure portal
description: "Intune을 사용하여 AirPrint 호환 프린터에 iOS 및 macOS 장치를 자동으로 연결하는 방법을 알아봅니다.\""
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 712a79fb-14ef-4f6b-aba5-1dfca900afd2
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5f55d05dd39fca02e72535cbbff9afb8d575ed9f
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2018
---
# <a name="airprint-settings-for-ios-and-macos-devices"></a>iOS 및 macOS 장치에 대한 AirPrint 설정

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

이 설정을 사용하여 네트워크에서 AirPrint 호환 프린터에 자동으로 연결하도록 iOS 또는 macOS 장치를 구성합니다. 계속하려면 프린터의 IP 주소와 리소스 경로가 필요합니다.

## <a name="find-airprint-printer-information"></a>AirPrint 프린터 정보 찾기

이 절차를 사용하여 iOS 장치 사용자가 알려진 AirPrint 프린터로 인쇄할 수 있도록 AirPrint 페이로드에 AirPrint 정보를 추가합니다.

1. AirPrint 프린터와 동일한 로컬 네트워크(서브넷)에 연결된 Mac에서 터미널을 엽니다(**/Applications/Utilities**).
2. 터미널에서 **ippfind**를 입력한 다음 Enter 키를 누릅니다.
3. 예를 들어 명령에서 반환하는 프린터 정보를 기록합니다(예: **ipp://myprinter.local.:631/ipp/port1**). 정보의 첫 번째 부분은 프린터의 이름이며, 마지막 부분은 리소스 경로입니다.
4. 터미널에서 **ping myprinter.local**을 입력한 다음 Enter 키를 누릅니다.
5. 명령에서 반환된 IP 주소 정보를 기록합니다(예: **PING myprinter.local (10.50.25.21)**).
6. 마지막으로, AirPrint 페이로드 설정에서 IP 주소 및 리소스 경로를 사용합니다. 예를 들어 IP 주소는 **10.50.25.21**, 리소스 경로는 **/ipp/port1**일 수 있습니다.

## <a name="configure-an-airprint-profile"></a>AirPrint 프로필 구성

1. **장치 기능** 블레이드에서 **AirPrint**를 선택합니다.
2. **AirPrint** 블레이드에서 AirPrint 대상을 추가하려면 해당 **IP 주소** 및 **리소스 경로**를 입력한 다음 **추가**를 클릭합니다.
3. 필요에 맞게 대상을 계속 추가합니다. 작업이 끝나면 **확인**을 선택합니다.

프린터 목록을 쉼표로 구분된 값(.csv) 파일에서 가져오거나 목록을 내보낼 수도 있습니다.


## <a name="next-steps"></a>다음 단계

이제 선택한 그룹에 장치 프로필을 할당할 수 있습니다. 자세한 내용은 [장치 프로필을 할당하는 방법](device-profile-assign.md)을 참조하세요.