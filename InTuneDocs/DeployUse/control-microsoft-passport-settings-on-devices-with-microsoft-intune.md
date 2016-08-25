---
title: "장치의 Microsoft Passport 설정 제어 | Microsoft Intune"
description: "Intune이 Active Directory 또는 Azure Active Directory 계정을 사용하여 암호, 스마트 카드 또는 가상 스마트 카드를 대신하는 대체 로그인 방법인 Microsoft Passport for Work와 통합하는 방법을 알아봅니다."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 402bc5a1-ada3-4c4c-a0de-292d026b4444
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 822264b7af87c0241e1d345544b8e9892f9e8c51
ms.openlocfilehash: c05929f3c4032bf8e252f4b2087b23dfdecf846b


---

# Microsoft Intune으로 장치의 Microsoft Passport 설정 제어
Microsoft Intune은 Active Directory 또는 Azure Active Directory 계정을 사용하여 암호, 스마트 카드 또는 가상 스마트 카드를 대신하는 대체 로그인 방법인 Microsoft Passport for Work와 통합합니다.

Passport를 사용하면 암호 대신 *사용자 제스처*를 사용하여 로그인할 수 있습니다. 사용자 제스처는 단순 PIN, 생체 인식 인증(예: Windows Hello) 또는 외부 장치(예: 지문 판독기)일 수 있습니다.

>[!TIP]
>현재 Microsoft Passport for Work는 비즈니스용 Windows Hello라고 합니다. Intune 콘솔에서는 이 변경 내용이 아직 반영되지 않습니다.

Intune는 다음 두 가지 방법으로 Passport for Work에 통합됩니다.

-   Intune 정책을 사용하여 사용자가 로그인하는 데 사용할 수 있는 제스처와 사용할 수 없는 제스처를 제어할 수 있습니다.

-   Passport for Work KSP(키 저장소 공급자)에 인증 인증서를 저장할 수 있습니다. 자세한 정보는 [Microsoft Intune에서 인증서 프로필을 통해 리소스 액세스 보안](secure-resource-access-with-certificate-profiles.md) 항목을 참조하세요.

## Passport for Work 정책 만들기

1.  [Microsoft Intune 관리 콘솔](https://manage.microsoft.com)에서 **관리자** &gt; **모바일 장치 관리** &gt; **Windows** &gt; **Passport for Work**를 선택하여 Passport for Work 페이지를 엽니다.

    ![Passport for Work 페이지](../media/passport.png)

2.  다음 설정 중 하나를 선택합니다.
    - **등록된 장치에서 Passport for Work 사용 안 함**. Windows 10 장치에서 Passport for Work를 사용하지 않으려는 경우에는 이 설정을 선택합니다. 화면의 다른 모든 설정은 사용할 수 없게 됩니다.
    - **등록된 장치에서 Passport for Work 사용**. 모든 Windows 10 장치에서 Passport for Work 설정을 구성하려는 경우 이 설정을 선택합니다.
    - **구성되지 않음**. Passport for Work를 제어하도록 Intune을 사용하지 않으려는 경우에는 이 설정을 선택합니다. Windows 10 장치에서 기존 Passport for Work 설정이 변경되지 않습니다. 화면의 다른 모든 설정은 사용할 수 없게 됩니다.
3.  **등록된 장치에서 Passport for Work 사용**을 선택한 경우에는 등록된 모든 Windows 10 및 Windows 10 모바일 장치에 적용될 필요한 설정을 구성합니다.
4.  작업이 끝나면 **저장**을 선택합니다.

## Passport for Work: PIN 설정


- **최소 PIN 길이 필요**/**최대 PIN 길이 필요**. 로그인을 보호하기 위해 지정한 최소 및 최대 PIN 길이를 사용하도록 장치를 구성합니다. 기본 PIN 길이는 6자이지만 최소 길이인 4자를 적용할 수 있습니다. 최대 PIN 길이는 127자입니다.
- **PIN에 소문자 필요**/**PIN에 대문자 필요**/**PIN에 특수 문자 필요**. PIN에 대문자, 소문자, 특수 문자를 사용하도록 요구하여 강력한 PIN을 적용할 수 있습니다. 다음 중에서 선택합니다.
    - **허용**. 사용자는 해당 PIN에 문자 형식을 사용할 수 있지만 필수는 아닙니다.
    - **필수**. 사용자는 PIN에 하나 이상의 문자 형식을 포함해야 합니다. 예를 들어, 일반적으로 하나 이상의 대문자 및 특수 문자가 필요합니다.
    - **허용되지 않음**(기본값). PIN에서 대문자 형식을 사용하지 않아야 합니다. (설정이 구성되지 않은 경우에도 이 동작 수행)
    > [!TIP]
    > 특수 문자에는 다음이 포함됩니다. **! " # $ % &amp; ' ( ) &#42; + , - . / : ; &lt; = &gt; ? @ [ \ ] ^ _ &#96; { &#124; } ~**
- **PIN 만료(일)**. 사용자가 변경해야 하는 기간 이후에 PIN에 대한 만료 기간을 지정하는 것이 좋습니다. 기본값은 41일입니다.
- **PIN 기록 저장**. 이전에 사용한 PIN의 재사용을 제한합니다. 기본적으로 마지막 5개 PIN을 다시 사용할 수 없습니다.


## Passport for Work: 기타 설정

- **TPM(신뢰할 수 있는 플랫폼 모듈) 사용**. TPM 칩은 추가적인 데이터 보안 계층을 제공합니다.<br>다음 값 중 하나를 선택합니다.
    - **필수**(기본값). 액세스할 수 있는 TPM이 있는 장치만 Passport for Work를 프로비전할 수 있습니다.
    - **기본 설정**. 장치에서 먼저 TPM을 사용하려고 합니다. 사용할 수 없는 경우에는 소프트웨어 암호화를 사용할 수 있습니다.
- **생체 인식 인증 허용**. Passport for Work PIN 대신 안면 인식 또는 지문과 같은 생체 인식 인증을 설정합니다. 사용자는 생체 인식 인증에 실패하는 경우 작업 PIN을 구성해야 합니다. 다음 중에서 선택합니다.
    - **예**. Passport for Work에서 생체 인식 인증이 허용됩니다.
    - **아니요**. Passport for Work에서 모든 계정 유형에 대해 생체 인식 인증을 금지합니다.
- **사용 가능한 경우 향상된 스푸핑 방지 사용**. Windows Hello의 스푸핑 방지 기능을 지원하는 장치에서 사용할지 여부를 구성합니다(예: 실제 얼굴 대신 얼굴 사진 검색).<br>**예**로 설정하면 얼굴 인식 기능이 지원되는 경우 모든 사용자는 얼굴 인식 기능에 대해 스푸핑 방지 기능을 사용해야 합니다.
- **Remote Passport 사용**. 이 옵션이 **예**로 설정되면 원격 Passport를 데스크톱 컴퓨터 인증을 위한 휴대용 포함 장치로 사용할 수 있습니다. 데스크톱 컴퓨터가 Azure Active Directory에 연결되어 있어야 하고 해당 포함 장치는 Passport for Work PIN으로 구성되어야 합니다.

## 추가 정보
Microsoft Passport에 대한 자세한 내용은 Windows 10 설명서의 [가이드](https://technet.microsoft.com/library/mt589441.aspx)를 참조하세요.



<!--HONumber=Aug16_HO1-->


