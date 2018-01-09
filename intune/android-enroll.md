---
title: "Intune에서 Android 장치 등록 | Microsoft Docs"
titlesuffix: Azure portal
description: "Intune에 Android 장치를 등록하는 방법을 알아봅니다."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: angrobe
ms.date: 12/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ad018bdfa55b030f5d714017ae09f616ae2bf164
ms.sourcegitcommit: 9fabf1a8db53842f7b00762374de5b137158ee25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="enroll-android-devices"></a>Android 장치 등록

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune 관리자는 Samsung Knox Standard 장치를 포함한 Android 장치를 관리할 수 있습니다. 회사 프로필 [Android for Work 장치](#enable-enrollment-of-android-for-work-devices)를 관리할 수도 있습니다.

Samsung Knox Standard를 실행하는 장치가 Intune의 다중 사용자 관리에서 지원됩니다. 즉, 사용자가 Azure AD 자격 증명을 사용하여 장치에 로그인하고 로그아웃할 수 있습니다. 장치는 사용 여부와 관계없이 중앙에서 관리됩니다. 사용자가 로그인하면 앱에 액세스할 수 있고 앱에 정책을 적용할 수도 있습니다. 사용자가 로그아웃하면 모든 앱 데이터가 지워집니다.

## <a name="prerequisite"></a>필수 구성 요소

모바일 장치 관리를 준비하려면 MDM 기관을 **Microsoft Intune**으로 설정해야 합니다. 지침은 [MDM 기관 설정](mdm-authority-set.md)을 참조하세요. 이 항목은 모바일 장치 관리에 대해 Intune을 처음 설정할 때 한 번만 설정하면 됩니다.

## <a name="set-up-android-enrollment"></a>Android 등록 설정

기본적으로 Intune에서는 Android 및 Samsung Knox Standard 장치 등록을 허용합니다.

Android 장치를 차단하거나 등록에서 개인적으로 소유한 Android 장치를 차단하려면 [장치 유형 제한 설정](enrollment-restrictions-set.md)을 참조하세요.

장치 관리를 사용하려면 사용자가 Google Play에서 사용할 수 있는 Intune 회사 포털 앱을 다운로드한 다음 앱을 열고 안내에 따라 장치를 등록해야 합니다. Android 장치가 관리되면 [준수 정책 할당](compliance-policy-create-android.md), [앱 관리](app-management.md) 등을 수행합니다.

## <a name="enable-enrollment-of-android-for-work-devices"></a>Android for Work 장치 등록 사용

[Android for Work를 지원](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012)하는 장치의 작업 프로필 관리를 사용하도록 설정하려면 Intune에 Android for Work 바인딩을 추가해야 합니다. Android for Work를 지원하지만 이전에 정규 Android 장치로 등록된 장치를 등록하려면 먼저 장치 등록을 취소한 다음 다시 등록해야 합니다.

[장치 등록 관리자](device-enrollment-manager-enroll.md) 계정을 사용하여 Android for Work 장치를 등록하는 경우 계정당 등록할 수 있는 장치 수는 최대 10개입니다.

## <a name="add-android-for-work-binding-for-intune"></a>Intune에 대한 Android for Work 바인딩 추가

1. **Intune MDM 설정**<br>
아직 설정하지 않은 경우 **Microsoft Intune**으로 [모바일 장치 관리 기관을 설정](mdm-authority-set.md)하여 모바일 장치 관리를 준비합니다.
2. **Android for Work 바인딩 구성**<br>
    Azure Portal에서 Intune 관리자로 **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.

   a. **Intune** 블레이드에서 **장치 등록** > **Android for Work 등록**을 선택하고 **구성**을 선택하여 Google Play의 Android for Work 웹 사이트를 엽니다. 웹 사이트가 브라우저의 새 탭에 열립니다.
   ![Android for Work 바인딩을 구성할 링크가 표시된 스크린샷](./media/android-work-bind.png)

   b. **Google에 로그인**<br>
   Google의 로그인 페이지에서 이 테넌트에 대한 모든 Android for Work 관리 작업과 연결할 Google 계정을 입력합니다. Play for Work 콘솔에서 앱을 관리 및 게시하기 위해 귀사의 IT 관리자가 공유하는 Google 계정입니다.

   c. **조직 세부 정보 제공**<br>
   **조직 이름**에 회사 이름을 제공합니다. **EMM(엔터프라이즈 이동성 관리) 공급자**의 경우 **Microsoft Intune**이 나타나야 합니다. Android for Work 계약에 동의하고 **확인**을 선택합니다. 요청이 처리됩니다.

## <a name="specify-android-for-work-enrollment-settings"></a>Android for Work 등록 설정 지정
   Android for Work는 특정 Android 장치에서만 지원됩니다. Google의 [Android for Work requirements](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012 style="target=new_window")(Android for Work 요구 사항)를 참조하세요. Android for Work를 지원하는 장치는 기본 Android 관리도 지원합니다. Intune에서는 Android for Work를 지원하는 장치를 관리하는 방법을 지정할 수 있습니다.

   - **모든 장치를 Android로 관리** Android for Work를 지원하는 장치를 비롯한 모든 Android 장치가 기존 Android 장치로 등록됩니다.
   - **지원되는 장치를 Android for Work로 관리** Android for Work를 지원하는 모든 장치가 Android for Work 장치로 등록됩니다. Android for Work를 지원하지 않는 Android 장치는 기본 Android 장치로 등록됩니다.
   - **이 사용자 그룹의 사용자에 대해서만 지원되는 장치를 Android for Work로 관리** Android for Work 관리 대상을 제한된 사용자 집합으로 지정할 수 있습니다. Android for Work를 지원하는 장치를 등록하도록 선택된 그룹 구성원만 Android for Work 장치로 등록됩니다. 다른 구성원은 모두 Android 장치로 등록됩니다. 이 설정은 Android for Work 파일럿 기간에 유용합니다.

## <a name="approve-the-company-portal-app-in-the-managed-google-play-store"></a>관리되는 Google Play 스토어에서 회사 포털 앱 승인
관리되는 Google Play 스토어에서 Android용 회사 포털 앱을 승인하여 자동 앱 업데이트를 받도록 해야 합니다. 승인하지 않으면 회사 포털이 결국 최신 상태가 아니게 되며, Microsoft에서 릴리스하는 중요한 버그 수정이나 새로운 기능을 받지 못할 수 있습니다.

Intune 회사 포털을 승인하려면 다음 단계를 따르세요.

1.  [관리되는 Google Play 스토어](https://play.google.com/work/apps/details?id=com.microsoft.windowsintune.companyportal)에서 회사 포털 앱을 다운로드합니다.
2.  Android for Work에 대한 바인딩을 구성하는 데 사용한 것과 동일한 Google 계정으로 관리되는 Google Play 스토어에 로그인합니다.
3.  **승인**을 클릭합니다.  새 대화 상자가 열립니다.
4.  이 대화 상자에서 권한을 검토하고 **승인**을 클릭합니다. 회사 포털 앱이 장치의 회사 프로필을 관리할 수 있게 하려면 이러한 권한을 허용해야 합니다.
5.  **앱이 새 권한을 요청할 때 승인 유지**를 선택하고 **저장**을 클릭합니다.

<!--  ## Next steps for Android for Work
After configuring the Android for Work binding and settings, you can do the following:
- [Deploy Android for Work apps](android-for-work-apps.md)
- [Add Android for Work configuration policies](android-for-work-policy-settings-in-microsoft-intune.md)  -->

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>회사 리소스에 액세스할 수 있도록 사용자에게 장치를 등록하는 방법 설명

사용자에게 Google Play로 이동하여 Intune 회사 포털 앱을 다운로드한 후 앱을 열고 안내 메시지에 따라 장치를 등록하도록 알립니다. 앱에서 예상되는 작업 내용과 IT 관리자가 장치에서 볼 수 있는 항목과 볼 수 없는 항목을 등록 과정 중에 안내합니다.

또한 온라인 등록 단계: [Intune에서 Android 장치 등록](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android)에 대한 링크를 최종 사용자에게 전송할 수 있습니다.

다른 사용자 작업에 대한 정보는 다음 문서를 참조하세요.

- [Microsoft Intune에서 최종 사용자 환경 관련 리소스](end-user-educate.md)
- [Intune에서 Android 장치 사용](https://docs.microsoft.com/intune-user-help/using-your-android-device-with-intune)

## <a name="unbind-your-android-for-work-administrative-account"></a>Android for Work 관리 계정 바인딩 해제

Android for Work 등록 및 관리를 해제할 수 있습니다. Intune 관리 콘솔에서 **바인딩 해제**를 선택하면 등록된 모든 Android for Work 장치가 등록에서 제거됩니다. Android for Work 계정과 Intune 사이의 관계도 제거됩니다.

### <a name="to-unbind-an-android-for-work-account"></a>Android for Work 계정 바인딩 해제하려면

1. **Android for Work 바인딩에 대한 바인딩 해제**<br>
    Azure Portal에서 Intune 관리자로 **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.  **Intune** 블레이드에서 **장치 등록** > **Android for Work 등록**을 선택한 다음 **바인딩 해제**를 선택합니다.

2. **Android for Work 바인딩 삭제 동의**<br>
  바인딩을 삭제하고 Intune에서 Android for Work를 모두 등록 해제하려면 **예**를 선택합니다.
