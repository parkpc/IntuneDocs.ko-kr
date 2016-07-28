---
title: "Intune에서 회사 포털 앱을 설치하고 Windows 장치를 등록하면 어떻게 되나요? | Microsoft Intune"
description: 
keywords: 
author: Staciebarker
manager: arob98
ms.date: 7/8/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d65e3452-5bbf-4d26-a06e-401ddcc47f39
ROBOTS: noindex,nofollow
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 376e6c1ae229187ab8ec73390f091f1d534365dd
ms.openlocfilehash: 25d2708dbc514717affa54cba195e5fef7d602ba


---


# Intune에서 회사 포털 앱을 설치하고 Windows 장치를 등록하면 어떻게 되나요?

회사 포털 앱을 설치한 후 사용하여 Windows 또는 Windows Phone 장치를 등록할 때 Windows 10 이전 장치에 대해 아래에서 설명된 것처럼 IT 관리자가 회사 또는 학교 데이터를 안전하게 보호하기 위해 장치를 관리하도록 할 수 있습니다. Windows 10 장치에 대한 자세한 내용은 [이 페이지](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-windows10.md)를 참조하세요.

## 등록 후 모든 Windows 장치에서 발생하는 결과
Intune에서 Windows 또는 Windows Phone 장치를 등록하는 경우에 다음을 수행할 수 있습니다.

-   회사 네트워크, 전자 메일 및 작업 파일 액세스

-   회사 포털 웹 사이트에서 회사 앱 가져오기(Windows 7 및 Vista의 경우 회사 포털 웹 사이트에서만 회사 앱을 가져올 수 있음)

-   회사 또는 학교 전자 메일 계정을 자동으로 구성

-   분실하거나 도난당한 경우 전화를 공장 설정으로 다시 설정

장치를 등록할 경우 다음과 같은 작업을 수행할 수 있는 권한을 IT 관리자에게 부여합니다.

-   사용자 장치를 장치 제조업체의 기본 설정으로 리셋합니다. 장치를 분실하거나 도난당한 경우 유용한 조치입니다.

-   모든 회사 관련 데이터와 설치된 비즈니스 앱을 제거합니다. 개인 데이터 및 설정은 제거되지 않습니다.

-   IT 관리자는 사용자가 개인적으로 설치한 소프트웨어를 비롯하여 컴퓨터에 설치되어 있는 모든 소프트웨어의 인벤토리를 만들 수 있습니다.

-   장치에서 암호나 PIN을 설정해야 합니다. 암호나 PIN을 설정할 경우 잘못된 암호로 너무 많이 시도하면 장치가 잠기거나 장치가 제조업체의 기본 설정으로 초기화(데이터 삭제 포함)될 수 있습니다.

-   장치를 분실하거나 도난당하는 경우 장치의 모든 데이터를 강제로 암호화하여 데이터를 보호하는 데 도움을 줍니다.

-   사용 약관에 조건에 동의해야 합니다.

-   IT 관리자가 컴퓨터에 정책을 강제 적용할 수 있습니다. 예를 들어 컴퓨터의 암호나 PIN을 설정하도록 요구할 수 있습니다. 암호나 PIN을 설정할 경우 잘못된 암호로 너무 많이 시도하면 컴퓨터가 잠기거나 컴퓨터 하드 드라이브에서 모든 데이터가 삭제될 수 있습니다.

-   SD 카드를 사용하지 못하도록 설정합니다.

## 등록 후 모든 Windows PC에서 발생하는 결과

-  IT 관리자가 컴퓨터를 관리할 수 있도록 하고, 사용자가 앱 및 지원 정보 같은 회사 리소스를 얻을 수 있도록, 사용자의 컴퓨터에 소프트웨어가 설치됩니다. IT 관리자가 이 소프트웨어를 자동으로 업데이트할 수 있습니다.

-  Intune Endpoint Protection이 사용자의 컴퓨터에 설치될 수 있습니다. Endpoint Protection은 바이러스 및 맬웨어를 검사하는 소프트웨어입니다.

-  IT 관리자는 사용자가 개인적으로 설치한 소프트웨어를 비롯하여 컴퓨터에 설치되어 있는 모든 소프트웨어의 인벤토리를 만들 수 있습니다.

-  사용 약관에 동의가 필요할 수 있습니다.

-  IT 관리자가 사용자 컴퓨터의 하드 드라이브에서 데이터를 수집하거나 삭제할 수 있습니다. 또한 전체 하드 드라이브를 삭제할 수도 있습니다.

-  IT 관리자가 사용자 컴퓨터에 앱 및 업데이트를 설치할 수 있습니다.

-  IT 관리자가 컴퓨터에 정책을 강제 적용할 수 있습니다. 예를 들어 컴퓨터의 암호나 PIN을 설정하도록 요구할 수 있습니다. 암호나 PIN을 설정할 경우 잘못된 암호로 너무 많이 시도하면 컴퓨터가 잠기거나 컴퓨터 하드 드라이브에서 모든 데이터가 삭제될 수 있습니다.


## 장치 등록 후 8시간마다 발생되는 작업
등록된 장치에서 약 8시간마다 다음 작업이 수행됩니다.

-   IT 관리자가 사용하도록 설정한 임의의 정책 또는 앱 업데이트를 다운로드합니다.

-   하드웨어 인벤토리 업데이트를 보냅니다.

-   임의의 회사 앱 인벤토리 업데이트를 보냅니다.

등록하는 단계는 [Intune에서 Windows 장치 등록](enroll-your-device-in-intune-windows.md)을 참조하세요. IT 관리자가 내 장치에서 무엇을 볼 수 있는지 알아보려면 [내가 Intune에서 장치를 등록하면 IT 관리자에게 무엇이 표시되나요?](what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows.md)를 참조하세요.

의문 사항이 있으면 IT 관리자에게 문의하세요. IT 관리자의 연락처 정보는 [회사 포털 웹 사이트](http://portal.manage.microsoft.com)를 참조하세요.

### 참고 항목
[Intune에서 Windows 장치 사용](using-your-windows-device-with-intune.md)



<!--HONumber=Jul16_HO3-->


