---
title: "Intune에서 macOS 장치 등록 | Intune Azure 미리 보기 | Microsoft 문서"
description: "Intune Azure 미리 보기: Intune Azure 미리 보기에서 macOS 장치를 등록하는 방법을 알아봅니다."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 1/3/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 46429114-2e26-4ba7-aa21-b2b1a5643e01
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ba2affcdbcdfcd690d671c7b20f9d1e14a74f764
ms.openlocfilehash: 171175689adca027181f3da4d05222117de97e13


---

# <a name="enroll-macos-devices-in-intune-azure-preview"></a>Intune Azure 미리 보기에서 macOS 장치 등록

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Intune 관리자는 macOS 장치를 관리할 수 있습니다. 기본적으로 Azure Portal에서 사용자는 macOS 장치를 등록할 수 있습니다. [회사 포털 웹 사이트](http://portal.manage.microsoft.com)로 이동하여 macOS 장치를 등록하기만 하면 됩니다. 

## <a name="prerequisites"></a>전제 조건

macOS 장치 등록을 설정하기 전에 다음 필수 구성 요소를 완료합니다.

- [도메인 구성](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2)
- [MDM 기관 설정](set-mdm-authority.md)
- [그룹 만들기](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [회사 포털 구성](/intune-azure/manage-apps/company-portal-app.md)
- [Office 365 포털](http://go.microsoft.com/fwlink/p/?LinkId=698854)에서 사용자 라이선스 할당
- [Apple MDM Push Certificate 가져오기](get-an-apple-mdm-push-certificate.md)

## <a name="set-up-macos-enrollment"></a>macOS 등록 설정

기본적으로 Intune은 이미 macOS 장치를 등록할 수 있도록 설정되어 있습니다. 

macOS 장치의 등록을 허용하거나 차단하는 설정을 확인하려면 Azure Portal에서 Intune 블레이드로 이동하여 **등록** > **등록 제한**을 선택합니다. 

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>회사 리소스에 액세스할 수 있도록 사용자에게 장치를 등록하는 방법 설명

최종 사용자 등록 지침은 [Intune에서 macOS 장치 등록](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-macos)을 참조하세요. 예상되는 작업 내용과 IT 관리자가 장치에서 볼 수 있는 항목과 볼 수 없는 항목을 등록 과정 중에 알려줍니다.

최종 사용자의 다른 작업에 대한 정보는 다음 문서를 참조하세요.

- [Microsoft Intune에서 최종 사용자 환경 관련 리소스](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune)
- [Intune에서 iOS 또는 macOS 장치 사용](https://docs.microsoft.com/intune/enduser/using-your-ios-or-mac-os-x-device-with-intune)


<!--HONumber=Feb17_HO1-->


