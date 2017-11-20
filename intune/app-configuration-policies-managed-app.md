---
title: "장치 등록 없이 관리되는 앱용 앱 구성 정책 추가 | Microsoft Docs"
titlesuffix: Azure portal
description: "장치 등록 없이 관리되는 앱용 앱 구성 정책을 사용하는 방법을 알아봅니다."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: E61C1618-79D0-41A1-B61F-4123FB6672FC
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 750ce7dbb0dccf08757e076826e2d3650b6e6ab5
ms.sourcegitcommit: 67c037af31c1f167ec9b4f4baa754631c817e7d1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2017
---
# <a name="add-app-configuration-policies-for-managed-apps-without-device-enrollment"></a>장치 등록 없이 관리되는 앱용 앱 구성 정책 추가

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

등록되지 않은 장치에도 Intune 앱 SDK를 지원하는 관리되는 앱으로 앱 구성 정책을 사용할 수 있습니다. 

1. Azure Portal에 로그인합니다.
2. **추가 서비스** > **모니터링 + 관리** + **Intune**을 선택합니다.
3. **모바일 앱** 워크로드를 선택합니다.
4. **관리** 그룹에서 **앱 구성 정책**을 선택하고 **추가**를 클릭합니다.
5. 다음 세부 정보를 설정합니다.
    - **Name**  
      Azure Portal에 표시되는 프로필의 이름입니다.
    - **설명**  
      Azure Portal에 표시되는 프로필의 설명입니다.
    - **장치 등록 유형**  
      **앱 관리**를 선택합니다.
6. **연결된 앱**을 선택하여 구성할 앱을 선택합니다. 승인했으며 Intune과 동기화한 앱을 앱 목록에서 선택합니다.
7. 앱에서 지원하는 각 구성 설정의 경우 **이름** 및 **값**을 입력하고 줄임표(**...**)를 클릭합니다.  
    구성을 삭제하려면 줄임표(**...**)를 클릭하고 **삭제**를 선택합니다.  
    Intune 앱 SDK를 사용할 수 있는 앱은 키-값 쌍의 구성을 지원합니다. 키-값 구성이 지원되는 앱에 대한 자세한 내용은 각 앱에 대한 설명서를 참조하세요.  
    또한 응용 프로그램에 의해 생성된 데이터로 동적으로 채워지는 토큰을 사용할 수 있습니다.

## <a name="configuration-values-using-tokens"></a>토큰을 사용하는 구성 값

특정 토큰을 생성하여 Intune에서 관리되는 응용 프로그램에 보낼 수 있습니다. 예를 들어 앱 구성에서 전자 메일 설정을 사용할 수 있는 경우 토큰을 사용하여 동적 전자 메일을 추가할 수 있습니다. 앱에서 예상되는 이름을 **이름** 필드에 입력한 다음, **값** 필드에 `\{\{mail\}\}`을 입력합니다.

Intune은 구성 설정에서 다음과 같은 토큰 형식을 지원합니다.

- \{\{userprincipalname\} \} -(예:  **John@contoso.com** )
- \{\{mail\}\} - (예: **John@contoso.com**)
- \{\{partialupn\}\} - (예: **John**)
- \{\{accountid\}\} - (예: **fc0dc142-71d8-4b12-bbea-bae2a8514c81**)
- \{\{deviceid\}\} - (예: **b9841cd9-9843-405f-be28-b2265c59ef97**)
- \{\{userid\}\} - (예: **3ec2c00f-b125-4519-acf0-302ac3761822**)
- \{\{username\}\} - (예: **John Doe**)
- \{\{PrimarySMTPAddress\}\} - (예: testuser@ad.domain.com) 


> [!Note]  
> \{\{ 및 \}\} 문자는 토큰 형식에만 사용되며 다른 용도로 사용하면 안 됩니다.

## <a name="next-steps"></a>다음 단계

평소대로 앱을 계속 [할당](apps-deploy.md) 및 [모니터링](apps-monitor.md)합니다.