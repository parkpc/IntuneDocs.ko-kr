---
title: "모바일 응용 프로그램 관리 문제 해결 | Microsoft 문서"
description: "이 항목에서는 조건부 액세스 배포의 몇 가지 문제 해결 팁을 설명합니다."
keywords: 
author: NathBarn
ms.author: oldang
manager: angerobe
ms.date: 09/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd5a0a3b-0013-4be3-a233-ce6e9083149f
translationtype: Human Translation
ms.sourcegitcommit: d50a5751a5afd987196336e9443dc5a429a283fd
ms.openlocfilehash: b333c0f5097fec38bf0dd78726a028fd7aaccd2f


---

# <a name="troubleshoot-mobile-application-management"></a>모바일 응용 프로그램 관리 문제 해결

Intune 모바일 응용 프로그램 관리에 문제가 있으면 이 문서의 내용을 참조하여 문제 해결을 시작할 수 있습니다. 이 항목에서는 관리자에게 발생할 수 있는 몇 가지 일반적인 문제와 질문, 그리고 해결 방법과 대답을 제공합니다.

## <a name="common-it-administrator-issues"></a>IT 관리자에게 일반적으로 발생하는 문제

1. **문제:** Azure Portal에서 만든 장치 등록을 포함하지 않는 앱 보호 정책이 iOS 및 Android 장치의 비즈니스용 Skype 앱에 적용되지 않습니다.

  **해결 방법**: 최신 인증을 사용하도록 비즈니스용 Skype를 설정해야 합니다.  [Enable your tenant for modern authentication](http://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)(최신 인증을 사용하도록 테넌트 설정)의 지침을 따라 Skype에 최신 인증을 설정합니다.

2. **문제:** 모든 사용자에 대해 [지원되는 Office 앱](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners)에 앱 보호 정책이 적용되지 않습니다.

  **해결 방법**: 사용자가 Intune용 라이선스를 취득했으며, Office 앱이 배포된 앱 보호 정책의 대상인지 확인합니다. 새로 배포된 앱 보호 정책이 적용되려면 최대 8시간이 걸릴 수 있습니다.

3. **문제:** IT 관리자가 Azure Portal에서 앱 보호 정책을 구성할 수 없습니다.

  **해결 방법**:

  Azure Portal에 액세스할 수 있는 사용자 역할은 다음과 같습니다.

  - 전역 관리자 - [Office 포털](http://portal.office.com/)에서 설정할 수 있음
  - 소유자 - [Azure Portal](https://portal.azure.com/)에서 설정할 수 있음
  - 참가자 - [Azure Portal](https://portal.azure.com/)에서 설정할 수 있음<br>

  이러한 역할 설정에 대한 도움말은 [Microsoft Intune을 사용하여 모바일 앱 관리 정책 구성 준비](../deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)를 참조하세요.

4. **문제:** 앱 보호 정책을 최근 배포한 사용자 계정이 관리 콘솔 보고서에 표시되지 않습니다.

  **해결 방법**: 사용자가 앱 보호 정책 대상으로 새로 지정된 경우 대상 사용자로 보고서에 표시되는 데 최대 24시간이 걸릴 수 있습니다.

5. **문제:** 정책 변경/업데이트를 적용하는 데 최대 8시간이 걸릴 수 있습니다.  

  **해결 방법**: 서비스와 강제로 동기화하도록 최종 사용자가 앱에서 로그아웃했다가 다시 로그인하면 됩니다.  

6. **문제:** 앱 보호 정책이 Apple DEP 장치에 적용되지 않습니다.

  **해결 방법**: Apple DEP(장치 등록 프로그램)에서 사용자 선호도를 사용 중인지 확인합니다. 사용자 선호도는 DEP에 따라 사용자 인증이 필요한 모든 앱에 필수입니다.
자세한 내용은 [Enroll corporate-owned Device Enrollment Program iOS devices](../deploy-use/ios-device-enrollment-program-in-microsoft-intune.md)(회사 소유의 iOS 장치를 장치 등록 프로그램에 등록)를 참조하세요.

## <a name="common-end-user-issues"></a>최종 사용자에게 일반적으로 발생하는 문제

### <a name="issues-on-ios"></a>iOS에의 문제

대화 상자/오류 메시지 | 원인 | 업데이트 관리 |
-- | --- | --- |
**앱이 설정되지 않음**: 이 앱을 사용자가 사용하도록 설정되지 않았습니다. 도움이 필요하면 IT 관리자에게 문의하세요. | 앱의 필수 앱 보호 정책을 검색하지 못했습니다. |iOS 앱 보호 정책이 사용자의 보안 그룹에 배포되어 있으며 이 앱을 대상으로 하는지 확인합니다.
**Intune Managed Browser에 오신 것을 환영합니다.**: 이 앱은 Microsoft Intune으로 관리할 때 가장 잘 작동합니다. 언제든지 이 앱을 사용하여 웹 검색을 할 수 있으며 Microsoft Intune으로 앱을 관리하는 경우 추가 데이터 보호 기능에 액세스할 수 있습니다. | Intune Managed Browser 앱의 필수 앱 보호 정책을 검색하지 못했습니다. <br><br>사용자는 계속 앱을 사용하여 웹을 검색할 수는 있지만 앱은 Intune을 통해 관리되지 않습니다. | iOS 앱 보호 정책이 사용자의 보안 그룹에 배포되어 있으며 Intune Managed Browser 앱을 대상으로 하는지 확인합니다.
**로그인 실패**: 지금은 로그인할 수 없습니다. 나중에 다시 시도하십시오. | 사용자가 회사 또는 학교 계정으로 로그인을 시도한 후 MAM 서비스에 사용자를 등록하지 못했습니다. | iOS 앱 보호 정책이 사용자의 보안 그룹에 배포되어 있으며 이 앱을 대상으로 하는지 확인합니다.
**계정이 설정되지 않음**: 조직에서 회사 또는 학교 데이터에 액세스하기 위한 계정을 설정하지 않았습니다. 도움이 필요하면 IT 관리자에게 문의하세요. | 사용자 계정에 Intune A 다이렉트 라이선스가 없습니다. | [Office 포털](http://portal.office.com)에서 사용자의 계정에 Intune 라이선스가 할당되어 있는지 확인합니다.
**규정을 준수하지 않는 장치**: 탈옥한 장치를 사용 중이므로 이 앱을 사용할 수 없습니다. 도움이 필요하면 IT 관리자에게 문의하세요. | Intune에서 사용자가 탈옥한 장치를 사용 중임을 검색했습니다. | 장치를 기본 초기 설정으로 다시 설정합니다. Apple 지원 사이트의 [지침](https://support.apple.com/en-us/HT201274)을 따르세요.
**인터넷 연결 필요**: 이 앱을 사용할 수 있는지 확인하려면 인터넷에 연결되어 있어야 합니다. | 장치가 인터넷에 연결되어 있지 않습니다. | Wi-Fi 또는 데이터 네트워크에 장치를 연결합니다.
**알 수 없는 오류**: 앱을 다시 시작해 보세요. 문제가 계속될 경우 IT 관리자에게 문의하세요. | 알 수 없는 오류가 발생했습니다. | 잠시 기다린 후 다시 시도하세요. 오류가 계속되면 [여기](/how-to-get-support-for-microsoft-intune.md)서 Intune 지원 티켓을 작성합니다.
**조직 데이터에 액세스**: 지정한 회사 또는 학교 계정은 이 앱에 액세스할 수 없습니다. 다른 계정으로 로그인해야 할 수 있습니다. 도움이 필요하면 IT 관리자에게 문의하세요. | Intune에서 사용자가 장치용으로 MAM에 등록된 계정이 아닌 두 번째 회사 또는 학교 계정으로 로그인을 시도했음을 발견했습니다. 장치당 한 번에 하나의 회사 또는 학교 계정만 MAM을 통해 관리할 수 있습니다. | 사용자가 로그인 화면에 사용자 이름이 미리 입력되어 있는 계정으로 로그인하도록 합니다. <br> <br> 아니면 새 회사 또는 학교 계정으로 로그인하고 MAM에 등록된 기존 계정은 제거하도록 합니다.
**연결 문제**: 예기치 않 은 연결 문제가 발생했습니다. 연결을 확인하고 다시 시도하세요.  |  예기치 않은 오류가 발생했습니다. | 잠시 기다린 후 다시 시도하세요. 오류가 계속되면 [여기](/how-to-get-support-for-microsoft-intune.md)서 Intune 지원 티켓을 작성합니다.
**경고**: 이 앱은 더 이상 사용할 수 없습니다. 자세한 내용은 IT 관리자에게 문의하십시오. | 앱의 인증서 유효성을 검사하지 못했습니다. | 앱이 최신 버전인지 확인합니다. <br><br> 앱을 다시 설치합니다.
**오류**: 이 앱은 문제가 발생하여 닫아야 합니다. 이 오류가 계속되면 IT 관리자에게 문의하세요. | Apple iOS 키 집합에서 MAM 앱 PIN을 읽지 못했습니다. | 장치를 다시 시작합니다. 앱이 최신 버전인지 확인합니다. <br><br> 앱을 다시 설치합니다.


### <a name="issues-on-android"></a>Android의 문제

대화 상자/오류 메시지 | 원인 | 업데이트 관리 |
-- | --- | --- |
**앱이 설정되지 않음**: 이 앱을 사용자가 사용하도록 설정되지 않았습니다. 도움이 필요하면 IT 관리자에게 문의하세요. | 앱의 필수 앱 보호 정책을 검색하지 못했습니다. |iOS 앱 보호 정책이 사용자의 보안 그룹에 배포되어 있으며 이 앱을 대상으로 하는지 확인합니다.
**앱 시작 실패**: 앱을 시작하는 중 문제가 발생했습니다. 앱 또는 Intune 회사 포털 앱을 업데이트해 보세요. 도움이 필요하면 IT 관리자에게 문의하세요. | Intune에서 앱에 대해 유효한 앱 보호 정책을 검색했는데 MAM 초기화 중에 앱 작동이 중단됩니다. | 앱이 최신 버전인지 확인합니다. <br><br> Intune 회사 포털 앱이 장치에 설치되어 있으며 최신 상태인지 확인합니다. <br><br> 오류가 계속되면 회사 포털 앱을 사용하여 Intune에 로그를 보내거나 [여기](/how-to-get-support-for-microsoft-intune.md)서 지원 티켓을 작성합니다.
**앱을 찾을 수 없음**: 조직에서 이 콘텐츠를 열 수 있도록 허용한 앱이 이 장치에 없습니다. 도움이 필요하면 IT 관리자에게 문의하세요. | 사용자가 다른 앱에서 회사 또는 학교 데이터를 열려고 했는데 Intune이 데이터를 열도록 허용된 다른 관리되는 앱을 찾을 수 없습니다. | Android 앱 보호 정책이 사용자의 보안 그룹에 배포되어 있고, 해당하는 데이터를 열 수 있는 하나 이상의 다른 MAM 지원 앱을 대상으로 하는지 확인합니다.
**로그인 실패**: 다시 로그인해 보세요. 문제가 계속되면 IT 관리자에게 문의하세요. | 사용자가 로그인하는 데 사용한 계정을 인증하지 못했습니다. | 사용자가 Intune MAM 서비스에 이미 등록되어 있는 회사 또는 학교 계정(이 앱에 정상적으로 로그인하는 데 사용했던 첫 번째 회사 또는 학교 계정)을 사용하여 로그인하는지 확인합니다. <br><br> 앱의 데이터를 지웁니다. <br><br> 앱이 최신 버전인지 확인합니다. <br><br> 회사 포털이 최신 버전인지 확인합니다.
**인터넷 연결 필요**: 이 앱을 사용할 수 있는지 확인하려면 인터넷에 연결되어 있어야 합니다. | 장치가 인터넷에 연결되어 있지 않습니다. | Wi-Fi 또는 데이터 네트워크에 장치를 연결합니다.
**규정을 준수하지 않는 장치**: 루팅된 장치를 사용하고 있으므로 이 앱을 사용할 수 없습니다. 도움이 필요하면 IT 관리자에게 문의하세요. | Intune에서 사용자가 루팅된 장치를 사용 중임을 검색했습니다. | 장치를 기본 초기 설정으로 다시 설정합니다.
**계정이 설정되지 않음**: 이 앱은 Microsoft Intune에서 관리해야 하지만 계정이 설정되지 않았습니다. 도움이 필요하면 IT 관리자에게 문의하세요. | 사용자 계정에 Intune A 다이렉트 라이선스가 없습니다. | [Office 포털](http://portal.office.com)에서 사용자의 계정에 Intune 라이선스가 할당되어 있는지 확인합니다.
**앱을 등록할 수 없음**: 이 앱은 Microsoft Intune에서 관리해야 하지만 지금은 이 앱을 등록할 수 없습니다. 도움이 필요하면 IT 관리자에게 문의하세요. | 앱 보호 정책이 필요한데 앱을 MAM 서비스에 자동으로 등록하지 못했습니다. | 앱의 데이터를 지웁니다. <br><br> 회사 포털 앱을 통해 Intune에 로그를 보내거나 [여기](/how-to-get-support-for-microsoft-intune.md)서 지원 티켓을 등록합니다.





### <a name="see-also"></a>참고 항목
- [모바일 응용 프로그램 관리 설정 유효성 검사](../deploy-use/validate-mobile-application-management.md)
- [Microsoft Intune을 사용하여 모바일 앱 관리 정책 구성 준비](../deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


