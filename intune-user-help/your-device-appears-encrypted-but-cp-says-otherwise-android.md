---
title: "Android 장치가 암호화된 것 같음"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 05/25/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ba593c08-1a78-4013-8525-b45a948772ec
searchScope: User help
ROBOTS: 
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 269ad7968242f8f5ce7095c9c73347987675e846
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2017
---
# <a name="your-android-device-seems-to-be-encrypted-but-company-portal-says-otherwise"></a>Android 장치가 암호화된 것 같은데 회사 포털에 다르게 표시됨

장치를 암호화하는 경우 자신만 알고 있는 비밀 키로 장치의 정보를 인코드하여 권한이 없는 사용자가 해당 정보에 액세스할 수 없도록 합니다. 정보 보안을 보장하기 위한 단계로서, 조직에서는 회사 파일, 메일 또는 데이터에 액세스하기 전에 Android 장치를 암호화할 것을 요구합니다.

## <a name="common-issues"></a>일반적인 문제

최신 버전의 Android(특히 v7.0 이상 버전)에서는 장치가 완전하게 암호화되도록 시작 암호를 설정해야 합니다. 시작 암호의 설명과 위치는 장치 제조업체마다 다릅니다. 대부분의 경우에는 시작 암호를 사용한 시작을 "보안 시작"이라고 합니다. 

## <a name="solutions"></a>솔루션

### <a name="add-a-startup-pin"></a>시작 PIN 추가

특정 Android 장치에서는 장치의 보안을 유지하기 위해 시작 PIN을 만들어야 합니다. 여러 제조업체에서 다양한 버전의 Android를 사용하고 있습니다. 설정 앱에서 이 옵션을 사용하도록 설정하는 위치를 찾아 이 문제의 해결을 시도해 볼 수 있습니다. 예를 들어 Samsung Galaxy S7에서는 **설정** > **잠금 화면 및 보안** > **보안 시작**으로 이동하여 보안 시작을 사용하도록 설정합니다.  

### <a name="downgrade-your-version-of-android"></a>Android 버전 다운그레이드
장치에서 Android 6.0 이상으로 다운그레이드하는 옵션을 제공하는 경우 다운그레이드합니다. 장치 다운그레이드를 시도해야 하는 경우 데이터 손실 위험이 있습니다. 그렇지 않으면 IT 관리자에게 문의하여 이 문제를 해결하는 것이 좋습니다. [회사 포털 웹 사이트](http://portal.manage.microsoft.com)에서 IT 관리자의 연락처 정보를 얻을 수 있습니다.

## <a name="specific-manufacturer-issues"></a>특정 제조업체 문제

버전 7.0 이상의 일부 Android 장치에서는 특정 Android 플랫폼 표준과 일치하지 않는 방식으로 데이터를 암호화합니다. 이러한 장치는 기본적으로 암호화되는 것처럼 보이지만 이 방법은 Intune에서 장치에 대한 물리적 액세스 권한이 있는 악의적인 사용자로 인해 장치의 정보가 위험해질 수 있는 방법으로 인식됩니다.

> [!Note]
> Microsoft는 제조업체와 협력하여 테스트 중에 확인되거나 사용자들이 보고하는 문제를 해결합니다. 새로운 정보를 사용할 수 있을 때마다 이 문서를 업데이트할 예정입니다. 

## <a name="known-devices"></a>알려진 장치

### <a name="known-devices-that-can-be-updated-to-fix-this-issue"></a>이 문제를 해결하기 위해 업데이트할 수 있는 알려진 장치

다음 장치 중 하나를 소유한 경우 최신 버전의 Android로 장치를 업데이트하지 않았다면 이 문제가 발생할 수 있습니다. **설정** > **업데이트**로 이동하여 이러한 장치용 업데이트를 설치할 수 있습니다. 

- [Huawei Honor 8](http://consumer.huawei.com/en/support/mobile-phones/honor8_en-sup.htm)
- [Huawei P9](http://consumer.huawei.com/mobile-phones/p9/index.html)

### <a name="known-devices-that-currently-cannot-be-updated-to-fix-this-issue"></a>현재 이 문제를 해결하기 위해 업데이트할 수 없는 알려진 장치

- [Huawei Mate 8](http://consumer.huawei.com/en/mobile-phones/mate8/index.htm)
- [Xiaomi Mi 스마트폰](https://xiaomi-mi.com/mi-smartphones/)
