---
title: "Intune에서 macOS 장치 등록 | Intune Azure 미리 보기 | Microsoft 문서"
description: "Intune Azure 미리 보기: Intune Azure 미리 보기에서 macOS 장치를 등록하는 방법을 알아봅니다."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 46429114-2e26-4ba7-aa21-b2b1a5643e01
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a2e840797c06322b9efc59438e0675e57b7cdb24
ms.openlocfilehash: f217988313debd33bcba3f8168aa03b6dbf8586e
ms.lasthandoff: 02/14/2017


---

# <a name="enroll-macos-devices-in-intune-azure-preview"></a>Intune Azure 미리 보기에서 macOS 장치 등록

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Intune을 통해 macOS 장치를 관리할 수 있습니다. 장치 관리를 사용하려면 사용자가 [회사 포털 웹 사이트](http://portal.manage.microsoft.com)로 이동하여 장치를 등록하고 메시지를 따라야 합니다. macOS 장치가 관리 상태에 있으면 [macOS 장치에 대한 사용자 지정 설정을 만들](https://docs.microsoft.com/intune-azure/configure-devices/custom-for-macos) 수 있습니다. 더 많은 기능이 곧 제공됩니다.

## <a name="prerequisites"></a>전제 조건

macOS 장치 등록을 설정하기 전에 다음 필수 구성 요소를 완료합니다.

- [도메인 구성](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2)
- [MDM 기관 설정](set-mdm-authority.md)
- [그룹 만들기](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [회사 포털 구성](/intune-azure/manage-apps/company-portal-app.md)
- [Office 365 포털](http://go.microsoft.com/fwlink/p/?LinkId=698854)에서 사용자 라이선스 할당
- [Apple MDM Push Certificate 가져오기](get-an-apple-mdm-push-certificate.md)

## <a name="set-up-macos-enrollment"></a>macOS 등록 설정

기본적으로 Intune에서는 이미 macOS 장치 등록을 허용합니다. 

등록에서 macOS 장치를 차단하려면 [Set device type restrictions](https://docs.microsoft.com/intune-azure/enroll-devices/set-enrollment-restrictions#set-device-type-restrictions)(장치 유형 제한 설정)를 참조하세요. 

사용자가 등록할 수 있는 장치의 최대 수를 설정하려면 [Set device limit restrictions](https://docs.microsoft.com/intune-azure/enroll-devices/set-enrollment-restrictions#set-device-limit-restrictions)(장치 제한 한도 설정)를 참조하세요.

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>회사 리소스에 액세스할 수 있도록 사용자에게 장치를 등록하는 방법 설명

최종 사용자에게 [회사 포털 웹 사이트](http://portal.manage.microsoft.com)로 가서 메시지를 따라 장치를 등록하도록 알려줘야 합니다. 또한 온라인 등록 단계: [macOS Intune에서 장치 등록](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-macos)에 대한 링크를 최종 사용자에게 전송할 수 있습니다. 

최종 사용자의 다른 작업에 대한 정보는 다음 문서를 참조하세요.

- [Microsoft Intune에서 최종 사용자 환경 관련 리소스](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune)
- [Intune에서 iOS 또는 macOS 장치 사용](https://docs.microsoft.com/intune/enduser/using-your-ios-or-mac-os-x-device-with-intune)
