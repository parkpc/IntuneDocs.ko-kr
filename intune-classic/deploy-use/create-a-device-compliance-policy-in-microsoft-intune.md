---
title: 장치 준수 정책 만들기
description: 규정 준수 정책을 만들어 회사 데이터에 액세스하는 데 사용하는 모바일 장치 및 PC 보안을 유지합니다.
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 10/12/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5336dac0-a2cc-4cd4-8511-67e4f95bd700
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ed6f66747364debd89661d78bcf3b002b1c8a9b6
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="create-a-device-compliance-policy-in-microsoft-intune"></a>Microsoft Intune에서 장치 규정 준수 정책 만들기

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

이 항목에서는 호환되는 것으로 간주하기 위해 따라야 하는 규정 준수 정책을 만드는 데 사용할 수 있는 단계를 간략히 설명합니다.

##  <a name="step-1-add-a-new-policy"></a>1단계: 새 정책 추가
  [Microsoft Intune 관리 콘솔](https://manage.microsoft.com)에서 **정책** &gt; **준수 정책** &gt; **추가**를 선택합니다.

  ![Intune 관리 콘솔의 페이지 맨 위에 있는 메뉴에서 추가 옵션을 보여주는 규정 준수 정책 페이지의 스크린 샷](./media/intune-sa-3a-add-compliance-policy.png)

##  <a name="step-2--configure-settings"></a>2단계: 설정 구성
**정책 만들기** 페이지에서 필요한 설정을 사용합니다.
  -   암호 및 암호화와 같은 시스템 보안 설정
  -   Windows 장치 상태 증명 서비스에서 장치를 무단 해제 또는 정상으로 보고하는지 여부와 같은 장치 상태 설정
  -   필요한 최소 운영 체제 버전 또는 허용된 최대 운영 체제 버전과 같은 장치 속성 설정
![정책 만들기 페이지의 일반 탭](./media/intune-sa-3b-create-policy.png)


##  <a name="step-3-save-the-policy"></a>3단계: 정책 저장
작업이 끝나면 **정책 저장**을 선택합니다.

정책을 저장한 후에 바로 배포하는 옵션이 있고 나중에 배포하도록 선택할 수도 있습니다. 새 정책이 **정책** 작업 영역의 **준수 정책** 노드에 표시됩니다.

##  <a name="step-4-set-the-compliance-status-validity-period"></a>4단계: 준수 상태 유효 기간 설정
장치가 규정을 준수하지 않는 것으로 간주되기까지 장치를 체크 인해야 하는 시간을 지정하려면 준수 정책 설정으로 이동한 후 시간을 업데이트합니다. 기본값은 30일로 설정되어 있습니다.

![정책 메뉴 모음의 규정 준수 정책 설정 옵션](../media/mdm-compliance-policy-settings.png)

![규정 준수 정책 대화 상자](../media/mdm-ca-compliance-status-validity-period.png)

## <a name="supported-policy-settings"></a>지원되는 정책 설정
다음 테이블에서는 규정 준수 정책 설정 및 해당 사항이 지원되는 플랫폼을 나열합니다.

-------------

|Setting|iOS|Android|Windows|
|-----|----|-----|-----|
|모바일 장치의 잠금을 해제하는 데 암호 필요|iOS 6 이상|Android 4.0 이상 <br>Samsung KNOX Standard 4.0 이상|Windows Phone 8.1 이상|
|단순 암호 허용|iOS 6 이상|지원되지 않음|Windows Phone 8.1 이상|
|최소 암호 길이|iOS 6 이상| Android 4.0 이상<br>Samsung KNOX Standard 4.0 이상| Windows Phone 8.1 이상<br>Windows 8.1|
|필수 암호 유형|iOS 6 이상|사용할 수 없음|Windows Phone 8.1 이상 <br>Windows RT<br> Windows RT 8.1 <br>Windows 8.1|
|최소 문자 집합 수|iOS 6 이상|사용할 수 없음|Windows Phone 8.1 이상 <br>Windows RT<br> Windows RT 8.1 <br>Windows 8.1|
|암호 품질|사용할 수 없음|Android 4.0 이상 <br>Samsung KNOX Standard 4.0 이상|사용할 수 없음|
|암호를 요구하기 전까지 비활성 시간(분)|iOS 6 이상|Android 4.0 이상<br>Samsung KNOX Standard 4.0 이상|Windows Phone 8.1 이상<br>Windows RT 및 Windows RT 8.1<br>Windows 8.1|
|암호 만료(일)|iOS 6 이상|Android 4.0 이상<br>Samsung KNOX Standard 4.0 이상|Windows Phone 8.1 이상<br>Windows RT 및 Windows RT 8.1<br>Windows 8.1|
|암호 기록 기억|iOS 6 이상|Android 4.0 이상<br>Samsung KNOX Standard 4.0 이상|Windows Phone 8.1 이상<br>Windows RT 및 Windows RT 8.1<br>Windows 8.1|
|이전 암호 다시 사용 방지|iOS 6 이상|Android 4.0 이상<br>Samsung KNOX Standard 4.0 이상|Windows Phone 8.1 이상<br>Windows RT 및 Windows RT 8.1<br>Windows 8.1|
|장치가 유휴 상태에서 되돌아오는 경우 암호 필요| 사용할 수 없음| 사용할 수 없음|Windows 10 Mobile|
|모바일 장치 암호화 필요|해당 없음|Android 4.0 이상<br>Samsung KNOX Standard 4.0 이상|Windows Phone 8.1 이상<br> Windows 8.1|
|정상으로 보고되는 장치 필요| 사용할 수 없음| 사용할 수 없음|Windows <br>Windows 10 Mobile|
|장치는 탈옥 또는 루팅되지 않아야 함|iOS 6 이상|Android 4.0 이상<br>Samsung KNOX Standard 4.0 이상|사용할 수 없음|
|전자 메일 계정은 Intune을 통해 관리해야 함|iOS 6 이상|사용할 수 없음| 사용할 수 없음|
|Intune으로 관리해야 하는 전자 메일 프로필 선택|iOS 6 이상|사용할 수 없음| 사용할 수 없음|
|필요한 최소 OS|iOS 6 이상|Android 4.0 이상<br>Samsung KNOX Standard 4.0 이상| Windows Phone 8.1 이상<br>Windows 8.1|
|허용된 최대 OS 버전|iOS 6 이상|Android 4.0 이상<br>Samsung KNOX Standard 4.0 이상|Windows Phone 8.1 이상<br>Windows 8.1|

각 플랫폼에서 지원되는 규정 준수 설정에 대한 자세한 내용을 보려면 다음 중 하나를 선택합니다.
> [!div class="op_single_selector"]
> - [iOS 장치용 규정 준수 정책 설정](ios-compliance-policy-settings-in-microsoft-intune.md)
> - [Android 장치용 규정 준수 정책 설정](android-compliance-policy-settings-in-microsoft-intune.md)
> - [Windows 및 Windows Phone용 규정 준수 정책 설정](windows-compliance-policy-settings-in-microsoft-intune.md)


## <a name="next-steps"></a>다음 단계
[규정 준수 정책 배포 및 모니터링](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md)

### <a name="see-also"></a>참고 항목
[장치 규정 준수 정책 소개](introduction-to-device-compliance-policies-in-microsoft-intune.md)
