---
title: "장치 사용 중지 | Microsoft Intune"
description: "Intune은 정책 및 회사 포털을 제거하여 Intune 관리에서 장치를 제거할 수 있도록 선택적 초기화 및 전체 초기화를 모두 지원합니다."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3dbec400-5d8a-47be-b892-7745811d9de2
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: f2ecd0c90df60dce3a610c00fa0bc35ea7c3a7d3
ms.openlocfilehash: c96f320856270281772cc3abc891d142eab97ac7


---

# Intune 관리에서 장치 사용 중지

장치가 회사 소유 또는 개인 소유인지 관계없이 결과적으로 관리되는 장치는 Intune 관리에서 제거되어야 합니다. 다양한 이유로 장치를 사용 중지해야 할 수 있습니다.

-   사용자가 계획된 방법으로 퇴사(“관리된” 떠남)
-   갑작스러운 퇴사(해고, 사퇴 등).
-   장치 분실
-   장치 용도 변경(다른 사용자에게 이관, 다른 용도로 재사용 등)

모바일 장치로 관리되는 장치를 선택적으로 초기화하거나 전체를 초기화할 수 있습니다. 또는 장치를 잠그고 암호를 재설정할 수도 있습니다. 장치를 초기화하면 사용자 구독을 확보하여 다른 장치를 추가할 수 있습니다. Intune 클라이언트 소프트웨어로 관리되는 PC를 사용 중지할 수도 있습니다.

## 장치에서 데이터 및 앱 지우기
선택적 초기화 및 전체 초기화 둘 다 정책 및 회사 포털을 제거하여 Intune 관리에서 장치를 제거합니다. 결과적으로 장치에는 Microsoft SharePoint, 메일 또는 Office 365와 같은 회사 리소스에 로그인하는 데 필요한 자격 증명이 더 이상 없게 됩니다.

[선택적 초기화](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#selective-wipe)는 자신의 장치를 Intune에 등록한 직원이 수행하면 좋은 작업입니다. 이 경우 장치의 개인 정보는 그대로 보존되기 때문입니다. 회사 데이터만 제거됩니다.

용도를 변경해야 하는 장치의 경우 [전체 초기화](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#full-wipe)를 사용할 수도 있습니다. 이렇게 하면 장치가 공장 기본 설정으로 재설정됩니다.

## Azure Active Directory 포털에서 장치를 삭제하려면

1.  조직 자격 증명을 사용하여 [http://aka.ms/accessaad](http://aka.ms/accessaad) 또는 [https://portal.office.com](https://portal.office.com)에 로그인한 다음 **관리 센터** &gt; **Azure AD**를 선택합니다.

2.  Azure 구독이 없으면 만듭니다. 유료 계정이 있으면 신용 카드 또는 결제 과정이 필요하지 않습니다. **무료 Azure Active Directory 등록** 구독 링크를 선택합니다.

4.  **Active Directory**를 선택하고 조직을 선택합니다.

5.  **사용자** 탭을 선택합니다.

6.  삭제하려는 장치의 사용자를 선택합니다.

7.  **장치**를 선택합니다.

8.  적합한 장치를 선택하고 **장치 삭제**를 선택합니다. 장치는 다음번에 Active Directory와 동기화될 때 삭제됩니다. 이 과정은 대개 4시간 이내에 진행됩니다. 동기화 후 장치는 관리에서 제거됩니다. 그러면 이 사용자에 대한 장치 제한에서 장치 하나가 제거됩니다.

## 관리되는 컴퓨터 사용 중지
Intune 클라이언트 소프트웨어로 관리되는 컴퓨터는 Intune 관리 콘솔의 관리에서 제거될 수 있습니다. 이렇게 제거할 경우 컴퓨터에서 클라이언트 소프트웨어도 제거되고 Intune 정책이 삭제됩니다. [Intune 클라이언트 소프트웨어로 관리되는 컴퓨터 사용 중지](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client#retire-a-computer.md)에 대한 정보를 참조하세요.

## 장치 액세스 차단
장치가 분실되었거나 직원이 회사 소유의 하드웨어를 반환하지 않고 퇴사하여 장치를 사용 중지해야 할 경우 [암호를 재설정하고 원격으로 장치를 잠글](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) 수도 있습니다. 이렇게 하면 회사 정보가 잘못 사용되는 것을 막을 수 있습니다. 단, 해당 장치는 분실된 것으로 등록해야 할 수 있습니다.

직원의 Intune 사용자 계정에서 라이선스를 해지할 수도 있습니다. 그러면 라이선스를 확보하여 새로운 사용자 계정에 할당할 수 있습니다.

## 하드웨어 사용 중지
장치 자체의 수명이 다해 더 이상 사용할 수 없는 경우도 있습니다. 이러한 경우에는 전체 초기화로 장치를 [초기 설정으로 다시 설정](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md) 하면 모든 데이터가 제거되며 해당 장치가 Intune에서 제거됩니다. 그런 다음 회사 정책에 따라 하드웨어를 폐기할 수 있습니다.

### 참고 항목
[전체 또는 선택적 초기화를 통해 데이터 보호 지원](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md)



<!--HONumber=Oct16_HO3-->


