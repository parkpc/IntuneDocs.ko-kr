---
title: Windows 버전 업그레이드 정책 설정
description: Intune을 사용하여 Windows 10 장치를 다른 버전으로 자동 업그레이드하는 방법을 알아봅니다.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 04/14/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 8589866a-3f13-489b-a5cd-cee017d16d54
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: coryfe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 005f8cf2e769b1b007424e55867160a0f5828f7a
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2018
---
# <a name="windows-edition-upgrade-policy-settings-in-microsoft-intune"></a>Microsoft Intune에서 Windows 버전 업그레이드 정책 설정

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune **버전 업그레이드 정책**을 사용하면 다음 Windows 10 버전 중 하나를 실행하는 장치를 다른 버전으로 자동 업그레이드할 수 있습니다.
* Windows 10 Desktop
* Windows 10 Holographic
* Windows 10 Mobile

지원되는 업그레이드 경로는 다음과 같습니다.
- Windows 10 Pro에서 Windows 10 Enterprise로 업그레이드
- Windows 10 Home에서 Windows 10 Education으로 업그레이드
- Windows 10 Mobile에서 Windows 10 Mobile Enterprise로 업그레이드
- Windows 10 Holographic Pro에서 Windows 10 Holographic Enterprise로

## <a name="before-you-start"></a>시작하기 전에
장치를 최신 버전으로 업그레이드하기 전에 다음 중 하나가 있어야 합니다.
* Windows 10 Desktop 버전용 정책에서 대상으로 지정하는 모든 장치에 새 버전의 Windows를 설치하는 데 유효한 제품 키 MAK(다중 정품 인증 키) 또는 KMS(키 관리 서버) 키 둘 중 하나를 사용할 수 있습니다.
**또는** 정책에서 대상으로 지정하는 모든 장치에 새 Windows 버전을 설치하기 위한 라이선스 정보가 포함된 Microsoft 라이선스 파일(Windows 10 Mobile 및 Windows 10 Holographic 버전용).
* 대상으로 지정한 Windows 10 장치를 Microsoft Intune에 등록해야 합니다. Intune PC 클라이언트 소프트웨어를 실행하는 PC에는 버전 업그레이드 정책을 사용할 수 없습니다.

## <a name="edition-upgrade-policy-settings"></a>버전 업그레이드 정책 설정

|설정 이름|세부 정보|
|-|-|
|**Name**|버전 업그레이드 정책의 이름을 입력합니다.|
|**설명**|필요에 따라 Intune 콘솔에서 식별하는 데 도움이 되는 정책 설명을 입력합니다.
|**업그레이드할 버전**|드롭다운 목록에서 대상 장치를 업그레이드할 Windows 10 Desktop, Windows 10 Holographic 또는 Windows 10 Mobile 버전을 선택합니다.
|**제품 키**|대상으로 지정된 모든 Windows 10 Desktop 장치를 업그레이드하는 데 사용할 수 있는 Microsoft에서 가져온 제품 키를 지정합니다.<br>제품 키가 포함된 정책을 만든 후에는 나중에 제품 키를 편집할 수 없습니다. 보안상 키가 가려지기 때문입니다. 제품 키를 변경하려면 전체 키를 다시 입력해야 합니다.
|**라이선스 파일**|**찾아보기**를 선택하여 대상으로 지정된 장치를 업그레이드하려는 Windows Holographic 또는 Windows 10 Mobile 버전에 대한 라이선스 정보를 포함하는 Microsoft에서 가져온 라이선스 파일을 선택합니다.

### <a name="see-also"></a>참고 항목
[Microsoft Intune 정책을 사용하여 장치의 설정 및 기능 관리](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
