<<<<<<< HEAD
---
title: "원격 초기화를 사용하여 데이터 보호 지원 | Microsoft Intune"
description: "Intune에서는 중요한 회사 데이터를 제거하고 많은 회사 리소스에 대한 액세스 권한을 제거할 수 있는 선택적 초기화 및 전체 초기화 기능을 제공합니다."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8519e411-3d48-44eb-9b41-3e4fd6a93112
ms.reviewer: lancecra
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: dcfa3af374a7e64e931508e1a8022bf8a50c71a7
ms.openlocfilehash: a09c9b55d7906ab792bda90b172a36b3656ed6dd

||||||| merged common ancestors
---
title: "원격 초기화를 사용하여 데이터 보호 지원 | Microsoft Intune"
description: "Intune에서는 중요한 회사 데이터를 제거하고 많은 회사 리소스에 대한 액세스 권한을 제거할 수 있는 선택적 초기화 및 전체 초기화 기능을 제공합니다."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8519e411-3d48-44eb-9b41-3e4fd6a93112
ms.reviewer: lancecra
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: dcfa3af374a7e64e931508e1a8022bf8a50c71a7
ms.openlocfilehash: a09c9b55d7906ab792bda90b172a36b3656ed6dd

=======
---
title: "원격 초기화를 사용하여 데이터 보호 지원 | Microsoft Intune"
description: "Intune에서는 중요한 회사 데이터를 제거하고 많은 회사 리소스에 대한 액세스 권한을 제거할 수 있는 선택적 초기화 및 전체 초기화 기능을 제공합니다."
keywords: 
author: staciebarker
ms.author: staciebarker
manager: angrobe
ms.date: 11/02/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8519e411-3d48-44eb-9b41-3e4fd6a93112
ms.reviewer: lancecra
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9d44a6494bed0758b9768045bd204ea0eb481636
ms.openlocfilehash: 5900894ded0518f731ac76c3eac0332e5a3f6c4b

>>>>>>> 8eb792f839091c94f1906392b6dd69b3e259f43d

---
<<<<<<< HEAD

# Microsoft Intune을 사용하여 전체 또는 선택적 초기화를 통해 데이터 보호 지원
장치가 더 이상 필요하지 않기 때문이든, 용도가 변경되었기 때문이든, 분실되었기 때문이든 관계없이 Intune으로 관리 장치에서 앱 및 데이터를 초기화할 수 있습니다. 이를 위해, Intune은 선택적 초기화 및 전체 초기화 기능을 제공합니다. 또한 사용자가 Intune에 등록된 개인적으로 소유한 장치의 Intune 회사 포털에서 원격 장치 초기화 명령을 실행할 수 있습니다.
||||||| merged common ancestors

# Microsoft Intune을 사용하여 전체 또는 선택적 초기화를 통해 데이터 보호 지원
장치가 더 이상 필요하지 않기 때문이든, 용도가 변경되었기 때문이든, 분실되었기 때문이든 관계없이 Intune으로 관리 장치에서 앱 및 데이터를 초기화할 수 있습니다. 이를 위해, Intune은 선택적 초기화 및 전체 초기화 기능을 제공합니다. 또한 사용자가 Intune에 등록된 개인적으로 소유한 장치의 Intune 회사 포털에서 원격 장치 초기화 명령을 실행할 수 있습니다.
=======

# <a name="help-protect-your-data-with-full-or-selective-wipe-using-microsoft-intune"></a>Microsoft Intune을 사용하여 전체 또는 선택적 초기화를 통해 데이터 보호 지원
Intune 관리 장치 중에서 이제 필요 없거나 용도를 다시 설정하거나 잃어버린 장치에 있는 앱과 데이터를 초기화할 수 있습니다. 이를 위해, Intune은 선택적 초기화 및 전체 초기화 기능을 제공합니다. 또한 사용자가 Intune에 등록된 개인적으로 소유한 장치의 Intune 회사 포털 앱에서 원격 장치 초기화 명령을 실행할 수 있습니다.
>>>>>>> 8eb792f839091c94f1906392b6dd69b3e259f43d

  > [!NOTE]
  > 이 항목에서는 Intune 모바일 장치 관리에서 관리 장치를 초기화하는 방법만 설명합니다. [Azure 포털](https://portal.azure.com)을 사용하여 [앱에서 회사 데이터를 초기화](wipe-managed-company-app-data-with-microsoft-intune.md)할 수도 있습니다. [Intune 클라이언트 소프트웨어로 관리되는 컴퓨터를 사용 중지](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client#retire-a-computer.md)할 수도 있습니다.

## <a name="full-wipe"></a>전체 초기화

**전체 초기화** 시에는 모든 회사 및 사용자 데이터와 설정이 제거되어 장치가 공장 기본 설정으로 복원됩니다. 그리고 장치가 Intune에서 제거됩니다. 전체 초기화는 새로운 사용자에게 장치를 제공하기 전이나 장치를 분실하거나 도난당한 경우 장치를 리셋하는 데 유용합니다.  **전체 초기화는 주의하여 선택해야 합니다. 장치의 데이터가 복구될 수 없습니다**.


> [!Warning]
> RAM이 4GB 미만인 Windows 10 RTM 장치(Windows 10 버전 1511 이전 장치)는 초기화된 경우 액세스하지 못할 수 있습니다. 응답하지 않는 Windows 10 장치에 액세스하려면 USB 드라이브로 장치를 부팅할 수 있습니다.

### <a name="remotely-wipe-a-device-from-the-intune-administrator-console"></a>Intune 관리자 콘솔에서 장치를 원격으로 초기화

1.  초기화할 장치를 선택합니다. 사용자 또는 장치를 기준으로 찾을 수 있습니다.

    -   **사용자 기준:**

        1.  [Intune 관리자 콘솔](https://manage.microsoft.com/)에서 **그룹** &gt; **모든 사용자**를 선택합니다.

        2.  초기화하려는 모바일 장치의 사용자의 이름을 선택합니다. **속성 보기**를 선택합니다.

        3.  사용자의 **속성** 페이지에서 **장치**를 선택한 다음 초기화하려는 모바일 장치의 이름을 선택합니다. 여러 장치를 선택하려면 Ctrl 키를 누른 채 장치를 클릭합니다.

    -   **장치 기준:**

        1.  [Intune 관리자 콘솔](https://manage.microsoft.com/)에서 **그룹** &gt; **모든 모바일 장치**를 선택합니다.

         ![사용 중지 또는 초기화 작업 시작](../media/dev-sa-wipe.png)

        2.  **장치**를 선택하고 초기화하려는 모바일 장치의 이름을 선택합니다. 여러 장치를 선택하려면 Ctrl 키를 누른 채 장치를 클릭합니다.

2.  **사용 중지/초기화**를 선택합니다.

3.  장치를 사용 중지할지 묻는 확인 메시지가 나타납니다.

    -   회사 앱과 데이터만 제거하는 **선택적인 초기화**를 수행하려면 **예**를 선택합니다.

    -   모든 앱과 데이터를 지우고 장치를 공장 기본 설정으로 되돌리는 **전체 초기화**를 수행하려면 **사용 중지 전에 장치 초기화**를 선택합니다. 이 작업은 Windows 8.1을 제외한 모든 플랫폼에 적용됩니다. **전체 초기화로 제거된 데이터는 복구할 수 없습니다**.

장치가 켜져 있고 연결되어 있는 경우 초기화 명령이 모든 장치 유형에서 전파되는 데 15분 미만이 걸립니다.

## <a name="selective-wipe"></a>선택적 초기화

**선택적 초기화**는 해당되는 MAM(모바일 앱 관리) 데이터, 설정, 메일 프로필을 비롯한 회사 데이터를 장치에서 제거합니다. 선택적 초기화는 사용자의 개인적인 데이터를 장치에 남겨둡니다. 그리고 장치가 Intune에서 제거됩니다. 다음 표에서는 제거되는 데이터와 선택적 초기화 후 장치에 남아 있는 데이터에 대한 영향을 설명합니다. (테이블은 플랫폼별로 구성됩니다.)

**iOS**

|데이터 형식|iOS|
|-------------|-------|
|Intune에서 설치한 회사 앱 및 관련 데이터|앱이 제거됩니다. 회사 앱 데이터가 제거됩니다.<br /><br />모바일 앱 관리를 사용하는 Microsoft 앱의 앱 데이터가 제거됩니다. 앱은 제거되지 않습니다.|
|설정|Intune 정책에서 설정한 구성은 더 이상 적용되지 않으며 사용자는 설정을 변경할 수 있습니다.|
|Wi-Fi 및 VPN 프로필 설정|제거됩니다.|
|인증서 프로필 설정|인증서가 제거되고 해지됩니다.|
|관리 에이전트|관리 프로필이 제거됩니다.|
|메일|장치에서 메일을 제거 및 캐시한 Intune을 통해 프로비전되는 메일 프로필이 삭제됩니다. Microsoft Exchange를 온-프레미스에서 호스트하는 경우 메일 프로필 및 캐시된 메일이 제거되지 않습니다.|
|Outlook|iOS에 대해 Microsoft Outlook 앱에서 받은 메일이 제거됩니다.</br>예외: Exchange를 온-프레미스에서 호스트하는 경우 메일이 제거되지 않습니다.|
|AAD(Azure Active Directory) 가입 취소|AAD 레코드가 제거됩니다.|
|연락처 | 앱에서 기본 주소록에 직접 동기화된 연락처가 제거됩니다.  기본 주소록에서 다른 외부 소스에 동기화된 연락처는 초기화할 수 없습니다. <br /> <br />현재는 Outlook 앱만 지원됩니다.

**Android**

|데이터 형식|Android|Android Samsung KNOX Standard|
|-------------|-----------|------------------------|
|웹 링크|제거됩니다.|제거됩니다.|
|관리되지 않는 Google Play 앱|앱 및 데이터는 계속 설치되어 있습니다.|앱 및 데이터는 계속 설치되어 있습니다.|
|관리되지 않는 LOB(기간 업무) 앱|앱 및 데이터는 계속 설치되어 있습니다.|앱이 제거되고 그에 따라 앱의 로컬 데이터가 제거됩니다. 앱 외부(예: SD 카드)의 데이터는 제거되지 않습니다.|
|관리되는 Google Play 앱|앱 데이터가 제거됩니다. 앱은 제거되지 않습니다. 앱 외부(예: SD 카드)의 MAM 암호화로 보호되는 데이터는 암호화 및 사용할 수 없는 상태를 유지하지만 제거되지 않습니다.|앱 데이터가 제거됩니다. 앱은 제거되지 않습니다. 앱 외부(예: SD 카드)의 MAM 암호화로 보호되는 데이터는 암호화 상태를 유지하지만 제거되지 않습니다.|
|관리되는 LOB(기간 업무) 앱|앱 데이터가 제거됩니다. 앱은 제거되지 않습니다. 앱 외부(예: SD 카드)의 MAM 암호화로 보호되는 데이터는 암호화 및 사용할 수 없는 상태를 유지하지만 제거되지 않습니다.|앱 데이터가 제거됩니다. 앱은 제거되지 않습니다. 앱 외부(예: SD 카드)의 MAM 암호화로 보호되는 데이터는 암호화 및 사용할 수 없는 상태를 유지하지만 제거되지 않습니다.|
|설정|Intune 정책에서 설정한 구성은 더 이상 적용되지 않으며 사용자는 설정을 변경할 수 있습니다.|Intune 정책에서 설정한 구성은 더 이상 적용되지 않으며 사용자는 설정을 변경할 수 있습니다.|
|Wi-Fi 및 VPN 프로필 설정|제거됩니다.|제거됩니다.|
|인증서 프로필 설정|인증서가 해지되었지만 제거되지는 않았습니다.|인증서가 제거되고 해지되었습니다.|
|관리 에이전트|장치 관리자 권한이 해지됩니다.|장치 관리자 권한이 해지됩니다.|
|메일|Android에 대해 Microsoft Outlook 앱에서 받은 메일이 제거됩니다.|장치에서 메일을 제거 및 캐시한 Intune을 통해 프로비전되는 메일 프로필이 삭제됩니다. Microsoft Exchange를 온-프레미스에서 호스트하는 경우 메일 프로필 및 캐시된 메일이 제거되지 않습니다.|
|Outlook|iOS에 대해 Microsoft Outlook 앱에서 받은 메일이 제거됩니다.</br>예외: Exchange를 온-프레미스에서 호스트하는 경우 메일이 제거되지 않습니다.|iOS에 대해 Microsoft Outlook 앱에서 받은 메일이 제거됩니다.</br>예외: Exchange를 온-프레미스에서 호스트하는 경우 메일이 제거되지 않습니다.|
|AAD(Azure Active Directory) 가입 취소|AAD 레코드가 제거됩니다.|AAD 레코드가 제거됩니다.|
|연락처 | 앱에서 기본 주소록에 직접 동기화된 연락처가 제거됩니다.  기본 주소록에서 다른 외부 소스에 동기화된 연락처는 초기화할 수 없습니다. <br /> <br />현재는 Outlook 앱만 지원됩니다.|앱에서 기본 주소록에 직접 동기화된 연락처가 제거됩니다.  기본 주소록에서 다른 외부 소스에 동기화된 연락처는 초기화할 수 없습니다. <br /> <br />현재는 Outlook 앱만 지원됩니다.

**Windows**

|데이터 형식|Windows 8.1(MDM) 및 Windows RT 8.1|Windows RT|Windows Phone 8 및 Windows Phone 8.1|Windows 10|
|-------------|----------------------------------------------------------------|--------------|-----------------------------------------|--------|
|Intune에서 설치한 회사 앱 및 관련 데이터|EFS로 보호되는 파일에서 키를 해지하므로 사용자는 파일을 열 수 없습니다.|회사 앱은 제거하지 않습니다.|회사 포털을 통해 처음에 설치된 앱은 제거됩니다. 회사 앱 데이터가 제거됩니다.|앱이 제거되고 테스트용 로드 키가 제거됩니다.|
|설정|Intune 정책에서 설정한 구성은 더 이상 적용되지 않으며 사용자는 설정을 변경할 수 있습니다.|Intune 정책에서 설정한 구성은 더 이상 적용되지 않으며 사용자는 설정을 변경할 수 있습니다.|Intune 정책에서 설정한 구성은 더 이상 적용되지 않으며 사용자는 설정을 변경할 수 있습니다.|Intune 정책에서 설정한 구성은 더 이상 적용되지 않으며 사용자는 설정을 변경할 수 있습니다.|
|Wi-Fi 및 VPN 프로필 설정|제거됩니다.|제거됩니다.|지원 안 됨|제거됩니다.|
|인증서 프로필 설정|인증서가 제거되고 해지되었습니다.|인증서가 제거되고 해지되었습니다.|지원 안 됨|인증서가 제거되고 해지되었습니다.|
|메일|Windows 메일 및 첨부 파일용 메일 앱을 포함하는 EFS 지원 메일을 제거합니다.|지원 안 됨|장치에서 메일을 제거 및 캐시한 Intune을 통해 프로비전되는 메일 프로필이 삭제됩니다.|Windows 메일 및 첨부 파일용 메일 앱을 포함하는 EFS 지원 메일을 제거합니다. Intune을 통해 프로비전된 메일 계정을 제거합니다.</br>**예외**: Microsoft Exchange를 온-프레미스에서 호스트하는 경우 메일 계정이 제거되지 않습니다.|
|AAD(Azure Active Directory) 가입 취소|아니요.|아니요.|AAD 레코드가 제거됩니다.|해당 없음. Windows 10에서는 Azure Active Directory 가입 장치를 선택적으로 초기화할 수 없습니다.|

## <a name="wipe-encryption-file-system-efsenabled-content"></a>EFS(암호화 파일 시스템) 지원 콘텐츠 초기화
EFS로 암호화된 콘텐츠의 선택 초기화는 Windows 8.1 및 Windows RT 8.1에서 지원됩니다. 다음은 EFS 지원 콘텐츠의 선택적 초기화에 적용됩니다.

-   Intune 계정과 동일한 인터넷 도메인을 사용하는 EFS로 보호되는 앱 및 데이터만 선택적으로 초기화됩니다. 자세한 내용은 [장치 데이터 관리를 위한 Windows 선택적 초기화](http://technet.microsoft.com/library/dn486874.aspx)를 참조하세요.

-   EFS와 연결된 도메인에 대한 변경 사항이 있는 경우 새 도메인을 사용하는 앱 및 데이터를 선택적으로 초기화하기 전에 변경 사항을 적용하는 데 최대 48시간이 걸릴 수 있습니다.

-   Intune에 등록된 각 도메인이 초기화됩니다.

현재 EFS 선택 초기화가 지원되는 데이터 및 앱은 다음과 같습니다.

-   Windows용 메일 앱

-   클라우드 폴더

-   EFS로 암호화된 파일 및 폴더. 자세한 내용은 [파일 시스템 암호화에 대한 모범 사례](http://support.microsoft.com/kb/223316)를 참조하세요.

-   조직이 Active Directory에서 해당 ID를 관리하는 경우 EFS 선택적 초기화가 제대로 작동하려면 DirSync(디렉터리 동기화) 도구를 사용하여 정보를 AAD에 동기화해야 합니다.  DirSync에 대한 자세한 내용은 Azure Active Directory 설명서의 [디렉터리 동기화 시나리오](http://technet.microsoft.com/library/dn441212.aspx)를 참조하세요.

## <a name="monitor-retire-wipe-and-delete-actions"></a>사용 중지, 초기화 및 삭제 작업 모니터링
사용 중지, 초기화 또는 삭제된 장치에 대한 보고서를 가져오려면:

1.  [Intune 관리자 콘솔](https://manage.microsoft.com/)에서 **보고서** &gt; **장치 기록 보고서**를 선택합니다.

2.  보고서의 시작 및 종료 날짜를 입력한 다음 **보고서 보기**를 선택합니다.

이 보고서는 작업을 수행한 사용자를 보여 줍니다.

### <a name="see-also"></a>참고 항목
[장치 사용 중지](retire-devices-from-microsoft-intune-management.md)

[장치 데이터 관리를 위한 Windows 선택적 초기화](http://technet.microsoft.com/library/dn486874.aspx)



<!--HONumber=Nov16_HO2-->


