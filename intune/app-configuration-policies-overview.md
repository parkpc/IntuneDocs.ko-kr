---
title: "Intune용 구성 정책 추가 | Microsoft Docs"
titlesuffix: Azure portal
description: "Intune용 앱 구성 정책을 사용하는 방법에 대해 알아봅니다."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 834B4557-80A9-48C0-A72C-C98F6AF79708
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b690f691278d0cc708ed7e586e30aee4ed6e807a
ms.sourcegitcommit: 67c037af31c1f167ec9b4f4baa754631c817e7d1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2017
---
# <a name="app-configuration-policies-for-intune"></a>Intune용 앱 구성 정책

Microsoft Intune에서 앱 구성 정책을 사용하여 사용자가 iOS 또는 Android 앱을 실행할 때 설정을 제공합니다. 예를 들어 사용자가 앱에서 다음 사항을 지정해야 할 수 있습니다.

- 사용자 지정 포트 번호
- 언어 설정
- 보안 설정
- 회사 로고와 같은 브랜딩 설정

사용자가 이러한 설정을 잘못 입력하면 기술 지원팀의 부담이 증가하며 새 앱 도입이 지연될 수 있습니다.

앱 구성 정책을 사용하는 경우 사용자가 앱을 실행하기 전에 정책에서 이러한 설정을 사용자에게 할당할 수 있으므로 이러한 문제를 방지할 수 있습니다. 배포한 설정은 자동으로 제공되므로 사용자가 아무런 작업을 수행하지 않아도 됩니다.

사용자 및 장치에 이러한 정책을 직접 할당하지는 않으며, 대신 앱에 정책을 연결한 다음 앱을 할당합니다. 정책 설정은 앱에서 해당 설정을 확인할 때마다(일반적으로는 앱을 처음 실행할 때) 사용됩니다.

Intune을 사용한 앱 구성을 사용하는 방법에는 두 가지 옵션이 있습니다.
 - **관리되는 장치**  
   장치는 MDM 공급자로 Intune에서 관리됩니다.
 - **관리되는 앱**  
   앱이 장치 등록 없이 관리됩니다.

## <a name="apps-that-support-app-configuration"></a>앱 구성을 지원하는 앱

앱 구성 정책을 지원하는 앱에서 해당 정책을 사용할 수 있습니다. Intune에서 앱 구성을 지원하려면 앱 구성 사용을 지원하도록 앱을 작성해야 합니다. 자세한 내용은 앱 공급업체에 문의하세요.

Intune 앱 SDK를 앱에 통합하거나 앱이 개발된 후 앱을 래핑하여 기간 업무 앱을 준비할 수 있습니다. iOS와 Android 둘 다에 사용할 수 있는 Intune 앱 SDK를 통해 앱을 앱 보호 정책에 사용할 수 있도록 설정할 수 있습니다. Intune 앱 SDK는 앱 개발자에게서 필요한 코드 변경의 양을 최소화하려고 합니다. 자세한 내용은 [Intune 앱 SDK 개요](app-sdk.md)를 참조하세요.

## <a name="graph-api-support-for-app-configuration"></a>앱 구성에 대한 Graph API 지원

또한 Graph API를 사용하여 앱 구성 작업을 수행할 수 있습니다. 자세한 내용은 [Graph API Reference MAM Targeted Config](https://graph.microsoft.io/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create)(Graph API 참조 MAM 대상 구성)를 참조하세요.

## <a name="next-steps"></a>다음 단계

### <a name="managed-devices"></a>관리되는 장치

 - iOS 장치로 앱 구성을 사용하는 방법을 알아봅니다.  [관리되는 iOS 장치용 앱 구성 정책 추가](app-configuration-policies-use-ios.md)를 참조하세요.
 - Android 장치로 앱 구성을 사용하는 방법을 알아봅니다.  [관리되는 Android 장치용 앱 구성 정책 추가](app-configuration-policies-use-android.md)를 참조하세요.

### <a name="managed-apps"></a>관리되는 앱

 - 관리되는 앱으로 앱 구성을 사용하는 방법을 알아봅니다. [장치 등록 없이 관리되는 앱용 앱 구성 정책 추가](app-configuration-policies-managed-app.md)를 참조하세요.