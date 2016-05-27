---
# required metadata

title: Microsoft Intune에 장치를 등록하도록 준비 | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 44fd4af0-f9b0-493a-b590-7825139d9d40

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune에 장치를 등록하도록 준비
Intune으로 직원이 모바일 장치(Android, iOS 및 Windows Phone 및 Windows PC 포함)를 등록할 수 있도록 하려면 장치 등록을 활성화해야 합니다. 등록을 허용하려면 모바일 장치 관리 기관을 설정하고 Intune 회사 포털을 구성하고 라이선스를 할당하고 장치 플랫폼에 대한 등록을 활성화해야 합니다.

## <a name="BKMK_Set_MDM_Authority"></a>모바일 장치 관리 기관 설정
MDM 기관은 일련의 장치를 관리할 권한을 가진 관리 서비스를 정의합니다. MDM 기관에 대한 옵션에는 Intune 자체 및 Intune을 사용하는 Configuration Manager가 포함됩니다. Configuration Manager를 관리 기관으로 설정한 경우 모바일 장치 관리에 다른 서비스를 사용할 수 없습니다.

>[!IMPORTANT]
> Intune만 사용(온라인 서비스)하여 모바일 장치를 관리할지, 아니면 Intune으로 System Center Configuration Manager(온-프레미스 소프트웨어 솔루션 및 온라인 서비스 결합)를 사용하여 모바일 장치를 관리할지를 신중히 고려해야 합니다. 이런 항목을 설정한 후에는 모바일 장치 관리 기관을 변경할 수 없습니다.



1.  [Microsoft Intune 관리 콘솔](http://manage.microsoft.com)에서 **관리** &gt; **모바일 장치 관리**를 클릭합니다..

2.  **작업** 목록에서 **모바일 장치 관리 기관 설정**을 클릭합니다. **MDM 기관 설정** 대화 상자가 열립니다.

    ![MDM 기관 설정 대화 상자](../media/intune-mdm-authority.png)

3.  Intune을 MDM 기관으로 지정할 것임을 확인하라는 요청 메시지가 표시됩니다. 이 확인란을 선택한 후 **예** 를 클릭하여 모바일 장치를 관리하는 데 Microsoft Intune을 사용합니다.

## Intune 회사 포털 구성 및 라이선스 할당
Intune 회사 포털을 사용하여 사용자는 앱과 같은 회사 리소스에 액세스하고 기술 지원팀 정보를 찾고 장치를 등록 및 등록 해제할 수 있습니다. 장치를 등록하기 전에 [회사 포털을 구성](/intune/get-started/get-started-with-a-paid-subscription-to-microsoft-intune-step-7)해야 합니다. 또한 Intune에 대한 액세스를 허용하려면 [사용자 라이선스를 할당](/intune/get-started/get-started-with-a-paid-subscription-to-microsoft-intune-step-4)해야 합니다.

## 모바일 장치 설정
MDM 기관을 설정한 후 조직에서 지원하려는 운영 체제에 대한 장치 관리를 설정해야 합니다. 장치 관리를 설정하는 데 필요한 단계는 운영 체제에 따라 다릅니다. 예를 들어 Android OS는 Intune 관리 콘솔에서 아무런 작업이 필요하지 않습니다. 반면에 Windows 및 iOS는 관리를 허용하려면 장치와 Intune 간의 트러스트 관계가 필요합니다.

> [!div class="op_single_selector"]
- [Microsoft Intune을 사용한 Android 관리 설정](set-up-android-management-with-microsoft-intune.md)
- [Microsoft Intune을 사용한 iOS 및 Mac 관리 설정](set-up-ios-and-mac-management-with-microsoft-intune.md)
- [Microsoft Intune을 사용한 Windows Phone 관리 설정](set-up-windows-phone-management-with-microsoft-intune.md)
- [Microsoft Intune을 사용한 Windows 장치 관리 설정](set-up-windows-device-management-with-microsoft-intune.md)

또한 다음을 수행할 수 있습니다.
 - [장치 등록 관리자 계정](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)을 사용하여 여러 장치 등록
 - 장치 및 대상 정책 등록을 돕도록 [IMEI 번호를 사용하여 회사 소유 장치 지정](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md)


<!--HONumber=May16_HO1-->


