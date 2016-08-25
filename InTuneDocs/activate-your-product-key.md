---
title: "제품 키 활성화 | Microsoft Intune"
description: "제품 키를 사용하여 Intune 구독을 하거나 기존 구독에 사용자를 추가할 수 있습니다."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 844c2ca8-2721-4f72-b1dd-be9b1da1f220
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6716a3d1fb53dc3de0189f637d5664d0a2023d05
ms.openlocfilehash: 36cec469166ebaac2def784fa3134dd56587f52a


---

# 제품 키 활성화
제품 키를 사용하여 구독을 하거나 기존 구독에 사용자를 추가할 수 있습니다. 제품 키는 구독을 하거나, 온라인 서비스에 액세스하거나, 소프트웨어를 다운로드하는 데 필요한 25자로 된 고유한 영숫자 코드입니다. Microsoft 파트너 또는 대리점에서 제품 키를 구입할 수 있습니다.

## 제품 키 사용
제품 키를 사용하려면 25자리 코드를 입력합니다.

-   [!INCLUDE[wit_firstref](./includes/wit_firstref_md.md)] 제품 키를 활성화하려면 [여기](https://account.manage.microsoft.com/commerce/productkeystart.aspx)로 이동합니다.

-   Enterprise Mobility Suite 제품 키를 활성화하려면 [여기](http://www.microsoft.com/ems/open)로 이동합니다.

> [!NOTE]
> 제품 키를 분실한 경우 구입한 파트너 또는 대리점에 문의하세요.

## System Center Configuration Manager 소프트웨어 다운로드
System Center Configuration Manager 소프트웨어를 다운로드하려면 [볼륨 라이선스 서비스 센터](http://go.microsoft.com/fwlink/?LinkID=232300)로 이동합니다.

## 제품 키를 입력할 때 발생하는 문제 해결

|오류 메시지|해결 방법|
|-----------------|--------------|
|**입력한 제품 키가 올바르지 않습니다. 다시 입력하세요.** 또는 **이 제품 키가 올바르지 않습니다. 다른 제품 키를 입력하세요**.|입력하는 숫자와 문자를 주의 깊게 확인합니다. 문자 또는 숫자를 혼동할 수 있습니다(예: "O"와 0, “S”와 5 등). 문제가 지속되면 제품 키를 구매한 대리점에 문의하세요.|
|**이 제품 키를 이미 입력했습니다. 다른 키를 입력하세요**.|이미 입력한 제품 키를 확인하여 키가 아직 추가되지 않았는지 검토합니다. 문제가 계속되면 [고객 지원 담당자](http://go.microsoft.com/fwlink/?LinkID=394189)에게 문의하세요.|
|**입력한 제품 키가 만료되었습니다. 다른 키를 입력하세요**.|[고객 지원 담당자](http://go.microsoft.com/fwlink/?LinkID=394189)에게 문의하세요.|
|**입력한 제품 키가 이미 사용되었습니다. 다른 제품 키를 입력하세요**.|입력한 제품 키가 이미 사용되었습니다. 사용자나 조직의 멤버가 키를 이미 사용하지 않았는지 확인하세요. 키가 아직 사용되지 않은 경우 제품 키를 구입한 대리점에 문의하세요.|
|**죄송합니다. 지금은 요청을 처리할 수 없습니다. 잠시 기다린 후 다시 시도하세요**.|다시 시도해도 15분 넘게 동일한 오류 메시지가 표시되면 [고객 지원 담당자](http://go.microsoft.com/fwlink/?LinkID=394189)에게 문의하세요.|
|**요청된 구독을 사용할 수 없습니다. 다음 중 하나가 원인일 수 있습니다. 제품을 사용할 수 없습니다. - 국가에서 서비스가 제공되지 않습니다. - 동일한 평가판을 두 번 이상 사용/선택할 수 없습니다. 문제가 지속되면 Microsoft 지원에 문의하세요**.|[고객 지원 담당자](http://go.microsoft.com/fwlink/?LinkID=394189)에게 문의하세요.|
|**이 제안이 허용하는 것보다 많은 사용자 라이선스를 추가했습니다. 최대 사용자 라이선스 수는 10,000,000입니다. 이 제품 키를 제거하고 더 적은 수의 사용자 라이선스를 추가하는 제품 키를 입력하세요**.|대리점 또는 파트너에 문의하세요. 이 계정으로 사용할 수 있는 것보다 많은 라이선스를 구입했습니다.|
|**제품 키를 사용하려면 전역 또는 대금 청구 관리자여야 합니다**.|권한이 대금 청구 또는 전역 관리자로 설정되어 있어야 합니다. 이를 확인하려면 관리자 콘솔에서 **관리자** &gt; **설정**을 클릭합니다.|
|**죄송합니다. 지금은 계정을 만들 수 없습니다. 잠시 기다린 후 다시 시도하세요**.|문제가 계속되면 [고객 지원 담당자](http://go.microsoft.com/fwlink/?LinkID=394189)에게 문의하세요.|
|**죄송합니다. 주문을 처리할 수 없습니다**.|테넌트를 만들었지만, 제품 키가 사용되지 않았습니다. 위에 제공된 링크를 사용하여 제품 키를 다시 사용하세요. 문제가 계속되면 [고객 지원 담당자](http://go.microsoft.com/fwlink/?LinkID=394189)에게 문의하세요.|



<!--HONumber=Jul16_HO4-->


