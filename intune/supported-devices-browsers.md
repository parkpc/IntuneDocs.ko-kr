---
title: "지원되는 장치 - Microsoft Intune"
description: "Intune 장치 관리용으로 지원되는 장치 플랫폼 및 브라우저를 나열합니다."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/06/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d1ac59c-a885-4276-8576-f3cf81c2d268
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b168cbf5282b4e016133d071c56c8abd54c2e23b
ms.sourcegitcommit: dc2595bec05206a826cd10cb834bf6043145c917
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/14/2017
---
# <a name="supported-devices-and-browsers"></a>지원되는 장치 및 브라우저

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

이 문서는 기업에서 장치 관리를 담당하는 시스템 관리자용으로 작성되었습니다. 휴대폰에서 Intune을 설치하는 방법에 대한 도움말은 [관리되는 장치를 사용하여 작업 완료](/intune-user-help/company-portal-frequently-asked-questions)를 참조하세요.

Microsoft Intune의 설정을 시작하기 전에 다음 요구 사항을 검토합니다.

- [지원되는 장치 및 컴퓨터](#intune-supported-devices)
- [Intune을 사용하도록 지원되는 웹 브라우저 목록](#intune-supported-web-browsers)

또한 [Intune 네트워크 대역폭 사용량](network-bandwidth-use.md)([클래식 포털](/intune-classic/get-started/network-bandwidth-use))을 잘 이해해야 합니다.

## <a name="intune-supported-devices"></a>Intune 지원 장치

Intune 모바일 장치 관리 기능을 사용하면 다음과 같은 장치를 관리할 수 있습니다.

[!INCLUDE[mdm-supported-devices](./includes/mdm-supported-devices.md)]

### <a name="supported-samsung-knox-standard-devices"></a>지원되는 Samsung KNOX Standard 장치

회사 포털 앱이 장치가 [지원 KNOX 장치의 목록](https://www.samsungknox.com/knox-supported-devices/knox-workspace)에 표시되는 경우에만 MDM 등록 중에 삼성 KNOX 정품 인증을 시도합니다. 그러면 KNOX 정품 인증 오류로 인해 MDM 등록을 방해하지 않도록 방지할 수 있습니다. Samsung KNOX 정품 인증을 지원하지 않는 장치는 표준 Android 장치로 등록합니다. Samsung 장치 중 일부에만 KNOX를 지원하는 모델 번호가 있을 수 있습니다. Samsung 장치를 구매하고 배포하기 전에 장치 재판매인과 함께 KNOX 호환성을 검사합니다.

다음과 같은 목록의 Samsung 장치 모델은 KNOX를 지원하지 않으며 Android용 회사 포털 앱에서 네이티브 Android 장치로 등록됩니다.

| **장치 이름** | **장치 모델 번호** |
| --- | --- |
| Galaxy Avant | SM-G386T |
| Galaxy Core 2/Core 2 Duos | SM-G355H<br>SM-G355M |
| Galaxy Core Lite | SM-G3588V |
| Galaxy Core Prime | SM-G360H |
| Galaxy Core LTE | SM-G386F<br>SM-G386W |
| Galaxy Grand | GT-I9082L<br>GT-I9082<br>GT-I9080L |
| Galaxy Grand 3 | SM-G7200 |
| Galaxy Grand Neo | GT-I9060I |
| Galaxy Grand Prime Value Edition | SM-G531H |
| Galaxy J Max | SM-T285YD |
| Galaxy J1 | SM-J100H<br>SM-J100M<br>SM-J100ML |
| Galaxy J1 Ace | SM-J110F<br>SM-J110H |
| Galaxy J1 Mini | SM-J105M |
| Galaxy J2/J2 Pro | SM-J200H<br>SM-J210F |
| Galaxy J3 | SM-J320F<br>SM-J320FN<br>SM-J320H<br>SM-J320M |
| Galaxy K Zoom | SM-C115 |
| Galaxy Light | SGH-T399N |
| Galaxy Note 3 | SM-N9002<br>SM-N9009 |
| Galaxy Note 7/Note 7 Duos | SM-N930S<br>SM-N9300<br>SM-N930F<br>SM-N930T<br>SM-N9300<br>SM-N930F<br>SM-N930S<br>SM-N930T |
| Galaxy Note 10.1 3G | SM-P602 |
| Galaxy S2 Plus | GT-I9105P |
| Galaxy S3 Mini | SM-G730A<br>SM-G730V |
| Galaxy S3 Neo | GT-I9300<br>GT-I9300I |
| Galaxy S4 | SM-S975L |
| Galaxy S4 Neo | SM-G318ML |
| Galaxy S5 | SM-G9006W |
| Galaxy S6 Edge | 404SC |
| Galaxy Tab A 7.0&quot; | SM-T280<br>SM-T285 |
| Galaxy Tab 3 7&quot;/Tab 3 Lite 7&quot; | SM-T116<br>SM-T210<br>SM-T211 |
| Galaxy Tab 3 8.0&quot; | SM-T311 |
| Galaxy Tab 3 10.1&quot; | GT-P5200<br>GT-P5210<br>GT-P5220 |
| Galaxy Trend 2 Lite | SM-G318H |
| Galaxy V Plus | SM-G318HZ |
| Galaxy Young 2 Duos | SM-G130BU |

Intune을 사용하여 Windows Server 운영 체제를 관리할 수는 없습니다.

### <a name="windows-pc-software-client"></a>Windows PC 소프트웨어 클라이언트

Windows PC에서는 대체 등록 방법으로 [Intune 소프트웨어 클라이언트](/intune-classic/deploy-use/manage-windows-pcs-with-microsoft-intune)를 배포하고 설치할 수 있습니다. 이 기능은 Intune 클래식 포털을 통해서만 사용할 수 있습니다. Intune 소프트웨어 클라이언트를 사용하면 Windows 7 이상 버전(Windows 10 Home Edition은 제외)을 실행하는 PC를 관리할 수 있습니다.

<!--  ### Exchange ActiveSync management

You can manage [Exchange ActiveSync devices](/intune-classic/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune) from the Intune console. This option provides a limited set of management capabilities when compared to the other methods. See [Capabilities of built-in Mobile Device Management in Office 365](https://support.office.com/article/Capabilities-of-built-in-Mobile-Device-Management-for-Office-365-a1da44e5-7475-4992-be91-9ccec25905b0) for a list of supported devices.  -->

## <a name="intune-supported-web-browsers"></a>Intune 지원 웹 브라우저

여러 관리 태스크를 수행하려면 다음과 같은 관리 웹 사이트 중 하나를 사용해야 합니다.

- [Office 365 포털](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Azure Portal](https://portal.azure.com/)

이러한 포털에 대해 지원되는 브라우저는 다음과 같습니다.
- Microsoft Edge(최신 버전)
- Microsoft Internet Explorer 11
- Safari(최신 버전, Mac만)
- Chrome(최신 버전)
- Firefox(최신 버전)

### <a name="intune-classic-portal"></a>Intune 클래식 포털

Intune PC 소프트웨어 클라이언트 및 Mobile Threat Defense 파트너와의 통합과 같은 Intune 클래식 전용 기능은 Intune 클래식 포털(https://manage.microsoft.com)에서만 사용 가능합니다. Intune 클래식 포털에는 Silverlight 브라우저 지원이 필요합니다.

Intune 콘솔을 지원하는 Silverlight 브라우저는 다음과 같습니다.
- Internet Explorer 10 이상
- Google Chrome(버전 42 이전 버전)
- Silverlight가 지원되는 Mozilla Firefox [자세히 알아보기](https://go.microsoft.com/fwlink/?linkid=836872)

> [!Note]
> Microsoft Edge 및 모바일 브라우저는 [Microsoft Silverlight](https://msdn.microsoft.com/library/cc838158(v=vs.95).aspx)를 지원하지 않기 때문에 Intune 클래식 포털용으로 지원되지 않습니다.

서비스 관리자 권한이 있는 사용자이거나 전역 관리자 역할이 있는 테넌트 관리자만이 이 포털에 로그인할 수 있습니다. 관리 콘솔에 액세스하려면 계정에 Intune을 사용할 수 있는 라이선스가 있어야 하며 계정의 로그인 상태가 **허용**이어야 합니다.
