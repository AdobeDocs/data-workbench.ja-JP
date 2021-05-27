---
description: 設定ファイルを編集することで、データセットの構築ルールを変更できます。
title: データセット設定について
uuid: 813933d1-f52d-4584-8edd-ce9cd4aed74a
exl-id: 1358d08e-d81c-453d-a3a3-c1f279f38192
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '916'
ht-degree: 84%

---

# データセット設定について{#understanding-dataset-configuration}

設定ファイルを編集することで、データセットの構築ルールを変更できます。

構築されたデータセットの物理的な格納場所は Data Workbench サーバーコンピューター上の [!DNL temp.db] ファイルですが、そのデータセットの設定ファイルは、プロファイルのディレクトリ内に存在します。プロファイルには、特定の分析を目的としたデータセット（拡張ディメンションを含む）の構築に使用される一連の設定ファイルが含まれています。加えて、指標、派生ディメンション、ワークスペース、レポート、ビジュアライゼーションなど、アナリストがデータセットを対話的に操作して情報を得るためのエンティティの定義もプロファイルに含まれています。

ユーザーが編集することになるデータセット設定ファイルの従属先プロファイルを「データセットプロファイル」と呼びます。データセットプロファイルは、様々な継承プロファイルを参照します。分析のニーズに応じてアドビのアプリケーションを設定するために自分が作成、保守しているあらゆるプロファイルを参照することが可能です。アプリケーションに付属している（アプリケーションに備わっている様々な機能の前提となる）内部プロファイルをデータセットプロファイルから参照することもできます。

各種プロファイルについて詳しくは、『*Data Workbench ユーザーガイド*』を参照してください。

<!--
c_req_config_files.xml
-->

データセットプロファイルは、Insight サーバーコンピューター上の以下の設定ファイルを必要とします。

* **Profile.cfg：**&#x200B;継承プロファイルと、そのプロファイルの処理サーバーをリストします。処理サーバーは、プロファイルのデータを処理する Insight サーバーの DPU です。Insight サーバークラスターをインストール済みである場合は、単一のプロファイルを実行する Insight サーバーコンピューターを複数指定できます。

   データセットプロファイルの [!DNL Profile.cfg] ファイルに継承プロファイルを追加する手順については、『*サーバー製品のインストールと管理に関するガイド*』を参照してください。Insight サーバークラスターのインストール方法と Insight サーバークラスター上で実行するデータセットプロファイルの設定方法について詳しくは、『*サーバー製品のインストールと管理に関するガイド*』を参照してください。

* **Dataset\Log Processing.cfg：**&#x200B;データセット構築プロセスのログ処理段階を制御します。[ログ処理](../../home/c-dataset-const-proc/c-dataset-constr.md#concept-8a63892878004dc389c7dad784fcb061)を参照してください。 [!DNL Log Processing.cfg]ファイルについて詳しくは、[ログ処理設定ファイル](../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md)を参照してください。

* **Dataset\Transformation.cfg：**&#x200B;データセット構築プロセスの変換段階を制御します。[変換](../../home/c-dataset-const-proc/c-dataset-constr.md#concept-88f72e0897a744b5bc03df5039264dda)を参照してください。 プロファイル固有の分析に使用するデータセットは通常、[!DNL Transformation.cfg] ファイルで設定します。[!DNL Transformation.cfg]ファイルについて詳しくは、[変換設定ファイル](../../home/c-dataset-const-proc/c-trans-config-file/c-abt-trans-config-file.md)を参照してください。

* **データセットインクルードファイル：** ファイ [!DNL dataset include] ルには、データセットプロファイルのまたはファイルに含まれるパラメーターのサブセットが含まれま [!DNL Log Processing.cfg] す [!DNL Transformation.cfg] が、継承されたプロファイル内で保存および管理されます。[!DNL Dataset include] ファイルは、メインのデータセット設定ファイルを補完します。詳しくは、[データセットインクルードファイル](../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)を参照してください。

Adobeアプリケーションの実装時に提供されるデータセットプロファイルには、[!DNL Profile Manager]を使用して開いたり、編集したり、保存したりできるデータセット設定ファイルが含まれています。

[!DNL Profile Manager]について詳しくは、『*Insightユーザーガイド*』を参照してください。

<!--
c_addl_config_files.xml
-->

これらは必須ではありませんが、これらのファイルを使用することで、より細かくデータセット構築プロセスを制御することができます。

* **：**[!DNL Log Processing Mode.cfg]データセットに組み入れるデータの処理を一時停止したり、オフラインソースを指定したりすることができます。Data Workbench サーバーの状態ファイルが保存される頻度を指定することもできます。[追加の設定ファイル](../../home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md#concept-1afef4f88f1e467ab4326875fd1d3004)を参照してください。

* **：**[!DNL Server.cfg]Data Workbench サーバーに接続する Data Workbench コンピューターのデフォルトのデータキャッシュサイズ（バイト単位）を指定します。[追加の設定ファイル](../../home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md#concept-1afef4f88f1e467ab4326875fd1d3004)を参照してください。

* **Transform.cfg と Transform Mode.cfg：**&#x200B;データ変換機能を使用するためのライセンスを持っている場合にのみ、これらのファイルを利用できます。[!DNL Transform.cfg] ファイルには、変換機能で使用されるデータ変換とログのソースを定義するパラメーターが含まれています。そこで定義した変換によってソースデータが加工され、指定した形式で出力されます。[!DNL Insight Transform Mode.cfg] ファイルでは、データセットに組み入れるデータの処理を一時停止したり、オフラインソースを指定したりすることができます。変換機能を実行する Insight サーバーの状態ファイルが保存される頻度を指定することもできます。[変換機能](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/transform/t-config-tfm.html)を参照してください。

<!--
c_next_steps.xml
-->

具体的なデータセット設定作業については、次の表で目的に合った節を参照してください。

<table id="table_394CFB5135274545B5DA37952EC6943E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 目的 </th> 
   <th colname="col2" class="entry"> ... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ログソースを定義する </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> ログソース </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ログ処理時にデータセットに含めるログエントリを決める </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> データフィルター</a> </p> <p> <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> ログ記録条件</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>大量のイベントデータを伴った追跡 ID の分割を有効にする </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> キー分割</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ファイルサーバーユニットとして実行するように Insight サーバーを設定する </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Insightサーバーのファイルサーバーユニットの設定  </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>中央の正規化サーバーとして実行するように Insight サーバーを設定する </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Insightサーバーのファイルサーバーユニットの設定  </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>時間ディメンションの作成と時刻の変換に使用するタイムゾーンを設定する </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956"> タイムゾーン </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>アドビから提供される内部プロファイルに付属のデータセット設定ファイルに小さな変更を加える </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077"> 既存のデータセットインクルードファイルの編集 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ログ処理から変換に渡すデータに対し新しいフィールドを指定する </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e"> 新しいデータセットインクルードファイルの作成 </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab"> ログ処理データセットインクルードファイル </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>変換を定義する </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> データ変換 </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e"> 新しいデータセットインクルードファイルの作成 </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> 変換データセットインクルードファイル </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>拡張ディメンションを作成する </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md"> 拡張ディメンション </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e"> 新しいデータセットインクルードファイルの作成 </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> 変換データセットインクルードファイル </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ログ処理全体または変換全体で使用するパラメーターを定義する </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> データセットインクルードファイルでのパラメーターの定義 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>データセットを監視し管理する </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-config-int.md#concept-0ea33a52ce234ec8951e7b4430fbc5ab"> データセット設定インターフェイスの操作 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>特定の拡張ディメンションが Insight のディメンションメニューに表示されないようにする </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-dataset-comp.md#concept-50d9a004736f42f6b0aa7cde0d6148ff"> データセットのコンポーネントの非表示 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>変更できない（または変更したくない）データセット設定ファイルがプロファイルに存在する場合にそのファイルを無効にする </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-dataset-comp.md#concept-50d9a004736f42f6b0aa7cde0d6148ff"> データセットのコンポーネントの非表示 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>データセットを再処理する </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> 再処理と再変換 </a> </p> </td> 
  </tr> 
 </tbody> 
</table>
