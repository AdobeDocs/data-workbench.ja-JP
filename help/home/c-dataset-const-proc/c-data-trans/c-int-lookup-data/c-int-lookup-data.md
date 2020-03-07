---
description: Data Workbench サーバーは、Data Workbench に備わっているいくつかの変換によって、ルックアップデータをデータセットに組み入れることができます。
solution: Analytics
title: ルックアップデータの統合
topic: Data workbench
uuid: 35fd48f7-c0c4-4a83-919d-c15902f27495
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ルックアップデータの統合{#integrating-lookup-data}

Data Workbench サーバーは、Data Workbench に備わっているいくつかの変換によって、ルックアップデータをデータセットに組み入れることができます。

ルックアップデータは、社内のデータベースやルックアップファイルから取り込まれる外部データです。この外部データをイベントデータと統合してデータセットを作成できます。一般に、ルックアップデータは、ログソースから得られるイベントデータを補足する目的に使用します。概念上、ルックアップデータの使用は、イベントデータレコードに、さらに別の列の情報を追加すること、と考えることができます。

ルックアップデータを使用する際は、メモリ常駐型のルックアップテーブルにデータを読み込みます。このテーブル内の列には、イベントデータレコードにも存在する共通のキーが含まれている必要があります。ルックアップテーブルそのもののデータは、フラットファイルや ODBC データソースから読み込むことができます。ルックアップデータは、データセット構築プロセスのログ処理段階または変換段階でデータセットに組み入れることができます。

ルックアップデータを組み入れるにはまず、ルックアップファイルを作成するか、SQL データベースにアクセスするために必要な情報を用意したうえで、ログ処理や変換に使用するデータセット設定ファイルに、以下に示した変換を定義する必要があります。

**ルックアップデータをデータセットに統合するには**

1. ルックアップファイルを作成します。詳しくは、 [ルックアップテーブルへのデータ投入](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-pop-lookup-table.md#concept-dd761338731a40e0997c33dfdabdcdf8).
1. 適切なデータセット設定ファイルの Transformations パラメーターに、次のいずれかのタイプの変換を定義します。

   * [!DNL Categorize]
   * [!DNL FlatFileLookup]
   * [!DNL ODBCLookup]

>[!NOTE]
>
>変換は、ファ [!DNL ODBCLookup] イルまたはファイルで定義されてい [!DNL Transformation.cfg] る場合にのみ機能し [!DNL Transformation Dataset Include] ます。
