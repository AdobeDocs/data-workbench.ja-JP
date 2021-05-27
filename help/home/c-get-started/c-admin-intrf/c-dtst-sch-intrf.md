---
description: データセットスキーマインターフェイスには、変換データセット設定ファイルで定義された拡張ディメンション（可算、シンプル、多対多、数値、非正規、時間ディメンション）が表示され、これらのディメンション間の関係についての概観を示します。
title: データセットスキーマインターフェイス
uuid: 3726e568-d3ea-47f8-8ac4-582c97fbbe0a
exl-id: a8d4cf02-4ff7-4fcc-9062-425c1fe1fb28
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 70%

---

# データセットスキーマインターフェイス{#dataset-schema-interface}

データセットスキーマインターフェイスには、変換データセット設定ファイルで定義された拡張ディメンション（可算、シンプル、多対多、数値、非正規、時間ディメンション）が表示され、これらのディメンション間の関係についての概観を示します。

さらに、[!DNL Dataset Schema]インターフェイスには、定義した派生ディメンションと、非表示に設定されている拡張ディメンションが表示されます。

![](assets/vis_DatasetSchema_Example2.png)

>[!NOTE]
>
>スキーマダイアグラム内からディメンションを検索できます。 検索文字列によって見つかったディメンションの名前はハイライトされ、下位の子ディメンションで見つかったヒットに対しては親クラスの行の色が変更されます。スクロールして階層とコンテキストを表示できるよう、可算ディメンションは表示されたままになります。

**インターフェイスを使用してディメンションタイプを解釈する [!DNL Dataset Schema] には**

次の表に、[!DNL Dataset Schema]インターフェイスで名前が表示されるディメンションのタイプと色を示します。 （上記の例の）サンプルディメンションの親についても記述しています。

<table id="table_CF888522626E49A4A10D87085CAB5CC1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ディメンションタイプ </th> 
   <th colname="col2" class="entry"> Color </th> 
   <th colname="col3" class="entry"> サンプルディメンションと親 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 可算 </td> 
   <td colname="col2"> ピンク </td> 
   <td colname="col3"> <p>Visitor - このスキーマでは、Visitor はルートの可算ディメンションです。 </p> <p>Session - 親は Visitor です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 非正規 </td> 
   <td colname="col2"> 黄色 </td> 
   <td colname="col3"> DenormalPage - 親は Page View です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 派生 </td> 
   <td colname="col2"> 青 </td> 
   <td colname="col3"> Next Page - 親は Page View です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 多対多 </td> 
   <td colname="col2"> ピンクと緑（親からのステムはピンクで、ディメンション名は緑です。） </td> 
   <td colname="col3"> Search Term - 親は Session です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 数値 </td> 
   <td colname="col2"> 緑 </td> 
   <td colname="col3"> Exact Page Duration - 親は Page View です。この例では、Exact Page Duration は非表示の数値ディメンションです。この表の非表示ディメンションタイプを参照してください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> シンプル </td> 
   <td colname="col2"> 緑 </td> 
   <td colname="col3"> Page - 親は Page View です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 時間 </td> 
   <td colname="col2"> 緑 </td> 
   <td colname="col3"> Hour - 親は Session です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 非表示 </td> 
   <td colname="col2"> 非表示ディメンションは、適切なディメンションタイプの色を暗くしたものです。例えば、非表示の数値ディメンションは、より暗く、明るさの少ない緑です。 </td> 
   <td colname="col3"> Exact Page Duration - 親は Page View です </td> 
  </tr> 
 </tbody> 
</table>

これらのディメンションについて詳しくは、『*データセット設定ガイド*』を参照してください。 

**ディメンションにデフォルトのビジュアライゼーションを表示するには**

* [!DNL Dataset Schema]インターフェイスで、目的のディメンションをクリックします。 デフォルトのビジュアライゼーションが表示されます。例えば、デフォルトのビジュアライゼーションが、セッションと選択したディメンションを表示するテーブルで、URIディメンションをクリックすると、Data Workbenchにセッション別のURIを持つテーブルが表示されます。

   >[!NOTE]
   >
   >表示されるデフォルトのビジュアライゼーションを変更する場合は、「データセットスキーマインターフェイス](../../../home/c-get-started/c-admin-intrf/c-dtst-sch-intrf.md#concept-e147b3a5b542453ca2b121e1c85bb175)」を参照してください。[

**ディメンションに特定のビジュアライゼーションを表示するには**

* [!DNL Dataset Schema]インターフェイスで、目的のディメンションを右クリックし、**[!UICONTROL Add Visualization]** / *&lt;**[!UICONTROL visualization type]**>*&#x200B;をクリックします。
