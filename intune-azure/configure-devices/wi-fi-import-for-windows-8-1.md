---
title: "Windows 8.1 이상에 대한 Wi-Fi 설정 가져오기"
titleSuffix: Intune Azure preview
description: "Intune Azure 미리 보기: Windows에서 Wi-Fi 설정을 Intune Wi-Fi 프로필로 가져오는 방법"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2c4e9b19-b268-4f6d-9663-7cdbe4e4a8dd
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: b0157f1021ae7c98392dc3c96481a4514758b059
ms.lasthandoff: 02/18/2017


---

# <a name="how-to-import-wi-fi-settings-for-windows-81-and-later-devices-in-microsoft-intune"></a>Microsoft Intune에서 Windows 8.1 이상 장치에 대한 Wi-Fi 설정을 가져오는 방법

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Windows 8.1 또는 Windows 10 데스크톱이나 모바일을 실행하는 장치의 경우에는 이전에 파일로 내보낸 Wi-Fi 구성 프로필을 가져올 수도 있습니다.

## <a name="export-wi-fi-settings-from-a-windows-device"></a>Windows 장치에서 Wi-Fi 설정 내보내기

Windows에서 **netsh wlan** 유틸리티를 사용하여 기존 Wi-Fi 프로필을 Intune에서 읽을 수 있는 XML 파일로 내보낼 수 있습니다. 필수 WiFi 프로필이 이미 설치되어 있는 Windows 컴퓨터에서 다음 절차를 따릅니다.
1. 내보낸 Wi-Fi 프로필에 대한 로컬 폴더를 만듭니다(예: **c:\WiFi**).
1. 관리자 권한으로 명령 프롬프트를 엽니다.
1. **netsh wlan show profiles** 명령을 실행하고 내보내려는 프로필의 이름을 적어 둡니다. 이 예제에서 프로필 이름은 **WiFiName**입니다.
1. 다음 명령을 실행합니다. **netsh wlan export profile name="ProfileName" folder=c:\Wifi**. 이렇게 하면 **Wi-Fi-WiFiName.xml**이라는 Wi-Fi 프로필이 대상 폴더에 생성됩니다.

## <a name="import-the-wi-fi-settings-into-intune"></a>Intune으로 Wi-Fi 설정 가져오기

1. Azure 포털에 로그인합니다.
2. **추가 서비스** > **기타** > **Intune**을 선택합니다.
3. **Intune** 블레이드에서 **장치 구성**을 선택합니다.
2. **장치 구성** 블레이드에서 **관리** > **프로필**을 선택합니다.
3. 프로필 블레이드에서 **프로필 만들기**를 클릭합니다.
4. **프로필 만들기** 블레이드에서 장치 제한 프로필에 대한 **이름** 및 **설명**을 입력합니다.
5. **플랫폼** 드롭다운 목록에서 **Windows 8.1 이상**을 선택합니다.
6. **프로필** 유형 드롭다운 목록에서 **Wi-Fi 가져오기**를 선택합니다.
7. **Wi-Fi 기본** 블레이드에서 다음을 구성합니다.
    - **연결 이름** Wi-Fi 연결 이름을 입력합니다. 이 이름은 최종 사용자가 사용 가능한 Wi-Fi 네트워크를 찾아볼 때 표시됩니다.
    - **프로필 XML** 찾아보기 단추를 클릭하여 Intune으로 가져오려는 Wi-Fi 프로필 설정이 포함된 XML 파일을 선택합니다.
    - **파일 내용** 선택한 구성 프로필에 대한 XML 코드를 표시합니다.
8. 완료되면 **프로필 만들기** 블레이드로 돌아가서 **만들기**를 누릅니다.

프로필이 만들어지고 프로필 목록 블레이드에 표시됩니다.

