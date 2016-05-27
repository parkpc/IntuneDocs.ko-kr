---
# required metadata

title: Microsoft Intune にデバイスを登録する準備 | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 44fd4af0-f9b0-493a-b590-7825139d9d40

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune にデバイスを登録する準備
従業員が Intune にモバイル デバイス (Android、iOS、Windows Phone、Windows PC など) を登録できるようにするには、デバイスの登録を有効にする必要があります。 登録を許可するには、モバイル デバイス管理機関を設定し、Intune ポータル サイトを構成し、ライセンスを割り当て、デバイス プラットフォームの登録を有効にする必要があります。

## <a name="BKMK_Set_MDM_Authority"></a>モバイル デバイス管理機関を設定する
MDM 機関では、一連のデバイスを管理するためのアクセス許可を持つ管理サービスを定義します。 MDM 機関のオプションには、Intune 単体で使用するか、Intune を Configuration Manager と連携させて使用する方法があります。 Configuration Manager を管理機関として設定した場合、モバイル デバイス管理のために使用できるサービスは他にありません。

>[!IMPORTANT]
> モバイル デバイスの管理に Intune のみ (オンライン サービス) を使用するか、System Center Configuration Manager と Intune との統合 (オンプレミス ソフトウェア ソリューションをオンライン サービスと組み合わせて使用) を使用するのかについて、慎重に検討します。 モバイル デバイス管理機関は、設定したら変更できません。



1.  [Microsoft Intune 管理コンソール](http://manage.microsoft.com)で、**[管理]**  &gt;  **[モバイル デバイス管理]** の順にクリックします。.

2.  **[タスク]** リストで **[モバイル デバイス管理機関の設定]**をクリックします。 **[MDM 機関の設定]** ダイアログ ボックスが開きます。

    ![[MDM 機関の設定] ダイアログ ボックス](../media/intune-mdm-authority.png)

3.  Intune によって、Intune を MDM 機関にすることを確認するよう求められます。 チェック ボックスをオンにしてから、[ **はい** ] をクリックし、Microsoft Intune を使用してモバイル デバイスを管理します。

## Intune ポータル サイトの構成とライセンスの割り当て
Intune ポータル サイトでは、アプリなどの会社リソースにアクセスしたり、ヘルプデスク情報を検索したり、デバイスを登録/登録解除したりすることができます。 デバイスを登録する前に、[ポータル サイトを構成](/intune/get-started/get-started-with-a-paid-subscription-to-microsoft-intune-step-7)する必要があります。 また、[ユーザー ライセンスを割り当て](/intune/get-started/get-started-with-a-paid-subscription-to-microsoft-intune-step-4)て、Intune へのアクセスを許可する必要もあります。

## デバイス管理のセットアップ
MDM 機関を設定したら、組織がサポートするオペレーティング システムにデバイス管理をセットアップする必要があります。 デバイス管理のセットアップに必要な手順は、オペレーティング システムによって異なります。 たとえば、Android OS では、Intune 管理コンソールで必要になる操作はありません。 これに対して、Windows および iOS では管理を許可するため、デバイスと Intune との間に信頼関係が必要です。

> [!div class="op_single_selector"]
- [Microsoft Intune を使用して Android の管理をセットアップする](set-up-android-management-with-microsoft-intune.md)
- [Microsoft Intune を使用した iOS および Mac の管理のセットアップ](set-up-ios-and-mac-management-with-microsoft-intune.md)
- [Microsoft Intune を使用して Windows Phone の管理をセットアップする](set-up-windows-phone-management-with-microsoft-intune.md)
- [Microsoft Intune を使用して Windows デバイスの管理をセットアップする](set-up-windows-device-management-with-microsoft-intune.md)

次も実行できます。
 - [デバイス登録マネージャー アカウント](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)を使用して多数のデバイスを登録する
 - [会社所有のデバイスを IMEI 番号を使用してデバイスおよびターゲット ポリシーを登録できるように指定する](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md)


<!--HONumber=May16_HO1-->


