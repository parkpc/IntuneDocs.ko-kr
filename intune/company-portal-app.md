---
title: "회사 포털 앱을 구성하는 방법"
titleSuffix: Microsoft Intune
description: "Intune 회사 포털 앱에 회사별 브랜딩을 적용할 수 있는 방법을 알아봅니다."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/01/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dec6f258-ee1b-4824-bf66-29053051a1ae
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: cd876739fb0f3ad6d2e0fea705825a26ebc9fe03
ms.sourcegitcommit: aafed032492c1b5861d7097a335f9bbb29ce3221
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2018
---
# <a name="how-to-configure-the-microsoft-intune-company-portal-app"></a>Microsoft Intune 회사 포털 앱을 구성하는 방법

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Microsoft Intune 회사 포털에서 사용자는 회사 데이터에 액세스하고 장치 등록, 앱 설치, IT 부서 지원 정보 찾기 등의 일반적인 작업을 수행할 수 있습니다.        

> [!Tip]        
> 회사 포털을 사용자 지정할 때는 구성이 회사 포털 웹 사이트 및 회사 포털 앱에 모두 적용됩니다.       

회사 포털을 사용자 지정하면 최종 사용자에게 친숙하고 유용한 환경을 제공하는 데 도움이 됩니다. 이렇게 하려면 **Mobile Apps** 작업에서 **설정** > **회사 포털 브랜딩**을 선택한 다음 필요한 설정을 구성합니다.      

## <a name="company-contact-information-and-privacy-statement"></a>회사 연락처 정보 및 개인정보취급방침        
회사 이름은 회사 포털의 제목으로 표시됩니다. 연락처 정보 및 세부 정보는 회사 포털의 **IT 담당자** 화면에서 사용자에게 표시됩니다. 개인정보취급방침은 사용자가 개인정보취급방침 링크를 클릭하면 표시됩니다.        


|필드 이름|최대 길이|추가 정보|        
|-|-|-|     
|**회사 이름**|40|이 이름은 회사 포털의 제목으로 표시됩니다.|        
|**IT 부서 연락처 이름**|40|이 이름은 **IT 담당자** 페이지에 표시됩니다.|      
|**IT 부서 전화 번호**|20|이 연락처 번호는 **IT 담당자** 페이지에 표시됩니다.|        
|IT 부서 전자 메일 주소|40|이 연락처 주소는 **IT 담당자** 페이지에 표시됩니다. 유효한 메일 주소를 **alias@domainname.com** 형식으로 입력해야 합니다.|     
|**추가 정보**|120|**IT 담당자** 페이지에 표시됩니다.|      
|**회사 개인정보취급방침 URL**|79|사용자가 회사 포털에서 개인정보취급방침 링크를 클릭할 때 표시되는 회사 개인정보취급방침을 지정할 수 있습니다. **https://www.contoso.com** 형식의 올바른 URL을 입력해야 합니다.|        

## <a name="support-contacts"></a>지원 연락처     
지원 웹 사이트가 회사 포털의 사용자에게 표시되어, 온라인 지원에 액세스할 수 있도록 합니다.        



|필드 이름|최대 길이|추가 정보|        
|-|-|-|     
|**지원 웹 사이트 URL**|150|최종 사용자가 사용할 지원 웹 사이트가 있는 경우 여기에서 URL을 지정합니다. URL은 **https://www.contoso.com** 형식이어야 합니다. URL을 지정하지 않으면 회사 포털의 **IT 담당자** 페이지에서 지원 웹 사이트에 대해 아무 내용도 표시되지 않습니다.|        
|**지원 웹 사이트 이름**|40|이 이름은 지원 웹 사이트의 URL에 대해 표시되는 식별 이름입니다. 지원 웹 사이트 URL을 지정하고 식별 이름을 지정하지 않으면 IT 웹 사이트로 이동이 회사 포털의 **IT 담당자** 페이지에 표시됩니다.       

## <a name="company-branding-customization"></a>회사 브랜딩 사용자 지정       
회사 로고, 회사 이름, 테마 색 및 배경으로 회사 포털을 사용자 지정할 수 있습니다.     



|필드 이름|추가 정보|       
|-|-|       
|**테마 색**|회사 포털에 적용할 테마 색을 선택합니다.|      
|**회사 로고 표시**|이 옵션을 설정한 경우 회사 포털에서 표시할 회사 로고를 업로드할 수 있습니다. 회사 포털 배경이 흰색인 경우에 표시되는 로고 하나와 회사 포털 배경이 직접 선택한 테마 색을 사용하는 경우에 표시되는 로고 하나, 두 개의 로고를 업로드할 수 있습니다. 각 로고는 .png 또는 .jpg 파일 형식이어야 하며 최대 해상도가 400 x 100픽셀이고 크기가 750KB 이하여야 합니다.<br>업로드된 로고 옆에 입력한 회사 이름을 표시할 수도 있습니다.|      

변경 내용을 저장한 후 **Intune 웹 포털에서 설정을 미리 봅니다.**를 선택하여 구성의 모양을 확인할 수 있습니다.
