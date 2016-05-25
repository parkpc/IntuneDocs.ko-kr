---
# required metadata

title: Microsoft Intune을 사용한 iOS 장치용 Apple DEP 관리 | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8ff9d9e7-eed8-416c-8508-efc20fca8578

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# 회사 소유 장치 등록 프로그램 iOS 장치 등록
Microsoft Intune은 “무선으로” DEP(장치 등록 프로그램)를 통해 구매한 iOS 장치를 등록하는 등록 프로필을 배포할 수 있습니다. 등록 패키지는 장치에 대한 설정 도우미 옵션을 포함할 수 있습니다. DEP를 통해 등록된 장치는 사용자가 등록을 취소할 수 없습니다.

## Microsoft Intune을 사용한 iOS 장치용 Apple DEP 관리
Apple DEP(장치 등록 프로그램)로 회사 소유의 iOS 장치를 관리하려면 조직이 Apple DEP에 가입하고 해당 프로그램을 통해 장치를 획득해야 합니다. 해당 프로세스의 세부 정보는 [https://deploy.apple.com](https://deploy.apple.com)에서 제공됩니다. 이 프로그램의 이점 중 하나는 각 장치를 컴퓨터에 연결하지 않고도 장치를 자동 설치할 수 있다는 것입니다.

회사 소유의 iOS 장치를 DEP에 등록하려면 Apple의 DEP 토큰이 필요합니다. Intune에서는 이 토큰을 통해 회사에서 소유한 DEP 참가 장치에 대한 정보를 동기화할 수 있습니다. 또한 Apple에 등록 프로필을 업로드하고 이러한 프로필에 장치를 할당할 수 있습니다.

1.  **Microsoft Intune으로 iOS 장치 관리 시작**
    iOS DEP(장치 등록 프로그램) 장치를 등록하려면 먼저 Intune에 대한 iOS 관리 사용을 완료해야 합니다.

2.  **암호화 키 가져오기**
    관리자 권한으로 [Microsoft Intune 관리 콘솔](http://manage.microsoft.com)을 열고 **관리** &gt; **모바일 장치 관리** &gt; **iOS** &gt; **장치 등록 프로그램**으로 이동한 다음 **암호화 키 다운로드**를 클릭합니다. 암호화 키(.pem) 파일을 로컬로 저장합니다. .pem 파일은 Apple 장치 등록 프로그램 포털에서 트러스트 관계 인증서를 요청하는 데 사용됩니다.

      ![장치 등록 프로그램 토큰 업데이트](../media/dev-sa-ios-dep.png)

3.  **장치 등록 프로그램 토큰 가져오기**
    [장치 등록 프로그램 포털](https://deploy.apple.com)(https://deploy.apple.com)로 이동한 다음 회사 Apple ID로 로그인합니다. 나중에 DEP 토큰을 갱신하려면 이 Apple ID를 사용해야 합니다.

    1.  [장치 등록 프로그램 포털](https://deploy.apple.com) 포털에서 **장치 등록 프로그램** &gt; **서버 관리**로 이동한 다음 **MDM 서버 추가**를 클릭합니다..

    2.  **MDM 서버 이름** 을 입력한 다음 **다음**을 클릭합니다. 서버 이름은 참조용으로 MDM 서버를 식별하기 위한 것으로, Microsoft Intune 서버의 이름 또는 URL이 아닙니다.

    3.  **&lt;ServerName&gt; 추가** 대화 상자가 열립니다. **파일 선택...**을 클릭하여 .pem 파일을 업로드한 후 **다음**을 클릭합니다..

    4.  **&lt;ServerName&gt; 추가** 대화 상자에 **내 서버 토큰** 링크가 표시됩니다. 컴퓨터에 서버 토큰(.p7m) 파일을 다운로드한 다음 **완료**를 클릭합니다..

    이 인증서(.p7m) 파일은 Intune과 Apple 장치 등록 프로그램 서버 간에 트러스트 관계를 설정하는 데 사용됩니다.

4.  **Intune에 DEP 토큰 추가**
    [Microsoft Intune 관리 콘솔](http://manage.microsoft.com)에서 **Admin** &gt; **모바일 장치 관리** &gt; **iOS** &gt; **장치 등록 프로그램**으로 이동하고 **DEP 토큰 업로드**. **찾아보기**를 클릭하여 인증서(.p7m) 파일에 **Apple ID**를 입력하고 **업로드**를 클릭합니다..

5.  **회사 장치 등록 정책 추가**
    [Microsoft Intune 관리 콘솔](http://manage.microsoft.com)에서 **정책** &gt; **회사 장치 등록**으로 이동한 다음 **추가**를 클릭합니다. **이름** 및 **설명**을 포함한 **일반** 세부 정보를 제공하고, 프로필에 할당된 장치에 사용자 선호도가 있는지 또는 그룹에 속해 있는지 여부를 지정한 다음 **이 정책에 대한 장치 등록 프로그램 구성 설정**을 사용하도록 설정하여 DEP를 지원합니다. **도우미 창 설정**은 설정 중에 구성되는 iOS 장치 설정을 정의합니다.

      ![설정 도우미 창](../media/pol-sa-corp-enroll.png)

6.  **관리를 위해 DEP 장치 할당**
    [장치 등록 프로그램 포털](https://deploy.apple.com)(https://deploy.apple.com)로 이동한 다음 회사 Apple ID로 로그인합니다. **배포 프로그램** &gt; **장치 등록 프로그램** &gt; **장치 관리**로 이동합니다. **장치 선택** 방법을 지정하고, 장치 정보를 제공한 다음 장치 **일련번호**, **주문 번호** 또는 **CSV 파일 업로드**에 따라 세부 정보를 지정합니다. 그런 다음 **서버에 할당**을 선택하고 Microsoft Intune에 대해 지정된 &lt;ServerName&gt;을 선택한 다음 **확인**을 클릭합니다..

7.  **DEP 관리 장치 동기화**
    관리자 권한으로 [Microsoft Intune 관리 콘솔](http://manage.microsoft.com)을 열고 **관리** &gt; **모바일 장치 관리** &gt; **iOS** &gt; **장치 등록 프로그램**으로 이동한 다음 **지금 동기화**를 클릭합니다. 동기화 요청이 Apple에 전송됩니다. 동기화 후에 DEP 관리 장치를 보려면 [Microsoft Intune 관리 콘솔](http://manage.microsoft.com)에서 **그룹** &gt; **모든 회사 소유 장치**로 이동합니다. **회사 소유 장치** 작업 영역에서는 장치를 켜고 설치 도우미를 실행하여 장치를 등록할 때까지 관리되는 장치 **상태**가 "연결되지 않음"으로 표시됩니다.

    허용 가능한 DEP 트래픽에 대한 Apple의 약관을 준수하려면 Intune에서는 다음과 같은 제한 사항을 적용합니다.
     -  전체 DEP 동기화는 7일마다 한 번 이상 실행할 수 없습니다. 전체 동기화 중 Intune은 Apple에서 일련 번호가 이전에 동기화되었는지 여부를 Intune에 할당한 모든 일련 번호를 새로 고칩니다. 전체 동기화를 이전 전체 동기화의 7일 이내에 시도하는 경우 Intune은 Intune에 나열되지 않은 일련 번호만 새로 고칩니다.
     -  모든 동기화 요청은 완료하는 데 10분이 주어집니다. 이 시간 동안 또는 요청이 성공될 때까지 동기화 단추는 비활성화됩니다.

8.  **사용자에게 장치 배포**
    이제 회사 소유 장치를 사용자에게 배포할 수 있습니다. IOS 장치를 설정하는 경우에 Intune에 관리용으로 등록됩니다.



### 참고 항목
[장치 등록 준비](get-ready-to-enroll-devices-in-microsoft-intune.md)


<!--HONumber=May16_HO1-->


