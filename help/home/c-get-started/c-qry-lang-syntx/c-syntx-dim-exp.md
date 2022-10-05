---
description: ディメンション式は、単独で使用することはできませんが、ディメンションが指標式またはフィルター式の中で呼び出される場所ではどこでも使用できます。
title: ディメンション式の構文
uuid: c437cc52-4eb3-4202-a0b4-e23889f9c8a2
exl-id: 58609e31-8ad8-418b-9a9f-40462d6443f7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1855'
ht-degree: 92%

---

# ディメンション式の構文{#syntax-for-dimension-expressions}

{{eol}}

ディメンション式は、単独で使用することはできませんが、ディメンションが指標式またはフィルター式の中で呼び出される場所ではどこでも使用できます。

1. 下線を引いた語句は、式のテキストにそのまま入力する必要があります。
1. フォーム `{TEXT}?` オプションのテキストを表します。
1. フォーム `{TEXT}*` 0 回以上発生する可能性のあるテキストを表します。
1. フォーム `{A | B | C |...}` は、A、B、C など、指定されたオプションの 1 つだけから成るテキストを表します。.
1. フォーム `[A,B)` は、A から B までの範囲の数値を表します。

<table id="table_2D9AE1E2397843C284E838330370A1EE"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>識別子 </p> </td> 
   <td colname="col2"> <p>識別子は、名前付きディメンションを参照するものです。正しい識別子のルールについては、「<a href="../../../home/c-get-started/c-qry-lang-syntx/c-syntx-id.md#concept-735fa36fc49643269b3646aaaa8f2fa8">識別子の構文</a>」を参照してください。 </p> <p>例：Sessions[ Session_Number = “1” ] は、セッション番号が「1」のセッションの数です。セッション番号は、識別子によって参照される名前付きディメンションです。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>(ディメンション) </p> </td> 
   <td colname="col2"> <p>(ディメンション) という式の結果は、ディメンションの式の結果と同じです。丸括弧は、式の中の演算の順序を指定します。 </p> <p>例：Sessions[ (Page) = “/home” ] は、「/home」というページを訪問するセッションの数です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim by Level </p> </td> 
   <td colname="col2"> <p>ディメンション Dim と同じ要素を持つが、ディメンションレベルによって別のディメンションに関するディメンションを定義します。 </p> <p>具体的には、新しいディメンションの要素は、Dim の同じ要素と同じレベルの要素に関連付けられ、それらのレベルの要素に関連付けられた他のディメンションがあれば、その要素にも関連付けられます。 </p> <p>例：Sessions[ (Page by Visitor)=”/home” ] は、「/home」というページを訪問した訪問者のセッションの数です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>shift(Dim,Level,Group,N) </p> </td> 
   <td colname="col2"> <p>ディメンション Dim と同じ要素を持つディメンションを定義します。レベルの e 番目の要素と e+N 番目の要素がディメンショングループの同じ要素に関連する場合に、新しいディメンションでは、ディメンションレベルの e 番目の要素が、レベルの e+N 番目の要素に関連する Dim の要素と同じ要素に関連付けられます。 </p> <p>例：Page_Views[ shift(Page, Page_View, Session, 1)=”/home” ] は、同じセッションで表示された次のページが「/home」であるページビューの数です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>next(Dim,Level,Group,N) </p> </td> 
   <td colname="col2"> <p>shift(Dim,Level,Group,N) と同様ですが、ディメンションに空の値がある場合にスキップする点が異なります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>segment(Level {,String-&gt;Filter}*) </p> </td> 
   <td colname="col2"> <p> フィルターのリストに基づいてレベルの要素を分類するディメンションを定義します。新しいディメンションの要素は、引数として与えた文字列 String です。Level の各要素は、セグメントディメンションの要素のうち、そのフィルターが Level の要素を通す最初の要素に関連付けられます。これはセグメントのビジュアライゼーションと同様です。 </p> <p>例：segment(Visitor, "One-Time Visitors" -&gt; Visitor_Sessions = 1, "Very Loyal Visitors" -&gt; Visitor_Sessions &gt; 10, "Everyone Else" -&gt; True) は、訪問者を 3 つのグループに分類するディメンションを作成します。One-Time Visitors はセッションが 1 回だけの訪問者で、Very Loyal Visitors はセッションが 10 回を超える訪問者です。それ以外のすべての訪問者の値は Everyone Else になります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>bucket(Level, Metric, Count, Format {, Start {, Size}? }?) </p> </td> 
   <td colname="col2"> <p>要素が数値範囲（固定サイズ、例えば、[0-9]、[10-19] など）のディメンションを定義します。Level の要素は、そのレベルの要素の Metric の値を範囲に含むバケットディメンションの要素に関連付けられます。Format は、指標の要素の書式設定に使用する printf 書式の文字列です。 </p> <p>例：Page_Duration_Minutes が各ページでの滞在時間を表すページビューレベルのディメンションの場合、bucket(Session, sum(Page_Duration_Minutes, Page_View), 100, "%0.0f minutes", 0, 5) は、各セッションでの滞在時間を表すセッションレベルのディメンションです。要素は 5 分間隔です <code>{[0-5), [5-10),...,[495-500)}</code>. </p> <p>Start は、最初の間隔の開始値（デフォルト：0）であり、Size は間隔のサイズ（デフォルト：1）です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>prefix(Level {,ElementName-&gt;(Prefix{,Prefix}* )}* ) </p> </td> 
   <td colname="col2"> <p>指定した文字列 ElementName を要素とし、対応する文字列 Prefix のセットにそれらの要素が関連付けられているディメンションを定義します。Level の要素は、プレフィックスディメンションの要素に関連付けられますが、その際、レベルの要素の名前と一致する最も長いプレフィックスに関連付けられたプレフィックスディメンションの要素が選択されます。特殊文字「$」で終わるプレフィックスの場合は、完全に一致する必要があります。  </p> <p>例えば、prefix(URI, "Products" -&gt; ("/products/"), "Services" -&gt; ("/services/", "/products/service/"), "Warranties" -&gt; ("/products/warranty.html$", "/services/warranty.html$", "Everything Else" -&gt; ("/"))) は、URI を 4 つのカテゴリーに分類するディメンションを作成します。様々なページに対する効果は次のとおりです。 </p> <p>/products/warranty.html は、/products/warranty.html$ というプレフィックスと完全に一致するので、Warranty に分類されます。 </p> <p>/products/cars/specialcar.html は、/products/ というプレフィックスと一致し、これ以上長いプレフィックスとは一致しないので、Products に分類されます。 </p> <p>/products/service/something.html は、/products/ プレフィックスよりも長い /products/service/ というプレフィックスと一致するので、Services に分類されます。 </p> <p>/companyinfo/aboutus.html は、「/」というプレフィックスにのみ一致するので、「Everything Else」カテゴリーに分類されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>latency(Level, Clip, Dim, Filter, MaxBefore, MaxAfter, FormatString) </p> </td> 
   <td colname="col2"> <p>詳しくは、「 <a href="../../../home/c-get-started/c-intf-anlys-ftrs/c-config-ltcy-tbls/t-create-ltncy-dims.md#task-6d46ea8c89a047318d9c71bf105ef64a"> 待ち時間ディメンションの作成 </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>cartesian_product(Separator {,Dim}*) </p> </td> 
   <td colname="col2"> <p>指定したディメンションの要素のすべての組み合わせ（「デカルト積」）を要素とするディメンションを定義します。各要素の名前は、入力ディメンションの中の対応する要素を、指定した Separator 文字列で区切って連結した名前になります。 </p> <p>例えば、ディメンション D1 の要素が {"a", "b"} で、ディメンション D2 の要素が {"x", "y"} の場合、デカルト積 cartesian product("-", D1, D2) の要素は {"a-x", "a-y", "b-x", "b-y"} になります。 </p> <p>内部的には、入力ディメンションはそれぞれ、要素の数が 2 のべき乗（要素の数以上で最も近い数）であるかのように扱われます。このため、デカルト積にはダミーの要素がいくつか存在することになります。Data WorkbenchAPI を使用する場合、出力形式に応じて、これらの要素は省略されるか、「#nnn」と表示される場合があります (nnn は要素の序数です（クライアントは無視する必要があります）。 </p> <p>例えば、上記の例で D2 に 3 つの要素 {"x", "y", "z"} がある場合、要素は 4 つあるもとのして扱われ、デカルト積の要素は {"a-x", "a-y", "a-z", "#3", "b-x", "b-y", "b-z", "#7"} となります。 </p> <p>ディメンションを指定しない場合、1 つの要素「#0」を持つディメンションとなり、None ディメンションと等しくなります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>nearest_countable(Dim) </p> </td> 
   <td colname="col2"> <p>既に存在するディメンションを参照します。スキーマ内の Dim の親ディメンションのうち最も近い可算ディメンションです。例えば、nearest countable(URI) は Page_View と同一です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>normalized(Dim,Count) </p> </td> 
   <td colname="col2"> <p>最大 Count 個の要素で、非正規ディメンション Dim から正規化されたディメンションを定義します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>last_n(Dim, TimeMetric, FormatString, Count, Offset, TrimToData {, WeekStart}?) </p> </td> 
   <td colname="col2"> <p>日、週、年など、期間を表す要素から成るディメンション Dim に対し、Dim の要素のサブセットから成るディメンションを定義します。 </p> <p>サブセットは、定数の指標 TimeMetric の値で指定した時間に近い範囲です。ここで、TimeMetric の値は、1970 年 1 月 1 日午前 0 時（UTC）からの時間（秒）と解釈されます。範囲には Count 個の要素が含まれ、その最後の要素は、指定した Dim の要素の Offset 個後の要素となります。この要素の名前は、指定した文字列 FormatString で指標の値を書式設定した結果です。FormatString では、標準の C ライブラリ関数 strftime と同じ % エスケープを使用します。 </p> <p>trimToData が true の場合、結果のディメンションの先頭にある要素（Dim の先頭より前の要素）は削除されます。false の場合、Count で指定した数の要素が必ず存在します。結果のディメンションの最後には、実際には Dim にない要素が常に存在する可能性があります。 </p> <p>オプションの WeekStart を指定する場合、{ "Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat" } のいずれかにする必要があります。これにより、その曜日になる最も近い日まで TimeMetric が過去に移動されます。 </p> <p>例：Week の要素が { "10/03/10", "10/10/10", ..., "12/12/10" } で、内蔵の As Of 指標の値が 1292348109（2010 年 12 月 14 日の中頃）の場合、last n(Week, As_Of, "%m/%d/%y", 4, 0, false, "Sun") は、{ "12/12/10", "12/19/10", "12/23/10", "12/30/10" } という要素を持つディメンションを定義します。 </p> <p>例 2：Week ディメンションの要素が {"12/19/10", "12/26/10", ..., "01/30/11"} だけで、As Of 指標が上記のとおりの場合、last n(Week, As_Of, "%m/%d/%y", 4, 0, true, "Sun") は、{"12/19/10", "12/23/10", "12/30/10"} という要素を持つディメンションになります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>days_of_previous_months(Dim, TimeMetric, FormatString, nMonths, includeThisMonth, TrimToData) </p> </td> 
   <td colname="col2"> <p>日を表す要素から成るディメンション Dim に対し、Dim の要素のサブセットから成るディメンションを定義します。サブセットは、定数の指標 TimeMetric の値で指定した時間に近い範囲です。ここで、TimeMetric の値は、1970 年 1 月 1 日午前 0 時（UTC）からの時間（秒）と解釈されます。範囲には、指定した時間より前の nMonths か月の各日に対応する要素が含まれます。includeThisMonth が true の場合、指定した時間を含む月の各日も範囲に含まれます。 </p> <p>FormatString は、標準の C ライブラリ関数 strftime のように、「%」エスケープを使用して Dim の要素の書式を指定します。 </p> <p>trimToData が true の場合、結果のディメンションの先頭にある要素（Dim の先頭より前の要素）は削除されます。false の場合、Count で指定した数の要素が必ず存在します。結果のディメンションの最後には、実際には Dim にない要素が常に存在する可能性があります。 </p> <p>例：Day の要素が { "01/01/10", "01/02/10", ..., "12/31/10" } で、内蔵の As Of 指標の値が 1292348109（2010 年 12 月 14 日の中頃）の場合、previous months(Day, As_Of, "%m/%d/%y", 2, false, false) の要素は { "10/01/10", "10/02/10", ..., "11/30/10" } です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>days_of_current_month(Dim, TimeMetric, FormatString, allMonth, trimToData) </p> </td> 
   <td colname="col2"> <p>days_of_previous_months と同様ですが、要素が、TimeMetric で指定した時間と同じ月の日にのみ対応する点が異なります。allMonth が true の場合、該当する月の各日に対応する要素があります。true でない場合は、該当する月の初めから、指定した時間を含む日までの日付だけがディメンションの部分になります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>days_of_future_months(Dim, TimeMetric, FormatString, nMonths, includeThisMonth, TrimToData) </p> </td> 
   <td colname="col2"> <p>days of previous months と同様ですが、要素が、TimeMetric で指定した時間を含む月の前ではなく、後の月の日に対応する点が異なります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>hours_of_day(Dim, Metric, TimeFormatString, nDaysForward, TrimData) </p> </td> 
   <td colname="col2"> <p>時間を表す要素から成るディメンション Dim に対し、Dim の要素のサブセットから成るディメンションを定義します。サブセットは、定数の指標 TimeMetric の値で指定した時間に近い範囲です。ここで、TimeMetric の値は、1970 年 1 月 1 日午前 0 時（UTC）からの時間（秒）と解釈されます。範囲には、TimeMetric で指定した時間を含む日の nDaysForward 日後の日の各時間に対応する要素が含まれます。 </p> <p>FormatString は、標準の C ライブラリ関数 strftime のように、「%」エスケープを使用して Dim の要素の書式を指定します。書式の文字列は、必ず、渡された時間の日の初めにあたる午前 0 時を表す文字列を出力する必要があります。 </p> <p>trimToData が true の場合、結果のディメンションの先頭にある要素（Dim の先頭より前の要素）は削除されます。false の場合、Count で指定した数の要素が必ず存在します。結果のディメンションの最後には、実際には Dim にない要素が常に存在する可能性があります。 </p> <p>例：Hour の要素が { "01/01/10 00:00", "01/01/10 01:00", ..., "12/31/10 23:00" } で、内蔵の As Of 指標の値が 1292348109（2010 年 12 月 14 日の中頃）の場合、hours of day(Hour, As_Of, "%x 00:00", 0, false) の要素は { "12/12/10 00:00", "12/12/10 01:00", ..., "12/12/10 23:00" } です。 </p> </td> 
  </tr> 
 </tbody> 
</table>
