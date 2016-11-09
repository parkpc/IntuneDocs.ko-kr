---
title: "모바일 장치를 등록하는 방법 선택 | Microsoft Intune"
description: "몇 가지 간단한 질문에 응답하여 Intune에서 모바일 장치를 등록 하는 방법 결정"
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: cac62b64-3f8b-47ae-aa66-970c7ba15466
ms.reviewer: dagerrit
translationtype: Human Translation
ms.sourcegitcommit: 899f50cfec9e7c20d2981c077f93e0fccf37dc2b
ms.openlocfilehash: 0e516e3762dc5712a1b2d0f83016b51b15b7070f


---

# 모바일 장치를 등록하는 방법 선택

다음 질문에 답변하면 관리하는 장치에 대한 최상의 등록 방법을 결정하는 데 도움이 됩니다.

## **직원들이 조직에 개인용 장치를 가져오나요, 아니면 조직에서 장치를 제공하나요?**

  - **사용자 소유의 장치** - BYOD("Bring your own device") 등록
  - **회사 소유의 장치** - COD 등록

> [!div class="button"]
[BYOD 등록 >](#what-byod-devices-can-your-users-enroll)   
> [!div class="button"]
[COD 등록 >](#are-your-company-owned-devices-shared-or-do-they-have-dedicated-users)

## **사용자는 어떤 BYOD 장치를 등록할 수 있나요?**

> [!div class="button"]
[Android](/intune/deploy-use/set-up-android-management-with-microsoft-intune) [iOS 및 Mac](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) [Windows 10 Mobile 및 Windows Phone](/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune) [Windows PC](/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune)

## **회사 소유 장치가 공유되나요, 아니면 전용 사용자에게 제공되나요?**

> [!div class="button"]
[공유 >](#what-operating-system-are-your-shared-devices-running)   [전용 >](#how-will-you-manage-dedicated-ios-devices)


## **어떤 운영 체제에서 공유 장치를 실행하고 있나요?**

  > [!div class="button"]
  [Windows >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [Android >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [iOS >](#how-will-you-manage-shared-ios-devices)

## **공유 iOS 장치는 어떻게 관리해야 하나요?**

  > [!div class="button"]
  [iOS DEP 등록 >](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [iOS 직접 등록 >](/intune/deploy-use/ios-direct-enrollment-in-microsoft-intune)  [DEM 등록 >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

  - **Apple의 DEP(장치 등록 프로그램)** - DEP로 구입되고 관리되는 iOS 장치는 등록 프로필을 사용하여 대상으로 지정될 수 있습니다. 사용자가 처음으로 장치를 켤 때 장치는 DEP 프로필을 다운로드하고 프로필 DEP를 사용하여 등록됩니다.

  - **Mac의 Apple Configurator** - Apple Configurator는 Mac PC에서 실행되는 Apple 응용 프로그램입니다. USB 케이블로 iOS 장치를 Mac에 연결하여 장치에 등록 프로필을 설치할 수 있습니다. 장치를 공장 기본 설정으로 복원하여 등록할 수 있는 경우 설정 도우미 등록을 사용합니다. 장치를 공장 기본 설정으로 복원하지 않으려는 경우에는 직접 등록을 사용합니다.

  - **장치 등록 관리자** -Intune의 DEM(장치 등록 관리자)을 사용하면 관리자가 단일 사용자 계정으로 여러 모바일 장치를 등록할 수 있습니다. 이러한 장치에는 사용자 선호도(예: 전용 사용자)가 있을 수 없으며 회사 포털 앱을 설치하고 로그인하여 장치를 등록해야합니다.

## **전용 iOS 장치는 어떻게 관리해야 하나요?**

  > [!div class="button"]
  [IMEI로 태그 지정 >](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers) [iOS DEP](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [iOS 설치 도우미](/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [IMEI로 태그 지정](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

  다음과 같은 방법으로 전용 사용자가 포함된 회사 소유 장치를 등록할 수 있습니다.

  - **Apple의 DEP(장치 등록 프로그램)** - DEP로 구입되고 관리되는 iOS 장치는 등록 프로필을 사용하여 대상으로 지정될 수 있습니다. 사용자가 처음으로 장치를 켤 때 장치는 DEP 프로필을 다운로드하고 Intune을 사용하여 등록됩니다.

  - **Mac의 Apple Configurator** - Apple Configurator는 Mac PC에서 실행되는 Apple 응용 프로그램입니다. USB 케이블로 iOS 장치를 Mac에 연결하여 장치에 등록 프로필을 설치할 수 있습니다. 장치를 공장 기본 설정으로 복원하여 등록할 수 있는 경우 설정 도우미 등록을 사용합니다.

  - **IMEI 번호로 태그 지정** - 회사 소유 장치의 IMEI(International Mobile Equipment Identity) 번호를 가져와서 Intune에서 회사 소유 장치로 장치에 태그를 지정할 수 있습니다. 이렇게 하면 사용자가 메일, 앱, 데이터 등의 회사 리소스에 액세스하기 위해 회사 포털을 설치하여 장치를 개인 장치로 등록할 수 있습니다.



<!--HONumber=Sep16_HO2-->


