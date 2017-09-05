---
title: "Intune과 네트워크 액세스 제어 통합"
titleSuffix: Intune on Azure
description: "Intune과 NAC(네트워크 액세스 제어) 통합"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: aa7ecff7-8579-4009-8fd6-e17074df67de
ms.reviewer: davidra
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 15651b3f03959fd96edf1a585d0075204e35e61b
ms.sourcegitcommit: ce49a5c50e0d1e377ecb94185c4e6ac450e4701d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/29/2017
---
# <a name="network-access-control-nac-integration-with-intune"></a>Intune과 NAC(네트워크 액세스 제어) 통합

Intune은 장치가 온-프레미스 리소스에 액세스하려고 할 때 조직이 회사 데이터를 보호할 수 있도록 네트워크 액세스 제어 파트너와 통합됩니다.

## <a name="how-do-intune-and-nac-solutions-help-protect-your-organization-resources"></a>Intune 및 NAC 솔루션은 조직 리소스를 어떻게 보호하나요?

NAC 솔루션은 액세스 제어 결정을 내리기 위해 Intune에서 장치 등록 및 규정 준수 상태를 검사합니다. 장치가 등록되지 않았거나 등록되었으나 Intune 장치 준수 정책을 준수하지 않을 경우 등록 및/또는 장치 준수 확인을 위해 Intune에 리디렉션되어야 합니다.

### <a name="example"></a>예제

장치가 등록되었으며 Intune 규격인 경우 NAC 솔루션에서 회사 리소스에 대한 장치 액세스를 허용해야 합니다. 예를 들어 사용자가 회사 Wi-Fi 또는 VPN 리소스에 액세스하려고 할 때 액세스가 허용되거나 거부될 수 있습니다.

## <a name="nac-and-conditional-access"></a>NAC 및 조건부 액세스

NAC는 조건부 액세스와 연동하여 액세스 제어 결정을 제공합니다.

- 자세한 내용은 [Intune에서 조건부 액세스를 사용하는 일반적인 방법](conditional-access-intune-common-ways-use.md)을 참조하세요.

## <a name="how-the-nac-integration-works"></a>NAC 통합의 작동 방식

여기서는 Intune과 통합된 경우 NAC 통합이 작동하는 방식을 간략하게 설명합니다. 처음 세 단계에서는 온보딩 프로세스에 대해 설명합니다. NAC 솔루션이 Intune과 통합된 후 4-9단계에서는 지속적인 작업을 설명합니다.

![NAC와 Intune의 연동 방식](./media/ca-intune-common-ways-2.png)

1.  NAC 파트너 솔루션을 AAD(Azure Active Directory)에 등록하고 Intune NAC API에 위임된 사용 권한을 부여합니다.

2.  Intune 검색 URL을 포함한 적절한 설정으로 NAC 파트너 솔루션을 구성합니다.

3.  인증서 인증을 위해 NAC 파트너 솔루션을 구성합니다.

4.  사용자가 회사 Wi-Fi 액세스 지점에 연결하거나 VPN 연결 요청을 수행합니다.

5.  NAC 파트너 솔루션이 장치 정보를 Intune에 전달하고 장치 등록 및 준수 상태를 Intune에 요청합니다.

6.  장치가 규격이 아니거나 등록되지 않은 경우 NAC 파트너 솔루션이 사용자에게 등록하거나 장치 준수를 수정하도록 알립니다.

7.  장치가 해당 규정 준수 및/또는 등록 상태를 확인하려고 합니다.

8.  장치가 등록되고 규격이면 NAC 파트너 솔루션이 Intune에서 상태를 가져옵니다.

9.  성공적으로 연결되어 장치가 회사 리소스에 액세스할 수 있게 됩니다.

## <a name="next-steps"></a>다음 단계

-   [Intune과 Cisco ISE 통합](http://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_01000.html)

-   [Intune과 Citrix NetScaler 통합](http://docs.citrix.com/en-us/netscaler-gateway/12/microsoft-intune-integration/configuring-network-access-control-device-check-for-netscaler-gateway-virtual-server-for-single-factor-authentication-deployment.html)

-   [Intune과 HP Aruba Clear Pass 통합](https://support.arubanetworks.com/Documentation/tabid/77/DMXModule/512/Command/Core_Download/Default.aspx?EntryId=23757)
