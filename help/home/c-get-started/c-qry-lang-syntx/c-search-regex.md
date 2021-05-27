---
description: data workbench は、検索および並べ替え操作に正規表現（regex）を利用します。
title: 正規表現
uuid: dc8c1e88-4d95-4011-8a38-70fae0c5cf6d
exl-id: bb1be6d8-3b7a-47e4-bb29-4a65de99666b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 67%

---

# 正規表現{#regular-expressions}

data workbench は、検索および並べ替え操作に正規表現（regex）を利用します。

**[!UICONTROL Search]**&#x200B;フィールド内で、「re:」ステートメントに続いて検索を実行できます。次に例を示します。

```
<b>re: *.s</b>
```

<table id="table_BA125AB039794EE382B33003BE4E0AFB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> メタキャラクター </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>。（ドット） </p> </td> 
   <td colname="col2"> <p>1 文字に一致します。例えば、<span class="filepath">re:x.z</span> は「xyz」や「xxz」に一致します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>*（星印） </p> </td> 
   <td colname="col2"> <p>1 文字以上に一致します。例えば、<span class="filepath">re:Z*</span> は「ZZZ」に一致します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>? （ワイルドカード） </p> </td> 
   <td colname="col2"> <p>直前の式と最小のマッチングで 0 回または 1 回一致します。例えば、<span class="filepath">xy?z</span> は「xy」と「xyz」に一致します。 </p> </td> 
  </tr> 
 </tbody> 
</table>

このほか、一般的な正規表現を使用して、さらに複雑な検索文字列を作成することもできます。正規表現は、クエリエンティティパネルを含むすべてのData Workbench検索フィールドで使用されます。

詳しくは、[正規表現](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/c-dataset-constr.html#Regular_Expressions)の説明を参照してください。
