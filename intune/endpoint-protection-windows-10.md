---
title: "Windows 10용 Microsoft Intune Endpoint Protection 설정"
titlesuffix: 
description: "Windows 10 장치의 BitLocker와 같은 Endpoint Protection 설정을 제어하는 데 사용할 수 있는 Intune 설정을 알아봅니다."
keywords: 
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 02/23/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3af7c91b-8292-4c7e-8d25-8834fcf3517a
ms.reviewer: ilwu
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 02a32f678b40b2b40535984e17b41e0a864d8fdf
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/08/2018
---
# <a name="create-endpoint-protection-settings-for-windows-10-and-later-in-microsoft-intune"></a>Microsoft Intune의 Windows 10 이상용 Endpoint Protection 설정 만들기

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Endpoint Protection 프로필을 사용하면 BitLocker 및 Windows Defender와 같은 Windows 10 장치의 보안 기능을 제어할 수 있습니다.

이 아티클의 정보를 사용하여 Endpoint Protection 프로필을 만드는 방법을 알아봅니다.

> [!Note]
> Windows 10 Home 및 Professional 버전에서는 이러한 설정이 지원되지 않습니다.

## <a name="create-an-endpoint-protection-profile"></a>Endpoint Protection 프로필 만들기

1. 로그인은 [Azure 포털](https://portal.azure.com)합니다.
2. **모든 서비스** > **Intune**을 선택합니다. Intune은 **모니터링 + 관리** 섹션에 있습니다.
3. **Intune** 블레이드에서 **장치 구성**을 선택합니다.
2. **관리** 섹션 아래의 **장치 구성** 블레이드에서 **프로필**을 선택합니다.
3. 프로필 블레이드에서 **프로필 만들기**를 선택합니다.
4. **프로필 만들기** 블레이드에서 장치 기능 프로필에 대한 **이름** 및 **설명**을 입력합니다.
5. **플랫폼** 드롭다운 목록에서 **Windows 10 이상**을 선택합니다.
6. **프로필 유형** 드롭다운 목록에서 **Endpoint Protection**을 선택합니다.
7. 원하는 설정을 구성합니다. 이 아티클의 세부 정보를 사용하여 각 설정의 기능을 파악합니다. 작업이 끝나면 **확인**을 선택합니다.
8. **프로필 만들기** 블레이드로 돌아가서 **만들기**를 선택합니다.

프로필이 만들어지고 프로필 목록 블레이드에 표시됩니다.

## <a name="windows-defender-application-guard"></a>Windows Defender Application Guard

Application Guard는 Windows 10(64비트) 장치에서만 사용할 수 있습니다. 이 프로필을 사용하면 Win32 구성 요소가 설치되어 Application Guard를 활성화할 수 있습니다.

- **Application Guard** - Hyper-V 가상화된 검색 컨테이너에서 승인되지 않은 사이트를 엽니다.
- **클립보드 동작** - 로컬 PC와 Application Guard 가상 브라우저 간에 허용되는 복사/붙여넣기 작업을 선택합니다.
- **엔터프라이즈 사이트의 외부 콘텐츠** - 승인되지 않은 웹 사이트의 콘텐츠를 로드하지 못하도록 차단합니다.
- **가상 브라우저에서 인쇄** - PDF, XPS, 로컬 및/또는 네트워크 프린터에서 가상 브라우저의 내용을 인쇄할 수 있습니다.
- **로그 수집** - Application Guard 검색 세션에서 발생하는 이벤트에 대한 로그를 수집합니다.
- **사용자가 생성한 브라우저 데이터 보존** - Application Guard 가상 검색 세션 중에 만들어진 사용자 데이터(예: 암호, 즐겨찾기 및 쿠키)를 저장할 수 있습니다.
- **그래픽 가속** - 가상 그래픽 처리 장치에 대한 액세스를 사용하여 Application Guard 가상 검색 세션 내에서 작업할 때 그래픽 집약적 웹 사이트를 더 빠르게 로드...


## <a name="windows-defender-firewall"></a>Windows Defender 방화벽

### <a name="global-settings"></a>전역 설정

다음 설정은 모든 네트워크 형식에 적용할 수 있습니다.

- **파일 전송 프로토콜** - 상태 저장 FTP를 차단합니다.
- **삭제 전 보안 연결 유휴 시간** - *n*초 동안 네트워크 트래픽이 검색되지 않으면 보안 연결이 삭제됩니다.
- **미리 공유한 키 인코딩** - UTF-8을 사용하여 미리 공유한 키를 인코딩합니다.
- **IPsec 예외** - **IPv6 ICMP 종류 코드 네트워크 환경 검색**, **ICMP**, **IPv6 ICMP 종류 코드 라우터 검색** 및 **IPv4 및 IPv6 DHCP 네트워크 트래픽**을 포함하여 특정 트래픽이 IPsec에서 제외되도록 구성합니다.
- **인증서 해지 목록 확인** - **CRL 확인 사용 안 함**, **해지된 인증서에 대한 CRL 확인만 실패** 및 **오류 발생 시 CRL 확인 실패**를 포함하여 인증서 해지 목록 확인이 적용되는 방법에 대한 값을 설정합니다.
- **키 지정 모듈에 대해 선택적으로 인증 집합 일치** - 키 지정 모듈에서 인증 집합의 모든 인증 도구 모음을 지원하지 않는 경우 해당 인증 집합 전체를 무시하도록 설정합니다.
- **패킷 큐** - IPsec 터널 게이트웨이 시나리오의 암호화된 수신 및 일반 텍스트 전달에 대해 수신 쪽 소프트웨어의 크기 조정이 활성화되는 방법을 지정합니다. 이렇게 하면 패킷 순서가 유지됩니다.

### <a name="network-settings"></a>네트워크 설정

다음 설정은 **도메인(작업 공간) 네트워크**, **사설(검색 가능) 네트워크** 및 **공용(검색 불가능) 네트워크**를 포함한 특정 네트워크 형식에 적용할 수 있습니다.

#### <a name="general-settings"></a>일반 설정

- **Windows Defender 방화벽** - 네트워크 트래픽을 차단하려면 이 설정을 사용합니다.
- **은폐 모드** - 방화벽이 은폐 모드에서 작동하지 못하도록 차단합니다. 이렇게 차단하면 **IPsec 보안 패킷 예외**도 차단할 수 있습니다.
- **차폐** - 이 설정과 방화벽 설정을 사용하면 들어오는 모든 트래픽이 차단됩니다.
- **멀티캐스트 브로드캐스트에 대한 유니캐스트 응답** - 멀티캐스트 브로드캐스트에 대한 유니캐스트 응답을 차단합니다. 일반적으로 이러한 응답은 서비스 거부 공격이나 알려진 라이브 컴퓨터를 검색하려는 공격자를 나타낼 수 있으므로 멀티캐스트 또는 브로드캐스트 메시지에 대한 유니캐스트 응답을 받지 않으려고 합니다.
- **인바운드 알림** - 응용 프로그램이 포트에서 수신 대기하지 못하도록 차단될 때 사용자에 대한 알림 표시를 차단합니다.
- **인바운드 연결에 대한 기본 작업** - 방화벽이 인바운드 연결에서 수행하는 기본 작업을 차단합니다.

#### <a name="rule-merging"></a>규칙 병합

- **로컬 저장소의 권한 있는 응용 프로그램 Windows Defender 방화벽 규칙** - 인식하고 적용할 권한 있는 방화벽 규칙을 로컬 저장소에 적용합니다.
- **로컬 저장소의 전역 포트 Windows Defender 방화벽 규칙** - 인식하고 적용할 전역 포트 방화벽 규칙을 로컬 저장소에 적용합니다.
- **로컬 저장소의 Windows Defender 방화벽 규칙** - 인식하고 적용할 전역 방화벽 규칙을 로컬 저장소에 적용합니다.
- **로컬 저장소의 IPsec 규칙** - 스키마 또는 연결 보안 규칙 버전과 관계없이 로컬 저장소에서 연결 보안 규칙을 적용합니다.

## <a name="windows-defender-smartscreen-settings"></a>Windows Defender SmartScreen 설정

- **앱 및 파일용 SmartScreen** - 파일 실행 및 앱 실행에 대해 Windows SmartScreen을 사용하도록 설정합니다.
- **확인되지 않은 파일 실행** - Windows SmartScreen에서 확인하지 않은 파일을 최종 사용자가 실행하지 못하도록 차단합니다.

## <a name="windows-encryption"></a>Windows 암호화

### <a name="windows-settings"></a>Windows 설정

다음 설정은 Windows 10의 모든 버전에 적용됩니다.

- **장치 암호화** - 이 설정을 사용하면 장치 암호화를 사용하도록 설정하라는 메시지가 표시됩니다. 또한 다른 공급자의 암호화가 사용하도록 설정되지 않았는지 확인하라는 메시지도 표시됩니다. 다른 암호화 방법이 활성화된 상태에서 Windows 암호화를 켜면 장치가 불안정해질 수 있습니다.
- **메모리 카드 암호화** - 이 설정을 사용하면 장치에서 사용하는 모든 이동식 저장소 카드를 암호화합니다.


### <a name="bitlocker-base-settings"></a>BitLocker 기본 설정

기본 설정은 모든 종류의 데이터 드라이브에 대한 범용 BitLocker 설정입니다. BitLocker 그룹 정책 설정은 최종 사용자가 모든 종류의 데이터 드라이브에서 수정할 수 있는 드라이브 암호화 작업 또는 구성 옵션을 관리합니다.

- **다른 디스크 암호화에 대한 경고** - 최종 사용자 컴퓨터의 다른 디스크 암호화에 대한 경고 메시지가 표시되지 않도록 설정합니다.
- **암호화 방법 구성** - 운영 체제, 데이터 및 이동식 드라이브에 대한 암호화 알고리즘을 구성하려면 이 설정을 사용하도록 설정합니다.
    - **운영 체제 드라이브에 대한 암호화** - 운영 체제 드라이브에 대한 암호화 방법을 선택합니다. XTS-AES 알고리즘을 사용하는 것이 좋습니다.
    - **고정 데이터 드라이브에 대한 암호화** - 고정(기본 제공) 데이터 드라이브에 대한 암호화 방법을 선택합니다. XTS-AES 알고리즘을 사용하는 것이 좋습니다.
    - **이동식 데이터 드라이브에 대한 암호화** - 이동식 데이터 드라이브에 대한 암호화 방법을 선택합니다. 이동식 드라이브가 Windows 10을 실행하지 않는 장치와 함께 사용되는 경우 AES-CBC 알고리즘을 사용하는 것이 좋습니다.

### <a name="bitlocker-os-drive-settings"></a>BitLocker OS 드라이브 설정

다음 설정은 특히 운영 체제 데이터 드라이브에 적용됩니다.

- **시작 시 추가 인증** - TPM(신뢰할 수 있는 플랫폼 모듈) 사용을 포함하여 퓨터 시작에 필요한 인증 요구 사항을 구성합니다.
    - **호환되지 않는 TPM 칩과 BitLocker**
    - **호환되는 TPM 시작** - TPM 칩이 허용되는지, 허용되지 않는지 또는 필수인지 여부를 구성합니다.
    - **호환되는 TPM 시작 PIN** - TPM 칩과 함께 시작 PIN의 사용이 허용되는지, 허용되지 않는지 또는 필수인지 여부를 구성합니다.
    - **호환되는 TPM 시작 키** - TPM 칩과 함께 시작 키의 사용이 허용되는지, 허용되지 않는지 또는 필수인지 여부를 구성합니다.
    - **호환되는 TPM 시작 키 및 PIN** - TPM 칩과 함께 시작 키 및 PIN의 사용이 허용되는지, 허용되지 않는지 또는 필수인지 여부를 구성합니다.
- **최소 PIN 길이** - TPM 시작 PIN의 최소 길이를 구성하려면 이 설정을 사용하도록 설정합니다.
    - **최소 문자** - 시작 PIN에 필요한 문자 수를 **4**-**20** 사이로 입력합니다.
- **OS 드라이브 복구** - 이 설정을 사용하면 필요한 시작 정보를 사용할 수 없을 때 BitLocker로 보호된 운영 체제 드라이브를 복구하는 방법을 제어 할 수 있습니다.
    - **인증서 기반 데이터 복구 에이전트** - 데이터 복구 에이전트를 BitLocker로 보호된 운영 체제 드라이브와 함께 사용할 수 있게 하려면 이 설정을 사용하도록 설정합니다.
    - **사용자의 복구 암호 생성** - 사용자가 48자리 복구 암호를 생성하는 것이 허용되는지, 허용되지 않는지 또는 필수인지를 구성합니다.
    - **사용자의 복구 키 생성** - 사용자가 256비트 복구 키를 생성하는 것이 허용되는지, 허용되지 않는지 또는 필수인지를 구성합니다.
    - **BitLocker 설치 마법사의 복구 옵션** - 이 설정을 사용하면 BitLocker가 작동될 때 사용자가 복구 옵션을 보거나 변경하지 못하도록 방지할 수 있습니다.
    - **BitLocker 복구 정보를 AD DS에 저장** - BitLocker 복구 정보를 Active Directory에 저장할 수 있게 합니다.
    - **AD DS에 저장된 BitLocker 복구 정보** - Active Directory에 저장될 BitLocker 복구 정보 부분을 구성합니다. 다음 중에서 선택합니다.
        - **백업 복구 암호 및 키 패키지**
        - **백업 복구 암호만**
    - **BitLocker를 활성화하기 전에 AD DS에 복구 정보 저장** - 이 설정을 사용하면 장치가 도메인에 조인되어 있고 BitLocker 복구 정보가 Active Directory에 성공적으로 저장되어 있지 않을 때 사용자가 BitLocker를 작동할 수 없도록 합니다.
- **부팅 전 복구 메시지 및 URL** - 이 설정을 사용하면 부팅 전 키 복구 화면에 표시되는 메시지와 URL을 구성할 수 있습니다.
    - **부팅 전 복구 메시지** - 부팅 전 복구 메시지가 사용자에게 표시되는 방식을 구성합니다. 다음 중에서 선택합니다.
        - **기본 복구 메시지 및 URL 사용**
        - **빈 복구 메시지 및 URL 사용**
        - **사용자 지정 복구 메시지 사용**
        - **사용자 지정 복구 URL 사용**


### <a name="bitlocker-fixed-data-drive-settings"></a>BitLocker 고정 데이터 드라이브 설정

- **BitLocker로 보호되지 않는 고정 데이터 드라이브에 대한 쓰기 액세스** - 이 설정을 사용하면 모든 고정 또는 기본 제공 데이터 드라이브에서 BitLocker 보호를 사용하도록 설정해야 드라이브에 쓸 수 있습니다.
- **고정식 드라이브 복구** - 이 설정을 사용하면 필요한 시작 정보를 사용할 수 없을 때 BitLocker로 보호된 고정 드라이브를 복구하는 방법을 제어할 수 있습니다.
    - **데이터 복구 에이전트** - 데이터 복구 에이전트를 BitLocker로 보호된 고정 드라이브와 함께 사용하려면 이 설정을 사용하도록 설정합니다.
    - **사용자의 복구 암호 생성** - 사용자가 48자리 복구 암호를 생성하는 것이 허용되는지, 허용되지 않는지 또는 필수인지를 구성합니다.  
    - **사용자의 복구 키 생성** - 사용자가 256비트 복구 키를 생성하는 것이 허용되는지, 허용되지 않는지 또는 필수인지를 구성합니다.
    - **BitLocker 설치 마법사의 복구 옵션** - 이 설정을 사용하면 BitLocker가 작동될 때 사용자가 복구 옵션을 보거나 변경하지 못하도록 방지할 수 있습니다.
    - **BitLocker 복구 정보를 AD DS에 저장** - BitLocker 복구 정보를 Active Directory에 저장할 수 있게 합니다.
    - **AD DS에 저장된 BitLocker 복구 정보** - Active Directory에 저장될 BitLocker 복구 정보 부분을 구성합니다. 다음 중에서 선택합니다.
        - **백업 복구 암호 및 키 패키지**
        - **백업 복구 암호만**
    - **BitLocker를 활성화하기 전에 AD DS에 복구 정보 저장** - 이 설정을 사용하면 장치가 도메인에 조인되어 있고 BitLocker 복구 정보가 Active Directory에 성공적으로 저장되어 있지 않을 때 사용자가 BitLocker를 작동할 수 없도록 합니다.

### <a name="bitlocker-removable-data-drive-settings"></a>BitLocker 이동식 데이터 드라이브 설정

- **BitLocker로 보호되지 않는 이동식 데이터 드라이브에 대한 쓰기 액세스** - 이동식 저장소 드라이브에 BitLocker 암호화가 필요한지 여부를 지정합니다.
  - **다른 조직에서 구성된 장치에 대한 쓰기 액세스** - 다른 조직에 속한 이동식 데이터 드라이브에 쓸 수 있는지 여부를 지정합니다.

## <a name="windows-defender-exploit-guard"></a>Windows Defender Exploit Guard

[Windows Defender Exploit Guard](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/windows-defender-exploit-guard)를 사용하여 직원이 사용하는 앱의 공격 노출 영역을 관리하고 줄입니다.

### <a name="attack-surface-reduction"></a>공격 노출 영역 축소

악용 검색 맬웨어가 컴퓨터를 감염시키는 데 일반적으로 사용되는 [작업과 앱을 방지](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard)합니다.

#### <a name="rules-to-prevent-office-macro-threats"></a>Office 매크로 위협을 방지하는 규칙

Office 앱에서 다음 작업을 수행하지 못하도록 차단합니다.

- **다른 프로세스에 삽입되는 Office 앱(예외 없음)**
- **실행 가능 콘텐츠를 만드는 Office 앱/매크로**
- **자식 프로세스를 실행하는 Office 앱**
- **Office 매크로 코드에서 Win32 가져오기**

#### <a name="rules-to-prevent-script-threats"></a>스크립트 위협을 방지하는 규칙

스크립트 위협을 방지하기 위해 다음 항목을 차단합니다.

- **난독 처리된 js/vbs/ps/매크로 코드**
- **인터넷에서 다운로드된 페이로드를 실행하는 js/vbs(예외 없음)**

#### <a name="rules-to-prevent-email-threats"></a>이메일 위협을 방지하는 규칙

이메일 위협을 방지하기 위해 다음 항목을 차단합니다.

- **이메일(웹 메일/메일 클라이언트)에서 삭제된 실행 파일 콘텐츠(exe, dll, ps, js, vbs 등)의 실행(예외 없음)**

#### <a name="attack-surface-reduction-exceptions"></a>공격 노출 영역 축소 예외

- **공격 노출 영역 축소 규칙에서 제외할 파일 및 폴더** - 구성된 규칙에서 제외할 위치 목록을 가져오거나 추가합니다.

### <a name="controlled-folder-access"></a>폴더 액세스 제어

랜섬웨어와 같은 악성 앱과 위협으로부터 중요한 데이터를 보호합니다.

- **폴더 보호** - 악성 앱에 의한 원하지 않는 변경으로부터 파일 및 폴더를 보호합니다. **보호된 폴더에 액세스할 수 있는 앱 목록**을 가져오거나 수동으로 추가할 수 있습니다. 또한 업로드가 포함된 **보호해야 하는 추가 폴더의 목록**을 추가하거나 수동으로 추가할 수도 있습니다.

### <a name="network-filtering"></a>네트워크 필터링

모든 앱에서 평판이 낮은 IP/도메인으로의 아웃바운드 연결을 차단합니다.

### <a name="exploit-protection"></a>악용 방지

응용 프로그램을 악용하지 못하도록 차단하는 데 사용할 수 있는 메모리, 제어 흐름 및 정책 제한을 구성할 수 있는 XML 파일을 업로드하여 **Exploit Protection 인터페이스의 사용자 편집**을 차단합니다.

Exploit Protection을 사용하려면 선택한 시스템 및 응용 프로그램 완화 설정을 나타내는 XML 파일을 만듭니다. 다음 두 가지 방법 중 하나를 사용하여 수행할 수 있습니다.

 1. PowerShell: Get-ProcessMitigation, Set-ProcessMitigation 및 ConvertTo-ProcessMitigationPolicy PowerShell cmdlet 중 하나 이상을 사용하여 완화 설정을 구성하고 해당 설정의 XML 표현을 내보냅니다.

 2. Windows Defender 보안 센터 UI: Windows Defender 보안 센터에서 앱 및 브라우저 컨트롤을 클릭한 다음, 결과 화면의 아래쪽으로 스크롤하여 Exploit Protection을 찾습니다. 먼저 시스템 설정 및 프로그램 설정 탭을 사용하여 완화 설정을 구성합니다. 그런 다음 화면 아래쪽의 설정 내보내기 링크를 찾아서 해당 XML 표현을 내보냅니다.

## <a name="windows-defender-application-control"></a>Windows Defender 응용 프로그램 제어

**응용 프로그램 제어 코드 무결성 정책**을 사용하여 감사해야 하거나 Windows Defender 응용 프로그램 제어에서 실행하도록 신뢰할 수 있는 추가 앱을 선택합니다. Windows 구성 요소 및 모든 Windows 저장소 앱의 실행은 자동으로 신뢰할 수 있습니다.

**감사 전용** 모드에서 실행하는 경우 응용 프로그램이 차단되지 않습니다. **감사 전용** 모드는 로컬 클라이언트 로그에 있는 모든 이벤트를 기록합니다.

사용하도록 설정되면 응용 프로그램 제어는 **적용**에서 **감사 전용**으로 모드를 변경할 때에만 해제될 수 있습니다. 모드를 **적용**에서 **구성하지 않음**으로 변경하면 응용 프로그램 제어가 할당된 장치에 계속 적용됩니다.

## <a name="windows-defender-security-center"></a>Windows Defender 보안 센터

Windows Defender 보안 센터 앱은 개별 기능별로 별도의 앱 또는 프로세스로 작동하며, 알림 센터를 통해 알림을 표시합니다. 수집기 또는 단일 위치로 작동하여 상태를 확인하고 각 기능에 대한 일부 구성을 수행합니다. [Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-security-center/windows-defender-security-center) 문서에서 자세한 내용을 알아보세요.

#### <a name="windows-defender-security-center-app-and-notifications"></a>Windows Defender 보안 센터 앱 및 알림

Windows Defender 보안 센터 앱의 다양한 영역에 대한 최종 사용자 액세스를 차단합니다. 또한 섹션을 숨기면 관련 알림도 차단됩니다.

- **바이러스 및 위협 방지**
- **장치 성능 및 상태**
- **방화벽 및 네트워크 보호**
- **앱 및 브라우저 제어**
- **제품군 옵션**
- **앱 표시 영역의 알림** - 최종 사용자에게 표시할 알림을 선택합니다. 중요하지 않은 알림에는 검색 완료 시 알림을 포함한 Windows Defender 바이러스 백신 활동의 요약이 포함됩니다. 다른 모든 알림은 중요 알림으로 간주합니다.

#### <a name="it-contact-information"></a>IT 연락처 정보

Windows Defender 보안 센터 앱 및 앱 알림에 표시할 IT 연락처 정보를 제공합니다. **앱 및 알림에 표시**, **앱에만 표시**, **알림에만 표시** 또는 **표시 안 함**을 선택할 수 있습니다. **IT 조직 이름**과 다음 연락처 옵션 중 하나 이상을 정의해야 합니다.

- **IT 부서 전화 번호 또는 Skype ID**
- **IT 부서 이메일 주소**
- **IT 지원 웹 사이트 URL**

## <a name="next-steps"></a>다음 단계

계속해서 이 프로필을 그룹에 할당하려면 [장치 프로필을 할당하는 방법](device-profile-assign.md)을 참조하세요.
