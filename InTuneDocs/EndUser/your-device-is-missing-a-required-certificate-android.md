---
# required metadata

title: 장치에 필요한 인증서가 없습니다. | Microsoft Intune
description:
keywords:
author: staciebarker
manager: jeffgilb
ms.date: 05/31/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 9081b1d8-50e8-4bc2-ba37-766421364213

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: arnab
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# 장치에 필요한 인증서가 없습니다.
Android 장치가 Intune에 등록되어 있지 않고 휴대폰에 보통 설치되어 나오는 인증서가 없는 경우 Android 회사 포털 앱에 로그인할 수 없습니다. 로그인하려고 시도하면 다음과 같은 메시지가 표시됩니다.

![andr-cert-install-cert-missing](./media/andr-cert_install-1-cert_missing.png)

이 문제를 해결하고 필요한 인증서를 얻으려면

1.  브라우저에서 이 [Digicert 인증서 페이지](https://www.digicert.com/digicert-root-certificates.htm)로 이동합니다.

2.  Baltimore CyberTrust 루트 인증서(https://www.digicert.com/CACerts/BaltimoreCyberTrustRoot.crt)를 찾아 다운로드합니다.

3.  맨 위에서 아래로 끌어 알림을 연 후 알림 목록에서 **BaltimoreCyberTrustRoot.crt**를 탭합니다.

4.  **인증서 이름 지정** 대화 상자에서 기본 인증서 이름을 그대로 적용합니다.

5. **자격 증명 용도**가 **VPN 및 앱용**으로 설정되어 있는지 확인한 후 **확인**을 탭합니다.

    ![andr-cert-install-add-cert-name](./media/andr-cert_install-2-add_cert_name.png)

6. 회사 포털 앱 및 웹 브라우저를 닫습니다.

7. 회사 포털 앱을 다시 엽니다. 이제 회사 포털 앱에 로그인할 수 있습니다. 도움이 필요하면 IT 관리자에게 문의하세요.

여전히 도움이 필요하세요? IT 관리자에게 문의하세요. IT 관리자의 연락처 정보는 [회사 포털 웹 사이트](http://portal.manage.microsoft.com)를 참조하세요.

<!--HONumber=Jun16_HO2-->


