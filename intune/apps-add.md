---
title: "Microsoft Intune에 앱을 추가하는 방법"
titleSuffix: Intune on Azure
description: "사용자 및 장치에 할당할 준비가 된 앱을 Intune으로 가져오는 절차를 설명합니다. \""
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/17/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1ded457-0ecf-4f9c-a2d2-857d57f8d30a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 14f2ac5b25cfe3e688363a21775872baaa9ff89a
ms.sourcegitcommit: 4034ac474bfed358270a32459a2cf2fe02f44e45
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2017
---
# <a name="how-to-add-an-app-to-microsoft-intune"></a>Microsoft Intune에 앱을 추가하는 방법

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

사용자를 위해 앱을 관리하고 할당하려면 먼저 해당 앱을 Intune에 추가해야 합니다. Intune에서는 다양한 유형의 앱을 지원하며 각 유형마다 옵션이 다를 수 있습니다.

Intune을 사용하여 다음 앱 유형을 추가하고 지정할 수 있습니다.

![Intune에서 지원하는 앱 유형](./media/app-types.png)

지원되는 플랫폼은 다음과 같습니다.

- Android 스토어 앱
- Android LOB(기간 업무) 앱
- iOS 스토어 앱
- iOS LOB(기간 업무) 앱
- 웹앱
- Windows Phone 8.1 스토어 앱
- Windows Phone LOB(기간 업무) 앱(.xap 파일)
- Windows 스토어 앱
- Windows LOB(기간 업무) 앱(.msi 파일)

>[!TIP]
> 기간 업무(또는 LOB) 앱은 앱 스토어에서 설치하는 것이 아니라 앱 설치 파일에서 설치하는 앱입니다. 예를 들어 iOS LOB 앱을 설치하려면 응용 프로그램 보관 파일(확장명: .ipa)을 추가합니다. 일반적으로 이러한 앱은 사내에서 작성한 앱입니다.

## <a name="before-you-start"></a>시작하기 전에

앱을 추가하고 할당하기 전에 다음 사항을 고려해야 합니다.

- 스토어에서 앱을 추가하고 할당하는 경우 앱을 설치할 수 있도록 최종 사용자에게 해당 스토어의 계정이 있어야 합니다.
- 할당한 앱 또는 항목 중 일부는 기본 제공 iOS 앱에 종속될 수 있습니다. 예를 들어 iOS 스토어에서 책을 할당하는 경우 iBooks 앱은 장치에 있어야 합니다. iBooks 기본 제공 앱을 제거한 경우에는 Intune을 사용하여 복구할 수 없습니다.

## <a name="cloud-storage-space"></a>클라우드 저장소 공간
소프트웨어 설치 관리자 설치 유형(예: 기간 업무 앱)을 사용하여 만든 모든 앱은 패키징된 후 Intune 클라우드 저장소로 업로드됩니다. Intune의 평가판 구독에는 관리 앱 및 업데이트를 저장하는 데 사용되는 클라우드 기반의 2GB 저장소가 포함됩니다. 전체 구독에는 20GB의 저장소 공간이 포함됩니다.

원래 구매 방법을 사용하여 Intune용 저장소를 추가로 구입할 수 있습니다.  청구서 또는 신용 카드로 지불한 경우 [구독 관리 포털](https://portal.office.com/adminportal/home?switchtomodern=true#/subscriptions)을 참조하세요.  그 외의 경우에는 파트너나 영업 사원에게 문의하세요.

클라우드 저장소 공간에 대한 요구 사항은 다음과 같습니다.

-   모든 앱 설치 파일이 같은 폴더 내에 있어야 합니다.
-   업로드하는 파일의 최대 파일 크기는 2GB입니다.

## <a name="how-to-create-and-edit-categories-for-apps"></a>앱의 범주를 만들고 편집하는 방법

앱 범주를 사용하여 사용자가 회사 포털에서 보다 쉽게 찾을 수 있도록 앱을 정렬할 수 있습니다. 하나 이상의 범주(예: **개발자 앱**, 또는 **통신 앱**)를 앱에 할당할 수 있습니다.
Intune에 앱을 추가하는 경우 원하는 범주를 선택할 수 있는 옵션이 제공됩니다. 플랫폼 관련 항목을 사용하여 앱을 추하고 범주를 할당합니다. 사용자 고유의 범주를 만들고 편집하려면 다음 절차를 사용합니다.

1. Azure 포털에 로그인합니다.
2. **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
3. **Intune** 블레이드에서 **Mobile Apps**를 선택합니다.
4. **모바일 앱** 워크로드에서 **설정** > **앱 범주**를 선택합니다.
5. **앱 범주** 블레이드에 현재 범주 목록이 표시됩니다. 다음 작업 중 하나를 선택합니다.
    - **범주 만들기** - **범주 만들기** 블레이드에서 새 범주의 이름을 입력합니다. 이름은 하나의 언어로만 입력할 수 있으며, Intune에서 번역되지 않습니다. 완료되면 **만들기**를 클릭합니다.
    - **범주 편집** - 목록의 범주에 대해 '**...**'를 선택합니다. **속성** 블레이드에서 범주의 새 이름을 입력하거나 범주를 삭제할 수 있습니다.


## <a name="apps-added-automatically-by-intune"></a>Intune에서 자동으로 추가된 앱

이전에는 Intune에 신속하게 할당할 수 있는 많은 기본 제공 앱이 포함되어 있었습니다. 사용자 의견에 따라 이 목록은 제거되었으며 더 이상 기본 제공 앱은 표시되지 않습니다.
그러나 이미 기본 제공 앱을 할당한 경우 이러한 앱은 여전히 앱 목록에 표시됩니다. 필요에 따라 이러한 앱을 계속 할당할 수 있습니다.
이후 릴리스에서, Intune 포털에서 기본 제공 앱을 더 쉽게 선택하고 할당하는 방법이 추가될 예정입니다.

## <a name="next-steps"></a>다음 단계

각 플랫폼용 앱을 Intune에 추가하는 방법을 알아보려면 다음 항목 중 하나를 선택합니다.

- [Android 스토어 앱](store-apps-android.md)
- [Android LOB 앱](lob-apps-android.md)
- [iOS 스토어 앱](store-apps-ios.md)
- [iOS LOB 앱](lob-apps-ios.md)
- [웹앱(모든 플랫폼)](web-app.md)
- [Windows Phone 8.1 스토어 앱](store-apps-windows-phone-8-1.md)
- [Windows Phone LOB 앱](lob-apps-windows-phone.md)
- [Windows 스토어 앱](store-apps-windows.md)
- [Windows LOB 앱](lob-apps-windows.md)
- [Windows 10용 Office 365 앱](apps-add-office365.md)

