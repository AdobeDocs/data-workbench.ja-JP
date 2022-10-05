---
description: リソースモニターベクトルには、Memory Budget Monitor と Number of Queries Monitor が含まれます。
title: クエリキューのリソースモニター
uuid: 6b516bed-7f9a-4821-869e-19e720f20313
exl-id: 6d445a4d-a415-41ce-9d45-1bdd0e726edd
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 100%

---

# クエリキューのリソースモニター{#query-queue-resource-monitors}

{{eol}}

リソースモニターベクトルには、Memory Budget Monitor と Number of Queries Monitor が含まれます。

以下の表に、クエリーをキューに格納するために使用するリソースモニターフィールドを示します。

<table id="table_9991EED2647A460FACA2DC80D4973A8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> フィールド </th> 
   <th colname="col2" class="entry"> タイプ </th> 
   <th colname="col3" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Memory Budget Monitor </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>現在のユーザーグループが使用するクエリーメモリをモニタリングします。現在の使用量が Low Threshold と High Threshold の間である場合、ユーザーがワークスペースを閉じるなどしてメモリ使用量が Low Threshold の値を下回るまで、新しいバンチはスケジューリングされません。スケジュール済みのバンチの増大は許可されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>High Threshold </p> </td> 
   <td colname="col2"> <p>double </p> </td> 
   <td colname="col3"> <p>メモリ使用量の高しきい値（バイト単位）。メモリ使用量がこの値を上回る場合、スケジューリングは行われません。また、メモリ使用量がこの値を下回るまで、しばらくの間、最も優先順位が低いスケジュール済みバンチのスケジュールが一度に 1 つずつ取り消されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Low Threshold </p> </td> 
   <td colname="col2"> <p>重複 </p> </td> 
   <td colname="col3"> <p>メモリ使用量の低しきい値（バイト単位）。<span class="wintitle">Memory Budget Monitor</span> の値がこの値を下回る場合、新しいバンチのスケジュールおよびスケジュール済みバンチの増大が許可されます。例えば、ユーザーがワークスペースにビジュアライゼーションを追加すると、バンチが増大します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Reaction Time </p> </td> 
   <td colname="col2"> <p>重複 </p> </td> 
   <td colname="col3"> <p>メモリ使用量予測のスムージングに使用される時間定数。スムージング値によって、使用量の急増への反応を回避します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Number of Queries Monitor </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>プロファイルに対して現在スケジュールされているクエリーの合計数をモニタリングします。このリソースモニターを使用すると、クエリーの合計数が「Low Threshold」フィールドの値を下回っている場合に、バンチをスケジュールできます。このモニターは、クエリーの合計数が「High Threshold」フィールドの値を下回っている場合に、現在スケジュールされているバンチの増大を許可します。さらに、優先順位がより高いバンチのスケジュールまたは増大を許可するために、優先順位が低いバンチを削除します。ただし、この設定は、「Untouchable Priority」フィールドで指定された値より高い優先順位を持つバンチを妨げません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>高しきい値 </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>メモリ使用量の高しきい値（バイト単位）。メモリ使用量がこの値を上回る場合、スケジューリングは行われません。また、メモリ使用量がこの値を下回るまで、しばらくの間、最も優先順位が低いスケジュール済みバンチのスケジュールが一度に 1 つずつ取り消されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>低しきい値 </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>メモリ使用量の低しきい値（バイト単位）。<span class="wintitle">Memory Budget Monitor</span> の値がこの値を下回る場合、新しいバンチをスケジュールすることができます。スケジュール済みバンチは増大可能です。 </p> </td> 
  </tr> 
 </tbody> 
</table>
