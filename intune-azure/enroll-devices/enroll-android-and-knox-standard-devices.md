---
title: "Intune에서 Android 장치 등록 | Intune Azure 미리 보기 | Microsoft 문서"
description: "Intune Azure 미리 보기: Intune Azure 미리 보기에서 Android 장치를 등록하는 방법을 알아봅니다."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 08dad848a48adad7d9c6f0b5b3286f6550a266bd
ms.openlocfilehash: 99b790e33843efcf83a4687490b186a6e174bd81
ms.lasthandoff: 02/15/2017


---

# <a name="enroll-android-devices"></a>Android 장치 등록

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Intune을 사용하면 Samsung Knox 표준 장치를 비롯하여 Android 장치를 관리할 수 있습니다. 장치 관리를 사용하려면 사용자가 Google Play에서 사용할 수 있는 Intune 회사 포털 앱을 다운로드한 다음 앱을 열고 메시지를 따라 등록하여 자신의 장치를 등록해야 합니다. Android 장치가 관리 상태에 있으면 [호환성 정책을 만들고](https://docs.microsoft.com/intune-azure/set-device-compliance/create-a-compliance-policy-for-android), [앱을 관리](https://docs.microsoft.com/intune-azure/manage-apps/what-is-app-management)하는 등의 작업을 할 수 있습니다.

## <a name="prerequisite"></a>필수 구성 요소

모바일 장치 관리를 준비하려면 MDM 기관을 **Microsoft Intune**으로 설정해야 합니다. 지침은 [MDM 기관 설정](set-mdm-authority.md)을 참조하세요. 이 항목은 모바일 장치 관리에 대해 Intune을 처음 설정할 때 한 번만 설정하면 되므로 이미 설정했을 수 있습니다. 

## <a name="set-up-android-enrollment"></a>Android 등록 설정

기본적으로 Intune에서는 이미 Android 및 Samsung Knox Standard 장치 등록을 허용합니다. 

Android 장치를 차단하거나 등록에서 개인적으로 소유한 Android 장치를 차단하려면 [장치 유형 제한 설정](https://docs.microsoft.com/intune-azure/enroll-devices/set-enrollment-restrictions#set-device-type-restrictions)을 참조하세요. 

사용자가 등록할 수 있는 장치의 최대 수를 설정하려면 [Set device limit restrictions](https://docs.microsoft.com/intune-azure/enroll-devices/set-enrollment-restrictions#set-device-limit-restrictions)(장치 제한 한도 설정)를 참조하세요.

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>회사 리소스에 액세스할 수 있도록 사용자에게 장치를 등록하는 방법 설명

최종 사용자에게 Google Play로 이동하여 Intune 회사 포털 앱을 다운로드한 후 앱을 열고 메시지를 따라 장치를 등록하도록 알려야 합니다. 앱에서 예상되는 작업 내용과 IT 관리자가 장치에서 볼 수 있는 항목과 볼 수 없는 항목을 등록 과정 중에 안내합니다.

또한 온라인 등록 단계: [Intune에서 Android 장치 등록](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-android)에 대한 링크를 최종 사용자에게 전송할 수 있습니다. 

최종 사용자의 다른 작업에 대한 정보는 다음 문서를 참조하세요.

- [Microsoft Intune에서 최종 사용자 환경 관련 리소스](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune)
- [Intune에서 Android 장치 사용](https://docs.microsoft.com/intune/enduser/using-your-android-device-with-intune)
