---
title: "Office 365 모바일 앱에서 회사 데이터 누수 방지 | Microsoft 문서"
description: "Intune을 사용하면 Office 365 모바일 앱 또는 다른 LOB(기간 업무) 앱의 회사 데이터 누수를 방지하는 데 도움이 되는 MAM(모바일 응용 프로그램 관리) 정책을 사용하여 조직의 데이터를 보호할 수 있습니다."
keywords: 
author: jeffgilb
ms.author: jeffgilb
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 19be3de7-539c-49f5-8c46-5363b987fef9
ms.reviewer: pchacon
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: f268cf29461447306d0f5c3ca06d541d9a03a49d
ms.openlocfilehash: 0288ecd940d650304d83b7dd5803a56f69b936f7


---

# <a name="quick-start-guide-prevent-company-data-leaks-from-office-365-mobile-apps"></a>빠른 시작 가이드: Office 365 모바일 앱에서 회사 데이터 누수 방지

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune는 Office 365 모바일 앱 또는 다른 LOB(기간 업무) 앱의 회사 데이터 누수를 방지하는 데 도움이 되는 MAM(모바일 응용 프로그램 관리) 정책을 사용하여 조직의 데이터를 보호할 수 있습니다. Intune MAM 정책은 최종 사용자가 Intune MDM(모바일 장치 관리)에 장치를 등록하지 않고도 사용할 수 있습니다. 따라서 BYOD iOS 또는 Android 모바일 장치를 Microsoft MDM 솔루션(Intune, Configuration Manager 또는 EAS)에 등록하지 않으려는 사용자가 있거나, 최종 사용자 장치를 관리하지 않고 회사 데이터를 보호하려고 하거나, 이미 Microsoft MDM이 아닌 솔루션을 사용 중인 경우에는 Intune을 사용하여 회사의 데이터 보안을 강화할 수 있습니다.   

## <a name="is-this-quick-start-guide-right-for-me"></a>이 빠른 시작 가이드는 내게 적합한가요?
최종 사용자가 MDM(모바일 장치 관리) 솔루션에서 장치를 등록하지 않고도 iOS 및 Android 장치의 Office 365 및 LOB 앱 데이터에 액세스할 수 있도록 하지만 데이터를 복사하여 개인 앱에 붙여 넣는 것과 같이 해당 데이터로 할 수 있는 작업과 할 수 없는 작업을 제어하려고 하나요?

그렇다면 Microsoft Intune을 사용하여 iOS 및 Android에 Office 365 모바일 앱에 대한 MAM 정책을 설정할 수 있습니다. 잘라내기/복사/붙여넣기를 제한하고, ‘다른 이름으로 저장’을 방지하고, PIN 요구 사항을 설정하고, MAM으로 보호되는 데이터를 원격으로 초기화할 수 있는 기능 등이 여기에 포함됩니다.  이렇게 하면 사용자가 MDM 솔루션에 장치를 등록할 필요 없이 Office 모바일 앱을 사용하여 최고의 최종 사용자 환경을 유지하면서 회사 데이터가 보호됩니다.

## <a name="how-do-i-do-it"></a>어떻게 하나요?
1.    [Intune MAM(모바일 응용 프로그램 관리)이 작동하는 방식](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)에 대한 기본 사항을 확인합니다.
2.    Azure 포털에서 [MAM 정책을 만들기 전에 수행해야 할 작업](/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune)을 살펴봅니다.
3.    Intune을 사용하여 [MAM 정책을 만들고 배포](/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune)합니다.

### <a name="additional-information"></a>추가 정보:
- MAM 사용 앱을 통한 [최종 사용자 환경](/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune).
- [Intune을 사용하여 MAM을 위한 LOB 앱 준비](/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune)
- <a href="https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners" target="_blank">Microsoft Intune 응용 프로그램 파트너 목록 &rarr;</a> MAM 사용 앱 제공.

## <a name="what-should-i-do-next"></a>그다음에 어떻게 해야 하나요?
[Microsoft MDM이 아닌 솔루션에서 Microsoft Intune으로 마이그레이션](/intune/deploy-use/migrate-to-intune)

[Intune MDM에 장치 등록](/intune/deploy-use/enroll-devices-in-microsoft-intune)



<!--HONumber=Dec16_HO3-->


