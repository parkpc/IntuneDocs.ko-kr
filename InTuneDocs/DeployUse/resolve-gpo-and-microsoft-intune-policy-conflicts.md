---
# required metadata

title: GPO と Intune ポリシーの競合を解決する| Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: e76af5b7-e933-442c-a9d3-3b42c5f5868b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# グループ ポリシー オブジェクト (GPO) と Microsoft Intune ポリシーの競合を解決する
Intune では、管理対象のコンピューターの設定を管理するためにポリシーを使用しています。 たとえば、ポリシーを使用して、コンピューターの Windows ファイアウォールに関する設定を制御できます。 多くの Intune 設定は、Windows グループ ポリシーで構成する設定と似ています。 ただし、この 2 つの設定が互いに競合することがあります。

競合が発生した場合、コンピューターがドメインにログオンできない場合を除き、ドメインレベルのグループ ポリシーの方が Intune ポリシーよりも優先されます。 ドメインにログオンできない場合は、Intune ポリシーがクライアント コンピューターに適用されます。

## グループ ポリシーを使用する場合の操作
適用するポリシーがグループ ポリシーの管理対象かどうかを確認してください。 競合を回避するために、次の方法の 1 つまたは複数を採用することができます。

-   グループ ポリシー設定が適用されない Active Directory 組織単位 (OU) にコンピューターを移動してから、Intune クライアントをインストールします。 また、Intune に登録されているコンピューターを含む OU にグループ ポリシー設定を適用しない場合は、その OU へのグループ ポリシーの継承をブロックすることもできます。

-   WMI フィルターを使用するか、セキュリティ フィルターを使用して、Intune で管理されていないコンピューターにのみ GPO を制限します。 この操作方法の詳細と例については、以下の「[既存の GPO をフィルターして Intune ポリシーとの競合を回避する方法](resolve-gpo-and-microsoft-intune-policy-conflicts.md#BKMK_Filter)」を参照してください。

-   Intune ポリシーと競合するグループ ポリシー オブジェクトを無効にするか削除します。

Active Directory と Windows グループ ポリシーの詳細については、Windows Server のマニュアルを参照してください。

## 既存の GPO をフィルターして Intune ポリシーとの競合を回避する方法
Intune ポリシーと設定が競合するグループ ポリシー オブジェクト (GPO) を見つけたら、次のいずれかのフィルター方法を使用して、Intune で管理しないコンピューターのみにこれらの GPO が適用されるようにします。

### WMI フィルターを使用する方法
WMI フィルターは、クエリーの条件を満たすコンピューターにのみ、GPO を適用します。 WMI フィルターを適用するには、Intune サービスにコンピューターを登録する前に、エンタープライズ内のすべてのコンピューターに WMI クラスのインスタンスを展開します。

#### WMI フィルターを GPO に適用するには

1.  まず、管理オブジェクト ファイルを作成します。このためには、次のコードをコピーしてテキスト ファイルに貼り付け、**WIT.mof** という名前を付けて適切な場所に保存します。 このファイルには、Intune サービスに登録するコンピューターに展開される、WMI クラスのインスタンスが含まれています。

    ```
    //Beginning of MOF file.
    #pragma classflags("forceupdate")
    #pragma namespace ("\\\\.\\Root")
    instance of __Namespace
    {
       Name = "WindowsIntune";
    };

    #pragma namespace ("\\\\.\\Root\\WindowsIntune")
    [
       Description("This class defines Microsoft Intune common properties")
    ]
    class WindowsIntune_ManagedNode
    {
       [ read, Description("This defines whether Microsoft Intune Policy is enabled"): DisableOverride ToSubClass ]
       boolean WindowsIntunePolicyEnabled;
       [ read, key, Description("This property defines the version." "Example: 1.0"): ToSubClass ]
       string Version;
    };

    instance of WindowsIntune_ManagedNode
    {
       Version = "1.0";
       WindowsIntunePolicyEnabled = 1;
    };
    ```

2.  スタートアップ スクリプトかグループ ポリシーを使用して、ファイルを展開します。 以下は、スタートアップ スクリプトを使用する場合の展開コマンドです。 Intune サービスにクライアント コンピューターを登録する前に、WMI クラスのインスタンスを展開する必要があります。

    **C:/Windows/System32/Wbem/MOFCOMP &lt;MOF ファイルのパス&gt;\wit.mof**

3.  次のコマンドのいずれかを実行して、WMI フィルターを作成します。フィルター処理された GPO を、Intune で管理するコンピューターに適用するか、Intune で管理しないコンピューターに適用するかによって、実行するコマンドが異なります。

    -   Intune で管理しないコンピューターに GPO を適用する場合は、次のコマンドを使用します。

        ```
        Namespace:root\WindowsIntune
        Query:  SELECT WindowsIntunePolicyEnabled FROM WindowsIntune_ManagedNode WHERE WindowsIntunePolicyEnabled=0
        ```

    -   Intune で管理するコンピューターに GPO を適用する場合は、次のコマンドを使用します。

        ```
        Namespace:root\WindowsIntune
        Query:  SELECT WindowsIntunePolicyEnabled FROM WindowsIntune_ManagedNode WHERE WindowsIntunePolicyEnabled=1
        ```

4.  グループ ポリシー管理コンソールで GPO を編集して、前の手順で作成した WMI フィルターを適用するように設定します。

    -   Intune で管理されているコンピューターだけに GPO を適用する場合は、**WindowsIntunePolicyEnabled=1** のフィルターを適用します。.

    -   Intune で管理されていないコンピューターだけに GPO を適用する場合は、**WindowsIntunePolicyEnabled=0** のフィルターを適用します。.

グループ ポリシーで WMI フィルターを適用する方法については、ブログの投稿「 [Security Filtering, WMI Filtering, and Item-level Targeting in Group Policy Preferences (グループ ポリシー基本設定のセキュリティ フィルター処理、WMI フィルター処理、項目レベルでのターゲット設定)](http://go.microsoft.com/fwlink/?LinkId=177883)」を参照してください。.

### セキュリティ グループ フィルターの使用
グループ ポリシーを使用すると、グループ ポリシー管理コンソールで、選択した GPO の **[セキュリティ フィルター処理]** に指定されているセキュリティ グループのみに GPO を適用できます。 既定では、GPO は **[認証されたユーザー]** に適用されます。.

-   **[Active Directory ユーザーとコンピューター]** スナップインで、Intune で管理しないコンピューターとユーザー アカウントを含む新しいセキュリティ グループを作成します。 このグループに "**Not In Microsoft Intune**" などの名前を設定できます。.

-   グループ ポリシー管理コンソールで、選択した GPO の **[委任]** タブを開き、新しいセキュリティ グループを右クリックして、適切な**読み取り**アクセス許可と**グループ ポリシーの適用**アクセス許可をセキュリティ グループ内のユーザーとコンピューターの両方に委任できます。 (**グループ ポリシーの適用** アクセス許可は **[詳細設定]** ダイアログ ボックスで使用できます)。

-   次に、選択した GPO に新しいセキュリティ グループ フィルターを適用し、既定の **[認証されたユーザー]** フィルターを解除します。

新しいセキュリティ グループは、Intune サービス変更の登録として保持する必要があります。

### 関連項目
[Microsoft Intune を使用して Windows PC を管理する](manage-windows-pcs-with-microsoft-intune.md)


<!--HONumber=May16_HO1-->


