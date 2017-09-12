---
title: "Intune에 Windows 스토어 앱을 추가하는 방법"
titleSuffix: Azure portal
description: "Intune에 Windows 스토어 앱을 추가하는 방법을 알아봅니다.\""
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 07241b6d-86d8-4abb-83a2-3fc5feae5788
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f10da996f8587e63320e31ae57e88a5f14f3f9c2
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/09/2017
---
# <a name="how-to-add-windows-store-apps-to-microsoft-intune"></a>Microsoft Intune에 Windows 스토어 앱을 추가하는 방법

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


1. Azure 포털에 로그인합니다.
2. **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
3. **Intune** 블레이드에서 **앱 관리**를 선택합니다.
4. **모바일 앱** 워크로드에서 **관리** > **앱**을 선택합니다.
5. 앱 목록 위에서 **추가**를 선택합니다.
6. **앱 추가** 블레이드에서 **앱 정보**를 선택합니다.
7. **앱 편집** 블레이드에서 다음 정보를 구성합니다. 작업이 끝나면 **추가**를 클릭합니다. 선택한 앱에 따라 이 블레이드의 일부 값이 자동으로 채워질 수 있습니다.
    - **앱 이름** - 회사 포털에 표시되는 앱의 이름을 입력합니다. 사용하는 모든 앱 이름이 고유한지 확인합니다. 같은 앱 이름을 두 번 사용하는 경우에는 회사 포털에서 앱 중 하나만 사용자에게 표시됩니다.
    - **앱 설명** - 앱에 대한 설명을 입력합니다. 이 설명은 회사 포털에서 사용자에게 표시됩니다.
    - **게시자** - 앱의 게시자 이름을 입력합니다.
    - **앱 스토어 URL** - 만들려는 앱의 앱 스토어 URL을 입력합니다.
    - **최소 운영 체제** - 목록에서 앱을 설치할 수 있는 최소 운영 체제 버전을 선택합니다. 이전 버전의 운영 체제를 사용하는 장치에 앱을 할당할 경우 앱이 설치되지 않습니다.
    - **범주(선택 사항)** - 기본 제공 앱 범주 중 하나 이상 또는 사용자가 만든 범주를 선택합니다. 이렇게 하면 사용자가 회사 포털을 찾아볼 때 앱을 더 쉽게 찾을 수 있습니다.
    - **회사 포털에서 이 항목을 추천 앱으로 표시** - 사용자가 앱을 찾을 때 회사 포털의 기본 페이지에서 앱이 눈에 띄게 표시됩니다.
    - **정보 URL** - 필요에 따라 이 앱에 대한 정보를 포함하는 웹 사이트의 URL을 입력합니다. URL은 회사 포털에서 사용자에게 표시됩니다.
    - **개인 정보 URL** - 필요에 따라 이 앱에 대한 개인 정보 관련 정보를 포함하는 웹 사이트의 URL을 입력합니다. URL은 회사 포털에서 사용자에게 표시됩니다.
    - **개발자** - 필요에 따라 앱 개발자의 이름을 입력합니다.
    - **소유자** - 필요에 따라 이 앱의 소유자 이름을 입력합니다(예: **HR 부서**).
    - **메모** - 이 앱과 연결할 모든 메모를 입력합니다.
    - **아이콘 업로드** - 앱과 연결할 아이콘을 업로드합니다. 사용자가 회사 포털을 찾아볼 때 이 아이콘이 앱과 함께 표시됩니다.
8. 작업을 마치면 **앱 추가** 블레이드에서 **저장**을 선택합니다.

만든 앱이 앱 목록에 표시됩니다. 이 목록에서 선택한 그룹에 앱을 할당할 수 있습니다. 도움말은 [그룹에 앱을 할당하는 방법](apps-deploy.md)을 참조하세요.

## <a name="manually-assign-windows-10-company-portal-app"></a>Windows 10 회사 포털 앱 수동 할당
최종 사용자는 Microsoft 스토어에서 회사 포털 앱을 설치하여 장치를 관리하고 앱을 설치할 수 있습니다. 그러나 비즈니스 요구에 따라 회사 포털 앱을 할당해야 하는 경우에는 비즈니스용 Microsoft 스토어와 Intune을 통합하지 않았더라도 Intune에서 곧바로 Windows 10 회사 포털 앱을 수동으로 할당할 수 있습니다.

 > [!NOTE]
 > 이 옵션을 사용하려면 앱 업데이트가 릴리스될 때마다 수동 업데이트를 할당해야 합니다.

1. 자신의 계정으로 [비즈니스용 Microsoft 스토어](https://www.microsoft.com/business-store)에 로그인하고 **오프라인 라이선스** 버전의 회사 포털 앱을 가져옵니다.  
2. 앱을 가져왔으면 **인벤토리** 페이지에서 앱을 선택합니다.  
3. **플랫폼**으로 **Windows 10 all devices**(Windows 10 모든 장치)를 선택한 다음 적절한 **아키텍처**를 선택하고 다운로드합니다. 이 앱에는 앱 라이선스 파일이 필요 없습니다.
![Windows 10 모든 장치 및 아키텍처 X86 패키지 다운로드 세부 정보를 보여 주는 이미지](./media/Win10CP-all-devices.png)
4. "Required Frameworks"(필요한 프레임워크)에 나온 모든 패키지를 다운로드합니다. x86, x64 및 ARM 아키텍처에 대해 수행해야 하므로 아래와 같이 총 9개의 패키지가 됩니다.

![다운로드할 종속성 파일의 이미지 ](./media/Win10CP-dependent-files.png)
5. 회사 포털 앱을 Intune에 업로드하기 전에 패키지를 포함하는 폴더(예: C:&#92;Company Portal)를 다음과 같은 방법으로 만듭니다.
  1. C:\Company Portal에 회사 포털 패키지를 배치합니다. 이 위치에 Dependencies 하위 폴더도 만듭니다.  
  ![APPXBUN 파일과 함께 저장된 Dependencies 폴더의 이미지](./media/Win10CP-Dependencies-save.png)
  2. Dependencies 폴더에 9개의 종속성 패키지를 배치합니다.  
  종속성을 이 형식으로 배치하지 않는 경우 Intune은 패키지 업로드 도중에 패키지를 인식 및 업로드할 수 없습니다. 이에 따라 업로드에 실패하고 다음과 같은 오류가 표시됩니다.  
  ![이 소프트웨어 설치 관리자의 Windows 앱 종속성이 응용 프로그램 폴더에 없습니다. 이 응용 프로그램을 계속 만들고 할당할 수 있지만 누락된 Windows 앱 종속성이 제공될 때까지 실행되지 않습니다.](./media/Win10CP-error-message.png)
6. Intune으로 돌아간 후 회사 포털 앱을 새 앱으로 업로드합니다. 원하는 대상 사용자 집합에게 필수 앱으로 할당합니다.  

Intune에서 유니버설 앱의 종속성을 처리하는 방식에 대한 자세한 내용은 [Deploying an appxbundle with dependencies via Microsoft Intune MDM(Microsoft Intune MDM을 통해 종속성이 포함된 appxbundle 배포)](https://blogs.technet.microsoft.com/configmgrdogs/2016/11/30/deploying-an-appxbundle-with-dependencies-via-microsoft-intune-mdm/)을 참조하세요.  

### <a name="how-do-i-update-the-company-portal-on-my-users-devices-if-they-have-already-installed-the-older-apps-from-the-store"></a>사용자가 이미 스토어에서 이전 앱을 설치한 경우 어떻게 사용자의 장치에서 회사 포털을 업데이트하나요?
사용자가 이미 스토어에서 Windows 8.1 또는 Windows Phone 8.1 회사 포털 앱을 설치한 경우 관리자나 사용자의 별도 조치가 필요 없이 앱이 자동으로 새 버전으로 업데이트됩니다. 업데이트가 이루어지지 않는 경우 사용자에게 장치에서 스토어 앱에 대해 자동 업데이트를 활성화했는지 확인하도록 요청합니다.   

### <a name="how-do-i-upgrade-my-sideloaded-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>사이드로드한 Windows 8.1 회사 포털 앱을 Windows 10 회사 포털 앱으로 어떻게 업그레이드하나요?
권장되는 마이그레이션 경로는 할당 작업을 "제거"로 설정하여 Windows 8.1 회사 포털 앱의 할당을 삭제하는 것입니다. 이 작업이 완료되면 위의 옵션 중 하나를 사용하여 Windows 10 회사 포털 앱을 할당할 수 있습니다.  

앱을 사이드로드해야 하며 Symantec 인증서로 서명하지 않고 Windows 8.1 회사 포털을 할당한 경우에는 위의 Intune 섹션을 통해 직접 할당의 단계를 따라 업그레이드를 완료합니다.

앱을 사이드로드해야 하며 Symantec 코드 서명 인증서로 Windows 8.1 회사 포털을 서명 및 할당한 경우에는 아래 섹션의 단계를 따릅니다.  

### <a name="how-do-i-upgrade-my-signed-and-sideloaded-windows-phone-81-company-portal-app-or-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>서명 및 사이드로드된 Windows Phone 8.1 회사 포털 앱이나 Windows 8.1 회사 포털 앱을 어떻게 Windows 10 회사 포털 앱으로 업그레이드하나요?
권장되는 마이그레이션 경로는 할당 작업을 "제거"로 설정하여 Windows Phone 8.1 회사 포털 앱 또는 Windows 8.1 회사 포털 앱의 기존 할당을 삭제하는 것입니다. 이 작업이 완료되면 Windows 10 회사 포털 앱을 정상적으로 할당할 수 있습니다.  

이 작업을 마치지 않는 경우에는 업그레이드 경로를 준수하도록 Windows 10 회사 포털 앱을 적절하게 업데이트하고 서명해야 합니다.  

이 방법으로 Windows 10 회사 포털 앱이 서명 및 할당된 경우에는 스토어에서 사용할 수 있는 새 앱 업데이트 각각에 대해 이 프로세스를 반복해야 합니다. 앱은 스토어가 업데이트될 때 자동으로 업데이트되지 않습니다.  

이러한 방식으로 앱을 서명하고 할당하는 방법은 다음과 같습니다.

1. [https://aka.ms/win10cpscript](https://aka.ms/win10cpscript)에서 Microsoft Intune Windows 10 회사 포털 앱 서명 스크립트를 다운로드합니다.  이 스크립트가 작동하려면 호스트 컴퓨터에 Windows 10용 Windows SDK가 설치되어야 있어야 합니다. Windows 10용 Windows SDK를 다운로드하려면 [https://go.microsoft.com/fwlink/?LinkId=619296](https://go.microsoft.com/fwlink/?LinkId=619296) 페이지를 방문하세요.
2. 위에서 설명한 대로 비즈니스용 Microsoft 스토어에서 Windows 10 회사 포털 앱을 다운로드합니다.  
3. Windows 10 회사 포털 앱을 서명하려면 스크립트 헤더에 입력 매개 변수를 자세히 지정하여 스크립트를 실행합니다(아래에 추출됨). 종속성은 스크립트에 전달할 필요가 없습니다. 앱을 Intune 관리 콘솔에 업로드할 때만 필요합니다.

|매개 변수 | 설명|
| ------------- | ------------- |
|InputWin10AppxBundle |원본 appxbundle 파일이 위치한 경로입니다. |
|OutputWin10AppxBundle |서명된 appxbundle 파일의 출력 경로입니다.  Win81Appx는 Windows 8.1 또는 Windows Phone 8.1 회사 포털(.APPX) 파일이 위치한 경로입니다.|
|PfxFilePath |Symantec Enterprise 모바일 코드 서명 인증서(.PFX) 파일의 경로입니다. |
|PfxPassword| Symantec Enterprise 모바일 코드 서명 인증서의 암호입니다. |
|PublisherId |엔터프라이즈의 게시자 ID입니다. 없는 경우 Symantec Enterprise 모바일 코드 서명 인증서의 '제목' 필드를 사용합니다.|
|SdkPath | Windows 10용 Windows SDK의 루트 폴더에 대한 경로입니다. 이 인수는 선택 사항이며 기본적으로 ${env:ProgramFiles(x86)}\Windows Kits\10입니다.|
실행이 완료되면 스크립트는 서명된 버전의 Windows 10 회사 포털 앱을 출력합니다. 그러면 서명된 버전의 앱을 Intune 통해 LOB 앱으로 할당할 수 있으며, 현재 할당된 버전이 이 새 앱으로 업그레이드됩니다.  
