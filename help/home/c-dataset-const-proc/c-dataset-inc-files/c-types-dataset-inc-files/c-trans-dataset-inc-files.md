---
description: 継承プロファイルの変換データセットインクルードファイルには、データセット構築の変換段階に関連したパラメーターが含まれます。
title: 変換データセットインクルードファイル
uuid: 46756f68-843c-4b0d-a79e-f107ef85db6c
exl-id: 58793f82-162a-4d43-aea9-163716c82db6
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '529'
ht-degree: 69%

---

# 変換データセットインクルードファイル{#transformation-dataset-include-files}

{{eol}}

継承プロファイルの変換データセットインクルードファイルには、データセット構築の変換段階に関連したパラメーターが含まれます。

ファイルの先頭行には、Extended Dimensions、Parameters、Reprocess、Stage、Transformations の各パラメーターをすべてサポートする [!DNL TransformationInclude] 型が定義されます。その他のパラメーターはすべて、データセットプロファイルの Dataset ディレクトリにある [!DNL Transformation.cfg] ファイルの中で定義する必要があります。

拡張Dimension、パラメータ、再処理、ステージ、変換以外のパラメータを [!DNL Transformation Dataset Include] ファイルでエラーが発生しました。

次の名前を指定できます。 [!DNL Transformation Dataset Include] ファイルに含める必要のあるものは何でも指定しますが、ファイルの拡張子はにする必要があります [!DNL .cfg]. ファイルは、*inherited profile name*\Dataset\Transformation ディレクトリ内に格納されていることが必要です。データセット構築の変換段階でファイルが再帰的に読み込まれるので、 [!DNL Transformation Dataset Include] ディレクトリ内の任意のレベルのファイル ( 例： *継承されたプロファイル名*\Dataset\Transformation\*フォルダー名*\*インクルードファイル名*.cfg) を参照してください。

>[!NOTE]
>
>Site 用の多くの Web 固有の設定パラメーターは、 [!DNL Transformation Dataset Include] ファイル。 これらのパラメーターについて詳しくは、 [Web データの設定](../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).

次の表に、 [!DNL Transformation Dataset Include] ファイル：

<table id="table_7BD343888D9145BCBA889B531A4D18F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> パラメーター </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 拡張ディメンション </td> 
   <td colname="col2"> （オプション）。拡張ディメンションを定義します。詳しくは、 <a href="../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md"> 拡張ディメンション</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> パラメーター </td> 
   <td colname="col2"> （オプション）。他の設定パラメーターから参照可能な変数。詳しくは、 <a href="../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> データセットインクルードファイルでのパラメーターの定義</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Reprocess </td> 
   <td colname="col2"> <p>（オプション）。ここには任意の文字またはその組み合わせを入力できます。このパラメーターに変更を加えてファイルを保存すると、データの再変換が開始されます。 </p> <p> データの再処理について詳しくは、 <a href="../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> 再処理と再変換</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Stage </td> 
   <td colname="col2"> <p>（オプション）。この<span class="wintitle">変換データセットインクルード</span>ファイルに適用する処理ステージの名前。処理ステージは、<span class="filepath">Transformation.cfg</span> ファイルの Stages パラメーターで定義します。 </p> <p> <p>注意：Stage を指定するときは、ステージ名が、データセットプロファイルの <span class="filepath">Transformation.cfg</span> ファイルの Stages パラメーターに指定されている名前と完全に一致している必要があります。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Transformations </td> 
   <td colname="col2"> （オプション）。変換中に適用するデータ変換を定義します。利用可能な変換のタイプについて詳しくは、 <a href="../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> データ変換</a>. </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>を参照してください。 [!DNL Transformation.cfg] ファイル： [変換設定ファイル](../../../../home/c-dataset-const-proc/c-trans-config-file/c-abt-trans-config-file.md).

を使用する際は、次の点に注意してください。 [!DNL Transformation Dataset Include] ファイル：

* このファイルに含まれるいずれかのパラメーターを変更した場合、データの再変換が必要となります。
* [!DNL CrossRows], [!DNL ODBCLookup], [!DNL Sessionize]、および [!DNL AppendURI] 変換は、 [!DNL Transformation Dataset Configuration] ファイル。 これらの変換について詳しくは、 [データ変換](../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

* 前述のパラメーターはいずれも [!DNL Transformation Dataset Include] ファイルをメモ帳で開いて編集することによって追加することができます。編集後、保存した内容は、Data Workbench でファイルを開き直すと表示されます。新しいパラメーターを追加する際は、（Tab キーではなく）スペースキーで空白を 2 つ追加し、前の見出しレベルの右にインデントします。

アドビの [!DNL IP Geo-location] または [!DNL IP Geo-intelligence]   データサービスに登録した場合、これらのデータサービスに特化して作成された一連のデータ変換と拡張ディメンションから成る内部プロファイルがアドビから提供されます。変換とディメンションは、 [!DNL Transformation Dataset Include] 内部プロファイルの Dataset ディレクトリに含まれるファイル。 [!DNL IP Geo-location] データサービス用または [!DNL IP Geo-intelligence] データサービス用の内部プロファイルをインストールする手順については、『*Data Workbench ユーザーガイド*』を参照してください。
