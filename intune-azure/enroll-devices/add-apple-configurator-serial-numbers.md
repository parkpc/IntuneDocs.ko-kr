---
title: "Apple Configurator 일련 번호 추가 | Intune Azure 미리 보기 | Microsoft Docs"
description: "Intune Azure 미리 보기: Apple Configurator를 사용하여 회사 소유 iOS 장치에 일련 번호를 추가하는 방법을 알아봅니다."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d408aa38-7d1e-40df-9067-246e53f6e26f
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 37c56d0c219c61c345874b24e8ba9ac640f1ef76
ms.openlocfilehash: 4c2ebe535935518127a799ae0518c43a2e53de72
ms.lasthandoff: 02/17/2017


---

# <a name="add-apple-configurator-serial-numbers"></a>Apple Configurator 일련 번호 추가

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

[설정 도우미와 함께 Apple Configurator를 사용하여 회사 소유 iOS 장치를 등록](enroll-ios-devices-with-apple-configurator-and-setup-assistant.md)하려는 경우 다음 단계를 통해 Intune에 일련 번호를 추가할 수 있습니다. 일련 번호를 한 번에 하나씩 추가하거나, 일련 번호의 쉼표로 구분된 값(CSV) 파일을 업로드할 수 있습니다. 일련 번호를 추가한 후 프로필을 할당할 수 있습니다. 프로필에는 장치에 적용할 특정 관리 설정이 포함되어 있습니다.

iOS 장치를 등록하는 다른 방법은 [Intune에서 iOS 장치를 등록하는 방법 선택](choose-ios-enrollment-method.md)에 설명되어 있습니다.

**Intune에 Apple Configurator 일련 번호를 추가하려면**

1. 헤더 없이&2;열로 구성된 쉼표로 구분된 값(.csv) 목록을 만듭니다. 왼쪽 열에 IMEI 식별자를 추가하고 오른쪽 열에 세부 정보를 추가합니다. 현재 목록의 최대값은 500개 행입니다. 텍스트 편집기에 .csv 목록이 다음과 같이 표시됩니다.

    F7TLWCLBX196,장치 세부 정보</br>
   DLXQPCWVGHMJ,장치 세부 정보

2. Azure Portal에서 **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.

3.  Intune 블레이드에서 **장치 등록**을 선택한 다음 **Apple 등록**을 선택합니다.

4. **Apple Configurator 등록 설정 관리**에서 **Apple Configurator 일련 번호**를 선택합니다.

5. **Apple Configurator 일련 번호** 블레이드에서 **추가**를 선택합니다.

6. **일련 번호 추가** 블레이드에서 가져오려는 일련 번호에 적용할 프로필을 선택합니다. 기존 세부 정보를 덮어쓰는 새로운 세부 정보가 포함된 파일을 가져오려면 ‘기존 식별자에 대한 세부 정보를 덮어씁니다’를 선택하여 기존 세부 정보를 새로운 세부 정보로 바꿉니다.

7. 일련 번호의 .csv 파일로 이동하여 **추가**를 선택합니다.

## <a name="assign-a-profile-to-specific-serial-numbers"></a>특정 일련 번호에 프로필 할당

Intune을 사용하면 Azure Portal의 두 군데에서 프로필을 할당할 수 있습니다. 아래 단계를 사용하거나 Apple Configurator 등록 프로필 블레이드에서 프로필을 할당할 수 있습니다([설정 도우미를 사용하여 Apple Configurator로 iOS 장치 등록](enroll-ios-devices-with-apple-configurator-and-setup-assistant.md) 참조). 프로필을 이미 만든 경우에만 아래 단계를 사용하여 프로필을 할당할 수 있습니다.

1. Azure Portal에서 **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.

2. Intune 블레이드에서 **장치 등록**을 선택한 다음 **Apple 등록**을 선택합니다.

3. **Apple Configurator 일련 번호** 블레이드에서 프로필을 할당할 일련 번호를 선택한 다음 **프로필 할당**을 선택합니다.

4. **프로필 할당** 블레이드에서 할당할 프로필을 선택한 다음 **할당**을 선택합니다.

## <a name="delete-serial-numbers"></a>일련 번호 삭제
이전에 가져온 일련 번호를 삭제할 수 있습니다. 먼저 장치의 등록을 취소한 경우에만 일련 번호를 삭제할 수 있습니다. 일련 번호를 제거한 후에는 일련 번호를 다시 추가하지 않는 한 설정 도우미를 통해 Apple Configurator를 사용할 수 없습니다.

## <a name="view-the-state-of-a-device"></a>장치 상태 보기
장치 일련 번호는 다음 두 가지 상태 중 하나일 수 있습니다.

- 등록됨 - 장치가 등록되고 Intune 서비스에 연결되어 있습니다.
- 연결되지 않음 - 장치가 Intune 서비스에 연결된 적이 없습니다.
- 재설정 보류 중 - 장치가 등록되어 있지만 변경 내용이 적용되었습니다(예: 등록 설정 또는 적용된 DEP 프로필이 변경됨). 장치의 DEP 프로필을 변경한 경우 장치를 등록 취소했다가 다시 등록해야 변경 내용이 적용됩니다.

**일련 번호의 상태를 보려면**

**Apple Configurator 일련 번호** 블레이드에서 상태를 확인할 일련 번호를 선택하고 **상태** 항목 아래를 확인합니다.

