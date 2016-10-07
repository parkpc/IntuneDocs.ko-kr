---
title: "Lookout 통합 문제 해결 | Microsoft Intune"
description: "이 항목에서는 Lookout 통합에서 흔히 발생하는 문제의 해결 방법을 설명합니다."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: bbe0b5f4-b8bc-49f3-85a9-51fb2f226fca
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0736b5f24065f55d8fbd312395e4bb7226ebf619
ms.openlocfilehash: 5acf5c707a93aa0b5e7cefdcb0b160af09b9cf70


---

# Intune과 Lookout의 통합 문제 해결
이 항목에서는 Lookout MTP(Mobile Threat Protection) 설정 시 흔히 발생하는 몇 가지 문제를 설명합니다.
## 로그인 오류 문제 해결
### 403 오류
[Lookout MTP 콘솔](https://aad.lookout.com)에 로그인할 때 403 오류 **서비스에 액세스할 권한이 없습니다.** 메시지가 나타날 수 있습니다. 이 오류는 지정한 사용자 이름이 Lookout MTP에 액세스하도록 구성된 Azure AD(Azure Active Directory) 그룹의 구성원이 아닌 경우에 발생할 수 있습니다.

Lookout MTP는 구성된 Azure AD 그룹의 사용자만 액세스할 수 있도록 구성됩니다. 구성된 그룹 중에서 Lookout MTP 액세스 권한이 있는 그룹을 확실히 모르겠으면 Lookout 지원 부서에 문의합니다.

다음 방법으로 Lookout 지원 부서에 문의할 수 있습니다.

* 메일: enterprisesupport@lookout.com
* [MTP 콘솔](http://aad.lookout.com)에 로그인한 후 **지원** 모듈로 이동합니다.
* https://enterprise.support.lookout.com/hc/en-us/requests로 이동하여 지원을 요청합니다.

### 로그인할 수 없음
Azure AD 전역 관리자가 초기 Lookout 설정을 수락하지 않은 경우 다음 오류가 나타날 수 있습니다.

![로그인 오류를 보여 주는 Lookout 로그인 화면의 스크린샷](../media/mtp/lookout-mtp-consent-not-accepted-error.png)

이 문제를 해결하려면 전역 관리자가 https://aad.lookout.com/les?action=consent에 로그인하여 설치 초기화 확인 메시지를 수락해야 합니다. 자세한 정보는 [Lookout MTP 구독 설정](set-up-your-subscription-with-lookout-mtp.md) 항목에서 확인할 수 있습니다.

## 장치 상태 문제 해결

### 장치가 Lookout MTP 콘솔의 장치 목록에 표시되지 않음

이 문제는 다음 시나리오에서 발생할 수 있습니다.
* 이 장치를 소유하는 사용자가 **Lookout MTP 콘솔**에 지정된 **등록 그룹**에 없는 경우.  **시스템** 모듈에서 **Intune Connector** 탭으로 이동하여 **등록 관리** 설정을 확인합니다.  등록하기 위해 구성한 Azure AD 그룹이 하나 이상 보일 것입니다.  누락된 장치를 소유하는 사용자가 지정된 Azure AD 그룹에 속하는지 확인합니다.  새 사용자를 등록 그룹에 추가하면, 구성된 최대 폴링 간격(5분이 기본값임)이 지나야 장치가 Lookout MTP 콘솔의 **장치** 모듈에서 보입니다.

* 장치가 Lookout MTP에서 지원되지 않는 경우.  지원되지 않는 장치는 Lookout MTP 콘솔의 커넥터 설정에서 **관리되는 장치** 섹션에 나타납니다.

### 장치가 **보류 중** 상태로 계속 보고됨

장치가 **보류 중**으로 나타나는 것은 최종 사용자가 아직 Lookout for work 앱을 열어 **활성화** 단추를 탭하지 않았기 때문입니다. Lookout for Work 앱에서 장치를 활성화하는 방법에 대한 자세한 내용은 다음 항목을 참조하세요.

[Android 장치에 Lookout for Work를 설치하라는 메시지가 표시됨 ](http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android)

### Lookout MTP 콘솔에서 장치가 활성 상태로 표시되지만 장치 ID가 없습니다.  
이 장치를 소유하는 사용자가 Lookout MTP 콘솔에 지정된 등록 그룹에 없기 때문입니다.   장치를 소유하는 사용자가 등록 그룹에서 제거되었거나 그 사용자가 속한 등록 그룹이 제거되었을 때도 장치는 이 상태가 될 수 있습니다.

Lookout MTP 콘솔의 **시스템** 모듈에서 **Intune Connector** 탭으로 이동하여 **등록** 설정을 검토합니다.  등록하기 위해 구성한 Azure AD 그룹이 하나 이상 보일 것입니다.  장치를 소유하는 사용자가 지정된 Azure AD 그룹에 속하는지 확인합니다.  

장치가 이 상태에 있다면 Lookout은 위협을 감지하면 계속해서 사용자에게 알려주기는 하지만 Intune에 위협 정보를 전송하지는 않습니다.

### 장치가 연결 끊김 상태로 표시됨

연결이 끊겼다는 것은 Lookout MTP가 미리 구성된 시간 간격(기본값은 최소 7일에서 최대 30일) 동안 장치에서 아무런 수신을 받지 못했다는 의미입니다. 또한 회사 포털 앱 또는 Lookout for Work 앱이 장치에 설치되지 않았거나 제거되었음을 의미합니다. 앱을 다시 설치하면 이 문제가 해결될 것입니다. 사용자가 Lookout for Work를 열어 앱을 활성화하면 장치가 Lookout MTP, Intune과 함께 다시 동기화됩니다.    

### 장치에서 강제로 다시 동기화
관리자는 Lookout MTP 콘솔의 **장치** 모듈에서 장치를 선택한 후 삭제하도록 선택할 수 있습니다.   다음번에 장치 소유자가 Lookout for Work 앱을 열어 **활성화**를 탭하면 장치 상태가 완전히 다시 동기화됩니다.

### 장치 소유자가 이제 이 장치를 사용하지 않음
장치를 초기화하고 새 사용자에게 등록하도록 요청해야 합니다.  장치를 관리에서 제거하도록, [Intune 관리자 콘솔](https://manage.microsoft.com)에서 장치를 선택한 후 마우스 오른쪽 단추로 클릭하여 **사용 중지/초기화**를 선택합니다. 장치를 사용 중지한 후 삭제할 수 있습니다.

![사용 중지/초기화 옵션이 표시된 Intune 관리 콘솔의 장치 모듈 스크린샷](../media/mtp/mtp-retire-device-intune-console.png)

Lookout MTP 콘솔의 **장치** 모듈에서 **삭제**를 선택할 수도 있습니다.  

새 사용자가 Lookout MTP 콘솔에 지정된 등록 그룹에 속해 있는 동안에는 Azure AD가 장치를 새 사용자에 연결하면 장치가 나타납니다.

## 규정 준수 수정 워크플로
[Android 장치에 Lookout for Work를 설치하라는 메시지가 표시됨]( http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android)

[Android 장치에서 Lookout for Work가 발견한 위협을 해결해야 함 ](http://docs.microsoft.com/intune/enduser/you-need-to-resolve-a-threat-found-by-lookout-for-work-android)


### 참고 항목
[Lookout MTP 구독 설정](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-your-subscription-with-lookout-mtp)



<!--HONumber=Oct16_HO1-->


