---
title: "Microsoft Intune에 대한 최종 사용자 교육 방법 | Microsoft Intune"
description: "Intune을 성공적으로 배포하기 위해 정보를 최종 사용자와 공유합니다."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/17/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 48914533-f138-4dc0-8b93-4cea3ac61f7b
ms.reviewer: robstack
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: bb2848e42e0e842bd8049ab74904c70c582d6917
ms.openlocfilehash: 5f01c174be566b9dd645bb058de501b02693e07e
ms.lasthandoff: 02/23/2017


---

# <a name="how-to-educate-your-end-users-about-microsoft-intune"></a>Microsoft Intune에 대한 최종 사용자 교육 방법

Microsoft Intune을 사용하면 회사 데이터 보호를 유지하면서 직원들이 모바일 장치를 이용할 수 있습니다. [무료 평가판](/Intune/Understand/mobile-device-management-trial-guide-microsoft-intune.md)을 통한 Intune 평가, [메일 보호](/Intune/Understand/common-ways-to-use-intune#protecting-your-office-365-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices.md) 및 [Intune SDK와 함께 앱 포함](/intune/develop/intune-app-sdk.md)을 비롯하여 성공적인 배포를 위한 여러 단계가 있습니다.

이러한 기술 중에서 회사가 장치를 관리하는 이유의 중요성을 사용자가 이해하게 하는 기술은 없습니다. 실제로 Intune을 [BYOD 솔루션](/enterprise-mobility-security/solutions/byod-design-considerations-guide.md)으로 배포하는 경우 특히 개인 정보가 침해된다고 느끼는 최종 사용자가 많습니다.

> [!Important]
> 회사에서 장치를 관리해야 하는 이유에 대한 최종 사용자의 염려를 이해하고 사전에 해결하는 것이 성공적인 롤아웃에 중요합니다.

채택은 기술을 작동하고 전체 직원에게 배포하는 것뿐 아니라 최종 사용자 인구가 Intune에서 제공하는 보안 액세스를 수용하도록 하는 것입니다. 사용자가 엔터프라이즈 이동성에 대해 두려워하는 것은 대체로 엔터프라이즈 이동성의 기능과 수행할 수 있는 사항(수행할 수 없는 사항)에 대해 알아야 할 사항을 설명하지 않았기 때문입니다.

## <a name="things-to-consider-about-your-end-users"></a>최종 사용자에 대해 고려할 사항

__최종 사용자의 경험 수준은 어떤가요?__ 최종 사용자는 다양한 기술에서 다양한 경험이 있을 수 있습니다. 이러한 경험은 기억할 만한 자녀 사진부터 장치를 싱크대에 떨어뜨려 백업되지 않은 모든 데이터가 손실된 시간까지 좋은 경험일 수도 있고 나쁜 경험일 수도 있습니다. 이러한 경험에 따라 기술에 접근하는 방식과 장치의 개인 및 비즈니스 사용에 대한 인식이 달라집니다.

__이동성 관리는 내게 무엇을 의미하나요?__ 사용자 장치와 정보에 대한 회사의 액세스 권한 유무를 사용자가 완벽하게 이해하지 못할 수 있습니다. 사용자가 모든 움직임을 추적하는 IT 및 리더십의 잠재력에 대해 염려할 가능성이 큽니다. 특히 장치의 모든 활동이 비공개라고 믿는 경험이 적은 사용자에게는 염려스러울 수 있습니다. 경험이 많은 사용자는 장치를 감시하는 "빅 브라더"에서 비롯된 특정 두려움이 있을 수 있으며 이러한 염려를 동료에게 전파할 수도 있습니다.

__최종 사용자에게 어떤 불편을 줄 수 있나요?__ 앱을 설치하고, 장치를 등록하고, 준수를 유지하는 데 시간이 걸립니다. 회사 데이터의 보안을 Intune 배포의 최상위 우선 순위로 유지하지만 개인 장치에서 특별한 암호를 요구하면 사용자가 회사의 장치 관리에 분노하게 됩니다. 비즈니스에 중요한 전화 회의 중에 필수 앱 업데이트를 보내면 사용자의 생산성이 저하될 수 있으며, 모바일 장치를 사용할 수 있게 하려는 의도에 맞지 않습니다.

## <a name="things-you-should-do"></a>수행할 작업

이러한 사용자 염려를 줄이면 배포가 더 원활해집니다. 최종 사용자가 장치 관리를 수용하기 쉽게 만들기 위해 고려할 방법 목록이 있습니다.

* __풍부한 리소스를 제공합니다.__ Intune 설명서에는 최종 사용자가 장치 등록 및 문제 해결과 같은 특정 작업을 수행하는 방법을 파악하는 데 도움이 되는 다양한 콘텐츠가 있습니다. 이 중에는 사용자가 회사 포털 앱에서 이동된 문서가 포함되며, 문서는 회사 포털 앱 설치 및 Intune 등록, 보유한 장치에서 사용자가 수행할 수 있는 일반 작업 및 문제 해결 섹션으로 나뉩니다. 이 설명서는 [관리되는 장치를 사용하여 작업을 완료](/Intune/EndUser/use-managed-devices-to-get-work-done)하는 방법에 대한 설명에서 확인할 수 있습니다.

* __쉽게 액세스할 수 있게 합니다.__ 최종 사용자가 장치에서 도움을 받을 수 있는 위치를 알아야 합니다. [회사 포털을 사용자 지정](/Intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-7)하는 경우 사용자가 도움이 필요하면 지원을 받을 수 있도록 IT 관리자의 연락처 정보를 반드시 포함하세요.

* __개인적입니다.__ 배포와 관련 없는 지침을 제공하면 최종 사용자가 환경에 대한 배려가 없다고 느낄 수 있습니다. 이 [IT 관리자를 위한 사용자 지정 가능한, 최종 사용자 Intune 등록 템플릿](https://gallery.technet.microsoft.com/office/Intune-End-User-Enrollment-3a0c9b0c)을 사용하여 최종 사용자를 위한 고유한 등록 지침을 만들 수 있습니다.

* __다른 커뮤니케이션 방법을 찾습니다.__ [다양한 학습 스타일](http://www.umassd.edu/dss/resources/facultystaff/howtoteachandaccommodate/howtoaccommodatedifferentlearningstyles/)과 마찬가지로, 사용자에게는 원하는 정보 사용 방법이 있습니다. 설명서보다 동영상을 선호하는 사용자를 위해 [다양한 장치 유형을 등록하는 방법의 동영상 버전](https://channel9.msdn.com/Series/IntuneEnrollment) 등이 Channel 9에서 제공됩니다. 이 동영상을 사용자 고유의 [SharePoint 사이트](https://support.office.com/article/Embed-a-video-from-Office-365-Video-59e19984-c34e-4be8-889b-f6fa93910581)에 직접 포함하거나, 동영상 또는 오디오 트랙의 로컬 복사본으로 다운로드할 수 있습니다.

* __최종 사용자 경험을 파악합니다.__ 최종 사용자 경험은 회사의 생산성에 영향을 주며, 사용자 경험을 이해하면 도움을 요청할 때 문제를 더 쉽게 해결할 수 있습니다. 최종 사용자가 앱을 다운로드하는 방법을 이해하면 사용자에게 발생하는 문제를 더 쉽게 진단하고 더 빨리 문제를 해결하도록 도울 수 있습니다.

* **OWA(Outlook Web Access)**
  * [Intune에서 Android 장치 사용](https://docs.microsoft.com/Intune/EndUser/using-your-android-device-with-intune)
  * [Android 사용자가 앱을 얻는 방법](how-your-android-users-get-their-apps.md)

* **Android**
  * [Intune에서 iOS 장치 사용](https://docs.microsoft.com/Intune/EndUser/using-your-ios-device-with-intune)
  * [iOS 사용자가 앱을 얻는 방법](how-your-ios-users-get-their-apps.md)

* **Windows**
  * [Intune에서 Windows 장치 사용](https://docs.microsoft.com/Intune/EndUser/using-your-windows-device-with-intune)
  * [Windows 사용자가 앱을 얻는 방법](how-your-windows-users-get-their-apps.md)

* __솔직하게 설명합니다.__ 장치에서 관리하려는 사항을 사용자에게 명확하게 알립니다. 수집 중인 데이터 종류 및 수집하는 이유를 알립니다. 모든 자산 데이터를 사용하려는 방법을 알립니다. [Microsoft는 클라우드에서 고객 데이터를 처리하는 방법과 관련해서 최대한 많은 정보에 대한 권한이 회사에 있다고 믿으며](https://www.microsoft.com/trustcenter/about/transparency), 이러한 철학이 Intune에 대한 최종 사용자 만족도를 크게 높일 수 있다고 생각합니다.

>[!Note]
> 가능한 경우 투명성은 배포 성공의 필수 요건입니다.

신뢰와 잘 다듬어진 준수 정책을 결합하여 특정 유형의 개인 데이터를 *볼 수 있는* 경우에도 *보려고 하지* 않으며, 개인 정보를 침해할 경우 책임이 발생할 수 있다는 것을 최종 사용자에게 알립니다. 법무 및 HR 부서와 함께 방침을 작성하면 특히 까다로운 직원들에게 도움이 될 수 있습니다.

