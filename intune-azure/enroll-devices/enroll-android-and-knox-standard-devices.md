---
title: "Intune에서 Android 장치 등록 | Intune Azure 미리 보기 | Microsoft 문서"
description: "Intune Azure 미리 보기: Intune Azure 미리 보기에서 Android 장치를 등록하는 방법을 알아봅니다."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 12/16/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 990062ecf03a117dad74eb71e3f40abb79f22be6
ms.openlocfilehash: edd6303f3bb05dfff758cbb7d4bd08e21f083998


---

# <a name="enroll-android-devices"></a>Android 장치 등록

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Intune 관리자는 회사 포털에서 Samsung Knox Standard 장치를 포함한 Android 장치를 관리하도록 설정할 수 있습니다. 그러면 사용자가 Google Play에서 제공되는 회사 포털 앱을 사용하여 장치를 등록할 수 있습니다.

## <a name="prerequisite"></a>필수 구성 요소

모바일 장치 관리를 준비하려면 MDM 기관을 **Microsoft Intune**으로 설정해야 합니다. 지침은 [MDM 기관 설정](set-mdm-authority.md)을 참조하세요. 이 항목은 모바일 장치 관리에 대해 Intune을 처음 설정할 때 한 번만 설정하면 되므로 이미 설정했을 수 있습니다. 

## <a name="set-up-android-enrollment"></a>Android 등록 설정

기본적으로 Intune은 Android 및 Samsung Knox Standard 장치 등록을 허용하도록 설정됩니다. 

Android 장치의 등록을 허용하거나 차단하는 설정을 확인하려면 Azure Portal에서 Intune 블레이드로 이동하여 **등록** > **등록 제한**을 선택합니다. 

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>회사 리소스에 액세스할 수 있도록 사용자에게 장치를 등록하는 방법 설명

최종 사용자 등록 지침은 [Intune에서 Android 장치 등록](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-android)을 참조하세요. 예상되는 작업 내용과 IT 관리자가 장치에서 볼 수 있는 항목과 볼 수 없는 항목을 등록 과정 중에 알려줍니다.

최종 사용자의 다른 작업에 대한 정보는 다음 문서를 참조하세요.

- [Microsoft Intune에서 최종 사용자 환경 관련 리소스](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune)
- [Intune에서 Android 장치 사용](https://docs.microsoft.com/intune/enduser/using-your-android-device-with-intune)


<!--HONumber=Feb17_HO1-->


