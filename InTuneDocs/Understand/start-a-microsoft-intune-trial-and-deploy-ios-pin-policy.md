---
title: "Intune 평가판 시작 및 iOS PIN 정책 배포 | Microsoft Intune"
description: "Intune에서 iOS PIN 정책 배포"
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 06cb9a73-0f17-44b3-b334-86c98020316e
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 60ee39a7eeeb9068a7350ec87f60e7148ccb7826
ms.openlocfilehash: a4c38659c87c651678ee30134d50fb74f35fc388


---

# Microsoft Intune 평가판 시작 및 iOS PIN 정책 배포
이 단계별 지침은 Intune 평가판을 설정하고 iOS 장치에 대한 PIN 정책을 구성하는 데 도움이 됩니다. 시도할 수 있는 다른 일반적인 Intune 평가 작업 목록은 [일반적인 Microsoft Intune 평가 작업](common-microsoft-intune-evaluation-tasks.md)을 참조하세요.



## 이 작업의 필수 조건 검토

-   Internet Explorer가 있는 Windows PC - 관리 작업 수행

-   사용자 정책 유효성 검사 테스트를 위한 iOS 7.1 이상 장치

-   평가판을 등록하는 동안 사용자 자신을 인증하기 위한 휴대폰

## 무료 Intune 평가판 계정 만들기
> [!NOTE]
> Intune 구독을 이미 보유한 경우 이 섹션을 건너뛰고 다음 섹션으로 이동합니다.

1.  Windows PC에서 **Internet Explorer**(IE)를 마우스 오른쪽 단추로 클릭하고 **InPrivate 브라우징**을 선택합니다.

    ![InPrivate 브라우징을 시작합니다.](../media/30-day-trial-walkthrus/30day-start-trial-1-InPrivate.png)

2.  [Intune 등록 포털](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1)로 이동한 다음 요청된 정보를 제공하고 **다음**을 클릭합니다.

    ![계정을 등록합니다.](../media/30-day-trial-walkthrus/30day-start-trial-2-abt-you.png)

3.  관리 계정의 사용자 ID 및 암호를 입력하고 **다음**을 클릭합니다. 관리 작업을 수행하려면 이 ID를 사용하여 Intune 포털에 로그인합니다.

    ![ID를 만듭니다.](../media/30-day-trial-walkthrus/30day-start-trial-3-createID.png)

4.  휴대폰 번호를 입력하고 **문자 받기**를 클릭하여 번호의 유효성을 검사합니다.

    ![세부 정보의 유효성을 검사합니다.](../media/30-day-trial-walkthrus/30day-start-trial-4-textme.png)

5.  화면에 표시되는 정보를 저장하고 **사용할 준비가 되었습니다.**를 클릭합니다.

    ![준비 완료](../media/30-day-trial-walkthrus/30day-start-trial-5-ReadyToGo.png)

## 테스트 사용자 만들기

1.  Windows PC에서 **시작**을 클릭하여 사용자 관리 페이지로 이동합니다.

    ![사용자 관리 페이지로 이동합니다.](../media/30-day-trial-walkthrus/30day-crt-user-6-click-start.png)

2.  **+** 단추를 클릭하여 사용자를 추가합니다.

    ![사용자 추가](../media/30-day-trial-walkthrus/30day-crt-user-7-click-plus.png)

3.  **새 사용자 계정 만들기** 페이지에서 다음을 수행합니다.

    1.  테스트 사용자 정보를 제공합니다.

    2.  **암호 입력** 옵션을 선택합니다.

    3.  **다음에 로그인할 때 이 사용자가 암호를 변경하도록 설정** 확인란의 선택을 취소합니다.

    4.  **만들기**를 클릭합니다.

    ![새 사용자 계정 만들기](../media/30-day-trial-walkthrus/30day-crt-user-8-add-user-info.png)

4.  사용자 만들기 확인 페이지에서 **닫기**를 클릭합니다.

    ![사용자 만들기 확인 페이지](../media/30-day-trial-walkthrus/30day-crt-user-9-close-confirm.png)

5.  **새로 고침** 단추를 클릭하여 만든 테스트 사용자를 확인합니다.

    ![계정 확인](../media/30-day-trial-walkthrus/30day-crt-user-10-refresh-user.png)

## 테스트 사용자에 대한 iOS PIN 정책을 구성합니다.

1.  Windows PC에서 MDM 기관을 Intune으로 설정합니다.

    1.  [Intune 관리 콘솔](http://manage.microsoft.com/)로 이동한 다음 관리 계정으로 로그인하고 **모바일 장치 관리 시작**을 클릭합니다. 모바일 장치 관리 기관 페이지가 열립니다.

        ![Intune 콘솔을 시작합니다.](../media/30-day-trial-walkthrus/30day-cfg-pol-11-start-mg-mobl-dev.png)

    2.  **모바일 장치 관리 기관 설정** 링크를 클릭합니다.

        ![모바일 장치 관리 기관을 설정합니다.](../media/30-day-trial-walkthrus/30day-cfg-pol-12-link-set-mdm.png)

2.  iOS 장치를 등록할 수 있도록 설정합니다. 이 프로세스는 APNs(Apple Push Notification Service)와 Intune 구독 간에 신뢰할 수 있는 인증서를 설정합니다.

    1.  **iOS 및 Mac OS X 플랫폼 사용**을 클릭합니다.

        ![Enable iOS 및 Mac OS X 등록 사용](../media/30-day-trial-walkthrus/30day-cfg-pol-13-enbl-ios-plat.png)

    2.  **APNs 인증서 요청 다운로드**를 클릭합니다.

        ![APNs 인증서 다운로드](../media/30-day-trial-walkthrus/30day-cfg-pol-14-dwnld-cert-reqst.png)

    3.  CSR(인증서 서명 요청)의 파일 이름 및 위치를 지정하고 **저장**을 클릭합니다. 이 파일은 Intune 구독에서 보유한 개인 키에 해당하는 공개 키를 포함합니다.

        ![인증서 서명 요청을 지정합니다.](../media/30-day-trial-walkthrus/30day-cfg-pol-15-cert-name-loc.png)

    4.  **APC(Apple Push Certificate) 포털**을 클릭하여 새 탭을 엽니다.

        ![APNs 인증서 페이지로 이동합니다.](../media/30-day-trial-walkthrus/30day-cfg-pol-16-cert-portl-link.png)

    5.  Apple ID 및 암호를 입력하고 **로그인**을 클릭합니다. 이 ID는 iOS 앱 스토어에서 앱을 다운로드하기 위해 iOS 장치에서 사용하는 ID일 수 있습니다.

        ![APC(Apple Push Certificate) 포털에 로그인합니다.](../media/30-day-trial-walkthrus/30day-cfg-pol-17-id-passw-signin.png)

    6.  **인증서 만들기**를 클릭합니다.

        ![APNs 인증서를 만듭니다.](../media/30-day-trial-walkthrus/30day-cfg-pol-18-create-cert.png)

    7.  Apple의 사용 약관을 읽고 확인란을 선택한 다음 **동의함**을 클릭합니다.

        ![약관에 동의합니다.](../media/30-day-trial-walkthrus/30day-cfg-pol-19-TOU.png)

    8.  **찾아보기**를 클릭합니다.

        ![인증서를 저장한 위치로 이동합니다.](../media/30-day-trial-walkthrus/30day-cfg-pol-20-browse.png)

    9. 이전에 저장한 CSR 파일을 선택하고 **열기**를 클릭합니다.

        ![인증서를 엽니다.](../media/30-day-trial-walkthrus/30day-cfg-pol-21-CSRfile-open.png)

    10. **업로드** 단추를 클릭합니다.

        ![인증서를 업로드합니다.](../media/30-day-trial-walkthrus/30day-cfg-pol-22-upld-reqst.png)

    11. JSON 파일을 다운로드하라는 메시지가 표시되면 **다른 이름으로 저장**을 클릭합니다.

        ![JSON 파일을 저장합니다.](../media/30-day-trial-walkthrus/30day-cfg-pol-23-json-saveas.png)

    12. JSON 파일의 위치를 지정하고 **저장**을 클릭합니다.

        ![JSON 파일을 저장할 위치를 지정합니다.](../media/30-day-trial-walkthrus/30day-cfg-pol-24-json-save-loc.png)

        페이지가 몇 초 후에 자동으로 리디렉션되지 않을 경우 **취소**를 클릭합니다.

        ![페이지가 리디렉션되지 않으면 취소합니다.](../media/30-day-trial-walkthrus/30day-cfg-pol-25-json-pg-cancel.png)

    13. 새로 만든 인증서 파일을 검색하려면 **다운로드**를 클릭합니다.

        ![인증서를 다운로드합니다.](../media/30-day-trial-walkthrus/30day-cfg-pol-26-dwnld-retrv-cert.png)

    14. PEM 파일을 다운로드하라는 메시지가 표시되면 **다른 이름으로 저장**을 클릭합니다.

        ![PEM 파일을 다운로드합니다.](../media/30-day-trial-walkthrus/30day-cfg-pol-27-pem-saveas.png)

    15. PEM 파일의 위치를 지정하고 **저장**을 클릭합니다.

        ![PEM 파일을 저장합니다.](../media/30-day-trial-walkthrus/30day-cfg-pol-28-pem-save-loc.png)

    16. Intune 관리 콘솔 탭으로 돌아간 다음 **APNs 인증서 업로드**를 클릭합니다.

        ![APNs 인증서를 업로드합니다.](../media/30-day-trial-walkthrus/30day-cfg-pol-29-upld-cert.png)

    17. Apple ID를 입력하고 **찾아보기**를 클릭합니다.

        ![Apple ID를 입력 합니다.](../media/30-day-trial-walkthrus/30day-cfg-pol-30-app-id-browse.png)

    18. 방금 저장한 PEM 파일을 선택하고 **열기**를 클릭합니다.

        ![PEM 파일을 엽니다.](../media/30-day-trial-walkthrus/30day-cfg-pol-31-sel-pem-open.png)

    19. **업로드**를 클릭합니다.

        ![PEM 파일을 업로드합니다.](../media/30-day-trial-walkthrus/30day-cfg-pol-32-pem-upload.png)

        이제 APNs 인증서가 구성되었습니다.

        ![APNs 인증서 구성 완료](../media/30-day-trial-walkthrus/30day-cfg-pol-33-apns-confgd.png)

3.  정책 대상 지정을 위한 테스트 사용자 그룹을 만듭니다.

    1.  왼쪽 창에서 **그룹**을 클릭합니다.

        ![그룹을 엽니다.](../media/30-day-trial-walkthrus/30day-cfg-pol-34-clk-groups.png)

    2.  맨 오른쪽에 있는 **그룹 만들기**를 클릭합니다.

        ![그룹 만들기](../media/30-day-trial-walkthrus/30day-cfg-pol-35-crt-group.png)

    3.  그룹 이름을 제공하고 **모든 사용자**를 부모 그룹으로 선택한 후 **다음**을 클릭합니다.

        ![모든 사용자를 부모 그룹으로 선택합니다.](../media/30-day-trial-walkthrus/30day-cfg-pol-36-name-group.png)

    4.  **다음으로 그룹 멤버 자격 시작** 필드에서 **부모 그룹의 모든 사용자**를 선택하고 **마침**을 클릭합니다.

        ![부모 그룹으로 그룹 멤버 자격을 시작합니다.](../media/30-day-trial-walkthrus/30day-cfg-pol-37-all-users-group.png)

4.  iOS PIN 정책을 만들고 대상을 테스트 사용자 그룹으로 지정합니다.

    1.  왼쪽 창에서 **정책**을 클릭합니다.

        ![정책 작업 영역을 엽니다.](../media/30-day-trial-walkthrus/30day-cfg-pol-38-clk-policy.png)

    2.  맨 오른쪽에 있는 **정책 추가**를 클릭합니다.

        ![정책을 추가합니다.](../media/30-day-trial-walkthrus/30day-cfg-pol-39-add-policy.png)

    3.  iOS 노드를 확장하고 **일반 구성** 행을 선택한 다음 **정책 만들기**를 클릭합니다.

        ![iOS 일반 구성 정책 만들기](../media/30-day-trial-walkthrus/30day-cfg-pol-40-gen_cfg_pol.png)

    4.  정책의 이름을 입력하고 **모바일 장치의 잠금을 해제하는 데 암호 필요** 옵션을 설정한 다음 **최소 암호 길이**를 **4**로 설정합니다.

        ![암호 설정을 구성합니다.](../media/30-day-trial-walkthrus/30day-cfg-pol-41-name-policy.png)

    5.  **예**를 클릭하여 정책을 배포합니다.

        ![정책을 배포합니다.](../media/30-day-trial-walkthrus/30day-cfg-pol-42-yes-deploy-pol.png)

    6.  이전에 만든 사용자 그룹을 클릭한 다음 **추가**, **확인**을 차례로 클릭합니다.

        ![정책에 대한 그룹을 선택합니다.](../media/30-day-trial-walkthrus/30day-cfg-pol-43-add-pol-to-grp.png)

        이제 테스트 사용자 그룹을 대상으로 하는 iOS PIN 정책이 있습니다.

        ![정책 설정 완료](../media/30-day-trial-walkthrus/30day-cfg-pol-44-policy-applied.png)

## 이 정책이 iOS 장치에 적용되었는지 확인

1.  iPad에서 iOS 앱 스토어를 시작하고 무료 **Microsoft Intune 회사 포털** 앱을 설치한 다음 엽니다.

    ![회사 포털을 설치합니다.](../media/30-day-trial-walkthrus/30day-cfg-pol-45-cportal-installed.png)

2.  테스트 사용자 계정 이름 및 암호를 입력하고 **로그인**을 탭합니다.

    ![자격 증명을 제공합니다.](../media/30-day-trial-walkthrus/30day-cfg-pol-46-cportal-signin.png)

3.  **등록**을 탭하여 Intune에서 장치 등록을 시작합니다.

    ![등록을 시작합니다.](../media/30-day-trial-walkthrus/30day-cfg-pol-47-tap-enroll.jpg)

4.  **프로필 설치** 화면에서 **설치**를 탭합니다.

    ![프로필을 설치합니다.](../media/30-day-trial-walkthrus/30day-cfg-pol-48-profile-install-1.jpg)

5.  **프로필 설치** 대화 상자에서 **설치**를 탭합니다.

    ![프로필 설치를 계속합니다.](../media/30-day-trial-walkthrus/30day-cfg-pol-49-profile-install-2.jpg)

6.  **경고** 화면에서 **설치**를 탭합니다.

    ![경고 메시지를 수락합니다.](../media/30-day-trial-walkthrus/30day-cfg-pol-50-warning-install-3.png)

7.  **원격 관리** 대화 상자에서 **신뢰**를 탭합니다.

    ![원격 관리를 신뢰합니다.](../media/30-day-trial-walkthrus/30day-cfg-pol-51-remt-mgmt-trust.jpg)

8.  관리 프로필 설치가 완료되면 **완료**를 탭합니다. 이제 등록이 완료되었습니다.

    ![등록 완료](../media/30-day-trial-walkthrus/30day-cfg-pol-52-profile-done.jpg)

9. 등록이 완료되면 **확인**을 탭하고 회사 포털 앱을 닫습니다.

    ![확인을 탭하고 회사 포털 앱을 닫습니다.](../media/30-day-trial-walkthrus/30day-cfg-pol-53-devc-enrolled-ok.png)

10. 암호를 구성하라는 메시지가 표시되면 **계속**을 탭합니다.

    ![암호를 구성하라는 메시지를 수락합니다.](../media/30-day-trial-walkthrus/30day-cfg-pol-54-passcode-req-cont.png)

11. 암호를 입력하고 **계속**을 탭한 다음 암호를 다시 입력하고 **저장**을 탭합니다.

    ![암호를 제공 합니다.](../media/30-day-trial-walkthrus/30day-cfg-pol-55-passcode-enter.jpg)

12. 전원 단추를 눌러 iPad를 잠근 후 밀어서 잠금을 해제하려고 하면 이제 장치의 잠금을 해제하기 위해 암호를 입력해야 함을 확인할 수 있습니다.

### 참고 항목
[Intune 평가 가이드](get-started-with-a-30-day-trial-of-microsoft-intune.md)



<!--HONumber=Jul16_HO4-->


