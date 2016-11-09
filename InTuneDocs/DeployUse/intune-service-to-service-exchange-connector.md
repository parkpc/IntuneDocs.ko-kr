---
title: "Exchange Online용 Exchange Connector | Microsoft Intune"
description: "Intune을 Office 365 Exchange 서비스에 연결하여 Exchange ActiveSync MDM(모바일 장치 관리)을 지원합니다."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 05fa5dc9-9bad-4557-987a-9b8ce4edebb0
ms.reviewer: muhosabe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c880bd9dfb998355a18e78af898a96d4cee393f7
ms.openlocfilehash: a6438bb3ca21e5c46dca5ebe69266fd9bce9a4b8


---

# Exchange Online용 Intune Service-to-Service Connector 구성

이 정보를 사용하여 Microsoft Intune과 Exchange Online 또는 신규 Exchange Online Dedicated 서비스에 연결합니다. Exchange Online Dedicated 환경이 **신규** 상태인지 아니면 **기존** 상태인지 확인하려면 계정 관리자에게 문의하세요. Intune은 Exchange Connector 연결 형식에 상관없이 구독당 연결을 한 번만 지원합니다.

## Service-to-Service Connector에 대한 요구 사항
**Service to Service Connector**는 Exchange Online 또는 신규 Exchange Online Dedicated만 지원하며 온-프레미스 인프라에 대한 요구 사항은 없습니다.

|요구 사항|추가 정보|
|---------------|--------------------|
|Exchange Online 구성 및 실행|[Exchange Online](https://technet.microsoft.com/library/jj200580.aspx) |
|모바일 장치 관리 기관| [Microsoft Intune으로 모바일 장치 관리 기관 설정](prerequisites-for-enrollment.md#set-mobile-device-management-authority)|
|Microsoft Exchange 버전|Exchange Online 또는 신규 Exchange Online Dedicated 서비스|
|Active Directory 동기화|Intune Connector를 사용하려면 로컬 사용자 및 보안 그룹이 Azure Active Directory의 인스턴스와 동기화되도록 [Active Directory 동기화를 설정](/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3)해야 합니다.|

### Exchange cmdlet 요구 사항

또한 Intune Exchange Connector에 사용되는 Exchange Online 사용자 계정을 만들어야 합니다. 계정에는 Intune 관리 콘솔을 사용하고 다음과 같은 Windows PowerShell Exchange cmdlet을 실행할 수 있는 권한이 있어야 합니다.

 - Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings
 - Get-MobileDeviceMailboxPolicy, Set-MobileDeviceMailboxPolicy, New-MobileDeviceMailboxPolicy, Remove-MobileDeviceMailboxPolicy
 - Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule
 - Get-MobileDeviceStatistics
 - Get-MobileDevice
 - Get-ActiveSyncDeviceClass

## Service-to-Service Connector 설정

1. Exchange 관리자 권한 및 [위의](#exchange-cmdlet-requirements) cmdlet에 대한 권한을 가진 사용자 계정으로 [Microsoft Intune 관리 콘솔](http://manage.microsoft.com)을 엽니다. Microsoft Intune은 현재 로그인된 사용자의 전자 메일 주소를 사용하여 연결을 설정합니다.

2.  작업 영역 바로 가기 창에서 **관리**를 선택한 다음 **모바일 장치 관리** > **Microsoft Exchange** > **Exchange 연결 설정**으로 이동합니다.
![서비스 간 커넥터 설정 페이지](../media/intunesa5cservicetoserviceconnector.png)

3.  **Exchange 연결 설정** 페이지에서 **서비스 간 커넥터 설정**을 선택합니다.


Service-to-Service Connector에서 자동으로 Exchange Online 또는 신규 Exchange Online Dedicated 환경을 구성하고 해당 환경과 동기화합니다.

## Exchange 연결 확인

Exchange Connector를 구성했으면 [Microsoft Intune 관리자 콘솔](http://manage.microsoft.com)에서 **관리**로 이동한 후 **모바일 장치 관리** > **Microsoft Exchange**로 이동하고 제공한 세부 정보가 **Exchange 연결 정보**에 나타나는지 확인합니다.

마지막으로 성공한 동기화 시도의 시간과 날짜를 확인할 수도 있습니다.



<!--HONumber=Sep16_HO4-->


