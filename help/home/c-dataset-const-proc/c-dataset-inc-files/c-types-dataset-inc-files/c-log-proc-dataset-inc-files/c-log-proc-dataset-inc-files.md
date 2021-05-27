---
description: 継承プロファイルのログ処理データセットインクルードファイルには、データセット構築のログ処理段階に関連したパラメーターが含まれます。
title: ログ処理データセットインクルードファイル
uuid: 8bf99c9a-f674-4a07-bb3e-de0d9efc9716
exl-id: 06d8046d-6bac-4ccd-bcef-06f7c9ec7619
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '660'
ht-degree: 76%

---

# ログ処理データセットインクルードファイル{#log-processing-dataset-include-files}

継承プロファイルのログ処理データセットインクルードファイルには、データセット構築のログ処理段階に関連したパラメーターが含まれます。

[!DNL Log Processing Dataset Include]ファイルの最初の行では、Decoder Groups、Fields、Log Entry Condition、Parameters、Reprocess、Stage、Transformationsの各パラメーターをサポートするタイプ[!DNL LogProcessingInclude]を定義します。 その他ログ処理に必要なパラメーターはすべて、データセットプロファイルの Dataset ディレクトリにある [!DNL Log Processing.cfg] ファイルの中で定義する必要があります。[!DNL Log Processing Dataset Include]ファイルには任意の名前を付けることができますが、ファイルの拡張子は[!DNL .cfg]にする必要があります。 ファイルは、*inherited profile name*\Dataset\Log Processing ディレクトリ内に格納されていることが必要です。データセット構築のログ処理段階でファイルが再帰的に読み込まれるので、[!DNL Log Processing Dataset Include]ファイルはディレクトリ内の任意のレベルに保存できます(例：*inherited profile name*\Dataset\Log Processing\*folder name*\*include file name*.cfg)。

>[!NOTE]
>
>Site用のWeb固有の設定パラメーターの多くは、[!DNL Log Processing Dataset Include]ファイルで定義されます。 これらのパラメーターについて詳しくは、[Webデータの設定](../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519)を参照してください。

<table id="table_E2112652CCD443E889A529EEDC4ADF1C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> パラメーター </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Decoder Groups </td> 
   <td colname="col2"> <p><span class="filepath">Log Processing.cfg</span> ファイルの中でログファイルログソースまたは XML ファイルログソースを定義した場合は必須です。ログファイルや XML のログソースからデータフィールドを抽出する目的で定義するテキストファイルデコーダーまたは XML デコーダーを指定します。 </p> <p> <b>新しいデコーダーグループを追加するには</b> 
     <ul id="ul_54087499003C48C8B0AD9660A2F46EA9"> 
      <li id="li_E361861E61D246DDB3964C97CC5187E9"> <span class="uicontrol">Decoder Group</span> を右クリックし、<span class="uicontrol">新規追加</span>／<span class="uicontrol">TextFileDecoderGroup</span>（または <span class="uicontrol">XMLDecoderGroup</span>）をクリックします。 </li> 
      <li id="li_B2D61A0763AD4FEDB619BF9550EF4602"> 新しいグループの Name パラメーターに、目的のデコーダーグループの名前を入力します。 </li> 
     </ul> </p> <p> <p>注意：データセットプロファイルの <span class="filepath">Log Processing.cfg</span> ファイルで Decoder Group を指定するときは、その名前が、ここで入力する名前と完全に一致している必要があります。詳しくは、<a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e">ログファイル</a>を参照してください。 </p> </p> <p> 各グループに定義できるデコーダーについて詳しくは、 <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#concept-0db34988e17c41bfb1797f1d8e78aabd"> Text File Decoder Groups</a>または<a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3"> XML Decoder Groups</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> フィールド </td> 
   <td colname="col2"> <p><span class="wintitle">ログ処理データセット設定</span>ファイル内の <span class="wintitle">Log Sources</span> または <span class="wintitle">Transformations</span> に定義されているものの、<span class="wintitle">変換データセット設定</span>ファイル内の変換、条件、拡張ディメンションで使用する一連のフィールドはここに指定する必要があります。 </p> <p> 以下に示す各フィールドは、いずれかの<span class="wintitle">ログ処理データセットインクルード</span>ファイルで指定する必要があります。 
     <ul id="ul_D1BB18A80D874C0B9B54DA361698EB30"> 
      <li id="li_7E8B5B697BDA408DBE10D9A63AF295AC"> x-trackingid </li> 
      <li id="li_F5DEE90A596A4A1C86AF874653C4048C"> x-timestamp </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Log Entry Condition </td> 
   <td colname="col2"> <p>（オプション）データセットにログエントリを含めるかどうかの判断基準となるルールを定義します。詳しくは、 <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> ログ記録条件</a>. </p> <p> <p>注意：データセットに追加するログエントリは、<span class="wintitle">Log Processing.cfg</span> ファイル内およびすべての<span class="filepath">ログ処理データセットインクルード</span>ファイル内の <span class="wintitle">Log Entry Condition</span> を満たしている必要があります。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> パラメーター </td> 
   <td colname="col2"> （オプション）他の設定パラメーターから参照可能な変数。詳しくは、 <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> データセットインクルードファイルでのパラメーターの定義</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Reprocess </td> 
   <td colname="col2"> <p>（オプション）ここには任意の文字またはその組み合わせを入力できます。このパラメーターに変更を加えて Data Workbench サーバーにファイルを保存すると、データの再処理が開始されます。 </p> <p> データの再処理について詳しくは、 <a href="../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> 再処理と再変換</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Stage </td> 
   <td colname="col2"> <p>（オプション）この<span class="wintitle">ログ処理データセットインクルード</span>ファイルに適用する処理ステージの名前。処理ステージは、<span class="filepath">Log Processing.cfg</span> ファイルの Stages パラメーターで定義します。 </p> <p> <p>注意：Stage を指定するときは、ステージ名が、データセットプロファイルの <span class="filepath">Log Processing.cfg</span> ファイルの Stages パラメーターに指定されている名前と完全に一致している必要があります。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Transformations </td> 
   <td colname="col2"> （オプション）ログ処理中に適用するデータ変換を定義します。利用可能な変換のタイプについて詳しくは、 <a href="../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> データ変換</a>. </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>[!DNL Log Processing.cfg]ファイル内のパラメーターの説明については、[ログ処理設定ファイル](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md)を参照してください。

[!DNL Log Processing Dataset Include]ファイルを扱う際は、次の点に注意してください。

* このファイルに含まれるいずれかのパラメーターを変更した場合、全データの再処理が必要となります。
* 前述のパラメーターはいずれも [!DNL Log Processing Dataset Include] ファイルをメモ帳で開いて編集することによって追加することができます。編集後、保存した内容は、Data Workbench でファイルを開き直すと表示されます。新しいパラメーターを追加する際は、（Tab キーではなく）スペースキーで空白を 2 つ追加し、前の見出しレベルの右にインデントします。
