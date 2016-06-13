---
# required metadata

title: iOS 및 Mac 관리 설정 | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: dc451224-1372-4b84-b641-cfa67cb3849b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# iOS 및 Mac 관리 설정
Microsoft Intune에서는 iPhone, iPad 및 Mac 사용자가 회사 메일 및 앱에 액세스할 수 있도록 BYOD("Bring Your Own Device") iOS 및 Mac OS X 장치 등록을 사용하도록 설정할 수 있습니다. 사용하도록 설정한 후에는 사용자가 Intune 회사 포털 앱을 설치할 수 있으며 Intune 관리 콘솔을 사용하여 정책을 통해 대상 장치를 지정할 수 있습니다.

Intune을 사용하여 iOS 장치를 관리할 수 있으려면 장치가 Intune과 통신할 수 있어야 합니다. Apple에서는 APNS(Apple 푸시 알림 서비스) 인증서를 가져와 설정된 Intune과 트러스트 관계를 요구합니다.

1.  **Intune 설정**<br>
    모바일 장치 관리를 아직 준비하지 않은 경우 [모바일 장치 관리 기관](get-ready-to-enroll-devices-in-microsoft-intune.md#set-mobile-device-management-authority)을 **Microsoft Intune**으로 설정하고 MDM을 설정하여 관리를 준비합니다.

2.  **인증서 서명 요청 가져오기**<br>
    관리자 권한으로 [Microsoft Intune 관리 콘솔](http://manage.microsoft.com)을 열고 **관리** &gt; **모바일 장치 관리** &gt; **iOS 및 Mac OS X** &gt; **APNs 인증서 업로드**로 이동하여 **APNs 인증서 요청 다운로드**를 클릭합니다. 인증서 서명 요청(.csr) 파일을 로컬로 저장합니다. .csr 파일은 APC(Apple Push Certificate) 포털에서 트러스터 관계 인증서를 요청하는 데 사용됩니다.

    ![APNs 인증서 업로드 대화 상자](../media/Intune-iOS-enrollment-with-apns.png)

3.  **Apple Push Notification Service 인증서 가져오기**<br>
    [Apple Push Certificates 포털](http://go.microsoft.com/fwlink/?LinkId=269844)로 이동한 다음 회사 Apple ID로 로그인하여 .csr 파일을 사용해서 APNs 인증서를 만듭니다. Apple의 푸시 인증서 포털에서 **업로드**를 클릭하면 APNs에 사용할 수 없는 .json 파일을 수신하게 됩니다. 다운로드를 완료하고 **타사 서버용 인증서**를 위한 Apple 푸시 인증서 포털로 돌아가 **다운로드**를 클릭합니다.

    APNs(.pem) 인증서를 다운로드하고 파일을 로컬로 저장합니다. 나중에 APNs 인증서를 갱신하기 위해 이 Apple ID를 사용해야 합니다.

4.  **Intune에 APNs 인증서 추가**<br>
    [Microsoft Intune 관리 콘솔](http://manage.microsoft.com)에서 **관리** &gt; **모바일 장치 관리** &gt; **iOS 및 Mac OS X** &gt; **APNs 인증서 업로드**로 이동하여 **APNs 인증서 업로드**를 클릭합니다. 인증서(.pem) 파일을**찾아**  **열기** 를 클릭한 다음 **Apple ID**를 입력합니다. APNs 인증서가 있으면 Intune에서 등록된 모바일 장치에 정책을 푸시하여 iOS 장치를 등록하고 관리할 수 있습니다.

5.  **사용자에게 회사 포털을 사용하여 회사 리소스에 액세스하는 방법 알려주기**<br>
    사용자는 장치를 등록하는 방법과 장치가 관리될 때 발생하는 상황에 대해 알고 있어야 합니다. [Microsoft Intune 사용 방법에 대해 최종 사용자에게 알릴 내용](what-to-tell-your-end-users-about-using-microsoft-intune.md)

회사 또는 조직에서 사용자를 위한 iOS 장치를 구입한 경우 해당 장치도 관리를 위해 [회사 소유의 iOS 장치](enroll-corporate-owned-ios-devices-in-microsoft-intune.md)로 등록할 수 있습니다.

### 참고 항목
[Microsoft Intune에 장치를 등록하도록 준비](get-ready-to-enroll-devices-in-microsoft-intune.md)


<!--HONumber=May16_HO4-->


