---
title: "新機能 | Microsoft Intune"
description: "Microsoft Intune の今月の新機能と過去のリリースの情報について説明します"
keywords: 
author: Lindavr
manager: jeffgilb
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b8bff8951c8ced7656f007787d614fd277401fd0
ms.openlocfilehash: 35612b07cf18d8038af51cdfac5146b9e8a876fc


---

# Microsoft Intune の新機能
Microsoft Intune の今回のリリースの新機能について説明します。 また、過去のリリースに関する情報だけでなく、準備する必要がある今後の変更についても説明します。

Intune に関して以下の機能が現在開発されています。 これらのすべての機能は、最終的にハイブリッド環境 (Configuration Manager と Intune の共存環境) でサポートされるようになります。 最新のハイブリッド機能の詳細については、[ハイブリッド環境の新機能に関するページ](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx)を参照してください。


## 2016 年 7 月
## アプリ管理
### アプリのプロビジョニング プロファイルの更新エクスペリエンスを向上
Apple iOS 基幹業務モバイル アプリは、プロビジョニング プロファイルを含み、証明書で署名されたコードと共に構築されます。 iOS デバイスでアプリを実行すると、iOS により iOS アプリの整合性の確認と、プロビジョニング プロファイルで定義されたポリシーの施行が行われます。

アプリの署名に使用するエンタープライズ署名証明書は、通常 3 年間は継続します。 ただし、プロビジョニング プロファイルは 1 年後に期限が切れます。 この更新により、証明書がまだ有効である期間中、Intune には、有効期限が近づいているアプリを持つデバイスに新しいプロビジョニング プロファイルのポリシーを事前に展開するツールが用意されます。 詳細については、「[Use iOS mobile provisioning profile policies to keep your line of business apps up to date (基幹業務アプリケーションを常に最新の状態に保つために iOS モバイル プロビジョニング プロファイル ポリシーを使用する)](/intune/deploy-use/ios-mobile-app-provisioning-profiles)」を参照してください。
<!--- TFS 1280247--->
### Intune アプリ用の Xamarin SDK の提供開始
Intune アプリ SDK Xamarin コンポーネントを使用すると、Xamarin でビルドされたモバイル iOS および Android アプリで Intune のモバイル アプリ管理機能を有効にすることができます。 [Xamarin ストア](https://components.xamarin.com/view/Microsoft.Intune.MAM)または、[Microsoft Intune の Github ページ](https://github.com/msintuneappsdk)でコンポーネントを見つけることができます。
<!--- TFS 1061478 --->

## デバイス管理
### デバイス登録数上限の増加
Intune は、構成可能なデバイスの最大登録数をユーザーごとに 5 から 15 デバイスまで増加しました。
<!---TFS 1289896 --->



## ポータル サイトの更新
### ポータル Web サイト
- **Windows デバイス登録時のエンドユーザー エクスペリエンスの向上**<br/>
条件付きアクセスを使用している場合の、ポータル サイト Web サイトで Windows 8.1、Windows 10 デスクトップ、および Windows 10 Mobile の登録手順が明確化されました。 今後は、「デバイス登録」および「社内参加」の手順が個別に表示されます。そのため、社内参加 (WPJ) の失敗後にデバイスの状態を確認し プロセスを完了することが簡単になります。 この手順の分離により、IT 管理者のトラブルシューティングのプロセスも簡略化されることが見込まれます。 これまで、エンド ユーザーが登録しようとして、WPJ を除くすべての登録が成功した場合、登録されたデバイスがデバイス一覧に表示されないため識別できず、ユーザーの混乱の原因となっていました。

### Android
- **Android 用ポータル サイト アプリ**<br/>
Android エンド ユーザーに自分のデバイスに必要な証明書がないことを示すエラー メッセージが表示される場合、[How to resolve this] (この問題解決する方法) ボタンをタップすると、欠落している証明書をインストールするための[手順](/intune/enduser/your-device-is-missing-a-required-certificate-android#your-device-is-missing-a-certificate-required-by-your-it-administrator)を取得できます。 ユーザーが手順を完了しても、追加の「証明書が見つかりません」というエラー メッセージが表示される場合は、IT 管理者に連絡し、この[リンク](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#android-certificate-issues)を提供することが求められます。このリンクには、証明書の問題を解決するために IT 管理者が使用できる手順が含まれています。

- **登録済みデバイスへのサイド ロード アプリのインストールの制限**<br/>
Android 用 Intune ポータル サイト アプリを使用してデバイスを Intune に登録している場合を除き、Android デバイスは、ポータル サイト Web サイトを通じてアプリケーションをインストールすることができなくなります。
<!---TFS 1299082--->

### iOS
- **iOS ポータル サイト アプリのデバイス登録マネージャー アカウントへの変更**<br/>
パフォーマンスと拡張性を高めるために、Intune において、iOS のポータル サイト アプリの [**デバイス**] ウィンドウには今後、デバイス登録マネージャー (DEM) のデバイスの一部が表示されなくなります。 アプリを実行しているローカル デバイスのみ、ポータル サイト アプリ経由で登録されている場合にだけ表示されます。

    ローカル デバイスに対する操作は DEM で実行できますが、他の登録デバイスのリモート管理は、Intune 管理コンソールから実行する必要があります。 また、Apple Device Enrollment Program または Apple Configurator ツールでの DEM アカウントの使用は廃止されます。 共有 iOS デバイスに関しては、どちらの登録手段も既にユーザーレスの登録がサポートされています。

    共有デバイスのユーザーレスの登録が利用できない場合のみ DEM アカウントを使用してください。 詳細については、「[Microsoft Intune のデバイス登録マネージャーを使用した企業所有のデバイスの登録](https://docs.microsoft.com/en-us/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)」を参照してください。
<!---TFS 1233681--->

## Windows 機能の名前の変更
- [Microsoft Passport for Windows](/intune/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune) は **Windows Hello for Business** と呼ばれるようになりました。
- [エンタープライズ データ保護](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune)は **Windows Information Protection** と呼ばれるようになりました。

## 今後の更新情報
### Intune グループから Azure Active Directory グループへの移行 (2016年 8 月以降)
Intune は、Azure Active Directory (AAD) のセキュリティ グループを使用する、新しいグループ管理エクスペリエンスを作成しています。 これらの Azure AD ベースのセキュリティ グループは、ユーザーとデバイスの両方を含めることができ、新しい Azure ベースの Intune 管理ポータルの導入時に、すべてのグループの管理、ポリシーの展開、およびプロファイルの展開に使用されます。

この新しいエクスペリエンスによって、以下のことが実現します。
- サービス間でグループを複製する必要から解放されます。
- 新しい Azure Active Directory Premium (AADP) グループ機能の一部を利用できます。
- PowerShell および Graph を使用して拡張機能を提供します。
- エンタープライズ モビリティ管理で、グループ管理のエクスペリエンスが統合されます。

セキュリティ グループへの移行を有効にするため、現在の管理コンソールのエクスペリエンスにいくつかの変更が施されます。 これらの変更と、Azure AD セキュリティ グループの使用は、Intune のドキュメントに記録されます。

Intune の新規のお客様には、現在のテナントに表示される前に、セキュリティ グループの変更の一部が表示されます。

グループ管理の変更に加えて、次の機能が廃止される予定です。
- 新規グループ作成時のメンバーまたはグループの除外
- **グループ化を解除されたユーザー**と**グループ化を解除されたデバイス**のグループ
- サービス管理者の役割での**グループの管理**
- 通知ルールに対するカスタム グループベースの警告
- レポート内のグループのピボット

これら機能廃止を緩和する方法の詳細については、8 月にリリースされます。

### Android 用ポータル サイトへの '通知' の追加
Microsoft は、Android 用ポータル サイトに対する更新を 8 月にリリースし、ホームページ上に新しい**通知**アイコンを導入します。 このアイコンをタップすると、**通知**ページにアクセスし、デバイスのコンプライアンス非対応、登録の更新、および登録のアクティブ化などのポータル サイト アプリで注意が必要なすべての項目をエンド ユーザーに表示します。 iOS 用ポータル サイト アプリも使用している場合は、通知エクスペリエンスがすでに表示されます。 **通知**ページの導入に伴い、デバイスがすでに登録されている限り、Android 用ポータル サイトを起動または再開するたびに**会社アクセスのセットアップ**ページが表示されることはなくなります。 Microsoft は、多くのお客様がエンドユーザー ガイダンスを作成していることを把握しており、ガイダンスとスクリーンショットの更新が必要になる場合に事前に通知くださることに感謝いたします。 ドキュメントに今後のエクスペリエンスの変更を反映し、更新してください。 最新のスクリーンショットは、 https://aka.ms/androidcpupdate でご確認いただけます。  



### クラウドのロードマップ
[クラウド プラットフォームのロードマップ](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)では、Intune の今後の開発に関する情報を入手できます。

### 廃止予定のサービス
- **iOS ポータル サイト アプリのサポートの変更**<br/>
7 月には、iOS 用 Microsoft Intune ポータル サイト アプリのすべてのユーザーが、アプリの最新バージョンを使用するように要求されます。 新しいユーザーは最新バージョンのみをダウンロードでき、現在のユーザーは最新バージョンへの更新を求められます。 最新バージョンを使用するには iOS 8.0 以降が必要であり、デバイスで以前の iOS バージョンを実行している場合は、デバイスを iOS 8.0 以降に更新したうえでポータル サイト アプリを最新バージョンに更新するまで、ポータル サイトを使用できず、登録することもできません。 iOS 8.0 以前のバージョンを実行している登録済みのデバイスは、引き続き管理対象であり、Intune 管理コンソールに表示されます。  

- **iOS Managed Browser の最小バージョンの 8.0 への更新**<br/>
8 月、Intune は iOS 8.0 以降を実行するデバイスのみをサポートする、iOS 用の最新の Microsoft Intune Managed Browser アプリをリリースします。 iOS 7.1 デバイスでは、既存の Managed Browser アプリを使用することができますが、新しい Managed Browser の機能にアクセスしてフル活用できるように、ユーザーに iOS 8.0 以降に更新することをお勧めしてください。  
<!---TFS 1313253--->

- **Windows 8 および Windows Phone 8 用のポータル サイト アプリは、2016 年 9 月以降非推奨になります** <br/>
Microsoft Intune は、2016 年 9 月以降、Windows Phone 8 および Windows 8 プラットフォーム用 Microsoft Intune ポータル サイト アプリのサポートを終了します。 デバイスを Windows 8.1 および Windows Phone 8.1 に更新し、対応する Windows 8.1 および Windows Phone 8.1 のポータル サイト アプリを使用して、更新したデバイスへのアプリの配布を続行します。
<!---TFS 1255391--->

- **Intune Viewer アプリ** <br/>
新しい RMS 共有アプリのリリースに伴い、2016 年 8 月以降、次の Intune Viewer アプリを削除する予定です。
    - Intune AV Viewer
    - Intune PDF Viewer
    - Google Play の Android 用 Intune Image Viewer

  Intune Viewer アプリを使用する代わりに、[Android 用の新しい Rights Management アプリ (RMS 共有) ](https://docs.microsoft.com/en-us/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app)を使用することをお勧めします。そうすることで、3 つのアプリを個別にではなく、1 つのアプリを展開して、Android デバイス上の企業ファイルを安全に表示することができます。 Intune Viewer アプリがサポートされなくなると、Google ストアから削除され、その後使用することができなくなります。

<!--- - **Custom Group Targeting of Notification Rules Removal.**<br/>
Intune notification rules define who an email alert will be sent to from Intune. Currently, you can configure notification rules to send emails to all users of devices in an Intune device group that you created. From around June 1st 2016 moving forward, targeting user-created groups will no longer be supported.

    Today, to target a notification rule to a group you created from the Microsoft Intune administration console, you would take the following steps:

    In the **Admin** workspace, click **Notification Rules** > **Create New Rule**

    In step two of the Create Notification Rule Wizard, select the device groups which the rule will target. This step, “select device groups”, is being removed from the Intune Console.

    The preliminary timeline for this change is as follows:
    - In August, 2016, new tenants will not see step two of the Create Notification Rule Wizard. Exiting tenants are unaffected.
    - Around September, 2016, some existing tenants will not see the “select device groups” in the wizard.
    - Around November, 2016, we expect that all tenants will not see the “select device groups” in the wizard.

--->



## 以前の Intune のリリース
過去 6 か月間に公開された Intune のリリースについては、「[以前の Intune のリリース](previous-intune-releases.md)」の記事をご覧ください。

### 関連項目
* [Microsoft Intune のブログ](http://go.microsoft.com/fwlink/?LinkID=273882)
* [クラウド プラットフォームのロードマップ](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)



<!--HONumber=Jul16_HO3-->


