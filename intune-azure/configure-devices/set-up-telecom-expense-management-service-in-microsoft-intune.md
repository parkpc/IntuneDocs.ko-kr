---
title: "Telecom Expense Management 서비스 설정 | Intune Azure 미리 보기 | Microsoft Docs"
description: "Intune Azure 미리 보기: Intune과 통합되도록 Saaswedo Telecom Expense Management 서비스 구성"
keywords: Saaswedo
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 01/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b7bf5802-4b65-4aeb-ac99-8e639dd89c2a
ms.reviewer: sumitp
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 915d61344a3c1d388305dd51b1e2463bd2e32770
ms.openlocfilehash: 8d94fec099e1dc8918077062fb73b94a5973ea96

---

# <a name="set-up-a-telecom-expense-management-service-in-intune-azure-preview"></a>Intune Azure 미리 보기에서 Telecom Expense Management 서비스 설정
[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Intune에는 타사 소프트웨어 개발자인 Saaswedo의 Datalert Telecom Expense Management 솔루션이 통합되어 있습니다. Datalert는 통신 데이터 사용량을 관리하며 Intune 관리 장치에 대해 비용이 많이 들고 예기치 않은 데이터 및 로밍 초과분을 방지할 수 있도록 해주는 실시간 Telecom Expense Management 소프트웨어입니다. Intune은 Datalert와의 통합을 통해 정의된 임계값을 초과할 경우 자동화된 경고를 사용하여 로밍 및 국내 데이터 사용량 제한을 중앙에서 설정, 모니터링 및 적용할 수 있도록 지원합니다. 사용자가 임계값을 초과한 경우 로밍을 해제하는 등 개인 또는 최종 사용자 그룹에 여러 작업을 적용하도록 서비스를 구성할 수 있습니다. Datalert 관리 콘솔에서 데이터 사용량 및 모니터링 정보를 제공하는 보고서를 사용할 수 있습니다.

Intune에서 Datalert 서비스를 사용하려면 먼저 Datalert 콘솔 및 Intune에서 설정을 구성해야 합니다. Datalert 서비스 및 Intune에 대한 연결을 설정해야 합니다. Datalert 측의 연결이 설정되었지만 Intune 측의 연결이 설정되지 않은 경우에는 Intune에서 통신을 수신하지만 이를 무시합니다.

>[!NOTE]
>평가판 테넌트에서 이 기능을 사용하도록 설정하려면 활성화의 경우 [Microsoft 지원에 문의](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune)하고 필수 소프트웨어 라이선스의 경우 Datalert 지원에 문의하세요.

## <a name="supported-platforms"></a>지원되는 플랫폼

- Samsung KNOX
- iOS 8.0 이상

## <a name="prerequisites"></a>전제 조건

- Microsoft Intune 구독
- Datalert Telecom Expense Management 서비스 구독

## <a name="list-of-telecom-expense-management-providers"></a>Telecom Expense Management 공급자 목록

Intune은 현재 다음 Telecom Expense Management 공급자와 통합되어 있습니다.

[Saaswedo Datalert Telecom Expense Management 서비스](http://www.datalert.biz/)

## <a name="configure-intune-to-work-with-the-datalert-service"></a>Datalert 서비스와 함께 작동하도록 Intune 구성

 

1. Azure 포털에 로그인합니다.
2. **추가 서비스** > **기타** > **Intune**을 선택합니다.
3. **Intune** 블레이드에서 **장치 구성**을 선택합니다.
2. **장치 구성** 블레이드에서 **설정** > **Telecom Expense Management**를 선택합니다.
2. **Telecom Expense Management** 아래에서 **연결 상태**를 선택합니다.

3. **TEM 서비스 공급자 목록**을 선택한 다음 표시된 목록에서 공급자를 선택합니다. 공급자와 관련된 페이지가 열립니다. Saaswedo의 경우 Datalert 페이지가 열립니다. 구독을 구매하려면 Saaswedo Datalert를 사용해야 합니다.

4. **Datalert** 관리 콘솔에서 다음을 수행합니다.

    a. **설정** 탭으로 이동한 다음 **MDM 구성** 섹션으로 이동합니다.

    b. 페이지에서 설정을 입력할 수 있도록 **잠금 해제**를 선택합니다.

    c. **서버 MDM**에서 **Microsoft Intune**을 선택합니다.

    d. **테 넌 트 ID**에 Intune 테넌트 ID를 입력하고 **연결** 단추를 선택합니다. **연결**을 선택하면 Datalert 서비스가 Intune에 체크 인되어 Datalert와 Intune의 기존 연결이 없는지 확인합니다. 몇 초 후 Microsoft 로그인 페이지가 표시되고 Datalert Azure 인증이 시작됩니다.

    e. Microsoft 인증 페이지에서 **동의함**을 선택합니다. Datalert "thank you." 페이지로 리디렉션됩니다. 이 페이지는 몇 초 후 닫힙니다. Datalert에서 연결의 유효성을 검사하고 유효성이 확인된 항목 목록 옆에 녹색 확인 표시를 표시합니다. 유효성 검사에 실패하면 빨간색 메시지가 표시됩니다. 이 경우 Datalert 지원에 도움을 요청하세요.

5. 몇 분 정도 기다렸다가 Azure Portal로 이동하여 연결 상태가 **활성**으로 표시되는지 확인합니다. 

    >[!NOTE]
    >평가판 테넌트에 이 기능을 사용하려면 [Microsoft 지원에 문의](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune)하세요.

6. Datalert 관리 콘솔로 돌아가 데이터 행을 구성합니다.

    a. **설정** 탭으로 이동합니다.

    b. **설정** 마법사로 이동하여 마법사의 단계를 따릅니다.



이제 Datalert 서비스가 활성화되어 데이터 사용량을 모니터링하고 구성된 사용량 제한을 초과한 장치에서 셀룰러 및 로밍 데이터를 해제하는 등의 작업을 시작합니다.

## <a name="turning-off-the-datalert-service"></a>Datalert 서비스 해제

Azure Portal에서 Datalert 서비스를 해제한 경우

- 이전의 사용량 제한 위반으로 인해 장치에 적용된 모든 작업이 실행 취소됩니다.
- 사용자의 데이터 액세스 및 로밍이 더 이상 차단되지 않습니다.
- Intune에서는 서비스에서 들어오는 신호를 계속 수신하지만 이를 무시합니다.

**서비스를 해제하려면**

1. Azure Portal의 **Telecom Expense Management** 블레이드에서 **사용 안 함**을 선택합니다.

2. **저장**을 선택합니다.

## <a name="viewing-data-usage-and-roaming-reports"></a>데이터 사용량 및 로밍 보고서 보기

이 시점에서는 데이터 사용량 보고를 Saaswedo의 Datalert 관리 콘솔에서만 사용할 수 있습니다.



<!--HONumber=Feb17_HO2-->


