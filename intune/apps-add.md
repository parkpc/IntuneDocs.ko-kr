---
title: "Microsoft Intune에 앱을 추가하는 방법"
titlesuffix: 
description: "사용자 및 장치에 앱을 할당할 수 있도록 앱을 Microsoft Intune에 추가하는 방법을 알아봅니다. Intune은 다양한 종류의 앱을 지원합니다."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/01/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1ded457-0ecf-4f9c-a2d2-857d57f8d30a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 91762eafbba5f96ce04f3ffd4d83f63434a3ac74
ms.sourcegitcommit: aafed032492c1b5861d7097a335f9bbb29ce3221
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2018
---
# <a name="how-to-add-an-app-to-microsoft-intune"></a>Microsoft Intune에 앱을 추가하는 방법

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

앱을 할당, 모니터링, 구성 또는 보호하려면 앱을 Intune에 추가해야 합니다. Intune은 다양한 종류의 앱을 지원합니다. 사용 가능한 옵션은 앱 유형마다 다릅니다.

Intune을 사용하여 다음 앱 유형을 추가하고 지정할 수 있습니다.
| 앱 유형                                  | 설치                                                                  | 업데이트                       |
|------------------------------------------ |----------------------------------------------------------------------------   |---------------------------    |
| 웹앱                           | Intune이 장치 홈 화면에 웹앱의 바로 가기 생성          | 앱 업데이트가 자동     |
| 사내에서 작성한 앱(기간 업무)  | Intune이 장치에 앱 설치(관리자가 설치 파일 제공)    | 관리자가 앱 업데이트       |
| 스토어 앱                       | Intune이 장치에 앱 설치                                       | 앱 업데이트가 자동     |
| 기본 제공 앱                        | Intune이 장치에 앱 설치                                       | 앱 업데이트가 자동     |


Intune은 웹앱 외에도 다음과 같은 스토어 앱 및 LOB 앱을 위한 특정 플랫폼을 지원합니다.
- 스토어 앱
    - Android 스토어 앱
    - iOS 스토어 앱
    - Windows Phone 8.1 스토어 앱
    - Windows 스토어 앱
    - Android for Work 앱
    - Windows용 Office 365 앱
    - macOS용 Office 365 앱
- 앱 빌드 - LOB(기간 업무)
    - Android LOB(기간 업무) 앱
    - iOS LOB(기간 업무) 앱
    - Windows Phone LOB(기간 업무) 앱(.xap 파일)
    - Windows LOB(기간 업무) 앱(.msi 파일만)
- 기본 제공 앱    

>[!TIP]
> LOB(기간 업무) 앱은 앱 설치 파일로 추가합니다. 예를 들어 iOS LOB 앱을 설치하려면 **앱 추가** 블레이드에서 **앱 유형**으로 **기간 업무 앱**을 선택합니다. 그런 다음, 앱 패키지 파일(확장명 .ipa)을 선택합니다. 이러한 유형의 앱은 일반적으로 사내에서 작성됩니다.

## <a name="assess-application-requirements"></a>응용 프로그램 요구 사항 평가 
IT 관리자는 그룹에서 사용해야 하는 앱뿐 아니라 각 그룹 및 하위 그룹에 필요한 기능도 결정해야 합니다. 각 앱에 대해 필요한 플랫폼, 해당 앱이 필요한 사용자 그룹, 해당 그룹에 적용할 구성 정책, 적용할 보호 정책을 결정해야 합니다.  

뿐만 아니라 MDM(모바일 장치 관리)에 집중해야 하는지 아니면 MAM(모바일 응용 프로그램 관리)에만 집중하면 되는지 결정해야 합니다. Intune을 사용하여 장치를 관리하면(모바일 장치 관리) 다음과 같은 경우에 유용합니다.
- 사용자가 생산성 유지를 위해 WiFi 또는 VPN 회사 연결 프로필이 필요한 경우.
- 사용자가 자신의 장치에 앱 집합을 푸시해야 하는 경우.
- 조직이 보안이나 암호화 같은 특정 MDM(모바일 장치 관리) 컨트롤을 호출하는 규정 또는 기타 정책을 준수해야 하는 경우.

장치를 관리하지 않고 Intune을 사용하여 앱을 관리하면(모바일 응용 프로그램 관리) 다음과 같은 경우에 유용합니다.
- 사용자에게 BYOD를 허용하려는 경우.
- 사용자에게 MAM 보호가 작동하고 있다는 사실을 지속적인 장치 수준 알림이 아닌 일회성 팝업을 통해 알리려는 경우.
- 개인 장치에서 더 적은 관리 기능이 필요한 정책을 준수하려는 경우. 예를 들어 장치 전체에 대한 회사 데이터를 관리하는 대신 앱에 대한 회사 데이터를 관리할 수 있습니다.

자세한 내용은 [MDM 및 MAM 비교](byod-technology-decisions.md)를 참조하세요.

### <a name="determine-who-will-use-the-app"></a>앱을 사용할 사람 결정
Intune에 앱을 추가한 후에는 해당 앱을 사용할 수 있는 사용자 그룹을 할당합니다. 먼저 앱이 포함하는 데이터의 중요도에 따라 앱에 액세스할 수 있는 적절한 그룹을 결정해야 합니다. 조직 내 특정 유형의 역할을 포함하거나 제외해야 합니다. 예를 들어 영업 그룹에는 특정 LOB 앱만 필요하고 엔지니어링, 재무, HR 또는 법률에 집중하는 직원들은 LOB 앱을 사용해야 합니다. 또한 영업 그룹은 모바일 장치에서 회사 내부 서비스에 액세스해야 하는 경우가 있으므로 추가적인 데이터 보호 기능이 필요할 것입니다. 이 그룹이 앱을 사용하여 리소스에 연결하는 방식을 결정해야 합니다. 앱이 액세스하는 데이터가 클라우드 또는 온-프레미스에서 실시간인지 결정해야 합니다. 사용자가 앱을 사용하여 리소스에 연결하는 방식도 결정해야 합니다. 또한 Intune에서는 기간 업무 앱 서버와 같은 온-프레미스 데이터에 대한 보안 액세스가 필요한 모바일 앱에 대한 액세스를 지원합니다. 이러한 유형의 액세스는 일반적으로 Microsoft Azure Active Directory 앱 프록시와 같은 경계에서 표준 VPN 게이트웨이 또는 프록시와 결합된 액세스 제어에 [Intune 관리 인증서](certificates-configure.md)를 사용하여 수행됩니다. Intune의 [앱 줄 바꿈 도구 및 앱 SDK](apps-prepare-mobile-application-management.md)를 사용하면 액세스한 데이터를 기간 업무 앱 내에서 유지할 수 있으므로, 소비자 앱 또는 서비스에 회사 데이터를 전달할 수 없습니다.

[Intune 배포 계획, 설계 및 구현 가이드](planning-guide.md)를 사용하여 각 사용 사례 및 하위 사용 사례 앱 시나리오와 연결된 조직 그룹을 식별하는 방법을 확인하세요. 그룹에 앱을 할당하는 방법에 대한 자세한 내용은 [Microsoft intune을 사용하여 그룹에 앱을 할당하는 방법](apps-deploy.md)을 참조하세요. 

### <a name="determine-the-type-of-app-for-your-solution"></a>솔루션에 사용할 앱 유형 결정
다음 앱 유형 중에서 선택할 수 있습니다.
- **웹앱** - 웹앱은 클라이언트-서버 응용 프로그램입니다. 서버는 UI, 콘텐츠 및 기능을 포함하고 있는 웹앱을 제공합니다. 또한 플랫폼을 호스팅하는 현대식 웹은 일반적으로 보안, 부하 분산 및 기타 이점을 제공합니다. 이 앱 유형은 웹에서 별도로 유지 관리됩니다. Intune을 사용하여 이 앱 유형을 가리킵니다. 또한 이 앱에 액세스할 수 있는 사용자 그룹을 할당합니다. Android는 웹앱을 지원하지 않습니다.
- **사내에서 작성한 앱(기간 업무)** - 사내에서 만들어진 앱은 LOB(기간 업무) 앱입니다. 이러한 유형의 앱 기능은 Windows, iOS, Android 등 Intune에서 지원하는 플랫폼 중 하나에서 사용할 수 있도록 개발되었습니다. 조직에서 업데이트를 별도 파일로 만들어서 관리자에게 제공합니다. 관리자는 Intune으로 업데이트를 추가 및 배포하여 사용자에게 앱 업데이트를 제공합니다. 
- **스토어 앱** - 스토어 앱은 Windows 스토어, iOS 스토어 또는 Android 스토어에 업로드된 앱입니다. 스토어 앱의 공급자는 앱 업데이트를 유지 관리 및 제공합니다. 관리자는 Intune을 사용하여 스토어 목록에서 앱을 선택하고 사용자가 사용할 수 있는 앱으로 추가합니다.

조직에 필요한 앱을 결정할 때 이러한 앱이 클라우드 서비스와 통합되는 방식, 앱이 액세스하는 데이터, BYOD 사용자에게 앱을 제공할 것인지 여부, 앱의 인터넷 액세스가 필요한지 여부를 고려해야 합니다.

조직에 필요한 앱 유형 결정에 대한 자세한 내용은 [디자인 만들기](planning-guide-design.md#feature-requirements)의 **기능 요구 사항** 섹션에서 **앱**을 참조하세요.

### <a name="understanding-app-management-and-protection-policies"></a>앱 관리 및 보호 정책 이해
앱이 회사의 규정 준수 및 보안 정책을 따르도록 Intune을 사용하여 배포하는 앱의 기능을 수정할 수 있습니다. 이를 통해 회사 데이터를 보호하는 방식을 결정할 수 있습니다. Intune 관리 앱은 다음과 같은 풍부한 모바일 응용 프로그램 보호 정책을 지원합니다.

- 복사하여 붙여넣기 및 다른 이름으로 저장 함수 제한
- Intune Managed Browser 앱 내에서 열리는 웹 링크 구성
- 다중 ID 사용 및 앱 수준 조건 액세스 사용

또한 Intune 관리 앱은 등록 없이 앱 보호를 사용할 수 있으므로 사용자의 장치를 관리하지 않고도 데이터 손실 방지 정책을 적용할 수 있습니다. 뿐만 아니라 Intune 앱 소프트웨어 개발 키트와 앱 래핑 도구를 사용하여 모바일 및 기간 업무 앱에서 회사 모바일 앱 관리를 통합할 수 있습니다. 이러한 도구에 대한 자세한 내용은 [Intune 앱 SDK 개요](app-sdk.md)를 참조하세요.

### <a name="understanding-licensed-apps"></a>라이선스 앱 이해
웹앱, 스토어 앱 및 LOB 앱 외에도 다음과 같은 대량 구매 프로그램 앱 및 라이선스 앱에 대해 알고 있어야 합니다.     
- **기업을 위한 Apple 대량 구매 프로그램(iOS 및 MacOS)** - iOS 앱 스토어는 회사에서 실행하려는 앱의 라이선스를 여러 개 구매하는 기능을 제공합니다. 여러 복사본을 구매하면 회사에서 앱을 효율적으로 관리할 수 있습니다. 자세한 내용은 [iOS 대량 구매 앱 관리](vpp-apps-ios.md)를 참조하세요.
- **Android for Work(Android)** - 표준 Android 장치에 할당하던 방식과 다른 방법으로 Android for Work 장치에 앱을 할당합니다. Android for Work에 대해 설치하는 모든 앱은 Google Play for Work 스토어에서 받습니다. 스토어에 로그온하여 원하는 앱을 찾아본 다음 승인합니다. 그러면 앱이 Azure Portal의 [사용이 허가된 앱] 노드에 나타납니다. 여기에서 다른 앱을 할당하는 방식과 동일하게 앱 할당을 관리할 수 있습니다.
- **비즈니스용 Windows 스토어(Windows 10)** - 비즈니스용 Microsoft 스토어는 조직에서 사용할 앱을 찾아서 개별적으로 또는 대량으로 구입할 수 있는 위치를 제공합니다. 스토어를 Microsoft Intune에 연결하여 Azure Portal에서 대량 구매 앱을 관리할 수 있습니다. 자세한 내용은 [비즈니스용 Microsoft 스토어에서 앱 관리](windows-store-for-business.md)를 참조하세요. 

## <a name="before-you-start"></a>시작하기 전에
앱을 추가하고 할당하기 전에 다음 사항을 고려해야 합니다.

- 스토어에서 앱을 추가하고 할당하는 경우 앱을 설치할 수 있도록 최종 사용자에게 해당 스토어의 계정이 있어야 합니다.
- 할당한 앱 또는 항목 중 일부는 기본 제공 iOS 앱에 종속될 수 있습니다. 예를 들어 iOS 스토어에서 책을 할당하는 경우 iBooks 앱은 장치에 있어야 합니다. iBooks 기본 제공 앱을 제거한 경우에는 Intune을 사용하여 복구할 수 없습니다.

## <a name="cloud-storage-space"></a>클라우드 저장소 공간
소프트웨어 설치 관리자 설치 유형(예: 기간 업무 앱)을 사용하여 만든 모든 앱은 패키징된 후 Intune 클라우드 저장소로 업로드됩니다. Intune의 평가판 구독에는 관리 앱 및 업데이트를 저장하는 데 사용되는 클라우드 기반의 2GB 저장소가 포함됩니다. 전체 구독에는 20GB의 저장소 공간이 포함됩니다.

원래 구매 방법을 사용하여 Intune용 저장소를 추가로 구입할 수 있습니다.  청구서 또는 신용 카드로 지불한 경우 [구독 관리 포털](https://portal.office.com/adminportal/home?switchtomodern=true#/subscriptions)을 참조하세요.  그 외의 경우에는 파트너나 영업 사원에게 문의하세요.

클라우드 저장소 공간에 대한 요구 사항은 다음과 같습니다.

-   모든 앱 설치 파일이 같은 폴더 내에 있어야 합니다.
-   업로드하는 파일의 최대 파일 크기는 2GB입니다.

## <a name="how-to-create-and-edit-categories-for-apps"></a>앱의 범주를 만들고 편집하는 방법

앱 범주를 사용하여 사용자가 회사 포털에서 보다 쉽게 찾을 수 있도록 앱을 정렬할 수 있습니다. 하나 이상의 범주(예: **개발자 앱**, 또는 **통신 앱**)를 앱에 할당할 수 있습니다.
Intune에 앱을 추가하는 경우 원하는 범주를 선택할 수 있는 옵션이 제공됩니다. 플랫폼 관련 항목을 사용하여 앱을 추하고 범주를 할당합니다. 사용자 고유의 범주를 만들고 편집하려면 다음 절차를 사용합니다.

1. 로그인은 [Azure 포털](https://portal.azure.com)합니다.
2. **모든 서비스** > **Intune**을 선택합니다. Intune은 **모니터링 + 관리** 섹션에 있습니다.
3. **Intune** 블레이드에서 **Mobile Apps**를 선택합니다.
4. **모바일 앱** 워크로드에서 **설정** > **앱 범주**를 선택합니다.
5. **앱 범주** 블레이드에 현재 범주 목록이 표시됩니다. 다음 작업 중 하나를 선택합니다.
    - **범주 만들기** - **추가**를 선택하여 **범주 만들기** 블레이드를 표시한 다음, 새 범주의 이름을 추가합니다. 이름은 하나의 언어로만 입력할 수 있으며, Intune에서 번역되지 않습니다. 완료되면 **만들기**를 클릭합니다.
    - **범주 편집** - 목록의 범주에 대해 '**...**'를 선택합니다. 이 옵션은 범주를 **대시보드에 고정** 또는 **삭제**할 수 있는 팝업 메뉴를 표시합니다.

## <a name="apps-added-automatically-by-intune"></a>Intune에서 자동으로 추가된 앱

이전에는 Intune에 신속하게 할당할 수 있는 많은 기본 제공 앱이 포함되어 있었습니다. 사용자 의견에 따라 이 목록은 제거되었으며 더 이상 기본 제공 앱은 표시되지 않습니다.
그러나 이미 기본 제공 앱을 할당한 경우 이러한 앱은 여전히 앱 목록에 표시됩니다. 필요에 따라 이러한 앱을 계속 할당할 수 있습니다.
이후 릴리스에는 Azure Portal에서 기본 제공 앱을 더 쉽게 선택하고 할당하는 방법이 추가될 예정입니다.

## <a name="next-steps"></a>다음 단계

각 플랫폼용 앱을 Intune에 추가하는 방법을 알아보려면 다음 항목 중 하나를 선택합니다.

- [Android 스토어 앱](store-apps-android.md)
- [Android LOB 앱](lob-apps-android.md)
- [iOS 스토어 앱](store-apps-ios.md)
- [iOS LOB 앱](lob-apps-ios.md)
- [웹앱(모든 플랫폼)](web-app.md)
- [Windows Phone 8.1 스토어 앱](store-apps-windows-phone-8-1.md)
- [Windows Phone LOB 앱](lob-apps-windows-phone.md)
- [Windows 스토어 앱](store-apps-windows.md)
- [Windows LOB 앱](lob-apps-windows.md)
- [Windows 10용 Office 365 앱](apps-add-office365.md)
- [기본 제공 앱](apps-add-built-in.md)

