---
description: 継承プロファイルの変換データセットインクルードファイルには、データセット構築の変換段階に関連したパラメーターが含まれます。
solution: Analytics
title: 変換データセットインクルードファイル
topic: Data workbench
uuid: 46756f68-843c-4b0d-a79e-f107ef85db6c
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 変換データセットインクルードファイル{#transformation-dataset-include-files}

継承プロファイルの変換データセットインクルードファイルには、データセット構築の変換段階に関連したパラメーターが含まれます。

ファイルの先頭行には、Extended Dimensions、Parameters、Reprocess、Stage、Transformations の各パラメーターをすべてサポートする [!DNL TransformationInclude] 型が定義されます。その他のパラメーターはすべて、データセットプロファイルの Dataset ディレクトリにある [!DNL Transformation.cfg] ファイルの中で定義する必要があります。

Including parameters other than Extended Dimensions, Parameters, Reprocess, Stage, and Transformations in a [!DNL Transformation Dataset Include] file generates errors.

You can name a [!DNL Transformation Dataset Include] file anything you want, but its file extension must be [!DNL .cfg]. ファイルは、*inherited profile name*\Dataset\Transformation ディレクトリ内に格納されていることが必要です。Because the files are loaded recursively during the transformation phase of dataset construction, you can store the [!DNL Transformation Dataset Include] files at any level within the directory (for example, *inherited profile name*\Dataset\Transformation\*folder name*\*include file name*.cfg).

>[!NOTE]
>
>Siteの多くのWeb固有の設定パラメーターは、ファイル内で定義さ [!DNL Transformation Dataset Include] れます。 これらのパラメーターについて詳しくは、Webデ [ータの設定を参照してください](../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519)。

The following table describes the parameters that are available in a [!DNL Transformation Dataset Include] file:

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
   <td colname="col2"> (オプション)拡張ディメンションを定義します。詳しくは、 <a href="../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md"> 拡張ディメンション</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> パラメーター </td> 
   <td colname="col2"> (オプション)他の設定パラメーターから参照可能な変数。詳しくは、 <a href="../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> データセットインクルードファイルでのパラメーターの定義</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Reprocess </td> 
   <td colname="col2"> <p>(オプション)ここには任意の文字またはその組み合わせを入力できます。このパラメーターに変更を加えてファイルを保存すると、データの再変換が開始されます。 </p> <p> データの再処理について詳しくは、<a href="../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md">再処理と再変換</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Stage </td> 
   <td colname="col2"> <p>(オプション)この<span class="wintitle">変換データセットインクルード</span>ファイルに適用する処理ステージの名前。処理ステージは、<span class="filepath">Transformation.cfg</span> ファイルの Stages パラメーターで定義します。 </p> <p> <p>注意：Stage を指定するときは、ステージ名が、データセットプロファイルの <span class="filepath">Transformation.cfg</span> ファイルの Stages パラメーターに指定されている名前と完全に一致している必要があります。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Transformations </td> 
   <td colname="col2"> (オプション)変換中に適用するデータ変換を定義します。利用可能な変換のタイプについて詳しくは、<a href="../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md">データ変換</a>を参照してください。 </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>ファイル内のパラメーターの説明については、 [!DNL Transformation.cfg] 変換設定ファイルを [参照してください](../../../../home/c-dataset-const-proc/c-trans-config-file/c-abt-trans-config-file.md)。

You should keep the following points in mind whenever you are working with [!DNL Transformation Dataset Include] files:

* このファイルに含まれるいずれかのパラメーターを変更した場合、データの再変換が必要となります。
* [!DNL CrossRows]、、、 [!DNL ODBCLookup]お [!DNL Sessionize]よび変 [!DNL AppendURI] 換は、ファイル内で定義されている場合にのみ機能 [!DNL Transformation Dataset Configuration] します。 これらの変換について詳しくは、データ変換を参 [照してください](../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md)。

* 前述のパラメーターはいずれも [!DNL Transformation Dataset Include] ファイルをメモ帳で開いて編集することによって追加することができます。編集後、保存した内容は、Data Workbench でファイルを開き直すと表示されます。新しいパラメーターを追加する際は、（Tab キーではなく）スペースキーで空白を 2 つ追加し、前の見出しレベルの右にインデントします。

アドビの [!DNL IP Geo-location] または [!DNL IP Geo-intelligence]   データサービスに登録した場合、これらのデータサービスに特化して作成された一連のデータ変換と拡張ディメンションから成る内部プロファイルがアドビから提供されます。The transformations and dimensions are defined in [!DNL Transformation Dataset Include] files that are included in the Dataset directory of the internal profile. [!DNL IP Geo-location] データサービス用または [!DNL IP Geo-intelligence] データサービス用の内部プロファイルをインストールする手順については、『*Data Workbench ユーザーガイド*』を参照してください。
