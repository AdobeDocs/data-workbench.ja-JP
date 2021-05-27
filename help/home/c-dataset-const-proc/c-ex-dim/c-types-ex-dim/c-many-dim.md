---
description: 多対多ディメンションは、その親の可算ディメンションとの間に多対多の関係を持ちます。
title: 多対多ディメンション
uuid: 42c909e8-1228-4210-9406-ffc0d92372fa
exl-id: 02d1a21c-a5b4-4b58-8089-9b9c68a7b1d1
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 100%

---

# 多対多ディメンション{#many-to-many-dimensions}

多対多ディメンションは、その親の可算ディメンションとの間に多対多の関係を持ちます。

多対多ディメンションは、その親ディメンションに含まれる各エレメントの値の集合を表したもの、と考えることができます。例えば、多対多ディメンションである Search Phrase は、Session レベルのディメンションです（Session という親を持ちます）。このディメンションは、Session ディメンションを切り口として各セッションに関連付けられた検索語句の集合を表します。特定の検索語句が使用されるセッションの数は不特定であり、また、1 つのセッションには 0 個以上の検索語句が含まれています。したがって、Search Phrase ディメンションと Session ディメンションには多対多の関係が存在することになります。

多対多ディメンションは、以下のパラメーターによって定義します。

<table id="table_A6D495008DFF4DD28A3ECD718D775E54"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> パラメーター </th> 
   <th colname="col2" class="entry"> 説明 </th> 
   <th colname="col3" class="entry"> デフォルト </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 名前 </td> 
   <td colname="col2"> Data Workbench のユーザーが見てわかりやすいディメンションの名前。ディメンション名にハイフン（-）を含めることはできません。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> コメント </td> 
   <td colname="col2"> （オプション）拡張ディメンションについてのメモ。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 条件 </td> 
   <td colname="col2"> 親と入力フィールドの値との関係を作成する条件。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Hidden </td> 
   <td colname="col2"> Data Workbench のインターフェイスにディメンションを表示するかどうかを指定します。デフォルトでは false に設定されています。例えば、指標の基準としてのみ使用されるディメンションであれば、このパラメーターを true に設定して、Data Workbench に表示されないようにすることができます。 </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Input </td> 
   <td colname="col2"> <p>親ディメンション（Parent）に関連付ける値。このフィールドが文字列ベクトルである場合、その各エレメントが、親との間に独自の関係を持ちます。 </p> <p> <p>注意：親ディメンションの特定のエレメントについて、すべてのログエントリの入力値が空である場合、親ディメンションのそのエレメントに多対多ディメンションのエレメントは一切関連付けられません。 </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Parent </td> 
   <td colname="col2"> 親ディメンションの名前。すべての可算ディメンションは、親ディメンションになることができます。 </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

次の例は、Web サイトトラフィックから収集されたイベントデータを使用する多対多ディメンションの定義です。この多対多ディメンションは、訪問者が特定のセッション期間に購入した製品に対してそのセッションを関連付けるもので、「Selected Product」という名前が付けられています。x-products フィールドは、値のベクトルを含んでいます。ベクトル内の値はそれぞれページビューに関連付けられ、ページビューはセッションに関連付けられています。

![](assets/cfg_Transformation_Dim_ManytoMany.png)

このような変換を作成することによって、選択した製品ディメンションとその各製品を含んだセッションの数との関係を描写するビジュアライゼーションを Data Workbench で作成することができます。
