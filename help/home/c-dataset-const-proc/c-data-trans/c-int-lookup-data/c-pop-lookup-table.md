---
description: Categorize 変換または FlatFileLookup 変換を使用した場合、フラットファイル（格納場所は、変換を定義するときに指定）からメモリにルックアップテーブルが読み込まれ、データが投入されます。
solution: Analytics
title: ルックアップテーブルへのデータ投入
topic: Data workbench
uuid: a11f3902-8853-4d22-bbfd-b2a3d143cb7b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ルックアップテーブルへのデータ投入{#populating-the-lookup-table}

Categorize 変換または FlatFileLookup 変換を使用した場合、フラットファイル（格納場所は、変換を定義するときに指定）からメモリにルックアップテーブルが読み込まれ、データが投入されます。

指定するフラットファイルは、以下の要件を満たしている必要があります。

* ファイル内の行とルックアップテーブル内の行が一対一で対応している必要があります。
* ファイル内の列は、ASCII の区切り文字で区切られている必要があります。行終端文字以外で、かつイベントデータ自体に出現していない文字であれば、どのような文字でも使用できます。フラットファイルの列の区切りに使用されている文字は、変換を定義するときに指定します。

[!DNL ODBCLookup] 変換を使用した場合、指定した [!DNL ODBC] データベースのテーブルまたはビューからメモリにルックアップテーブルが読み込まれ、データが投入されます。変換を定義するときは、Data Workbench サーバーがデータベースとの接続を確立する際に必要となるデータソース、ユーザー名、パスワードも指定する必要があります。

>[!NOTE]
>
>ルックアップテーブルは、Data Workbenchサーバーがデータセットの構築を最初に開始したときに読み込まれます。 接続の確立後に、ルックアップファイルに変更を加えないでください。変換段階で使用されるフラットファイルや [!DNL ODBC] テーブルに変更を加えた場合は、データセット全体を再変換する必要があります。ログ処理段階で使用するフラットファイルに変更を加えた場合、新しくデータセットに追加されるレコードにはすべて、新しいルックアップデータが適用されますが、過去にさかのぼって変更が適用されることはありません。
