---
title: "Intune 라이선스 관리 | Microsoft Intune"
description: "Intune 구독에 대해 사용자에게 라이선스를 할당하는 방법을 설명합니다."
keywords: 
author: Staciebarker
manager: arob98
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bb4314ea-88b5-44d3-92ce-4c6aff0587a4
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 376e6c1ae229187ab8ec73390f091f1d534365dd
ms.openlocfilehash: c86cbb42554d388c943faa37a7c59b376fdaf287


---

# Intune 라이선스 관리
사용자가 로그인하여 Intune 서비스를 사용하거나 장치를 관리에 등록할 수 있게 하려면 먼저 [Office 365 포털](http://go.microsoft.com/fwlink/p/?LinkId=698854)을 사용하여 각각의 사용자에게 Intune 구독에 대한 라이선스를 할당해야 합니다. 라이선스가 할당되면 사용자 이름이 Intune 관리 콘솔에 표시됩니다. 그러면 사용자는 장치를 최대 5개 등록할 수 있습니다.

Microsoft EMS(Enterprise Mobility Suite)를 사용하는 조직에는 EMS 패키지의 Intune 서비스 또는 Azure Active Directory Premium만 필요한 사용자가 있을 수 있습니다. [Azure Active Directory PowerShell cmdlet](https://msdn.microsoft.com/library/jj151815.aspx)을 사용하여 한가지 서비스 또는 서비스 하위 집합을 할당할 수 있습니다. 자세한 내용은 [PowerShell을 사용하여 Intune 라이선스 관리](start-with-a-paid-subscription-to-microsoft-intune-step-4-posh.md)를 참조합니다.

## Intune 라이선스가 할당되는 방식
사용자 계정이 온-프레미스에 Active Directory에서 동기화되었거나 [Office 365 포털](http://go.microsoft.com/fwlink/p/?LinkId=698854)을 통해 클라우드 서비스 구독에 추가된 경우에는, Intune 라이선스가 자동으로 할당되지 않습니다. 대신, 나중에 Intune 테넌트 관리자가 Office 365 포털에서 사용자에게 라이선스를 할당하도록 사용자 계정을 편집해야 합니다.

구독이 그 구독과 연결된 다른 클라우드 서비스와 Azure AD를 공유하는 경우에는, 해당 서비스에 추가된 사용자에 대한 액세스를 갖게 됩니다. 각 사용자에게 라이선스가 할당될 때까지 이러한 사용자는 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]에 대한 라이선스를 보유하지 못합니다.

> [!TIP]
> [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]에 대한 라이선스를 할당하거나 해지하는 옵션을 사용할 수 없는 경우에는 [Enterprise Mobility Suite](https://www.microsoft.com/en-us/server-cloud/enterprise-mobility/overview.aspx)를 사용할 때 제공되는 옵션과 같은 볼륨 라이선스 옵션이 구독에 포함되어 있는 것일 수 있습니다. 라이선스를 할당하거나 해지하는 방법에 대한 자세한 내용은 라이선스 옵션에 대한 설명서를 참조하십시오.

## Intune 사용자 라이선스 할당

[Office 365 포털](http://go.microsoft.com/fwlink/p/?LinkId=698854)을 사용하여 클라우드 기반 사용자를 수동으로 추가하고, 클라우드 기반 사용자 계정 및 온-프레미스 Active Directory에서 Azure AD로 동기화한 계정 양쪽 모두에 대해 라이선스를 할당합니다.

1.  테넌트 관리자 자격 증명을 사용하여 [Office 365 포털](http://go.microsoft.com/fwlink/p/?LinkId=698854)에 로그인한 후 **사용자** > **모든 사용자**를 선택합니다.

2.  Intune 사용자 라이선스를 할당하고 싶은 사용자 계정을 선택하고, **Microsoft Intune** (독립 실행형) 또는 **Enterprise Mobility Suite** 중 하나를 선택합니다.

3.  이제 사용자 계정은 서비스를 사용하고 장치를 관리에 등록하는 데 필요한 권한이 생겼습니다.

### PowerShell을 사용하여 EMS 사용자 라이선스를 선택적으로 관리
Microsoft EMS(Enterprise Mobility Suite)를 사용하는 조직에는 EMS 패키지의 Intune 서비스 또는 Azure Active Directory Premium만 필요한 사용자가 있을 수 있습니다. [Azure Active Directory PowerShell cmdlet](https://msdn.microsoft.com/library/jj151815.aspx)을 사용하여 한가지 서비스 또는 서비스 하위 집합을 할당할 수 있습니다. 

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

### 다음 단계
축하합니다. *Intune 빠른 시작 가이드*의 4단계를 완료했습니다.
>[!div class="step-by-step"]

>[&larr; **사용자를 Intune에 동기화**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**사용자 및 장치 구성** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)  



<!--HONumber=Jul16_HO3-->


