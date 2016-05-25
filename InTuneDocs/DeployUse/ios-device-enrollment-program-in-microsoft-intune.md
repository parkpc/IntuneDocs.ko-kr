---
# required metadata

title: Microsoft Intune を使用した iOS デバイスの Apple DEP 管理 | Microsoft Intune
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

# 会社所有のデバイス登録プログラムによる iOS デバイスの登録
Microsoft Intune は、"無線" で Device Enrollment Program (DEP) を通じて購入した iOS デバイスを登録する登録プロファイルを展開できます。 登録パッケージには、デバイスのセットアップ アシスタント オプションを含めることができます。 DEP を使用して登録したデバイスの場合は、ユーザーが登録を解除することはできません。

## Microsoft Intune を使用した iOS デバイスの Apple DEP 管理
Apple の Device Enrollment Program (DEP) を使用して企業所有の iOS デバイスを管理するには、組織が Apple DEP に参加し、そのプログラムを使用してデバイスを取得する必要があります。 そのプロセスの詳細については、  [https://deploy.apple.com](https://deploy.apple.com)を参照してください。 このプログラムの利点には、各デバイスをコンピューターに USB 接続することなく、デバイスを楽に設定できる点があります。

DEP に企業所有の iOS デバイスを登録するには、Apple の DEP トークンが必要です。 このトークンにより、Intune は企業所有の DEP 参加デバイスに関する情報を同期できるようになります。 また、Intune は Apple への登録プロファイルのアップロードを実行して、デバイスをそれらのプロファイルに割り当てられるようになります。

1.  **Microsoft Intune で iOS デバイスの管理を始める**
    iOS Device Enrollment Program (DEP) デバイスを登録する前に、まず、Intune の iOS 管理を有効にする必要があります。

2.  **暗号化キーを取得する**
    管理者ユーザーとして、[Microsoft Intune の管理コンソール](http://manage.microsoft.com)を開き、**[管理者]** &gt; **[モバイル デバイス管理]** &gt; **[iOS]** &gt; **[デバイス登録プログラム]** の順に移動して、**[暗号化キーのダウンロード]** をクリックします。 暗号化キー (.pem) ファイルをローカルに保存します。 .pem ファイルは、Apple Device Enrollment Program ポータルから信頼関係証明書を要求するために使用します。

      ![Device Enrollment Program のトークンの更新](../media/dev-sa-ios-dep.png)

3.  **Device Enrollment Program のトークンを取得する**
    [Device Enrollment Program ポータル](https://deploy.apple.com) (https://deploy.apple.com) に移動し、会社の Apple ID でサインインします。 この Apple ID は、将来 DEP トークンを更新するために使用する必要があります。

    1.  [Device Enrollment Program ポータル](https://deploy.apple.com)で、**[Device Enrollment Program]** &gt; **[Manage Servers]** の順に移動し、**[Add MDM Server]** をクリックします。.

    2.   **MDM サーバー名** を入力し、[ **Next**] をクリックします。 サーバー名は、自分が MDM サーバーを識別できるようにするための名前です。 Microsoft Intune サーバーの名前または URL ではありません。

    3.  **[Add &lt;ServerName&gt;]** ダイアログ ボックスが開きます。 **[Choose File…]** をクリックして .pem ファイルをアップロードし、**[Next]** をクリックします。.

    4.  **[Add &lt;ServerName&gt;]** ダイアログ ボックスに、**[Your Server Token]** リンクが表示されます。 サーバー トークン (.p7m) ファイルをコンピューターにダウンロードしたら、**[Done]** をクリックします。.

    この証明書 (.p7m) ファイルは、Intune と Apple の Device Enrollment Program サーバーとの間に信頼関係を確立するために使用されます。

4.  **Intune に DEP トークンを追加する**
    [Microsoft Intune 管理コンソール](http://manage.microsoft.com)で、**[管理者]** &gt; **[モバイル デバイス管理]** &gt; **[iOS]** &gt; **[デバイス登録プログラム]** に進み、[**DEP トークンのアップロード]** をクリックします。. 証明書 (.p7m) ファイルを **[参照]** して、**[Apple ID]** を入力し、**[アップロード]** をクリックします。.

5.  **業務用デバイスの登録ポリシーを追加する**
    [Microsoft Intune 管理コンソール](http://manage.microsoft.com)で、**[ポリシー]** &gt; **[業務用デバイスの登録]** に移動し、**[追加]** をクリックします。  **[全般]** の詳細 ( **[名前]** や **[説明]**など) を入力し、プロファイルに割り当てられたデバイスがユーザー アフィニティを持つかグループに属するかを指定して、 **[このポリシーのデバイス登録プログラムの設定を構成します]** を有効にして、DEP をサポートします。  **[セットアップ アシスタント]** ウィンドウでは、セットアップ中に構成する iOS デバイスの設定を定義します。

      ![[セットアップ アシスタント] ウィンドウ](../media/pol-sa-corp-enroll.png)

6.  **管理対象の DEP デバイスを割り当てる**
    [Device Enrollment Program ポータル](https://deploy.apple.com) (https://deploy.apple.com) に移動し、会社の Apple ID でサインインします。 **[Deployment Program]** &gt; **[Device Enrollment Program]** &gt; **[Manage Devices]** に移動します。  **デバイスの選択**方法を指定し、デバイス情報を入力して、デバイスの **シリアル番号**、 **注文番号**、または **CSV ファイルのアップロード**で詳細を指定します。 次に、**[Assign to Server]** を選択し、Microsoft Intune に指定した &lt;ServerName&gt; を選択して、**[OK]** をクリックします。.

7.  **DEP 管理対象デバイスを同期する**
    管理者ユーザーとして、[Microsoft Intune 管理コンソール](http://manage.microsoft.com)を開き、**[管理者]** &gt; **[モバイル デバイス管理]** &gt; **[iOS]** &gt; **[デバイス登録プログラム]** に移動して、**[今すぐ同期]** をクリックします。 同期要求が Apple に送信されます。 同期後に DEP 管理対象デバイスを表示するには、[Microsoft Intune 管理コンソール](http://manage.microsoft.com)で、**[グループ]** &gt; **[会社が所有しているすべてのデバイス]** に移動します。 デバイスの電源を入れ、セットアップ アシスタントを実行して、デバイスを登録するまで、**[会社が所有しているデバイス]** ワークスペースには管理対象デバイスの **[状態]** が "未接続" と表示されます。

    許容される DEP トラフィックについての Apple の規約に準拠するため、Intune では次の制限が課せられます。
     -  完全な DEP 同期は 7 日ごとに 1 回以上実行できません。 完全同期時に、Intune は Apple が Intune に割り当てたすべてのシリアル番号を、シリアルが以前に同期されているかどうかに関係なく更新します。 前回の完全同期の 7 日以内に完全同期が試みられると、Intune は Intune にまだ一覧表示されていないシリアル番号のみを更新します。
     -  すべての同期要求は、完了までに 10 分与えられます。 この時間中または要求が成功するまで、[同期] ボタンは無効にされます。

8.  **デバイスをユーザーに配布する**
    これで、会社が所有するデバイスをユーザーに配布できるようになりました。 iOS デバイスの電源をオンにすると、iOS デバイスが Intune の管理対象として登録されます。



### 関連項目
[デバイスの登録の準備](get-ready-to-enroll-devices-in-microsoft-intune.md)


<!--HONumber=May16_HO1-->


