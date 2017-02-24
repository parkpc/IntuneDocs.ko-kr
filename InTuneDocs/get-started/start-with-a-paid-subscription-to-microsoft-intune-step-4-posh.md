---
title: "PowerShell을 사용하여 Intune 라이선스 관리 | Microsoft 문서"
description: "PowerShell을 사용하여 Intune 라이선스 관리"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/14/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d2d31c80-c32c-4315-8271-1b0cf9a1f78a
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ad13897fe7bbe4fe13167bb4ce7f558b436a7a90
ms.openlocfilehash: dd71cc8f0d1fc5802f7f24e5f275089ffa24a1c5


---

# <a name="manage-intune-licenses-using-powershell"></a>PowerShell을 사용하여 Intune 라이선스 관리

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

이 항목에서는 관리자가 PowerShell을 사용하여 Intune 사용자 라이선스를 관리하는 방법을 알려줍니다.

사용자가 로그인하여 Intune 서비스를 사용하거나 장치를 관리되는 상태로 등록하려면 먼저 [Intune 라이선스 관리](start-with-a-paid-subscription-to-microsoft-intune-step-4.md)에 각 사용자에게 Intune 구독에 사용할 라이선스를 할당해야 합니다. 그러나 Microsoft Enterprise Mobility + Security를 사용하는 조직에는 EMS 패키지의 Intune 서비스 또는 Azure Active Directory Premium만 필요한 사용자가 있을 수 있습니다. [Azure Active Directory PowerShell cmdlet](https://msdn.microsoft.com/library/jj151815.aspx)을 사용하여 한 가지 서비스 또는 서비스 하위 집합을 할당할 수 있습니다.

EMS 서비스에 대해 사용자 라이선스를 선택적으로 할당하려면, [Windows PowerShell용 Azure Active Directory 모듈](https://msdn.microsoft.com/library/jj151815.aspx#bkmk_installmodule)이 설치된 컴퓨터에서 관리자로 PowerShell을 엽니다. PowerShell은 로컬 컴퓨터 또는 ADFS 서버에 설치할 수 있습니다.

원하는 서비스 계획에만 적용되는 새로운 라이선스 SKU 정의를 만들어야 합니다. 이렇게 하려면, 적용하지 않을 계획은 비활성화합니다. 예를 들면, Intune 라이선스를 할당하지 않는 라이선스 SKU 정의를 만들 수 있습니다. 사용 가능한 서비스 목록을 보려면 다음을 입력합니다.

    (Get-MsolAccountSku | Where {$_.SkuPartNumber -eq "EMS"}).ServiceStatus

다음 명령을 실행하여 Intune 서비스 계획을 제외할 수 있습니다. 같은 방법을 사용하여 전체 보안 그룹으로 확장하거나 보다 세분화된 필터를 사용할 수 있습니다.

**예 1** 명령줄에서 새로운 사용자를 만들고 라이선스의 Intune 부분을 사용하지 않고 EMS 라이선스를 할당합니다.

    Connect-MsolService

    New-MsolUser -DisplayName “Test User” -FirstName FName -LastName LName -UserPrincipalName user@<TenantName>.onmicrosoft.com –Department DName -UsageLocation US

    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -AddLicenses <TenantName>:EMS -LicenseOptions $CustomEMS


다음을 통해 검증합니다.

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com").Licenses.ServiceStatus

**예 2** 이미 라이선스가 할당된 사용자에 대한 EMS 라이선스의 Intune 부분을 비활성화합니다.

    Connect-MsolService

    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -RemoveLicenses IAPProdPartnerTest:EMS

    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -AddLicenses <TenantName>:EMS -LicenseOptions $CustomEMS

다음을 통해 검증합니다.

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com" .Licenses.ServiceStatus

![PoSH-AddLic-Verify](./media/posh-addlic-verify.png)

### <a name="next-steps"></a>다음 단계
축하합니다. *Intune 빠른 시작 가이드*의 4단계를 완료했습니다.
>[!div class="step-by-step"]

>[&larr; **사용자를 Intune에 동기화**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**사용자 및 장치 구성** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)  



<!--HONumber=Feb17_HO3-->


