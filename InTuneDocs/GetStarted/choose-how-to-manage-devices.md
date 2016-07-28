---
title: "장치를 관리하는 방법 선택 | Microsoft Intune"
description: 
keywords: 
author: jeffgilb
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 770aad50-fd7a-4cf1-a793-f95fe47fc3f8
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 4a7c6d8f4e47f050888e9fcf5edfa586c4a24065
ms.openlocfilehash: 502a08c1bf49057220917d929a8ffe0b98d3de2a


---

# 장치를 관리하는 방법 선택
[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] 다양한 장치를 서비스에 *등록*하여 관리할 수 있습니다. 사용자가 *회사 포털*을 사용하여 장치를 등록하고 앱을 검색 및 설치하며 해당 장치가 회사 정책을 준수하도록 하고 IT 지원에 문의하는 등 다양한 작업을 수행할 수 있습니다.

## 모바일 장치를 관리하는 방법
[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] 다음 장치 플랫폼을 관리할 수 있습니다.

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

<div class="alert alert-tip">
  <h5><span class="icon-tip"></span> 팁</h5>
  <p>위에서 지원되는 버전보다 이전 버전의 iOS를 실행하는 장치를 이전에 등록한 경우 등록된 장치가 유지됩니다. 그러나 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] 각각에 대한 설명서를 확인하여 해당 기능이 iOS의 해당 버전을 지원하는지 확인합니다.</p>
</div>

[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] 사용자의 장치, 즉 BYOD("Bring Your Own Device")를 관리할 수 있습니다. 또한, 회사에서 사용자가 선택할 수 있는 장치 목록을 제공하는 시나리오를 포함하여 회사 소유의 장치, 즉 CYOD(“Choose Your Own Device”)를 관리할 수도 있습니다.

### 관리에 장치 등록
iOS, Android 및 Windows Phone을 비롯한 모바일 장치 운영 체제의 경우 항상 장치를 등록해야 합니다. 그러나 조직의 요구 사항에 따라 장치를 등록하는 방법이 다릅니다.

|등록 유형|BYOD|CYOD|관리자 계정이 있는 공유 장치|사용자 계정이 없는 공유 장치|
|-------------------|--------|--------|--------------------------------------|----------------------------------------|
|**설명**|Microsoft Intune을 사용하여 등록하는 개인 장치|단일 사용자를 위한 회사 소유 장치|많은 사용자가 공유하는 관리자 계정을 사용하여 관리되는 회사 소유의 장치|많은 사용자가 사용하며 사용자가 지정되지 않은 회사 소유 장치|
|**장치 사용자**|Owner|할당된 사용자|사용자 고유의 계정 없음|특정 사용자 없음|
|**등록한 사람**|Owner|관리자|장치 관리자|모든 사용자|
|**등록을 취소한 사람**|소유자 또는 관리자|관리자|관리자|관리자|
|**다시 설정할 수 있는 사람**|소유자 또는 관리자|관리자|관리자|관리자|

<div class="alert alert-tip">
  <h5><span class="icon-tip"></span> 팁</h5>
  <p>장치에서 제공하는 기능의 전체 목록은 [모바일 장치 관리 기능](mobile-device-management-capabilities-in-microsoft-intune.md)을 참조하세요.</p>
</div>



## Windows PC를 관리하는 방법
[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] Intune 컴퓨터 클라이언트를 사용하여 Windows Vista 및 이후 Windows PC를 관리할 수 있습니다. 그러나 Windows PC의 경우 해당 프로그램을 설치할지 또는 장치를 등록할 때 사용할 수 없는 몇 가지 기능을 제공하는 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] PC 클라이언트 소프트웨어를 등록할지를 선택할 수 있습니다. 대부분의 시나리오에서 컴퓨터 클라이언트보다 큰 기능 집합을 제공하는 Intune으로 Windows 장치를 등록합니다.

다음을 수행하려는 경우 Intune 컴퓨터 클라이언트를 사용하는 것이 좋습니다.
<ul>
<li>Windows PC를 관리하는 기능을 사용하는 Microsoft Intune 컴퓨터 클라이언트를 사용합니다.</li>
<li>등록에 지원되지 않는 운영 체제를 실행하는 Windows PC를 관리합니다.</li>
</ul>

<div class="alert alert-tip">
  <h5><span class="icon-tip"></span> 팁</h5>
  <p>지원되는 Windows PC에서 Intune 컴퓨터 클라이언트를 설치하는 기능의 전체 목록은 [Windows PC 관리 기능](windows-pc-management-capabilities-in-microsoft-intune.md)을 참조하세요.</p>
</div>

## Exchange ActiveSync 관리
또한 Exchange ActiveSync를 사용하여 장치를 관리할 수 있습니다. 그러려면 온-프레미스 커넥터를 설치하거나 기본 제공 서비스 간 커넥터를 사용하여 Exchange Server에 연결해야 합니다.

온-프레미스 커넥터를 설치하기 위한 하드웨어 및 소프트웨어 요구 사항에 대한 자세한 내용은 [온-프레미스 커넥터의 요구 사항](/intune/deploy-use/intune-on-premises-exchange-connector#requirements-for-the-on-premises-connector) 섹션을 참조하세요.

Exchange와 함께 온-프레미스 커넥터 또는 서비스 간 커넥터를 사용하는 방법에 대한 자세한 내용은 [Exchange ActiveSync와 Microsoft Intune을 사용한 모바일 장치 관리](/intune/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune) 항목을 참조하세요.



## 다음 단계
지금까지 [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]을 사용하여 장치를 등록하는 경우 사용할 수 있는 기능 중 몇 가지를 살펴봤습니다. 이제, [장치를 등록](/intune/deploy-use/enroll-devices-in-microsoft-intune)해야 합니다. 장치를 등록한 후에 이 항목에서 설명한 기능을 모두 활용할 수 있습니다. <!--lindavr: There's a logical flaw in our "get to know/get started" content. You can take the path in this topic or you can take the path in the What to know before your get started topic. And they don't cover the same ground. -->



<!--HONumber=Jul16_HO3-->


