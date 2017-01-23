---
title: "원격 잠금 및 암호 재설정 | Microsoft 문서"
description: "Intune은 원격 잠금 및 암호 재설정 기능을 제공합니다."
keywords: 
author: staciebarker
ms.author: staciebarker
manager: angrobe
ms.date: 01/06/17
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 970f8c81-7c7f-4789-9ed4-2133d50b9db6
ms.reviewer: chrisgre
translationtype: Human Translation
ms.sourcegitcommit: d05c9d7a78474c19e142bca94e232289fbfba1d9
ms.openlocfilehash: b3504cc1aab8bbe553581d822af63363668a8ef7

---
# <a name="help-protect-your-devices-with-remote-lock-and-passcode-reset"></a>원격 잠금 또는 암호 재설정으로 장치 보호 지원

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune은 원격 잠금 및 암호 재설정 기능을 제공합니다.

## <a name="lock-a-device-remotely"></a>장치 원격 잠금
사용자가 장치를 잃어버린 경우 장치를 원격으로 잠글 수 있습니다. 원격 잠금을 사용하려면 먼저 장치에 PIN 또는 암호가 설정되어 있어야 합니다. 

아래 표에는 여러 모바일 플랫폼에서 원격 잠금이 작동하는 방법이 정리되어 있습니다.

|플랫폼|원격 잠금|
|------------|---------------|
|macOS|지원되지 않음|
|iOS|지원됨|
|Android|지원됨|
|Windows 10 및 Windows 10 Mobile|지원됨|
|Windows Phone 8 및 Windows Phone 8.1|지원됨|
|Windows RT 8.1 및 Windows RT|장치의 현재 사용자가 장치를 등록한 사용자인 경우 지원됨|
|Windows 8.1|장치의 현재 사용자가 장치를 등록한 사용자인 경우 지원됨|

Intune 소프트웨어 클라이언트에 등록된 Windows PC에서는 원격 잠금이 지원되지 않습니다.

### <a name="lock-a-mobile-device-remotely-through-the-intune-console"></a>Intune 콘솔을 통해 원격으로 모바일 장치 잠그기

1.  [Intune 관리자 콘솔](https://manage.microsoft.com/)에서 **그룹** &gt; **모든 장치** &gt; **모든 모바일 장치**를 선택합니다.

2.  Intune에 등록된 장치에 대해 **모든 직접 관리 장치**를 선택하거나 **모든 Exchange ActiveSync 관리 장치**를 선택합니다.

    > [!TIP]
    > 또한 사용자별 장치로 이동할 수 있습니다. **모든 사용자**를 선택합니다. 사용자의 속성 페이지에서 **장치**를 선택한 다음 잠그려는 모바일 장치의 이름을 선택합니다.

3.  목록에서 잠그려는 장치를 선택합니다. 작업 표시줄에서 **원격 작업**을 선택하고 **원격 잠금**을 선택합니다.

## <a name="reset-the-passcode-on-a-device"></a>장치에서 암호를 다시 설정
사용자가 암호를 잊은 경우 장치에서 암호를 제거하거나 장치에서 새로운 임시 암호를 적용하여 도움을 줄 수 있습니다. 다음 표에는 여러 모바일 플랫폼에서 암호 재설정이 작동하는 방법이 정리되어 있습니다.

|플랫폼|암호 재설정|
|------------|------------------|
|macOS|지원되지 않음|
|iOS|장치에서 암호를 제거하도록 지원됩니다. 새로운 임시 암호를 만들지 않습니다.|
|Android|Android 7.0 이전 버전에서 지원됩니다. 임시 암호를 만듭니다.|
|Windows 10 Mobile|지원됨|
|Windows Phone 8 및 Windows Phone 8.1|지원됨|
|Windows RT 8.1|지원 안 됨|
|Windows 8.1|지원 안 됨|
|Windows 10 Desktop|지원 안 됨|

Intune 소프트웨어 클라이언트에 등록된 Windows PC에서는 암호 재설정이 지원되지 않습니다.

### <a name="reset-a-passcode"></a>암호 재설정

1.  [Intune 관리자 콘솔](https://manage.microsoft.com/)에서 **그룹** &gt; **모든 장치** &gt; **모든 모바일 장치**를 선택합니다.

2.  Intune에 등록된 장치에 대해 **모든 직접 관리 장치**를 선택하거나 **모든 Exchange ActiveSync 관리 장치**를 선택합니다.

    > [!TIP]
    > 또한 사용자별 장치로 이동할 수 있습니다. **모든 사용자**를 클릭합니다. 사용자의 속성 페이지에서 **장치**를 클릭한 다음 초기화하려는 모바일 장치의 이름을 클릭합니다.

3.  목록에서 잠그려는 장치를 선택합니다. 작업 표시줄에서 **원격 작업**을 선택하고 **암호 재설정**을 선택합니다.


### <a name="see-also"></a>참고 항목
[장치 사용 중지](retire-devices-from-microsoft-intune-management.md) 및 [장치 데이터 관리를 위한 Windows 선택적 초기화](http://technet.microsoft.com/library/dn486874.aspx)



<!--HONumber=Jan17_HO2-->


