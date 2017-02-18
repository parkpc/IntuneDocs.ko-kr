---
title: "Microsoft의 모바일 장치 관리 평가 | Microsoft Docs"
description: "Intune 무료 평가판에서 MDM을 평가합니다."
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 11/29/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47806f69-303d-41d9-9b0e-9b9445ea24ac
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 4133c64d283682f0be37cd6ac69164ef872a5026


---

# <a name="evaluate-mobile-device-management-in-microsoft-intune"></a>Microsoft의 모바일 장치 관리 평가

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

이 평가 가이드에서는 Intune에서 모바일 장치 관리가 작동하는 방식을 보여 줍니다. 다음을 수행합니다.
- Intune에서 관리할 장치를 등록합니다.
- 사용자 및 장치를 구성할 그룹을 만듭니다.
- 몇 가지 장치 관리 정책을 만들어 그룹에 배포합니다.
- 등록된 장치의 사용자가 자신의 장치에 설치할 수 있도록 앱을 게시합니다.
<!--- - Monitor the device? View a report of compliant devices?--->
<!--- - Remove the device from management--->

## <a name="assumptions"></a>가정
이 가이드에서는 평가 목적으로만 평가판을 사용하며, 구독할 때 새 환경에서 시작하는 것으로 가정합니다.

평가판을 쉽게 시작할 수 있도록 Intune만 사용하는 매우 간단한 환경을 설정하며, 이 환경이 모바일 장치 관리 기관인 것으로 가정합니다. 그러나 보다 자세한 내용을 살펴볼 수 있도록 가이드 전체에서 심층적인 기술 콘텐츠를 안내합니다.

평가판에서는 구독 버전에서 수행할 수 있는 모든 작업을 수행할 수 있습니다. 다만, 평가판에서는 사용자 계정이 100개로 제한됩니다.

## <a name="whats-not-covered"></a>다루지 않는 내용
|관심 있는 항목 |참조 문서 |
|------------------------|----------|
|테스트 환경이 아닌 환경에서의 MDM | [시작](https://docs.microsoft.com/en-us/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune) |
|Intune 및 System Center Configuration Manager를 사용한 MDM | [하이브리드 모바일 장치 관리](https://docs.microsoft.com/en-us/sccm/mdm/understand/hybrid-mobile-device-management) |

위 가이드는 프로덕션 환경에서 Intune을 설정하도록 도와주기 때문에 내용이 더 길고 평가 가이드보다 검토해야 하는 결정 사항이 더 많습니다.

Intune을 신속하게 익히려면 평가 가이드로 시작한 후 다른 가이드를 진행하는 것이 좋습니다.

## <a name="prerequisites-for-this-evaluation"></a>이 평가를 위한 필수 구성 요소
- Internet Explorer 10 이상
- Intune 사용자가 회사 포털을 사용하여 자신의 장치를 등록 및 관리하는 방법을 테스트하는 데 사용할 장치. 이 가이드에서는 iPad 및 Android 휴대폰을 사용합니다.
- IPad 또는 다른 iOS 장치를 관리하려면 [Apple 푸시 알림 서비스 인증서](https://docs.microsoft.com/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune)가 필요합니다.
- [Intune 평가판 구독](sign-up-for-30-day-trial-microsoft-intune.md)

## <a name="set-your-mdm-authority"></a>MDM 기관 설정
Intune으로 모바일 장치를 관리하기 위해 수행해야 하는 첫 번째 단계는 **MDM(모바일 장치 관리) 기관**을 설정하는 것입니다.

이 평가판에서 가정한 대로 독립 실행형 Intune을 사용하거나, Intune을 EMS(Enterprise Mobility + Security)의 일부로 사용하는 경우 Intune을 모바일 장치 관리 기관으로 설정해야 합니다. 즉, 조직에서 모바일 장치를 관리하는 데 사용하는 서비스로 Intune을 지정합니다.

System Center Configuration Manager와 함께 Intune을 사용하여 모바일 장치를 관리하려는 고객은 모바일 장치 관리 기관으로 Intune을 사용할지 또는 Configuration Manager를 사용할지 결정해야 합니다. 현재 한 번 설정한 후에는 변경하기가 매우 어렵기 때문에 이는 중요한 결정이지만 이 평가 가이드의 범위를 벗어납니다. Intune 또는 Configuration Manager를 MDM 기관으로 설정할 경우의 의미에 대한 자세한 내용은 [독립 실행형 Intune과 하이브리드 모바일 장치 관리 간의 선택](https://docs.microsoft.com/en-us/sccm/mdm/understand/choose-between-standalone-intune-and-hybrid-mobile-device-management)을 참조하세요.

평가판에서는 Intune을 MDM 기관으로 설정합니다. 이는 프로덕션 환경에 평가판을 사용하지 않는 한 프로덕션 환경에 영향을 주지 않습니다.

1. [Intune 관리 콘솔](https://manage.microsoft.com/)에서 **관리** &gt; **모바일 장치 관리**를 선택합니다.
2. **작업** 목록에서 **MDM 기관 설정**을 선택합니다. **MDM 기관 설정** 대화 상자가 열립니다. <!---screen shot--->
3. Intune을 MDM 기관으로 지정할 것임을 확인하라는 요청 메시지가 표시됩니다. 이 확인란을 선택한 후 **예**를 선택하여 모바일 장치를 관리하는 데 Intune을 사용합니다.

## <a name="enroll-your-test-devices-into-intune"></a>Intune 테스트 장치 등록

이 가이드에서는 Android 휴대폰 및 Apple iPad를 등록하지만 이 섹션의 끝에 [Intune에서 장치를 등록하는 방법에 대한 자세한 정보](#Learn-more-about-device-enrollment)를 제공하는 링크가 나와 있습니다.
### <a name="android"></a>Android
[Google Play](http://go.microsoft.com/fwlink/p/?LinkId=386612)에서 사용할 수 있는 Microsoft Corporation의 **Intune 회사 포털** 앱을 설치하고 무료 평가판에 등록할 때 [만든 Intune 사용자 자격 증명](sign-up-for-30-day-trial-microsoft-intune.md#add-users)으로 로그인합니다.

### <a name="ios"></a>iOS
사용자가 iOS 장치를 등록하려면 먼저 이러한 장치를 관리하도록 Intune을 설정해야 합니다.

1. **인증서 서명 요청 가져오기**<br/>
관리자 계정으로 Intune에 로그온한 후 **관리** > **모바일 장치 관리** > **iOS 및 Mac OS X** > **APNs 인증서 업로드**로 이동하여 **APNs 인증서 요청 다운로드**를 클릭합니다. 인증서 서명 요청(.csr) 파일을 로컬로 저장합니다. .csr 파일은 APC(Apple Push Certificate) 포털에서 트러스터 관계 인증서를 요청하는 데 사용됩니다. <!--- screen shot--->
2.    **Apple Push Notification Service 인증서 가져오기**<BR/>
[Apple Push Certificates 포털](https://idmsa.apple.com/IDMSWebAuth/login?appIdKey=3fbfc9ad8dfedeb78be1d37f6458e72adc3160d1ad5b323a9e5c5eb2f8e7e3e2&rv=2)로 이동한 다음 회사 Apple ID로 로그인하여 .csr 파일을 사용해서 APNs 인증서를 만듭니다. **Apple Push Certificate Portal에서 업로드**를 선택하면 APNs에 사용할 수 없는 .json 파일을 수신하게 됩니다. 다운로드를 완료하고 타사 서버용 인증서를 위한 Apple Push Certificates Portal로 돌아가 **다운로드**를 선택합니다.

 APNs(.pem) 인증서를 다운로드하고 파일을 로컬로 저장합니다. 나중에 APNs 인증서를 갱신하기 위해 이 Apple ID를 사용해야 합니다.
3.    **Intune에 APNs 인증서 추가**<BR/>
Microsoft Intune 관리 콘솔에서 **관리** > **모바일 장치 관리** > **iOS 및 Mac OS X** > **APNs 인증서 업로드**로 이동하여 **APNs 인증서 업로드**를 선택합니다. 인증서(.pem) 파일로 이동한 후 **열기**를 선택하고 Apple ID를 입력합니다. APNs 인증서가 있으면 Intune에서 등록된 모바일 장치에 정책을 푸시하여 iOS 장치를 등록하고 관리할 수 있습니다.
4.    **회사 리소스를 이용할 수 있도록 사용자에게 장치를 등록하는 방법 설명**<br/>
최종 사용자 등록 지침은 [Intune에서 iOS 장치 등록](https://docs.microsoft.com/en-us/Intune/enduser/enroll-your-device-in-intune-ios) 및 [Intune에서 Mac OS X 장치 등록](https://docs.microsoft.com/en-us/Intune/enduser/enroll-your-device-in-intune-mac-os-x)을 참조하세요. 예상되는 작업 내용과 IT 관리자가 장치에서 볼 수 있는 항목과 볼 수 없는 항목을 등록 과정 중에 알려줍니다.


### <a name="learn-more-about-device-enrollment"></a>장치 등록에 대한 자세한 정보

Intune은 다음 장치 플랫폼을 지원합니다.

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

장치 관리를 사용하기 위한 요구 사항은 관리하려는 플랫폼에 따라 다릅니다.
- **Android** 모바일 장치에서는 사용자가 Google Play에서 제공되는 [회사 포털 앱을 사용하여 등록](/intune/deploy-use/set-up-android-management-with-microsoft-intune)할 수 있습니다. Intune에서는 추가 구성을 수행할 필요가 없습니다.
- [**iOS 및 Mac OS X**에 대한 설치 요구 사항](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune)
- [**Windows Phone**에 대한 설치 요구 사항](/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune)

<!--- ## Verify enrollment--->
<!--- START HERE

### iOS and Mac OS X
Install the **Microsoft Intune Company Portal** app from Microsoft Corporation available in the App Store and sign in with Intune user credentials added above. View **Enrolled devices** to add your device.



### Windows Phone 8.1
Users install the **Company Portal** app from Microsoft Corporation, available in the Windows Phone store, and sign in with the Intune user credentials added above.  View **Enrolled devices** to add your device.

## Install the previously deployed app
Open the Company Portal on the mobile device, choose **Apps**, and then install **Microsoft Skype**.--->



## <a name="next-steps"></a>다음 단계
[사용자 및 장치를 구성하기 위한 그룹 만들기](get-started-with-a-30-day-trial-of-microsoft-intune-step-3.md)



<!--HONumber=Jan17_HO1-->


