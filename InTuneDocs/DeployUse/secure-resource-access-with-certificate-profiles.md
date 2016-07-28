---
title: "리소스 액세스에 대한 인증서 프로필 | Microsoft Intune"
description: "각 사용자 장치에 설치된 인증서를 사용하여 VPN, Wi-Fi 및 전자 메일 액세스를 보호합니다."
keywords: 
author: Nbigman
manager: Arob98
ms.date: 07/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8cbb8499-611d-4217-a7b4-e9b864785dd0
ms.reviewer: kmyrup
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 72288296d966b9b9fae4fd721b4460528213f626
ms.openlocfilehash: c8158b6a54347f6bec1008142eed44daca8946d0


---

# Microsoft Intune에서 인증서 프로필을 통해 리소스 액세스 보안
VPN, Wi-Fi 또는 메일 프로필을 통해 회사 리소스에 액세스할 수 있도록 설정하는 경우 각 사용자 장치에 설치된 인증서로 해당 액세스를 보호할 수 있습니다. 이 서비스의 작동 방식은 다음과 같습니다.

1. [SCEP에 대한 인증서 인프라 구성](configure-certificate-infrastructure-for-scep.md) 또는 [PFX 인증서 인프라 구성](configure-certificate-infrastructure-for-pfx.md)에 설명된 대로 올바른 인증서 인프라가 마련되어 있는지 확인합니다.

2. 장치가 인증 기관의 적법성을 인식할 수 있도록 각 장치에 루트 인증서(또는 중간 CA 인증서)를 설치합니다. **신뢰할 수 있는 인증서 프로필**을 만들어 배포하면 됩니다. 이 프로필을 배포하면 Intune으로 관리하는 장치가 루트 인증서를 요청하고 받습니다. 각 플랫폼에 대해 별도 프로필을 만들어야 합니다. **신뢰할 수 있는 인증서 프로필**을 이러한 플랫폼에 사용할 수 있습니다.
 -  iOS 7.1 이상
 -  Mac OS X 10.9 이상
 -  Android 4.0 이상
 -  Windows 8.1 이상
 -  Windows Phone 8.1 이상

3. [Intune 인증서 프로필 구성](configure-intune-certificate-profiles.md)에 설명된 대로 각 장치에서 메일, VPN 및 Wi-Fi 액세스 인증에 사용할 인증서를 요청하도록 합니다. 이러한 플랫폼에서 장치에 대해 **PKCS #12(.PFX) 인증서 프로필** 또는 **SCEP 인증서 프로필**을 만들고 배포할 수 있습니다.

-  Android 4.0 이상
-  iOS 7.1 이상
-  Windows 10(데스크톱 및 모바일) 이상

다음에 대해 **SCEP 인증서 프로필**을 사용합니다.
-   Mac OS X 10.9 이상
-   Windows Phone 8.1 이상

각 플랫폼에 대해 별도 프로필을 만들어야 합니다. 프로필을 만들 때 이미 만들어 놓은 **신뢰할 수 있는 루트 인증서 프로필**과 연결합니다.

> [!NOTE]           
> -    엔터프라이즈 인증 기관이 없는 경우 새로 만들어야 합니다.
>- 장치 플랫폼에 따라 SCEP(Simplified Certificate Enrollment Protocol) 프로필을 사용하기로 결정한 경우 NDES(네트워크 장치 등록 서비스) 서버도 구성해야 합니다.
>-  SCEP 프로필을 사용하든, 아니면 .PFX 프로필을 사용하든 간에 Microsoft Intune 인증서 커넥터를 다운로드하고 구성해야 합니다.
> 이러한 모든 항목의 구성은 [SCE 인증서 인프라 구성](configure-certificate-infrastructure-for-scep.md) 및 [PFX 인증서 인프라 구성](configure-certificate-infrastructure-for-pfx.md)에 나와 있습니다.

### 다음 단계
- [SCEP 인증서 인프라 구성](configure-certificate-infrastructure-for-scep.md)
- [PFX 인증서 인프라 구성](configure-certificate-infrastructure-for-pfx.md)
- [Intune 인증서 프로필 구성](configure-intune-certificate-profiles.md)



<!--HONumber=Jul16_HO3-->


