---
title: "MAM을 사용한 앱에 대한 최종 사용자 환경 | Microsoft Intune"
description: "이 항목에서는 모바일 앱 관리 정책을 통해 앱이 관리될 때 예상되는 결과를 설명합니다."
keywords: 
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b57e6525-b57c-4cb4-a84c-9f70ba1e8e19
ms.reviewer: andcerat
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 359f76daa35a14e4107a9e03c6a1b1f4d1215777
ms.openlocfilehash: e43dea5630975165ea7468836a8b0328f0656030


---

# Microsoft Intune을 사용하여 MAM을 사용한 앱에 대한 최종 사용자 환경
MAM(모바일 응용 프로그램 관리) 정책은 앱이 회사 컨텍스트에서 사용되는 경우에만 적용됩니다.  다음 시나리오를 참고하여 관리되는 앱을 작동하는 방법을 이해합니다.
##  iOS 장치에서 OneDrive 액세스

1.  	**OneDrive** 앱을 시작하여 로그인 페이지를 엽니다.

    ![OneDrive 로그인 페이지의 스크린 샷](../media/AppManagement/iOS_OneDriveLaunch.png)

    > [!NOTE]
    > 개인 장치에서는 일반적으로 최종 사용자가 앱을 다운로드합니다.  장치가 MDM 솔루션에서 관리되는 경우 장치에 앱을 배포할 수 있습니다.

2.  회사 계정 사용자 이름을 입력합니다. 회사 자격 증명을 입력할 수 있도록 **O365 인증** 페이지로 리디렉션됩니다.

    ![O365 로그인 페이지의 스크린 샷](../media/AppManagement/iOS_O365SignInPage.png)

3.  Azure AD에서 자격 증명을 성공적으로 인증하면 MAM 정책이 적용되며, **OneDrive** 앱을 다시 시작하라는 메시지가 표시됩니다.
  >[참고!] Intune에서 등록되지 않은 장치에서만 다시 시작 필요 대화 상자가 표시됩니다.

    ![다시 시작이 필요한 대화 상자의 스크린 샷](../media/AppManagement/iOS_AppRestartforMAM.png)

4.  **OneDrive** 앱을 다시 시작하면 MAM 정책이 켜진 상태로 앱이 시작됩니다. 이제 앱에 대한 **PIN** 을 설정하라는 메시지가 표시됩니다. (해당 정책을 구성한 경우).

    ![Pin을 입력하도록 요청하는 OneDrive 앱의 스크린 샷](../media/AppManagement/iOS_AppPINPrompt.png)

5.  PIN을 설정하고 확인하면 **비즈니스용 OneDrive**의 파일에 액세스할 수 있습니다.

    ![기존 파일의 목록으로 열린 파일 위치를 보여 주는 스크린 샷](../media/AppManagement/iOS_OneDriveSuccess.png)

    > [!NOTE]
    > 배포된 정책을 변경하는 경우 다음에 앱을 열 때 변경 내용이 적용됩니다.

##  Android 장치의 OneDrive 액세스

1.  OneDrive 앱을 시작하여 로그인 페이지를 엽니다.

    > [!NOTE]
    > 개인 장치에서는 일반적으로 최종 사용자가 앱을 다운로드합니다.  장치가 MDM 솔루션에서 관리되는 경우 장치에 앱을 배포할 수 있습니다.

2.  회사 계정 사용자 이름을 입력합니다. 회사 자격 증명을 입력할 수 있도록 **O365 인증** 페이지로 리디렉션됩니다.

    ![Android 장치에서 O365 로그인 페이지의 스크린 샷](../media/AppManagement/Android_O365SignInPage.png)

3.  **Azure AD**에서 자격 증명을 성공적으로 인증하면 회사 포털 앱을 설치하는 지침이 포함된 메시지가 표시됩니다(아직 장치에 설치되지 않은 경우).  **앱 다운로드** 를 탭하여 계속 진행합니다.

>[!NOTE]
>회사 포털 앱에는 Android 장치에서 MAM 정책과 관련된 모든 앱이 필요합니다. Intune에 등록되지 않은 장치의 경우 앱을 장치에 설치해야 하지만 시작 또는 앱에 로그인이 필요하지 않습니다.  


  ![회사 포털 앱 요구 사항 메시지가 있는 대화 상자의 스크린 샷](../media/AppManagement/Android_CompanyPortalMessage.png)

4.  이제 **Google Play** 스토어에 있으며, **회사 포털** 앱을 다운로드하고 설치할 수 있습니다.

    회사 포털 앱은 데이터를 안전하게 보호하는 데 도움이 됩니다.

    ![회사 포털 앱의 스크린 샷](../media/AppManagement/Android_CompanyPortalInstall.png)

5.  설치를 완료한 후 **동의함**을 선택하여 약관에 동의합니다.

6.  **OneDrive** 앱이 자동으로 시작됩니다.

7.  다음에 OneDrive를 열면 정책 설정이 **OneDrive**앱 액세스 시 PIN을 요구하도록 설정된 경우 **PIN** 을 설정하라는 메시지가 표시됩니다.

    ![PIN 프롬프트가 표시된 OneDrive 앱의 스크린 샷](../media/AppManagement/Android_OneDriveSetPIN.png)

8.  PIN이 설정 및 확인되고 나면 이제 앱 정책에 의해 관리되는 **OneDrive**를 계속 사용할 수 있습니다.


##  다중 ID가 지원되는 앱 사용
예를 들어 Microsoft Word는 이 시나리오에 사용됩니다.

1.  장치에서 **Word** 앱을 엽니다. 여기서는 iOS 장치를 사용하여 단계를 보여 줍니다.

2.  	**새로 만들기** 를 탭하여 새 Word 문서를 만듭니다.

    ![화면 맨 아래에 표시되는 새 메뉴 옵션이 있는 iOS 장치의 스크린 샷](../media/AppManagement/iOS_WordCreateNewDoc.png)

3.  사용자가 선택한 문장을 입력합니다.  이 문서를 저장하려는 경우 방금 만든 문서를 저장하기 위한 옵션으로 개인 및 회사 위치가 둘 다 표시됩니다.  이 단계에서는 이 회사/개인 컨텍스트가 아직 설정되지 않았으므로 앱 정책이 적용되지 않습니다.

4.  비즈니스용 OneDrive 위치에 문서를 저장합니다. 이 문서는 이제 회사 데이터로 태깅되고 정책 제한이 적용됩니다.

    ![Word 문서에서 입력된 문장의 스크린 샷](../media/AppManagement/iOS_WordCreateCompanyDoc.PNG)

5.  회사 위치에 저장한 문서를 엽니다.  텍스트를 복사하고 개인**Facebook** 계정을 연 다음 복사한 텍스트를 붙여넣으려고 합니다.  새 Facebook 게시물에 콘텐츠를 붙여넣을 수 없습니다. 붙여넣기 옵션이 회색으로 표시되지는 않지만 **붙여넣기**를 누를 때 아무 작업도 수행되지 않습니다.

    ![잘라내기, 복사 및 붙여넣기 선택 항목을 보여 주는 스크린 샷](../media/AppManagement/iOS_WordCopyCompany.png)

    ![Facebook 게시물에 붙여 넣지 않은 데이터를 보여 주는 스크린 샷](../media/AppManagement/iOS_FacebookPasteCompany.png)

6.  이제 2단계와 3단계를 반복하여 다른 새 문서를 만들고, 선택한 문장을 입력한 다음 회사에 저장하는 대신 **OneDrive - 개인**과 같은 개인 위치에 저장합니다.

    ![복사하려고 선택한 문장이 있는 잘라내기, 복사 및 붙여넣기 선택 항목의 스크린 샷](../media/AppManagement/iOS_WordCopyPersonal.png)

7.  저장된 개인 문서를 엽니다.  텍스트를 복사하고 **Facebook** 앱을 연 다음 복사한 텍스트를 붙여넣으려고 합니다. 보시다시피 Facebook 게시물에 콘텐츠를 붙여넣을 수 있습니다.

    ![Facebook 게시물에 붙여 넣었음을 보여 주는 콘텐츠](../media/AppManagement/iOS_FacebookPastePersonal.png)

##  사용자 계정 관리

Intune은 장치 당 하나의 사용자 계정에 MAM 정책을 배포하도록 지원합니다. 장치에 둘 이상의 회사 계정이 있으면 하나의 회사 계정은 MAM 정책에 의해 관리됩니다.

사용 중인 앱에 따라 두 번째 사용자는 장치에서 차단될 수도 있고 차단되지 않을 수도 있습니다. 그러나 어떤 경우이든 MAM 정책을 가져오는 첫 번째 사용자만이 정책에 영향을 받습니다.

MAM 정책을 배포하기 전에 장치에 기존의 여러 사용자 계정이 있으면 첫 번째 사용자에게 MAM 정책을 배포하는 계정은 Intune MAM 정책에 의해 관리됩니다.

**Microsoft Word**, **Excel** 및 **PowerPoint**는 두 번째 사용자 계정을 차단하지 않지만 두 번째 사용자 계정은 MAM 정책의 영향을 받지 않습니다.  

**OneDrive 및 Outlook 앱**의 경우 회사 계정을 하나만 사용할 수 있습니다.  해당 앱에서는 여러 회사 계정의 추가가 차단됩니다.  그러나 사용자를 제거하고 장치에 다른 사용자를 추가할 수 있습니다.

여러 사용자 계정이 처리되는 방법을 더 깊게 이해하려면 아래 예제 시나리오를 참고합니다.

사용자 A는 **회사 X** 및 **회사 Y**에서 일합니다. 사용자 A는 각 회사에 회사 계정을 보유하고 둘 다 Intune를 사용하여 MAM 정책을 배포합니다. **회사 X**는 **회사 Y**보다 **먼저** MAM 정책을 배포합니다. **회사 X**와 연결된 계정은 MAM 정책을 가져오지만 회사 Y와 관련된 계정이 아닙니다. 회사 Y와 관련된 사용자 계정이 MAM 정책에 의해 관리되기를 바란다면 회사 X와 관련된 사용자 계정을 제거해야 합니다.
### 두 번째 계정 추가
#### iOS
iOS 장치를 사용하는 경우 동일한 장치에 두 번째 회사 계정을 추가하려고 하면 차단 메시지가 표시될 수 있습니다.  또한 기존 계정을 제거하고 새 계정을 추가하는 옵션이 표시됩니다. 이 작업을 위해 **예**를 선택합니다.

![메시지 및 예 및 아니요 옵션을 차단하는 대화 상자의 스크린 샷](../media/AppManagement/iOS_SwitchUser.PNG)
####  Android
Android 장치를 사용하는 경우 기존 계정을 제거하고 새 계정을 추가하는 지침이 포함된 차단 메시지가 표시될 수 있습니다.  Android 장치에서 기존 계정을 제거하려면 **설정 &gt;일반 &gt; 응용 프로그램 관리자 &gt; 회사 포털로 이동한 다음 "데이터 지우기"를 선택**합니다.

![오류 메시지 및 계정을 제거하는 지침의 스크린 샷](../media/AppManagement/Android_SwitchUser.png)

##  Rights Management 공유 앱을 사용하여 미디어 파일 보기
Android 장치에서 회사 AV, PDF 및 이미지 파일을 보려면 [Microsoft Rights Management(RMS) 공유 앱](https://play.google.com/store/apps/details?id=com.microsoft.ipviewer)을 사용합니다.

Google Play 스토어에서 이 응앱을 다운로드합니다.  앱이 장치에 설치되면 앱을 실행하고 회사 자격 증명으로 인증합니다. 이제 다른 정책에서 관리하는 앱에서 보호되지 않거나 보호된 파일을 볼 수 있습니다.

다음 파일 형식이 지원됩니다.

* **오디오:** AAC LC, HE-AACv1(AAC+), HE-AACv2(향상된 AAC+), AAC ELD(향상된 낮은 지연 AAC), AMR-NB, AMR-WB, FLAC, MP3, MIDI, Vorbis, PCM/WAVE.
* **비디오:** H.263, H.264 AVC, MPEG-4 SP, VP8.
* **이미지:** jpg, pjpg, png, ppng, bmp, pbmp, gif, pgif, jpeg, pjpeg.
* PDF, PPDF

------------
|**pfile**|**텍스트**|
|----|----|
|Pfile은 암호화된 콘텐츠 및 RMS 라이선스를 캡슐화하고 모든 파일 형식을 보호하기 위해 사용할 수 있는 보호된 파일에 대한 일반적인 "래퍼" 형식입니다.|XML, CSV 등을 포함하는 텍스트 파일은 보호되는 경우에도 앱에서 열어서 볼 수 있습니다. 파일 형식: txt, ptxt, csv, pcsv, log, plog, xml, pxml|
---------------
**Intune에 등록하지 않은 Android 장치**

Intune에서 관리하는 다른 앱에서 파일을 보기 위해 RMS 공유 앱을 사용하려면 먼저 RMS 앱을 시작한 다음 회사 계정으로 인증합니다.  로그인한 상태에서 **RMS 라이선스가 없는 경우에 한해** 다음과 같은 메시지가 표시됩니다.

**인증 성공 - 이제 회사 파일을 볼 수 있지만 사용자가 파일을 보호할 수 있는 권한을 갖도록 조직이 설정되지 않습니다. 자세한 내용은 IT 관리자에게 문의하세요.**

이 메시지가 나타나도 RMS 공유 앱을 사용하여 회사 파일을 볼 수는 있습니다. Intune에서 관리하는 다른 앱에서 회사 파일을 열고 볼 수는 있으며 MAM 정책이 계속 적용됩니다.  이 메시지의 의미는 RMS 공유 앱의 추가 보호 기능을 추가할 수 없다는 것입니다.  보호 기능을 파일에 추가하려면 RMS 라이선스가 있어야 합니다. RMS 파일 보호 기능에 대한 자세한 내용을 확인하려면 [장치에서 파일 보호](https://docs.microsoft.com/en-us/rights-management/rms-client/sharing-app-protect-in-place) 및 [메일로 공유하는 파일 보호](https://docs.microsoft.com/en-us/rights-management/rms-client/sharing-app-protect-by-email)를 참조하세요.


### 참고 항목
[Microsoft Intune으로 모바일 앱 관리 정책 만들기 및 배포](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Jul16_HO3-->


