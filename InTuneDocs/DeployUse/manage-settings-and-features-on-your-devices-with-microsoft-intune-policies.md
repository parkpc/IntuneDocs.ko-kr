---
# required metadata

title: 정책을 사용하여 장치의 설정 및 기능 관리 | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 09bae0b9-4f79-4658-8ca1-a71ab992c1b2

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune 정책을 사용하여 장치의 설정 및 기능 관리
Microsoft Intune **정책**은 모바일 장치 및 컴퓨터에서 기능을 제어하는 설정 그룹입니다. 권장 설정 또는 사용자 지정 설정이 포함된 템플릿을 사용하여 정책을 만든 후 장치 또는 사용자 그룹에 해당 정책을 배포할 수 있습니다.

## 어떤 유형의 정책을 사용할 수 있습니까?

Intune 정책은 다음과 같은 범주로 분류됩니다. 사용하는 범주는 정책을 만들고 배포하는 방법에 영향을 줍니다.


- **구성 정책:** 장치에 대한 보안 설정 및 기능을 관리하는 데 널리 사용됩니다. 이 항목의 정보를 사용하여 이러한 정책을 만들고 배포하는 방법에 대해 알아보고 사용 가능한 설정을 탐색할 수 있습니다.
- **장치 준수 정책:** 조건부 액세스 정책을 준수하는 것으로 간주되기 위해 장치가 준수해야 하는 규칙 및 설정을 정의합니다. 준수 정책을 사용하여 조건부 액세스와 독립적으로 장치의 준수를 모니터링하고 수정할 수도 있습니다.
자세한 내용은 [Microsoft Intune의 장치 준수 정책](introduction-to-device-compliance-policies-in-microsoft-intune.md) 항목을 참조하세요.
- **조건부 액세스 정책:** 지정하는 조건에 따라 전자 메일 및 기타 서비스를 보호하는 데 도움이 됩니다.
자세한 내용은 [Microsoft Intune을 사용한 메일 및 O365 서비스 액세스 제한](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) 항목을 참조하세요.
- **회사 장치 등록 정책:** 회사 장치 등록 정책에 대한 자세한 내용은 [Microsoft Intune을 사용하여 iOS 및 Mac 관리 설정](set-up-ios-and-mac-management-with-microsoft-intune.md) 항목을 참조하세요.
- **리소스 액세스 정책:** 이 정책 그룹은 함께 작동하여 사용자가 어디에 있든지 상관없이 정상적인 작업 수행에 필요한 파일 및 리소스에 쉽게 액세스하게 해 줍니다.
자세한 내용은 [Microsoft Intune을 사용하여 회사 리소스에 대한 액세스 허용](enable-access-to-company-resources-with-microsoft-intune.md) 항목을 참조하세요.


Intune 정책의 전체 목록을 보려면 [Microsoft Intune 정책 참조](microsoft-intune-policy-reference.md) 항목을 참조하세요.




## 구성 정책 만들기

1.  [Microsoft Intune 관리 콘솔](https://manage.microsoft.com/)에서 **정책** &gt; **구성 정책** &gt; **추가**를 클릭합니다.

2.  원하는 정책을 선택합니다. 해당 정책에 권장되는 설정을 사용하거나(사용 가능한 경우. 나중에 이러한 설정을 변경할 수 있음) 원하는 설정으로 사용자 지정 정책을 만들 수 있습니다.

    > [!TIP] 올바른 정책을 선택하는 데 도움이 필요하면 [Microsoft Intune 정책 참조](microsoft-intune-policy-reference.md) 항목을 참조하세요.

3.  준비가 되면 **정책 만들기**를 클릭합니다.

4.   **정책 만들기** 화면에서 정책의 이름과 설명(옵션)을 구성합니다.

5.  필요한 정책 설정을 구성하고 **정책 저장**을 클릭합니다.

    어떤 정책 설정이든 도움이 필요하면 다음 목록에서 정책 유형을 선택 합니다.

    - [iOS 장치용 설정](ios-policy-settings-in-microsoft-intune.md)
    - [Android 장치에 대한 설정](android-policy-settings-in-microsoft-intune.md)
    - [Windows 8 및 Windows 8.1 장치에 대한 설정](windows-configuration-policy-settings-in-microsoft-intune.md)
    - [Windows Phone 8.1 장치에 대한 설정](windows-phone-8-1-policy-settings-in-microsoft-intune.md)
    - [Windows 10 Desktop 및 Mobile에 대한 설정](windows-10-policy-settings-in-microsoft-intune.md)
    - [Windows Team 장치에 대한 설정](windows-team-configuration-policy-settings-in-microsoft-intune.md)
    - [Windows 버전 업그레이드에 대한 설정](edition-upgrade-policy-settings-in-microsoft-intune.md)
    - [Mac OS X 장치의 설정](mac-os-x-policy-settings-in-microsoft-intune.md)
    - [Exchange ActiveSync에 대한 설정](exchange-activesync-policy-settings-in-microsoft-intune.md)
    - [사용 약관 정책에 대한 설정](terms-and-condition-policy-settings-in-microsoft-intune.md)
    - [모바일 장치에 대한 일반 설정(레거시)](mobile-device-security-policy-settings-in-microsoft-intune.md)

4.  확인 대화 상자에서 정책을 지금 배포하려면 **예** 를 클릭하고, 지금 배포하지 않고 정책을 만들려면 **아니요** 를 클릭합니다.

**정책** 작업 영역에서 각 정책 유형 섹션을 검색하여 새 정책을 보고 편집할 수 있습니다.

권장 설정을 사용하는 정책을 만든 경우 새 정책의 이름은 템플릿 이름, 날짜 및 시간의 조합입니다. 정책을 편집하면 해당 이름이 편집할 당시의 시간 및 날짜로 업데이트됩니다.

정책을 만든 후에는 보통 하나 이상의 사용자 또는 장치 그룹에 정책을 배포합니다.

> [!TIP]
> 모든 정책 유형을 배포하지는 않습니다. 예를 들어 모바일 응용 프로그램 관리 정책은 배포하지 않습니다. 이 정책 유형은 앱에 연결한 후에 배포합니다.

## 구성 정책 배포

1.   **정책** 작업 영역에서 배포할 정책을 선택하고 **배포 관리**를 클릭합니다.

2.   **배포 관리** 대화 상자에서

    -   **정책을 배포하려면** - 정책을 배포하려는 그룹을 하나 이상 선택한 후 **추가** &gt; **확인**을 클릭합니다.

    -   **정책을 배포하지 않고 대화 상자를 닫으려면** - **취소**를 클릭합니다.

배포한 정책을 선택하면 정책 목록 아래쪽에서 배포에 대한 추가 정보를 볼 수 있습니다.

## 정책 관리

1.  [Microsoft Intune 관리 콘솔](https://manage.microsoft.com/)에서 **정책**을 클릭하여 관리하려는 정책을 찾아서 선택합니다.

2.  다음 작업 중 하나를 선택합니다.

- **편집** - 선택한 정책의 속성을 열어 변경합니다.
- **삭제** - 선택한 정책을 삭제합니다.<br>정책을 삭제한 경우 배포된 모든 그룹에서 해당 정책이 삭제됩니다.
- **배포 관리** - 정책을 배포할 그룹을 선택하고 **추가**를 클릭합니다.

## Intune 정책에 대한 작업

### 장치의 정책을 최신 상태로 되도록 새로 고치려면(Intune 클라이언트 소프트웨어를 실행하는 Windows PC에만 적용)

1.  [Microsoft Intune 관리 콘솔](https://manage.microsoft.com/)에서 **그룹**을 클릭한 후 장치 그룹을 선택합니다.

2.  정책을 새로 고칠 장치를 선택한 후 **원격 작업** &gt; **정책 새로 고침**을 클릭합니다.

3.  Intune 관리 콘솔의 오른쪽 아래에서 **원격 작업**을 클릭하여 작업 상태를 확인합니다.

## Intune 정책에 대한 질문과 대답

### 정책 또는 앱을 배포한 후 모바일 장치에서 해당 정책 또는 앱을 수신할 때까지 걸리는 시간
정책 또는 앱을 배포하면 Intune에서는 Intune 서비스에 체크 인해야 한다는 알림을 장치에 즉시 보내기 시작합니다. 이 과정은 대개 5분 이내에 완료됩니다.

첫 번째 알림을 보낸 후 장치가 정책을 수신하기 위해 체크 인하지 않으면 알림을 3번 더 보냅니다.  장치가 꺼져 있거나 네트워크에 연결되어 있지 않은 등 오프라인 상태인 경우에는 알림을 받지 못할 수 있습니다.

이 경우 장치는 아래와 같이 다음에 예약된 Intune 서비스 체크 인 시에 정책을 수신하게 됩니다.

- iOS - 6시간마다
- Android - 8시간마다
- Windows Phone - 8시간마다
- 등록된 Windows RT 장치 - 24시간마다
- 장치로 등록된 Windows 8.1 및 Windows 10 PC - 8시간마다

장치를 방금 등록한 경우에는 다음과 같이 체크 인 빈도가 더 높아집니다.

- iOS - 6시간 동안 15분마다/그 이후에는 6시간마다
- Android - 15분 동안 3분마다/그 이후 2시간 동안은 15분마다/그 이후에는 8시간마다
- Windows Phone - 15분 동안 5분마다/그 이후 2시간 동안은 15분마다/그 이후에는 8시간마다
- 장치로 등록된 Windows PC - 30분 동안 3분마다/그 이후에는 24시간마다

사용자는 언제든지 회사 포털 앱을 시작하여 장치를 동기화해 즉시 정책을 확인할 수도 있습니다.

### Intune에서 장치에 알림을 즉시 보내도록 하는 작업
장치는 체크 인하라는 알림을 받거나 위의 표에 나와 있는 정기 예약 체크 인 시간 동안 Intune에 체크 인합니다.  데이터 지우기, 잠금, 암호 다시 설정, 앱 배포, 프로필 배포(Wi-Fi, VPN, 메일 등) 또는 정책 배포와 같은 특정 작업으로 장치나 사용자를 대상으로 지정하면 Intune에서는 이러한 업데이트를 받으려면 Intune 서비스에 체크 인해야 한다는 알림을 장치에 즉시 보내기 시작합니다.

회사 포털에서 연락처 정보를 수정하는 등의 기타 변경 작업을 수행하는 경우에는 장치에 알림이 즉시 전송되지 않습니다.

> [!TIP]
> 설정을 포함하는 정책을 Android 장치에 배포하는 경우 정책을 준수하기 위해 작업을 수행해야 한다는 메시지가 사용자에게 표시됩니다. 사용자가 이 작업을 수행하거나 장치를 다시 시작할 때까지 새 정책 설정은 적용되지 않습니다.

### 여러 정책을 같은 사용자 또는 장치에 배포하는 경우 적용되는 설정을 확인하는 방법
둘 이상의 정책을 같은 사용자 또는 장치에 배포할 때는 개별 설정 수준에서 적용되는 설정을 평가합니다.

-   준수 정책 설정은 항상 구성 정책 설정보다 우선적으로 적용됩니다.

-   다른 준수 정책의 동일 설정과 대조하여 평가하는 경우 더 제한적인 준수 정책 설정이 적용됩니다.

-   다른 구성 정책의 동일 설정과 대조하여 평가하는 경우 가장 제한적인 구성 정책 설정이 적용됩니다.

### MAM(모바일 응용 프로그램 관리) 정책이 서로 충돌하는 경우 앱에 적용되는 정책
다시 설정 전까지의 PIN 입력 시도와 같이 숫자 입력 필드에 대한 설정을 제외하면, 충돌하는 값은 모바일 응용 프로그램 관리 정책에서 사용 가능한 가장 제한적인 설정으로 지정됩니다.  숫자 입력 필드의 경우 권장 설정 옵션을 사용하여 콘솔에서 MAM 정책을 만드는 경우의 값과 동일하게 설정됩니다.

두 정책 설정이 동일하면 충돌이 발생합니다.  복사/붙여넣기 설정을 제외하면 동일한 두 MAM 정책을 구성한 경우를 예로 들 수 있습니다.  이 경우 복사/붙여넣기 설정이 가장 제한적인 값으로 설정되며 나머지 설정은 구성된 대로 적용됩니다.

정책 하나를 앱에 배포하여 적용한 후에 두 번째 정책을 배포하는 경우 처음 배포한 정책이 우선권을 가지게 되므로 적용된 상태로 유지되고 두 번째 정책은 충돌하는 정책으로 표시됩니다. 그러나 두 정책을 동시에 적용하는 경우에는 먼저 적용된 정책이 없으므로 두 정책 모두 충돌하는 상태가 되며, 충돌하는 설정은 가장 제한적인 값으로 설정됩니다.

### iOS 사용자 지정 정책 충돌 시의 결과
Intune은 Apple 구성 파일 또는 사용자 지정 OMA-URI 정책 페이로드를 평가하지 않으며 전달 메커니즘으로만 작동합니다.

따라서 사용자 지정 정책을 배포할 때는 구성된 설정이 준수, 구성 또는 기타 사용자 지정 정책과 충돌하지 않는지 확인해야 합니다. 설정이 충돌하는 사용자 지정 정책에서는 설정이 임의 순서에 따라 적용됩니다.

### 정책이 삭제되거나 더 이상 적용할 수 없는 경우 어떻게 되나요?
정책을 삭제하거나 정책이 배포된 그룹에서 장치를 제거하면, 정책 및 설정이 다음 테이블에 따라 장치에서 제거됩니다.

#### 등록된 장치

- Wi-Fi, VPN, 인증서 및 전자 메일 프로필 - 이러한 프로필은 지원되는 모든 등록된 장치에서 제거됩니다.
- 다른 모든 정책 유형
    - **Windows 및 Android 장치** -설정이 장치에서 제거되지 않습니다.
    - **Windows Phone 8.1 장치** - 다음 설정이 제거됩니다.
        - 모바일 장치의 잠금을 해제하는 데 암호 필요
        - 단순 암호 허용
        - 최소 암호 길이
        - 필수 암호 유형
        - 암호 만료(일)
        - 암호 기록 기억
        - 장치를 초기화하기 전까지 허용되는 로그인 반복 오류 횟수
        - 암호를 요구하기 전까지 비활성 시간(분)
        - 필수 암호 유형 - 최소 문자 집합 수
        - 카메라 허용
        - 모바일 장치 암호화 필요
        - 이동식 저장소 허용
        - 웹 브라우저 허용
        - 앱 스토어 허용
        - 화면 캡처 허용
        - 지리적 위치 허용
        - Microsoft 계정 허용
        - 복사 및 붙여넣기 허용
        - Wi-Fi 테더링 허용
        - 무료 Wi-Fi 핫스팟에 자동 연결 허용
        - Wi-Fi 핫스팟 보고 허용
        - 공장 재설정 허용
        - Bluetooth 허용
        - NFC 허용
        - Wi-Fi 허용
    
    - **iOS** - 다음을 제외한 모든 설정이 제거됩니다.
        - 음성 로밍 허용
        - 데이터 로밍 허용
        - 로밍하는 동안 자동 동기화 허용

#### Intune 클라이언트 소프트웨어를 실행하는 Windows PC

- **Endpoint Protection 설정** - 설정이 원래 권장 값으로 복원됩니다. 유일한 예외는 기본값이 **아니요** 인 **Microsoft 활성 보호 서비스에 가입**설정입니다. 자세한 내용은 [Microsoft Intune용 Endpoint Protection을 사용한 Windows PC의 보안 유지 방법](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md) 항목을 참조하세요.
- **소프트웨어 업데이트 설정** - 설정이 운영 체제의 기본 상태로 다시 설정됩니다. 자세한 내용은 [Microsoft Intune에서 소프트웨어 업데이트를 사용하여 Windows PC를 최신 상태로 유지](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md) 항목을 참조하세요.
- **Microsoft Intune Center 설정** - 정책에서 구성된 모든 지원 연락처 정보가 컴퓨터에서 삭제됩니다.
- **Windows 방화벽 설정** - 설정이 컴퓨터 운영 체제의 기본값으로 다시 설정됩니다. 자세한 내용은 [Microsoft Intune용 Endpoint Protection을 사용한 Windows PC의 보안 유지 방법](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md) 항목을 참조하세요.





<!--HONumber=May16_HO3-->


