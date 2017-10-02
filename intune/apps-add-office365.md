---
title: "Intune을 사용하여 Windows 10 장치에 Office 365 ProPlus 앱 설치"
titlesuffix: Azure portal
description: "Intune을 사용하여 Office 365 앱을 Windows 10 장치에 더 간편하게 설치하는 방법을 알아봅니다."
keywords: 
author: dougeby
ms.author: dougeby
manager: angrobe
ms.date: 08/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3292671a-5f5a-429e-90f7-b20019787d22
ms.reviewer: aiwang
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f4e3ad7b68be723e0cab7b541b0ae7e3cc858c99
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2017
---
# <a name="how-to-assign-office-365-proplus-2016-apps-to-windows-10-devices-with-microsoft-intune"></a>Microsoft Intune을 사용하여 Office 365 ProPlus 2016 앱을 Windows 10 장치에 할당하는 방법

이 앱 형식을 통해 관리하는 Windows 10 실행 장치에 Office 365 ProPlus 2016 앱을 쉽게 할당할 수 있습니다. Microsoft Project Online 데스크톱 클라이언트 및 Microsoft Visio Pro for Office 365에 대한 라이선스가 있는 경우 관련 앱을 설치할 수 있습니다. 원하는 앱이 Intune 콘솔의 앱 목록에 하나의 앱으로 표시됩니다.


## <a name="before-you-start"></a>시작하기 전에

>[!IMPORTANT]
>이 Office 설치 방법은 Microsoft Office의 다른 버전이 장치에 설치된 경우에만 지원됩니다.

- 이러한 앱을 배포할 장치에서 Windows 10 크리에이터스 업데이트 이상을 실행하고 있어야 합니다.
- Intune에서는 Office 365 ProPlus 2016 제품군에서 Office 앱을 추가하는 기능만 지원합니다.
- Intune에서 앱 패키지를 설치할 때 Office 앱이 열리면 저장되지 않은 파일에서 최종 사용자의 데이터가 손실될 수 있습니다.
- 이 설치 방법은 Windows 10S 장치에서 지원되지 않습니다.
- Intune은 Windows 스토어의 365 데스크톱 앱(Office Centennial 앱)을 이미 Intune으로 Office 365 앱을 배포한 장치에 설치하는 것을 지원하지 않습니다. 이 구성을 설치할 경우 데이터 손실이나 손상이 발생할 수 있습니다.


## <a name="get-started"></a>시작

1.  Azure 포털에 로그인합니다.
2.  **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다.
3.  **Intune** 블레이드에서 **Mobile Apps**를 선택합니다.
4.  **모바일 앱** 워크로드에서 **관리** > **앱**을 선택합니다.
5.  앱 목록 위에서 **추가**를 선택합니다.
6.  **앱 추가** 블레이드에서 **Office 365 ProPlus 제품군(Windows 10)**을 선택합니다.

## <a name="configure-the-app-suite"></a>앱 패키지 구성

이 단계에서 장치에 할당할 Office 앱을 선택합니다.

1.  **앱 추가** 블레이드에서 **앱 패키지 구성**을 선택합니다.
2.  **앱 패키지 구성** 블레이드에서 장치에 할당할 표준 Office 앱을 선택합니다. 또한 Microsoft Project Online 데스크톱 클라이언트 및 Microsoft Visio Pro for Office 365에 대한 라이선스가 있는 경우 관련 앱을 설치할 수 있습니다.
3.  작업이 끝나면 **확인**을 클릭합니다.

>[!IMPORTANT]
> 앱 패키지를 만든 후에는 해당 속성을 편집할 수 없습니다. 다른 속성을 구성하려면 앱 패키지를 삭제하고 새 앱 패키지를 만듭니다.

## <a name="configure-app-information"></a>앱 정보 구성

이 단계에서는 앱 패키지에 대한 정보를 제공합니다. 이 정보를 사용하여 Intune에서 앱 패키지를 식별하고 사용자가 회사 포털 앱에서 앱 패키지를 찾을 수도 있습니다.

1.  **앱 추가** 블레이드에서 **앱 패키지 정보**를 선택합니다.
2.  **앱 패키지 정보** 블레이드에서 다음 정보를 지정합니다. 
    - **패키지 이름** - 회사 포털에 표시되는 앱 패키지의 이름을 입력합니다. 사용하는 모든 패키지 이름이 고유한지 확인합니다. 같은 앱 패키지 이름이 두 번 나타나는 경우 앱 중 하나만 회사 포털에서 사용자에게 표시됩니다.
    - **패키지 설명** - 앱 패키지에 대한 설명을 입력합니다. 예를 들어 포함하도록 선택한 앱을 나열할 수 있습니다.
    - **게시자** - 앱의 게시자 이름을 입력합니다.
    - **범주** - 필요한 경우 기본 제공 앱 범주 중 하나 이상 또는 사용자가 만든 범주를 선택합니다. 이렇게 하면 사용자가 회사 포털을 찾아볼 때 앱 패키지를 더 쉽게 찾을 수 있습니다.
    - **회사 포털에서 이 항목을 추천 앱으로 표시** - 사용자가 앱을 찾을 때 회사 포털의 기본 페이지에서 앱 패키지가 눈에 띄게 표시됩니다.
    - **정보 URL** - 필요에 따라 이 앱에 대한 정보를 포함하는 웹 사이트의 URL을 입력합니다. URL은 회사 포털에서 사용자에게 표시됩니다.
    - **개인 정보 URL** - 필요에 따라 이 앱에 대한 개인 정보 관련 정보를 포함하는 웹 사이트의 URL을 입력합니다. URL은 회사 포털에서 사용자에게 표시됩니다.
    - **개발자** - 필요에 따라 앱 개발자의 이름을 입력합니다.
    - **소유자** - 필요에 따라 이 앱의 소유자 이름을 입력합니다(예: **HR 부서**).
    - **메모** - 이 앱과 연결할 모든 메모를 입력합니다.
    - **아이콘 업로드** - 사용자가 회사 포털을 찾아볼 때 이 아이콘이 앱과 함께 표시됩니다.
3.  작업이 끝나면 **확인**을 클릭합니다.

## <a name="configure-app-settings"></a>앱 설정 구성

이 단계에서는 앱 패키지에 대한 설치 옵션을 구성합니다. 설정은 패키지에 추가한 모든 앱에 적용됩니다.

1.  **앱 추가** 블레이드에서 **앱 패키지 설정**을 선택합니다.
2.  **앱 패키지 설정** 블레이드에서 다음 정보를 지정합니다. 
    - **Office 버전** - Office의 32비트 또는 64비트 비전을 할당할지 여부를 선택합니다. 32비트 버전은 32비트 및 64비트 장치에 모두 설치할 수 있지만, 64비트 버전은 64비트 장치에만 설치할 수 있습니다.
    - **업데이트 채널** - 장치에서 Office를 업데이트하는 방법을 선택합니다. 다양한 업데이트 채널에 대한 자세한 내용은 Office 365 ProPlus의 업데이트 채널 개요를 참조하세요. 다음 중에서 선택합니다. 
        - **현재**
        - **지연**
        - **첫 번째 릴리스 현재**
        - **첫 번째 릴리스 지연**
    - **Automatically accept the app end user license agreement**(앱 최종 사용자 사용권 계약 자동으로 동의) - 최종 사용자가 사용권 계약에 동의하도록 요구하지 않으려면 이 옵션을 선택합니다. Intune에서 자동으로 계약에 동의합니다.
    - **공유 컴퓨터 인증 사용** - 여러 사용자가 컴퓨터를 공유할 경우 공유 컴퓨터 인증이 사용됩니다. 자세한 내용은 Office 365 ProPlus의 공유 컴퓨터 인증 개요를 참조하세요.
    - **언어** - Office는 최종 사용자 장치에 Windows와 함께 설치된 지원 언어로 자동으로 설치됩니다. 앱 패키지와 함께 추가 언어를 설치하려면 이 옵션을 선택합니다.

>[!IMPORTANT]
> 앱 패키지를 만든 후에는 해당 속성을 편집할 수 없습니다. 다른 속성을 구성하려면 앱 패키지를 삭제하고 새 앱 패키지를 만듭니다.

## <a name="finish-up"></a>끝내기

작업을 마치면 **앱 추가** 블레이드에서 **저장**을 선택합니다. 만든 앱은 앱 목록에 표시됩니다.

## <a name="error-codes-when-installing-the-app-suite"></a>앱 패키지 설치 시 오류 코드

다음 표에는 발생할 수 있는 일반적인 오류 코드와 해당 의미가 나와 있습니다.

### <a name="status-for-office-csp"></a>Office CSP 상태: 

||||
|-|-|-|
|상태|단계|설명|
|1460(ERROR_TIMEOUT)|다운로드|Office 배포 도구를 다운로드하지 못함|    
|13(ERROR_INVALID_DATA)|-|다운로드된 Office 배포 도구의 서명을 확인할 수 없음| 
|CertVerifyCertificateChainPolicy의 오류 코드|-|다운로드된 Office 배포 도구의 인증 확인 실패|    
|997|WIP|설치| 
|0|설치 후|설치 성공|    
|1603(ERROR_INSTALL_FAILURE)|-|필수 구성 요소 확인 실패, 예:<br>- SxS(2016 MSI 설치 시 설치를 시도함)<br>- 버전 불일치<br>- 기타|     
|0x8000ffff(E_UNEXPECTED)|-|컴퓨터에 간편 실행 Office가 없을 때 제거를 시도함.|    
|17002|-|시나리오를 완료하지 못함(설치). 가능한 원인:<br>- 사용자가 설치를 취소함<br>- 다른 설치가 설치를 취소함<br>- 설치 시 공간 부족<br>- 알 수 없는 언어 ID| 
|17004|-|알 수 없는 SKU|   


### <a name="office-deployment-tool-error-codes"></a>Office 배포 도구 오류 코드

|||||
|-|-|-|-|
|시나리오|반환 코드|UI|참고| 
|활성 간편 실행 설치가 없는 경우 제거 작업|-2147418113, 0x8000ffff 또는 2147549183|오류 코드: 30088-1008<br>오류 코드: 30125-1011(404)|Office 배포 도구| 
|설치된 MSI 버전이 있는 경우 설치|1603|-|Office 배포 도구| 
|사용자가 설치를 취소함 또는 다른 설치가 설치를 취소함|17002|-|간편 실행| 
|32비트가 설치된 장치에 64비트 설치 시도.|1603|-|Office 배포 도구 반환 코드| 
|알 수 없는 SKU 설치 시도(유효한 SKU만 전달해야 하므로 Office CSP에 대한 올바른 사용 사례가 아님)|17004|-|간편 실행| 
|공간 부족|17002|-|간편 실행| 
|간편 실행 클라이언트를 시작하지 못함(예기치 않음)|17000|-|간편 실행| 
|간편 실행 클라이언트가 시나리오를 큐에 넣지 못함(예기치 않음)|17001|-|간편 실행| 

## <a name="next-steps"></a>다음 단계

이제 선택한 그룹에 앱을 할당할 수 있습니다. 도움말은 [그룹에 앱을 할당하는 방법](/intune-azure/manage-apps/deploy-apps)을 참조하세요.

             


