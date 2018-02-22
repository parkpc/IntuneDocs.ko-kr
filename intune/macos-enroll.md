---
title: "Intune에 macOS 장치 등록"
titlesuffix: Azure portal
description: "Intune에 macOS 장치를 등록하는 방법을 알아봅니다.\""
keywords: 
author: ErikjeMS
ms.author: erikje
nmanager: dougeby
ms.date: 10/30/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 46429114-2e26-4ba7-aa21-b2b1a5643e01
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f896ebd51f989c0e441043d320247946cdb8997b
ms.sourcegitcommit: 9bd6278d129fa29f184b2d850138f8f65f3674ea
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2018
---
# <a name="enroll-macos-devices-in-intune"></a>Intune에 macOS 장치 등록

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune을 통해 macOS 장치를 관리할 수 있습니다. 장치 관리를 사용하려면 사용자가 [회사 포털 웹 사이트](http://portal.manage.microsoft.com)로 이동하여 장치를 등록하고 메시지를 따라야 합니다. macOS 장치가 관리 상태에 있으면 [macOS 장치에 대한 사용자 지정 설정을 만들](custom-settings-macos.md) 수 있습니다. 더 많은 기능이 곧 제공됩니다.

## <a name="prerequisites"></a>전제 조건

macOS 장치 등록을 설정하기 전에 다음 필수 구성 요소를 완료합니다.

- [도메인 구성](custom-domain-name-configure.md)
- [MDM 기관 설정](mdm-authority-set.md)
- [그룹 만들기](https://docs.microsoft.com/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [회사 포털 구성](company-portal-app.md)
- [Office 365 포털](http://go.microsoft.com/fwlink/p/?LinkId=698854)에서 사용자 라이선스 할당
- [Apple MDM Push Certificate 가져오기](apple-mdm-push-certificate-get.md)

## <a name="set-up-macos-enrollment"></a>macOS 등록 설정

기본적으로 Intune에서는 이미 macOS 장치 등록을 허용합니다.

등록에서 macOS 장치를 차단하려면 [Set device type restrictions](enrollment-restrictions-set.md)(장치 유형 제한 설정)를 참조하세요.

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>회사 리소스에 액세스할 수 있도록 사용자에게 장치를 등록하는 방법 설명

최종 사용자에게 [회사 포털 웹 사이트](http://portal.manage.microsoft.com)로 가서 메시지를 따라 장치를 등록하도록 알립니다. 또한 온라인 등록 단계: [macOS Intune에서 장치 등록](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos)에 대한 링크를 최종 사용자에게 전송할 수 있습니다.

최종 사용자의 다른 작업에 대한 정보는 다음 문서를 참조하세요.

- [Microsoft Intune에서 최종 사용자 환경 관련 리소스](end-user-educate.md)
- [Intune에서 macOS 장치 사용](/intune-user-help/using-your-macos-device-with-intune)
