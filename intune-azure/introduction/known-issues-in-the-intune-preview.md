---
title: "Microsoft Intune 미리 보기의 알려진 문제"
titleSuffix: Intune Azure preview
description: "Intune Azure 미리 보기: 미리 보기의 알려진 문제를 알아봅니다."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/06/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33a6645-a57e-4424-a1e9-0ce932ea83c5
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: b6c245d60c661c04b4c4d29c9bdcdd752254d978
ms.openlocfilehash: ec3f87994b19591bda4ec201eac3c839798d634c
ms.lasthandoff: 03/15/2017


---

# <a name="known-issues-in-the-microsoft-intune-preview"></a>Microsoft Intune 미리 보기의 알려진 문제


[!INCLUDE[azure_preview](../includes/azure_preview.md)]


이 항목을 사용하여 Intune 미리 보기의 알려진 문제를 파악할 수 있습니다.

여기에 나열되지 않은 버그를 보고하려면 [지원 요청을 시작](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune)하세요.

Intune에 추가할 새로운 기능을 요청하려면 [Uservoice](https://microsoftintune.uservoice.com/forums/291681-ideas/category/189016-azure-admin-console) 사이트에서 보고서를 제출하는 것이 좋습니다.

## <a name="administration-and-accounts"></a>관리 및 계정

- 전역 관리자(테넌트 관리자라고도 함)는 별도의 Intune 또는 EMS(Enterprise Mobility Suite) 라이선스 없이 일상적인 관리 작업을 계속 수행할 수 있습니다. 그러나 전역 관리자가 자신의 장치나 회사 장치 등록 또는 Intune 회사 포털 사용 등의 서비스를 사용하려는 경우 다른 사용자와 마찬가지로 Intune 또는 EMS 라이선스가 필요합니다.

## <a name="apple-enrollment-profile-migration"></a>Apple 등록 프로필 마이그레이션
- 앞으로 몇 달 후에 Intune은 새 Azure Portal을 통한 Apple 장비 등록 프로그램 및 Apple Configurator 등록 관리를 활성화합니다. Apple 장비 등록 프로그램 토큰을 삭제하고 업데이트된 토큰을 업로드하지 않는 경우 Intune 계정 마이그레이션의 일부로 원래 토큰이 새 Azure Portal에서 복원됩니다. 이 토큰을 제거하고 DEP 등록을 방지하려면 Azure Portal에서 토큰을 삭제하기만 하면 됩니다. 

