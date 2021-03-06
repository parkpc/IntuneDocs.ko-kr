<<<<<<< HEAD
---
title: "iOS 앱 간의 데이터 전송 관리 | Microsoft Intune"
description: "이 항목을 사용하여 iOS의 다음에서 열기 기능과 모바일 앱 관리 정책을 사용하여 앱 간의 데이터 전송을 관리하는 방법을 파악할 수 있습니다."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3a4515c1-b325-4ac1-9f0a-45ac27e00681
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a4f7a503417938eabb4334757dcf12a63f082fd3
ms.openlocfilehash: 080d861e8fd2d0140ffe5d9987032213ae0e4d4c

||||||| merged common ancestors
---
title: "iOS 앱 간의 데이터 전송 관리 | Microsoft Intune"
description: "이 항목을 사용하여 iOS의 다음에서 열기 기능과 모바일 앱 관리 정책을 사용하여 앱 간의 데이터 전송을 관리하는 방법을 파악할 수 있습니다."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3a4515c1-b325-4ac1-9f0a-45ac27e00681
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a4f7a503417938eabb4334757dcf12a63f082fd3
ms.openlocfilehash: 080d861e8fd2d0140ffe5d9987032213ae0e4d4c

=======
---
title: "iOS 앱 간의 데이터 전송 관리 | Microsoft Intune"
description: "이 항목을 사용하여 iOS의 다음에서 열기 기능과 모바일 앱 관리 정책을 사용하여 앱 간의 데이터 전송을 관리하는 방법을 파악할 수 있습니다."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3a4515c1-b325-4ac1-9f0a-45ac27e00681
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a4f7a503417938eabb4334757dcf12a63f082fd3
ms.openlocfilehash: 080d861e8fd2d0140ffe5d9987032213ae0e4d4c

>>>>>>> cbfbf499eccf5c2397decf9af598d6cda806b377

---

# <a name="manage-data-transfer-between-ios-apps-with-microsoft-intune"></a>Microsoft Intune으로 iOS 앱 간의 데이터 전송 관리
## <a name="manage-ios-apps"></a>IOS 앱 관리
회사 데이터 보호는 파일 전송이 관리하는 앱으로만 제한되도록 하는 작업을 포함합니다.  다음과 같은 방법으로 iOS 앱을 관리할 수 있습니다.

-   앱에 대한 MAM 정책을 구성하여 회사 데이터 손실을 방지하며, 앞으로 이러한 앱을 **정책 관리** 앱이라고 부릅니다.

-   **MDM 채널**을 사용하여 앱을 배포하고 관리할 수도 있습니다.  이렇게 하려면 MDM 솔루션에 장치를 등록해야 합니다. **정책 관리된** 앱 또는 다른 관리되는 앱일 수 있습니다.

iOS 장치의 **관리에서 열기** 기능은 **MDM 채널**을 통해 장치에 배포된 앱 간에만 파일 전송이 발생하도록 제한할 수 있습니다. 관리에서 열기 제한 사항은 구성 설정에서 설정되며 MDM 소프트웨어를 사용하여 배포됩니다.  사용자가 배포된 앱을 설치하면 설정한 제한 사항이 적용됩니다.
##  <a name="using-mam-with-ios-apps"></a>iOS 앱과 함께 MAM 사용
MAM(모바일 앱 관리) 정책을 **관리에서 열기** 기능과 함께 사용하여 회사 데이터를 다음과 같은 방법으로 보호할 수 있습니다.

-   **직원 소유 장치는 MDM 솔루션에서 관리되지 않음:** MAM 정책 설정을 **앱에서 관리되는 앱으로만 데이터 전송 허용**으로 설정할 수 있습니다. 최종 사용자가 정책 관리된 앱이 아닌 앱에서 보호된 파일을 여는 경우에는 파일을 읽을 수 없습니다.

-   **Intune에서 관리되는 장치:** Intune에 등록된 장치의 경우 MAM 정책이 있는 앱과 Intune을 통해 배포된 다른 관리되는 iOS 앱 간의 데이터 전송은 자동으로 허용됩니다. MAM 정책이 있는 앱 간에 데이터 전송을 허용하려면 **앱에서 관리되는 앱으로만 데이터 전송 허용** 설정을 사용하도록 설정합니다. **관리에서 열기** 기능을 사용하여 Intune을 통해 배포된 앱 간의 데이터 전송을 제어할 수 있습니다.   

-   **타사 MDM 솔루션으로 관리되는 장치:** iOS **관리에서 열기** 기능을 사용하여 관리되는 앱으로만 데이터 전송을 제한할 수 있습니다.
타사 MDM 솔루션을 사용하여 배포하는 앱도 Intune에서 구성한 MAM 정책과 연결되도록 하려면 [사용자 UPN 설정 구성](#configure-user-upn-setting) 연습에서 설명한 대로 사용자 UPN 설정을 구성해야 합니다.  사용자 UPN 설정으로 앱을 배포하면 최종 사용자가 회사 계정을 사용하여 로그인할 때 MAM 정책이 앱에 적용됩니다.

> [!IMPORTANT]
> 사용자 UPN 설정은 타사 MDM으로 관리되는 장치에 배포된 앱에만 필요합니다.  Intune으로 관리되는 장치의 경우 이 설정이 필요하지 않습니다.

## <a name="configure-user-upn-setting"></a>사용자 UPN 설정 구성
이 구성은 타사 MDM 솔루션으로 관리되는 장치에 필요합니다. 아래에 설명된 절차는 UPN 설정 및 결과로 생성되는 최종 사용자 환경을 구현하는 방법에 대한 일반적인 흐름입니다.


1.  Azure 포털에서 iOS 플랫폼에 대한 [모바일 앱 관리 정책을 구성](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)합니다. 회사 요구 사항에 따라 정책 설정을 구성하고 이 정책이 있어야 하는 앱을 선택합니다.

2.  3단계 및 4단계에서 설명한 설정을 사용하여 **타사 MDM 솔루션을 통해** 관리할 앱 및 메일 프로필을 배포합니다.

3.  다음과 같은 앱 구성 설정으로 앱을 배포합니다. key=IntuneMAMUPN, Value=<username@company.com>[예: ‘IntuneMAMUPN’, ‘jondoe@microsoft.com’]

4.  등록된 장치에 다음에서 열기 관리 정책을 배포합니다.

### <a name="example-end-user-experience"></a>최종 사용자 환경의 예

1.  최종 사용자가 장치에 Microsoft Word 앱을 설치합니다.

2.  최종 사용자가 관리되는 기본 메일 앱을 시작하여 메일에 액세스합니다.

3.  최종 사용자가 Microsoft Word에서 기본 메일의 문서를 열려고 합니다.

4.  Word 앱이 시작되면 회사 계정을 사용하여 로그인하라는 메시지가 최종 사용자에게 표시됩니다.  메시지가 표시될 때 최종 사용자가 입력하는 계정이 Microsoft Word 앱에 대한 앱 구성 설정에서 지정한 계정과 일치해야 이와 같이 진행됩니다.

    > [!NOTE]
    > 최종 사용자는 개인적인 작업을 수행하기 위해 Word에 다른 개인 계정을 추가할 수 있으며 개인 컨텍스트에서 Word 앱을 사용하는 경우 이러한 개인 계정에는 MAM 정책이 적용되지 않습니다.

5.  로그인이 성공하면 앱 정책 설정이 Word 앱에 적용됩니다.

6.  이제 데이터 전송이 성공하고 앱의 문서에 회사 ID로 태그가 지정됩니다. 또한 데이터가 회사 컨텍스트에서 처리되고 정책 설정이 그에 따라 적용됩니다.

### <a name="see-also"></a>참고 항목
[Microsoft Intune에서 모바일 앱 관리 정책을 사용하여 앱 데이터 보호](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Nov16_HO1-->


