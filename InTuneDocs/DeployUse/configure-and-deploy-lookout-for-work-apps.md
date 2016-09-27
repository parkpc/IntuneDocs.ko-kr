---
title: "Lookout for Work 앱 배포 | Microsoft Intune"
description: "Android용 Lookout for Work 앱을 구성하고 배포합니다."
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 524c4209-ad57-4d35-955e-a00d796bf858
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9c2ffb5fe497d56d8250fe3dec7db606c2067a1c
ms.openlocfilehash: c43104ff199e1800bfded35154d2be0cfd0c40f3


---

# Lookout for Work 앱 구성 및 배포
이번 릴리스에서는 4.1을 실행하는 Android 장치에서 Lookout for work 앱을 사용할 수 있습니다.
## Android
이 섹션에서는 Intune에 등록한 Android 장치에 Lookout for Work 응용 프로그램을 구성하고 배포하는 방법을 설명합니다.  
* 1단계: [Microsoft Intune 관리자 콘솔](https://manage.microsoft.com)에서 **앱**으로 이동하고 **앱 추가**를 선택합니다.   
* 2단계: 게시자의 **소프트웨어 설치** 페이지에서 **외부 링크**를 선택한 후 다음 URL을 지정합니다. https://play.google.com/store/apps/details?id=com.lookout.enterprise
>[!NOTE]
>관리되는 브라우저가 필요한 상자는 클릭하지 마세요.

* 3단계: **소프트웨어 설명** 페이지에서 다음 정보를 입력합니다.
  * **게시자:** Lookout Mobile Security
  * **이름:** Lookout for Work
  * **설명:** Lookout은 우수한 보호 기능으로 장치를 모바일 위협으로부터 안전하게 지켜줍니다. Lookout 앱을 장치에 설치하면 앱이 위협으로부터 장치를 보호하고 위협을 발견하면 사용자는 물론, 사용자의 회사 관리자에게 알려줍니다.
  * **범주:** 컴퓨터 관리
* 4단계: 완료하면 **Microsoft Intune으로 데이터를 업로드했습니다.** 메시지가 나타납니다.

이제 Intune 콘솔에서 **앱**을 클릭하면 목록에 Lookout for Work 앱이 보입니다. ![목록에 나타난 Lookout for work 앱을 보여주는 Intune 관리 콘솔 앱 페이지의 스크린샷](../media/mtp/lookout-app-listed-intune-console.png)

5단계: 이 시점에서 Intune은 Lookout for Work Android 앱을 배포하는 방법을 인식하게 됩니다.   위 화면에 표시된 Lookout for Work 앱을 선택한 후 **배포 관리**를 선택하여 앱을 사용자에게 배포할 수 있습니다.

Lookout MTP 콘솔의 등록 관리 옵션에 추가한 사용자와 동일한 사용자를 선택해야 합니다.  Lookout MTP에 사용자 그룹을 추가하는 방법에 대한 정보는 [Lookout MTP 구독 구성 섹션](set-up-your-subscription-with-lookout-mtp#configure-your-subscription-with-lookout-mtp)에 나온 3단계를 참조하세요.
>[!IMPORTANT]
> Intune 앱 배포 마법사는 Azure AD 사용자 그룹을 인식하지 못하기 때문에 Intune 사용자 그룹을 대신 사용합니다. 따라서 [이](plan-your-user-and-device-groups.md) 항목에 설명한 대로, Lookout MTP 콘솔에 등록된 Azure AD 사용자 그룹을 기반으로 Intune 사용자 그룹을 만들어야 합니다.

6단계: Lookout 앱을 사용자 장치에 설치하도록 하는 **필수 설치**를 선택합니다.

### 장치 활성화
배포를 위해 **필수 설치** 옵션을 선택하면 Intune에서 Lookout for work 응용 프로그램을 장치에 푸시합니다.   

사용자가 장치에서 Lookout for Work를 열면 앱을 활성화하고 Azure Active Directory로 로그인 옵션을 선택하라는 메시지가 표시됩니다. 최종 사용자의 작업 과정에 대한 자세한 안내는 다음 항목에서 살펴볼 수 있습니다.

* [Android 장치에 Lookout for Work를 설치하라는 메시지가 표시됨](http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android)

* [Android 장치에서 Lookout for Work가 발견한 위협을 해결해야 함](http://docs.microsoft.com/intune/enduser/you-need-to-resolve-a-threat-found-by-lookout-for-work-android)

## 다음 단계
* [규정 준수 정책에서 장치 위협 방지 규칙 활성화](enable-device-threat-protection-rule-in-compliance-policy.md)



<!--HONumber=Sep16_HO2-->


