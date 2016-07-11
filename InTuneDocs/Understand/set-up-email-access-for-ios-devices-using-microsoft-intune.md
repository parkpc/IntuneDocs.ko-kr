---
title: "Microsoft Intune을 사용하여 iOS 장치에 대한 메일 액세스 설정 | Microsoft Intune"
description: 
keywords: 
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3853673d-290a-400f-8e45-d55e39d42acd
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 7f3985b10ac9612c8c1efc4756eb25cdcf29b023
ms.openlocfilehash: 5b746cee0806fb44b1fd847efb9791d525673133


---

# Microsoft Intune을 사용하여 iOS 장치에 대한 메일 액세스 설정
Intune으로 장치를 등록하는 경우 사용자가 회사 메일에 액세스할 수 있도록 장치를 구성할 수 있습니다. 특정 장치 유형에 대해 이를 수행하는 한 가지 방법은 **전자 메일 프로필**을 만들고 배포하는 것입니다. 전자 메일 프로필은 사용자의 장치를 설정하고 회사 메일 서비스에 연결하는 Intune 정책의 한 종류입니다.
전자 메일 프로필을 사용하여 등록된 장치에 대해 전자 메일 액세스를 자동화하여 장치를 수동으로 설정할 필요가 없도록 합니다. 전자 메일 프로필은 또한 동일한 기본 설정 및 동일한 방식으로 모든 최종 사용자가 액세스를 설정하도록 합니다.

## 이 연습의 목표

- iOS 장치에 대한 전자 메일 프로필을 만들고 배포
- 전자 메일 프로필 정책이 성공적으로 적용되었는지 확인

## 이 연습을 시작하기 전에 필요한 항목

- 온-프레미스 또는 Azure에서 Office/E3 구독의 일부로 호스팅되는 Exchange Server
- 회사 Exchange Server의 호스트 이름 FQDN(정규화된 도메인 이름)입니다(예: **contosodemo55.onmicrosoft.com**).
- 전자 메일 프로필을 배포할 사용자 그룹. [Microsoft Intune 평가판 시작 및 iOS PIN 정책 배포](start-a-microsoft-intune-trial-and-deploy-ios-pin-policy.md) 연습을 완료한 경우 생성한 **GroupDemo** 사용자 그룹을 사용할 수 있습니다.
- 프로필을 배포하기 위해 등록된 iOS 장치. 다시, [Microsoft Intune 평가판 시작 및 iOS PIN 정책 배포](start-a-microsoft-intune-trial-and-deploy-ios-pin-policy.md) 연습을 완료한 경우 일부 iOS 장치를 등록합니다.

## iOS 장치에 대한 전자 메일 프로필을 만들고 배포하는 단계

이 연습에서는 평가판 구독과 함께 제공되는 호스팅된 Exchange Server를 사용합니다.
1. Intune 콘솔에서 **정책**을 클릭하고 **정책 추가**를 클릭합니다.
![<add-policy>](./media/Email-Walkthrough/Email-Walkthrough-1.png)
2. **새 정책 만들기** 대화 상자에서 **iOS**를 확장하고 **메일 프로필**을 선택한 후 **정책 만들기**를 클릭합니다.
![<ios-email-profile-policy>](./media/Email-Walkthrough/Email-Walkthrough-2.png)
3. 정책 만들기 페이지에서 정책에 대한 이름(예: **iOS email profile - user-password**) 및 설명을 입력합니다. 서로 다른 장치 유형 및 다른 인증 방법에 대해 여러 전자 메일 프로필이 있을 수 있으므로 어떤 것에 해당하는 프로필인지를 보여 주는 이름을 사용할 수 있습니다.
4. Exchange 호스트 이름을 입력합니다. Azure에서 호스팅되는 Exchange Server를 사용하고 있으므로 호스트 이름에 대해 단순히 **outlook.office365.com**
![<add-exchange-host-name>을 입력합니다.](./media/Email-Walkthrough/Email-Walkthrough-3.png)
5. 전자 메일 서비스를 식별할 수 있도록 장치 사용자에게 표시될 계정 이름을 입력합니다. 예를 들어 **Contoso Email**을 입력합니다.
6. Exchange 서비스의 사용자를 인증하는 데 사용자 이름 및 암호를 사용하므로 사용자 이름 및 암호 설정을 그대로 둡니다.
7. 요구 사항을 충족하도록 동기화 설정을 조정합니다. 지금은 변경하고자 하는 특정 값이 없다면 기본값을 사용합니다.  
8. **정책 저장**을 클릭합니다.
9. 이제 정책을 배포할지 묻는 대화 상자가 나타납니다. **예**를 클릭합니다.
![<deploy-policy-now-dialog>](./media/Email-Walkthrough/Email-Walkthrough-4.png)
10. 다음에 표시되는 창에서 메일 프로필을 배포할 사용자 그룹을 선택하고 **추가**, **확인**을 차례로 클릭합니다.
![<finish-add-policy>](./media/Email-Walkthrough/Email-Walkthrough-5.png)**확인**을 클릭하면 1~2분 이내에 정책이 등록된 장치로 적용되기 시작합니다.

## 프로필 성공적으로 적용되었는지 확인하는 단계

프로필이 적용되었는지 확인하려면 전자 메일 프로필을 배포한 장치 중 하나에 액세스해야 합니다.
1. iOS 장치에서 메일 앱을 엽니다.
앱에 사용자의 전자 메일 사용자 이름 및 암호를 묻는 메시지가 나타납니다.
![<verify-policy-add-password>](./media/Email-Walkthrough/Email-Walkthrough-6.png)
2. 사용자의 Exchange 메일 계정에 대한 사용자 이름 및 암호를 입력하고 **확인**을 탭합니다.
 Exchange 계정에 대한 메일 앱이 열리고 전자 메일이 장치에 대해 동기화되기 시작합니다.
![<exchange-account-opens>](./media/Email-Walkthrough/Email-Walkthrough-7.png)
3. 메일 앱의 계정 설정에서 계정 이름이 전자 메일 프로필에 입력된 것과 동일하고(예를 들어 **Contoso Mail**) 동기화 설정이 올바르게 설정되었는지 확인합니다.
![<check-account-settings>](./media/Email-Walkthrough/Email-Walkthrough-8.png)
![<check-email-account-name>](./media/Email-Walkthrough/Email-Walkthrough-9.png) 메일 프로필이 장치에 자동으로 적용되지 않는 것으로 나타나는 경우 장치에서 회사 포털 앱을 사용하여 정책을 수동으로 적용할 수 있습니다.
1. 회사 포털 앱을 엽니다.
2. **내 장치**를 탭합니다.
3. 장치의 이름을 탭합니다.
![<tap-device-name](./media/Email-Walkthrough/Email-Walkthrough-10.png)
4. **동기화** > **준수 확인**을 탭합니다.
![<tap-sync-check-device>](./media/Email-Walkthrough/Email-Walkthrough-11.png) 몇 분 후에 메일 프로필이 장치에 적용됩니다. 그런 다음 확인 단계에 따라 프로필이 제대로 적용되었는지 확인할 수 있습니다.

## 참고 항목
[Intune 평가 가이드](get-started-with-a-30-day-trial-of-microsoft-intune.md)



<!--HONumber=Jun16_HO4-->


