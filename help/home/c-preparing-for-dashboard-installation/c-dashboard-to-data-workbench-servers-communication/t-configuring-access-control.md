---
description: ダッシュボードで、Data Workbenchのデータにアクセスして表示できる読み取り専用の権限が必要です。 書き込み権限は不要です。
solution: Analytics
title: アクセス制御の設定
topic: Data workbench
uuid: 600b6799-547d-46da-9027-4f64943e2ccd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# アクセス制御の設定{#configuring-access-control}

ダッシュボードで、Data Workbenchのデータにアクセスして表示できる読み取り専用の権限が必要です。 書き込み権限は不要です。

アクセス制御の設定には、FSU上のフ [!DNL Access Control.cfg] ァイルを編集し、Data Workbenchのダッシュボードに権限を付与する新しいグループを追加する必要があります。

1. ファイルを編集しま [!DNL AccessControl.cfg] す（できれば、Data Workbenchワークステーションを使用します）。
1. 「 *Insight Dashboard Access」という名前の新しいグループを作成します*。
1. このグループのメンバーの下で、この目的で提供された適切なCNを追加します(例：CN:INSIGHT-USER01)。 このCNについては、アドビカスタマーケアにお問い合わせください。
1. このグループの読み取り専用アクセスで、次の内容を反映するようにリストを変更します。

* /プロファイル/$
* /プロファイル/
* /アドレス
* /ステータス/
* /Users/$

1. ダッシュボードに対する書き込み権限が不要なので、読み取り/書き込みアクセス・セクションから項目を削除します。
1. 権限を有効にするために、 [!DNL AccessControl.cfg] ファイルに対する変更をサーバーに保存します。
