---
description: 時間ディメンションを使用すると、Input Time (1970 epoch) パラメーターに指定した任意のタイムスタンプフィールドに基づいて、定期的または絶対的なローカル時間ディメンション（日、曜日、時間帯、予約時刻など）のグループを作成できます。
title: 時間ディメンション
uuid: b633cf4f-0db4-4378-9e59-43b6ad8f772d
exl-id: f9534b24-3a16-4220-bac2-bc541e121005
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 100%

---

# 時間ディメンション{#time-dimensions}

時間ディメンションを使用すると、Input Time (1970 epoch) パラメーターに指定した任意のタイムスタンプフィールドに基づいて、定期的または絶対的なローカル時間ディメンション（日、曜日、時間帯、予約時刻など）のグループを作成できます。

時間ディメンションを定義する際に、週の開始日パラメーターを指定することで、月曜日以外の曜日を週の最初の日として選択できます。ディメンション名さえ異なっていれば、データセットには、時間ディメンションのグループを複数定義できます。

時間ディメンションは、以下のパラメーターによって定義します。

<table id="table_9734F6CD7ABA4661A2F9A5FB948A7282"> 
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
   <td colname="col2"> Data Workbench に表示される、ディメンションのわかりやすい名前。ディメンション名にハイフン（-）を含めることはできません。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> コメント </td> 
   <td colname="col2"> （オプション）拡張ディメンションについてのメモ。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ディメンション </td> 
   <td colname="col2"> <p>次に示した任意の期間についてディメンション名を指定できます。 </p> <p> 
     <ul id="ul_EB0837DD66BE4004A615A6029EEF4CD5"> 
      <li id="li_2E46E6DB004E443C8CC831DCEE743D60"> 日 </li> 
      <li id="li_F59A27779EBE4E2A84E0972EE8BCDFA7"> 曜日 </li> 
      <li id="li_7D74CD547ED1449091EF7B2E0E8C46DE"> 時間 </li> 
      <li id="li_706AF9D385CB44C098DEBACA3BA2CD4B"> 時刻 </li> 
      <li id="li_76FBF69B25954885A0192D308A155E41"> 月 </li> 
      <li id="li_3C16955BE5C54291A25E25CD31259661"> 週 </li> 
     </ul> </p> <p> ここに入力した名前は、ディメンションメニューのほか、Data Workbench のビジュアライゼーションに表示されます。時間ディメンションの名前を空欄にした場合、データセットにディメンションは作成されません。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Hidden </td> 
   <td colname="col2"> Data Workbench のインターフェイスにディメンションを表示するかどうかを指定します。デフォルトでは false に設定されています。例えば、指標の基準としてのみ使用されるディメンションであれば、このパラメーターを true に設定して、Data Workbench に表示されないようにすることができます。 </td> 
   <td colname="col3"> true </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Input Time (1970 epoch) </td> 
   <td colname="col2"> <p>入力として使用するタイムスタンプフィールドの名前。 </p> <p> <p>注意：このフィールドの値は、1970 年 1 月 1 日 00:00:01 からの秒数を表している必要があります。Input Time が有効な時間（1970 ～ 2037）ではない場合、変換プロセスは失敗し、Data Workbench サーバーからエラーが生成されます。 </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Parent </td> 
   <td colname="col2"> 親ディメンションの名前。すべての可算ディメンションは、親ディメンションになることができます。Web データの場合、親は Session です。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Week Start Day </td> 
   <td colname="col2"> <p>週の第 1 日として使用する曜日。 </p> <p> このパラメーターは、Week ディメンションや Day of Week ディメンションのほか、週の観点で定義されているすべての時間報告ディメンションに影響します。 </p> </td> 
   <td colname="col3"> Mon </td> 
  </tr> 
 </tbody> 
</table>

この例では、ユーザー定義の入力フィールド x-time-1970 に基づいて時間ディメンションのグループを作成します。この時間ディメンションのグループ名は「Session Time」です。各ディメンションの親は Session ディメンションであるので、時間ディメンションの各エレメントは、セッション期間の開始時間と対応します。Week ディメンションの各週の始まりは、Week Start Day パラメーターにより月曜日に指定されています。

![](assets/cfg_Transformation_Dim_TimeDim.png)
