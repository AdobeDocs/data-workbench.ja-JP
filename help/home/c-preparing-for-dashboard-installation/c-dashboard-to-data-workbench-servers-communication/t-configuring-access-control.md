---
description: Data Workbench のデータにアクセスして表示するには、ダッシュボードに特定の読み取り専用権限が必要です。 書き込み権限は必要ありません。
title: ダッシュボードのアクセス制御の設定
uuid: 600b6799-547d-46da-9027-4f64943e2ccd
exl-id: a9ff61bb-c519-4205-8fa8-bfd1986fcd60
source-git-commit: 90b9fff995cb37a62024f454f009e9e0d7b927cd
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 2%

---

# ダッシュボードのアクセス制御の設定{#configuring-dashboard-access-control}

{{eol}}

Data Workbench のデータにアクセスして表示するには、ダッシュボードに特定の読み取り専用権限が必要です。 書き込み権限は必要ありません。

アクセス制御の設定には、 [!DNL Access Control.cfg] ファイルを FSU に追加し、新しいグループを追加して、data workbench ダッシュボードに権限を付与します。

1. を編集します。 [!DNL AccessControl.cfg] ファイル（data workbench ワークステーションを使用することが望ましい）
1. という名前の新しいグループを作成します。 *Insight ダッシュボードアクセス*.
1. このグループのメンバーの下で、この目的のために提供された適切な CN を追加します ( 例：CN:INSIGHT-USER01)。 この CN については、Adobeカスタマーケアにお問い合わせください。
1. このグループの読み取り専用アクセス権で、リストを変更して次のことを反映します。

* /プロファイル/$
* /プロファイル/
* /アドレス
* /ステータス/
* /ユーザー/$

1. ダッシュボードに対する書き込み権限が不要なので、読み取り/書き込みアクセスセクションから項目をすべて削除します。
1. 変更を [!DNL AccessControl.cfg] ファイルをサーバーに送信して、権限を有効にします。
