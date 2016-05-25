---
# required metadata

title: 새로운 기능 | Microsoft Intune
description:
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune의 새로운 기능

## 2016년 4월
이 모든 기능은 하이브리드 고객에 대해서도 지원됩니다(Intune과 통합된 Configuration Manager).
### 앱 관리
- **MAM 사용자 규정 준수.**
이제 Azure Active Directory(AAD) 테넌트에 속하는 모든 사용자에 대한 응용 프로그램 관리 정책의 [상태](monitor-mobile-app-management-policies-with-Microsoft-Intune.md)를 볼 수 있습니다. 여기에는 다음 항목이 포함됩니다.
   - 장치
   - 장치의 앱

   상태 값:

   **Checked in**(체크 인 됨): 사용자에게 정책이 배포되었고, 회사 컨텍스트에서 앱이 사용되었으며, 성공적으로 정책이 수신되었다는 것을 나타냅니다.

    **Not checked in**(체크인 안됨): 사용자에게 정책이 배포되었지만, 그 뒤로 회사 컨텍스트에서 앱이 사용되지 않았다는 것을 나타냅니다.


- **Outlook 연락처 동기화를 방지하기 위한 MAM 컨트롤(Android).**
장치 등록 없이 새 설정을 [모바일 응용 프로그램 관리](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)에 사용할 수 있습니다. 이 설정을 통해 응용 프로그램이 Android 장치의 기본 주소록에 대해 연락처를 동기화하는 것을 방지할 수 있습니다. 이 설정을 사용하면, 대상 응용 프로그램은 연락처를 기본 주소록에 더 이상 저장할 수 없게 됩니다. 이 설정을 사용하지 않으면, 대상 응용 프로그램은 연락처를 기본 주소록에 저장할 수 있게 됩니다. [장치 또는 앱을 원격으로 초기](wipe-managed-company-app-data-with-Microsoft-Intune.md)화하는 경우, 기본 주소록에 이미 저장되어 있는 모든 연락처가 제거됩니다. 이 새로운 설정은 Android 장치의 Outlook 응용 프로그램에서 처음 지원됩니다.

### 장치 관리
- **회사 소유 장치에 대한 전화 번호 식별.** "회사"로 분류되는 전화는 이제 전체 전화 번호로 식별됩니다(예: 모바일 장치 인벤토리 보고서를 실행하는 경우). BYOD 전화 번호는 마지막 4자리만 표시되고 ****으로 계속 마스킹됩니다.


### 회사 포털 업데이트
**Android 회사 포털 앱**
Intune에 장치를 등록하지 않았거나 올바른 인증서가 설치되지 않은 사용자는 Android 회사 포털 앱에 로그인할 수 있으며 “You cannot sign in because your device is missing a required certificate.”(장치에 필요한 인증서가 없어서 로그인할 수 없습니다.)라는 메시지를 보게 됩니다. 메시지에는 “해결 방법” 링크가 포함되며, 사용자가 이 링크를 탭하면 인증서 설치에 대한 지침을 볼 수 있습니다. 최종 사용자가 문제를 해결하기 위해 수행하는 단계를 보려면 [장치에 필요한 인증서가 없습니다.](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_cert_missing) 참조하세요..

**iOS 회사 포털 앱**
홈 화면의 콘텐츠를 새로 고치기 위해 끌어오기-새로 고침 작업에 대한 지원이 추가되었습니다. 여기에는 나열된 앱, 나열된 장치, 및 IT 연락처 정보가 포함됩니다. 끌어오기-새로 고침 작업은 정책 또는 준수 정보를 확인하지 않습니다. 이 작업은 현재 장치의 타일을 선택하고 **동기화** 단추를 탭하여 수행할 수 있습니다.

**Windows 10 Mobile 및 Windows Phone 8.1 회사 포털 앱**
최종 사용자가 LOB(기간 업무) 앱을 설치하는 경우, 향상된 앱 설치 환경이 표시됩니다. 앱 설치가 너무 오래 걸리면, 사용자는 동기화 프로세스가 다시 시작되도록 장치를 수동으로 동기화할 수 있습니다. 최종 사용자 지침을 검토하려면 [앱 설치 속도를 높이기 위해 장치를 수동으로 동기화](https://technet.microsoft.com/library/mt427782.aspx#BKMK_win10m_wp81_sync_manually)를 참조하세요..

**회사 포털 웹 사이트**
Windows 10 Mobile 및 Windows Phone 8.1 사용자가 LOB(기간 업무) 앱을 설치하는 경우, 다음과 같은 새로운 상태가 표시되어, 사용자의 설치 상태에 대해 보다 자세한 정보를 제공하게 됩니다.

* **장치가 동기화될 때까지 기다리는 중** – 사용자가 “설치”를 탭했고 이제 장치가 Intune 인프라와의 동기화를 시도합니다. 설치를 완료하려면 그 전에 동기화가 필요합니다. "장치가 동기화될 때까지 기다리는 중" 메시지 역시 사용자가 탭하면, 동기화 프로세스가 너무 오래 걸리거나 멈춘 경우 Intune에서 장치를 수동으로 동기화하는 방법에 대한 [지침](https://technet.microsoft.com/library/mt590895.aspx#BKMK_iwp_sync_manually)을 볼 수 있는 링크입니다.
* **다운로드 중** – 사용자의 다운로드 요청이 처리 중이며 장치가 앱을 다운로드 및 설치 중입니다.

이런 상태가 추가되기 전에는, 사용자에게 “설치 중” 상태만 보여줬기 때문에(화면에 수 시간 동안 유지되기도 하는) 앱 설치가 오래 걸리면 혼란스러웠습니다. 새로운 상태가 추가되었기 때문에, 이제 사용자들은 지원을 요청하는 대신 "장치가 동기화될 때까지 기다리는 중" 링크를 클릭하고 지침에 따라서 동기화 프로세스가 재시작되도록 강제 적용할 수 있습니다.

### 향후 예정 사항

**장치 등록 관리자 계정에 대한 변경.** 성능과 확장성을 개선하기 위해, Intune은 회사 포털 앱의 내 장치 창에 더 이상 모든 장치 등록 관리자(DEM)를 표시하지 않을 예정입니다. 앱을 실행하는 로컬 장치가 회사 포털 앱을 통해 등록된 경우에만 표시합니다. DEM 사용자가 로컬 장치에서 작업을 수행할 수 있지만, 등록된 다른 장치의 원격 관리는 Intune 관리 콘솔에서만 수행될 수 있습니다.  또한, Intune은 Apple 장치 등록 프로그램 또는 Apple 구성기 도구에서 DEM 계정을 사용하지 않을 예정입니다. 이 두 가지 등록 방식은 공유 iOS 장치에 대해 사용자 정보가 없는 등록을 지원합니다.  DEM 계정은 공유 장치에 대해 사용자 정보가 없는 등록을 사용할 수 없는 경우에만 사용합니다.

[클라우드 플랫폼 로드맵](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)에서 Intune에 대해 예정된 개발 정보를 지속적으로 알아볼 수 있습니다..


## 이전 Intune 릴리스
지난 6개월간 Intune에 릴리스된 목록을 보려면 [이전 Intune 릴리스](previous-intune-releases.md) 문서를 참조하세요.



### 참고 항목
* [Microsoft Intune 블로그](http://go.microsoft.com/fwlink/?LinkID=273882)


<!--HONumber=May16_HO1-->


