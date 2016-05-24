---
# required metadata

title: 응용 프로그램 출시 | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 0fc32ed3-bcf4-472a-80e7-eb20986f78fa

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# 응용 프로그램 출시
이 항목에서는 Microsoft Intune에서 앱의 단계적 출시에 대한 특정한 권장 사항을 제공합니다. 출시 단계에 대한 일반 정보는 [Microsoft Intune 배포에 대한 출시 단계](rollout-phases-for-microsoft-intune-deployment.md)를 참조하세요..

### 앱 출시 단계
앱 출시 단계는 다음과 같습니다.

-   프로젝트 범위

-   개념 증명

-   파일럿

-   전사적 출시

-   운영 및 유지 관리

## 프로젝트 범위
다음 사항을 고려합니다.

-   앱의 사용자 작업을 사용할 수 있는지 확인합니다.

-   사용자 및 해당 장치(사용할 수 있는 모든 운영 체제)에 대한 앱의 적합성을 확인합니다.

-   [Microsoft Intune을 사용하여 앱 추가](/intune/deploy-use/add-apps)에 설명된 대로 선택한 앱에 대한 설치 관리자가 Intune 앱 배포에서 지원되는지 확인합니다..

-   앱 배포 필수 구성 요소가 설치되어 있는지 확인합니다. <!---, as described in [Plan for app deployment in Microsoft Intune](plan-for-app-deployment-in-microsoft-intune.md--->).

-   앱 형식이 Intune에서 지원되는지 확인합니다.

-   앱을 업로드할 수 있는 충분한 클라우드 저장소 공간이 있는지 확인합니다. [Microsoft Intune을 사용하여 앱 추가](/intune/deploy-use/add-apps)에서 추가 저장소 구매를 위한 지침을 제공합니다..

## 개념 증명
개념 증명 단계에서는 테스트 목적으로 엄격하게 구성된 장치 및 사용자의 실험 환경에서 앱 배포를 테스트 합니다.

-   지원 센터가 이 단계에 참여하여 테스트 및 프로덕션 배포에서 발생할 수 있는 문제를 알아봅니다. 문제 해결 정보는 [Microsoft Intune에서 앱 배포 문제 해결](/intune/troubleshoot/troubleshoot-app-deployment-problems-in-microsoft-intune)에서 지원합니다..

-   이 시점에서는 프로세스에서 파일럿 및 프로덕션 사용자에 대한 통신 계획을 개발해야 합니다. 이 계획은 최소한 배포되는 앱, 사용자가 앱을 사용하는 방법 및 시기, 배포하는 비즈니스 용도 및 자가 진단 정보와 지원 센터에 연락하는 방법 등 문제 발생 시 수행할 작업을 포함해야 합니다.

## 파일럿
파일럿 중에 작은 그룹의 테스트 사용자 및 장치에 앱을 배포합니다. 다음 사항을 고려합니다.

-   테스트 그룹이 제품 출시 이후 앱을 사용하는 사용자 및 장치를 대표하도록 합니다.

-   앱 배포에 대한 지원 센터를 교육하고 테스트 그룹의 사용자를 돕도록 준비시킵니다.

-   일반적으로 앱을 사용하고 파일럿 관리자에게 안정적으로 문제를 보고하는 테스트 사용자를 선택합니다.

-   파일럿 사용자 통신 계획을 활성화합니다.

## 엔터프라이즈 출시

-   파일럿 결과를 사용하여 엔터프라이즈 출시를 조정할 수 있습니다.

-   앱 출시 일정을 지원 센터에 알립니다. 요청을 도와주고 필요에 따라 배포를 조정하는 작업을 충족하는 메커니즘이 필요합니다.

-   문제가 발생하는 경우 배포 문제를 해결할 준비가 되어 있습니다.

-   프로덕션 사용자 통신 계획을 활성화합니다.

-   앱 배포, 그룹 추가에 대한 증분 단계적 접근 방식을 사용하여 출시가 원활하게 진행되도록 합니다.

## 운영 및 유지 관리
**작업:** 경고 및 사용자 또는 장치 문제에 대한 Intune 콘솔을 모니터링하고 디자인에 따라 응용 프로그램 배포가 작동하는지 확인합니다.

**지원 센터:** 지원 센터는 지원 요청에서 발생할 수 있는 앱 가용성에 대한 모든 변경 내용을 인식하도록 합니다.

### 참고 항목
[앱 배포](/intune/deploy-use/deploy-apps)

[Microsoft Intune에서 앱 배포 문제 해결](/intune/troubleshoot/troubleshoot-app-deployment-problems-in-microsoft-intune)


<!--HONumber=May16_HO1-->


