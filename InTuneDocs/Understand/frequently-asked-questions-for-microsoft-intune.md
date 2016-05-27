---
# required metadata

title: 질문과 대답 | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: a8126cca-9ec4-454b-a20b-dc1bb6797327

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Intune에 대한 질문과 대답
이 문서는 Intune에 대한 몇 가지 자주 묻는 질문에 대답합니다. 여기에서 질문에 대한 답변을 찾을 수 없는 경우 [알려 주세요](https://microsoftintune.uservoice.com/)..

## 일반적인 문제

-   **Intune 서비스가 업데이트된 때를 어떻게 알 수 있나요?**

    manage.microsoft.com에서 계정에 로그온합니다. 관리 개요에서 **서비스 상태 보기**를 선택합니다. 테넌트의 위치와 유지 관리 일정이 표시됩니다. [새로운 기능](/intune/deploy-use/whats-new-in-microsoft-intune) 문서에서 서비스 업데이트를 참조하세요.

-   **사용자가 회사 포털 앱 내에서 장치 이름을 바꿀 경우 해당 이름이 Intune 또는 Configuration Manager에서도 변경되나요?**

    아니요. 해당 이름은 사용자의 편의를 위해서만 변경됩니다.

-   **모바일 장치용 Intune에 원격 지원 기능이 있나요?**

    없습니다. [Bomgar](http://www.bomgar.com/) 및 [TeamViewer](https://www.teamviewer.com/)와 같은 타사 앱이 유용할 수 있습니다.

## 계정

-   **Intune의 평가를 시작하고 평가판에 대해 새 테넌트를 만드는 경우 동일한 테넌트를 사용하여 평가에 Office 365를 추가할 수 있나요?**

    예. globaladmin@&lt;company&gt;.onmicrosoft.com과 같은 기존 Intune 테넌트/구독의 전역 관리자를 사용하여 로그인하세요..

-   **평가판 구독 중에 Intune에 MDM 기관을 할당하는 경우 중간에 다른 회사의 서비스로 전환하는 것이 어려운가요?**

    Intune 외에 다른 서비스를 사용하시는 것을 생각해 보지는 않았지만, 선택한 MDM 기관이 다른 서비스로의 이동 가능성에 영향을 미치지 않습니다. 특히 Intune을 선택하든, System Center Configuration Manager와 Intune을 선택하든, 아무런 문제가 없습니다.

-   **기존 Office 365 도메인 이름을 후속 Intune 계정으로 사용할 수 있나요?**

    그렇습니다. Intune 평가판을 만들거나 라이선스를 활성화할 때 기존 Office 365 테넌트 및 확인된 도메인과 연결된 조직 ID를 사용하여 로그인하는 경우는 가능합니다.

    Intune은 Office 365 계정의 경우처럼 동일한 도메인/사용자/등을 사용합니다. 각 Office 365 사용자는 Intune 라이선스를 사용하여 Intune 사용자로 설정되어야 합니다. 이 작업은 테넌트를 관리하는 전역 관리자가 수행해야 합니다.

## 등록

-   **사용자는 어디에서 장치 등록 방법을 익힐 수 있나요?**

    [IT 관리자에 대한 최종 사용자 Intune 등록 지침](https://gallery.technet.microsoft.com/End-user-Intune-enrollment-55dfd64a)의 정보를 사용하거나 사용자 지정할 수 있습니다..

-   **장치 등록 문제를 해결하려면 어떻게 해야 하나요?**

    일반적인 등록 문제를 해결하는 방법은 [Intune에서 장치 등록 문제 해결](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune)에 제공됩니다..

-   **사용자에게 등록 문제가 발생하는 경우 등록 로그를 수집하려면 어떻게 해야 하나요?**

    [이 지침](http://www.microsoft.com/en-us/download/46391)을 따르세요..

## 모바일 장치 관리

-   **일반 MDM**

    -   **장치가 무단 해제되었는지 여부를 Intune에서 알 수 있나요?**

        일부 운영 체제의 경우는 알 수 있습니다. 무단 해제된 장치를 관리하는 방법에 대한 자세한 내용은 [장치 준수 정책 만들기](/intune/deploy-use/create-a-device-compliance-policy-in-microsoft-intune.md)를 참조하세요..

    -   **장치에서 회사 데이터를 선택적으로 초기화할 수 있나요?**

        예. 선택적 초기화에 대한 자세한 내용은 [원격 초기화, 원격 잠금 또는 암호 재설정으로 데이터 보호 지원](/intune/deploy-use/use-remote-lock-and-passcode-reset-in-microsoft-intune.md)을 참조하세요..

    -   **Intune을 통해 모바일 장치 브라우저의 특정 웹 사이트를 차단하는 방법이 있나요?**

        플랫폼의 기본 브라우저에는 없습니다. 그러나 iOS 및 Android 장치에서 관리되는 Intune을 배포할 때 URL을 차단하거나 허용할 수 있습니다. 자세한 내용은 [Managed Browser 정책을 사용하여 인터넷 액세스 관리](/intune/Deploy-Use/Manage-Internet-access-using-managed-browser-policies-with-Microsoft-Intune.md)를 참조하세요..

    -   **사용자의 앱 제거를 제한할 수 있나요?**

        일반적으로는 제한할 수 없습니다. 그러나 감독된 iOS 장치에서는 Apple Configurator를 사용하여 배포된 앱의 제거를 방지할 수 있습니다. 

    -   **모바일 데이터 사용을 관리하는 방법이 있나요?**

        직접적으로는 없지만 [Wi-Fi 프로필을 사용하여 회사 네트워크에 연결하도록 지원](/intune/Deploy-Use/wi-fi-connections-in-microsoft-intune.md)에 설명된 대로 Wi-Fi 프로필을 장치에 푸시하여 기본 연결 방법이 Wi-Fi가 되도록 할 수 있습니다. 또한 일부 플랫폼(예: iOS 및 Android KNOX)에서는 음성 및 데이터 로밍과 같은 설정을 제어할 수 있습니다.

    -   **사용자가 장치를 등록 취소하지 못하게 하는 방법이 있나요? 회사 소유의 장치라면 어떤가요?**

        일반적으로는 없습니다. 그러나 사용자 지정 Windows Phone 설정을 사용하여 Windows Phone 8.1에서 사용자 등록 취소를 방지할 수 있습니다. 또한 Apple DEP(장치 등록 프로그램)에서 감독되고 등록되는 iOS 장치의 경우에는 사용자가 장치 등록을 취소하지 못하게 할 수 있습니다.

    -   **선택한 MDM 기관을 전환할 수 있나요?**

        상황에 따라 MDM 기관을 전환할 수 있습니다. 이렇게 하려면 [Microsoft Intune에 대한 지원을 받는 방법](/intune/Troubleshoot/How-to-get-support-for-Microsoft-Intune.md)에 설명된 대로 고객 지원에 문의하세요. 아래 표에 가능한 변경 내용이 나와 있습니다. MDM 기관을 변경하려면 장치를 다시 등록해야 합니다.

        ||**대상:** Intune!**대상:** O365|**대상:** Configuration Manager(Intune 포함)
        |**시작:** Intune| |예&#42;|예|
        |**시작:** O365||예&#42;||예|
        |**시작:** Configuration Manager(Intune 포함)|예|예| |
        
        &#42;O365 및 Intune MDM 기관은 공존할 수 있으므로 모바일 장치를 다시 등록할 필요가 없습니다.



-   **Windows**

    -   **Windows 스토어 앱을 테스트용으로 로드할 수 있나요?**

        공개적으로 사용할 수 있는 앱은 테스트용으로 로드할 수 없습니다. XAP를 다운로드할 수는 있지만 공용 XAP이고, 개발자의 코드 서명 인증서로 암호화되고 서명되어 있으므로 Intune에 업로드할 수 없습니다. 직접 개발하고 본인의 코드 서명 인증서로 서명한 앱만 테스트용으로 로드될 수 있습니다.

    -   **회사 포털을 통해 배포되는 Windows Phone 스토어 앱을 사용하려면 최종 사용자에게 Microsoft 계정이 있어야 하나요?**

        그렇습니다. 최종 사용자는 Microsoft 계정이 있어야만 앱을 가져올 수 있습니다. 단, 테스트용으로 로드된 개인 LOB 앱은 Microsoft 계정 없이 장치에 배포할 수 있습니다.

    -   **Intune에서 Windows Phone 8.1을 관리하려면 Microsoft 계정이 필요한가요?**

        아니요. 그렇지만 공용 스토어의 앱 대부분을 설치하는 데는 계정이 필요합니다.

        **Windows Phone에서 관리하는 데 Symantec 인증서 필요한 이유가 무엇입니까?**
        Windows Phone에서 앱을 설치하는 방법을 제어합니다. Microsoft 계정을 가진 모든 사용자가 Windows Phone 스토어에서 앱을 설치하거나, 회사에서 Windows Phone 설명서에 나와 있는 특정 프로세스를 통해 내부적으로 개발한 LOB(기간 업무) 앱을 설치 또는 테스트 로드할 수 있습니다. LOB 앱을 설치하면 Windows Phone은 Symantec이 발급한 특수 유형의 인증서 하나만 신뢰합니다. 시중에 판매되거나 개인적으로 생성한 다른 인증서는 사용할 수 없습니다. 이 요구 사항은 Intune뿐만 아니라 모든 모바일 장치 관리 솔루션에 적용됩니다.

        Symantec 인증서는 AET(응용 프로그램 등록 토큰)를 만듭니다. 장치를 모바일 장치 관리용으로 등록하거나, 대역 외 보안 웹사이트 또는 전자 메일 첨부 파일에서 설치할 수 있는 경우 장치에 AET를 설치할 수 있습니다. 관리자는 [Windows Phone SDK](http://go.microsoft.com/fwlink/?LinkId=268439)에서 제공하는 도구를 이용하여 Symantec 인증서를 사용하는 모든 LOB 앱에 서명해야 합니다. 사용자가 LOB 앱을 설치하려고 하면 Windows Phone 운영 체제에서 AET의 서명을 앱의 서명과 비교하여 확인합니다. 서명이 일치하면 설치를 계속 진행하도록 허용하지만, AET를 확인할 수 없으면 설치하지 못합니다. AET를 확인할 수 없는 몇 가지 이유는 다음과 같습니다.

        -   장치에 AET를 설치하지 않은 경우

        -   AET가 만료된 경우

        -   앱에 서명하는 데 사용된 동일한 Symantec 인증서로 AET를 만들지 않은 경우

        Windows Phone에서는 MDM을 등록할 때 AET를 표시할 필요가 없지만, 2014년 11월 릴리스 이전의 Intune에서는 등록할 때 외에는 AET 및 ssp.xap를 설치할 수 있는 다른 방법이 없기 때문에 AET와 서명된 ssp.xap가 필요합니다.

    **Intune 사용자용 AET를 만드는 방법은 무엇입니까?**
  관리자가 해당 Symantec 인증서에 필요한 .pfx 파일을 업로드하면 Intune에서 AET를 자동으로 만들어 등록된 Windows Phone에 배포합니다. 따라서 Intune 관리자가 Windows Phone SDK에서 AET 생성기 도구를 사용할 필요가 없습니다.

      > [!IMPORTANT]
        > Intune은 AET의 수동 생성과 대역 외 배포를 지원하지 않습니다.

    **Symantec 인증서에 대한 요구 사항을 줄이기 위해 변경된 점은 무엇입니까?**
       2014년 11월 릴리스의 Intune은 회사에 Symantec 인증서가 없는 경우의 시나리오를 허용하도록 변경되었습니다.

       -   Windows Phone 8.1용 회사 포털은 저장소에서 설치하는 데 사용할 수 있으므로, Symantec 인증서로 서명하고 AET에 대한 유효성을 검사하지 않아도 됩니다. 대신 저장소 게시 프로세스의 일부로 앱의 유효성을 검사합니다.

        -   Windows Phone 8.1 장치는 휴대폰에 AET가 있든, 없든 등록할 수 있습니다. AET를 사용할 수 있는 경우 Intune으로 장치를 처음 동기화할 때 AET가 설치됩니다. AET 없는 경우에도 Intune에서 장치를 계속 관리할 수 있으며, 사용자가 저장소에서 회사 포털을 설치하고 Symantec 인증서 없이도 회사 포털의 기능을 대부분 사용하여 앱에 서명할 수 있습니다.

        Windows Phone 8 장치에 대한 Symantec 요구 사항에는 변경된 사항이 없습니다. Windows Phone 8 장치는 등록할 때 표시되는 AET와 서명된 ssp.xap가 있어야 합니다. 그렇지 않으면 등록에서 차단됩니다.

        **Windows Phone 8.1 장치를 등록했지만 Symantec 인증서가 없는 경우 지원되는 기능은 무엇입니까?**
        Windows Phone 8.1 장치를 등록했지만 Symantec 인증서에 없는 경우 다음 기능을 사용할 수 있습니다.

        -   정책을 만들어 장치에 푸시

        -   회사 포털에 표시할 IT 부서의 연락처 정보 구성

        -   저장소에 딥 링크를 만들어 회사 포털에 배포

        -   웹 페이지 링크를 만들어 회사 포털에 배포

        -   회사 포털을 사용하기 전에 사용자가 동의해야 하는 사용 약관 만들기

        Symantec 인증서 없이도 수행할 수 있는 한 가지 기능은 LOB 앱을 배포하는 것입니다.

        > [!IMPORTANT]
        > Intune 소프트웨어 게시자는 앱에 업로드할 때 서명되어 있는지 확인하지 않습니다. 서명되지 않은 앱을 배포하는 경우 사용자가 설치하려고 하면 실패합니다.

        **회사 포털은 있지만 Symantec 인증서는 없는 경우 사용자가 수행할 수 있는 작업은 무엇입니까?**
        사용자가 저장소에서 회사 포털을 설치하기 전에는 Windows Phone 8.1 장치를 등록할 필요가 없습니다. 장치를 등록하지 않은 경우 사용자에게 등록하라는 메시지가 표시됩니다. 회사 포털에서 메시지를 터치하면 사용자가 해당 장치를 등록할 수 있는 **설정/작업 공간**으로 바로 안내됩니다.

        장치를 등록하지 않고도 사용자는 저장소에서 설치한 회사 포털을 통해 다음과 같은 작업을 수행할 수 있습니다.

        -   관리자가 구성한 사용 약관 동의 또는 거부 사용자가 사용 약관을 거부하면 회사 포털이 닫힙니다.

        -   IT 부서의 연락처 정보 확인

        -   IOS, Android 및 Windows 장치 등 등록된 장치 확인

        -   저장소에서 앱의 딥 링크 사용

        -   웹 링크를 사용하여 웹 페이지 열기

        장치를 등록하면 사용자는 **내 장치** 목록에서 장치를 볼 수 있습니다. 등록한 후에는 장치에 배포된 Intune 정책이 모두 적용됩니다. AET를 가져오고 LOB 앱을 설치하려면 장치를 등록해야 합니다. LOB 앱을 설치하려는 장치를 등록하지 않은 경우 등록할 수 있는 위치로 안내됩니다.

        회사에 Symantec 인증서가 없는 경우 사용자가 수행할 수 없는 단 한 가지 작업은 관리자가 배포한 LOB 앱을 설치하는 것입니다.

        **저희 회사는 이미 인증서를 보유하고 Windows Phone 8.1 장치를 등록했습니다. 이제 저장소에서 회사 포털을 사용할 수 있는데, 다른 작업을 수행해야 합니까?**
        현재 다운로드 센터의 ssp.xap는 Windows Phone 8.1 장치에서 여전히 작동합니다. 계속해서 설치할 때 회사 포털을 등록하고 가져오도록 사용자에게 안내할 수 있습니다.

        **사용자가 저장소에서 회사 포털을 가져오는 경우 어떤 장단점이 있습니까?**
        장점:

        -   Windows Phone 8.1 장치를 등록하지 않은 경우에도 사용자가 딥 링크와 웹 링크를 가져올 수 있음

        -   Microsoft가 회사 포털을 업데이트하는 경우 ssp.xap를 다운로드하고 서명, 재배포하지 않고도 저장소 앱을 자동으로 업데이트

        -   Windows Phone 8.1, iOS, Android 및 Windows 사용자에 대한 설명서가 일관된 경우: "저장소로 이동하여 회사 포털 설치"

        -   사용자가 설치한 앱을 확인하고 앱을 열 때 등록 지침을 가져올 수 있음

        단점:

        -   사용자에게 "**회사 허브**"를 설치하라는 확인란이 표시되지만 장치 앱 목록에 있는 회사 포털로 사용자를 안내하지는 않음

        -   사용자가 회사 포털을 열 때까지 사용자 지정 약관에 동의하도록 요구하지 않음

        다음과 같은 경우 계속해서 등록할 때 설치한 ssp.xap를 등록하고 보유하도록 사용자에게 안내할 수 있습니다.

        -   회사 블록을 통해 Windows Phone에서 저장소에 액세스하는 경우 사용자는 등록할 때 설치한 ssp.xap를 가져와야 합니다.

        -   해당 Windows Phone에 구성된 Microsoft 계정이 없는 사용자는 저장소에서 회사 포털을 설치할 수 없습니다.

        -   기존 Windows Phone 등록 설명서에 설정, 작업 공간으로 먼저 이동하라고 나와 있는 경우 해당 설명서를 업데이트하고 사용자를 저장소로 안내하는 동안 시간이 걸릴 수 있습니다.

        **다운로드 센터의 ssp.xap와 저장소 앱 간에는 어떤 차이점이 있습니까?**

        -   저장소의 회사 포털은 설치할 때 Symantec 인증서로 서명할 필요가 없음

        -   저장소의 회사 포털은 사용자에게 사용 약관을 표시하지만, 다운로드 센터의 ssp.xap는 표시하지 않음

        -   저장소의 회사 포털은 .xap 대신 .appx 사용

        **회사 포털 파일을 가져와서 저장소로 보내는 대신 저희 사용자에게 푸시할 수 있습니까?**
        예. 다운로드 센터에서 다음 운영 체제에 대한 회사 포털 앱을 다운로드할 수 있습니다.

        -   Windows Phone 8.1: [http://go.microsoft.com/fwlink/?LinkId=615799](http://go.microsoft.com/fwlink/?LinkId=615799)

        -   Windows Phone 8.0: [http://go.microsoft.com/fwlink/?LinkId=268440](http://go.microsoft.com/fwlink/?LinkId=268440)

        -   Windows 8.1: [http://go.microsoft.com/fwlink/?LinkId=615800](http://go.microsoft.com/fwlink/?LinkId=615800)

        **회사에 Symantec 인증서는 없지만 사용자가 저장소에서 계속 회사 포털을 설치할 수 있는 경우 회사에서 Windows Phone의 Windows Intune 평가판 관리용 지원 도구를 계속 사용할 수 있습니까?**
        예. LOB 앱 설치가 포함된 개념 증명을 수행해야 하는 경우 평가판 관리 도구는 회사 포털의 저장소 버전에서 작동합니다. 그러나 Windows Phone 8.1 장치를 등록하는 데 Symantec 인증서의 AET가 더 이상 필요하지 않기 때문에 회사에서 스토어 앱의 딥 링크를 사용하여 앱 설치를 테스트할 수 있습니다.

        Windows Phone의 Windows Intune 평가판 관리용 지원 도구는 Intune 평가판 구독 전용입니다.

        > [!IMPORTANT]
        > 평가판 관리 도구 테스트만 사용하세요. 평가판 관리 도구의 AET를 사용해 등록한 장치는 평가판 관리 도구용 Symantec 인증서를 더 이상 사용할 수 없거나 회사에서 서명 앱에 필요한 자체 Symantec 인증서를 확보한 경우 등록 취소하고 나서 다시 등록해야 합니다.

        **Windows Phone 8.1 장치를 등록한 후에도 회사에서 Symantec 인증서 없이 시작했다가 나중에 하나 추가할 수 있습니까?**
        예. Windows Phone 8.1 장치를 이미 등록했더라도 Symantec 인증서를 가져와 ssp.xap에 서명하고 ssp.xap 및 pfx 파일을 업로드할 수 있습니다. 그러면 Intune에서 AET를 생성합니다. Windows Phone 8.1 장치는 다음에 동기화할 때 최대 8시간 동안 AET를 가져옵니다. xap 및 pfx를 업로드하고 나서 LOB 앱을 배포하기 전에는 8시간 이상 가져올 수 있습니다.


-   **Android**

    -   **Android 장치를 암호화하는 데 시간이 얼마나 걸리나요?**

        소요 시간은 주로 장치의 프로세서 속도와 총 메모리 및 사용된 메모리 양에 따라 다르며 Intune의 기능과는 관련이 없습니다.

-   **iOS**

    -   **Intune을 사용하여 iOS 앱을 배포할 때 응용 프로그램의 IPA 및 매니페스트 파일이 업로드되지 않으면 계속 설치하기 위해 장치에 지정된 AppleID가 필요한가요?**

        아니요. Intune이 비트(Intune에 업로드된 IPA)를 제공하는 경우 응용 프로그램이 테스트용으로 로드되어 Apple ID가 필요하지 않습니다.

    -   **Apple 스토어에 대한 액세스를 허용하지 않고 iOS에서 앱을 설치하도록 하는 방법이 있나요?**

        아니요. 하지만 앱 스토어를 사용하도록 설정하고 iOS에서 허용된/차단된 앱을 사용하여 사용자가 수행하는 작업을 계속 감시할 수 있습니다. 테스트용으로 로드한 LOB 앱을 사용하기 위해 Apple 앱 스토어에 액세스할 필요는 없습니다.

    -   **회사 포털을 통해 배포되는 Apple 스토어 앱을 사용하려면 최종 사용자에게 iTunes 계정이 있어야 하나요?**

        그렇습니다. 최종 사용자는 iTunes 계정이 있어야만 앱을 가져올 수 있습니다.

    -   **앱 스토어를 차단할 수 있나요?**

        그렇습니다. 하지만 최종 사용자가 시작한 앱 설치 및 업데이트 뿐만 아니라 앱 스토어의 모든 앱 설치 및 업데이트가 차단됩니다. 즉, Intune에서 배포하는 모든 공용 앱 스토어 앱도 설치되지 않습니다.

## 앱 배포

-   **권장 앱을 추가하려면 어떻게 해야 하나요?**

    Intune에서는 이러한 앱을 "추천 앱"이라고 하며 이러한 앱은 [Microsoft Intune에서 앱 배포](/Intune/Deploy-Use/deploy-apps-in-microsoft-intune.md)에 설명되어 있습니다..

-   **배포하려는 앱에 대한 추가 클라우드 저장소를 얻을 수 있나요?**

    예. 클라우드 저장소 요구 사항 섹션의 [앱 배포](/Intune/Deploy-Use/deploy-apps.md)에서 이 내용을 확인할 수 있습니다..

## 보안

-   **BitLocker는 Intune을 통해 적용될 수 있나요?**

    Windows 8.1/RT의 OMA-DM 에이전트를 사용하면 암호화 상태를 읽거나 가져올 수 있습니다. 그렇지만 설정할 수는 없습니다. 이러한 사항은 Intune 및 다른 모바일 장치 관리 서비스의 경우에 해당됩니다.

-   **BitLocker를 사용하여 Windows 8 태블릿을 암호화하는 경우 사용자가 연속적으로 여러 번 로그온에 실패하면 전체 장치 초기화를 적용할 수 있나요?**

    Windows RT 8.1/RT 장치에 Intune을 비롯한 모바일 장치 관리 서비스에 대한 전체 초기화 옵션은 없습니다. Intune은 이러한 장치에 대해 선택적 초기화 기능을 제공합니다. Intune에서 초기화/선택적 초기화에 대한 자세한 내용은 [Microsoft Intune을 사용하여 앱 및 데이터 보호](/intune/Deploy-Use/protect-apps-and-data-with-microsoft-intune.md)를 참조하세요..

## 회사 포털

-   **회사 포털을 사용자 지정할 수 있나요?**

    예. Intune 관리 콘솔에서 해당 설정에 대한 **관리&gt;회사 포털**로 이동합니다.

## Configuration Manager와 Microsoft Intune

-   **Intune과 함께 Configuration Manager를 사용하는 경우 어디서 내 장치를 관리합니까?**

    Intune 에이전트가 설치된 장치가 Intune 콘솔에서 표시되는 경우에도 모든 장치는 Configuration Manager 콘솔에서 관리합니다. 모바일 장치는 Intune 콘솔에서 표시되지 않습니다.

-   **장치에서 선택적 초기화를 수행할 수 있나요?**

    Intune에서 System Center 2012 R2 Configuration Manager 이상을 사용하는 경우 회사 데이터를 제거하는 선택적 초기화를 수행할 수 있습니다. 자세한 내용은 [Microsoft Intune을 사용하여 앱 및 데이터 보호](/intune/Deploy-Use/protect-apps-and-data-with-microsoft-intune.md)를 참조하세요..

-   **Intune과 함께 Configuration Manager를 사용하는 경우 Intune 관리 포털을 계속 사용할 수 있나요?**

    사용할 수 있지만 Intune 에이전트가 설치된 PC만 해당 포털에서 관리할 수 있습니다. 포털에 서비스, 서비스 상태 등에 대한 경고와 관련된 일부 기타 유용한 정보가 있지만 장치 관리 설정이 등록된 장치에는 적용되지 않습니다.



<!--HONumber=May16_HO1-->


