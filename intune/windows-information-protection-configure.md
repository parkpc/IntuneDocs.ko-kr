---
title: "Windows Information Protection 구성 - Intune"
titleSuffix: Intune Azure preview
description: "Intune Azure 미리 보기: Windows Information Protection을 관리하는 데 사용할 수 있는 Intune 설정을 알아봅니다."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f233672c-7d9b-4554-af1f-92c001a1a3c5
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: fc58b07fe33ff6223dfa182fb4f81f15379295fa
ms.contentlocale: ko-kr
ms.lasthandoff: 05/23/2017


---

# <a name="how-to-configure-windows-information-protection-in-microsoft-intune"></a>Microsoft Intune에서 Windows Information Protection을 구성하는 방법

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

기업에서 직원 소유 장치가 증가됨에 따라 메일, 소셜 미디어, 공용 클라우드 등의 앱 및 서비스를 통해 실수에 의한 데이터 유출의 위험도 증가하며, 이러한 상황은 기업에서 제어할 수 없습니다. 예를 들어 직원이 개인 메일 계정에서 최신 엔지니어링 사진을 전송하거나, 제품 정보를 복사한 후 트윗에 붙여넣거나, 진행 중인 판매 보고서를 공용 클라우드 저장소에 저장합니다.

**Windows Information Protection**은 직원 환경을 방해하지 않으면서 이러한 잠재적인 데이터 유출로부터 보호하는 데 도움이 됩니다. 또한 작업 환경이나 기타 앱을 변경하지 않고도 엔터프라이즈 앱 및 데이터가 회사 소유 장치 및 직원이 회사에 가져오는 개인 장치에서 실수로 누출되지 않도록 보호하는 데도 유용합니다.

이 Intune 정책은 Windows Information Protection, 엔터프라이즈 네트워크 위치, 보호 수준 및 암호화 설정으로 보호되는 앱 목록을 관리합니다.

>[!NOTE]
> Windows 10 회사 포털 앱에서 Windows 정보 보호를 사용하려면 회사 포털 앱을 Windows 정보 보호의 **예외** 모드에 추가해야 합니다. 

### <a name="next-steps"></a>다음 단계
자세한 내용은 [Windows 정보 보호를 사용하여 엔터프라이즈 데이터 보호](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip)를 참조하세요.

