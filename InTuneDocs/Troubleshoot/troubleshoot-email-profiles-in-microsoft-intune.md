---
# required metadata

title: 전자 메일 프로필 문제 해결 | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f5c944ea-32a6-48af-bb57-16d5f1f3c588

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune에서 전자 메일 프로필 문제 해결
여기에서는 일부 메일 프로필 문제와 이 문제를 해결하는 방법을 제공합니다.

이 정보로 문제가 해결되지 않는 경우 [Microsoft Intune에 대한 지원을 받는 방법](how-to-get-support-for-microsoft-intune.md)을 참조하여 도움을 얻을 수 있는 다른 방법을 찾아보세요.


## 전자 메일 계정에서 이미지를 보낼 수 없습니다.
자동으로 구성된 전자 메일 계정의 사용자는 자신의 장치에서 그림이나 이미지를 보낼 수 없습니다.
**Allow e-mail to be sent from third-party applications**(타사 응용 프로그램에서 전자 메일을 보내도록 허용) 옵션이 활성화되지 않은 경우에 이런 일이 발생합니다.

### Intune 솔루션

1.  Microsoft Intune 관리 콘솔을 열고 **정책** 작업 &gt; **구성 정책**을 선택합니다..

2.  메일 프로필을 선택하고 **편집**을 클릭합니다..

3.  **Allow e-mail to be sent from third-party applications**(타사 응용 프로그램에서 전자 메일을 보내도록 허용)을 선택합니다.

### Intune 솔루션과 통합된 Configuration Manager

1.  Configuration Manager 콘솔 &gt; **자산 및 호환성**을 엽니다..

2.  **개요** -&gt; **호환성 설정** -&gt; **회사 리소스 액세스**를 확장하고 **전자 메일 프로필**을 선택합니다..

3.  전자 메일 프로필을 마우스 오른쪽 단추로 클릭하고 **속성**을 엽니다..

4.  **동기화 설정** 탭에서 **Allow e-mail to be sent from third-party applications**(타사 응용 프로그램에서 전자 메일을 보내도록 허용)을 선택합니다..

## 다음 단계
문제 해결 정보가 도움이 되지 않는 경우 [Microsoft Intune에 대한 지원을 받는 방법](how-to-get-support-for-microsoft-intune.md)의 설명에 따라, Microsoft 지원에 문의하세요..


<!--HONumber=May16_HO1-->


