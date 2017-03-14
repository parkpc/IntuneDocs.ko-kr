---
title: "Apple MDM Push Certificate 가져오기"
titleSuffix: Intune Azure preview
description: "Intune Azure 미리 보기: Intune에서 iOS 장치를 관리하기 위해 Apple MDM Push Certificate를 가져오는 단계를 알아봅니다."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 26991bd0c7632d04b75ecbec023d96c1045f337a
ms.lasthandoff: 02/18/2017


---

# <a name="get-an-apple-mdm-push-certificate"></a>Apple MDM 푸시 인증서 가져오기 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Intune은 iPad, iPhone 및 Mac OS X 장치의 MDM(모바일 장치 관리)을 가능하게 하고, 사용자가 회사 메일 및 앱에 액세스할 수 있게 해줍니다. APN(Apple 푸시 알림) 서비스 인증서는 Intune에서 iOS 및 Mac 장치를 관리하는 데 필요합니다. 인증서를 Intune에 추가하면 사용자가 회사 포털 앱을 설치하여 장치를 등록할 수도 있고 관리자가 회사 소유의 iOS 장치 관리를 설정할 수도 있습니다.

## <a name="steps-to-get-your-certificate"></a>인증서를 가져오는 단계
Azure Portal에서 **추가 서비스** > **모니터링 + 관리** > **Intune**을 선택합니다. Intune 블레이드에서 **장치 등록** > **Apple MDM Push Certificate**를 선택한 후 Azure Portal에서 번호가 매겨진 단계(아래 참조)를 따릅니다.

**1단계. Apple MDM Push Certificate를 만드는 데 필요한 Intune 인증서 서명 요청을 다운로드합니다.**<br>
**CSR 다운로드**를 선택하여 .csr 파일을 로컬로 다운로드하고 저장합니다. .csr 파일은 APC(Apple Push Certificate) 포털에서 트러스터 관계 인증서를 요청하는 데 사용됩니다.

**2단계. Apple MDM Push Certificate를 만듭니다.**<br>
**MDM Push Certificate 만들기**를 선택하여 APC(Apple Push Certificate) 포털로 이동합니다. 회사 Apple ID로 로그인하여 .csr 파일로 푸시 인증서를 만듭니다. Apple의 Push Certificate 포털에서 **업로드**를 선택하면 .json 파일이 제공됩니다. Push Certificate에 이 파일을 사용하지 마세요. 다운로드를 완료하고 타사 서버용 인증서를 위한 Apple Push Certificates Portal로 돌아가 **다운로드**를 선택합니다. 푸시 인증서(.pem 파일)를 다운로드하여 파일을 로컬에 저장합니다.
참고

**3단계. MDM Push Certificate를 만드는 데 사용되는 Apple ID를 입력합니다.**

**4단계. Apple MDM Push Certificate로 이동하여 업로드합니다.**<br>
인증서(.pem) 파일로 이동한 후 **열기**를 선택하고 **업로드**를 선택합니다. Push Certificate가 있으면 Intune에서 등록된 모바일 장치에 정책을 푸시하여 iOS 장치를 등록하고 관리할 수 있습니다.

