---
title: "장치 사용 중지 | Microsoft Intune"
description: 
keywords: 
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3dbec400-5d8a-47be-b892-7745811d9de2
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 779127bfd39145010f0d9b6609286aaf4dedfdc8
ms.openlocfilehash: c06f1fc1168b0dde515eaa82d15095ec4d73d1cf


---

# Intune 관리에서 장치 사용 중지

장치가 회사 소유 또는 개인 소유인지 관계없이 관리되는 장치는 Intune 관리에서 사용 중지되어야 하는 시점에 이릅니다. 장치 사용 중지는 비교적 직관적이며 선택적 초기화 또는 전체 초기화를 수행합니다.
## 장치에서 데이터 및 앱 지우기
선택적 초기화 및 전체 초기화는 모두 정책 및 회사 포털을 제거하여 Intune 관리에서 장치를 제거하므로 장치에 회사 리소스(예: Microsoft SharePoint, 전자 메일 또는 Office 365)에 로그온하는 데 필요한 자격 증명이 더 이상 없습니다.

[선택적 초기화](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#selective-wipe)는 자신의 장치를 Intune에 등록한 직원이 수행하면 좋은 작업입니다. 이 경우 장치의 개인 정보는 그대로 보존되기 때문입니다. 회사 데이터만 제거됩니다.

회사 소유 장치의 경우 [전체 초기화](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#full-wipe)를 사용할 수 있으며 장치가 출하 시 설정으로 다시 설정됩니다.

## 회사 네트워크에 대한 액세스 취소
직원이 퇴사하고 회사에서 소유한 하드웨어를 반납하지 않아서 장치를 사용 중지하는 경우 장치를 [원격으로도 잠글](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) 수 있습니다. 이렇게 하면 회사 정보 및 회사 하드웨어의 부적절한 사용을 방지할 수 있습니다. 단, 해당 장치는 분실된 것으로 등록해야 할 수 있습니다.

직원의 Intune 사용자 계정에서 라이선스를 해지할 수도 있습니다. 그러면 라이선스를 확보하여 새로운 사용자 계정에 할당할 수 있습니다.

## 하드웨어 사용 중지
장치 자체의 수명이 다해 더 이상 사용할 수 없는 경우도 있습니다. 이러한 경우에는 전체 초기화로 장치를 [초기 설정으로 다시 설정](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md) 하면 모든 데이터가 제거되며 해당 장치가 Intune에서 제거됩니다. 그런 다음 회사 정책에 따라 하드웨어를 폐기할 수 있습니다.

### 참고 항목
[전체 또는 선택적 초기화를 통해 데이터 보호 지원](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md)



<!--HONumber=Jun16_HO4-->


