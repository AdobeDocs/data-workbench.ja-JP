---
description: 待ち時間ディメンションは、Sessions（セッション）などの可算ディメンションや、Day（日）などの時間ディメンションである親ディメンションから作成されます。
title: 待ち時間ディメンションの作成
uuid: 531d8bf6-a66f-4b02-9d81-05664fb9c988
exl-id: 38b470ef-9409-455b-b2b8-b0391f80b800
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '542'
ht-degree: 88%

---

# 待ち時間ディメンションの作成{#create-a-latency-dimension}

待ち時間ディメンションは、Sessions（セッション）などの可算ディメンションや、Day（日）などの時間ディメンションである親ディメンションから作成されます。

Data Workbenchで待ち時間テーブルを作成すると、ビジュアライゼーションファイル(.vw)に待ち時間ディメンションが自動的に追加されます。 以下の手順に従って、テーブルの待ち時間ディメンションを編集できます。

**待ち時間ディメンションを編集するには**

1. 作成した待ち時間テーブルをメモ帳などのテキストエディターで開きます。このフォルダーは、ユーザーのインストールディレクトリ内のUser > `working profile name` > WorkData Workbenchーにあります。

   定義された待ち時間ディメンションには、次の例に示すパラメーターが含まれています（待ち時間ディメンションの定義には、他のパラメーターが含まれている場合もあります）。[!DNL line entity = LatencyDim:]は、待ち時間ディメンションの定義の開始を示します。

   ```
   entity = LatencyDim:
   Name = string: dimension name
   Level = ref: wdata/model/dim/level
   Clip = ref: wdata/model/dim/clip
   Time = ref: wdata/model/dim/time dimension
   Format = printf_format: 
   format = string: %+0.0f time string
   offset = double: offset
   Time Before = int: time before
   Time After = int: time after
   ```

1. 以下の表を参考にして、Name、Level、Clip、Time、Format、Time Before または Time After パラメーターの値を編集します。

   <table id="table_13DF30B8B7314F118D0ED5DF9EA70B9B"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> パラメーター </th> 
      <th colname="col2" class="entry"> 入力する情報 </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> <p>名前 </p> </td> 
      <td colname="col2"> <p>（オプション）ディメンションラベルまたはエレメントを右クリックしたときにコンテキストメニューに表示される待ち時間ディメンションの名前。 </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Level </p> </td> 
      <td colname="col2"> <p>待ち時間ディメンションの親である可算ディメンション。セッション、訪問者、ページビューなどがあります。 </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>クリップ </p> </td> 
      <td colname="col2"> <p>待ち時間ディメンションのレベルと 1 対多の関係にある可算ディメンション。待ち時間は、このディメンションの境界を超える計算されません。例えば、ページビューのレベルとセッションのクリップを指定した場合、待ち時間は、同じセッション中にイベントとして発生したページビューに対して計算されます。 </p> <p>1 対多の（単純な）ディメンションの詳細については、『<i>データセット設定ガイド</i>』を参照してください。 </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>時間 </p> </td> 
      <td colname="col2"> <p>待ち時間ディメンションの経過時間を計測するために使用されるディメンション。このディメンションには、日や時間などの時間ディメンション、または訪問者、セッション、ページビューなどの可算ディメンションを指定できます。 </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 形式 </td> 
      <td colname="col2"> <p>（オプション）待ち時間のビジュアライゼーションのData Workbenchを指定します。 Format パラメーターでは、次の値を編集できます。 
      <ul id="ul_ABF4C17BDE2E4F6C9CBDD933674DE861"> 
         <li id="li_5ED6A7267C81444983AF8507ADC6A5AB">時間文字列。待ち時間のビジュアライゼーションに表示される時間の単位（日や週など）。時間ディメンションを変更した場合は、時間文字列も変更してください。 </li> 
         <li id="li_E3B517ECE1494221AAE90455CC0AAB42">オフセット。Time Before の値を負の値にした整数。例えば、Time Before が 7 の場合、オフセットは -7 となります。 </li> 
      </ul> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Time Before </p> </td> 
      <td colname="col2"> <p>待ち時間が計算されるイベントの前の最大時間（Time ディメンションの単位で表現します）。この値が 0 の場合、またはこの値を設定しない場合、待ち時間は、未来に向かってのみ計算されます。 </p> <p>この値を変更した場合は、Format パラメーターのオフセット値も変更してください。オフセットの値は、Time Before の値を負の値にした整数です。 </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Time After </p> </td> 
      <td colname="col2"> <p>待ち時間が計算されるイベントの後の最大時間（Time ディメンションの単位で表現します）。 </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. [!DNL .vw]ファイルをUser\*working profile name*\Workフォルダーに保存します。

   次に、デフォルトの待ち時間ディメンションの設定を示します。

   ```
   entity = LatencyDim:
   Name = string: 
   Level = ref: wdata/model/dim/Session
   Clip = ref: wdata/model/dim/Visitor
   Time = ref: wdata/model/dim/Day
   Time Before = int: 7
   Time After = int: 7
   ```

   次の待ち時間ディメンションでは、各セッションイベントの待ち時間が時間単位で計算され、Time Before が 0 に設定されています。したがって、待ち時間は、定義されたイベントの後 24 時間以内に発生したセッションに対してのみ計算されます。

   ```
   entity = LatencyDim:
   Name = string:
   Level = ref: wdata/model/dim/Session
   Clip = ref: wdata/model/dim/Visitor
   Time = ref: wdata/model/dim/Hour
   Time Before = int: 0
   Time After = int: 24
   ```
