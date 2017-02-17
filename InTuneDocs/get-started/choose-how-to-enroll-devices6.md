---
title: "모바일 장치를 등록하는 방법 선택 | Microsoft 문서"
description: "몇 가지 간단한 질문에 응답하여 Intune에서 모바일 장치를 등록 하는 방법 결정"
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/14/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 40262e47-1ab4-437d-8ca5-c89b5022f91f
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
translationtype: Human Translation
ms.sourcegitcommit: b4295fbc9df88fa537f18b1280dfcc32702ccc51
ms.openlocfilehash: 173e95ac2d0039accb3465386bf67fb3dee90723


---
# <a name="choose-how-to-enroll-mobile-devices"></a>모바일 장치를 등록하는 방법 선택

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

이러한 일련의 질문에 답변하면 관리하는 장치에 대한 최상의 등록 방법을 결정하는 데 도움이 됩니다.

## <a name="how-will-you-manage-dedicated-corporate-owned-devices"></a>**회사 소유의 전용 장치를 어떻게 관리하나요?**

  > [!div class="button"]
[iOS DEP >](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune)  
> [!div class="button"]
[iOS 설정 길잡이 >](/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune)
> [!div class="button"]
[IMEI로 태그 지정 >](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

  다음과 같은 방법으로 전용 사용자가 포함된 회사 소유 장치를 등록할 수 있습니다.

  - **Apple의 DEP(장치 등록 프로그램)** - DEP로 구입되고 관리되는 iOS 장치는 등록 프로필을 사용하여 대상으로 지정될 수 있습니다. 사용자가 처음으로 장치를 켤 때 장치는 DEP 프로필을 다운로드하고 Intune을 사용하여 등록됩니다.

  - **Mac의 Apple Configurator** - Apple Configurator는 Mac PC에서 실행되는 Apple 응용 프로그램입니다. USB 케이블로 iOS 장치를 Mac에 연결하여 장치에 등록 프로필을 설치할 수 있습니다. 장치를 공장 기본 설정으로 복원하여 등록할 수 있는 경우 설정 도우미 등록을 사용합니다.

  - **IMEI 번호로 태그 지정** - 회사 소유 장치의 IMEI(International Mobile Equipment Identity) 번호를 가져와서 Intune에서 회사 소유 장치로 장치에 태그를 지정할 수 있습니다. 이는 전용("단일 사용자") Windows 및 Android 장치를 회사 소유로 확인하는 유일한 방법입니다. Apple 장치 등록 프로그램 또는 Apple 구성기에 등록되지 않는 iOS 장치도 IMEI 숫자로 태그될 수 있습니다. 장치가 “회사”로 태그되도록 미리 선언한 후에는 장치를 사용자에게 분배할 수 있습니다. 그런 다음 사용자는 회사 포털을 설치하여 장치를 전용 장치로 등록함으로써 전자 메일, 앱, 데이터 등의 회사 리소스에 액세스할 수 있습니다.

  > [!div class="button"]
  [< 뒤로](choose-how-to-enroll-devices3.md)



<!--HONumber=Feb17_HO3-->


