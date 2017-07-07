---
title: Set up iOS and Mac management
description: "Microsoft Intune으로 Mac OS X 장치뿐만 아니라 iPad 및 iPhone을 포함하는 iOS 장치의 MDM(모바일 장치 관리)도 수행합니다."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dc451224-1372-4b84-b641-cfa67cb3849b
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: af300534b3868a829c0b648d4df2587886ef749b
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2017
---
# <a name="set-up-ios-and-mac-device-management"></a>iOS 및 Mac 관리 설정

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune은 iPad, iPhone 및 macOS 장치의 MDM(모바일 장치 관리)을 가능하게 하고, 사용자가 회사 메일 및 앱에 액세스할 수 있게 해줍니다. APN(Apple 푸시 알림) 서비스 인증서는 Intune에서 iOS 및 Mac 장치를 관리하는 데 필요합니다. 인증서가 Intune에 추가되면 사용자가 회사 포털 앱을 설치하여 장치를 등록할 수도 있고 관리자가 [회사 소유의 iOS 장치 관리](enroll-corporate-owned-ios-devices-in-microsoft-intune.md)를 설정할 수도 있습니다.

1.  **Intune 설정**<br>
    모바일 장치 관리를 아직 준비하지 않은 경우 [모바일 장치 관리 기관](prerequisites-for-enrollment.md#step-2-set-mdm-authority)을 **Microsoft Intune**으로 설정하고 MDM을 설정하여 관리를 준비합니다.

2.  **인증서 서명 요청 가져오기**<br>
    관리자 권한으로 [Microsoft Intune 관리 콘솔](https://manage.microsoft.com)을 열고 **관리** &gt; **모바일 장치 관리** &gt; **iOS 및 Mac OS X** &gt; **APNs 인증서 업로드**로 이동하여 **APNs 인증서 요청 다운로드**를 선택합니다. 인증서 서명 요청(.csr) 파일을 로컬로 저장합니다. .csr 파일은 APC(Apple Push Certificate) 포털에서 트러스터 관계 인증서를 요청하는 데 사용됩니다.

    ![APNs 인증서 업로드 대화 상자](../media/Intune-iOS-enrollment-with-apns.png)

3.  **Apple Push Notification Service 인증서 가져오기**<br>
    [Apple Push Certificates 포털](http://go.microsoft.com/fwlink/?LinkId=269844)로 이동한 다음 회사 Apple ID로 로그인하여 .csr 파일을 사용해서 APNs 인증서를 만듭니다. Apple의 푸시 인증서 포털에서 **업로드**를 선택하면 APNs에 사용할 수 없는 .json 파일을 수신하게 됩니다. 다운로드를 완료하고 **타사 서버용 인증서**를 위한 Apple 푸시 인증서 포털로 돌아가 **다운로드**를 선택합니다.

    APNs(.pem) 인증서를 다운로드하고 파일을 로컬로 저장합니다.

    > [!NOTE]
    > 매년 이 APN 인증서를 갱신(교체 아님)해야 합니다. 이 동일한 Apple ID를 사용하여 Apple의 Push Certificate Portal에 로그인한 다음 이 항목의 동일한 지침을 사용하여 인증서를 다운로드하여 Intune에 업로드합니다.

4.  **Intune에 APNs 인증서 추가**<br>
    [Microsoft Intune 관리 콘솔](https://manage.microsoft.com)에서 **관리** &gt; **모바일 장치 관리** &gt; **iOS 및 Mac OS X** &gt; **APNs 인증서 업로드**로 이동하여 **APNs 인증서 업로드**를 선택합니다. 인증서(.pem) 파일로 이동한 후 **열기**를 선택하고 **Apple ID**를 입력합니다. APNs 인증서가 있으면 Intune에서 등록된 모바일 장치에 정책을 푸시하여 iOS 장치를 등록하고 관리할 수 있습니다.

5.  **회사 리소스를 이용할 수 있도록 사용자에게 장치를 등록하는 방법 설명**

    최종 사용자 등록 지침은 [Intune에서 iOS 장치 등록](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) 및 [Intune에서 macOS 장치 등록](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos)을 참조하세요. 예상되는 작업 내용과 IT 관리자가 장치에서 볼 수 있는 항목과 볼 수 없는 항목을 등록 과정 중에 알려줍니다.

    최종 사용자의 다른 작업에 대한 정보는 다음 문서를 참조하세요.
    - [Microsoft Intune에서 최종 사용자 환경 관련 리소스](/intune/end-user-educate)
    - [iOS 및 Mac 장치용 최종 사용자 가이드](https://docs.microsoft.com/intune-user-help/using-your-ios-or-macOS-device-with-intune)

회사 또는 조직에서 사용자를 위한 iOS 장치를 구입한 경우 해당 장치도 관리를 위해 [회사 소유의 iOS 장치](enroll-corporate-owned-ios-devices-in-microsoft-intune.md)로 등록할 수 있습니다.

### <a name="see-also"></a>참고 항목
[Microsoft Intune 등록을 위한 필수 구성 요소](prerequisites-for-enrollment.md)
