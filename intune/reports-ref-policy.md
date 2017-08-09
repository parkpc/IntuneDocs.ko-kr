---
title: "정책 | Microsoft 문서"
description: "Intune 데이터 웨어하우스 API에서 엔터티 컬렉션의 정책 범주에 대한 항목을 참조하세요."
keywords: "Intune 데이터 웨어하우스"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: D5ADB9D8-D46A-43BD-AB0F-D6927508E3F4
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6af0ff1f463c153e62f6df63ce811076c5f692f2
ms.sourcegitcommit: addf6a40caa22c22adfd2e2eff7d666cd1877e3c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/04/2017
---
# <a name="reference-for-policy-entities"></a>정책 엔터티에 대한 참조

**정책** 범주는 다음과 같은 정보를 추적하는 모바일 장치에 대한 엔터티를 포함합니다.

  -  장치 구성 프로필, 앱 구성 프로필 및 규정 준수 정책의 인벤토리  
  -  하루에 성공, 보류, 실패, 또는 오류 상태에 있는 장치의 수  
  -  하루에 성공, 보류, 실패, 또는 오류 상태에 있는 사용자의 수  
  -  성공, 보류, 실패, 또는 오류 상태에 있는 장치의 누적 수  

## <a name="policy"></a>정책

**정책** 엔터티는 장치 구성 프로필, 앱 구성 프로필 및 규정 준수 정책을 나열합니다. 정책을 MDM(Mobile Device Management)을 통해 기업 내 그룹에 할당할 수 있습니다.

| 속성  | 설명 | 예 |
|---------|------------|--------|
| PolicyKey |데이터 웨어하우스에서 정책을 나타내는 고유 키 |123 |
| PolicyId |데이터 웨어하우스에서 정책의 고유 식별자 |b66bc706-ffff-7437-0340-032819502773 |
| PolicyName |정책 이름 |"Windows 10 Baseline" |
| PolicyVersion |정책 버전 정책이 편집, 변경되었거나 새 버전이 만들어진 날짜입니다. |1, 2, 3 |
| IsDeleted |정책 레코드가 업데이트되었는지 나타냅니다.  True - 정책에 업데이트된 필드를 포함한 새 레코드가 있습니다. False- 정책에 대한 최신 레코드입니다. |True/False |
| StartDateInclusiveUTC |데이터 웨어하우스에서 정책이 만들어진 UTC 날짜 및 시간 |11/23/2016 12:00:00 AM |
| DeletedDateUTC |IsDeleted가 True로 변경된 UTC 날짜 및 시간 |11/23/2016 12:00:00 AM |
| RowLastModifiedDateTimeUTC |데이터 웨어하우스에서 정책이 마지막으로 수정된 UTC 날짜 및 시간 |11/23/2016 12:00:00 AM |

## <a name="policytype"></a>PolicyType

**PolicyType** 엔터티는 장치 구성 프로필, 앱 구성 프로필 및 규정 준수 정책 유형을 나열합니다. 정책을 MDM(Mobile Device Management)을 통해 기업 내 그룹에 할당할 수 있습니다.

| 속성  | 설명 | 예 |
|---------|------------|--------|
| PolicyTypeId |원본 시스템에서 정책의 고유 식별자 |123 |
| PolicyTypeKey |데이터 웨어하우스에서 정책의 고유 식별자 |1 |
| PolicyTypeName |정책 형식의 이름입니다. |Windows 10 규정 준수 정책 |

## <a name="deviceconfiguration"></a>DeviceConfiguration

**DeviceConfigurationProfileDeviceActivity** 엔터티는 하루에 성공, 보류, 실패 또는 오류 상태에 있는 장치의 수를 나열합니다. 숫자는 엔터티에 할당된 장치 구성 프로필을 반영합니다. 예를 들어 장치가 모든 할당된 정책에 대해 성공 상태에 있으면 그 날에 대해 성공 카운터를 1만큼 높입니다. 장치에 두 프로필이 할당된 경우(성공 상태에 하나, 오류 상태에 하나) 엔터티는 성공 카운터를 하나 늘리고 장치를 오류 상태에 놓습니다. 엔터티는 지난 30일 동안 특정 날짜에 해당 상태에 있는 장치가 몇 개인지 표시합니다.

| 속성  | 설명 | 예 |
|---------|------------|--------|
| DateKey |데이터 웨어하우스에서 장치 구성 프로필 체크인이 기록된 날짜 키 |20160703 |
| Pending |보류 상태에 있는 고유 장치 수 |123 |
| 성공 |성공 상태에 있는 고유 장치 수 |12 |
| 오류 |오류 상태에 있는 고유 장치 수 |10 |
| Failed |실패 상태에 있는 고유 장치 수 |2 |

## <a name="userconfiguration"></a>UserConfiguration

**UserConfigurationProfileDeviceActivity** 엔터티는 하루에 성공, 보류, 실패, 오류 상태에 있는 사용자 수를 표시합니다. 숫자는 엔터티에 할당된 장치 구성 프로필을 반영합니다. 예를 들어 사용자가 모든 할당된 정책에 대해 성공 상태에 있으면 해당 날짜에 대한 성공 카운터를 1만큼 높입니다. 사용자에게 두 프로필이 할당된 경우(하나는 성공 상태, 하나는 오류 상태) 오류 상태의 사용자를 카운트합니다.  **UserConfigurationProfileDeviceActivity** 엔터티는 지난 30일 동안 특정 날짜에 해당 상태에 있는 사용자 수를 표시합니다.

| 속성  | 설명 | 예 |
|---------|------------|--------|
| DateKey |데이터 웨어하우스에서 장치 구성 프로필 체크인이 기록된 날짜 키 |20160703 |
| Pending |보류 상태에 있는 고유 사용자 수 |123 |
| 성공 |성공 상태에 있는 고유 사용자 수 |12 |
| 오류 |오류 상태에 있는 고유 사용자 수 |10 |
| Failed |실패 상태에 있는 고유 사용자 수 |2 |

## <a name="policytypeactivity"></a>PolicyTypeActivity

**PolicyTypeActivity** 엔터티는 성공, 보류, 실패 또는 오류 상태에 있는 장치의 누적 수를 표시합니다. 하루의 장치 구성 프로필, 앱 구성 프로필, 규정 준수 정책에 대한 상태를 표시합니다.

| 속성  | 설명 | 예 |
|---------|------------|--------|
| DateKey |데이터 웨어하우스에서 장치 구성 프로필 체크인이 기록된 날짜 키 |20160703 |
| PolicyKey |정책 키. 정책과 결합하여 policyName을 가져올 수 있음 |Windows 10 기준 |
| PolicyTypeKey |정책 키 유형. 정책 유형과 결합하여 정책 유형 이름을 가져올 수 있음 |Windows10Compliance 정책 |
| Pending |보류 상태에 있는 고유 장치 수 |123 |
| 성공 |성공 상태에 있는 고유 장치 수 |12 |
| 오류 |오류 상태에 있는 고유 장치 수 |10 |
| Fail- |실패 상태에 있는 고유 장치 수 |2 |