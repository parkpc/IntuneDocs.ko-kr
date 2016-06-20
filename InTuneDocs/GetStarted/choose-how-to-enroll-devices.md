---
# required metadata

title: 모바일 장치를 등록하는 방법 선택 | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 06/06/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: cac62b64-3f8b-47ae-aa66-970c7ba15466

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: damionw
#ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# 모바일 장치를 등록하는 방법 선택

모바일 장치 등록은 스마트폰, 태블릿 및 PC를 Microsoft Intune에서 관리하도록 하는 프로세스입니다. 관리자는 다음 사항에 따라 장치를 등록하는 최상의 방법을 결정해야 합니다.

 -  소유권(개인 및 회사 소유)
 -  사용(공유 및 개인)
 -  플랫폼(iOS, Android, Windows Phone, Windows PC, Mac PC)

다음 질문에 답변하면 관리하는 장치에 대한 최상의 등록 방법을 결정하는 데 도움이 됩니다.

## 직원들이 자신의 장치를 갖고 오나요, 아니면 장치가 조직에서 제공되나요?

  **사용자 소유 장치** - "BYOD"(Bring Your Own Device) 등록 – 사용자가 장치에 Intune 회사 포털 앱을 설치하고 메일, 회사 앱, 회사 데이터 및 지원과 같은 회사 리소스에 액세스할 수 있습니다.  
  > [!div class="button"]   [BYOD 등록 >](..deploy-use/get-ready-to-enroll-devices-in-microsoft-intune)

  **회사 소유 장치** - COD(Company-Owned Devices)는 조직의 요구 사항과 관리될 장치의 유형에 따라 다양한 방법으로 등록될 수 있습니다. 다음 질문...

## 회사 소유 장치가 공유되나요, 아니면 개별 사용자에게 발급되나요?

**공유 회사 소유 장치** - 이러한 장치는 단일 사용자에게 발급되지 않으며 일반적으로 메일에 액세스하도록 구성되지 않습니다. 예로는 사용자가 필요에 따라 풀에서 꺼낸 다음 반환하는 키오스크 장치나 작업 지향 장치가 있습니다. 권장되는 등록 방법은 장치의 플랫폼에 따라 달라집니다.

  - **Windows 및 Android 장치** - *장치 등록 관리자*는 회사 포털 앱을 사용하여 많은 공유 장치를 등록하는 데 사용할 수 있는 Intune 계정입니다.
  > [!div class="button"]   [장치 등록 관리자 >](../deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

  - **iOS 장치** - 공유 iOS 장치는 세 가지 방법으로 관리할 수 있습니다.  **어떻게 공유 iOS 장치를 등록할 것인가요?**

    - **Apple의 DEP(장치 등록 프로그램)** - DEP로 구입되고 관리되는 iOS 장치는 등록 프로필을 사용하여 대상으로 지정될 수 있습니다. 사용자가 처음으로 장치를 켤 때 장치는 DEP 프로필을 다운로드하고 프로필 DEP를 사용하여 등록됩니다.
    > [!div class="button"]     [DEP 등록 >](../deploy-use/ios-device-enrollment-program-in-microsoft-intune)

    - **Mac의 Apple Configurator** - Apple Configurator는 Mac PC에서 실행되는 Apple 응용 프로그램입니다. USB 케이블로 iOS 장치를 Mac에 연결하여 장치에 등록 프로필을 설치할 수 있습니다. 장치를 공장 기본 설정으로 복원하여 등록할 수 있는 경우 설정 도우미 등록을 사용합니다. 장치를 공장 기본 설정으로 복원하지 않으려는 경우에는 직접 등록을 사용합니다.

    > [!div class="button"]     [설정 도우미 등록 >](../deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) 또는 [직접 등록 >](../deploy-use/ios-direct-enrollment-in-microsoft-intune)

    - **위에 해당하지 않는 경우** - Apple의 DEP 또는 Apple Configurator 등록 방법을 사용할 수 없거나 사용하지 않으려는 경우 Intune의 장치 등록 관리자를 사용합니다.
    > [!div class="button"]     [DEM 등록 >](../deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).

**개별 사용자** - 개별 사용자에게 발급되는 회사 소유 장치는 사용자가 개인 장치로 메일과 데이터에 액세스할 수 있도록 허용하는 동안 회사 자산으로 추적되어야 합니다. 권장되는 등록 방법은 장치의 플랫폼에 따라 달라집니다.

  - **Windows 및 Android 장치** - 회사 소유 장치의 IMEI(International Mobile Equipment Identity) 번호를 가져와서 Intune에서 회사 소유 장치로 장치에 태그를 지정할 수 있습니다. 이렇게 하면 사용자가 메일, 앱, 데이터 등의 회사 리소스에 액세스하기 위해 회사 포털을 설치하여 장치를 개인 장치로 등록할 수 있습니다.
  > [!div class="button"]   [IMEI로 태그 지정 >](../deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

  - **iOS 장치** - 공유 iOS 장치는 세 가지 방법으로 관리할 수 있습니다.  **어떻게 공유 iOS 장치를 등록할 것인가요?**

    - **Apple의 DEP(장치 등록 프로그램)** - DEP로 구입되고 관리되는 iOS 장치는 등록 프로필을 사용하여 대상으로 지정될 수 있습니다. 사용자가 처음으로 장치를 켤 때 장치가 DEP 프로필을 다운로드하고 프로필에 따라 등록됩니다.
    > [!div class="button"]     [DEP 등록](../deploy-use/ios-device-enrollment-program-in-microsoft-intune).

    - **Mac의 Apple Configurator** - Apple Configurator는 Mac PC에서 실행되는 Apple 응용 프로그램입니다. USB 케이블로 iOS 장치를 Mac에 연결하여 장치에 등록 프로필을 설치할 수 있습니다. 장치를 공장 기본 설정으로 복원하여 등록할 수 있는 경우 설정 도우미 등록을 사용합니다.

    장치를 공장 기본 설정으로 복원하지 않으려는 경우에는 직접 등록을 사용합니다.
    장치를 공장 기본 설정으로 복원하여 등록할 수 있는 경우 설정 도우미 등록을 사용합니다.
    > [!div class="button"][iOS 설정 도우미 등록](../deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [!div class="button"][iOS 직접 등록](../deploy-use/ios-direct-enrollment-in-microsoft-intune).

    - **위에 해당하지 않는 경우** - Apple의 DEP 또는 Apple Configurator 등록 방법을 사용할 수 없거나 사용하지 않으려는 경우 회사 소유 장치의 IMEI(International Mobile Equipment Identity) 번호를 가져와서 Intune에서 회사 소유 장치로 장치에 태그를 지정할 수 있습니다. 이렇게 하면 사용자가 메일, 앱, 데이터 등의 회사 리소스에 액세스하기 위해 회사 포털을 설치하여 장치를 개인 장치로 등록할 수 있습니다. > [!div class="button"][IMEI 번호로 장치에 태그 지정](../deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)


<!--HONumber=Jun16_HO1-->


