---
# required metadata

title: 사용자 및 장치 그룹 계획 | Microsoft Intune
description:
keywords:
author: nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f11bb256-1094-4f7e-b826-1314c57f3356

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# 사용자 및 장치 그룹 계획
Intune의 그룹은 장치 및 사용자 관리에 뛰어난 유연성을 제공합니다. 다음 사항에 따라 조직의 요구에 맞도록 그룹을 설정할 수 있습니다.

- 지리적 위치
- department
- 하드웨어 특성
- 운영 체제
- 장치가 사용자 소유인지 또는 회사 소유인지 여부


## Intune 그룹의 작업 방법


Intune 관리 콘솔에 있는 그룹 노드의 기본 보기는 다음과 같습니다.

![Intune 콘솔에 있는 그룹 노드에 대한 기본 보기의 스크린샷](/intune/media/Intune_Planning_Groups_Default_small.png)

정책이 그룹에 배포되므로 그룹 계층 구조는 디자인 시 주요 고려 사항 중 하나입니다. 또한 그룹을 만든 후에는 그룹의 부모 그룹을 변경할 수 없으므로 Intune 서비스 사용을 시작하는 순간부터 그룹의 디자인이 중요하다는 것을 알아야 합니다. 여기서는 조직의 요구에 따라 그룹 계층 구조를 디자인하기 위한 몇 가지 권장 방법을 설명합니다.

## 그룹 구성원 자격 규칙

1. 그룹에는 사용자 또는 장치 중 하나만 포함할 수 있으며 이 둘을 동시에 포함할 수는 없습니다.

    * **장치 그룹:** 여기에는 컴퓨터와 모바일 장치가 모두 포함됩니다. 그룹에 컴퓨터를 추가하려면 먼저 컴퓨터를 등록해야 합니다. 그룹에 모바일 장치를 추가하려면 먼저 모바일 장치를 지원하도록 환경을 구성해야 하고, Exchange ActiveSync에서 장치를 검색하거나 등록해야 합니다.

    * **사용자 그룹:** 그룹은 Active Directory에서 동기화되는 그룹인 보안 그룹의 사용자를 포함할 수 있습니다. Active Directory 동기화를 사용하지 않는 경우 이러한 그룹을 수동으로 만들 수 있습니다.

2. 하나의 장치 또는 사용자가 둘 이상의 그룹에 속할 수도 있습니다.

3. 그룹에서 다음 구성원 규칙에 따라 구성원을 포함하거나 제외할 수 있습니다.

    * **구성원 자격 기준:** Intune에서 구성원을 포함하거나 제외하기 위해 실행하는 동적 규칙입니다. 이러한 기준은 로컬 AD(Active Directory)에서 동기화되는 **보안 그룹** 및 기타 정보를 사용합니다. 보안 그룹 또는 데이터가 변경되면 AD와 동기화할 때 그룹 구성원이 달라질 수 있습니다.

    * **직접 회원 관리 규칙:** 구성원을 명시적으로 추가하거나 제외하는 정적 규칙입니다. 구성원 목록은 정적입니다.

4. AD DS(Active Directory 도메인 서비스)가 사용자 또는 컴퓨터를 포함하는 사용자 그룹이나 장치 그룹을 만드는 데에는 필요하지 않지만, 모바일 장치를 포함하는 장치 그룹의 경우 모바일 장치를 지원하도록 환경을 구성해야 합니다.

    또한 장치를 검색하여 Intune에 추가해야 합니다.

## 그룹 관계 규칙

1. 사용자가 만드는 모든 그룹에는 상위그룹이 있어야 하며, 그룹이 만들어진 후에는 해당 그룹의 상위 그룹을 변경할 수 없습니다.

2. 하위 그룹에 사용자 또는 장치를 추가할 경우:

    * 하위 그룹은 항상 상위 그룹의 일부입니다.

    * 하위 그룹에 추가하는 새 구성원은 자동으로 해당 그룹의 상위 그룹에 추가됩니다.

    * 구성원이 상위 그룹에서 제외되면 하위 그룹에 해당 구성원을 추가할 수 없습니다.

3. 상위 그룹의 구성원이 하위 그룹의 사용 가능한 구성원을 정의합니다.

4. 상위 그룹을 삭제하면 하위 그룹도 모두 삭제됩니다.

5. 콘텐츠 및 정책을 하위 그룹에는 배포하지 않고 상위 그룹에만 배포할 수 있습니다.

6. 상위 그룹의 구성원이 아닌 하위 그룹에 특정 사용자 또는 장치를 추가할 수 있습니다. 그렇게 하면 새 그룹 구성원이 상위 그룹에 추가됩니다.

    그러나 상위 그룹에서 제외된 구성원은 하위 그룹에 추가할 수 없습니다.

7. 그룹 구성원은 재귀적입니다. 예를 들면 다음과 같습니다.

    * **박단** 은 **노트북 사용자** 보안 그룹이라는 한 그룹에만 속한 구성원입니다.

    * **노트북 사용자** 그룹은 **승인된 사용자** 보안 그룹의 구성원입니다.

    * Intune에서 **승인된 사용자** 그룹의 구성원이 포함된 동적 구성원 쿼리를 사용하는 그룹을 만듭니다. 그 결과 Intune 사용자 그룹에 **Pat**이 포함됩니다.

> [!TIP]
> 그룹을 만들 때 정책을 적용하는 방법을 생각해야 합니다. 예를 들어 조직에 장치 운영 체제 관련 정책 및 다른 역할 또는 Active Directory에 이미 정의된 조직 단위와 관련된 정책이 있을 수 있습니다. iOS, Android 및 Windows 전용 장치 그룹과 함께 각 조직 역할에 대한 사용자 그룹이 있으면 유용할 수 있습니다.

<!--- should we just link to a policies topic at this point and remove this? Ask Rob
 You'll probably want to create a default policy that applies to all groups and devices, to establish the basic compliance requirements of your company. Then create more specific policies for the broadest categories of users and devices, for example, email policies for each of the device operating systems.

 Be careful naming your policies so that you can easily identify them later. For example, a good, descriptive policy name is **WP Email Policy for Entire Company**.

 Each time you create a restrictive policy you'll want to communicate it to your users, so after you create the more general groups and policies pay attention to how you create smaller groups so that you can reduce unnecessary communication.--->

## 기본 제공 그룹
Intune은 편집하거나 삭제할 수 없는 9개의 기본 제공 그룹을 제공합니다. <!--maybe a screen shot would be best?-->

-   **모든 사용자**
    -   그룹 해제된 사용자
-   **모든 장치**
    -   모든 컴퓨터
    -   모든 모바일 장치
        -   모든 직접 관리 장치
        -   모든 Exchange ActiveSync 관리 장치
    -   모든 회사 소유 장치
    -   그룹 해제된 장치

> [!NOTE]
> 명심할 사항: *단순하게 유지*. 아래에 설명하는 것과 같은 특정 요구 사항이 조직에 없는 경우 간단하게 유지하고 기본 그룹 구조 및 정책을 사용하는 것이 장기적인 서비스 관리에 도움이 됩니다. 그룹별로 거의 차별화하지 않고 사용자를 동일하게 처리하여 유지 관리할 정책 수를 줄일 수 있다면 유지 관리가 더 용이합니다.


### 조직의 모든 사용자 및 장치
모두에 적용되는 정책이 있을 수 있으므로 조직의 모든 사용자 및 장치에 대해 부모 그룹을 정의합니다. Intune에서는 이 목적을 위해 기본 **모든 사용자** 및 **모든 장치** 그룹을 사용할 수 있습니다. 본인의 고유 장치(BYOD)에 대한 그룹 및 회사 소유 장치(CO)에 대한 그룹과 같은 구체적인 사항별로 장치를 체계화하는 하위 그룹은 **모든 사용자** 및 **모든 장치** 부모 그룹의 하위 그룹일 수 있습니다.

## 조직을 위해 그룹 사용자 지정

### BYOD 및 회사 소유 장치
조직이 회사에서 직원이 본인의 장치를 사용하도록 허용하거나(BYOD), 회사 소유 장치(CO)를 제공하거나, 둘의 조합을 적용한 경우 그러한 두 범주의 장치를 기반으로 정책을 적용하는 것이 좋습니다.

BYOD 또는 혼합의 경우에 로컬 개인 정보 보호 규정을 침해하지 않는 정책을 계획해야 합니다. 자신의 장치를 가져오는 모든 사용자에 대한 부모 그룹을 만듭니다. 그런 다음 이 그룹을 사용하여 이 범주의 모든 사용자에 해당하는 정책을 적용할 수 있습니다.

![BYOD 상위 그룹 만들기 스크린샷](/intune/media/Intune_Planning_Groups_BYOD_small.png)

마찬가지로 조직의 CO 사용자에 대한 그룹을 만들 수 있습니다.

![BYOD 및 CO에 대한 형제 사용자 그룹의 스크린샷](/intune/media/Intune_Planning_Groups_BYOD_Hierachy_View_small.png)

<!---START HERE--->

### 지역에 대한 그룹
조직에 특정 지역에 대한 정책이 필요한 경우 지리적 영역에 따라 그룹을 만들 수 있습니다. AD(Active Directory)에서 이미 만든 지역 그룹을 기반으로 하고 이를 Azure AD에 동기화할 수 있습니다. 또한 Azure AD에서 직접 만들 수도 있습니다.

이러한 스크린샷은 온-프레미스 AD에서 동기화된 그룹에 따라 Intune 그룹을 만드는 방법을 보여 줍니다. 이 예제에서는 **미국 사용자 그룹**이라는 AD 보안 그룹이 있다고 가정합니다.

1. 먼저 일반 정보를 제공합니다.

![그룹 편집 영역의 스크린샷](/intune/media/Intune_Planning_Groups_AD_General_small.png)

구성원 자격 조건에서 AD에서 동기화된 **미국 사용자 그룹**을 구성원 자격 규칙에 사용할 보안 그룹으로 선택합니다.

![그룹 편집 대화 상자](/intune/media/Intune_Planning_Groups_AD_Criteria_small.png)

검토한 다음 **마침**을 선택하여 그룹 만들기를 완료합니다.

![그룹 편집 대화 상자](/intune/media/Intune_Planning_Groups_AD_Summary_small.png)

이 예제에서는 중동 및 아시아 그룹인 MEA도 만들었습니다.

> [!NOTE] 그룹 구성원 자격이 보안 그룹 구성원 자격에 따라 채워지지 않는 경우 해당 구성원에게 Intune 라이선스를 할당했는지 확인합니다.

### 특정 하드웨어에 대한 그룹
조직이 특정 하드웨어 유형에 적용되는 정책을 요구하는 경우 이 요구 사항을 기반으로 그룹을 만들 수 있습니다. 온-프레미스 AD에서 이미 만든 특정 그룹의 기준 광고를 바탕으로 하고 Azure AD에 동기화할 수 있습니다. 또한 Azure AD에서 직접 만들 수도 있습니다. 이 예제에서는 **미국 사용자 그룹**을 **노트북 사용자** 그룹의 부모로 사용합니다.

![보안 그룹 대화 상자 선택](/intune/media/Intune_Planning_Groups_Laptop_small.png)

이제 그룹 계층 구조가 아래와 같이 표시됩니다. Intune 그룹 **노트북 사용자** 내에 구성원이 있습니다. 이제 이 그룹에 적용된 모든 정책이 미국 지역의 BYOD 노트북 사용자에게 적용됩니다.

![노트북 사용자 그룹의 표시](/intune/media/Intune_Planning_Groups_Laptop_Hierarchy_small.png)

### 특정 운영 체제에 대한 그룹
조직이 Android, iOS 또는 Windows와 같은 특정 운영 체제에 적용되는 정책을 요구하는 경우 이 요구 사항을 기반으로 그룹을 만들 수 있습니다. 앞의 예와 같이 온-프레미스 AD에서 이미 만든 OS 고유 그룹의 기준 광고를 바탕으로 하고 Azure AD에 동기화할 수 있습니다. 또한 Azure AD에서 직접 만들 수도 있습니다.

이전 예제에 나오는 같은 방법을 따라 특정 OS 플랫폼을 사용하는 <!--devices?--> 사용자를 기반으로 그룹을 만들 수 있습니다.

> [!NOTE] 사용자가 여러 모바일 플랫폼/운영 체제를 사용하며 사용자를 Android 사용자, iOS 사용자 또는 Windows 사용자로 분류하는 자동화된 방식이 없는 경우 장치 수준에서 정책을 적용하는 것이 좋습니다. 이렇게 하면 OS 관련 정책을 적용할 때 유연성이 커집니다.
>
> 장치의 OS에 따라 동적으로 그룹을 프로비전할 수 없습니다. 이 작업을 수행할 때는 AD 또는 AAD 보안 그룹을 사용합니다.

![노트북 사용자 그룹의 표시](/intune/media/Intune_Planning_Groups_OS_Hierachy_small.png)

모든 사용자 그룹이 이러한 조직 요구 사항에 따라 채워진 후 그룹 계층 구조는 다음과 같아야 합니다.

![그룹 계층 보기](/intune/media/Intune_Planning_Groups_Midpoint_Hierachy_small.png)

이 계층 구조를 사용하여 조직의 정책을 적절하게 적용할 수 있습니다.

### 장치 그룹
아래와 같이 BYOD 시나리오에 대해 모든 직원 소유 장치를 포함하는 광범위한 그룹으로 시작하여 장치에 대한 유사한 그룹을 만들 수도 있습니다.

![그룹 만들기 대화 상자](/intune/media/Intune_Planning_Groups_Device_General_small.png)

그룹에 모든 BYO 장치가 포함되도록 **모든 장치(컴퓨터 및 모바일)**을 선택해야 합니다.

![구성원 자격 기준 정의 페이지](/intune/media/Intune_Planning_Groups_Device_Criteria_small.png)

검토하고 **마침**을 선택하여 BYOD 그룹을 만듭니다.

![그룹 만들기 대화 상자](/intune/media/Intune_Planning_Groups_Device_Summary_small.png)

장치 그룹 계층 구조가 사용자 그룹 계층 구조와 비슷해질 때까지 계속해서 장치 그룹을 만듭니다. 그러면 Intune 콘솔의 그룹 노드가 다음과 같이 표시됩니다.

![Intune 그룹 계층 보기](/intune/media/Intune_Groups_Hierarchy_Final_Small.png)

## 그룹 계층 구조 및 명명 규칙
정책 관리가 용이하도록 각 정책의 이름을 용도, 플랫폼 및 적용되는 범위에 따라 지정하는 것이 좋습니다. 이 명명 표준은 정책 적용의 준비 과정에서 만든 그룹 구조를 따라야 합니다.

예를 들어 미국 지역 수준에서 모든 회사, Android, 모바일 장치에 적용되는 Android 정책의 경우 정책 이름을 **CO_US_Mob_Android_General**로 지정할 수 있습니다.

![Android에 대한 정책 만들기](/intune/media/Intune_planning_policy_android_small.png)

이러한 방식으로 정책 이름을 지정하면 아래와 같이 정책과 의도한 사용 및 범위를 콘솔의 정책 노드에서 빠르게 식별할 수 있습니다.

![Intune 정책 목록](/intune/media/Intune_planning_policy_view_small.png)

## 다음 단계
[그룹 만들기](use-groups-to-manage-users-and-devices-with-microsoft-intune.md)


<!--HONumber=Jun16_HO3-->


