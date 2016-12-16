---
title: "Intune 앱 SDK의 이점 | Microsoft 문서"
description: 
keywords: 
author: mtillman
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd9f05e7-26e6-45e0-8d38-67d8232b1cae
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 613e293d9bd853d6de7cdc0d753cc8473afc180b
ms.openlocfilehash: e8f96499f006af590b6e7da295503696110dad4e


---

# <a name="intune-app-sdk-overview"></a>Intune 앱 SDK 개요
Intune 앱 SDK는 iOS 및 Android 플랫폼 둘 다에 사용할 수 있으며 Microsoft Intune을 통해 모바일 앱 관리 기능을 사용할 수 있게 합니다. Intune 앱 SDK는 앱 개발자에게서 필요한 코드 변경의 양을 최소화하려고 합니다. 앱의 동작을 변경하지 않고 대부분의 SDK 기능을 사용하도록 설정할 수 있습니다. 최종 사용자 및 IT 관리자 환경을 개선하기 위해 API를 활용하여 앱 참여를 요구하는 기능에 대한 앱 동작을 사용자 지정할 수 있습니다. 

앱을 사용하도록 설정하면 IT 관리자가 Intune 관리 앱에 정책을 배포하고 이러한 기능을 활용하여 회사 데이터를 보호할 수 있습니다.

## <a name="regular-features"></a>일반 기능

### <a name="control-users-ability-to-move-corporate-documents"></a>사용자의 회사 문서 이동 기능을 제어합니다.
IT 관리자는 Intune 관리 앱에서 회사 문서의 파일 재배치를 제어할 수 있습니다. 예를 들어 파일 백업 앱이 회사 데이터를 클라우드로 백업할 수 없도록 하는 정책을 배포할 수 있습니다.

### <a name="configure-clipboard-restrictions"></a>클립보드 제한 구성
IT 관리자는 Intune 관리 앱의 클립보드 동작을 구성할 수 있습니다. 예를 들어 최종 사용자가 클립보드를 사용하여 Intune 관리 앱에서 잘라내기/복사하여 관리되지 않는 개인 앱에 붙여넣을 수 없도록 정책을 배포할 수 있습니다.

### <a name="enforce-encryption-on-saved-data"></a>저장된 데이터에 암호화 적용
IT 관리자는 앱에서 장치에 저장하는 데이터가 암호화되도록 하는 정책을 적용할 수 있습니다.

### <a name="remotely-wipe-corporate-data"></a>원격으로 회사 데이터 초기화
IT 관리자는 Intune 관리 앱에서 회사 데이터를 원격으로 초기화할 수 있습니다. 이 기능은 ID 기반이며 최종 사용자의 회사 ID와 연결된 파일만 삭제합니다. 이렇게 하려면 기능에 앱 참여가 필요합니다. 앱은 사용자 설정에 따라 초기화를 수행할 ID를 지정할 수 있습니다. 앱에서 지정된 이러한 사용자 설정이 없을 경우 기본 동작은 응용 프로그램 디렉터리를 초기화하고 최종 사용자에게 액세스가 제거되었음을 알리는 것입니다.

### <a name="enforce-the-use-of-a-managed-browser"></a>Managed Browser 사용 적용
IT 관리자는 Intune 관리 앱 내에서 링크를 열 때 Intune Managed Browser 앱을 사용하도록 적용할 수 있습니다. 이렇게 하면 회사 환경에 표시되는 링크가 Intune 관리 앱의 도메인 내에 유지됩니다.

### <a name="enforce-a-pin-policy"></a>PIN 정책 적용
IT 관리자는 Intune 관리 앱이 시작될 때 PIN 정책을 적용할 수 있습니다. 이렇게 하면 앱을 시작하는 사용자가 처음에 등록된 회사 또는 학교 계정으로 로그인한 사용자와 동일한 사용자이도록 합니다. 최종 사용자가 해당 PIN을 구성할 때 Intune 앱 SDK는 Azure Active Directory를 사용하여 등록된 Intune 계정과 최종 사용자의 자격 증명을 비교하여 확인합니다.

### <a name="require-users-to-enter-credentials-before-they-can-start-apps"></a>사용자가 앱을 시작하기 전에 자격 증명을 입력하도록 요구
IT 관리자는 사용자가 Intune 관리 앱을 시작하기 전에 자격 증명을 입력하도록 요구할 수 있습니다. Intune 앱 SDK는 Azure Active Directory를 사용하여 입력된 자격 증명이 후속 로그인에 다시 사용되는 Single Sign-On 환경을 제공합니다. ID 관리 솔루션 [Azure Active Directory와 페더레이션](https://msdn.microsoft.com/library/azure/jj679342.aspx)의 인증도 지원됩니다.

### <a name="check-device-health-and-compliance"></a>장치 상태 및 규정 준수 확인
IT 관리자는 최종 사용자가 Intune 관리 앱에 액세스하기 전에 장치 상태 및 회사 정책 준수를 확인할 수 있습니다. iOS 플랫폼에서 이 정책은 장치가 무단 해제되었는지 확인합니다. Android 플랫폼에서 이 정책은 장치가 루팅되었는지 확인합니다.

### <a name="sdk-multi-identity-support"></a>SDK 다중 ID 지원
다중 ID 지원은 단일 앱에서 정책 관리(회사) 계정과 관리되지 않는(개인) 계정을 동시에 사용할 수 있게 해주는 기능입니다.

예를 들어 많은 사용자가 iOS 및 Android용 Outlook 앱에서 회사 및 개인 메일 계정을 둘 다 구성합니다. 사용자가 회사 계정으로 데이터에 액세스하는 경우 IT 관리자는 MAM 정책 관리가 적용됨을 확신해야 합니다. 그러나 사용자가 개인 메일 계정에 액세스할 때는 해당 데이터가 IT 관리자의 제어를 벗어나야 합니다. 이를 위해 Microsoft Intune은 관리 정책의 대상을 응용 프로그램의 회사 계정으로만 제한합니다. 이 다중 ID 기능은 조직이 개인 및 회사 계정을 둘 다 지원하는 장치와 앱에서 발생하는 데이터 보호 문제를 해결하는 데 도움이 됩니다.

* **다중 ID를 지원하는 방법**: Microsoft Intune 앱 SDK API를 사용하여 클립보드 작업 및 파일 작업과 같은 특정 데이터 작업에서 UPN(사용자 계정 이름)을 지정할 수 있습니다. SDK는 UPN을 사용하여 수행된 호출을 Microsoft Intune 서비스에 장치를 등록하는 데 사용된 UPN과 일치시킵니다. UPN이 일치하는 경우 호출이 "회사 데이터" 호출로 처리되고 데이터가 보호됩니다. UPN이 일치하지 않는 경우 호출이 "개인 데이터" 호출로 처리되고 데이터가 보호되지 않습니다.

### <a name="app-management-without-device-enrollment"></a>장치 등록이 제외된 앱 관리

>[!IMPORTANT]
>장치 등록이 제외된 Intune 모바일 앱 관리는 현재 iOS용 Intune 앱 SDK에만 사용할 수 있습니다. 


개인 장치가 있는 많은 사용자는 MDM(모바일 장치 관리) 제품에 개인 장치를 등록하지 않고 회사 데이터를 보고 사용할 수 있기를 원합니다. MDM 등록 시 장치를 전체적으로 제어해야 하므로 사용자는 회사가 개인 장치를 전체적으로 제어하는 것을 주저합니다.

장치 등록이 제외된 앱 관리를 사용하면 Microsoft Intune 서비스가 MDM 채널을 통해 정책을 배포하지 않고 직접 MAM 정책을 앱에 배포할 수 있습니다. MDM 채널이 필요하지 않으므로 MDM 등록도 필요하지 않습니다.



<!--HONumber=Dec16_HO2-->


