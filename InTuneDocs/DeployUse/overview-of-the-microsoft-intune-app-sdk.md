---
title: "Microsoft Intune 앱 SDK 개요 | Microsoft Intune"
description: 
keywords: 
author: Msmbaldwin
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ef1751bb-3a2f-4662-a922-38c076869eb3
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 779127bfd39145010f0d9b6609286aaf4dedfdc8
ms.openlocfilehash: 8a9dfe8224b4e0e441691043eaffea73c456b3ec


---

# Microsoft Intune 앱 SDK 개요
Intune 앱 SDK는 iOS 및 Android 플랫폼 둘 다에 사용할 수 있으며 Microsoft Intune을 통해 모바일 앱 관리 기능을 사용할 수 있게 합니다. 또한 개발자에게 요구되는 코드 변경량을 줄이려고 합니다. 앱의 동작을 변경하지 않고 대부분의 SDK 기능을 사용하도록 설정할 수 있습니다. 최종 사용자 및 IT 관리자 환경을 개선하기 위해 API를 활용하여 앱 참여를 요구하는 기능에 대한 앱 동작을 사용자 지정할 수 있습니다. 

앱을 사용하도록 설정하면 IT 관리자가 Intune 관리 앱에 정책을 배포하고 이러한 기능을 활용하여 회사 데이터를 보호할 수 있습니다.

# 기능
## 사용자의 회사 문서 이동 기능을 제어합니다.
IT 관리자는 Intune 관리 앱에서 회사 문서의 파일 재배치를 제어할 수 있습니다. 예를 들어 파일 백업 앱이 회사 데이터를 클라우드로 백업할 수 없도록 하는 정책을 배포할 수 있습니다.  

## 클립보드 제한 구성
IT 관리자는 Intune 관리 앱의 클립보드 동작을 구성할 수 있습니다. 예를 들어 최종 사용자가 클립보드를 사용하여 Intune 관리 앱에서 잘라내기/복사하여 관리되지 않는 앱에 붙여넣을 수 없도록 정책을 배포할 수 있습니다.

## 화면 캡처 제한 구성
IT 관리자는 Intune 관리 앱이 표시되는 경우 사용자가 화면을 캡처할 수 없도록 차단할 수 있습니다. 이 제한을 적용하면 회사 기밀 콘텐츠의 캡처 및 릴리스가 방지됩니다. 이 기능은 Android 장치에만 사용할 수 있습니다. 

## 저장된 데이터에 암호화 적용
IT 관리자는 앱에서 장치에 저장하는 데이터가 암호화되도록 하는 정책을 적용할 수 있습니다.

## 원격으로 회사 데이터 초기화
IT 관리자는 Microsoft Intune에서 장치 등록이 취소될 때 Intune 관리 앱에서 회사 데이터를 원격으로 초기화할 수 있습니다. 이 기능은 ID 기반이며 최종 사용자의 회사 ID와 관련된 파일만 삭제합니다. 이렇게 하려면 기능에 앱 참여가 필요합니다. 앱은 사용자 설정에 따라 초기화를 수행할 ID를 지정할 수 있습니다. 앱에서 지정된 이러한 사용자 설정이 없을 경우 기본 동작은 응용 프로그램 디렉터리를 초기화하고 최종 사용자에게 회사 리소스 액세스가 제거되었음을 알리는 것입니다. 

## Managed Browser 사용 적용
IT 관리자는 Intune 관리 앱 내에서 링크를 열 때 Managed Browser를 사용하도록 적용할 수 있습니다. Microsoft Intune Managed Browser를 사용하면 Intune 관리되는 메일 클라이언트의 메일에 표시되는 링크가 Intune 관리 앱의 도메인 내에 유지됩니다.

## PIN 정책 적용
IT 관리자는 Intune 관리 앱을 시작할 때 PIN 정책을 적용할 수 있습니다. 이 정책은 Microsoft Intune에 장치를 등록한 최종 사용자가 앱을 시작하는 개인과 동일한지 확인하는 데 도움이 됩니다. 최종 사용자가 해당 PIN을 구성할 때 Intune 앱 SDK는 Azure Active Directory를 사용하여 장치 등록 자격 증명과 최종 사용자의 자격 증명을 비교합니다. 

## 사용자가 앱을 시작하기 전에 자격 증명을 입력하도록 요구
IT 관리자는 사용자가 Intune 관리 앱을 시작하기 전에 자격 증명을 입력하도록 요구할 수 있습니다. Intune 앱 SDK는 Azure Active Directory를 사용하여 입력된 자격 증명이 후속 로그인에 다시 사용되는 Single Sign-On 환경을 제공합니다. ID 관리 솔루션 [Azure Active Directory와 페더레이션](https://msdn.microsoft.com/en-us/library/azure/jj679342.aspx)의 인증도 지원됩니다. 

## 장치 상태 및 규정 준수 확인
IT 관리자는 최종 사용자가 Intune 관리 앱에 액세스하기 전에 장치 상태 및 회사 정책 준수를 확인할 수 있습니다. iOS 플랫폼에서 이 정책은 장치가 무단 해제되었는지 확인합니다. Android 플랫폼에서 이 정책은 장치가 루팅되었는지 확인합니다.  





<!--HONumber=Jun16_HO4-->


