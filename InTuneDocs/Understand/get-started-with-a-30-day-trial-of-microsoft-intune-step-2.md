---
title: "Intune의 30일 평가판에 사용자 추가 | Microsoft Intune"
description: "Intune 무료 30일 평가판을 등록할 때 사용자를 개별적으로 또는 일괄적으로 추가하는 방법"
keywords: 
author: lindavr
manager: angrobe
ms.date: 08/09/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9e40999b-46f7-447b-8974-72af82bec7ef
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 51fba2b01d8978bc062c50c4388714609be0fdf0
ms.openlocfilehash: 4276d0fed0fc30490a640a067d78096ff0cf78ae


---

# Microsoft Intune의 30일 평가판에 사용자 추가
계정을 설정했으므로 이제 **새 사용자** 마법사로 Intune에 개별 사용자 계정을 추가하거나 **사용자 일괄 추가** 마법사로 여러 사용자를 일괄 추가할 수 있습니다(이 섹션의 지침 참조).  시작하기 전에 Intune에서 관리자 계정을 처리하는 방법을 이해하는 것이 중요합니다.

테넌트 관리자는 Office 365 관리 센터를 사용하여 Microsoft Intune **사용자 그룹**에 사용자를 추가할 수 있습니다. 사용자를 **사용자 그룹** 에 추가하는 것은 사용자에게 Intune 구독 라이선스를 할당하는 것이며, 이러한 사용자가 Microsoft Intune 관리 콘솔에 표시되도록 만드는 것이기도 합니다.

Intune의 관리자 계정은 일반 사용자 계정과 달리 Office 365 관리 센터에서 생성되지 않습니다. 대신 **관리자 관리**의 **관리** 작업 영역에서 관리 콘솔을 사용하여 사용자에게 읽기 전용 액세스 또는 완전한 액세스 관리 권한을 할당할 수 있습니다. 읽기 전용 액세스 권한을 할당 받은 서비스 관리자는 Intune 설정을 변경할 수 없으며, 데이터를 보고 보고서를 실행할 수만 있습니다. 전체 액세스 권한이 있는 서비스 관리자는 사용 가능한 모든 관리 권한을 가집니다.

Intune 관리 콘솔을 사용하여 테넌트 관리자 정보를 볼 수는 있지만 여기에서 테넌트 관리자를 만들 수는 없습니다. 기본적으로 구독 소유자가 Microsoft Intune 서비스에 대한 테넌트 관리자가 되며, Office 365 관리 센터 및 Intune 관리 콘솔 모두에 대한 모든 권한을 가집니다. Office 365 관리 센터를 사용하여 하나 이상의 추가적인 테넌트 관리자 계정을 만들어 작업을 위임하고, 암호를 잊었을 때 Intune 서비스 관리 계정이 잠기는 것을 방지하는 것이 좋습니다.

## 개별 사용자 계정 추가
다음 단계를 사용하여 평가판 테넌트에 추가 사용자 계정을 만들 수 있습니다. 추가한 각 사용자 계정은 Intune 무료 평가판의 일부로 받은 100개의 라이선스 중 하나로 계산됨을 기억하십시오.

1.  [Office 365 관리 센터](http://go.microsoft.com/fwlink/?LinkID=787455)에서 **사용자 추가** &gt; **새로 만들기** &gt; **사용자**를 선택하여 **새 사용자** 마법사를 시작합니다.

2.  **세부 정보** 페이지에서 필수 필드를 입력합니다.

3.  **설정** 페이지에서 사용자의 **위치**를 설정합니다.

4.  **그룹** 페이지에서 **다음**을 선택하여 기본값을 그대로 사용하고 해당 사용자 계정에 Intune의 라이선스를 할당합니다.

5.  **전자 메일** 페이지에서 사용자 이름 및 계정의 임시 암호에 대한 알림을 받을 전자 메일 주소를 5개까지 지정합니다. 여러 전자 메일 주소는 세미콜론(;)으로 구분합니다. 완료되면 **만들기**를 선택하여 사용자를 구독에 추가합니다.

6.  **결과** 페이지에서 새 계정 이름 및 임시 암호를 확인할 수 있습니다. Intune은 임시 암호를 자동으로 만듭니다.

7.  새 사용자가 Office 365 관리 센터에 표시되면, 새 사용자가 성공적으로 생성되었는지 확인합니다.

    1.  [Intune 관리 콘솔](https://manage.microsoft.com/)에서 **관리자** &gt; **회사 포털**을 선택한 후 화면 아래로 스크롤합니다. **Intune 회사 포털**에 표시된 URL을 복사합니다.

    2.  "개인 정보 모드"(Internet Explorer에서는 **도구** &gt; **InPrivate 브라우징** 선택)로 새 브라우저 창을 열거나 다른 장치에서 새 브라우저 창을 연 후 이전 단계에서 복사한 URL로 이동합니다. 사용자가 처음으로 로그인하는 경우 계정의 새 암호를 입력해야 합니다.

## 사용자 일괄 추가
Intune에 여러 사용자를 일괄 추가하려면 **사용자 일괄 추가** 마법사를 사용하여 사용자 데이터가 포함된 CSV(쉼표로 구분된 값) 파일을 업로드합니다. 마법사의 링크를 사용하여 빈 템플릿 및 샘플 CSV 파일을 다운로드할 수 있습니다. CSV 파일의 첫 행에는 각 사용자 데이터 열 레이블이 올바른 순서대로 포함되어야 합니다. 그런 다음 CSV 파일에 각 사용자의 **사용자 이름** (예: **bob@contoso.com**) 및 **표시 이름** (예: **Bob Kelly**)을 포함해야 합니다.

1.  [Office 365 관리 센터](http://go.microsoft.com/fwlink/?LinkID=787455)에서 **사용자** &gt; **새로 만들기**를 선택합니다.

2.  **일괄 추가**를 선택하여 사용자 일괄 추가 마법사를 시작합니다.

3.  **파일 선택** 페이지에서 **찾아보기**를 선택하여 컴퓨터에서 기존 CSV 파일을 지정하여 업로드합니다. 마법사의 링크를 사용하여 샘플 CSV 파일이나 빈 템플릿 파일을 다운로드할 수도 있습니다.

4.  **확인** 페이지에서 결과를 검토한 후 자세한 내용을 보려면 **보기**를 선택합니다.

5.  **설정** 페이지에서 로그인 상태가 **허용**인지 확인하고 **위치**를 설정합니다. 이러한 설정은 CSV 파일에서 추가한 모든 사용자 계정에 적용됩니다.

6.  **그룹** 페이지에서 **다음**을 선택하여 기본값을 그대로 사용하고 CSV 파일로 추가된 모든 사용자 계정에 Intune용 라이선스를 할당합니다. 기본적으로 각 계정에 Intune의 라이선스를 할당하는 확인란이 선택되어 있습니다.

7.  **전자 메일** 페이지에서 Intune이 각 계정에 대해 만든 사용자 이름 및 임시 암호에 대한 알림을 받을 전자 메일 주소를 5개까지 지정합니다. 여러 전자 메일 주소는 세미콜론(;)으로 구분합니다. **만들기**를 선택하여 사용자를 구독에 추가합니다.

8.  **결과** 페이지에서 각 사용자 계정에 대한 계정 이름 및 임시 암호를 확인할 수 있습니다.

가져오기를 통해 추가한 각 사용자 계정이 이제 Office 365 관리 센터의 **사용자** 노드에 표시됩니다. 새 사용자가 처음으로 로그인할 때는 자신의 계정에 대한 새 암호를 지정해야 합니다.

### 다음 단계
축하합니다. *Microsoft Intune 평가판* 연습의 2단계를 완료했습니다.

>[!div class="step-by-step"]

>[&larr; **평가판 등록**](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-1.md)     [**그룹 만들기** &rarr;](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-3.md)  



<!--HONumber=Aug16_HO2-->


