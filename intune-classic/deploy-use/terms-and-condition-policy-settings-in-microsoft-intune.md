---
title: "사용 약관 정책 설정"
description: "회사 포털 등록, 회사 포털의 작업 리소스 액세스 및 회사 포털 사용 시의 장치와 사용자에 대한 영향을 설명하기 위해 사용자 그룹에 Intune 사용 약관을 배포할 수 있습니다."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/11/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6edf0ac1-4f46-4543-a9e5-f484ac37e9a5
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 75e68a49fb8437bb7742cfa1e458edab5c0b1836
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/10/2017
---
# <a name="terms-and-condition-policy-settings-in-microsoft-intune"></a>Microsoft Intune의 사용 약관 정책 설정

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

사용자 그룹에 Intune 사용 약관을 배포하여 등록, 작업 리소스 액세스, 회사 포털 앱이 장치와 사용자에 미치는 영향을 설명할 수 있습니다. 사용자는 먼저 사용 약관에 동의해야 회사 포털을 사용하여 작업 등록 및 액세스를 수행할 수 있습니다.

각기 다른 사용 약관을 포함하는 여러 정책을 만들어 배포할 수 있습니다. 또한 같은 버전의 사용 약관을 여러 언어로 생성한 다음 적합한 그룹에 배포할 수도 있습니다.

## <a name="create-a-terms-and-conditions-policy"></a>사용 약관 정책을 만들기

1.  [Microsoft Intune 관리 콘솔](https://manage.microsoft.com)에서 **정책** &gt; **사용 약관**을 클릭합니다.

    ![사용 약관 정책 스크린샷](./media/pol-sa-terms-conditions.png)

2.  **추가**를 클릭하여 새 사용 약관 정책을 만듭니다.

    기존 정책을 **편집**하거나 **삭제**할 수도 있습니다.

3.  **사용 약관 만들기** 페이지에서 다음 정보를 지정합니다.

    -   **이름**&mdash;Intune 콘솔에 표시되는 고유한 정책 이름

    -   **설명**&mdash;Intune 콘솔에서 정책을 식별하는 데 사용할 수 있는 세부 정보

    -   **제목**&mdash;회사 포털에 표시되는 제목

    -   **사용자가 동의하는 경우 그 의미를 설명하는 텍스트**&mdash;사용 약관 동의와 관련하여 사용자에게 표시되는 레이블. 예: "사용 약관에 동의함"

4.  작업을 마쳤으면 **저장**을 클릭합니다. 새 정책이 **정책** 작업 영역의 **사용 약관** 노드에 표시됩니다.

## <a name="deploy-a-terms-and-conditions-policy"></a>사용 약관 정책 배포

1.  [Microsoft Intune 관리 콘솔](https://manage.microsoft.com)에서 **정책** &gt; **사용 약관**을 클릭합니다.

2.  **사용 약관 정책** 목록에서 배포할 정책을 선택하고 **배포 관리**를 클릭합니다.

3.  **배포 관리** 대화 상자에서 정책을 배포할 사용자 그룹을 선택하고 **확인**을 클릭합니다.

    대상 사용자가 회사 포털에 액세스하면 배포한 사용 약관이 Intune에 표시됩니다. 사용자는 해당 약관에 동의해야 회사 리소스에 액세스할 수 있습니다.

## <a name="monitor-a-terms-and-conditions-policy"></a>사용 약관 정책 모니터링

1.  [Microsoft Intune 관리 콘솔](https://manage.microsoft.com)에서 **정책** &gt; **사용 약관**을 클릭합니다.

2.  **새 보고서 만들기** 창에서 **보고서 보기**를 클릭합니다. 배포한 사용 약관에 동의한 사용자의 세부 정보를 보여 주는 보고서가 열립니다.

### <a name="updates-and-version-control-for-terms-and-conditions"></a>사용 약관 업데이트 및 버전 제어
기존 사용 약관 정책을 편집하는 경우 정책을 배포할 때 발생하는 동작을 선택할 수 있습니다. 다음 절차에 따라 기존 사용 약관 정책을 업데이트할 수 있습니다.

## <a name="work-with-multiple-versions-of-terms-and-conditions"></a>여러 버전의 사용 약관 사용

1.  [Microsoft Intune 관리 콘솔](https://manage.microsoft.com)에서 **정책** &gt; **사용 약관**을 클릭합니다.

2.  편집할 사용 약관 정책을 선택하고 **편집**을 클릭합니다.

3.  **사용 약관 편집** 페이지에서 필요한 사항을 편집한 다음 모든 사용자가 이 새 버전의 사용 약관에 동의해야 하는지, 아니면 신규 사용자에게만 새 버전을 표시할지를 지정합니다.

    사용 약관 정책을 크게 변경할 때마다 버전 번호를 높이고 동의를 요구하는 것이 좋습니다. 오타를 수정하거나 서식을 변경하는 등의 경우에는 현재 버전 번호를 유지합니다.

### <a name="see-also"></a>참고 항목
[Microsoft Intune 정책을 사용하여 장치의 설정 및 기능 관리](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
