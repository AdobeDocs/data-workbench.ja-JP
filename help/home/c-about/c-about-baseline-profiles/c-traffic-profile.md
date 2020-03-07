---
description: トラフィックプロファイルには、訪問者トラフィックを識別する次の指標が含まれています。
solution: Analytics
title: トラフィックプロファイル指標
topic: Data workbench
uuid: 7dfa18ef-d2cd-44ae-8c56-a0630a9d5cf2
translation-type: tm+mt
source-git-commit: 2e4991206394ca0c463210990ea44dfb700341a5

---


# トラフィックプロファイル指標{#traffic-profile-metrics}

トラフィックプロファイルには、訪問者トラフィックを識別する次の指標が含まれています。

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
   <td colname="col3"> 各ページでサイトに入ったセッションの数。 この指標は、ページディメンションに対してのみ評価されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 出口率 </td> 
   <td colname="col2">数式： <span class="filepath"> Exits/Page_Views </span><p>レベル：ページビュー </p></td> 
   <td colname="col3"> 各ページからサイトを離脱したセッションの割合。 離脱率指標は、ページディメンションに対してのみ評価できます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 出口 </td> 
   <td colname="col2">数式：<span class="filepath"> Page_Views[no shift(None,Page_View, Session,1)] </span><p>レベル：ページビュー </p></td> 
   <td colname="col3"> 各ページからサイトを離脱したセッションの数。 この指標は、ページディメンションに対してのみ評価されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> LVCI90 </td> 
   <td colname="col2">数式： <span class="filepath"> (raw（訪問者） - ((raw（訪問者） + .69)^0.5 * 1.281551 - 1.2269))*(Visitors/raw（訪問者）)</span><p>レベル：訪問者 </p></td> 
   <td colname="col3"> Insightからレポートされる、可能な最も少ない訪問者数の測定値。 数学的には、90%の確率で最も低い訪問者数を指定します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ページビュー期間 </td> 
   <td colname="col2"> <p>数式： <span class="filepath"> sum (exact_page_duration, page_view)*0.1/Page_Views[any Exact_Page_Duration]</span></p> <p>レベル：ページビュー </p> </td> 
   <td colname="col3"> 特定のページまたはページのグループでの平均滞在時間(MM:SS)。 この指標は、ページディメンションに対してのみ評価されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> セッションごとのページビュー数 </td> 
   <td colname="col2"> <p>数式： <span class="filepath"> Page_Views/（Page_View別のセッション） </span></p> <p>レベル：セッション </p> </td> 
   <td colname="col3"> 各セッションでのページビューの平均数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ページビュー数 </td> 
   <td colname="col2">数式： <span class="filepath"> sum(One, Page_View)</span><p>レベル：ページビュー </p></td> 
   <td colname="col3"> ページビュー数。 ページビューとは、定義済みのページに対するリクエストです（画像やその他のフィルタされたコンテンツへのアクセスはカウントされません）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ページビューの割合 </td> 
   <td colname="col2">数式： <span class="filepath"> Page_Views/total(Page_Views) </span><p>レベル：ページビュー </p></td> 
   <td colname="col3"> ページビューの割合。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> セッションの割合 </td> 
   <td colname="col2">数式：セッ <span class="filepath"> ション/合計（セッション）</span><p>レベル：セッション </p></td> 
   <td colname="col3"> セッションの割合。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 訪問者の割合 </td> 
   <td colname="col2">数式： <span class="filepath"> 訪問者数/合計（訪問者数） </span><p>レベル：訪問者 </p></td> 
   <td colname="col3"> 訪問者の割合。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 参照訪問者の割合 </td> 
   <td colname="col2"> <p>数式：Referred_Visitors/Visitors </p> <p>レベル：訪問者 </p> </td> 
   <td colname="col3"> 別のサイトからこのサイトを参照した訪問者の割合。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 参照セッション </td> 
   <td colname="col2"> <p>数式： <span class="filepath"> Sessions[リファラー&lt;&gt; 'なし'およびリファラー&lt;&gt;'ブックマーク']</span></p> <p>レベル：セッション </p> </td> 
   <td colname="col3"> 別のサイトからこのサイトを参照したセッションの数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 参照訪問者 </td> 
   <td colname="col2"> <p>数式： <span class="filepath"> Visitors[Visitor_ Referrer&lt;&gt;'None' and Visitor_Referrer&lt;&gt;'book marks']</span></p> <p>レベル：訪問者 </p> </td> 
   <td colname="col3"> 別のサイトからこのサイトを参照した訪問者の数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 定着 </td> 
   <td colname="col2"> <p>数式： <span class="filepath"> Sessions[None,Ses sion,Visitor,1) = ""] / Sessions</span></p> <p>レベル：セッション </p> </td> 
   <td colname="col3"> 訪問者が最後にセッションを行った以外のセッションの割合。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> セッション時間 </td> 
   <td colname="col2"> <p>数式： <span class="filepath"> (sum (Exact_Page_Duration, Session)*.1/Sessions)[Session_ Duration &lt;= '01:00:00']</span></p> <p>レベル：セッション </p> </td> 
   <td colname="col3">訪問者が1回のセッションに滞在した平均時間(MM:SS)。 <p><p>注意：この指標は、セグメントエクスポート機能で <a href="https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html#Segment_Export" format="http" scope="external"> 使用できます</a> 。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> ページビュー別のセッション </td> 
   <td colname="col2"> <p>数式：Page_ <span class="filepath"> View別のセッション</span></p> <p> レベル：セッション </p> </td> 
   <td colname="col3"> ページビューがあったセッションの数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> セッション数 </td> 
   <td colname="col2"> <p>数式： <span class="filepath"> sum(One, Session)</span></p> <p>レベル：セッション </p> </td> 
   <td colname="col3"> 訪問者セッションの数。 セッションとは、Webサイトの1人の訪問者に対するアクティビティの期間のことです。 各訪問者の個々のセッションは、cookie、タイムアウト、その他のヒューリスティックを使用して識別されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SCI80 </td> 
   <td colname="col2"> <p>数式：信 <span class="filepath"> 頼性（セッション） * 1.281551 /セッション</span></p> <p>レベル：訪問者 </p> </td> 
   <td colname="col3"> Data Workbenchによってレポートされる、セッション指標の信頼度の測定。 数学的には、実際の回答が時間の80%を占める範囲を指定する+/ — パーセントです。 目安として、SCI80の割合を2倍にすると、実際の回答が99%になる範囲が与えられる。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UVCI90 </td> 
   <td colname="col2"> <p>数式： <span class="filepath"> (((raw(Visitors) + .68)^0.5 * 1.281551 + 1.2269) + raw(Visitors))*( Visitors/raw(Visitors))</span></p> <p>レベル：訪問者 </p> </td> 
   <td colname="col3"> Insightからレポートされる、可能な最も多い訪問者数の測定値。 数学的には、90%の確率で最も多い訪問者数を指定します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> VCI80 </td> 
   <td colname="col2">数式： <span class="filepath"> (raw（訪問者） + .68)^0.5 * 1.281551 + 1.2269) / raw（訪問者）</span><p>レベル：訪問者 </p></td> 
   <td colname="col3"> Insightからレポートされる訪問者指標の信頼度の測定。 数学的には、実際の回答が時間の80%を占める範囲を指定する+/ — パーセントです。 目安として、VCI80の割合を2倍にすると、実際の回答が99%になる範囲が得られます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ページビュー別訪問者数 </td> 
   <td colname="col2"> <p>数式：ペー <span class="filepath"> ジビュー別訪問者数</span></p> <p>レベル：ページビュー </p> </td> 
   <td colname="col3"> ページビューがあった訪問者の数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> セッション別訪問者数 </td> 
   <td colname="col2"> <p>数式：セッシ <span class="filepath"> ョン別訪問者数 </span></p> <p>レベル：セッション </p> </td> 
   <td colname="col3"> セッションを行った訪問者の数。 </td> 
  </tr> 
 </tbody> 
</table>

