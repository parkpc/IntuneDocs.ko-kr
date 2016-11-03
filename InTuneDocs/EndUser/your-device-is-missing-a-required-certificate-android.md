---
title: "장치에 필요한 인증서가 없습니다. | Microsoft Intune"
description: 
keywords: 
author: staciebarker
manager: angrobe
ms.date: 09/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9081b1d8-50e8-4bc2-ba37-766421364213
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: arnab
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: bff97f79c6e88bbf55c2c3a259891bb6206b690b
ms.openlocfilehash: 9a763e13818ec5c1708d121125cadd37e25e3193


---


# 장치에 필요한 인증서가 없습니다.


## 장치에 일반적으로 휴대폰에 설치되는 인증서가 없습니다.
Android 장치가 Intune에 등록되어 있지 않고 휴대폰에 보통 설치되어 나오는 인증서가 없는 경우 Android 회사 포털 앱에 로그인할 수 없습니다. 로그인하려고 시도하면 다음과 같은 메시지가 표시됩니다.

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

이 문제를 해결하고 필요한 인증서를 얻으려면

1.  브라우저에서 이 [Digicert 인증서 페이지](https://www.digicert.com/digicert-root-certificates.htm)로 이동합니다.

2.  Baltimore CyberTrust 루트 인증서(https://www.digicert.com/CACerts/BaltimoreCyberTrustRoot.crt)를 찾아 다운로드합니다.

3.  맨 위에서 아래로 끌어 알림을 연 후 알림 목록에서 **BaltimoreCyberTrustRoot.crt**를 탭합니다.

4.  **인증서 이름 지정** 대화 상자에서 기본 인증서 이름을 그대로 적용합니다.

5. **자격 증명 용도**가 **VPN 및 앱용**으로 설정되어 있는지 확인한 후 **확인**을 탭합니다.

    ![screenshot-certificate-name-dialog-showing-baltimore-certificate-name](./media/andr-cert_install-2-add_cert_name.png)

6. 회사 포털 앱 및 웹 브라우저를 닫습니다.

7. 회사 포털 앱을 다시 엽니다. 이제 회사 포털 앱에 로그인할 수 있습니다. 도움이 필요하면 IT 관리자에게 문의하세요.

## 장치에 IT 관리자에게 필요한 인증서가 없습니다.
Android 장치가 Intune에 등록되어 있지 않고 IT 관리자에게 필요한 특정 인증서가 없는 경우 Android 회사 포털 앱에 로그인할 수 없습니다. 로그인하려고 시도하면 다음과 같은 메시지가 표시됩니다.

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

>[!NOTE]
> "인증서 없음" 메시지가 표시되는 경우 [장치에 일반적으로 휴대폰에 설치되는 인증서가 없습니다.](#your-device-is-missing-a-certificate-that-usually-comes-installed-on-your-phone)의 단계를 따릅니다. 이와는 다른 메시지 및 인증서이므로 이 섹션의 단계에 따라 누락된 인증서를 가져옵니다.

이 문제를 해결하고 필요한 인증서를 가져오려는 경우 다음 두 가지 주요 단계를 수행해야 합니다.

- 회사 또는 학교 PC를 확인하여 누락된 인증서를 식별합니다.
- 장치를 사용하여 인터넷에서 누락된 인증서를 다운로드합니다.

### 회사 또는 학교 PC를 확인하여 누락된 인증서를 식별합니다.

1. PC에서 Internet Explorer를 엽니다. 이 용도로 사용할 PC가 없으면 IT 관리자에게 문의합니다. IT 관리자의 연락처 정보는 [회사 포털 웹 사이트](http://portal.manage.microsoft.com)를 참조하세요.

2. [회사 포털 웹 사이트](http://portal.manage.microsoft.com)로 이동한 후 회사 또는 학교 자격 증명으로 로그인합니다.

3. 브라우저의 주소 표시줄의 맨 오른쪽에서 아래와 같이 자물쇠 모양의 기호를 클릭합니다. 자물쇠 기호가 보이지 않으면 중지한 후 IT 관리자에게 문의하세요. 잠금은 안전하게 로그인되어 있음을 의미하므로 해당 기호가 표시되지 않으면 계속 진행하지 않아야 합니다.

    ![screenshot-internet-explorer-address-bar-padlock-symbol](./media/andr-missing-cert-ie-padlock-symbol.png)

4. **인증서 보기**를 클릭합니다.

    ![screenshot-internet-explorer-view-certificates-button-on-website-identification-dialog](./media/andr-missg-cert-ie-view-cert-button.png)

5. **인증서** 대화 상자에서 **인증 경로** 탭을 클릭한 다음 인터넷에서 가져와야 하는 인증서를 식별합니다. 필요한 인증서의 이름은 위 스크린샷에 강조 표시된 것과 같은 위치에 있습니다.

### Android 모바일 장치에서 누락된 인증서를 다운로드한 후 설치합니다.

1. Bing이나 Google 같은 검색 엔진을 사용하여 이전 섹션에서 식별한 누락된 인증서의 이름을 검색합니다. 인증서는 ".crt" 또는 ".pem" 등의 다른 "확장명"으로 끝날 수 있습니다.

2. 웹 사이트에서 루트 인증서를 다운로드합니다.

3. 인증서 다운로드 후 장치 맨 위에서 아래로 끌어 알림을 열고, 알림 목록에서 인증서 이름을 누릅니다.

4. 아래 표시된 **인증서 이름 지정** 대화 상자에서 기본 인증서 이름을 그대로 적용합니다.

5. **자격 증명 용도**가 **VPN 및 앱용**으로 설정되어 있는지 확인한 후 **확인**을 탭합니다.

    ![screenshot-certificate-name-dialog-showing-certificate-name](./media/andr-missing-cert-cert-name.png)

6. 회사 포털 앱을 닫습니다.

7. 회사 포털 앱을 다시 엽니다. 이제 회사 포털 앱에 로그인할 수 있습니다. 도움이 필요하면 IT 관리자에게 문의하세요.

위에 표시된 것과 동일한 "인증서 없음" 메시지가 표시되고 위에 단계를 이미 진행했으면 IT 관리자가 설치에 도움을 주어야 하는 다른 인증서가 아직 있는 것일 수 있습니다. IT 관리자에게 문의하고 문제 해결 단계가 포함된 이 [링크](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#android-certificate-issues)를 제공합니다.





<!--HONumber=Sep16_HO3-->


