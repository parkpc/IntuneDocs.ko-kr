---
title: 등록된 장치용 앱 추가
description: 앱을 배포하려면 먼저 Intune에 추가해야 합니다. 그런 후에는 이러한 앱을 배포하고 관리할 수 있는 Intune 콘솔에서 사용할 수는 있습니다.
keywords: ''
author: mattbriggs
ms.author: mabrigg
manager: dougeby
ms.date: 01/11/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f5b1f1ae-f177-450a-9af9-936a02d052e3
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9f5fec22a17eef39819b38567793a2f579815e59
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2018
---
# <a name="add-apps-for-enrolled-devices-to-intune"></a>Intune에 등록된 장치용 앱 추가

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

앱을 배포하거나 관리하려면 먼저 Microsoft Intune에 추가해야 합니다. 이 항목에서는 등록된 장치용 앱을 추가하는 방법을 보여 줍니다.


> [!IMPORTANT]
> 이 항목의 정보를 참조하면 등록된 장치 및 등록된 Windows PC에 배포하려는 앱을 추가할 수 있습니다. Intune 클라이언트 소프트웨어를 사용하여 관리하는 Windows PC에 앱을 추가하려는 경우에는 [Microsoft Intune에서 Windows PC에 앱 추가](add-apps-for-windows-pcs-in-microsoft-intune.md)를 참조하세요.

## <a name="add-the-app"></a>앱 추가
Intune 소프트웨어 게시자를 사용하여 앱 속성을 구성한 다음 해당하는 경우 클라우드 저장소 공간에 앱을 업로드합니다. 다음 절차를 따릅니다.

1.  [Microsoft Intune 관리자 콘솔](https://manage.microsoft.com)에서 **앱** &gt; **앱 추가**를 선택하여 Intune 소프트웨어 게시자를 시작합니다.

    > [!TIP]
    > 게시자를 시작하기 전에 Intune 사용자 이름과 암호를 입력해야 할 수도 있습니다.

2.  게시자의 **소프트웨어 설치** 페이지에서 **장치에 이 소프트웨어를 사용할 수 있는 방법 선택**에 다음 옵션 중 하나를 선택합니다.
    - **소프트웨어 설치 관리자**는 **.msi** 확장명을 사용하여 앱에 대해 다음을 수행합니다.
        - **소프트웨어 설치 관리자 파일 형식 선택**. 배포할 소프트웨어의 유형을 나타냅니다. 예를 들어 iOS 앱을 설치하려는 경우 **iOS용 앱 패키지(&#42;.ipa 파일)**를 선택합니다.
        - **소프트웨어 설치 파일의 위치 지정**. 설치 파일의 위치를 입력하거나 **찾아보기**를 선택하여 목록에서 위치를 선택합니다.
        - **동일한 폴더의 추가 파일 및 하위 폴더 포함**. 이 옵션은 **Windows Installer** 파일 형식에만 적용됩니다.<br>Windows Installer를 사용하는 일부 소프트웨어의 경우 보통 설치 파일과 같은 폴더에 있는 지원 파일이 필요합니다. 이러한 파일도 배포하려는 경우 이 옵션을 선택합니다.<br>이 설치 유형에서는 클라우드 저장 공간 중 일부를 사용합니다.

  -   **외부 링크**는 앱 스토어에 대한 링크를 지정하여 만들려는 앱에 대해 다음 작업을 수행합니다.

        - **URL 지정**. URL을 다음 중 하나로 지정합니다.
            - 배포할 앱의 앱 스토어 URL. 예를 들어 Android용 Microsoft 원격 데스크톱 앱을 배포하려는 경우 **https://play.google.com/store/apps/details?id=com.microsoft.rdc.android**를 지정합니다.<br>앱의 URL을 확인하려면 검색 엔진을 사용하여 앱이 포함된 스토어 페이지를 찾습니다. 예를 들어 원격 데스크톱 앱을 찾으려는 경우 **Microsoft 원격 데스크톱 Android**를 검색할 수 있습니다.
            - 웹 사이트. Intune은 장치 사이트에 바로 가기 아이콘을 배포합니다(웹 클립이라고도 함).
            - 웹앱. Intune은 앱에 대한 바로 가기 아이콘을 장치에 배포합니다.
        - **이 링크를 열려면 Managed Browser가 필요(Android 및 iOS에만 해당)**. 웹 사이트 또는 웹앱에 대한 링크를 사용자에게 배포할 경우 Intune 관리 브라우저에서만 링크를 열 수 있습니다. 이 브라우저는 장치에 설치되어 있어야 합니다.<br>Managed Browser에 대한 자세한 내용은 [Microsoft Intune에서 관리 브라우저 정책을 사용하여 인터넷 액세스 관리](manage-internet-access-using-managed-browser-policies.md) 항목을 참조하세요.<br>이 설치 유형에서는 클라우드 저장 공간을 사용하지 않습니다.

  -   **앱 스토어에서 관리되는 iOS 앱**은 MAM(모바일 응용 프로그램 관리) 정책을 사용하여 관리하려는 iTunes 스토어의 무료 앱에 대해 다음을 수행합니다.

        - **URL 지정**. 배포할 앱의 앱 스토어 URL을 입력합니다. 예를 들어 iOS용 Microsoft 작업 폴더 앱을 배포하려는 경우 **https://itunes.apple.com/us/app/work-folders/id950878067?mt=8**을 지정합니다.<br>이 설치 유형에서는 클라우드 저장 공간을 사용하지 않습니다.

        예를 들어 iTunes 스토어의 Microsoft Word 앱을 장치에 배포하려는 경우 페이지는 다음과 같습니다.

        ![Intune 소프트웨어 게시자](./media/publisher-for-mobile.png)

> [!NOTE]
> 스토어에서 앱을 추가하고 배포하는 경우 앱을 설치할 수 있도록 최종 사용자에게 해당 스토어의 계정이 있어야 합니다.

3.  **소프트웨어 설명** 페이지에서 다음 항목을 구성합니다.

    > [!TIP]
    > 사용하는 설치 관리자 유형에 따라 이러한 값 중 일부는 자동으로 입력되어 있을 수 있습니다.

    - **게시자**. 앱 게시자의 이름을 입력합니다.
    - **이름**. 회사 포털에 표시되는 앱의 이름을 입력합니다.<br>사용하는 모든 앱 이름이 고유한지 확인합니다. 같은 앱 이름을 두 번 사용하는 경우에는 회사 포털에서 앱 중 하나만 사용자에게 표시됩니다.
    - **설명**. 앱에 대한 설명을 입력합니다. 이 설명은 회사 포털에서 사용자에게 표시됩니다.
    - **소프트웨어 정보 URL**. **소프트웨어 설치 관리자**를 선택한 경우에만 사용 가능합니다. 필요에 따라 이 앱에 대한 정보를 포함하는 웹 사이트의 URL을 입력합니다. URL은 회사 포털에서 사용자에게 표시됩니다.
    - **개인정보취급방침 URL**. **소프트웨어 설치 관리자**를 선택한 경우에만 사용 가능합니다. 필요에 따라 이 앱에 대한 개인정보 관련 정보를 포함하는 웹 사이트의 URL을 입력합니다. URL은 회사 포털에서 사용자에게 표시됩니다.
    - **범주**(선택 사항). 기본 제공 앱 범주 중 하나를 선택합니다. 이렇게 하면 사용자가 회사 포털을 찾아볼 때 앱을 더 쉽게 찾을 수 있습니다.
    - **회사 포털에서 이 항목을 추천 앱 및 하이라이트로 표시**. 사용자가 앱을 찾아볼 때 회사 포털의 기본 페이지에 앱을 쉽게 확인할 수 있도록 표시합니다.
    - **아이콘**(선택 사항). 앱과 연결할 아이콘을 업로드합니다. 사용자가 회사 포털을 찾아볼 때 이 아이콘이 앱과 함께 표시됩니다.

        이 예제에서는 iOS용 Microsoft Word 앱에 대한 설명을 구성했습니다.

        ![소프트웨어 설명 예제](./media/ios-software-description.png)

4.  **요구 사항** 페이지에서 장치에 앱을 설치하려면 충족해야 하는 요구 사항을 선택합니다. 예를 들어 iOS용 앱 패키지의 경우 필요한 최소 iOS 버전을 선택할 수 있습니다. 또한 iPhone 또는 iPad와 같이 선택해야 하는 장치의 종류를 선택할 수 있습니다.

    > [!TIP]
    > **요구 사항** 페이지는 일부 앱 유형에 대해서만 표시됩니다.

5.  **Windows Installer** 파일 형식을 선택하면 추가 마법사 페이지가 표시됩니다. 이 파일 형식은 Windows 10 이상을 실행하는, Intune에 등록된 PC에 소프트웨어를 배포할 때 사용됩니다.

6.  **요약** 페이지에서 지정한 정보를 검토합니다. 준비가 되면 **업로드**를 선택합니다.

7.  **닫기**를 선택하여 완료합니다.

앱이 **앱** 작업 영역의 **앱** 노드에 표시됩니다.

## <a name="example---deploying-msi-applications-to-windows-10-devices"></a>예 - Windows 10 장치에 .msi 응용 프로그램 배포
이 4분 분량의 비디오에서는 Windows 10을 실행하는 등록 장치에 Windows Installer(.msi) 응용 프로그램을 배포하는 방법에 대해 설명합니다.<br><br>

<iframe src="https://channel9.msdn.com/Series/How-to-Control-the-Uncontrolled/6--How-to-Deploy-MSI-Applications-to-Windows-10-Using-Intune-and-Mobile-Device-Management-MDM/player" width="640" height="360" allowFullScreen frameBorder="0"></iframe>

## <a name="next-steps"></a>다음 단계

앱을 만들면 다음 단계는 배포입니다. 자세한 내용은 [Microsoft Intune에서 앱 배포](deploy-apps.md)를 참조하세요.
