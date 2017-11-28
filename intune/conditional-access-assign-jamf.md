---
title: "준수 정책을 Jamf에서 관리되는 장치에 적용"
titlesuffix: Azure portal
description: "준수를 사용하여 Jamf에서 관리되는 장치를 보호할 수 있습니다."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c87fd2bd-7f53-4f1b-b985-c34f2d85a7bc
ms.reviewer: elocholi
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6184552ce901ffc062f0453f169ec992049ae69b
ms.sourcegitcommit: 82088d297eef629e3da6011681ead442ae7e25f7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2017
---
# <a name="enforce-compliance-on-macs-managed-with-jamf-pro"></a>Jamf Pro로 관리되는 Mac에서 준수 적용

|적용 대상: Azure Portal의 Intune |
|--|
|클래식 포털의 Intune에 대한 설명서를 찾으시나요? [여기로 이동](/intune/introduction-intune?toc=/intune-classic/toc.json)하세요.|
| |

|현재 비공개 미리 보기|
|--|
|이 항목에 설명된 기능은 현재 고객에게 비공개 미리 보기로만 제공됩니다. 모든 고객에게 릴리스되면 이 메시지는 제거됩니다.|
| |

Azure Active Directory 및 Microsoft Intune의 조건부 액세스 정책을 사용하여 최종 사용자가 조직 요구 사항을 준수하도록 할 수 있습니다. 이 정책을 [Jamf Pro로 관리되는](conditional-access-integrate-jamf.md) Mac에 적용할 수 있습니다. Intune 및 Jamf Pro 콘솔에 둘 다 액세스할 수 있어야 합니다.

## <a name="set-up-device-compliance-policies-in-intune"></a>Intune에서 장치 준수 정책 설정

1. Microsoft Azure를 열고 **Intune** > **장치 준수** > **정책**으로 이동합니다. 비준수 사용자 및 그룹에 대한 일련의 작업(예: 경고 메일 보내기) 선택을 포함하여 macOS에 대한 정책을 만들 수 있습니다.
2. 원하는 그룹을 검색한 후 정책을 적용합니다.

## <a name="require-the-company-portal-app-for-macos"></a>macOS용 회사 포털 앱 필요

1. macOS 장치에서 https://aka.ms/macoscompanyportal로 이동하여 macOS용 회사 포털 앱의 현재 버전을 다운로드합니다.
2. Jamf Pro를 열고 **컴퓨터 관리** > **패키지**로 이동합니다.
3. macOS용 회사 포털 앱이 포함된 새 패키지를 만든 다음 **저장**을 클릭합니다.
4. **컴퓨터** > **정책**을 열고 **새로 만들기**를 선택합니다.
5. **일반** 페이로드를 사용하여 트리거 및 실행 빈도를 포함한 정책에 대한 설정을 구성합니다.
6. **패키지** 페이로드를 선택하고 **구성**을 클릭합니다.
7. **추가**를 클릭하여 회사 포털 앱이 포함된 패키지를 선택합니다.
8. **작업** 팝업 메뉴에서 **설치**를 선택합니다.
9. 패키지의 설정을 구성합니다.
10. **범위** 탭을 클릭하여 회사 포털 앱을 설치할 컴퓨터를 지정합니다. **Save**을 클릭합니다. 다음 번에 컴퓨터에서 선택한 트리거가 발생하고 **일반** 페이로드의 기준을 충족하면 정책에 따라 범위가 지정된 장치가 실행됩니다.

## <a name="direct-your-users-to-register-jamf-pro-managed-devices-with-azure-active-directory"></a>사용자에게 Azure Active Directory를 사용하여 Jamf Pro로 관리되는 장치를 등록하도록 지시

> [!NOTE]
> 다음 단계를 진행하기 전에 macOS용 [회사 포털을 배포](conditional-access-assign-jamf.md#require-the-company-portal-app-for-macos)해야 합니다.  

최종 사용자는 Jamf Self 서비스를 통해 회사 포털 앱을 시작하여 Azure AD가 포함된 장치를 Jamf Pro에서 관리되는 장치로 등록해야 합니다.

1. Jamf Pro에서 **컴퓨터** > **정책**으로 이동하고 장치 등록을 위한 새 정책을 만듭니다.
2. 트리거 및 실행 빈도를 포함하여 **조건부 액세스** 페이로드를 구성합니다. 우선 순위를 **뒤**로 설정합니다.
3. **범위** 탭을 클릭하고 정책 범위를 모든 대상 장치로 지정합니다.
4. **Self Service** 탭을 클릭하여 정책을 Jamf Self Service에서 사용 가능하게 설정합니다. **장치 준수** 범주에 정책을 포함합니다. **Save**을 클릭합니다.
