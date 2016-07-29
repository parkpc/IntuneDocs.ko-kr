---
title: "Intune에서 Windows 장치 등록을 취소하면 어떻게 되나요? | Microsoft Intune"
description: 
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47e03edb-0c57-4e25-8e89-4a1069267b8c
ROBOTS: noindex,nofollow
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 618e2abda642c3b9b2e813824dfd4235c9309faa
ms.openlocfilehash: 33bc0e494d1297421d253a9246175a18924c1c52


---


# Intune에서 Windows 장치 등록을 취소하면 어떻게 되나요?

발생하는 상황에 대한 추가적인 정보를 보려면 위의 "이 문서의 내용" 섹션에 표시된 링크 중 사용하고 있는 장치 유형에 해당하는 링크를 사용하세요.

- [Windows 10 mobile, 8.1, Windows 8, Windows 7, Vista](#windows-10-mobile--8-1,-windows-8,-windows-7,-vista)
- [Windows 10, Windows 8.1 또는 Windows Phone 8](#windows-10--windows-8-1-or-windows-phone-8)
- [Windows 8.1을 실행하는 Windows RT 또는 Windows RT](#windows-rt-running-windows-8-1-or-windows-rt)


## Windows 10, Windows 8.1, Windows 8, Windows 7, Vista

-   장치가 더 이상 회사 포털에 나타나지 않으며 회사 포털에서 앱을 설치할 수 없습니다.

-   Intune 클라이언트 소프트웨어를 설치한 경우 컴퓨터에서 제거됩니다.

-   Intune Endpoint Protection 소프트웨어가 컴퓨터에서 제거됩니다. 컴퓨터에 다른 바이러스 방지 소프트웨어가 설치되어 있지만 사용되지 않도록 설정된 경우, Intune Endpoint Protection을 제거하면 이 응용 프로그램이 다시 사용되도록 설정될 수 있습니다. 회사 포털에서 컴퓨터를 제거한 후 해당 컴퓨터를 확인해야 합니다.

    > [!IMPORTANT]
    > ´Ù¸¥ ¹ÙÀÌ·¯½º ¹æÁö ¼ÒÇÁÆ®¿þ¾î°¡ ´Ù½Ã »ç¿ëµÇµµ·Ï ¼³Á¤µÇÁö ¾Ê°Å³ª ´Ù¸¥ ¹ÙÀÌ·¯½º ¹æÁö ¼ÒÇÁÆ®¿þ¾î°¡ ¼³Ä¡µÇ¾î ÀÖÁö ¾ÊÀº °æ¿ì ÄÄÇ»ÅÍ´Â ¹ÙÀÌ·¯½º ¹× ¸È¿þ¾î °ø°Ý¿¡ Ãë¾àÇØÁú ¼ö ÀÖ½À´Ï´Ù.

-   장치를 추가할 때 장치에서 변경된 모든 설정(예: 카메라 사용 안 함)이 더 이상 적용되지 않습니다.

-   컴퓨터가 Intune 서비스로부터 더 이상 자동 소프트웨어 업데이트 또는 바이러스 백신 소프트웨어 업데이트를 받지 못합니다. ±×·¯³ª ÄÄÇ»ÅÍ°¡ ±¸¼ºµÈ ¹æ½Ä¿¡ µû¶ó Windows Server Update Services, Windows ¾÷µ¥ÀÌÆ® ¶Ç´Â Microsoft ¾÷µ¥ÀÌÆ®¸¦ »ç¿ëÇÏ¿© ¾÷µ¥ÀÌÆ®¸¦ °è¼Ó ¹ÞÀ» ¼ö ÀÖ½À´Ï´Ù.

또한 Windows 8.1의 경우

-   장치에서 더 이상 회사 앱 및 회사 데이터를 사용할 수 없습니다.

-   Windows ¸ÞÀÏ°ú °°Àº ÀÏºÎ ¸ÞÀÏ ¾Û¿¡¼­ ÀåÄ¡¿¡ ÀúÀåµÈ È¸»ç ÀÌ¸ÞÀÏ¿¡ ´õ ÀÌ»ó ¾×¼¼½ºÇÒ ¼ö ¾ø½À´Ï´Ù.

-   Wi-Fi ¶Ç´Â VPN(°¡»ó »ç¼³¸Á)À» »ç¿ëÇÏ¿© È¸»ç ³×Æ®¿öÅ©¿¡ ¿¬°áÇÒ ¼ö ¾ø½À´Ï´Ù.

-   장치에서 더 이상 일부 회사 리소스(예: 파일 공유 또는 내부 웹 사이트)에 액세스하지 못할 수 있습니다.

## Windows 10 mobile, Windows Phone 8.1 또는 Windows Phone 8

-   장치에서 회사 포털 앱이 제거되어 장치가 더 이상 회사 포털에 나타나지 않으며, 회사 포털 앱 또는 회사 포털 웹 사이트에서 앱을 설치할 수 없습니다.

-   장치에서 더 이상 회사 앱 및 회사 데이터를 사용할 수 없습니다.

-   장치를 추가할 때 장치에서 변경된 모든 설정(예: 카메라 사용 안 함 또는 특정 암호 길이 요구)이 더 이상 적용되지 않습니다.

    > [!IMPORTANT]
    > À¯ÀÏÇÑ ¿¹¿Ü´Â ¾ÏÈ£È­ Á¤Ã¥ÀÌ¸ç, ÀÌ Á¤Ã¥Àº ¿©ÀüÈ÷ Àû¿ëµË´Ï´Ù. 회사 정책에서 Windows Phone의 암호화를 요구하는 경우 휴대폰을 암호 해제하는 유일한 방법은 Windows Phone의 **설정** 메뉴를 사용하여 휴대폰을 초기화하는 것입니다.

## Windows 8.1을 실행하는 Windows RT 또는 Windows RT

-   장치에서 회사 포털 앱이 제거되어 장치가 더 이상 회사 포털에 나타나지 않으며, 회사 포털에서 앱을 설치할 수 없습니다.

-   장치에서 더 이상 회사 앱 및 회사 데이터를 사용할 수 없습니다.

-   장치를 추가할 때 장치에서 변경된 모든 설정(예: 카메라 사용 안 함 또는 특정 암호 길이 요구)이 더 이상 적용되지 않습니다.

-   ´õ ÀÌ»ó Wi-Fi ¶Ç´Â VPN(°¡»ó »ç¼³¸Á)À» »ç¿ëÇÏ¿© È¸»ç ³×Æ®¿öÅ©¿¡ ¿¬°áÇÒ ¼ö ¾ø½À´Ï´Ù.

-   장치에서 더 이상 일부 회사 리소스(예: 파일 공유 또는 내부 웹 사이트)에 액세스하지 못할 수 있습니다.

-   Windows ¸ÞÀÏ°ú °°Àº ÀÏºÎ ¸ÞÀÏ ¾Û¿¡¼­ ÀåÄ¡¿¡ ÀúÀåµÈ È¸»ç ÀÌ¸ÞÀÏ¿¡ ´õ ÀÌ»ó ¾×¼¼½ºÇÒ ¼ö ¾ø½À´Ï´Ù.

Windows RT ÀåÄ¡¸¦ Á¦°ÅÇÏ¸é ´ÙÀ½°ú °°Àº »óÈ²ÀÌ ¹ß»ýÇÕ´Ï´Ù.

-   장치에서 회사 포털 앱이 제거되어 장치가 더 이상 회사 포털에 나타나지 않으며, 회사 포털에서 앱을 설치할 수 없습니다.

-   장치에서 더 이상 회사 앱 및 회사 데이터를 사용할 수 없습니다.

-   장치를 추가할 때 장치에서 변경된 모든 설정(예: 카메라 사용 안 함 또는 특정 암호 길이 요구)이 더 이상 적용되지 않습니다.

의문 사항이 있으면 IT 관리자에게 문의하세요. IT 관리자의 연락처 정보는 [회사 포털 웹 사이트](http://portal.manage.microsoft.com)를 참조하세요.

### 참고 항목
[Intune에서 Windows 장치 사용](using-your-windows-device-with-intune.md)



<!--HONumber=Jul16_HO4-->


