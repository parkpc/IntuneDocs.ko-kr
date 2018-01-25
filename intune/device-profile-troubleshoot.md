---
title: "Microsoft Intune에서 장치 프로필 문제 해결"
titlesuffix: Azure portal
description: "문제가 발생하는 경우 이 항목의 정보를 참조하여 Intune 장치 프로필 관련 문제를 해결할 수 있습니다.\""
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 1/17/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0bc5ad6e0467fe8a8c98c1ad2d71b967c18b8233
ms.sourcegitcommit: 967a7c23b863123398c40b812e2eb02c921a0afe
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/18/2018
---
# <a name="troubleshooting-device-profiles-in-microsoft-intune"></a>Microsoft Intune에서 장치 프로필 문제 해결


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

이 항목의 정보를 사용하여 Intune 장치 프로필과 관련된 일반적인 문제를 해결할 수 있습니다.

## <a name="why-doesnt-a-user-get-a-new-profile-when-changing-a-password-or-passphrase-on-an-existing-wi-fi-profile"></a>기존 Wi-Fi 프로필에서 암호를 변경할 때 사용자가 새 프로필을 받지 못하는 이유는 무엇인가요? 
회사 Wi-Fi 프로필을 만들고, 프로필을 그룹에 배포하고, 암호를 변경하고, 프로필을 저장할 때 사용자는 새 프로필을 받게 됩니다. 하지만 사용자가 새 프로필을 받지 못할 수 있습니다. 

이런 문제를 방지하려면 회사 Wi-Fi에 장애가 발생할 경우 사용자가 게스트 Wi-Fi로 대체하도록 게스트 Wi-Fi를 설정해야 합니다. 자동으로 연결하는 설정을 사용하도록 설정해야 합니다. 게스트 Wi-Fi 프로필은 모든 사용자에게 배포해야 합니다.

다음과 같은 권장 사항이 몇 가지 더 있습니다.
- 연결하려는 Wi-Fi 네트워크에 암호가 사용되므로 Wi-Fi 라우터에 직접 연결할 수 있는지 확인합니다. iOS 장치로 테스트할 수 있습니다.
- Wi-Fi 끝점(Wi-Fi 라우터)에 연결을 완료한 후 사용한 SSID와 자격 증명(암호)을 기록해 둡니다
- 미리 공유한 키 필드에 SSID와 자격 증명(암호)을 입력합니다. 
- 사용자 수가 제한된 테스트 그룹(가급적 IT 팀)에 배포합니다. 
- iOS 장치를 Intune에 동기화합니다. 아직 등록하지 않은 경우 등록합니다. 
- 동일한 Wi-Fi 끝점에 다시 연결을 테스트합니다(첫 번째 단계 참조).
- 더 큰 그룹에 롤아웃하고 최종적으로 조직의 모든 예상 사용자에게 롤아웃합니다. 

## <a name="how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-assigned"></a>정책 또는 앱을 할당한 후 모바일 장치에서 해당 정책 또는 앱을 수신할 때까지 걸리는 시간
정책 또는 앱을 할당하면 Intune에서는 Intune 서비스에 체크 인해야 한다는 알림을 장치에 즉시 보내기 시작합니다. 이 과정은 대개 5분 이내에 완료됩니다.

첫 번째 알림을 보낸 후 장치가 정책을 수신하기 위해 체크 인하지 않으면 알림을 3번 더 보냅니다. 장치가 꺼져 있거나 네트워크에 연결되어 있지 않은 등 오프라인 상태인 경우에는 알림을 받지 못할 수 있습니다. 이 경우 장치는 다음과 같이 Intune 서비스를 사용하여 예약된 다음 체크 인에서 정책을 가져옵니다.

- iOS 및 macOS: 6시간마다
- Android: 8시간마다
- Windows Phone: 8시간마다
- 장치로 등록된 Windows 8.1 및 Windows 10 PC: 8시간마다

방금 등록된 장치인 경우 다음과 같이 체크 인 빈도가 더 빈번합니다.

- iOS 및 macOS: 6시간 동안 15분마다, 그 이후 6시간마다
- Android: 15분 동안 3분마다, 그 이후 2시간 동안 15분마다, 그 이후 8시간마다
- Windows Phone: 15분 동안 5분마다, 그 이후 2시간 동안 15분마다, 그 이후 8시간마다
- 장치로 등록된 Windows PC: 30분 동안 3분마다, 그 이후 8시간마다

사용자는 언제든지 회사 포털 앱을 열어 장치를 동기화해 즉시 정책을 확인할 수도 있습니다.

사용자 선호도가 없는 장치의 경우 등록 직후의 동기화 빈도는 몇 시간에서 하루 이상으로 다양합니다. Intune은 장치에서 서비스를 체크 인하기 위해 다양한 간격으로 요청을 보냅니다. 그러나 아직도 장치의 결정에 따라 실제로 그렇게 수행됩니다. 초기 등록 후에는 장치 등록 형식과 장치에 할당된 정책 및 프로필에 따라 장치에서 해당 체크 인을 완료하는 데 걸리는 시간을 예측할 수 없습니다. 그러나 장치가 등록되고 모든 초기 정책이 적용되면 장치에서 약 6시간마다 새 정책을 확인해야 합니다.

## <a name="what-actions-cause-intune-to-immediately-send-a-notification-to-a-device"></a>Intune에서 장치에 알림을 즉시 보내도록 하는 작업
장치는 체크 인하라는 알림을 받거나 정기 예약 체크 인 중에 Intune에 체크 인합니다. 초기화, 잠금, 암호 재설정, 앱 할당, 프로필 할당(Wi-Fi, VPN, 메일 등) 또는 정책 할당과 같은 작업을 통해 구체적으로 장치 또는 사용자를 대상으로 지정하면, Intune에서 이러한 업데이트를 받으려면 Intune 서비스에 체크 인해야 한다는 알림을 장치에 즉시 보내기 시작합니다.

회사 포털에서 연락처 정보를 수정하는 등의 기타 변경 작업을 수행하는 경우에는 장치에 알림이 즉시 전송되지 않습니다.

## <a name="if-multiple-policies-are-assigned-to-the-same-user-or-device-how-do-i-know-which-settings-gets-applied"></a>여러 정책을 같은 사용자 또는 장치에 할당하는 경우 적용되는 설정은 어떻게 확인할 수 있는가요?
둘 이상의 정책을 같은 사용자 또는 장치에 할당할 때는 개별 설정 수준에서 적용되는 설정을 평가합니다.

-   준수 정책 설정은 항상 구성 정책 설정보다 우선적으로 적용됩니다.

-   다른 준수 정책의 동일 설정과 대조하여 평가하는 경우 더 제한적인 준수 정책 설정이 적용됩니다.

-   구성 정책 설정이 다른 구성 정책의 설정과 충돌하는 경우 이 충돌은 Azure Portal에 표시됩니다. 이러한 충돌은 수동으로 해결해야 합니다.

## <a name="what-happens-when-app-protection-policies-conflict-with-each-other-which-one-is-applied-to-the-app"></a>앱 보호 정책이 서로 충돌하는 경우 어떤 정책을 앱에 적용해야 할까요?
다시 설정 전까지의 PIN 입력 시도와 같이 숫자 입력 필드에 대한 설정을 제외하면, 충돌하는 값은 앱 보호 정책에서 사용 가능한 가장 제한적인 설정으로 지정됩니다. 권장 설정 옵션을 사용하여 콘솔에서 MAM 정책을 만든 것처럼 숫자 입력 필드는 값과 동일하게 설정됩니다.

두 프로필 설정이 동일하면 충돌이 발생합니다. 복사/붙여넣기 설정을 제외하면 동일한 두 MAM 정책을 구성한 경우를 예로 들 수 있습니다. 이 시나리오에서는 복사/붙여넣기 설정이 가장 제한적인 값으로 설정되지만, 나머지 설정은 구성된 대로 적용됩니다.

앱에 하나의 프로필을 할당하여 적용한 후에 두 번째 프로필을 할당하면, 첫 번째 프로필이 우선 순위가 높으므로 계속 적용되며, 두 번째 프로필은 충돌하는 프로필로 표시됩니다. 둘 다 동시에 적용되면 이전 프로필이 없다는 것을 의미하므로 두 프로필이 충돌하게 됩니다. 충돌하는 설정은 가장 제한적인 값으로 설정됩니다.

## <a name="what-happens-when-ios-custom-policies-conflict"></a>iOS 사용자 지정 정책 충돌 시의 결과
Intune은 Apple 구성 파일 또는 사용자 지정 OMA-URI(Open Mobile Alliance Uniform Resource Identifier) 프로필 페이로드를 평가하지 않으며 전달 메커니즘으로만 작동합니다.

사용자 지정 프로필을 할당할 때는 구성된 설정이 준수, 구성 또는 기타 사용자 지정 정책과 충돌하지 않는지 확인해야 합니다. 설정이 충돌하는 사용자 지정 프로필에서는 설정이 임의 순서에 따라 적용됩니다.

## <a name="what-happens-when-a-profile-is-deleted-or-no-longer-applicable"></a>프로필이 삭제되거나 더 이상 적용할 수 없는 경우 어떻게 되나요?
프로필을 삭제하거나 프로필이 할당된 그룹에서 장치를 제거하면, 다음 목록에 따라 장치에서 프로필 및 설정이 제거됩니다.

### <a name="enrolled-devices"></a>등록된 장치

- Wi-Fi, VPN, 인증서 및 전자 메일 프로필: 이러한 프로필은 지원되는 모든 등록된 장치에서 제거됩니다.
- 모든 기타 프로필 유형:
    - **Windows 및 Android 장치**: 설정이 장치에서 제거되지 않습니다.
    - **Windows Phone 8.1 장치**: 다음 설정이 제거됩니다.
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

    - **iOS**: 다음을 제외한 모든 설정이 제거됩니다.
        - 음성 로밍 허용
        - 데이터 로밍 허용
        - 로밍하는 동안 자동 동기화 허용

## <a name="i-changed-a-device-restriction-profile-but-the-changes-havent-taken-effect"></a>장치 제한 프로필을 변경했지만 변경 내용이 적용되지 않습니다.
Windows Phone은 MDM 또는 EAS를 통해 보안 정책을 설정하면 이 정책의 보안 강도가 줄어드는 것을 허용하지 않습니다. 예를 들어 **문자 암호의 최소 수** 를 8로 설정한 다음 4로 줄이려고 합니다. 더 제한적인 프로필이 이미 장치에 적용되었습니다.

장치 플랫폼에 따라서는 프로필을 덜 안전한 값으로 변경하려는 경우 보안 정책을 다시 설정해야 할 수 있습니다.
예를 들어, 데스크톱 Windows에서는, 오른쪽에서 안쪽으로 살짝 밀어 **참 메뉴** 모음을 열고 **설정** &gt; **제어판**을 선택합니다. **사용자 계정** 애플릿을 선택합니다.
왼쪽 탐색 메뉴의 아래쪽에 **보안 정책 재설정** 링크가 있습니다. 선택한 후 **정책 재설정** 단추를 선택합니다.
Android, Windows Phone 8.1 이상 및 iOS와 같은 기타 MDM 장치의 경우 제한적인 프로필을 적용할 수 있도록 사용을 중지하고 덜 서비스에 다시 등록해야 해야 합니다.


### <a name="next-steps"></a>다음 단계
문제 해결 정보가 도움이 되지 않는 경우 [Microsoft Intune에 대한 지원을 받는 방법](get-support.md)의 설명에 따라 Microsoft 지원에 문의하세요.