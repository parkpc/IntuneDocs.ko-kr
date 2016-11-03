---
title:
- "모바일 응용 프로그램 관리 문제 해결 | Microsoft Intune"
description: 
keywords: 
author: karaman
manager: angerobe
ms.date: 09/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd5a0a3b-0013-4be3-a233-ce6e9083149f
translationtype: Human Translation
ms.sourcegitcommit: 9cfb3694b2fae919fd0554a6e21b497cdcf19c72
ms.openlocfilehash: f33e8de82ee07bb4571a5bfaff63af72f9086376


---

# 모바일 응용 프로그램 관리 문제 해결

모바일 응용 프로그램 관리에 문제가 있으면 여기서 시작합니다. 이 항목에는 솔루션에서 함께 발생할 수 있는 몇 가지 일반적인 문제가 포함되어 있습니다.


**문제:** Azure 콘솔의 등록 정책이 없는 MAM은 iOS/Android 장치의 비즈니스용 Skype 앱에 적용되지 않습니다.

해결 방법: 최신 인증을 사용하도록 비즈니스용 Skype를 설정해야 합니다.  [Enable your tenant for modern authentication](http://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)(최신 인증을 사용하도록 테넌트 설정)의 지침을 따라 Skype에 최신 인증을 설정합니다.

**문제:** 등록 정책 없이 설정한 MAM이 사용자에 관계없이, 지원되는 모든 Office 앱 [https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners]에 적용되지 않습니다.
 
해결 방법: 사용자에게 Intune 라이선스가 있는지 확인합니다.  

**문제:** IT 관리자가 Azure Portal에서 MAM 정책을 구성할 수 없습니다.

해결 방법: Azure Portal에 액세스할 수 있는 역할은 다음과 같습니다.

- 전역 관리자 - [Office 포털](http://portal.office.com/)에서 설정할 수 있음
- 소유자 - [Azure Portal](https://portal.azure.com/)에서 설정할 수 있음
- 참가자 - [Azure Portal](https://portal.azure.com/)에서 설정할 수 있음

이러한 역할 설정에 대한 도움말은 [Microsoft Intune을 사용하여 모바일 앱 관리 정책 구성 준비](https://docs.microsoft.com/en-us/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune)를 참조하세요. 

**문제:** MAM 정책 적용을 받도록 최근에 지정한 사용자가 앱 보고서에 표시되지 않습니다.

해결 방법: 사용자가 MAM 정책 대상으로 새로 지정된 경우 대상 사용자로 보고서에 표시되는 데 최대 24시간이 걸릴 수 있습니다. 

**문제:** 정책 변경/업데이트를 적용하는 데 최대 8시간이 걸릴 수 있습니다.  

해결 방법: 서비스와 강제로 동기화하도록 최종 사용자가 앱에서 로그아웃했다가 다시 로그인하면 됩니다.  

**문제:** MAM 정책이 Apple DEP 장치에 적용되지 않습니다.

해결 방법: Apple DEP(장치 등록 프로그램)에서 사용자 선호도를 사용 중인지 확인하세요. 사용자 선호도는 DEP에 따라 사용자 인증이 필요한 모든 앱에 필수입니다.
자세한 내용은 [Enroll corporate-owned Device Enrollment Program iOS devices](https://docs.microsoft.com/en-us/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune)(회사 소유의 iOS 장치를 장치 등록 프로그램에 등록)를 참조하세요.


### 참고 항목
- [모바일 응용 프로그램 관리 설정 유효성 검사](https://docs.microsoft.com/en-us/intune/deploy-use/validate-mobile-application-management)
- [Microsoft Intune을 사용하여 모바일 앱 관리 정책 구성 준비](https://docs.microsoft.com/en-us/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune) 





<!--HONumber=Sep16_HO2-->


