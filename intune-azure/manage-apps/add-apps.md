---
title: "Microsoft Intune에 앱을 추가하는 방법 | Intune Azure 미리 보기 | Microsoft Docs"
description: "Intune Azure 미리 보기: 이러한 절차를 통해 사용자 및 장치에 할당할 준비가 된 Intune으로 앱을 가져올 수 있습니다. "
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1ded457-0ecf-4f9c-a2d2-857d57f8d30a
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 969ce8deae9142944f3481172277dc252baa5779
ms.openlocfilehash: a7838f57b2eb8bd36a875f7b5b001b12eafcbf8d

---

# <a name="how-to-add-an-app"></a>앱을 추가하는 방법 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

사용자를 위해 앱을 관리하고 할당하려면 먼저 해당 앱을 Intune에 추가해야 합니다. Intune에서는 다양한 유형의 앱을 지원하며 각 유형마다 옵션이 다를 수 있습니다.

Intune에서는 다음과 같은 앱 유형의 추가 및 할당을 지원합니다.

![Intune에서 지원하는 앱 유형](./media/app-types.png)

지원되는 플랫폼은 다음과 같습니다. 각 앱 유형을 추가하는 방법에 대한 자세한 내용을 보려면 항목 중 하나를 클릭하세요.

- [Android 기간 업무 앱](/intune-azure/manage-apps/android-lob-app)
- [Android 스토어 앱](/intune-azure/manage-apps/android-store-app)
- [iOS 기간 업무 앱](/intune-azure/manage-apps/ios-lob-app)
- [iOS 스토어 앱](/intune-azure/manage-apps/ios-store-app)
- [웹앱(모든 플랫폼)](/intune-azure/manage-apps/web-app)
- [Windows Phone 8.1 스토어 앱](/intune-azure/manage-apps/windows-phone-8-1-store-app)
- [Windows 스토어 앱](/intune-azure/manage-apps/windows-store-app)

> [!NOTE]
> 스토어에서 앱을 추가하고 배포하는 경우 앱을 설치할 수 있도록 최종 사용자에게 해당 스토어의 계정이 있어야 합니다.

## <a name="how-to-create-and-edit-categories-for-apps"></a>앱의 범주를 만들고 편집하는 방법 

앱 범주를 사용하여 최종 사용자가 회사 포털에서 보다 쉽게 찾을 수 있도록 앱을 정렬할 수 있습니다. 하나 이상의 범주(예: **개발자 앱**, 또는 **통신 앱**)를 앱에 할당할 수 있습니다. Intune에 앱을 추가하는 경우 원하는 범주를 선택할 수 있는 옵션이 제공됩니다. 플랫폼 관련 항목을 사용하여 앱을 추하고 범주를 할당합니다. 사용자 고유의 범주를 만들고 편집하려면 다음 절차를 사용합니다. 

1. Azure 포털에 로그인합니다. 
2. **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다. 
3. **Intune** 블레이드에서 **앱 관리**를 선택합니다. 
4. **모바일 앱** 워크로드에서 **설정** > **앱 범주**를 선택합니다. 
5. **앱 범주** 블레이드에 현재 범주 목록이 표시됩니다. 다음 작업 중 하나를 선택합니다. 
    - **범주 만들기** - **범주 만들기** 블레이드에서 새 범주의 이름을 입력합니다. 이름은 하나의 언어로만 입력할 수 있으며, Intune에서 번역되지 않습니다. 완료되면 **만들기**를 클릭합니다.
    - **범주 편집** - 목록의 범주에 대해 '**...**'를 선택합니다. **속성** 블레이드에서 범주의 새 이름을 입력하거나 범주를 삭제할 수 있습니다. --->






<!--HONumber=Feb17_HO1-->


