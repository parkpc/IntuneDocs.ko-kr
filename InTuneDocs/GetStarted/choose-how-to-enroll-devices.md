---
# required metadata

title: モバイル デバイスの登録方法の選択 | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 06/06/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: cac62b64-3f8b-47ae-aa66-970c7ba15466

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: damionw
#ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# モバイル デバイスの登録方法の選択

モバイル デバイス登録は、スマートフォン、タブレット、PC を Microsoft Intune で管理できるようにするためのプロセスです。 管理者は、デバイスの最適な登録方法を次の基準で決定する必要があります。

 -  所有権 (個人所有と 会社所有)
 -  使用方法 (共有と 個人使用)
 -  プラットフォーム (iOS、Android、Windows Phone、Windows PC、Mac PC)

次の質問に答えることで、管理するデバイスの最適な登録方法が決まります。

## デバイスは社員が自分のものを持ち込みますか。それとも、会社が提供しますか。

  **ユーザーが所有するデバイス** - "BYOD” (Bring Your Own Device) 登録 – ユーザーは自分のデバイスに Intune ポータル サイト アプリをインストールし、登録できます。電子メール、会社のアプリ、会社のデータ、サポートなど、会社のリソースにアクセスできます。  
  > [!div class="button"]   [BYOD 登録 >](..deploy-use/get-ready-to-enroll-devices-in-microsoft-intune)

  **会社所有のデバイス** -会社所有のデバイス (COD) を、会社のニーズや管理対象デバイスの種類に合わせ、さまざまな方法で登録できます。 次の質問...

## 会社所有デバイスを共有しますか。デバイスごとに利用者が登録されますか。

**会社所有のデバイスを共有** - デバイスの利用者が 1 名ではなく、通常、電子メールにアクセスできるように設定されません。 たとえば、キオスク デバイスやタスク指向デバイスなどがあります。利用者が必要に応じてプールから取り出し、利用後に返却します。 推奨される登録方法は、デバイスのプラットフォームにより異なります。

  - **Windows デバイスと Android デバイス** - *デバイス登録マネージャー*は、ポータル サイト アプリによるさまざまな共有デバイスの登録に利用できる Intune アカウントです。
  > [!div class="button"]   [デバイス登録マネージャー >](../deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

  - **iOS デバイス** - 共有する iOS デバイスを 3 通りの方法で管理できます。  **共有 iOS デバイスはどのような方法で登録しますか。**

    - **Apple のデバイス登録プログラム (DEP)** - DEP で購入し、管理している iOS デバイスが対象となります。登録プロファイルが利用されます。 利用者がデバイスの電源を初めて入れると、デバイスが DEP プロファイルをダウンロードし、プロファイル DEP で登録します。
    > [!div class="button"]     [DEP 登録 >](../deploy-use/ios-device-enrollment-program-in-microsoft-intune)

    - **Mac の Apple Configurator** - Apple Configurator は Mac PC で実行される Apple アプリケーションです。 USB ケーブルで iOS デバイスを Mac に接続し、デバイスに登録プロファイルをインストールできます。 デバイスを工場出荷時にリセットして登録できる場合、セットアップ アシスタント登録を使用します。 デバイスを工場出荷時にリセットしない場合、直接登録を使用します。

    > [!div class="button"]     [セットアップ アシスタント登録 >](../deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) または[直接登録 >](../deploy-use/ios-direct-enrollment-in-microsoft-intune)

    - **上記のいずれにも該当しない** - Apple の DEP も Apple Configurator も登録方法として利用できない、または利用が好ましくない場合、Intune のデバイス登録マネージャーを利用します。
    > [!div class="button"]     [DEM 登録 >](../deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).

**個別ユーザー** - ユーザーごとに支給される会社所有デバイスは会社の資産として追跡記録する必要があります。利用者は個人のデバイスとして電子メールやデータにアクセスできます。 推奨される登録方法は、デバイスのプラットフォームにより異なります。

  - **Windows デバイスと Android デバイス** - 会社所有デバイスの IMEI (携帯機器の国際的な識別番号) をインポートすることで、Intune でデバイスに会社所有のタグを付けることができます。 その後、ポータル サイトをインストールし、デバイスを個人デバイスとして登録し、電子メール、アプリ、データなど、会社のリソースにアクセスできます。
  > [!div class="button"]   [IMEI でタグ設定 >](../deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

  - **iOS デバイス** - 共有する iOS デバイスを 3 通りの方法で管理できます。  **共有 iOS デバイスはどのような方法で登録しますか。**

    - **Apple のデバイス登録プログラム (DEP)** - DEP で購入し、管理している iOS デバイスが対象となります。登録プロファイルが利用されます。 利用者がデバイスの電源を初めて入れると、デバイスが DEP プロファイルをダウンロードし、プロファイルに基づいて登録されます。
    > [!div class="button"]     [DEP 登録](../deploy-use/ios-device-enrollment-program-in-microsoft-intune).

    - **Mac の Apple Configurator** - Apple Configurator は Mac PC で実行される Apple アプリケーションです。 USB ケーブルで iOS デバイスを Mac に接続し、デバイスに登録プロファイルをインストールできます。 デバイスを工場出荷時にリセットして登録できる場合、セットアップ アシスタント登録を使用します。

    デバイスを工場出荷時にリセットしない場合、直接登録を使用します。
    デバイスを工場出荷時にリセットして登録できる場合、セットアップ アシスタント登録を使用します。
    > [!div class="button"][iOS セットアップ アシスタント登録](../deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [!div class="button"][iOS 直接登録](../deploy-use/ios-direct-enrollment-in-microsoft-intune).

    - **上記のいずれも** - Apple の DEP も Apple Configurator も登録方法として利用できない、または利用が好ましくない場合、会社所有デバイスの IMEI (携帯機器の国際的な識別番号) をインポートすることで、Intune でデバイスに会社所有のタグを付けることができます。 その後、ポータル サイトをインストールし、デバイスを個人デバイスとして登録し、電子メール、アプリ、データなど、会社のリソースにアクセスできます。 > [!div class="button"][IMEI 番号を使用したデバイスへのタグ付け](../deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)


<!--HONumber=Jun16_HO1-->


