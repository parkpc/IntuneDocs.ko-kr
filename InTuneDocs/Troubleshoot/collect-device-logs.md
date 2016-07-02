---
title: "장치 로그 수집 | Microsoft Intune"
description: 
keywords: 
author: Nbigman
manager: jeffgilb
ms.date: 06/01/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d97fb610-9d88-40e5-bb06-447eec533630
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ac5c66f57194a84580aa495a58e5281683aa1cca
ms.openlocfilehash: 4fc08fcea6cea897b9ddc3d0c00f2d83069f639d


---

# 장치 로그

문제 해결 과정의 일환으로 사용자 장치에서 로그를 수집할 수 있습니다. 이러한 로그를 수집하기 위한 지침은 여기에 설명되어 있습니다. 일반적으로 장치에 액세스하거나, 로그를 수집하여 해당 로그를 보내달라고 사용자에게 요청할 수 있습니다. 

### Android 로그 위치
Android 로그는 *<Android Device>\Phone\Android\data\com.microsoft.windowsintune.companyportal\files*에 있습니다. [Send Android diagnostic data logs to your IT administrator using email](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-email-android)(메일을 사용하여 IT 관리자에게 Android 진단 데이터 로그 보내기) 항목에 설명된 대로 사용자가 로그 파일을 메일로 보낼 수도 있습니다.

### iOS 로그

[IT 관리자에게 iOS 등록 오류 보내기](/intune/enduser/send-errors-to-your-it-admin-ios)에 설명된 대로 사용자가 등록 오류를 보낼 수 있습니다.

### Mac OS X 장치

1. **Console(콘솔)** 앱을 엽니다.
2. **FILES(파일)**에서 **system.log**를 선택합니다.
3. 맨 위의 메뉴 모음에서 **File(파일)** > **Save a Copy As…(다른 이름으로 복사본 저장…)**를 선택하고 파일을 저장합니다.

### Windows Phone

**Windows Phone 회사 포털**에서, 사용자가 **…**을 선택하여 메뉴에 액세스한 후 **로그 보내기**를 선택해야 합니다. 이 옵션은 포털에 로그인하기 전과 후에 모두 사용할 수 있습니다.

### Windows

Windows 회사 포털의 경우 로그는 *%localappdata%\Packages\Microsoft.CompanyPortal_8wekyb3d8bbwe\LocalState*에 있습니다.



<!--HONumber=Jun16_HO4-->


