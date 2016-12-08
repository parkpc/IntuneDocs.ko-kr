---
title: "Intune으로 마이그레이션 | Microsoft Intune"
description: 
keywords: 
author: jeffgilb
ms.author: jeffgilb
manager: jeffgilb
ms.date: 11/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 88936b8a-7453-4410-b6db-29f636ba3e72
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 29b6e5a3d319c741482fcc2b600842e2e42b96e2
ms.openlocfilehash: c5adeb2164a55d029c9d7f86490092a72f04f126


---

# <a name="migrate-to-intune"></a>Intune으로 마이그레이션


기존 엔터프라이즈 이동성 관리 솔루션에서 Intune으로 마이그레이션은 아래의 일반적인 단계 순서를 따를 수 있습니다.

![Intune을 위한 마이그레이션 단계](./media/migrate-intune-steps.png)

## <a name="notify-users"></a>사용자에게 알림

Intune 파일럿 배포가 요구 사항을 만족하는 것으로 확인된 후 예상되는 사용자 장치의 Intune으로 마이그레이션에 관하여 사용자에게 알립니다. 메일 주소, 지침 및 [포스터](https://gallery.technet.microsoft.com/Intune-End-User-Enrollment-3a0c9b0c?WT.mc_id=Blog_Intune_General_PCIT)는 기대치를 설정하고 사용자가 회사 리소스 및 응용 프로그램에 대해 중단되지 않는 연결을 유지하기 위해 실행해야 하는 단계에 관한 등록 정보를 제공하는 데 도움이 될 수 있습니다. 지원 팀이 마이그레이션 프로세스에서 사용자를 도울 준비가 되어 있는지 확인합니다.

## <a name="modify-your-existing-enterprise-mobility-management-solution"></a>기존 엔터프라이즈 이동성 관리 솔루션 수정

기존 엔터프라이즈 이동성 관리 솔루션과 Intune 간에 조건부 액세스 정책을 처리하도록 계획하는 방법에 따라 기존 조건부 액세스 정책을 사용하지 않도록 설정해야 할 수 있습니다. 기존 조건부 액세스 정책을 사용하지 않도록 설정하거나 기존 조건부 액세스 정책의 범위가 Intune으로 마이그레이션하려고 하는 사용자/장치를 포함하지 않도록 설정합니다.  Intune과 기존 엔터프라이즈 이동성 관리 솔루션이 모두 같은 사용자/장치에 조건부 액세스 정책을 적용하도록 하지 마십시오.

## <a name="enable-intune-conditional-access-policy-optional"></a>조건부 액세스 정책을 설정(선택 사항)

장치 마이그레이션을 위한 유예 기간 없이 조건부 액세스 정책을 즉시 적용하기로 결정한 경우 이 단계에서 Intune의 조건부 액세스 정책을 설정하십시오.  이 결정을 사용자 및 기술 지원 팀에 잘 전달해야 합니다.  장치가 Intune에 등록되지 않고 Intune 정책을 준수하지 않은 경우 사용자는 Intune에 등록하고 장치가 Intune 정책을 준수할 때까지 회사 리소스에 액세스할 수 없습니다.

## <a name="unenrolling-devices-from-your-existing-enterprise-mobility-management-solution"></a>기존 엔터프라이즈 이동성 관리 솔루션에서 장치 등록 해제

Intune에 등록하기 전에 기존 엔터프라이즈 이동성 관리 솔루션에서 장치를 등록 해제해야 합니다. 최상의 사용자 환경을 위해 사용자가 장치 자체를 등록 해제할 수 있도록 하는 것이 좋습니다.  솔루션 공급자의 등록 해제 지침에 따라 사용자 및 장치를 플랫폼에서 올바르게 제거하여 최종 사용자에 대한 장애를 최소화해야 합니다.

## <a name="enrolling-devices-in-intune"></a>Intune에 장치 등록

마이그레이션을 예약한 사용자는 회사 리소스, 전자 메일 및 응용 프로그램에 대한 액세스를 다시 획득하거나 액세스 상실을 방지하기 위해 즉시 Intune에 등록해야 합니다. 조건부 액세스를 구성했는데 사용자가 Intune에 등록하기 전에 메일에 연결하려고 하는 경우에는 해당 사용자의 액세스가 차단되며 등록 메일이 전송됩니다. 이 메일은 사용자에게 장치를 Intune에 등록하도록 안내합니다.  또는 사용자가 Intune 회사 포털 앱 또는 Windows 8.1 및 Windows 10 Mobile의 경우 운영 체제를 통해 고유하게 Intune에 등록할 수 있습니다. 플랫폼별 등록 단계에 대한 추가 지침은 [Microsoft Intune 사용에 관하여 최종 사용자에게 알릴 사항](/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune)을 참조하세요.

## <a name="configure-intune-conditional-access-optional"></a>Intune 조건부 액세스 구성(선택 사항)

조건부 액세스 적용에 대해 유예 기간을 허용한 경우 Intune에서 조건부 액세스 정책을 설정하여 최종 사용자에게 알린 유예 기간이 종료했을 때 등록을 시작할 수 있습니다. 이렇게 하려면 모든 장치가 Intune 조건부 액세스 정책의 요구 사항을 즉시 만족해야 합니다.

## <a name="enroll-remaining-devices-and-users"></a>남은 장치 및 사용자 등록

이제 조건부 액세스를 설정했으므로 모든 사용자는 회사 리소스에 대한 액세스를 획득하려면 Intune에 등록하고 조직의 준수 정책을 준수해야 합니다. 사용자를 단계별 등록으로(한 번에 모두 실행하지 않고) 마이그레이션한 경우 모든 장치 및 사용자가 등록되고 Intune에서 관리될 때까지 위 단계를 반복합니다.

## <a name="retire-the-previous-enterprise-mobility-management-solution"></a>기존 엔터프라이즈 이동성 관리 솔루션 사용 중지

모든 사용자및 장치를 Intune으로 마이그레션하고 Intune으로 마이그레이션이 성공적인 것을 확인한 후 기존 엔터프라이즈 이동성 관리 솔루션을 사용 중지하거나 서비스에서 구독 취소할 수 있습니다. 솔루션 공급자의 지침에 따라 불필요한 인프라 요구사항을 정확히 모두 제거하고 구독/라이선스를 모두 취소해야 합니다.

## <a name="additional-migration-resources"></a>추가 마이그레이션 리소스

Intune으로 마이그레이션에 대해 추가적인 도움이 필요합니까? 우리는 마이그레이션을 원활하게 수행하도록 돕기 위해 전문가 지원 옵션을 제공합니다.

<!--- - [Microsoft Intune Onboarding](/em/solutions/fasttrack-center-benefit-for-enterprise-mobility-suite-ems)--->
- [Microsoft Consulting Services](https://www.microsoft.com/en-us/microsoftservices/default.aspx)
- [Intune 기술 및 일반 지원](/intune/troubleshoot/how-to-get-support-for-microsoft-intune)
- [Microsoft Intune TechNet 포럼](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod)

## <a name="get-a-downloadable-copy-of-this-guide"></a>이 가이드의 다운로드 가능한 복사본 가져오기

이 전체 가이드의 다운로드 가능 복사본을 가져오려면 [TechNet 갤러리](https://gallery.technet.microsoft.com/Migrating-to-Intune-ea439387)를 방문하세요.



<!--HONumber=Nov16_HO4-->


