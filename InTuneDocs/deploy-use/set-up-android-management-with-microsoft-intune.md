---
title: "Android 관리 설정 | Microsoft 문서"
description: "Microsoft Intune으로 Android 및 KNOX Standard 장치에 대한 MDM(모바일 장치 관리)을 사용하도록 설정합니다."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 01/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dbe5cad1-3e0d-41a9-966b-738156089700
ms.reviewer: lacranda
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 6b99854e17e00a0dd0f91fa82fd1b79d1dfe5663
ms.openlocfilehash: 8e2588e2bb0537877f0164bc996fa973f25ea4dd


---

# <a name="set-up-android-device-management"></a>Android 장치 관리 설정

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune 관리자는 회사 포털에서 Samsung Knox Standard 장치를 포함한 Android 장치를 관리하도록 설정할 수 있습니다. 그러면 사용자가 Google Play에서 제공되는 회사 포털 앱을 사용하여 장치를 등록할 수 있습니다.

기본적으로 Android 장치는 Intune에 등록할 수 있습니다. Android 장치 등록을 차단하려면 관리자 자격 증명으로 [Microsoft Intune 관리 포털](http://manage.microsoft.com)에 로그인합니다. **관리** > **모바일 장치 관리** > **등록 규칙**을 선택한 다음 **Android 장치 허용** 확인란을 선택 취소합니다.

1.  **Intune 설정**<br>
    모바일 장치 관리를 아직 준비하지 않은 경우 [모바일 장치 관리 기관](prerequisites-for-enrollment.md#step-2-set-mdm-authority)을 **Microsoft Intune**으로 설정하고 MDM을 설정하여 관리를 준비합니다.

2.  **Android 등록 사용**<br>
    Intune 콘솔에서 추가적으로 구성할 필요 없이 Android 모바일 장치 등록을 설정할 수 있습니다.

3.  **회사 리소스를 이용할 수 있도록 사용자에게 장치를 등록하는 방법 설명**

    최종 사용자 등록 지침은 [Intune에서 Android 장치 등록](../enduser/enroll-your-device-in-intune-android.md)을 참조하세요. 예상되는 작업 내용과 IT 관리자가 장치에서 볼 수 있는 항목과 볼 수 없는 항목을 등록 과정 중에 알려줍니다.

    최종 사용자의 다른 작업에 대한 정보는 다음 문서를 참조하세요.
  - [Microsoft Intune에서 최종 사용자 환경 관련 리소스](how-to-educate-your-end-users-about-microsoft-intune.md)
  - [Android 장치용 최종 사용자 가이드](../enduser/using-your-android-device-with-intune.md)

중국에는 Google Play 스토어를 사용할 수 없으므로 Android 장치 사용자는 중국 앱 마켓플레이스에서 제공되는 회사 포털을 다운로드해야 합니다. Android용 회사 포털 앱은 다음 스토어에서 다운로드할 수 있습니다.
* [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
* [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
* [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
* [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)
* [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)

Android 용 회사 포털 앱은 Google Play 서비스를 사용하여 Microsoft Intune 서비스와 통신합니다. 중국에서는 Google Play 서비스가 아직 제공되지 않으므로 다음 작업을 수행하면 완료까지 최대 8시간 걸릴 수 있습니다. 

|Intune 관리 콘솔| Android용 Intune 회사 포털 앱 |Intune 회사 포털 웹 사이트|   
|---|---|---|
|전체 초기화| 원격 장치 제거| 장치(로컬 및 원격) 제거|
|선택적 초기화| 장치 다시 설정| 장치 재설정|
|신규 또는 업데이트된 앱 배포| 사용 가능한 LOB(기간 업무) 앱 설치| 장치 암호 재설정|
|원격 잠금|||
|암호 재설정|||

### <a name="see-also"></a>참고 항목
[Microsoft Intune에서 장치 등록을 위한 필수 조건](prerequisites-for-enrollment.md)



<!--HONumber=Feb17_HO3-->


