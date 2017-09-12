---
title: "앱 보호 정책을 사용하는 Android 앱"
titlesuffix: Azure portal
description: "이 항목에서는 앱 보호 정책을 통해 Android 앱을 관리할 때 예상되는 상황을 설명합니다.\""
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a6816285-8e43-4dc8-bca0-e80ec5ef01e6
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ac70c8ce3bbc8338339e7becb8b28d594bb2fbf6
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/09/2017
---
# <a name="what-to-expect-when-your-android-app-is-managed-by-app-protection-policies"></a>Android 앱이 앱 보호 정책에 의해 관리될 때 예상되는 상황 

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

이 항목에서는 앱 보호 정책이 적용되는 앱에 대한 사용자 환경을 설명합니다. 앱 보호 정책은 회사 계정을 사용하여 앱에 액세스하거나 회사의 OneDrive 비즈니스 위치에 저장된 파일에 액세스하는 경우처럼 앱이 업무용으로 사용될 때만 적용됩니다.
##  <a name="accessing-apps"></a>앱 액세스

회사 포털 앱에는 Android 장치에서 앱 보호 정책과 관련된 모든 앱이 필요합니다.

Intune에 등록되지 않은 장치의 경우 회사 포털 앱을 장치에 설치해야 합니다. 그러나 사용자는 앱 보호 정책에 의해 관리되는 앱을 사용하기 위해 먼저 회사 포털 앱을 시작하거나 로그인해야 할 필요가 없습니다.
회사 포털 앱은 intune에서 안전한 위치를 통해 데이터를 공유하는 방법이므로, 장치가 Intune에 등록되어 있지 않아도 회사 포털 앱은 필요합니다.


##  <a name="using-apps-with-multi-identity-support"></a>다중 ID가 지원되는 앱 사용

앱 보호 정책은 업무용으로 앱을 사용할 때만 적용되므로 업무용인지 개인용인지에 따라 앱 동작이 달라질 수 있습니다.

다중 ID를 지원하는 앱의 경우, Intune은 최종 사용자가 업무용으로 앱을 사용할 때만 앱 보호 정책을 적용합니다.  예를 들어 최종 사용자는 업무용 데이터에 액세스할 경우 PIN 프롬프트를 받습니다.  **Outlook 앱**에서는 최종 사용자가 앱을 시작할 때 PIN을 입력하라는 메시지가 표시됩니다. **OneDrive 앱**에서는 최종 사용자가 회사 계정을 입력할 때 PIN을 입력하라는 메시지가 표시됩니다.  Microsoft **Word**, **PowerPoint* 및 **Excel**의 경우에는 최종 사용자가 회사의 비즈니스용 OneDrive 위치에 저장된 문서에 액세스할 때 PIN을 입력하라는 메시지가 표시됩니다.
##  <a name="managing-user-accounts-on-the-device"></a>장치에서 사용자 계정 관리

Intune은 장치 당 하나의 사용자 계정에 앱 보호 정책을 배포하도록 지원합니다.

* 사용 중인 앱에 따라 두 번째 사용자는 장치에서 차단될 수도 있고 차단되지 않을 수도 있습니다. 그러나 어떤 경우이든 앱 보호 정책을 가져오는 첫 번째 사용자만이 정책에 영향을 받습니다.

  * **Microsoft Word**, **Excel** 및 **PowerPoint**는 두 번째 사용자 계정을 차단하지 않지만 두 번째 사용자 계정은 앱 보호 정책의 영향을 받지 않습니다.

  * **OneDrive 및 Outlook 앱**의 경우 회사 계정을 하나만 사용할 수 있습니다.  해당 앱에서는 여러 회사 계정의 추가가 차단됩니다.  그러나 사용자를 제거하고 장치에 다른 사용자를 추가할 수 있습니다.


* 앱 보호 정책을 배포하기 전에 장치에 기존의 여러 사용자 계정이 있으면 첫 번째 사용자에게 앱 보호 정책을 배포하는 계정은 Intune 앱 보호 정책에 의해 관리됩니다.


여러 사용자 계정이 처리되는 방법을 더 깊게 이해하려면 아래 예제 시나리오를 참고합니다.

사용자 A는 **회사 X** 및 **회사 Y**에서 일합니다. 사용자 A는 각 회사에 회사 계정을 보유하고 둘 다 Intune을 사용하여 앱 보호 정책을 배포합니다. **회사 X**는 **회사 Y**보다 **먼저** 앱 보호 정책을 배포합니다. **회사 X**와 연결된 계정은 앱 보호 정책을 가져오지만 회사 Y와 관련된 계정이 아닙니다. 회사 Y와 관련된 사용자 계정이 앱 보호 정책에 의해 관리되기를 바란다면 회사 X와 관련된 사용자 계정을 제거해야 합니다.
### <a name="adding-a-second-account"></a>두 번째 계정 추가
####  <a name="android"></a>Android
Android 장치를 사용하는 경우 기존 계정을 제거하고 새 계정을 추가하는 지침이 포함된 차단 메시지가 표시될 수 있습니다.  기존 계정을 제거하려면 **설정 &gt;일반 &gt; 응용 프로그램 관리자 &gt; 회사 포털로 이동한 다음 "데이터 지우기"를 선택**합니다.

![오류 메시지 및 계정을 제거하는 지침의 스크린 샷](./media/android-switch-user.png)

##  <a name="viewing-media-files-with-the-azure-information-protection-app-previously-known-as-rights-management-sharing-app"></a>Azure Information Protection 앱(이전에는 Rights Management 공유 앱)으로 미디어 파일 보기
Android 장치에서 회사 AV, PDF 및 이미지 파일을 보려면 [Azure Information Protection 앱](https://play.google.com/store/apps/details?id=com.microsoft.ipviewer)을 사용합니다.

Google Play 스토어에서 이 응앱을 다운로드합니다.  

다음 파일 형식이 지원됩니다.

* **오디오:** AAC LC, HE-AACv1(AAC+), HE-AACv2(향상된 AAC+), AAC ELD(향상된 낮은 지연 AAC), AMR-NB, AMR-WB, FLAC, MP3, MIDI, Ogg Vorbis, PCM/WAVE.
* **비디오:** H.263, H.264 AVC, MPEG-4 SP, VP8.
* **이미지:** jpg, pjpg, png, ppng, bmp, pbmp, gif, pgif, jpeg, pjpeg.
* **문서:** PDF, PPDF

------------
|**pfile**|**텍스트**|
|----|----|
|Pfile은 암호화된 콘텐츠와 Azure Information Protection 라이선스를 캡슐화하고 모든 파일 형식을 보호하는 데 사용할 수 있는 보호된 파일의 일반적 "래퍼" 형식입니다.|XML, CSV 등을 포함하는 텍스트 파일은 보호되는 경우에도 앱에서 열어서 볼 수 있습니다. 파일 형식: txt, ptxt, csv, pcsv, log, plog, xml, pxml|
---------------
## <a name="next-steps"></a>다음 단계
[iOS 앱이 앱 보호 정책으로 관리될 때 예상되는 상황](app-protection-enabled-apps-ios.md)

### <a name="see-also"></a>참고 항목
[Microsoft Intune으로 앱 보호 정책 만들기 및 배포](app-protection-policies.md)
