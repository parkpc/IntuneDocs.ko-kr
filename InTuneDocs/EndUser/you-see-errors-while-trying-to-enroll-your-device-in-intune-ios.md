---
title: "Intune에서 iOS 장치를 등록하는 동안 오류가 발생하는 경우 | Microsoft Intune"
description: 
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 08/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 92a8d06d-0ecb-4912-898b-993e8eaf4e58
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: esmich
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 38301b4e6964550008b08e99bf7016f1cc2561c3
ms.openlocfilehash: e2493f93c08aaf7c10c47a0835de498349799e28


---


# Intune에서 iOS 장치를 등록하는 동안 오류가 발생하는 경우

다음 표에서는 Intune에 iOS 장치를 등록하는 동안 표시될 수 있는 오류를 보여 줍니다. 이 링크를 IT 관리자와 공유하세요. IT 관리자의 연락처 정보는 [회사 포털 웹 사이트](http://portal.manage.microsoft.com)를 참조하세요.

|오류 메시지|문제|IT 관리자에게 알릴 내용|
|-----------------|---------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
|NoEnrollmentPolicy|등록 정책 없음|모든 등록 필수 구성 요소(예: APNs 인증서)가 구성되어 있는지와 "iOS가 플랫폼으로" 사용되도록 설정되어 있는지 확인합니다. 자세한 내용은 [iOS 및 Mac 장치 관리 설정](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune)을 참조하세요.|
|DeviceCapReached|너무 많은 모바일 장치가 이미 등록되어 있습니다.|사용자는 다른 모바일 장치를 등록하기 전에 현재 등록된 모바일 장치 중 하나를 회사 포털에서 제거해야 합니다. [Android](unenroll-your-device-from-intune-android.md), [iOS](unenroll-your-device-from-intune-ios.md), [Windows](unenroll-your-device-from-intune-windows.md) 중에서 사용 중인 장치 유형에 대한 지침을 참조하세요.|
|APNSCertificateNotValid|모바일 장치와 회사 네트워크 간 통신을 허용하는 인증서에 문제가 있습니다.<br /><br />IT 관리자에게 연락하여 모바일 장치를 등록하는 동안 **APNSCertificateNotValid** 메시지가 수신되었으며 이 표에 있는 해결 방법을 확인하도록 알립니다.|APNS(Apple Push Notification Service) 에서 등록 된 iOS 장치에 게 도달 하는 채널을 제공 합니다. APNS 인증서를 가져오는 단계를 수행하지 않았거나 APNS 인증서가 만료된 경우에는 등록 시도가 실패하고 이 메시지가 나타납니다.<br /><br />[Active Directory를 동기화하고 Intune에 사용자 추가](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-3) 및 [사용자 및 장치 구성](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-5)에서 사용자 설정에 대한 정보를 검토하세요.|
|AccountNotOnboarded|모바일 장치와 회사 네트워크 간 통신을 허용하는 인증서에 문제가 있습니다.<br /><br />IT 관리자에게 연락하여 모바일 장치를 등록하는 동안 **APNSNotOnboarded** 메시지가 수신되었으며 이 표에 있는 해결 방법을 확인하도록 알립니다.|APNS(Apple Push Notification Service) 에서 등록 된 iOS 장치에 게 도달 하는 채널을 제공 합니다. APNS 인증서를 가져오는 단계를 수행하지 않았거나 APNS 인증서가 만료된 경우에는 등록 시도가 실패하고 이 메시지가 나타납니다.<br /><br />자세한 내용은 [Microsoft Intune을 사용한 iOS 및 Mac 관리 설정](/Intune/Deploy-use/set-up-ios-and-mac-management-with-microsoft-intune)을 검토하세요.|
|DeviceTypeNotSupported|비 iOS 장치를 사용하여 등록하려고 했을 수 있습니다. 등록하려는 모바일 장치 유형이 지원되지 않습니다.<br /><br />장치가 iOS 버전 7.1 이상을 실행 중인지 확인합니다.<br /><br />IT 관리자에게 연락하여 모바일 장치를 등록하는 동안 **DeviceTypeNotSupported** 메시지가 수신되었으며 이 표에 있는 해결 방법을 확인하도록 알립니다.|사용자 장치가 iOS 버전 7.1 이상을 실행 중인지 확인합니다.|
|UserLicenseTypeInvalid|사용자 계정이 아직 필수 사용자 그룹의 구성원이 아니어서 모바일 장치를 등록할 수 없습니다.<br /><br />IT 관리자에게 연락하여 모바일 장치를 등록하는 동안 **UserLicenseTypeInvalid** 메시지가 수신되었으며 이 표에 있는 해결 방법을 확인하도록 알립니다.|사용자가 장치를 등록하려면 올바른 사용자 그룹의 구성원이어야 합니다. 이 메시지는 지정된 모바일 장치 관리 기관에 맞지 않는 라이선스 유형이 있음을 의미합니다. 예를 들어 Intune이 모바일 장치 관리 기관으로 지정되었는데 System Center 2012 R2 Configuration Manager 라이선스를 사용하는 경우 이 오류가 표시됩니다.<br /><br />자세한 내용은 다음을 검토하세요.<br /><br />[Microsoft Intune을 사용한 iOS 및 Mac 관리 설정](/Intune/Deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) 및 [Active Directory를 동기화하고 Intune에 사용자 추가](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-3) 및 [사용자 및 장치 구성](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-5)에서 사용자 설정에 대한 정보를 검토하세요.|
|MdmAuthorityNotDefined|IT 관리자가 회사의 모바일 장치 관리 방법을 구성해야 합니다.<br /><br />IT 관리자에게 연락하여 모바일 장치를 등록하는 동안 **MdmAuthorityNotDefined** 메시지가 수신되었으며 이 표에 있는 해결 방법을 확인하도록 알립니다.|Intune에서 모바일 장치 관리 기관이 지정되지 않았습니다.<br /><br />[Microsoft Intune 30일 평가판으로 시작하기](/Intune/Understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune)에서 "6단계: 모바일 장치 등록 및 앱 설치" 섹션의 항목 #1을 검토합니다.|





<!--HONumber=Aug16_HO5-->


