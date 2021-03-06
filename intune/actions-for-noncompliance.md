---
title: "Intune과 비준수에 대한 작업"
titleSuffix: Intune on Azure
description: "Intune에서 비준수에 대한 작업을 만드는 방법을 알아봅니다."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 01/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 573a8b000e63576f3dd3bae1b6e8e8c47733f6bf
ms.sourcegitcommit: a6fd6b3df8e96673bc2ea48a2b9bda0cf0a875ae
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2018
---
# <a name="automate-actions-for-noncompliance"></a>비준수에 대한 작업 자동화

**비준수에 대한 작업**을 사용하면 준수 정책 기준을 충족하지 않는 장치에 적용되는 작업을 시간순으로 구성할 수 있습니다. 기본적으로 장치가 준수 정책 기준을 충족하지 않는 것으로 감지되면 Intune에서 즉시 이 장치를 비준수로 표시하고 Azure AD 조건부 액세스에 따라 장치를 차단합니다. **비준수에 대한 작업**은 장치가 비준수 상태일 때 수행할 작업을 결정하는 데 더 많은 유연성을 제공합니다. 예를 들어 장치를 즉시 차단하지 않고 사용자에게 준수하도록 유예 기간을 부여하기로 결정할 수 있습니다.

2가지 유형의 작업이 있습니다.

-   **이메일을 통해 최종 사용자에게 알림**: 최종 사용자에게 보내기 전에 이메일 알림을 사용자 지정할 수 있습니다. Intune은 회사 로고, 연락처 정보를 비롯하여 받는 사람, 제목, 메시지 본문을 사용자 지정할 수 있습니다.

    또한 Intune은 비규격 장치에 대한 세부 정보를 이메일 알림에 포함합니다.

-   **장치를 비준수로 표시**: 장치를 비준수로 표시할 일정을 일 수로 지정할 수 있습니다. 작업이 즉시 적용되도록 구성하거나 사용자에게 장치 준수 정책을 준수할 유예 기간을 제공할 수 있습니다.

## <a name="before-you-begin"></a>시작하기 전에

비준수에 대한 작업을 설정하려면 하나 이상의 장치 준수 정책을 만들어야 합니다. 

- 다음 플랫폼에 대한 장치 준수 정책을 만드는 방법을 알아봅니다.

    -   [OWA(Outlook Web Access)](compliance-policy-create-android.md)
    -   [Android for Work](compliance-policy-create-android-for-work.md)
    -   [Android](compliance-policy-create-ios.md)
    -   [macOS](compliance-policy-create-mac-os.md)
    -   [Windows](compliance-policy-create-windows.md)

장치 준수 정책을 사용하여 장치에서 회사 리소스를 사용하지 못하도록 차단하려면 Azure AD 조건부 액세스 설정을 준비해야 합니다. 

- [EMS 조건부 액세스를 설정하는 방법](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)을 알아봅니다.

또한 알림 메시지 템플릿을 만들어 둬야 합니다. 알림 메시지 템플릿은 나중에 비준수에 대한 작업을 만드는 프로세스 중에 사용자에게 이메일을 보내는 데 사용됩니다.

### <a name="to-create-a-notification-message-template"></a>알림 메시지 템플릿 만들기

1. [Azure Portal에서 Intune](https://portal.azure.com)으로 이동하여 Intune 자격 증명으로 로그인합니다.
2. 왼쪽 메뉴에서 **More services**(추가 서비스)를 선택한 다음 텍스트 상자 필터에 **Intune**을 입력합니다.
3. **Intune**을 선택합니다.
4. **장치 준수**를 선택한 다음 **관리** 섹션 아래에서 **알림**을 선택합니다.
5. **알림 만들기**를 선택하고 다음 정보를 입력합니다.
    - 이름
    - 주체
    - 메시지
    - 메일 머리글 – 회사 로고 포함
    - 메일 바닥글 – 회사 이름 포함
    - 메일 바닥글 – 연락처 정보 포함

5. **알림 만들기**를 선택하고 다음 정보를 입력합니다.

    a. 이름

    b. 주체

    c.  메시지

    d. 이메일 머리글 – 회사 로고 포함

    e. 이메일 바닥글 – 회사 이름 포함

    f. 이메일 바닥글 – 연락처 정보 포함

![알림 메시지 템플릿 예제](./media/actionsfornoncompliance-1.PNG)

정보 추가를 완료하면 **만들기**를 선택합니다. 알림 메시지 템플릿을 사용할 수 있습니다.

> [!NOTE]
> 이전에 만든 알림 템플릿을 편집할 수도 있습니다.

## <a name="to-create-actions-for-noncompliance"></a>비준수에 대한 작업을 만들려면

> [!TIP]
> Intune에서는 기본적으로 비준수에 대한 작업 섹션에서 미리 정의된 하나의 작업을 제공합니다. 이 작업은 장치 준수 정책 기준을 충족하지 않는 것으로 감지된 장치를 비준수로 표시합니다. 감지된 후 장치가 비준수로 표시되는 기간을 사용자 지정할 수 있습니다. 이 작업은 제거할 수 없습니다.

새 장치 준수 정책을 만들 때 또는 기존 장치 준수 정책을 편집할 때 작업을 추가할 수 있습니다.

1.  Intune 작업의 **장치 준수 정책** 블레이드에서 **관리** 섹션 아래에 있는 **정책**을 선택합니다.

2.  장치 준수 정책을 클릭하여 선택한 다음 **관리** 섹션 아래에서 **속성**을 선택합니다.

3.  **Device compliance policy properties**(장치 준수 정책 속성) 블레이드가 열립니다. **비준수에 대한 작업**을 선택합니다.

4.  **비준수에 대한 작업** 블레이드가 열리면, **추가**를 선택하여 작업 매개 변수를 지정합니다. 이전에 만든 메시지 템플릿, 추가 수신자 및 유예 기간 일정을 선택할 수 있습니다. 일정에서 일 수(0 - 365)를 지정할 수 있습니다. 그런 다음 조건부 액세스 정책을 적용할 수 있습니다. 일 수를 **0**으로 지정하면 장치에서 장치 준수 정책을 준수하지 않을 때 조건부 액세스를 통해 회사 리소스에 대한 액세스를 **즉시** 차단합니다.

5.  정보 추가를 완료하면 **추가**, **확인**을 차례로 선택합니다.

## <a name="next-steps"></a>다음 단계
장치 준수 블레이드에서 사용할 수 있는 보고서를 실행하여 장치 준수 작업을 모니터링할 수 있습니다. 자세한 내용은 [Intune에서 장치 준수를 모니터링하는 방법](device-compliance-monitor.md)을 참조하세요.
