---
title: Android for Work 설정
description: Microsoft Intune으로 Android for Work 장치에 대한 MDM(모바일 장치 관리)을 설정합니다.
keywords: ''
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/29/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: b2fdcea9-9ad7-4d73-88e2-854b7a774bb2
ROBOTS: NOINDEX,NOFOLLOW
ms.custom: intune-classic
ms.openlocfilehash: 366e2b281c05e1233c61f7f35a50700677ad4b79
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="enable-enrollment-of-android-for-work-devices"></a>Android for Work 장치 등록 사용

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Android for Work 장치 관리를 사용하도록 설정하려면 Intune에 Android for Work 바인딩을 추가해야 합니다. Android for Work를 지원하지만 이전에 정규 Android 장치로 등록된 장치를 등록하려면 먼저 장치를 등록 취소한 후에 다시 등록해야 합니다.

## <a name="add-android-for-work-binding-for-intune"></a>Intune에 대한 Android for Work 바인딩 추가

1. **Intune 설정**<br>
모바일 장치 관리를 아직 준비하지 않은 경우 [모바일 장치 관리 기관](/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-8#enable-device-enrollment)을 **Microsoft Intune**으로 설정하고 MDM을 설정하여 관리를 준비합니다.

2. **Android for Work 바인딩 구성**<br>
    Intune 관리자 권한으로 [Microsoft Intune 관리 콘솔](https://manage.microsoft.com)을 열고 **관리** &gt; **모바일 장치 관리** &gt; **Android for Work**로 이동한 다음 **구성**을 클릭하여 Google Play의 Android for Work 웹 사이트를 엽니다. 이렇게 하면 브라우저에서 새 탭으로 열립니다.

3. **Google에 로그인**<br>
   Google의 로그인 페이지에서 이 테넌트에 대한 모든 Android for Work 관리 작업과 연결할 Google 계정을 입력합니다. 이 계정은 조직의 IT 관리자 간에 공유되며 Play for Work 콘솔에서 앱을 관리 및 게시하는 데 사용되는 Google 계정입니다.

4. **조직 세부 정보 제공**<br>
   **조직 이름**에 회사 이름을 제공합니다. **EMM(엔터프라이즈 이동성 관리) 공급자**의 경우 *Microsoft Intune*이 나타나야 합니다. Android for Work 계약에 동의하고 **확인**을 클릭합니다. 요청이 처리됩니다.

## <a name="specify-android-for-work-enrollment-settings"></a>Android for Work 등록 설정 지정
   Android for Work는 특정 Android 장치에서만 지원됩니다. Google의 [Android for Work requirements](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012 style="target=new_window")(Android for Work 요구 사항)를 참조하세요.  Android for Work를 지원하는 장치는 기본 Android 관리도 지원합니다.  Intune에서는 Android for Work를 지원하는 장치를 관리하는 방법을 지정할 수 있습니다.

   - **Android로 모든 장치 관리** - Android for Work를 지원하는 장치를 비롯하여 모든 Android 장치는 기본 Android 장치로 등록됩니다.
   - **Android for Work로 지원되는 장치 관리** - Android for Work를 지원하는 모든 장치는 Android for Work 장치로 등록됩니다. Android for Work를 지원하지 않는 Android 장치는 기본 Android 장치로 등록됩니다.
   - **사용자 그룹에 있는 사용자에 대해서만 Android for Work로 지원되는 장치 지원** - Android for Work 관리 대상을 제한된 사용자 집합으로 제한할 수 있습니다. Android for Work를 지원하는 장치를 등록하도록 선택된 그룹 구성원만 Android for Work 장치로 등록됩니다. 다른 구성원은 모두 Android 장치로 등록됩니다. 이 설정은 Android for Work 파일럿 기간에 유용합니다.

## <a name="next-steps-for-android-for-work"></a>Android for Work를 위한 다음 단계
Android for Work 바인딩 및 설정을 구성한 후 다음을 수행할 수 있습니다.
- [Android for Work 앱 배포](android-for-work-apps.md)
- [Android for Work 구성 정책 추가](android-for-work-policy-settings-in-microsoft-intune.md)

## <a name="unbinding-your-android-for-work-administrative-account"></a>Android for Work 관리 계정 바인딩 해제

Android for Work 등록 및 관리를 해제할 수 있습니다. Intune 관리 콘솔에서 **바인딩 해제**를 클릭하면 등록된 모든 Android for Work 장치가 등록에서 제거되고 Android for Work 계정과 Intune 간 관계가 제거됩니다.

### <a name="how-to-unbind-an-android-for-work-account"></a>Android for Work 계정을 바인딩 해제하는 방법

1. **Android for Work 바인딩에 대한 바인딩 해제**<br>
    관리자 권한으로 [Microsoft Intune 관리 콘솔](https://manage.microsoft.com)을 열고 **관리** &gt; **모바일 장치 관리** &gt; **Android for Work**를 열고 **바인딩 해제**를 클릭합니다.

2. **Android for Work 바인딩 삭제 동의**<br>
  바인딩을 삭제하고 Intune에서 Android for Work를 모두 등록 해제하려면 **예**를 클릭합니다.
