---
# required metadata

title: Microsoft Intune の Windows 10 ポリシー設定 | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 00a602d9-b339-4fd8-ab70-defbf6686855

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune の Windows 10 ポリシー設定

このトピックのポリシー設定の一覧を、登録済みの Windows 10 デスクトップおよび Windows 10 Mobile デバイスの設定構成に役立ててください。

## 全般構成ポリシーの設定

Windows 10 用の Microsoft **全般構成ポリシー**を使用して、登録済みの Windows 10 デスクトップおよび Windows 10 Mobile デバイスの全般設定を構成します。


### パスワード

|設定の名前|説明|[Windows] 10 Desktop|[Windows] 10 Mobile|
|----------------|----------------------|---------------------|
|**デバイスのロック解除にパスワードを必要とする**|サポート対象デバイスのパスワードが必要です。|○|○|
|**必要なパスワードの種類**|数値のみや英数字など、必要なパスワードの種類を指定します。|○|○|
|**必要なパスワードの種類** - **文字セットの最小数**|文字セットには、小文字、大文字、数字、および記号の 4 種類があります。 この設定では、パスワードに含める必要がある文字セットの数を指定します。|○|○|
|**パスワードの最小文字数**|デバイスのパスワードに含める必要がある最小文字数を指定します。|×|○|
|**デバイスをワイプするまでの連続サインイン エラーの数**|ログインの試みがこの回数だけ失敗した場合は、デバイスがワイプされます。|○|○|
|**画面がオフになるまでの非アクティブな時間 (分)**|デバイスがどれだけの時間アイドル状態であると、画面がロックされるかを指定します。|○|○|
|**パスワードの有効期限 (日数)**|デバイスのパスワードを設定後、変更が必要になるまでの日数を指定します。|○|○|
|**パスワードの履歴を記憶する**|エンド ユーザーに対して、以前に使用されたことのあるパスワードの作成を制限するかどうかを指定します。|○|○|
|**パスワードの履歴を保存する** - **前のパスワードを再利用できないようにする**|デバイスで記憶される、以前に使用したパスワードの数を指定します。|○|○|
|**ピクチャ パスワードと PIN を許可する**|画像に対するシンプルなジェスチャまたはシンプルな PIN でログインできるようにします。|○|×|
|**デバイスがアイドル状態から戻るときにパスワードを必須とする**|有効にすると、ユーザーはアイドル状態からデバイスのロックを解除するとき、パスワードを入力する必要があります。|×|○|

### 暗号化

|設定の名前|説明|[Windows] 10 Desktop|[Windows] 10 Mobile|
|----------------|----------------------|---------------------|
|**モバイル デバイスの暗号化を要求する**|対象デバイスの暗号化を有効にします。|×|○|

### システム

|設定の名前|説明|[Windows] 10 Desktop|[Windows] 10 Mobile|
|----------------|----------------------|---------------------|
|**画面のキャプチャを許可する**|ユーザーがデバイスの画面を画像としてキャプチャできるようにします。|いいえ|○|
|**手動での登録解除を許可する**|ユーザーがデバイスから会社アカウントを手動で削除できるようにします。|○|○|
|**ルート証明書の手動インストールを許可する**|ユーザーがルート証明書を手動でインストールできるかどうかを指定します。|×|○|
|**診断と利用状況データの Microsoft への送信を許可する**|デバイスから Microsoft に送信される、診断データと使用状況データの量を決定します。<br>**[いいえ]** - データは Microsoft に送信されません。<br>**[基本]** - 一部の情報のみを Microsoft に送信します。<br>**[拡張]** - より詳細な診断データを Microsoft に送信します。<br>**[完全 (推奨)]** - **[拡張]** で送信されるデータに加えて、デバイスの状態に関する追加データを送信します。|○|○|


### アカウントと同期

|設定の名前|説明|[Windows] 10 Desktop|[Windows] 10 Mobile|
|----------------|----------------------|---------------------|
|**Microsoft アカウントを許可する**|ユーザーがデバイスに Microsoft アカウントを関連付けられるようにします。|○|○|
|**Microsoft 以外のアカウントの手動追加を許可する**|Microsoft アカウントに関連付けられていないデバイスに、ユーザーが電子メール アカウントを追加できるようにします。|○|○|
|**Microsoft アカウントに対して設定同期を許可する**|Microsoft アカウントに関連付けられたデバイスとアプリの設定をデバイス間で同期できるようにします。|○|○|

### 電子メールの設定

|設定の名前|説明|[Windows] 10 Desktop|[Windows] 10 Mobile|
|----------------|----------------------|---------------------|
|**Windows メール アプリケーションで Microsoft アカウントをオプションにする**|Windows メールで Microsoft アカウントの使用を必須にしない場合に構成します。|○|いいえ|



### Microsoft Edge

|設定の名前|説明|[Windows] 10 Desktop|[Windows] 10 Mobile|
|----------------|----------------------|---------------------|
|**Web ブラウザーを許可する**|デバイスで Edge Web ブラウザーを使用できるようにします。|×|○|
|**アドレス バーで検索候補を許可する**|検索語句を入力したときに、検索エンジンからサイトが提案されるようになります。|○|○|
|**Internet Explorer へのイントラネット トラフィックの送信を許可する**|ユーザーが Internet Explorer でイントラネット Web サイトを開けるようになります。|○|×|
|**追跡禁止を許可する**|ユーザーがアクセスする Web サイトへ トラッキング拒否ヘッダーを送信できるように、Edge ブラウザーを構成します。|○|○|
|**SmartScreen を有効にする**|デバイスの SmartScreen ブラウザーの設定を有効にします。|○|○|
|**アクティブ スクリプティングを使用する**|JavaScript などのスクリプトが Edge ブラウザーで実行できるようにします。|○|○|
|**ポップアップを許可する**|ブラウザーのポップアップ ブロックを有効または無効にします。|○|×|
|**Cookie を使用する**|Cookie を使用するか、または無効にします。|○|○|
|**オートコンプリートを使用する**|ユーザーがブラウザーのオートコンプリートの設定を変更できるようにします。|○|×|
|**Password Manager を許可する**|Edge Password Manager 機能を有効または無効にします。|○|○|
|**エンタープライズ モード サイト リストの場所**|エンタープライズ モードで開く Web サイトの一覧を検索できる場所を指定します。 ユーザーは、この一覧を編集できません。|○|×|

### アプリ

|設定の名前|説明|[Windows] 10 Desktop|[Windows] 10 Mobile|
|----------------|----------------------|---------------------|
|**アプリケーション ストアを許可する**|ユーザーがデバイスからアプリ ストアにアクセスできるようにします。|×|○|



### 移動体通信

|設定の名前|説明|[Windows] 10 Desktop|[Windows] 10 Mobile|
|----------------|----------------------|---------------------|
|**データ ローミングを許可する**|データへのアクセス中にネットワーク間のローミングを許可します。|○|○|
|**移動体通信で VPN を許可する**|移動体通信ネットワークに接続したときに、デバイスが VPN 接続にアクセスできるようにするかどうかを制御します。|○|○|
|**移動体通信で VPN ローミングを許可する**|移動体通信ネットワークでのローミング中に、デバイスが VPN 接続にアクセスできるようにするかどうかを制御します。|○|○|

### ハードウェア

|設定の名前|説明|[Windows] 10 Desktop|[Windows] 10 Mobile|
|----------------|----------------------|---------------------|
|**カメラを許可する**|デバイスのカメラを使用できるようにするかどうかを指定します。|○|○|
|**リムーバブル記憶域を許可する**|SD カードなどの外部記憶装置をデバイスで使用できるようにするかどうかを指定します。|○|○|
|**Wi-Fi を許可する**|デバイスの Wi-Fi 機能の使用を許可します。|×|○|
|**インターネット共有を許可する**|デバイスでインターネット接続の共有を使用できるようにします。|○|○|
|**Wi-Fi の手動設定を許可する**|ユーザーが独自に Wi-Fi 接続を構成できるようにするか、Wi-Fi プロファイルで構成された接続のみを使用できるようにするかを制御します。|×|○|
|**無料 Wi-Fi スポットへの自動接続を許可する**|デバイスが無料の Wi-Fi ホットスポットに自動的に接続し、接続の使用条件に自動的に同意するようにします。|○|○|
|**位置情報を許可する**|デバイスが位置情報サービスの情報を使用できるかどうかを指定します。|○|○|
|**NFC を許可する**|デバイスが近距離無線通信機能を使用できるようにします。|○|○|
|**Bluetooth を許可する**|デバイスの Bluetooth 機能の使用を有効にします。|○|○|
|**Bluetooth 検出可能モードを許可する**|その他の Bluetooth 対応デバイスにより、デバイスが検出されるようにします。|○|○|
|**Bluetooth 広告を許可する**|デバイスが Bluetooth 経由で公開通知を受信できるようにします。|○|○|
|**Bluetooth 接続可能モードを許可する** **重要:** |この設定は、Windows 10 ではサポートされなくなったため、将来的に削除されます。|○|○|
|**電話リセットを許可する**|ユーザーがデバイスを工場出荷時設定にリセットできるかどうかを制御します。|○|○|
|**USB 接続を許可する**|デバイスが USB 接続を介して外部記憶域装置にアクセスできるかどうかを制御します。|○|○|
|**盗難防止モードを許可する**|Windows の盗難防止モードを有効にするかどうかを構成します。|○|○|

### 機能

|設定の名前|説明|[Windows] 10 Desktop|[Windows] 10 Mobile|
|----------------|----------------------|---------------------|
|**コピーと貼り付けを許可する**|デバイス上でのコピーと貼り付けの使用を有効または無効にします。|×|○|
|**音声録音を許可する**|デバイスの音声録音機能を有効または無効にします。|×|○|
|**Cortana を許可する**|Cortana による音声アシスタントを有効または無効にします。|○|○|
|**アクション センターの通知を許可する**|デバイス ロック画面上でのアクション センターの通知を有効または無効にします。|×|○|

### Defender

|設定の名前|説明|[Windows] 10 Desktop|[Windows] 10 Mobile|
|-|-|
|**リアルタイム監視を許可する**|マルウェアやスパイウェアなど、望ましくないソフトウェアについてのリアルタイム スキャンを有効にします。|○|×|
|**動作監視を許可する**|デバイス上で特定の既知のパターンで行われる疑わしい動作を、Defender がチェックできるようにします。|○|×
|**ネットワーク検査システムを有効にする**|ネットワーク検査システム (NIS) は、ネットワークを利用した悪用からデバイスを保護するのに役立ちます。NIS は、Microsoft Endpoint Protection Center で把握している脆弱性のシグネチャを使用して、悪意のあるトラフィックを検出し、ブロックします。|○|×
|**すべてのダウンロードをスキャンする**|Defender がインターネットからダウンロードされたすべてのファイルをスキャンするかどうかを制御します。|○|×
|**スクリプトのスキャンを許可する**|Defender が Internet Explorer で使用されているスクリプトをスキャンできるようにします。|○|×
|**ファイルとプログラムのアクティビティを監視する**|デバイス上のファイルとプログラムのアクティビティの監視を Defender に許可するには、この設定を有効にします。|○|×
|**解決済みマルウェアを追跡する日数**|指定した日数の間、Defender で解決済みマルウェアの追跡を続けられるようにし、以前に影響を受けたデバイスを手動でチェックできるようにします。 日数を **0** に設定すると、マルウェアは検疫フォルダーに残り、自動的に削除されなくなります。 |○|×
|**クライアント UI アクセスを許可する**|Windows Defender ユーザー インターフェイスをエンド ユーザーに対して非表示にするかどうかを制御します。<br>この設定の変更は、エンド ユーザーの PC が次に再起動されたときに有効になります。|○|×
|**毎日のクイック スキャンのスケジュール**|毎日のクイック スキャンが選択した時間に実行されるように、スケジュール設定できるようにします。|○|×
|**システム スキャンを予定に入れる**|システムのフル スキャンまたはクイック スキャンが選択した日時に定期的に実行されるように、スケジュール設定できるようにします。|○|×
|**スキャン中の CPU 使用率の制限**|スキャンに使用できる CPU の使用率を制限できるようにします (**1** から **100** まで)。)|○|×
|**アーカイブ ファイルをスキャンする**|Zip ファイルや Cab ファイルなどのアーカイブ済みのファイルを Defender がスキャンできるようにします。|○|×
|**電子メール メッセージをスキャンする**|デバイスに届いた電子メール メッセージを Defender が直ちにスキャンできるようにします。|○|×
|**リムーバブル ドライブをスキャンする**|USB スティックなどのリムーバブル ドライブを Defender がスキャンできるようにします。|○|×
|**マップされたネットワーク ドライブをスキャンする**|マップ済みネットワーク ドライブ上のファイルを Defender がスキャンできるようにします。<br>ドライブ上のファイルが読み取り専用である場合、Defender は検出したマルウェアを一切削除できません。|○|×
|**ネットワークの共有フォルダーから開いたファイルをスキャンする**|共有ネットワーク ドライブ上のファイルを Defender がスキャンできるようにします (UNC パスからアクセスされたファイルなど)。<br>ドライブ上のファイルが読み取り専用である場合、Defender は検出したマルウェアを一切削除できません。|○|いいえ
|**署名更新間隔**|Defender が新しいシグネチャ ファイルをチェックする間隔を指定します。|○|×
|**クラウド保護を許可する**|管理対象のデバイスからマルウェアのアクティビティに関する情報が Microsoft Active Protection Service に送信されるのを許可またはブロックします。 この情報は、将来的に本サービスの品質向上を目的として使用されます。|○|×
|**ユーザーにサンプルの提出を指示する**|悪意の有無を判断するために、Microsoft による詳しい分析が必要な可能性のあるファイルを、Microsoft に自動的に送信するかどうかを制御します。|○|×
|**スキャンまたはリアルタイム保護から除外するファイルとフォルダー**|**C:\Path** や **%ProgramFiles%\Path\filename.exe** などのファイルやフォルダーを、除外リストに 1 つ以上追加します。 これらのファイルとフォルダーは、リアルタイムまたはスケジュールされたスキャンの対象外となります。|○|×
|**スキャンの実行中、またはリアルタイム保護の使用時に除外するファイル拡張子**|**jpg** や **txt** などのファイル拡張子を、除外リストに 1 つ以上追加します。 これらの拡張子が付いたファイルは、リアルタイムまたはスケジュールされたスキャンの対象外となります。|○|×
|**スキャンの実行中、またはリアルタイム保護の使用時に除外するプロセス**|**.exe**、**.com**、**.scr** などの種類のプロセスを、除外リストに 1 つ以上追加します。 これらのプロセスは、リアルタイムまたはスケジュールされたスキャンの対象外となります。|○|×| 


### 更新プログラムの設定

|設定の名前|説明|[Windows] 10 Desktop|[Windows] 10 Mobile|
|----------------|---------------|----------------------|---------------------|
|**自動更新を直ちにインストールすることを許可する**|自動更新を許可するには、この設定を有効にします。 次に、以下のいずれかの設定を構成して、更新動作を制御します。<br /><br />**ダウンロードを通知する**<br /><br />**メンテナンス時刻に自動的にインストールする**<br /><br />**メンテナンス時刻に自動的にインストールし、再起動する**<br /><br />**スケジュールした時刻に自動的にインストールして再起動する** **注:** このオプションを選択した場合は、**[エンド ユーザーに通知を表示しない]** と **[スケジュールされた更新プログラムのインストール日を定義してください]** の設定も構成できます。.|○|×|

## カスタム ポリシー設定
Windows 10 および Windows 10 Mobile 用の Microsoft Intune **カスタム構成ポリシー**を使用して、Windows 10 および Windows 10 Mobile のデバイスで各機能の制御に使用できる OMA-URI (Open Mobile Alliance Uniform Resource Identifier) 設定を展開します。 これらの設定は、多くのデバイス製造元がデバイスの機能を制御するために使用する標準の設定です。

この機能は、Intune 全般構成ポリシーで構成できない Windows 10 設定を展開できるようにするためのものです。 これらのポリシーで構成できる設定については、「[Microsoft Intune ポリシーを使用してデバイスの設定と機能を管理する](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)」を参照してください。.

登録済みの Windows 10 デバイスで構成できる OMA-URI 設定のリストについては、このトピックで後ほど説明する、Windows 10 デバイスのカスタム URI 設定を参照してください。

### 全般設定

|設定の名前|説明|
    |----------------|--------------------|
    |**名前**|ポリシーの一意の名前を入力すると、Intune コンソール内で容易に識別できます。|
    |**説明**|ポリシーの概要や、ポリシーを特定するのに役立つその他の関連情報についての説明を入力します。|

### OMA-URI 設定

|設定の名前|説明|
    |--------|--------------------|
    |**設定の名前**|OMA-URI 設定の一意の名前を入力すると、設定リスト内で容易に識別できます。|
    |**設定の説明**|設定の概要と、それを特定するために役立つその他の関連情報についての説明を入力します。|
    |**データ型**|この OMA-URI 設定を指定する日付型を選択します。 次の中から選択します。<br /><br />-   **文字列型**<br />-   **文字列型 (XML)**<br />-   **日付と時刻**<br />-   **整数型**<br />-   **浮動小数点**<br />-   **ブール型**|
    |**OMA-URI (大文字と小文字を区別する)**|設定対象の OMA-URI を指定します。|
    |**値**|指定した OMA-URI に関連付ける値を指定します。|


## Windows 10 デバイスのカスタム URI 設定
このトピックでは、Microsoft Intune の **Windows 10 のカスタム ポリシー**で Windows 10 および Windows 10 Mobile デバイス用に構成できる設定を示します。.


> [!NOTE]
> 次の表の **[サポート]** 列には、次の値が使用されます。
> 
> -   **デスクトップ**: この設定は、Intune に登録されている Windows 10 Professional および Enterprise コンピューターのみをサポートします。
> -   **モバイル** : この設定は、Windows 10 Mobile デバイスのみをサポートします。
> -   **両方** : この設定は、デスクトップとモバイルの両方のデバイスをサポートします。
> 
> Windows のカスタム URI ポリシーを使用する場合は、すべてのデバイスが Intune に登録されている必要があります。

### ポリシー

|ポリシー名|[サポート]|説明|
|---------------|------------|-----------|
|**​Allow Auto Update**|デスクトップ|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Update/AllowAutoUpdate<br /><br />**データ型:** 整数<br /><br />**有効な値: 0** - **5**<br /><br />**既定値:** 1|
|**Schedule Install Day**|両方|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Update/ScheduledInstallDay<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0**: 毎日<br /><br />**1**: 日曜日<br /><br />**2**: 月曜日<br /><br />**3**: 火曜日<br /><br />**4**: 水曜日<br /><br />**5**: 木曜日<br /><br />**6**: 金曜日<br /><br />**7**: 土曜日<br /><br />**既定値:** 0|
|**Schedule Install Time**|両方|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Update/ScheduledInstallTime<br /><br />**データ型:** 整数<br /><br />**有効な値: 0** ～ **23** 時間 (0 は午前 0 時を指定)<br /><br />**既定値:** 3|
|**DeviceLock/AllowIdleReturnWithoutPassword**|モバイル|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/DeviceLock/AllowIdleReturnWithoutPassword<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0**: ユーザーはパスワードの猶予期間タイマーを設定できず、値は "毎回" に設定されます。<br /><br />**1**: ユーザーはパスワードの猶予期間タイマーを設定できます。<br /><br />**既定値:** 1|
|**WiFi/AllowWiFi**|モバイル|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/WiFi/AllowWiFi<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0**: **Wi-Fi 接続の使用**を許可しません。.<br /><br />**1**: **Wi-Fi 接続の使用を許可**します。.<br /><br />**既定値:** 1|
|**WiFi/AllowInternetSharing**|両方|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/WiFi/AllowInternetSharing<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : インターネット共有を許可しません。<br /><br />**1** : インターネット共有を許可します。<br /><br />**既定値:** 1|
|**WiFi/AllowAutoConnectToWiFiSenseHotspots**|両方|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/WiFi/AllowAutoConnectToWiFiSenseHotspots<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />**1** : 許可します。<br /><br />**既定値:** 1|
|**WiFi/AllowManualWiFiConfiguration**|モバイル|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/WiFi/AllowManualWiFiConfiguration<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0**: MDM でプロビジョニングされていない Wi-Fi 接続を許可しません。<br /><br />**1** : MDM で既にプロビジョニングされたネットワーク SSID 以外の新しいネットワーク SSID の追加を許可します。<br /><br />**既定値:** 1|
|**System/AllowLocation**|両方|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/System/AllowLocation<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />**1** : 許可します。<br /><br />**既定値:** 1|
|**System/AllowTelemetry**|両方|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/System/AllowTelemetry<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません (Enterprise のみの設定)<br /><br />**1** : 制限あり<br /><br />**2** : すべて<br /><br />**3**: すべてと診断情報<br /><br />**既定値:** 2|
|**System/AllowExperimentation**|両方|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/System/AllowExperimentation<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />**1**: 設定のみ<br /><br />**2**: 設定と実験<br /><br />**既定値:** 1|
|**Security/AntiTheftMode**|モバイル|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Security/AntiTheftMode<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0**: 盗難防止モードを許可しません。<br /><br />**1** : ユーザーの設定<br /><br />**既定値:** 1|
|**Connectivity/AllowUSBConnection**|モバイル|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowUSBConnection<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />**1** : 許可します。<br /><br />**既定値:** 1|
|**System/AllowUserToResetPhone**|モバイル|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/System/AllowUserToResetPhone<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />**1** : 許可します。<br /><br />**既定値:** 1|
|**Connectivity/AllowCellularDataRoaming**|両方|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowCellularDataRoaming<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />**1** : 許可します。<br /><br />**既定値:** 1|
|**Connectivity/AllowVPNOverCellular**|両方|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNOverCellular<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0**: VPN で携帯電話による接続を許可しません。<br /><br />**1** : VPN で携帯電話を含む任意の接続を使用できます。<br /><br />**既定値:** 1|
|**Connectivity/AllowVPNRoamingOverCellular**|モバイル|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />**1** : 許可します。<br /><br />**既定値:** 1|
|**Connectivity/AllowVPNRoamingOverCellular**|モバイル|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />**1** : 許可します。<br /><br />**既定値:** 1|
|**Connectivity/AllowBluetooth**|両方|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowBluetooth<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0**: ユーザーが Bluetooth を有効にすることを許可しません。<br /><br />**1**: 予約済み。 ユーザーが Bluetooth を有効にして構成することができます (Windows Phone 8.1 (MDM または EAS 対応)、Windows 10 デスクトップ、Windows 10 Mobile ではサポートされていません)。<br /><br />**2**: 許可済み。 ユーザーが Bluetooth を有効にして構成することができます。<br /><br />**既定値:** 2|
|**Experience/AllowScreenCapture**|モバイル|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Experience/AllowScreenCapture<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />**1** : 許可します。<br /><br />**既定値:** 1|
|**Experience/AllowTaskSwitcher**|モバイル|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Experience/AllowTaskSwitcher<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />**1** : 許可します。<br /><br />**既定値:** 1|
|**Experience/AllowVoiceRecording**|モバイル|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Experience/AllowVoiceRecording<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />**1** : 許可します。<br /><br />**既定値:** 1|
|**Experience/AllowSyncMySettings**|モバイル|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Experience/AllowSyncMySettings<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : ローミングを許可しません。<br /><br />**1** : ローミングを許可します。<br /><br />**既定値:** 1|
|**Experience/AllowManualMDMUnenrollment**|両方|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Experience/AllowManualMDMUnenrollment<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />**1** : 許可します。<br /><br />**既定値:** 1|
|**Accounts/AllowMicrosoftAccountConnection**|両方|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Accounts/AllowMicrosoftAccountConnection<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />**1** : 許可します。<br /><br />**既定値:** 1|
|**Accounts/AllowAddingNonMicrosoftAccountsManually**|両方|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Accounts/AllowAddingNonMicrosoftAccountsManually<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />**1** : 許可します。<br /><br />**既定値:** 1|
|**Security/AllowManualRootCertificateInstallation**|モバイル|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Security/AllowManualRootCertificateInstallation<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />**1** : 許可します。<br /><br />**既定値:** 1|
|**Security/AllowAddProvisioningPackages**|両方|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Security/AllowAddProvisioningPackages<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />**1** : 許可します。<br /><br />**既定値:** 1|
|**Search/DisableBackoff**|両方|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Search/DisableBackoff<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0**<br /><br />**1**<br /><br />**既定値:** 0|
|**Search/PreventRemoteQueries**|両方|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Search/PreventRemoteQueries<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0**<br /><br />**1**<br /><br />**既定値:** 1|
|**Search/AllowUsingDiacritics**|両方|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Search/AllowUsingDiacritics<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0**<br /><br />**1**<br /><br />**既定値:** 0|
|**Search/AlwaysUseAutoLangDetection**|両方|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Search/AlwaysUseAutoLangDetection<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0**<br /><br />**1**<br /><br />**既定値:** 0|
|**Search/DisableRemovableDriveIndexing**|両方|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Search/DisableRemovableDriveIndexing<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0**<br /><br />**1**<br /><br />**既定値:** 0|
|**Search/PreventIndexingLowDiskSpaceMB**|両方|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Search/PreventIndexingLowDiskSpaceMB<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0**<br /><br />**1**<br /><br />**既定値:** 1|
|**Search/AllowIndexingEncryptedStoresOrItems**|両方|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Search/AllowIndexingEncryptedStoresOrItems<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0**<br /><br />**1**<br /><br />**既定値:** 0|
|**Security/AllowRemoveProvisioningPackage**|両方|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Security/AllowRemoveProvisioningPackage<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />**1** : 許可します。<br /><br />**既定値:** 1|
|**Security/RequireProvisioningPackageSignature**|両方|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Security/RequireProvisioningPackageSignature<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0**<br /><br />**1**<br /><br />**既定値:** 0|
|**AboveLock/AllowActionCenterNotifications**|両方|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/AboveLock/AllowActionCenterNotifications<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />**1** : 許可します。<br /><br />**既定値:** 1|
|**TextInput/AllowIMENetworkAccess**|デスクトップ|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/TextInput/AllowIMENetworkAccess<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />オープン拡張辞書がオフになります。<br /><br />ユーザーは次の操作を実行できません。<br /><br />新しいオープン拡張辞書を追加する<br /><br />新しい検索統合構成ファイルを追加する<br /><br />クラウドの候補機能を使用する<br /><br />ユーザーが登録した単語を送信する<br /><br />補足:<br /><br />このポリシー設定を有効にする前に追加されたオープン拡張辞書は、変換には使用されません。<br /><br />このポリシー設定を有効にする前にインストールされた検索統合構成ファイルは使用されません。<br /><br />**1**: 許可します。<br /><br />オープン拡張辞書を追加して、既定で使用できます。 既定で検索統合機能も使用できます。<br /><br />ユーザーは次の操作を実行できます。<br /><br />クラウドの候補機能を使用する<br /><br />ユーザーが登録した単語を送信する<br /><br />**既定値:**|
|**TextInput/AllowKoreanExtendedHanja**|デスクトップ|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/TextInput/AllowKoreanExtendedHanja<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />**1** : 許可します。<br /><br />**既定値:** 1|
|**TextInput/AllowIMELogging**|デスクトップ|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/TextInput/AllowIMELogging<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0**: 誤変換記録機能が無効になります。 自動的に調整されたデータおよび入力履歴データはファイルには保存されません。<br /><br />**1**: 誤変換記録機能が有効になります。 自動的に調整されたデータおよび入力履歴データはファイルに保存されます。<br /><br />**既定値:** 1|
|**TextInput/AllowJapaneseNonPublishingStandardGlyph**|デスクトップ|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseNonPublishingStandardGlyph<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />**1** : 許可します。<br /><br />**既定値:** 1|
|**TextInput/AllowJapaneseIVSCharacters**|デスクトップ|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIVSCharacters<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />**1** : 許可します。<br /><br />**既定値:** 1|
|**TextInput/AllowJapaneseUserDictionary**|デスクトップ|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseUserDictionary<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />**1** : 許可します。<br /><br />**既定値:** 1|
|**TextInput/AllowJapaneseIMESurrogatePairCharacters**|デスクトップ|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIMESurrogatePairCharacters<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />**1** : 許可します。<br /><br />**既定値:** 1|
|**TextInput/ExcludeJapaneseIMEExceptShiftJIS**|デスクトップ|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptShiftJIS<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0**: JIS の文字を除くすべての文字をフィルター処理します。<br /><br />**1**: 文字はフィルター処理されません。<br /><br />**既定値:** 1|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208**|デスクトップ|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0**: JIS0208 の文字を除くすべての文字をフィルター処理します。<br /><br />**1**: 文字はフィルター処理されません。<br /><br />**既定値:** 1|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC**|デスクトップ|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0**: JIS0208 の文字または外字の文字を除くすべての文字をフィルター処理します。<br /><br />**1**: 文字はフィルター処理されません。<br /><br />**既定値:** 1|
|**TextInput/AllowInputPanel**|デスクトップ|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/TextInput/AllowInputPanel<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />**1** : 許可します。<br /><br />**既定値:** 1|
|**Bluetooth/AllowDiscoverableMode**|両方|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Bluetooth/AllowDiscoverableMode<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />**1** : 許可します。<br /><br />**既定値:** 1|
|**Bluetooth/AllowAdvertising**|両方|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Bluetooth/AllowAdvertising<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />**1** : 許可します。<br /><br />**既定値:** 1|
|**Settings/AllowDataSense**|両方|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Settings/AllowDataSense<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />**1** : 許可します。<br /><br />**既定値:** 1|
|**Settings/AllowVPN**|両方|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Settings/AllowVPN<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />**1** : 許可します。<br /><br />**既定値:** 1|
|**Settings/AllowWorkplace**|デスクトップ|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Settings/AllowWorkplace<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />**1** : 許可します。<br /><br />**既定値:** 1|
|**Settings/AllowDateTime**|両方|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Settings/AllowDateTime<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />**1** : 許可します。<br /><br />**既定値:** 1|
|**Settings/AllowLanguage**|デスクトップ|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Settings/AllowLanguage<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />**1** : 許可します。<br /><br />**既定値:** 1|
|**Settings/AllowRegion**|デスクトップ|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Settings/AllowRegion<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />**1** : 許可します。<br /><br />**既定値:** 1|
|**Settings/AllowSignInOptions**|デスクトップ|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Settings/AllowSignInOptions<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />**1** : 許可します。<br /><br />**既定値:** 1|
|**Settings/AllowYourAccount**|両方|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Settings/AllowYourAccount<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />**1** : 許可します。<br /><br />**既定値:** 1|
|**Settings/AllowPowerSleep**|デスクトップ|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Settings/AllowPowerSleep<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />**1** : 許可します。<br /><br />**既定値:** 1|
|**Settings/AllowAutoPlay**|デスクトップ|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Settings/AllowAutoPlay<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />**1** : 許可します。<br /><br />**既定値:** 1|
|**Experience/AllowCortana**|両方|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Experience/AllowCortana<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />**1** : 許可します。<br /><br />**既定値:** 1|
|**Search/SafeSearchPermissions**|モバイル|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Search/SafeSearchPermissions<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 厳密。成人向けコンテンツに対して最高レベルのフィルター処理を実行します。<br /><br />**1** : 中程度。成人向けコンテンツに対して中程度のフィルター処理を実行します (有効な検索結果はフィルター処理されません)。<br /><br />**既定値:** 1|
|**Experience/AllowCopyPaste**|モバイル|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Experience/AllowCopyPaste<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />**1** : 許可します。<br /><br />**既定値:** 1|
|**Force Start Size**|モバイル|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Start/ForceStartSize<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0**: ユーザーによるサイズ変更を許可します。<br /><br />**1**: 非全画面表示を強制します。<br /><br />**2**: 全画面表示を強制します。<br /><br />**既定値:** 0|
|**Update/RequireDeferUpgrade**|両方|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Update/RequireDeferUpgrade<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0**: アップグレードを遅延せず、CB (現在のブランチ) を維持します。<br /><br />**1**: 更新とアップグレードの遅延を有効にします。デバイスは CBB (ビジネスの現在のブランチ) の規則に従います。<br /><br />**既定値: 0**<br /><br />詳細については、次をご覧ください。<br /><br />[Windows 10 サービスの概要](https://technet.microsoft.com/library/mt598226(v=vs.85).aspx)<br /><br />[Windows 10 の展開計画](https://technet.microsoft.com/library/mt574241(v=vs.85).aspx)|
|**Update/DeferUpdatePeriod**|両方|**説明:** ソフトウェアの更新を最大 4 週間遅延させるポリシー。<br /><br />**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Update/DeferUpdatePeriod<br /><br />**データ型:** 整数<br /><br />**有効な値:** 0: 更新を直ちに反映します。1 ～ 4: ソフトウェアの更新を遅延させる期間を指定します (週単位)。<br /><br />**既定値: 0**<br /><br /><br />詳細については、次をご覧ください。<br /><br />[Windows 10 サービスの概要](https://technet.microsoft.com/library/mt598226(v=vs.85).aspx)<br /><br />[Windows 10 の展開計画](https://technet.microsoft.com/library/mt574241(v=vs.85).aspx)|
|**Update/DeferUpgradePeriod**|両方|**説明:** 機能のアップグレードを最大 8 か月間遅延させるポリシー。<br /><br />**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Update/DeferUpgradePeriod<br /><br />**データ型:** 整数<br /><br />**有効な値:** 0: 更新を直ちに反映します。 1 ～ 8: 機能のアップグレードを遅延させる期間を指定します (月単位)。<br /><br />**既定値: 0**<br /><br />詳細については、次をご覧ください。<br /><br />[Windows 10 サービスの概要](https://technet.microsoft.com/library/mt598226(v=vs.85).aspx)<br /><br />[Windows 10 の展開計画](https://technet.microsoft.com/library/mt574241(v=vs.85).aspx)|
|**Update/PauseDeferrals**|両方|**説明:** CBB コンピューターが更新とアップグレードの受信を 5 週間停止できるようにします。 これは、更新プログラムに問題がある場合に使用してください。<br /><br />**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Update/PauseDeferrals<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0**: 直ちに更新プログラムを適用します (既定)。<br /><br />**1**: 更新とアップグレードを一時停止します (一時停止の期限は 5 週間です)。<br /><br />**既定値: 0**|

### Windows Defender

|ポリシー名|[サポート]|説明|
|---------------|------------|-----------|
|**AllowRealtimeMonitoring**|デスクトップ|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Defender/AllowRealtimeMonitoring<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />**1** : 許可します。<br /><br />**既定値:** 1|
|**AllowBehaviorMonitoring**|デスクトップ|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Defender/AllowBehaviorMonitoring<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />**1** : 許可します。<br /><br />**既定値:** 1|
|**AllowIntrusionPreventionSystem**|デスクトップ|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Defender/AllowIntrusionPreventionSystem<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />**1** : 許可します。<br /><br />**既定値:** 1|
|**AllowIOAVProtection**|デスクトップ|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Defender/AllowIOAVProtection<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />**1** : 許可します。<br /><br />**既定値:** 1|
|**AllowScriptScanning**|デスクトップ|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Defender/AllowScriptScanning<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />**1** : 許可します。<br /><br />**既定値:** 1|
|**AllowOnAccessProtection**|デスクトップ|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Defender/AllowOnAccessProtection<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />**1** : 許可します。<br /><br />**既定値:** 1|
|**RealTimeScanDirection**|デスクトップ|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Defender/RealTimeScanDirection<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0**: すべてのファイルを監視 (双方向)<br /><br />**1** : 受信ファイルの監視<br /><br />**2** : 送信ファイルの監視<br /><br />**既定値:** 0|
|**DaysToRetainCleanedMalware**|デスクトップ|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Defender/DaysToRetainCleanedMalware<br /><br />**データ型:** 整数<br /><br />**有効な値: 0** - **90**: マルウェアを保持する時間を表します。<br /><br />**既定値:** 0: 永続的に検疫フォルダー内に保持します。自動的に削除しません。|
|**AllowUserUIAccess**|デスクトップ|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Defender/AllowUserUIAccess<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />**1** : 許可します。<br /><br />**既定値:** 1|
|**ScanParameter**|デスクトップ|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Defender/ScanParameter<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**1** : クイック スキャン<br /><br />**2**: フル スキャン<br /><br />**既定値:** 1|
|**ScheduleScanDay**|デスクトップ|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Defender/ScheduleScanDay<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0**: 毎日<br /><br />**1**: 月曜日<br /><br />**2**: 火曜日<br /><br />**3**: 水曜日<br /><br />**4**: 木曜日<br /><br />**5**: 金曜日<br /><br />**6**: 土曜日<br /><br />**7**: 日曜日<br /><br />**8** : スキャンはスケジュールされません<br /><br />**既定値:** 0|
|**ScheduleScanTime**|デスクトップ|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Defender/ScheduleScanTime<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0**: 午前 12:00<br /><br />**60** : 午前 1:00<br /><br />**120** : 午前 2:00<br /><br />**180** : 午前 3:00<br /><br />**240** : 午前 4:00<br /><br />**300** : 午前 5:00<br /><br />**360** : 午前 6:00<br /><br />**420** : 午前 7:00<br /><br />**480** : 午前 8:00<br /><br />**540** : 午前 9:00<br /><br />**600** : 午前 10:00<br /><br />**660** : 午前 11:00<br /><br />**720** : 午後 0:00<br /><br />**780** : 午後 1:00<br /><br />**840** : 午後 2:00<br /><br />**900** : 午後 3:00<br /><br />**960** : 午後 4:00<br /><br />**1020** : 午後 5:00<br /><br />**1080** : 午後 6:00<br /><br />**1140** : 午後 7:00<br /><br />**1200** : 午後 8:00<br /><br />**1260** : 午後 9:00<br /><br />**1320** : 午後 10:00<br /><br />**1381** : メンテナンス期間<br /><br />**既定値:** 120|
|**ScheduleQuickScanTime**|デスクトップ|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Defender/ScheduleQuickScanTime<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0**: 午前 12:00<br /><br />**60** : 午前 1:00<br /><br />**120** : 午前 2:00<br /><br />**180** : 午前 3:00<br /><br />**240** : 午前 4:00<br /><br />**300** : 午前 5:00<br /><br />**360** : 午前 6:00<br /><br />**420** : 午前 7:00<br /><br />**480** : 午前 8:00<br /><br />**540** : 午前 9:00<br /><br />**600** : 午前 10:00<br /><br />**660** : 午前 11:00<br /><br />**720** : 午後 0:00<br /><br />**780** : 午後 1:00<br /><br />**840** : 午後 2:00<br /><br />**900** : 午後 3:00<br /><br />**960** : 午後 4:00<br /><br />**1020** : 午後 5:00<br /><br />**1080** : 午後 6:00<br /><br />**1140** : 午後 7:00<br /><br />**1200** : 午後 8:00<br /><br />**1260** : 午後 9:00<br /><br />**1320** : 午後 10:00<br /><br />**1380** : 午後 11:00<br /><br />**既定値:** 120|
|**AVGCPULoadFactor**|デスクトップ|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Defender/AVGCPULoadFactor<br /><br />**データ型:** 整数<br /><br />**有効な値: 0** - **100**<br /><br />**既定値:** 50|
|**AllowArchiveScanning**|デスクトップ|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Defender/AllowArchiveScanning<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />**1** : 許可します。<br /><br />**既定値:** 1|
|**AllowEmailScanning**|デスクトップ|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Defender/AllowEmailScanning<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />**1** : 許可します。<br /><br />**既定値:** 0|
|**AllowFullScanRemovableDriveScanning**|デスクトップ|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Defender/AllowFullScanRemovableDriveScanning<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />**1** : 許可します。<br /><br />**既定値:** 0|
|**AllowFullScanOnMappedNetworkDrives**|デスクトップ|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Defender/AllowFullScanOnMappedNetworkDrives<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />**1** : 許可します。<br /><br />**既定値:** 1|
|**AllowScanningNetworkFiles**|デスクトップ|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Defender/AllowScanningNetworkFiles<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />**1** : 許可します。<br /><br />**既定値:** 1 - "許可" に設定されている場合は、RTP がオンのときにも実行されます。|
|**SignatureUpdateInterval**|デスクトップ|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Defender/SignatureUpdateInterval<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 定期的に署名を確認しません。<br /><br />**1**: 1 時間ごとにシグネチャを確認します。<br /><br />**2** : 2 時間ごとに署名を確認します。3 以上の値も同様に、間隔を示します。<br /><br />**24** : 毎日署名を確認します。<br /><br />**既定値:** 8 - 8 時間ごとに署名を確認します。|
|**AllowCloudProtection**|デスクトップ|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Defender/AllowCloudProtection<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 許可しません。<br /><br />**1** : 許可します。<br /><br />**既定値:** 1|
|**SubmitSamplesConsent**|デスクトップ|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Defender/SubmitSamplesConsent<br /><br />**データ型:** 整数<br /><br />**有効な値:**<br /><br />**0** : 常に確認のメッセージを表示します。<br /><br />**1** : 安全なサンプルを自動的に送信します。<br /><br />**2** : 送信することはありません。<br /><br />**3** : すべてのサンプルを自動的に送信します。<br /><br />**既定値:** 0|
|**ExcludedExtensions**|デスクトップ|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Defender/ExcludedExtensions<br /><br />**データ型:** 文字列<br /><br />**有効な値:**<br /><br />*&lt;セミコロンで区切られた拡張子の一覧&gt;* 例:  **obj;lib**<br /><br />**既定値:** 除外される拡張子はありません。|
|**ExcludedPaths**|デスクトップ|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Defender/ExcludedPaths<br /><br />**データ型:** 文字列<br /><br />**有効な値:**<br /><br />*&lt;セミコロンで区切られたパスの一覧&gt;*<br /><br />例: **c:\test;c:\test1.exe**<br /><br />**既定値:** 除外されるパスはありません。|
|**ExcludedProcesses**|デスクトップ|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Defender/ExcludedProcesses<br /><br />**データ型:** 文字列<br /><br />**有効な値:**<br /><br />*&lt;セミコロンで区切られたパスの一覧&gt;*<br /><br />例: **c:\test.exe;c:\test1.exe**<br /><br />**既定値:** 除外されるプロセスはありません。|

### Edge ブラウザー

|ポリシー名|[サポート]|説明|
|---------------|------------|-----------|
|**ブラウズを許可する**|モバイル|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Browser/AllowBrowser<br /><br />**データ型:** 整数<br /><br />**有効な値: 0**: ブラウズを無効にします。**1**: ブラウズを有効にします。<br /><br />**既定値:** 1|
|**AllowSearchSuggestionsinAddressBar**|両方|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Browser/AllowSearchSuggestionsinAddressBar<br /><br />**データ型:** 整数<br /><br />**有効な値: 0**: 検索候補を表示しません。**1**: 検索候補を表示します。<br /><br />**既定値:** 1|
|**SendIntranetTraffictoInternetExplorer**|デスクトップ|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Browser/SendIntranetTraffictoInternetExplorer<br /><br />**データ型:** 整数<br /><br />**有効な値: 0**: 無効 (Edge ブラウザーでイントラネット サイトを開きます)。**1**: 有効 (Internet Explorer でイントラネット サイトを開きます)。<br /><br />**既定値:** 0|
|**追跡禁止を許可する**|両方|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Browser/AllowDoNotTrack<br /><br />**データ型:** 整数<br /><br />**有効な値: 0**: 無効 (DNT を送信しません)。**1**: 有効 (DNT を送信します)。<br /><br />**既定値:** 0|
|**SmartScreen を構成する**|両方|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Browser/AllowSmartScreen<br /><br />**データ型:** 整数<br /><br />**有効な値: 0**: 許可しません。**1**: 許可します。<br /><br />**既定値:** 1|
|**ポップアップを許可する**|デスクトップ|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Browser/AllowPopups<br /><br />**データ型:** 整数<br /><br />**有効な値: 0**: ポップアップをブロックします。**1**: ポップアップを許可します。<br /><br />**既定値:** 0|
|**Cookie を使用する**|両方|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Browser/AllowCookies<br /><br />**データ型:** 整数<br /><br />**有効な値: 0**: ブロックしません。 すべての Web サイトの Cookie を使用します。**1**: サード パーティの Cookie のみをブロックします。**2**: すべての Cookie をブロックします。<br /><br />**既定値:** 0|
|**パスワードの保存を許可する**|両方|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Browser/AllowPasswordManager<br /><br />**データ型:** 整数<br /><br />**有効な値: 0**: Password Manager を無効にします。 <br />                        **1**: Password Manager を有効にします。<br /><br />**既定値:** 1|
|**オートコンプリートを使用する**|デスクトップ|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Browser/AllowAutofill<br /><br />**データ型:** 整数<br /><br />**有効な値: 0**: 無効になっています。**1**: 有効になっています。<br /><br />**既定値:** 0|
|**エンタープライズ サイトのリストを構成する**|デスクトップ|**URI の完全なパス:** ./Vendor/MSFT/Policy/Config/Browser/EnterpriseModeSiteList<br /><br />**データ型:** 文字列<br /><br />**有効な値: 0**: 構成されていません。**1**: IE のエンタープライズ モード サイト リストが構成されている場合はそれを使用します。**2**: エンタープライズ サイト リストの場所を指定します。<br /><br />**既定値:** 1|

### 関連項目
[Microsoft Intune ポリシーを使用してデバイスの設定と機能を管理する](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=May16_HO1-->


