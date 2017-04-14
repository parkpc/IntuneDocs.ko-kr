---
title: "Microsoft Intune에 앱을 추가하는 방법"
titleSuffix: Intune Azure preview
description: "Intune Azure 미리 보기: 이러한 절차를 통해 사용자 및 장치에 할당할 준비가 된 Intune으로 앱을 가져올 수 있습니다. "
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1ded457-0ecf-4f9c-a2d2-857d57f8d30a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: e4a6aaa1a8e23dc2c58345f73ff8db86018843e1
ms.openlocfilehash: fe12a6b890c2d5cba874e820afbe7671b754deb5
ms.lasthandoff: 04/11/2017

---

# <a name="how-to-add-an-app-to-microsoft-intune"></a>Microsoft Intune에 앱을 추가하는 방법

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

사용자를 위해 앱을 관리하고 할당하려면 먼저 해당 앱을 Intune에 추가해야 합니다. Intune에서는 다양한 유형의 앱을 지원하며 각 유형마다 옵션이 다를 수 있습니다.

Intune에서는 다음과 같은 앱 유형의 추가 및 할당을 지원합니다.

![Intune에서 지원하는 앱 유형](./media/app-types.png)

지원되는 플랫폼은 다음과 같습니다. 각 앱 유형을 추가하는 방법에 대한 자세한 내용을 보려면 항목 중 하나를 클릭하세요.

- [Android 스토어 앱](/intune-azure/manage-apps/android-store-app)
- [iOS 스토어 앱](/intune-azure/manage-apps/ios-store-app)
- [웹앱(모든 플랫폼)](/intune-azure/manage-apps/web-app)
- [Windows Phone 8.1 스토어 앱](/intune-azure/manage-apps/windows-phone-8-1-store-app)
- [Windows 스토어 앱](/intune-azure/manage-apps/windows-store-app)

> [!NOTE]
> 스토어에서 앱을 추가하고 배포하는 경우 앱을 설치할 수 있도록 최종 사용자에게 해당 스토어의 계정이 있어야 합니다.

## <a name="cloud-storage-space"></a>클라우드 저장소 공간
소프트웨어 설치 관리자 설치 유형(예: 기간 업무 앱)을 사용하여 만든 모든 앱은 패키징된 후 Microsoft Intune 클라우드 저장소로 업로드됩니다. Intune의 평가판 구독에는 관리 앱 및 업데이트를 저장하는 데 사용되는 클라우드 기반의 2GB 저장소가 포함됩니다. 전체 구독에는 20GB의 저장소 공간이 포함됩니다.

원래 구매 방법을 사용하여 Intune용 저장소를 추가로 구입할 수 있습니다.  청구서 또는 신용 카드로 지불한 경우 [구독 관리 포털](https://portal.office.com/adminportal/home?switchtomodern=true#/subscriptions)을 참조하세요.  그 외의 경우에는 파트너나 영업 사원에게 문의하세요.

클라우드 저장소 공간에 대한 요구 사항은 다음과 같습니다.

-   모든 앱 설치 파일이 같은 폴더 내에 있어야 합니다.
-   업로드하는 파일의 최대 파일 크기는 2GB입니다.

## <a name="how-to-create-and-edit-categories-for-apps"></a>앱의 범주를 만들고 편집하는 방법 

앱 범주를 사용하여 최종 사용자가 회사 포털에서 보다 쉽게 찾을 수 있도록 앱을 정렬할 수 있습니다. 하나 이상의 범주(예: **개발자 앱**, 또는 **통신 앱**)를 앱에 할당할 수 있습니다. Intune에 앱을 추가하는 경우 원하는 범주를 선택할 수 있는 옵션이 제공됩니다. 플랫폼 관련 항목을 사용하여 앱을 추하고 범주를 할당합니다. 사용자 고유의 범주를 만들고 편집하려면 다음 절차를 사용합니다. 

1. Azure 포털에 로그인합니다. 
2. **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다. 
3. **Intune** 블레이드에서 **앱 관리**를 선택합니다. 
4. **모바일 앱** 워크로드에서 **설정** > **앱 범주**를 선택합니다. 
5. **앱 범주** 블레이드에 현재 범주 목록이 표시됩니다. 다음 작업 중 하나를 선택합니다. 
    - **범주 만들기** - **범주 만들기** 블레이드에서 새 범주의 이름을 입력합니다. 이름은 하나의 언어로만 입력할 수 있으며, Intune에서 번역되지 않습니다. 완료되면 **만들기**를 클릭합니다.
    - **범주 편집** - 목록의 범주에 대해 '**...**'를 선택합니다. **속성** 블레이드에서 범주의 새 이름을 입력하거나 범주를 삭제할 수 있습니다.




