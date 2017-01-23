---
title: "MAM 정책용 Azure Portal | Microsoft 문서"
description: "Azure Portal을 사용하여 모바일 앱 관리 정책을 만듭니다. 여기에서 만든 정책은 Intune에 등록되었거나 등록되지 않은 장치에 적용할 수 있습니다."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7d6dae94-a833-40b7-9016-14ea234bb33c
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: fe44466fbcef67d02b16d3d2d335f657251451d3
ms.openlocfilehash: fa8d839da1cf0b2d207edc0b28de8a714ba0df02


---

# <a name="azure-portal-for-microsoft-intune-mam-policies"></a>Microsoft Intune MAM 정책용 Azure 포털

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Azure Portal은 MAM(모바일 앱 관리) 정책을 만들고 관리하는 데 사용됩니다.

- 장치에서 실행되는 앱 중에서 **Intune에서 등록하고 관리하는** 앱

- 장치에서 실행되는 앱을 모든 MDM 솔루션에 **등록하지 않음**.
- 장치에서 실행되는 앱 중에서 **타사 MDM 솔루션에 등록된 앱**.

>[!IMPORTANT]
> Azure Portal은 MAM 정책을 만들 수 있는 새로운 관리 콘솔이지만 MDM 시나리오에서 [Intune 관리 콘솔](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md)을 사용하여 Intune에 등록된 장치의 앱을 지원하는 MAM 정책을 만들 수도 있습니다.

> Intune 관리 콘솔에서 사용할 수 있는 MAM 정책 설정이 일부 나타나지 않을 수도 있습니다. 또한 Intune 관리 콘솔과 Azure 포털 둘 다에서 MAM 정책을 만들 경우 Azure 포털에서 만든 정책이 Intune 관리 콘솔에서 만든 정책을 재정의합니다. 이 시나리오에서는 Azure 포털 MAM 정책이 앱에 적용되어 사용자에게 배포됩니다.


## <a name="sign-in-to-the-azure-portal-and-customize-your-start-page"></a>Azure 포털에 로그인하고 시작 페이지를 사용자 지정합니다.

1.  [Azure Portal](https://portal.azure.com)로 이동한 다음 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] 자격 증명을 사용하여 로그인합니다.

    ![Azure Portal 로그인 페이지의 스크린 샷](../media/AppManagement/AzurePortal_MAMSigninPage.png)

2.  성공적으로 등록하면 **대시보드**가 나타납니다. **대시보드** 페이지를 사용자 지정할 수 있습니다.

    ![Azure 포털 대시보드의 스크린 샷](../media/AppManagement/AzurePortal_MAMStartboard_NoMAM.png)

3.  **찾아보기** 메뉴에서 **Intune**을 찾습니다.

    ![Intune이 강조 표시된 찾아보기 메뉴의 스크린샷](../media/AppManagement/MAM-Azure-Portal-1.png)

4.  **Intune** > **Intune 모바일 응용 프로그램 관리** > **설정**을 선택합니다.

    ![Intune 모바일 응용 프로그램 관리 블레이드의 스크린 샷](../media/AppManagement/MAM-Azure-Portal-2.png)

5. (선택 사항)**시작** 페이지에 블레이드를 고정하려면 블레이드의 **고정** 옵션을 사용합니다. **Intune 모바일 응용 프로그램 관리 블레이드**의 고정 아이콘을 클릭하여 **시작** 페이지에 고정합니다.

    ![강조 표시된 핀 아이콘이 있는 Intune 모바일 응용 프로그램 관리 블레이드의 스크린 샷](../media/AppManagement/AzurePortal_MAM_PinBladeAction.png)

    ![고정된 Intune 타일이 있는 대시보드의 스크린 샷](../media/AppManagement/AzurePortal_MAM_Startboard_withMAM.png)

## <a name="next-steps"></a>다음 단계
[모바일 앱 관리 정책 구성 준비](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Jan17_HO2-->


