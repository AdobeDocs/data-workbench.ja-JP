---
description: 変換を構築するうえでの決まりごとを表形式で示します。
title: 変換を構築する際の規則
uuid: 91dddca6-4c17-4107-b78b-0f8b8870ef8d
exl-id: c2552c52-c6d3-4c9f-8359-b5a58bf1a59f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 96%

---

# 変換を構築する際の規則{#conventions-for-constructing-transformations}

{{eol}}

変換を構築するうえでの決まりごとを表形式で示します。

<table id="table_BEB0F6C416D144B5A2DD3D1A21613B21"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 規則 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 順次実行 </td> 
   <td colname="col2"> <p>データセット設定ファイルに記述された変換は、上から順に（設定ファイルに列挙された順番に）ログエントリに適用されます。したがって、変換の出力結果を他の変換の入力として使用するためには、その順序で変換を記述する必要があります。つまり、ある変換からの出力を別の変換への入力として使用する場合、データセット設定ファイルには、前者を後者よりも前に配置することが重要となります。そのようにしないと、Data Workbench サーバーでエラーが発生します。 </p> <p> 複数のデータセットインクルードファイル内に定義された変換の順序付けは、処理ステージによって行うことができます。特定の処理ステージに関連付けられているすべてのデータセットインクルードファイルについて、変換の順序は、その入力と出力に基づいて決まります。加えて、1 つのステージ内の複数のデータセットインクルードファイルから、変換の結果として、同じフィールドにデータが出力された場合、Data Workbench サーバーからエラーが生成されます。 </p> <p> ステージについて詳しくは、 <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> ログ処理設定ファイル</a>, <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-abt-trans-config-file.md"> 変換設定ファイル</a>、および <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> データセットインクルードファイル</a>. </p> <p>一連の変換によってフィールドに加えられる変更は、<span class="wintitle">変換依存関係マップ</span>に表示されます。詳しくは、 <a href="../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md"> データセット設定ツール</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 出力名 </td> 
   <td colname="col2"> 変換には通常、出力フィールドを指定します。ユーザー定義の拡張フィールドを出力先とする場合、そのフィールド名は「x-」で始める必要があります。出力フィールド名に、スペースや特殊文字を含めることはできません。読みやすくするために、拡張フィールドの名前に大文字と小文字を混在させることはできますが（「x-NewCampaignName」、「x-New-Campaign-Name」など）、ソフトウェア内の処理としては、大文字と小文字が区別されません。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 入力フィールド </td> 
   <td colname="col2"> <p>入力フィールドは、いずれかのベースラインフィールド、または先行する変換の出力として得られたユーザー作成フィールドを指します。定数文字列が必要な場合、ベースラインフィールドやユーザー作成フィールドの代わりに、二重引用符で囲まれた文字列を使用することができます。 </p> <p> Data Workbench サーバーが処理できる代表的なデータフィールドの例については、 <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md"> イベントデータレコードフィールド</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 単純な文字列と文字列ベクトル </td> 
   <td colname="col2"> すべての変換は、文字列か、文字列ベクトルに対して作用します。単純な文字列は、直接表記された一連の文字です。文字列ベクトルは、0 個以上の単純な文字列を決まった順序で格納したものです。 </td> 
  </tr> 
 </tbody> 
</table>
