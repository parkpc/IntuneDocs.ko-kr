---
# required metadata

title: GPO 및 Intune 정책 충돌 해결 | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: e76af5b7-e933-442c-a9d3-3b42c5f5868b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# GPO(그룹 정책 개체) 및 Microsoft Intune 정책 충돌 해결
Intune은 관리 컴퓨터에서 설정을 쉽게 관리하도록 지원하는 정책을 사용합니다. 예를 들어 정책을 사용하여 컴퓨터의 Windows 방화벽에 대한 설정을 제어할 수 있습니다. 많은 Intune 설정이 Windows 그룹 정책으로 구성할 수 있는 설정과 비슷합니다. 그러나 경우에 따라 두 가지 방법이 서로 충돌할 수 있습니다.

충돌이 발생하는 경우 컴퓨터에서 도메인에 로그온할 수 있는 한 도메인 수준 그룹 정책이 Intune 정책보다 우선합니다. 이런 경우 Intune 정책이 클라이언트 컴퓨터에 적용됩니다.

## 그룹 정책을 사용하는 경우 수행해야 하는 작업
적용하는 일부 정책이 그룹 정책으로 관리되고 있지 않은지 확인하십시오. 충돌을 방지하기 위해 다음 방법 중 하나 이상을 사용할 수 있습니다.

-   Intune 클라이언트를 설치하기 전에 그룹 정책 설정이 적용되지 않은 Active Directory OU(조직 구성 단위)로 컴퓨터를 이동합니다. 또한 Intune에 등록되어 있으며 그룹 정책 설정을 적용하지 않을 컴퓨터가 포함된 OU에서 그룹 정책 상속을 차단할 수 있습니다.

-   WMI 필터 또는 보안 필터를 사용하여 Intune을 통해 관리되지 않는 컴퓨터로만 GPO를 제한합니다. 이렇게 하는 방법에 대한 자세한 내용 및 예제는 아래의 [기존 그룹 정책 개체를 필터링하여 Microsoft Intune 정책과의 충돌을 방지하는 방법](resolve-gpo-and-microsoft-intune-policy-conflicts.md#BKMK_Filter) 섹션을 참조하세요.

-   Intune 정책과 충돌하는 그룹 정책 개체를 사용하지 않거나 제거합니다.

Active Directory 및 Windows 그룹 정책에 대해서는 Windows Server 문서를 참조하십시오.

## Intune 정책과 충돌을 피하기 위해 기존 GPO를 필터링하는 방법
Intune 정책과 충돌할 수 있는 설정이 지정된 GPO를 식별한 경우 다음 필터링 방법 중 하나를 사용하여 Intune을 통해 관리되지 않는 컴퓨터만으로 해당 GPO를 제한합니다.

### WMI 필터 사용
WMI 필터는 GPO를 쿼리의 조건을 충족하는 컴퓨터에 선택적으로 적용합니다. WMI 필터를 적용하려면 Intune 서비스에 컴퓨터를 등록하기 전에 회사 내 모든 컴퓨터에 WMI 클래스 인스턴스를 배포하십시오.

#### GPO에 WMI 필터를 적용하려면

1.  다음 내용을 복사하여 텍스트 파일에 붙여넣은 다음 편리한 위치에 **WIT.mof**로 저장하여 관리 개체 파일을 만듭니다. 이 파일에는 Intune 서비스에 등록할 컴퓨터에 배포하는 WMI 클래스 인스턴스가 포함됩니다.

    ```
    //Beginning of MOF file.
    #pragma classflags("forceupdate")
    #pragma namespace ("\\\\.\\Root")
    instance of __Namespace
    {
       Name = "WindowsIntune";
    };

    #pragma namespace ("\\\\.\\Root\\WindowsIntune")
    [
       Description("This class defines Microsoft Intune common properties")
    ]
    class WindowsIntune_ManagedNode
    {
       [ read, Description("This defines whether Microsoft Intune Policy is enabled"): DisableOverride ToSubClass ]
       boolean WindowsIntunePolicyEnabled;
       [ read, key, Description("This property defines the version." "Example: 1.0"): ToSubClass ]
       string Version;
    };

    instance of WindowsIntune_ManagedNode
    {
       Version = "1.0";
       WindowsIntunePolicyEnabled = 1;
    };
    ```

2.  시작 스크립트나 그룹 정책을 사용하여 파일을 배포합니다. 다음은 시작 스크립트를 위한 배포 명령입니다. WMI 클래스 인스턴스는 클라이언트 컴퓨터를 Intune 서비스에 등록하기 전에 배포해야 합니다.

    **C:/Windows/System32/Wbem/MOFCOMP &lt;MOF 파일 경로&gt;\wit.mof**

3.  다음 명령 중 하나를 실행하여, 필터링할 GPO가 Intune을 통해 관리되는 PC에 적용되는지 아니면 Intune을 사용하여 관리되지 않는 컴퓨터에 적용되는지에 따라 WMI 필터를 만듭니다.

    -   Intune을 사용하여 관리되지 않는 컴퓨터에 적용되는 GPO의 경우 다음을 사용합니다.

        ```
        Namespace:root\WindowsIntune
        Query:  SELECT WindowsIntunePolicyEnabled FROM WindowsIntune_ManagedNode WHERE WindowsIntunePolicyEnabled=0
        ```

    -   Intune에서 관리되는 컴퓨터에 적용되는 GPO의 경우 다음을 사용합니다.

        ```
        Namespace:root\WindowsIntune
        Query:  SELECT WindowsIntunePolicyEnabled FROM WindowsIntune_ManagedNode WHERE WindowsIntunePolicyEnabled=1
        ```

4.  그룹 정책 관리 콘솔에서 GPO를 편집하여 이전 단계에서 만든 WMI 필터를 적용합니다.

    -   Intune을 사용하여 관리할 컴퓨터에만 적용해야 하는 GPO의 경우 **WindowsIntunePolicyEnabled=1** 필터를 적용합니다..

    -   Intune을 사용하여 관리하지 않을 컴퓨터에만 적용해야 하는 GPO의 경우 **WindowsIntunePolicyEnabled=0** 필터를 적용합니다..

그룹 정책에서 WMI 필터를 적용하는 방법에 대한 자세한 내용은 [Security Filtering, WMI Filtering, and Item-level Targeting in Group Policy Preferences(그룹 정책 기본 설정에서 보안 필터링, WMI 필터링 및 항목 수준 대상 지정)](http://go.microsoft.com/fwlink/?LinkId=177883)블로그 게시물을 참조하십시오..

### 보안 그룹 필터 사용
그룹 정책을 사용하여, 선택된 GPO에 대한 그룹 정책 관리 콘솔의 **보안 필터링** 영역에 지정된 보안 그룹에만 GPO를 적용할 수 있습니다. 기본적으로 GPO는 **인증된 사용자**에 적용됩니다..

-   **Active Directory 사용자 및 컴퓨터** 스냅인에서 Intune을 사용하여 관리하지 않을 컴퓨터와 사용자 계정을 포함하는 새 보안 그룹을 만듭니다. 예를 들어 이 그룹의 이름을 **Microsoft Intune에 포함되지 않음**으로 지정할 수 있습니다..

-   그룹 정책 관리 콘솔에서 선택한 GPO에 해당하는 **위임** 탭에서 새 보안 그룹을 마우스 오른쪽 단추로 클릭하여 보안 그룹의 사용자 및 컴퓨터 모두에 적절한 **읽기** 및 **그룹 정책 적용** 권한을 위임합니다. **그룹 정책 적용** 권한은 **고급** 대화 상자에서 지정할 수 있습니다.

-   그런 다음 새 보안 그룹 필터를 선택한 GPO에 적용하고 **인증된 사용자** 기본 필터를 제거합니다.

새 보안 그룹은 Intune 서비스 변경 내용에서 등록 항목으로 유지되어야 합니다.

### 참고 항목
[Microsoft Intune을 사용하여 Windows PC 관리](manage-windows-pcs-with-microsoft-intune.md)


<!--HONumber=May16_HO1-->


