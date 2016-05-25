---
# required metadata

title: Microsoft Intune에서 회사 소유의 iOS 장치 등록 | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 2d3ca4ab-f20c-4d56-9413-f8ef19cf0722

# optional metadata

ROBOTS: noindex,nofollow
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune에서 회사 소유의 iOS 장치 등록
Microsoft Intune은 Mac 컴퓨터에서 실행되는 [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) 도구 또는 Apple DEP(장치 등록 프로그램)를 사용하여 회사 소유의 iOS 장치를 등록하도록 지원합니다.

세 가지 방법으로 회사에 등록된 iOS 장치를 등록할 수 있습니다.

-   **설치 도우미 등록** – 장치를 공장 기본 설정으로 복원하고 장치의 새 사용자가 설치하도록 준비합니다. 이 메서드는 관리자가 iOS 장치를 Apple Configurator를 실행하는 Mac 컴퓨터에 USB로 연결하도록 하여 등록을 미리 구성합니다. 그러면 설정 도우미 프로세스를 실행하는 사용자에게 장치를 전달하며 회사 또는 학교 자격 증명을 사용하여 장치를 구성하고 등록 프로세스를 완료하게 됩니다. [Apple Configurator 및 설정 도우미를 사용하여 iOS 장치 등록](ios-setup-assistant-enrollment-in-microsoft-intune.md)

-   **직접 등록** – 장치를 준비하는 동안 사용할 수 있도록 Apple Configurator 규격 파일을 만듭니다. 등록된 장치 설정이 공장 기본값으로 복원되지 않았으나 사용자 정보가 없습니다. 이 메서드는 관리자가 iOS 장치를 Apple Configurator를 실행하는 Mac 컴퓨터에 USB로 연결하도록 하여 장치를 등록합니다. [Apple Configurator 직접 등록을 사용하여 iOS 장치 등록](ios-direct-enrollment-in-microsoft-intune.md)

-   **DEP(장치 등록 프로그램)** – Apple의 장치 등록 프로그램을 통해 구매한 장치에 “무선으로” 등록 프로필을 배포합니다. 사용자가 장치에서 설정 도우미를 실행하는 경우 장치는 Intune에 등록됩니다.  DEP를 통해 등록된 장치는 사용자가 등록을 취소할 수 없습니다. [장치 등록 프로그램 iOS 장치 등록](ios-device-enrollment-program-in-microsoft-intune.md)




### 참고 항목
[Microsoft Intune에 장치를 등록하도록 준비](get-ready-to-enroll-devices-in-microsoft-intune.md)


<!--HONumber=May16_HO1-->


