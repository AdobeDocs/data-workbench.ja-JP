---
description: Data Workbenchのデータにアクセスして表示できるダッシュボードには、特定の読み取り専用権限が必要です。 書き込み権限は必要ありません。
title: アクセス制御の設定
uuid: 600b6799-547d-46da-9027-4f64943e2ccd
exl-id: a9ff61bb-c519-4205-8fa8-bfd1986fcd60
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 6%

---

# アクセス制御の設定{#configuring-access-control}

Data Workbenchのデータにアクセスして表示できるダッシュボードには、特定の読み取り専用権限が必要です。 書き込み権限は必要ありません。

アクセス制御の設定では、FSU上の[!DNL Access Control.cfg]ファイルを編集し、Data Workbenchダッシュボードに権限を付与する新しいグループを追加します。

1. [!DNL AccessControl.cfg]ファイルを編集します（できれば、Data Workbenchワークステーションを使用）。
1. *Insight Dashboard Access*&#x200B;という名前の新しいグループを作成します。
1. このグループのメンバーの下で、この目的のために提供された適切なCNを追加します(例：CN:INSIGHT-USER01)。 このCNについては、Adobeカスタマーケアにお問い合わせください。
1. このグループの読み取り専用アクセス権で、次の内容を反映するようにリストを変更します。

* /プロファイル/$
* /プロファイル/
* /アドレス
* /ステータス/
* /ユーザー/$

1. ダッシュボードに対する書き込み権限が不要なので、読み取り/書き込みアクセスセクションから項目を削除します。
1. [!DNL AccessControl.cfg]ファイルに対する変更をサーバーに保存し、権限を有効にします。
