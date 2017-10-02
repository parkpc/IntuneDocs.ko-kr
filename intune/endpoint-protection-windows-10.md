---
title: "Windows 10용 Intune Endpoint Protection 설정"
titlesuffix: Azure portal
description: "Windows 10 장치의 BitLocker와 같은 Endpoint Protection 설정을 제어하는 데 사용할 수 있는 Intune 설정을 알아봅니다.\""
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3af7c91b-8292-4c7e-8d25-8834fcf3517a
ms.reviewer: ilwu
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 19c20ac5dd73b45dc06d1df6a7d08cc6bac42982
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2017
---
# <a name="endpoint-protection-settings-for-windows-10-and-later-in-microsoft-intune"></a>Microsoft Intune의 Windows 10 이상용 Endpoint Protection 설정

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Endpoint Protection 프로필을 사용하면 BitLocker와 같은 Windows 10 장치 및 Windows Defender의 보안 기능을 제어할 수 있습니다.

이 항목의 정보를 사용하여 Endpoint Protection 프로필을 만드는 방법을 알아봅니다.

## <a name="create-an-endpoint-protection-profile"></a>Endpoint Protection 프로필 만들기

1. Azure 포털에 로그인합니다.
2. **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
3. **Intune** 블레이드에서 **장치 구성**을 선택합니다.
2. **장치 구성** 블레이드에서 **관리** > **프로필**을 선택합니다.
3. 프로필 블레이드에서 **프로필 만들기**를 선택합니다.
4. **프로필 만들기** 블레이드에서 장치 기능 프로필에 대한 **이름** 및 **설명**을 입력합니다.
5. **플랫폼** 드롭다운 목록에서 **Windows 10 이상**을 선택합니다.
6. **프로필 유형** 드롭다운 목록에서 **Endpoint Protection**을 선택합니다.
7. **Windows 암호화** 블레이드에서 원하는 설정을 구성합니다. 이 항목의 세부 정보를 사용하여 각 설정의 기능을 파악합니다. 작업이 끝나면 **확인**을 선택합니다.
8. **프로필 만들기** 블레이드로 돌아간 다음 **만들기**를 선택합니다.

프로필이 만들어지고 프로필 목록 블레이드에 표시됩니다.

## <a name="windows-defender-smartscreen-settings"></a>Windows Defender SmartScreen 설정

- **앱 및 파일용 SmartScreen** - 파일 실행 및 앱 실행에 대해 Windows SmartScreen을 사용하도록 설정합니다.
- **확인되지 않은 파일 실행** - Windows SmartScreen에서 확인하지 않은 파일을 최종 사용자가 실행하지 못하도록 차단합니다.

## <a name="windows-encryption-settings"></a>Windows 암호화 설정

### <a name="windows-settings"></a>Windows 설정

- **장치 암호화 필요(데스크톱만 해당)** - 사용하도록 설정된 경우 사용자에게 장치 암호화를 사용하도록 설정하라는 메시지가 표시됩니다. 또한 다른 공급자의 암호화가 사용하도록 설정되지 않았는지 확인하라는 메시지도 표시됩니다. 다른 암호화 방법이 활성화된 상태에서 Windows 암호화를 켜면 장치가 불안정해질 수 있습니다.
- **메모리 카드 암호화 필요(모바일만 해당)** - 장치에서 사용하는 모든 이동식 메모리 카드를 암호화하려면 이 설정을 사용하도록 설정합니다.


### <a name="bitlocker-base-settings"></a>BitLocker 기본 설정

- **암호화 방법 구성** - 운영 체제, 데이터 및 이동식 드라이브에 대한 암호화 알고리즘을 구성하려면 이 설정을 사용하도록 설정합니다.
    - **운영 체제 드라이브에 대한 암호화** - 운영 체제 드라이브에 대한 암호화 방법을 선택합니다. XTS-AES 알고리즘을 사용하는 것이 좋습니다.
    - **고정 데이터 드라이브에 대한 암호화** - 고정(기본 제공) 데이터 드라이브에 대한 암호화 방법을 선택합니다. XTS-AES 알고리즘을 사용하는 것이 좋습니다.
    - **이동식 데이터 드라이브에 대한 암호화** - 이동식 데이터 드라이브에 대한 암호화 방법을 선택합니다. 이동식 드라이브가 Windows 10을 실행하지 않는 장치와 함께 사용되는 경우 AES-CBC 알고리즘을 사용하는 것이 좋습니다.


### <a name="bitlocker-os-drive-settings"></a>BitLocker OS 드라이브 설정

- **시작 시 추가 인증 필요** -
    - **호환되지 않는 TPM 칩과 BitLocker** -
    - **TPM 시작** - TPM 칩이 허용되는지, 허용되지 않는지 또는 필수인지를 구성합니다.
    - **TPM 시작 PIN** - TPM 칩과 함께 시작 PIN을 사용하는 것이 허용되는지, 허용되지 않는지 또는 필수인지를 구성합니다.
    - **TPM 시작 키** - TPM 칩과 함께 시작 키를 사용하는 것이 허용되는지, 허용되지 않는지 또는 필수인지를 구성합니다.
    - **TPM 시작 키 및 PIN** - TPM 칩과 함께 시작 키와 PIN을 사용하는 것이 허용되는지, 허용되지 않는지 또는 필수인지를 구성합니다.
- **최소 PIN 길이** - TPM 시작 PIN의 최소 길이를 구성하려면 이 설정을 사용하도록 설정합니다.
    - **최소 문자** - 시작 PIN에 필요한 문자 수를 **4**-**20** 사이로 입력합니다.
- **OS 드라이브 복구 활성화** - 필요한 시작 정보를 사용할 수 없을 경우 BitLocker로 보호된 운영 체제 드라이브가 복구되는 방법을 제어하려면 이 설정을 사용하도록 설정합니다.
    - **인증서 기반 데이터 복구 에이전트** - 데이터 복구 에이전트를 BitLocker로 보호된 운영 체제 드라이브와 함께 사용할 수 있게 하려면 이 설정을 사용하도록 설정합니다.
    - **사용자의 복구 암호 생성** - 사용자가 48자리 복구 암호를 생성하는 것이 허용되는지, 허용되지 않는지 또는 필수인지를 구성합니다.
    - **사용자의 복구 키 생성** - 사용자가 256비트 복구 키를 생성하는 것이 허용되는지, 허용되지 않는지 또는 필수인지를 구성합니다.
    - **BitLocker 설치 마법사에서 복구 옵션 숨기기** - 사용자가 BitLocker를 켤 때 복구 옵션을 보거나 변경할 수 없게 하려면 이 설정을 사용하도록 설정합니다.
    - **BitLocker 복구 정보를 AD DS에 저장** - BitLocker 복구 정보를 Active Directory에 저장할 수 있게 합니다.
    - **AD DS에 BitLocker 복구 정보에 대한 저장소 구성** - Active Directory에 저장되는 BitLocker 복구 정보 부분을 구성합니다. 다음 중에서 선택합니다.
        - **백업 복구 암호 및 키 패키지**
        - **백업 복구 암호만**
    - **BitLocker를 활성화하기 전에 AD DS에 복구 정보를 저장하도록 요구** - 장치가 도메인에 가입되고 BitLocker 복구 정보가 Active Directory에 저장되지 않은 경우 사용자가 BitLocker를 켤 수 없도록 하려면 이 설정을 사용하도록 설정합니다.
- **부팅 전 복구 메시지 및 URL 활성화** - 부팅 전 키 복구 화면에 표시되는 메시지와 URL을 구성하려면 이 설정을 사용하도록 설정합니다.
    - **부팅 전 복구 메시지** - 부팅 전 복구 메시지가 사용자에게 표시되는 방식을 구성합니다. 다음 중에서 선택합니다.
        - **기본 복구 메시지 및 URL 사용**
        - **빈 복구 메시지 및 URL 사용**
        - **사용자 지정 복구 메시지 사용**
        - **사용자 지정 복구 URL 사용**


### <a name="bitlocker-fixed-data-drive-settings"></a>BitLocker 고정 데이터 드라이브 설정

- **BitLocker로 보호되지 않는 고정 데이터 드라이브에 대한 쓰기 액세스 거부** - 사용하도록 설정된 경우 모든 고정 데이터 드라이브 또는 기본 제공 데이터 드라이브에서 BitLocker 보호를 사용하도록 설정해야 드라이브에 쓸 수 있습니다.
- **고정식 드라이브 복구 사용** - 필요한 시작 정보를 사용할 수 없을 경우 BitLocker로 보호된 고정 드라이브가 복구되는 방법을 제어하려면 이 설정을 사용하도록 설정합니다.
    - **데이터 복구 에이전트** - 데이터 복구 에이전트를 BitLocker로 보호된 고정 드라이브와 함께 사용하려면 이 설정을 사용하도록 설정합니다.
    - **사용자의 복구 암호 생성** - 사용자가 48자리 복구 암호를 생성하는 것이 허용되는지, 허용되지 않는지 또는 필수인지를 구성합니다.  
    - **사용자의 복구 키 생성** - 사용자가 256비트 복구 키를 생성하는 것이 허용되는지, 허용되지 않는지 또는 필수인지를 구성합니다.
    - **BitLocker 설치 마법사에서 복구 옵션 숨기기** - 사용자가 BitLocker를 켤 때 복구 옵션을 보거나 변경할 수 없게 하려면 이 설정을 사용하도록 설정합니다.
    - **BitLocker 복구 정보를 AD DS에 저장** - BitLocker 복구 정보를 Active Directory에 저장할 수 있게 합니다.
    - **AD DS에 BitLocker 복구 정보에 대한 저장소 구성** - Active Directory에 저장되는 BitLocker 복구 정보 부분을 구성합니다. 다음 중에서 선택합니다.
        - **백업 복구 암호 및 키 패키지**
        - **백업 복구 암호만**
    - **BitLocker를 활성화하기 전에 AD DS에 복구 정보를 저장하도록 요구** - 장치가 도메인에 가입되고 BitLocker 복구 정보가 Active Directory에 저장되지 않은 경우 사용자가 BitLocker를 켤 수 없도록 하려면 이 설정을 사용하도록 설정합니다.


### <a name="bitlocker-removable-data-drive-settings"></a>BitLocker 이동식 데이터 드라이브 설정

- **BitLocker로 보호되지 않는 이동식 데이터 드라이브에 대한 쓰기 액세스 거부** - 이동식 저장소 드라이브에 BitLocker 암호화가 필요한지 여부를 지정합니다.
    - **다른 조직에서 구성된 장치에 대한 쓰기 액세스 차단** - 다른 조직에 속해 있는 이동식 데이터 드라이브에 쓸 수 있는지 여부를 지정합니다.



## <a name="next-steps"></a>다음 단계

계속해서 이 프로필을 그룹에 할당하려면 [장치 프로필을 할당하는 방법](device-profile-assign.md)을 참조하세요.
