---
description: User Groups パラメーターを定義するテーブルです。
title: クエリキューのユーザーグループ
uuid: 90d9058c-1809-4579-a8c6-930a07affc83
exl-id: e9586ad4-4c0b-48b7-b533-4d23a0f4a216
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 100%

---

# クエリキューのユーザーグループ{#query-queue-user-groups}

{{eol}}

User Groups パラメーターを定義するテーブルです。

<table id="table_670A47E25A7A43F0B599BD7ABB173E69"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> フィールド </th> 
   <th colname="col2" class="entry"> タイプ </th> 
   <th colname="col3" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>名前 </p> </td> 
   <td colname="col2"> <p>string </p> </td> 
   <td colname="col3"> <p>ユーザーグループのユーザー定義名（Analysts など）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ポリシー </p> </td> 
   <td colname="col2"> <p>vector </p> </td> 
   <td colname="col3"> <p>ポリシータイプを指定します。右クリックして、「Standard Policy」または「Daily Schedule」を選択します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Standard Policy </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Standard Policy では、優先順位がより高いユーザーがキューに入ってきた場合でも、優先順位の低いユーザーが次第にキューの上位に移動してスケジュールされます。1 つのグループに同じタイプの複数のポリシーを追加できます。複数のポリシーの効果は累積的になります。 
     <ul id="ul_F7F60D23DC934F61AF2183177A11FA65"> 
      <li id="li_805ED3E740814FAEBFF2B411BAB3D248"><b>Priority Limit：</b>優先順位をそれ以上インクリメントしない上限。優先順位の最大値です。この値を使用すると、このポリシーによって生成される優先順位を特定の範囲に保つことができます（例えば、他のユーザーグループの優先順位を常により高くしたり、Untouchable Priority より上にならないようにするなど）。 </li> 
     </ul> </p> <p> <b>Standard Policy Increments</b> </p> <p>Standard Policy のインクリメント設定により、時間の経過に伴って、クエリーバンチの優先順位が上がります。これは、バンチのスケジュールを強制するものではありませんが、この設定を使用して、長時間待機しているユーザーを優先できます。キューに格納されるパラメーターは、現在キューに格納されているクエリー（リソースが不十分で完了できないために保留されているクエリーなど）に影響を与えます。スケジュール済みのパラメーターは、回答中のクエリーに影響を与えます。クエリーの優先順位は、該当するインクリメントフィールドとインクリメント間隔フィールドで指定された数値に従って上がります。 
     <ul id="ul_7A5EE18CE10E4484A203B938525C806C"> 
      <li id="li_4B5CD827AF3848DA811A96C851340518"><b>Queued Increment：</b>キュー格納済みクエリーの優先順位が更新のたびにインクリメントされる値を設定します。この設定により、優先順位の低いユーザーがスケジューリングキューを上方に移動します。 </li> 
      <li id="li_91CA798235234A1CAC7AB32A7FB1CE84"><b>Queued Increment Interval：</b>キュー格納済みクエリーの優先順位の更新間隔を秒数で設定します。 </li> 
      <li id="li_079275E21ABA43B796A853624A6BDC29"><b>Scheduled Increment：</b>スケジュール済みクエリーの優先順位が更新のたびにインクリメントされる値を設定します。 </li> 
      <li id="li_3AE2EC3EBE6C4670BA0FA1BBD03FEBBD"><b>Scheduled Increment Interval：</b>スケジュール済みクエリーの優先順位の更新間隔を秒数で設定します。 <p> <p>注意：インクリメントと更新間隔の値を、キュー格納済みバンチがスケジュール済みバンチより高くなるように設定すると、「揺れ」が生じることがあります（例えば、Queued Increment 値を 100、Scheduled Increment を 0、Queued Increment Interval を 1、Untouchable Priority が高くなるように設定するとしましょう。 ベースとなる優先順位が 0 の 2 つのクエリーバンチを受け取り、両方のクエリーを同時に実行するだけのリソースがない場合、どちらか 1 つがスケジュールされます。1 秒後、スケジュールされなかったクエリーの優先順位は 100 になり、スケジュールされたクエリーに取って代わります。さらに 2 秒後、取って代わられたクエリーの優先順位が 200 になり、2 つのクエリーの位置が再度入れ替わります。2 秒ごとに、もう一方のクエリーを実行できるよう、計算中のクエリーが妨げられるので、どちらのクエリーも完了しません）。 </p> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Daily Schedule Policy </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>1 日の特定の時間に優先順位を変更できます。このスケジュールは、<span class="wintitle">レポートサーバー</span>などの自動化されたクライアントおよびシステムのユーザーが様々なタイムゾーンにいる場合に役立ちます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>変更点 </p> </td> 
   <td colname="col2"> <p>int </p> </td> 
   <td colname="col3"> <p>右クリックして、スケジュール済みの優先順位の変更を追加します。Change Time は、変更が行われる時刻です。形式は hour:minutes AM/PM です。AM または PM を入力しない場合は、24 時間制が使用されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Priority Limit </p> </td> 
   <td colname="col2"> <p>int </p> </td> 
   <td colname="col3"> <p>変更によって得られる優先順位の最大値。Priority Change は、優先順位に追加される量です。例えば、値 0 はデフォルトの優先順位に戻ります。その他すべての値の場合は、デフォルトの優先順位にこの数値が付加された優先順位になります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ユーザー </p> </td> 
   <td colname="col2"> <p>ベクトル </p> </td> 
   <td colname="col3"> <p>グループのメンバーであるユーザーをリストします。 </p> <p> <b>Name：</b>ユーザーの証明書の「Common Name」フィールドに表示されるユーザーの名前。 </p> <p> <b>Extra Priority：</b>そのユーザーの開始優先順位を決定するため、ユーザーグループのベースの優先順位に付加する優先順位を指定します。 </p> </td> 
  </tr> 
 </tbody> 
</table>
