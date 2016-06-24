---
# required metadata

title: Microsoft Intune에 사용할 Symantec 엔터프라이즈 코드 서명 인증서 갱신 | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: c4813044-a925-4273-b0ec-e992fd55850a

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Windows 장치용 Symantec 엔터프라이즈 코드 서명 인증서 갱신

특정 Windows 및 Windows Phone 모바일 장치를 관리하는 데 사용되는 Symantec 인증서는 주기적으로 갱신해야 합니다. Windows Phone 8.0 장치의 경우, 장치 등록을 위해 서명된 회사 포털 앱 및 코드 서명 인증서가 필요합니다. 8.0 이후 버전의 Windows Phone 장치는 스토어에서 다운로드하는 회사 포털 앱을 사용할 수 있습니다. LOB(기간 업무) 앱을 배포할 때도 코드 서명 인증서가 필요합니다.

## Symantec 엔터프라이즈 코드 서명 인증서를 갱신하는 방법

1.  인증서가 만료되기 약 14일 전에 Symantec에서 보낸 갱신 전자 메일을 찾습니다. 이 전자 메일에 Symantec의 엔터프라이즈 인증서 갱신 관련 지침이 포함되어 있습니다.

    Symantec 인증서에 대한 자세한 내용을 확인하려면 [www.symantec.com](http://www.symantec.com)을 방문하거나 1-877-438-8776 또는 1-650-426-3400로 전화 문의하세요.

2.  웹 사이트(예: [https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do](https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do))로 이동한 다음 인증서에 연결된 Symantec 게시자 ID 및 전자 메일 주소를 사용하여 로그인합니다. 이때 인증서를 다운로드하는 데 사용하려는 것과 같은 컴퓨터를 사용하여 갱신을 시작해야 합니다.

3.  갱신이 승인 및 결제되면 인증서를 다운로드합니다.

## Windows Phone 8.0에 업데이트된 인증서를 설치하는 방법

1.  다음 웹 사이트에 있는 최신 Windows Phone 회사 포털을 다운로드하고 서명합니다. [http://www.microsoft.com/en-us/download/details.aspx?id=36060](http://www.microsoft.com/en-us/download/details.aspx?id=36060)..

2.  Intune 관리 콘솔([https://admin.manage.microsoft.com](https://admin.manage.microsoft.com))을 열고 **관리**, **모바일 장치 관리** &gt; **Windows Phone**으로 이동한 후에 **서명된 앱 업로드**를 클릭합니다..

3.  새로 서명된 회사 포털을 업로드합니다. 새로 서명된 SSP.xap와 Symantec에서 받은 새로운 .PFX 파일 또는 이러한 새 .PFX 파일로 생성한 응용 프로그램 등록 토큰이 필요합니다.

4.  업로드가 완료되면 Intune 관리 콘솔의 **소프트웨어** 작업 영역에서 이전 회사 포털 버전을 제거합니다.

5.  같은 인증서를 사용하여 모든 엔터프라이즈 LOB(기간 업무) 앱에 다시 서명을 한 다음 기존 응용 프로그램을 업로드 및 교체합니다.

현재 서명된 SSP.xap 파일을 제공하는 것이 업데이트된 코드 서명 인증서를 제공하는 유일한 방법입니다. 서명된 LOB(기간 업무) 앱을 지원하려면 사용자가 스토어에서 회사 포털 앱을 설치하더라도 회사 포털 앱에 서명하고 업로드해야 합니다.

## Windows Phone 8.1 이상 장치에 업데이트된 인증서를 설치하는 방법

1.  다음 웹 사이트에 있는 다운로드 센터에서 최신 Windows Phone 회사 포털을 다운로드하고 서명합니다. [http://www.microsoft.com/en-us/download/details.aspx?id=36060](http://www.microsoft.com/en-us/download/details.aspx?id=36060).

2.  [Intune 관리 콘솔](https://admin.manage.microsoft.com)(https://admin.manage.microsoft.com)을 열고 **관리** &gt; **모바일 장치 관리** &gt; **Windows Phone**으로 이동한 후에 **서명된 앱 업로드**를 클릭합니다..

3.  새로 서명된 회사 포털을 업로드합니다. You’ll need the newly signed SSP.xap and the new .PFX file you received from Symantec or the Application enrollment token that was created with this new .PFX file.

4.  업로드가 완료되면 **소프트웨어**  작업 영역에서 이전 회사 포털 버전을 제거합니다.

5.  새 인증서를 사용하여 모든 신규 및 업데이트된 엔터프라이즈 기간 업무 앱에 서명합니다. 기존 응용 프로그램에 다시 서명하고 다시 배포할 필요가 없습니다.


### 참고 항목
[Windows Phone 8.0 관리 설정](set-up-windows-phone-8.0-management-with-microsoft-intune.md)
[Windows Phone 관리 설정](set-up-windows-phone-management-with-microsoft-intune.md)


<!--HONumber=May16_HO1-->


