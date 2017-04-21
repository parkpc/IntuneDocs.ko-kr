---
title: "Microsoft Intune 미리 보기의 알려진 문제"
titleSuffix: Intune Azure preview
description: "Intune Azure 미리 보기: 미리 보기의 알려진 문제를 알아봅니다."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/13/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33a6645-a57e-4424-a1e9-0ce932ea83c5
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 24498abc504f05bd22dc7309bc22948292f9b1e6
ms.openlocfilehash: 4c81c17ba1419f0b5bdc4910be7d26a5893b32e0
ms.lasthandoff: 04/13/2017


---

# <a name="known-issues-in-the-microsoft-intune-preview"></a>Microsoft Intune 미리 보기의 알려진 문제


[!INCLUDE[azure_preview](../includes/azure_preview.md)]


이 항목을 사용하여 Intune 미리 보기의 알려진 문제를 파악할 수 있습니다.

여기에 나열되지 않은 버그를 보고하려면 [지원 요청을 시작](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune)하세요.

Intune에 추가할 새로운 기능을 요청하려면 [Uservoice](https://microsoftintune.uservoice.com/forums/291681-ideas/category/189016-azure-admin-console) 사이트에서 보고서를 제출하는 것이 좋습니다.

## <a name="groups-created-by-intune-during-migration-might-affect-functionality-of-other-microsoft-products"></a>마이그레이션 도중 Intune이 만든 그룹은 다른 Microsoft 제품의 기능에 영향을 줄 수 있습니다.

클래식 Intune에서 Azure Portal로 마이그레이션할 때 **All Users - b0b08746-4dbe-4a37-9adf-9e7652c0b421**이라는 이름의 새 그룹이 보일 수 있습니다. 이 그룹에는 Intune의 사용이 허가된 사용자뿐만 아니라 Azure Active Directory의 모든 사용자도 포함됩니다. 일부 기존 또는 새로운 사용자가 어떤 그룹의 멤버도 아니라면 다른 Microsoft 제품과 문제가 발생할 수 있습니다.

## <a name="altering-groups-created-by-intune-during-migration-will-delay-migration"></a>마이그레이션 중에 Intune에서 만든 그룹을 변경하면 마이그레이션이 지연됩니다.

마이그레이션을 준비하기 위하여 그룹이 Intune에서 Azure AD로 복사됩니다. 클래식 Intune 포털에서 추가적으로 변경한 모든 내용은 Azure AD 그룹에 업데이트됩니다. 그러나 Azure AD에서 변경한 내용은 클래식 Intune 콘솔에 다시 동기화되지 않습니다. 이는 Azure Portal로의 마이그레이션 실패와 마이그레이션 지연이라는 결과를 가져올 수 있습니다.

## <a name="compliance-policies-from-intune-will-not-show-up-in-new-console"></a>Intune의 규정 준수 정책은 새 콘솔에 표시되지 않습니다. 

클래식 Intune 포털에서 만든 모든 규정 준수 정책이 마이그레이션되지만 Azure Portal에 표시되지는 않습니다. 이는 Azure Portal의 디자인이 변경되었기 때문입니다. 클래식 Intune 포털에서 만든 규정 준수 정책이 계속 적용되지만 클래식 포털에서 보고 편집해야 합니다.
또한 Azure Portal에서 만든 새 규정 준수 정책은 클래식 포털에서는 보이지 않습니다.
자세한 내용은 [장치 준수](https://docs.microsoft.com/intune-azure/set-device-compliance/what-is-device-compliance)를 참조하세요.




## <a name="administration-and-accounts"></a>관리 및 계정

전역 관리자(테넌트 관리자라고도 함)는 별도의 Intune 또는 EMS(Enterprise Mobility Suite) 라이선스 없이 일상적인 관리 작업을 계속 수행할 수 있습니다. 그러나 전역 관리자가 자신의 장치나 회사 장치 등록 또는 Intune 회사 포털 사용 등의 서비스를 사용하려는 경우 다른 사용자와 마찬가지로 Intune 또는 EMS 라이선스가 필요합니다.

## <a name="apple-enrollment-profile-migration"></a>Apple 등록 프로필 마이그레이션
앞으로 몇 달 후에 Intune은 새 Azure Portal을 통한 Apple 장비 등록 프로그램 및 Apple Configurator 등록 관리를 활성화합니다. Apple 장비 등록 프로그램 토큰을 삭제하고 업데이트된 토큰을 업로드하지 않는 경우 Intune 계정 마이그레이션의 일부로 원래 토큰이 새 Azure Portal에서 복원됩니다. 이 토큰을 제거하고 DEP 등록을 방지하려면 Azure Portal에서 토큰을 삭제하기만 하면 됩니다. 

