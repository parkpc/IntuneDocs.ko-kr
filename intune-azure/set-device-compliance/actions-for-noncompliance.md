---
title: "비준수에 대한 작업"
titleSuffix: Intune Azure preview
description: "Intune Azure 미리 보기: 비준수 장치에 대한 작업을 만드는 방법을 알아봅니다."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6d0e0c4b-a562-44f3-82a4-80eb688d4733
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: deea78dcea9ade031441bf12b388a862235a8e9c
ms.openlocfilehash: 16da087e741e335144266c838c0a91050bd7d520
ms.lasthandoff: 03/15/2017


---

# <a name="create-actions-for-non-compliance"></a>비준수에 대한 작업 만들기

**비준수에 대한 작업**을 사용하면 준수하지 않는 장치에 적용되는 시간순 작업을 구성할 수 있습니다. 예를 들어 비준수 장치의 사용자에게 메일을 통해 알리거나 해당 장치가 조건부 액세스를 통해 회사 리소스에 액세스하는 것을 차단할 수 있습니다.

## <a name="use-case-scenario"></a>사용 사례 시나리오

기본적으로 장치가 Intune 장치 준수 정책에 따라 비준수로 보고되면 조건부 액세스에 의해 즉시 해당 장치가 차단되고 사용자는 준수 지침이 포함된 메일을 받게 됩니다. **비준수에 대한 작업**은 장치가 비준수 상태인 경우 수행할 일을 결정하는 데 더 많은 유연성을 제공합니다. 예를 들어 장치를 즉시 차단하지 않고 사용자에게 준수하도록 유예 기간을 부여하기로 결정할 수 있습니다.

2가지 유형의 작업이 있습니다.

-   메일을 통해 사용자에게 알림

-   조건부 액세스를 통한 회사 리소스 액세스 차단

## <a name="notify-the-user-via-email"></a>메일을 통해 사용자에게 알림

미리 생성된 기본 메일 템플릿 중에서 선택하거나 완전히 사용자 지정된 메일 알림을 만들 수 있습니다. 제목, 메시지 본문(회사 로고 포함), 연락처 정보, 추가 수신자 등의 사용자 지정을 제공합니다.

## <a name="block-corporate-resource-access-through-conditional-access"></a>조건부 액세스를 통한 회사 리소스 액세스 차단

회사 리소스에 대한 장치의 액세스를 차단할 일정(단위: 일수)을 결정할 수 있습니다. 이는 즉시 이루어질 수 있지만, 사용자에게 장치 준수 정책을 준수하도록 유예 기간을 부여할 수도 있습니다.

## <a name="before-you-begin"></a>시작하기 전에

비준수에 대한 작업을 설정하려면 하나 이상의 장치 준수 정책을 만들어야 합니다.

-   각 장치에 대한 장치 준수 정책을 만드는 방법을 알아봅니다.

    -   [OWA(Outlook Web Access)](https://docs.microsoft.com/intune-azure/set-device-compliance/create-a-compliance-policy-for-android)

    -   [Android for Work](https://docs.microsoft.com/intune-azure/set-device-compliance/create-a-compliance-policy-for-android-for-work)

    -   [iOS](https://docs.microsoft.com/intune-azure/set-device-compliance/create-a-compliance-policy-for-ios)

    -   [Windows](https://docs.microsoft.com/intune-azure/set-device-compliance/create-a-compliance-policy-for-windows)

장치 준수 정책을 사용하여 장치가 회사 리소스를 사용하는 것을 차단하도록 계획할 때는 EMS 조건부 액세스를 설정해 둬야 합니다.

- [EMS 조건부 액세스를 설정하는 방법](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)을 알아봅니다.

또한 알림 메시지 템플릿을 만들어 둬야 합니다. 알림 메시지 템플릿은 나중에 비준수에 대한 작업을 만드는 프로세스 중에 사용자에게 메일을 보내는 데 사용됩니다.

### <a name="to-add-a-notification-message-template"></a>알림 메시지 템플릿 추가

**장치 준수 정책** 블레이드에서 다음을 수행합니다.

1.  **관리** 아래에서 **알림**을 선택합니다. [알림 메시지 템플릿] 블레이드가 열립니다.

    ![알림 템플릿을 추가하는 방법](../media/afnc-1.png)

2.  **추가**를 선택한 후 다음을 정의해야 합니다.

    a.  설명

    b.  From

    c.  주체

    d.  메시지

    e.  메일 머리글 – 회사 로고 포함

    f.  메일 바닥글 – 회사 이름 포함

    g.  메일 바닥글 – 연락처 정보 포함

     ![알림 메시지 템플릿](../media/afnc-2.png)

정보 추가를 마친 후 **만들기**를 클릭하면 됩니다. 알림 메시지 템플릿을 사용할 수 있습니다.

> [!NOTE] 
> 이전에 만든 알림 템플릿을 편집할 수도 있습니다.

## <a name="to-create-actions-for-non-compliance"></a>비준수에 대한 작업을 만들려면

새 장치 준수 정책을 만들 때 또는 기존 장치 준수 정책을 편집하여 작업을 추가할 수 있습니다.

1.  **장치 준수 정책** 블레이드에서 **관리** 아래에 있는 **정책**을 선택합니다.

2.  장치 준수 정책을 클릭하여 선택합니다.

    ![규정 준수 정책](../media/afnc-3.png)

3.  **Device compliance policy properties**(장치 준수 정책 속성) 블레이드가 열립니다. **비준수에 대한 작업**을 선택합니다.

4.  [비준수에 대한 작업] 블레이드가 열립니다. **추가**를 선택하여 작업 매개 변수를 지정합니다.

    ![비준수에 대한 작업 블레이드](../media/afnc-4.png)

비준수에 대한 작업은 다음과 같습니다.

-   **조건부 액세스 정책 적용**

-   **최종 사용자에게 메일 보내기**

### <a name="enforce-conditional-access-policy"></a>조건부 액세스 정책 적용

이 비준수에 대한 작업을 추가하려면:

1.  **비준수에 대한 작업** 블레이드에서 **추가**를 선택합니다.

2.  **작업 매개 변수** 블레이드에서 [작업] 드롭다운 목록의 **조건부 액세스 정책 적용**을 선택합니다.

3.  **일정**에서 조건부 액세스 정책을 적용할 일수를 0부터 255까지 지정할 수 있습니다. 일수를 **0**으로 지정하는 경우 장치가 장치 준수 정책을 준수하지 않으면 조건부 액세스가 **즉시** 회사 리소스에 대한 액세스를 차단해야 함을 의미합니다.

    ![비준수에 대한 작업 예약](../media/afnc-5.png)

4.  **추가**를 선택한 다음 **작업** 블레이드에서 **확인**을 선택합니다.

5.  **Device compliance policy properties**(장치 준수 정책 속성) 블레이드에서 **저장**을 선택합니다.

### <a name="send-e-mail-to-end-user"></a>최종 사용자에게 메일 보내기

메일 템플릿을 사용하여 비준수 사용자에게 메일을 보낼 수 있습니다. 이러한 메일은 조직 전반에 걸쳐 장치 준수를 촉구하는 데 도움이 됩니다.

이 비준수에 대한 작업을 추가하려면:

1.  **비준수에 대한 작업** 블레이드에서 **추가**를 선택합니다.

2.  **작업 매개 변수** 블레이드에서 [작업] 드롭다운 목록의 **최종 사용자에게 메일 보내기**를 선택합니다.

3.  **메시지 템플릿**을 클릭하여 이전에 만든 메시지 템플릿을 선택합니다. 메시지 템플릿 내용을 본 다음 **선택**을 선택합니다.

    ![메시지 템플릿](../media/afnc-6.png)

> [!NOTE] 
> 메시지 템플릿을 볼 수 있지만 편집할 수는 없습니다. 메시지 템플릿을 편집하려는 경우에는 **알림** 블레이드로 돌아가야 합니다.

1.  **일정**에서 비준수 상태로부터 며칠 후에 사용자에게 메일을 보낼지 입력합니다. 일수를 **0**으로 지정하는 경우 메일이 **즉시** 전송됩니다.

2.  **추가**를 선택한 다음 **작업** 블레이드에서 **확인**을 선택합니다.

3.  **Device compliance policy properties**(장치 준수 정책 속성) 블레이드에서 **저장**을 선택합니다.

