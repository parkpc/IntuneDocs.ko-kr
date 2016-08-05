---
title: "デバイスをインベントリから削除する | Microsoft Intune"
description: "Intune では、デバイスのポリシーとポータル サイトを削除することによって Intune の管理対象からデバイスを削除する選択的ワイプとフル ワイプの両方をサポートします。"
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3dbec400-5d8a-47be-b892-7745811d9de2
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e9cbf5858cc4e860b540f421b6d463b8e7a429cf
ms.openlocfilehash: 42b723f99c34f03060140e5f280b87287d108ae1


---

# Intune の管理からデバイスを削除する

会社所有のデバイスであっても個人所有のデバイスであっても、デバイスを Intune の管理対象から削除することが必要となる場合があります。 デバイスを削除する手順は比較的簡単であり、選択的ワイプまたはフル ワイプのどちらかを実行します。
## デバイスからデータとアプリをワイプする
選択的ワイプとフル ワイプではいずれも、デバイスのポリシーとポータル サイトを削除することによって、Intune の管理対象からデバイスを削除します。それによって、デバイスには Microsoft SharePoint、電子メール、Office 365 などの会社のリソースにログオンするために必要な資格情報がなくなります。

[選択的ワイプ](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#selective-wipe)は、デバイス上の個人情報には影響を与えないため、従業員が Intune に個人のデバイスを登録している場合にお勧めの方法です。 会社のデータだけが削除されます。

会社所有のデバイスに対しては、デバイスを工場出荷時の設定にリセットする[フル ワイプ](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#full-wipe)も使用できます。

## 企業ネットワークへのアクセスを取り消す
デバイスを削除する理由が従業員が会社を退職したことであり、その従業員が会社所有のハードウェアを返却し忘れていた場合には、デバイスを[リモートでロック](use-remote-lock-and-passcode-reset-in-microsoft-intune.md)することもできます。 これにより、会社の情報と会社のハードウェアの両方の不正使用を防止できます。ただし、デバイスを損失として会計処理することが必要な場合があります。

また、その従業員の Intune のユーザー アカウントからライセンスを失効させる必要もあります。 これにより、ライセンスが解放され、そのライセンスを新しいユーザー アカウントに割り当てることができます。

## ハードウェアをインベントリから削除する
デバイス自体の寿命が訪れることがあります。 その場合は、フル ワイプによってデバイスを[工場出荷時の設定にリセット](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md)して、すべてのデータを削除し、Intune からデバイスを削除します。 その後は、会社のポリシーに従って、ハードウェアを処分できます。

### 関連項目
[フル ワイプまたは選択的ワイプを使用してデータを保護する](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md)



<!--HONumber=Jul16_HO4-->


