---
description: フィルターは、データセット内のデータのサブセットを定義する式です。
title: フィルター式の構文
uuid: faeb6847-3295-48ab-9d1c-db00f57647ba
exl-id: 515c1645-69c8-4990-a913-d2d505c6fe51
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '789'
ht-degree: 94%

---

# フィルター式の構文{#syntax-for-filter-expressions}

フィルターは、データセット内のデータのサブセットを定義する式です。

フィルターは、ディメンション間の関係に従って、各ディメンションの各要素を通すか、通さないかを決定します。

フィルターは[!DNL Filter Editor]を使用して編集できます。 [フィルターエディター](../../../home/c-get-started/c-analysis-vis/c-filter-editors/c-filter-editors.md#concept-2f343ecbed8240f18b0c1f1eccef11e3)を参照してください。

次の表の各構文の説明には、そのフィルターを使用する指標式の例があります。例えば、「Sessions[True]」は、「True」フィルターを使用して定義された指標です。 TrueフィルターはSessionディメンションのすべての要素を通すので、 Sessions[True]指標はSessions指標と同じです。

<table id="table_5D66E6C11B384460BAAA7A6130214594"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>True </p> </td> 
   <td colname="col2"> <p>定数フィルター。すべてのディメンションのすべての要素を通します。 </p> <p>例：Sessions[ True ] は Sessions と同じです。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>False </p> </td> 
   <td colname="col2"> <p>定数フィルター。すべてのディメンションのすべての要素を通しません。 </p> <p>例：Sessions[ False ] は常に 0 です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>not Filter </p> </td> 
   <td colname="col2"> <p>Filter が通さない要素を通します。 </p> <p>例：Sessions[ not Page=”A” ] は、ページ A を訪問しなかったセッションの数です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>FilterA and FilterB </p> </td> 
   <td colname="col2"> <p>FilterA および FilterB が通す要素を通します。 </p> <p>例：Sessions[ Page=”A” and Page=”B” ] は、ページ A およびページ B をともに訪問したセッションの数です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>FilterA or FilterB </p> </td> 
   <td colname="col2"> <p>FilterA または FilterB が通す要素を通します。 </p> <p>例：Sessions[ Page=”A” or Page=”B” ] は、ページ A、ページ B またはその両方を訪問したセッションの数です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Filter by Dim </p> </td> 
   <td colname="col2"> <p>ディメンション Dim の要素のうち、Filter が通す要素のセットを通します。 </p> <p>例：Sessions[ Page=”/home” by Visitor ] は、ページ「/home」を表示した訪問者に属するセッションの数です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>識別子 </p> </td> 
   <td colname="col2"> <p>プロファイル以外で定義されたフィルターを参照します。 </p> <p>例：Sessions[ Broken_Session_Filter ] は、Broken Session Filter が通すセッションの数です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim = “Value” </p> </td> 
   <td colname="col2"> <p>ディメンション Dim の指定した要素を通します。 </p> <p>例：Sessions[ Page=”A” ] は、ページ A を訪問したセッションの数です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt;&gt; “Value” </p> <p>Dim != “値” </p> </td> 
   <td colname="col2"> <p>ディメンション Dim の指定した要素以外をすべて通します。 </p> <p>例：Sessions[ Page&lt;&gt;”A” ] は、A 以外のページを訪問したセッションの数です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dim = #Ordinal </td> 
   <td colname="col2"> <p>ディメンション Dim の要素のうち、順序の値が Ordinal の要素を通します。 </p> <p>例：Sessions[ Month=#0 ] は、データセットの最初の月のセッションの数です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt;&gt; #Ordinal </p> <p>ディム！= #Ordinal </p> </td> 
   <td colname="col2"> <p>ディメンション Dim の指定した要素以外をすべて通します。 </p> <p>例：Sessions[ Session_Value &lt;&gt; #0 ] は、セッション値が 0 以外のセッションの数です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim matches “Expr” </p> </td> 
   <td colname="col2"> <p>ディメンション Dim の要素のうち、指定した正規表現に一致する要素を通します。Dim を非正規ディメンションまたは可算ディメンションにすることはできません。 </p> <p>例：Sessions[ URI matches “.*/product/.*” ] は、product ディレクトリのいずれかのページを訪問したセッションの数です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim notmatches “Expr” </p> </td> 
   <td colname="col2"> <p>ディメンション Dim の要素のうち、指定した正規表現に一致しない要素を通します。Dim を非正規ディメンションまたは可算ディメンションにすることはできません。 </p> <p>例：Sessions[ URI notmatches “.*\.jsp” ] は、JSP ページ以外のページを訪問したセッションの数です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt; “Value” </p> </td> 
   <td colname="col2"> <p>ディメンション Dim の要素のうち、要素 “Value” の順序の値よりも、順序の値が小さい要素を通します。“Value” がディメンションの要素ではない場合、ディメンションの現在のすべての要素よりも大きいものと見なされます。 </p> <p>例：Sessions[ Month &lt; “Jul ‘04” ] は、2004 年 7 月よりも前に発生したセッションの数です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &gt; “Value” </p> </td> 
   <td colname="col2"> <p>ディメンション Dim の要素のうち、要素 “Value” の順序の値よりも、順序の値が大きい要素を通します。“Value” がディメンションの要素ではない場合、ディメンションの現在のすべての要素よりも大きいものと見なされます。 </p> <p>例：Sessions[ Month &gt; “Jul ‘04” ] は、2004 年 7 月よりも後に発生したセッションの数です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt;= “Value” </p> </td> 
   <td colname="col2"> <p>ディメンション Dim の要素のうち、要素 “Value” の順序の値よりも、順序の値が小さいか等しい要素を通します。“Value” がディメンションの要素ではない場合、ディメンションの現在のすべての要素よりも大きいものと見なされます。 </p> <p>例：Sessions[ Session_Number &lt;= “2” ] は、ある訪問者の最初のセッションまたは 2 番目のセッションであったセッションの数です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dim &gt;= “Value” </td> 
   <td colname="col2"> <p>ディメンション Dim の要素のうち、要素 “Value” の順序の値よりも、順序の値が大きいか等しい要素を通します。“Value” がディメンションの要素ではない場合、ディメンションの現在のすべての要素よりも大きいものと見なされます。 </p> <p>例：Sessions[ Session_Number &gt;= “5” ] は、ある訪問者の 5 番目以降のセッションであったセッションの数です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>any Dim </p> </td> 
   <td colname="col2"> <p>ディメンション Dim のすべての要素を通します。 </p> <p>例：Sessions[ any Page_View ] は、少なくとも 1 度ページが表示されたセッションの数です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>no Dim </p> </td> 
   <td colname="col2"> <p>any Dim が通さない要素を通します。 </p> <p>例：Sessions[ no Page_View ] は、ページが表示されなかったセッションの数です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>(フィルター) </p> </td> 
   <td colname="col2"> <p>フィルターと同じです。フィルター式の一部のグループ化に使用します。 </p> </td> 
  </tr> 
 </tbody> 
</table>
