---
# required metadata

title: 장치 등록 | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8fc415f7-0053-4aa5-8d2b-03202eca4b87

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: damionw
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Intune에서 관리를 위해 장치 등록
Microsoft Intune MDM(모바일 장치 관리)에서는 등록을 사용하여 장치를 관리하고 리소스에 대한 액세스를 허용합니다. 장치를 등록하는 방법은 장치 유형, 소유권 및 필요한 관리 수준에 따라 다릅니다. "BYOD(Bring your own device)" 및 COD(회사 소유 장치) 시나리오는 등록 프로세스를 필요로 합니다. Exchange ActiveSync를 사용하거나 온-프레미스 또는 클라우드에서 호스트되는 조직에서는 등록 요구 사항 없이 가볍게 관리할 수 있습니다. Windows PC에서는 Intune 클라이언트 소프트웨어를 사용하여 관리할 수 있습니다.

###  지원되는 장치 플랫폼

Intune은 다음 장치 플랫폼을 관리할 수 있습니다.

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

## 장치 등록 사용  
 등록을 통해 사용자는 개인 장치에서 회사 리소스에 액세스할 수 있고 관리자는 해당 장치가 회사 리소스를 보호하는 정책을 준수하는지 확인할 수 있습니다. Intune으로 "BYOD(Bring your own device)" 시나리오를 사용하는 가장 좋은 방법입니다. 관리자는 Intune 콘솔에서 등록을 사용해야 하며 이 때 장치와 트러스트 관계를 만들고 사용자에게 라이선스를 할당해야 합니다. 그런 다음 일반적으로 사용자가 회사 또는 학교 자격 증명을 입력하여 장치를 등록합니다. 그런 다음 장치는 Intune에서 정책을 가져오고 리소스에 대한 액세스 권한을 얻습니다.

[Intune에서 장치 등록 준비](get-ready-to-enroll-devices-in-microsoft-intune.md)

## 회사 소유 장치 등록
Intune 콘솔로 COD(회사 소유 장치)를 관리할 수 있습니다. Apple에서 제공한 도구를 통해 iOS 장치를 등록할 수 있습니다. 관리자 또는 관리자 장치 등록 관리자를 사용하여 모든 장치 유형을 등록할 수 있습니다. IMEI 번호가 있는 장치도 회사 소유로 식별되고 태그가 지정되어 COD 시나리오를 사용할 수 있습니다.

[회사 소유 장치 등록](manage-corporate-owned-devices.md)

## Exchange ActiveSync와 Intune을 사용한 모바일 장치 관리
EAS MDM 정책을 사용하여 등록되지는 않았지만 EAS(Exchange ActiveSync)에 연결된 모바일 장치를 Intune에서 관리할 수 있습니다. Intune에서는 Exchange 커넥터를 사용하여 EAS 및 클라우드 호스티드 온-프레미스와 통신합니다.



[Exchange ActiveSync와 Intune을 사용한 모바일 장치 관리](mobile-device-management-with-exchange-activesync-and-microsoft-intune.md)


## Intune을 사용하여 Windows PC 관리  
또한 Windows PC Intune 클라이언트 소프트웨어를 사용하여 Windows PC를 관리하기 위해 Microsoft Intune을 사용할 수 있습니다. Intune 클라이언트로 관리하는 PC에서는 다음과 같은 작업이 가능합니다.

 - 소프트웨어 및 하드웨어 인벤토리 보고
 - 데스크톱 응용 프로그램(예:.exe 및.msi 파일) 설치
 - 방화벽 설정

Intune 클라이언트 소프트웨어로 관리된 컴퓨터는 선택적으로 초기화되거나 폐기될 수 없고 조건부 액세스, VPN 및 Wi-Fi 설정 또는 인증서 및 전자 메일 구성의 배포와 같은 많은 Intune 관리 기능을 사용할 수 없습니다.

[Intune을 사용하여 Windows PC 관리](manage-windows-pcs-with-microsoft-intune.md)


<!--HONumber=Jun16_HO2-->


