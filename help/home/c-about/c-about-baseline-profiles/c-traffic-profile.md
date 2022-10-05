---
description: トラフィックプロファイルには、訪問者トラフィックを識別するための次の指標が含まれています。
title: トラフィックプロファイルの指標
uuid: 7dfa18ef-d2cd-44ae-8c56-a0630a9d5cf2
exl-id: 38f191e5-5b30-4fe0-a680-bcb33fe52eca
source-git-commit: 4ab43bfbad96096fb2cebd77a8be8fa6d49fa7dc
workflow-type: tm+mt
source-wordcount: '709'
ht-degree: 2%

---

# トラフィックプロファイルの指標{#traffic-profile-metrics}

{{eol}}

トラフィックプロファイルには、訪問者トラフィックを識別するための次の指標が含まれています。

<table id="table_D981FB9F8B734E3C845A9628548565F1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 指標 </th> 
   <th colname="col2" class="entry"> 指標の数式とレベル </th> 
   <th colname="col3" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 入口 </td> 
   <td colname="col2">数式： <span class="filepath"> Page_Views[no shift(None,Page_View, Session,-1)]</span><p>レベル：ページビュー </p></td> 
   <td colname="col3"> 各ページでサイトに入ったセッションの数。 この指標は、Page ディメンションに対してのみ評価されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 出口率 </td> 
   <td colname="col2">数式： <span class="filepath"> 出口/ページビュー </span><p>レベル：ページビュー </p></td> 
   <td colname="col3"> 各ページからサイトを離脱したセッションの割合。 出口率指標は、ページディメンションに対してのみ評価できます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 出口 </td> 
   <td colname="col2">数式：<span class="filepath"> Page_Views[no shift(None,Page_View, Session,1)] </span><p>レベル：ページビュー </p></td> 
   <td colname="col3"> 各ページからサイトを離脱したセッション数。 この指標は、Page ディメンションに対してのみ評価されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> LVCI90 </td> 
   <td colname="col2">数式： <span class="filepath"> (raw（訪問者） - ((raw（訪問者） + .69)^0.5 * 1.281551 - 1.2269))*(Visitors/raw（訪問者）)</span><p>レベル：訪問者 </p></td> 
   <td colname="col3"> Insight から報告される、可能な訪問者の最も少ない数の指標です。 数学的には、90%の確率で最も低い訪問者数を指定します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ページ表示時間 </td> 
   <td colname="col2"> <p>数式： <span class="filepath"> sum (exact_page_duration, page_view)*0.1/Page_Views[any Exact_Page_Duration]</span></p> <p>レベル：ページビュー </p> </td> 
   <td colname="col3"> 特定のページまたはページのグループで費やした平均時間 (MM:SS)。 この指標は、Page ディメンションに対してのみ評価されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> セッションあたりのページビュー数 </td> 
   <td colname="col2"> <p>数式： <span class="filepath"> Page_Views/（Page_View 別のセッション） </span></p> <p>レベル：セッション </p> </td> 
   <td colname="col3"> ページビューがある各セッションの平均ページビュー数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ページビュー数 </td> 
   <td colname="col2">数式： <span class="filepath"> sum(One, Page_View)</span><p>レベル：ページビュー </p></td> 
   <td colname="col3"> ページビュー数。 ページビューとは、定義されたページに対する要求です（画像やその他のタイプのフィルターされたコンテンツへのアクセスはカウントされません）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ページビュー数の% </td> 
   <td colname="col2">数式： <span class="filepath"> Page_Views/total(Page_Views) </span><p>レベル：ページビュー </p></td> 
   <td colname="col3"> ページビューの割合。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> セッションの% </td> 
   <td colname="col2">数式： <span class="filepath"> セッション/合計（セッション）</span><p>レベル：セッション </p></td> 
   <td colname="col3"> セッションの割合。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 訪問者の% </td> 
   <td colname="col2">数式： <span class="filepath"> 訪問者数/合計（訪問者数） </span><p>レベル：訪問者 </p></td> 
   <td colname="col3"> 訪問者の割合。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> %参照訪問者 </td> 
   <td colname="col2"> <p>数式：Referred_Visitors/Visitors </p> <p>レベル：訪問者 </p> </td> 
   <td colname="col3"> 別のサイトからこのサイトを参照した訪問者の割合。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 参照セッション </td> 
   <td colname="col2"> <p>数式： <span class="filepath"> Sessions[Referrer&lt;&gt; 'None'および Referrer&lt;&gt;'bookmark']</span></p> <p>レベル：セッション </p> </td> 
   <td colname="col3"> 別のサイトからこのサイトを参照したセッションの数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 参照による訪問者 </td> 
   <td colname="col2"> <p>数式： <span class="filepath"> Visitors[Visitor_Referrer&lt;&gt;'None' and Visitor_Referrer&lt;&gt;'book marks']</span></p> <p>レベル：訪問者 </p> </td> 
   <td colname="col3"> 別のサイトからこのサイトに導かれた訪問者の数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 定着 </td> 
   <td colname="col2"> <p>数式： <span class="filepath"> Sessions[shift(None,Ses sion,Visitor,1) = ""] / Sessions</span></p> <p>レベル：セッション </p> </td> 
   <td colname="col3"> 訪問者が最後のセッションに含まれていないセッションの割合。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> セッション時間 </td> 
   <td colname="col2"> <p>数式： <span class="filepath"> (sum (Exact_Page_Duration, Session)*.1/Sessions)[Session_ Duration &lt;= '01:00:00']</span></p> <p>レベル：セッション </p> </td> 
   <td colname="col3">訪問者がセッションに費やした平均時間 (MM:SS)。 <p><p>注意：この指標を <a href="https://experienceleague.adobe.com/docs/data-workbench/using/client/t-open-ins.html#Segment_Export" format="http" scope="external"> セグメントの書き出し</a> 機能。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> ページビュー別セッション数 </td> 
   <td colname="col2"> <p>数式： <span class="filepath"> Page_View 別のセッション</span></p> <p> レベル：セッション </p> </td> 
   <td colname="col3"> ページビューを持つセッションの数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> セッション数 </td> 
   <td colname="col2"> <p>数式： <span class="filepath"> sum(One, Session)</span></p> <p>レベル：セッション </p> </td> 
   <td colname="col3"> 訪問者セッションの数。 セッションとは、Web サイトの 1 人の訪問者に対するアクティビティの期間のことです。 各訪問者の個々のセッションは、cookie、タイムアウト、およびその他の発見的方法を使用して識別されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SCI80 </td> 
   <td colname="col2"> <p>数式： <span class="filepath"> confidence(Sessions) * 1.281551 / Sessions</span></p> <p>レベル：訪問者 </p> </td> 
   <td colname="col3"> Data Workbench からレポートされる、セッション指標の信頼性の尺度です。 数学的には、実際の回答が 80%の時間範囲を示す+/ — パーセンテージです。 経験則として、SCI80 の割合を 2 倍にすると、実際の回答が 99%の確率で得られる範囲が得られます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UVCI90 </td> 
   <td colname="col2"> <p>数式： <span class="filepath"> (((raw（訪問者） + .68)^0.5 * 1.281551 + 1.2269) + raw（訪問者）)*( Visitors/raw（訪問者）)</span></p> <p>レベル：訪問者 </p> </td> 
   <td colname="col3"> Insight から報告される、可能な訪問者の最も高い数の指標。 数学的には、確率 90%の最高の訪問者数を指定します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> VCI80 </td> 
   <td colname="col2">数式： <span class="filepath"> ((raw（訪問者） + .68)^0.5 * 1.281551 + 1.2269) / raw（訪問者）</span><p>レベル：訪問者 </p></td> 
   <td colname="col3"> Insight から報告される、訪問者指標の信頼性の尺度です。 数学的には、実際の回答が 80%の時間範囲を示す+/ — パーセンテージです。 経験則として、VCI80 の割合を 2 倍にすると、実際の回答が 99%の確率で得られる範囲が得られます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ページビュー別訪問者数 </td> 
   <td colname="col2"> <p>数式： <span class="filepath"> ページビュー別訪問者数</span></p> <p>レベル：ページビュー </p> </td> 
   <td colname="col3"> ページビューを持つ訪問者の数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> セッション別訪問者数 </td> 
   <td colname="col2"> <p>数式： <span class="filepath"> セッション別訪問者数 </span></p> <p>レベル：セッション </p> </td> 
   <td colname="col3"> セッションをおこなった訪問者の数。 </td> 
  </tr> 
 </tbody> 
</table>
