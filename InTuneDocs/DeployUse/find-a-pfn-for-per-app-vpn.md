---
# required metadata

title: 앱별 VPN에 대한 PFN(패키지 패밀리 이름) 찾기 | Microsoft Intune
description:
keywords:
author: nbigman
manager: [ALIAS]
ms.date: 05/10/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 74643d1d-4fd9-4cff-ac79-1a42281d2f76

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: tycast
#ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# 앱별 VPN에 대한 PFN(패키지 패밀리 이름) 찾기

앱별 VPN을 구성할 수 있도록 두 가지 방법으로 PFN을 찾을 수 있습니다.

## Windows 10 컴퓨터에 설치된 앱에 대한 PFN 찾기 

작업할 앱이 Windows 10 컴퓨터에 이미 설치되어 있는 경우 [Get-AppxPackage](https://technet.microsoft.com/library/hh856044.aspx) PowerShell cmdlet을 사용하여 PFN을 가져올 수 있습니다.

Get-AppxPackage 구문은 다음과 같습니다.

` Parameter Set: __AllParameterSets`
` Get-AppxPackage [[-Name] <String> ] [[-Publisher] <String> ] [-AllUsers] [-User <String> ] [ <CommonParameters>]`

> 참고: PFN을 검색하려면 PowerShell을 관리자 권한으로 실행해야 할 수 있습니다.

예를 들어 컴퓨터에 설치된 모든 유니버설 앱에 대한 정보를 가져오려면 `Get-AppxPackage`를 사용합니다.

이름을 알고 있거나 이름의 일부를 알고 있는 앱에 대한 정보를 가져오려면 `Get-AppxPackage *<app_name>`을 사용합니다. 와일드카드 문자를 사용하면 앱의 전체 이름을 잘 모를 경우 특히 유용합니다. 예를 들어 OneNote에 대한 정보를 가져오려면 `Get-AppxPackage *OneNote`를 사용합니다.


다음은 OneNote에 대해 검색한 정보입니다.

`Name                   : Microsoft.Office.OneNote`

`Publisher              : CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US`

`Architecture           : X64`

`ResourceId             :`

`Version                : 17.6769.57631.0`

`PackageFullName        : Microsoft.Office.OneNote_17.6769.57631.0_x64__8wekyb3d8bbwe`

`InstallLocation        : C:\Program Files\WindowsApps`

`\Microsoft.Office.OneNote_17.6769.57631.0_x64__8wekyb3d8bbwe`

`IsFramework            : False`

**`PackageFamilyName      : Microsoft.Office.OneNote_8wekyb3d8bbwe`**

`PublisherId            : 8wekyb3d8bbwe`



## 컴퓨터에 설치되어 있지 않은 앱에 대한 PFN 찾기

1.  https://www.microsoft.com/en-us/store/apps로 이동합니다.
2.  검색 표시줄에 앱의 이름을 입력합니다. 이 예제에서는 OneNote를 검색합니다.
3.  앱에 대한 링크를 클릭합니다. 액세스하는 URL은 끝부분에 일련의 문자가 있다는 점에 유의하세요. 이 예제에서 URL은 다음과 같습니다.
`https://www.microsoft.com/en-us/store/apps/onenote/9wzdncrfhvjl`
4.  다른 탭에서 URL `https://bspmts.mp.microsoft.com/v1/public/catalog/Retail/Products/<app id>/applockerdata`를 붙여넣습니다. 여기에서 `<app id>`를 https://www.microsoft.com/en-us/store/apps에서 가져온 앱 ID 즉, 3단계에서 보았듯이 URL의 끝부분에 있는 일련의 문자로 대체합니다. OneNote를 검색하는 이 예제에서는 `https://bspmts.mp.microsoft.com/v1/public/catalog/Retail/Products/9wzdncrfhvjl/applockerdata`를 붙여넣습니다.

Edge에서는 원하는 정보가 표시됩니다. Internet Explorer에서는 정보를 확인하려면 **열기**를 클릭해야 합니다. PFN 값은 첫 번째 줄에 제공됩니다. 이 예제에서 결과는 다음과 같이 표시됩니다.
 

`{`
`  "packageFamilyName": "Microsoft.Office.OneNote_8wekyb3d8bbwe",`
`  "packageIdentityName": "Microsoft.Office.OneNote",`
`  "windowsPhoneLegacyId": "ca05b3ab-f157-450c-8c49-a1f127f5e71d",`
`  "publisherCertificateName": "CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US"`
`}`



<!--HONumber=Jun16_HO1-->


