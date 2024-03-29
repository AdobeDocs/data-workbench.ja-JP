---
description: Data Workbench サーバーでは、複数のタイプのディメンションを使用できます。 したがって、ディメンションを使用して指標、フィルター、派生ディメンションを作成する場合は、ディメンションのタイプを把握しておくことが重要です。
title: ディメンションタイプ
uuid: 07659373-8d9b-473d-8daa-ca8e7ac4afe8
exl-id: cbc25504-2c1c-4622-adc1-c9bbac8e12fb
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '754'
ht-degree: 67%

---

# ディメンションタイプ{#dimension-types}

{{eol}}

Data Workbench サーバーでは、複数のタイプのディメンションを使用できます。 したがって、ディメンションを使用して指標、フィルター、派生ディメンションを作成する場合は、ディメンションのタイプを把握しておくことが重要です。

Insight サーバーは、次のタイプのディメンションを作成および管理できます。

<table id="table_1A79B6C57ED145B6AA3BB05DD37AAD1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ディメンションタイプ </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 可算 </td> 
   <td colname="col2">ディメンション内の要素数をシステムでカウントできるディメンションタイプ。 可算ディメンションは他の可算ディメンションから派生する必要があります。可算ディメンションは他のディメンションの親または他の可算ディメンションの子にすることができます。 <p>例：訪問者、セッション、ページビュー、予約、および注文。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> シンプル </td> 
   <td colname="col2">親の可算ディメンションと 1 対多の関係を持つディメンション。 シンプルディメンションは、親ディメンションのエレメントのプロパティを表しているとみなせます。 <p>例：訪問者リファラーは、訪問者ディメンションが親のシンプルディメンションです。各訪問者には 1 つの訪問者リファラー（最初の HTTP リファラー）しかありませんが、多くの訪問者が同じ訪問者リファラーを持っている場合があります。そのため、訪問者リファラーは訪問者ディメンションに対して「1 対多」となります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 数値 </td> 
   <td colname="col2">並べ替えられた数値と、親の可算ディメンションとの 1 対多の関係を持つディメンション。 数値ディメンションは、親ディメンションのエレメントの数値プロパティを表しているとみなせます。数値ディメンションは多くの場合、「sum」指標を定義するために使われます。 <p>例：セッション売上高の数値ディメンションは、各セッションの売上高（ドル）を定義します。各セッションには単一の売上高の額がありますが、セッションの中には売上高が同じ額のものもあるため、セッション売上高はセッショに対して「1 対多」となります。「売上高」指標は、 <span class="filepath"> sum(Session_Revenue, Session)</span>：選択したセッションの合計売上高を示します。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 多対多 </td> 
   <td colname="col2">親の可算ディメンションと多対多の関係を持つディメンション。 多対多ディメンションは、親ディメンションにある各エレメントの値の「セット」を表しているとみなせます。多対多ディメンションは、親の（匿名）可算ディメンション、および匿名可算ディメンションの親のシンプルディメンションに等しいと言えます。 <p>例：検索用語の多対多ディメンションには、セッションの親があります。各セッションでは、ゼロ以上の検索用語を使え、検索用語は任意の数のセッションで使用できます。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 非正規 </td> 
   <td colname="col2">親の可算ディメンションと 1 対 1 の関係を持つディメンション。 非正規ディメンションのエレメント名には、親ディメンションの対応するエレメントに関する情報を含められます。非正規ディメンションは、親の各エレメントの任意の文字列値を保存しているとみなせます。非正規ディメンションは、Insight サーバーのセグメントエクスポート機能と併用して、可算ディメンションのサブセットまたは「セグメント」に関する詳細を出力できます。加えて、非正規ディメンションは、指標の公式やワークシートの可視化で参照でき、フィルターを定義するために使用できます（一部制限あり）。 <p>例：電子メールアドレスという非正規ディメンションの親は訪問者です。各訪問者には電子メールアドレスがあり、電子メールアドレスディメンションのエレメントはそれぞれ単一の訪問者に関連付けられています。2 人の訪問者が同じ電子メールアドレスを持っていたとしても、それぞれのアドレスは電子メールアドレスディメンションの異なるエレメントとなります。セグメントエクスポートは、電子メールアドレスディメンションを参照して、セグメントにある各訪問者の電子メールアドレスを出力できます。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 時間 </td> 
   <td colname="col2">指定したタイムスタンプフィールドに基づいて、定期的または絶対的なローカル時間ディメンション（日、曜日、時間、時刻など）のセットを作成できるディメンション。 時間ディメンションを定義する際に、週の開始日パラメーターを指定することで、月曜日以外の曜日を週の最初の日として選択できます。 <p>例：セッション時間という時間ディメンションの親はセッションです。そのため、ディメンションは時間ディメンション（日、曜日、時間、時間帯、月、週）のセットを定義し、そのエレメントはサイトで訪問者のセッションが始まった時間を表します。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 派生 </td> 
   <td colname="col2">派生ディメンションは、処理されるデータに基づいてデータセット設定で定義されるのではなく、他のディメンションや指標に基づいてプロファイル内で定義されます。 多くの派生ディメンションは、異なるタイプの可視化を実現するために自動的に作成されます。 <p>例えば、ユーザーがサイトまたはプロセスマップを構築する際に、Insight サーバーは「プレフィックス」ディメンションをサイレントで作成します。 他にも、レポーティング時間ディメンションのように、プロファイルのディメンションディレクトリ内のファイルによって定義されるものもあります。 </p></td> 
  </tr> 
 </tbody> 
</table>
