---
description: 「データセットのスキーマ」インターフェイスには、変換データセット設定ファイルで定義されている拡張ディメンション（可算、シンプル、多対多、数値、非正規、時間の各ディメンション）とそれらのディメンション間の関係が表示されます。
title: データセットのスキーマ
uuid: 4ef5f14b-dc19-4118-a2f2-d680ded8092c
exl-id: b80e6e8e-9147-46ec-8602-2d7e5d33f077
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 76%

---

# データセットのスキーマ{#dataset-schema}

{{eol}}

「データセットのスキーマ」インターフェイスには、変換データセット設定ファイルで定義されている拡張ディメンション（可算、シンプル、多対多、数値、非正規、時間の各ディメンション）とそれらのディメンション間の関係が表示されます。

また、 [!DNL Dataset Schema] インターフェイスには、定義した派生ディメンションと、非表示に設定されている拡張ディメンションが表示されます。

![](assets/vis_DatasetSchema_Example.png)

この節では、以下のトピックについて説明します。

* [「データセットスキーマ」インターフェイスを使用してディメンションタイプを解釈するには](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-schema.md#section-16a0a12b11334c07bec558c0b7d260b1)
* [ディメンションにデフォルトのビジュアライゼーションを表示するには](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-schema.md#section-1bbb73a5cbb34ffb844eb1932db85318)
* [ディメンションに特定のビジュアライゼーションを表示するには](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-schema.md#section-d46626df90bc4c44ae60c4b71eaeac7f)

## 「データセットのスキーマ」インターフェイスでディメンションのタイプを判別するには {#section-16a0a12b11334c07bec558c0b7d260b1}

次の表に、寸法のタイプと名前が [!DNL Dataset Schema] インターフェイス。 （上記の例の）サンプルディメンションの親についても記述しています。

<table id="table_20D1A9EAAED247338476C475C63255F5"> 
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
   <td colname="col3"> <p>Visitor：このスキーマのルート可算ディメンションは Visitor です。 </p> <p> Session：親は Visitor。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 非正規 </td> 
   <td colname="col2"> 黄色 </td> 
   <td colname="col3"> DenormalPage：親は Page View。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 派生 </td> 
   <td colname="col2"> 青 </td> 
   <td colname="col3"> Next Page：親は Page View。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 多対多 </td> 
   <td colname="col2"> ピンクとグリーン（親からのステムはピンクで、ディメンション名はグリーン） </td> 
   <td colname="col3"> Search Term：親は Session。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 数値 </td> 
   <td colname="col2"> グリーン </td> 
   <td colname="col3"> Exact Page Duration：親は Page View。この例では、Exact Page Duration は、非表示の数値ディメンションです。この表の「非表示」ディメンションタイプを参照してください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> シンプル </td> 
   <td colname="col2"> グリーン </td> 
   <td colname="col3"> Page：親は Page View。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 時間 </td> 
   <td colname="col2"> グリーン </td> 
   <td colname="col3"> Hour：親は Session。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 非表示 </td> 
   <td colname="col2"> 非表示ディメンションは、適切なディメンションタイプの色を暗くしたものです。例えば、非表示の数値ディメンションは、明るさを抑えた深緑で表示されます。 </td> 
   <td colname="col3"> Exact Page Duration：親は Page View。 </td> 
  </tr> 
 </tbody> 
</table>

## ディメンションのデフォルトのビジュアライゼーションを表示するには {#section-1bbb73a5cbb34ffb844eb1932db85318}

* 内 [!DNL Dataset Schema] インターフェイスで、目的のディメンションをクリックします。 デフォルトのビジュアライゼーションが表示されます。例えば、デフォルトのビジュアライゼーションが、セッションと選択ディメンションを表示するテーブルである場合、URI ディメンションをクリックすると、セッションごとの URI のテーブルが Data Workbench に表示されます。

>[!NOTE]
>
>表示されるデフォルトのビジュアライゼーションを変更する場合は、 *Data Workbenchユーザーガイド*.

## ディメンションの特定のビジュアライゼーションを表示するには {#section-d46626df90bc4c44ae60c4b71eaeac7f}

* 内 [!DNL Dataset Schema] インターフェイスで、目的のディメンションを右クリックし、 **[!UICONTROL Add Visualization]** > *&lt;**[!UICONTROL visualization type]**>*.
