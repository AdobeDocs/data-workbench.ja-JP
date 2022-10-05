---
description: Data Workbench サーバーは再処理中、ログ処理と変換のデータセット設定ファイルに指定された内容に従ってデータセットを再構築します。
title: 再処理と再変換について
uuid: 0253bc8c-8883-41eb-8a9f-e0685613ff5c
exl-id: 12c69935-a981-492c-9124-71f6f06ff77b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 69%

---

# 再処理と再変換について{#understanding-reprocessing-and-retransformation}

{{eol}}

Data Workbench サーバーは再処理中、ログ処理と変換のデータセット設定ファイルに指定された内容に従ってデータセットを再構築します。

そのためには、Data Workbench サーバー（InsightServer64.exe）が、データセット構築のログ処理段階と変換段階の両方を完了する必要があります。変換は、ログ処理の完了をきっかけとして自動的に開始されますが、ログ処理とは切り離して実行することもできます。

ログ処理の最中に、Data Workbench のユーザーがデータセット内のデータにアクセスすることはできません。変換段階では最新のデータにアクセスできますが、データはサンプリングされたものであって、完全なものではありません。変換中もデータ分析を続行できますが、進行している変換の範囲でしかクエリーは実行されません。

## 再処理 {#section-92f1e46bf1534b3dba39e9493190b8ab}

次のいずれかの作業を実行するたびに、ログ処理とそれに伴う変換が自動的に実行され、データセット設定ファイル内の指定に従ってデータセットが再構築されます。

* 新しいデータソースを追加する。
* [!DNL Profile.cfg] ファイルで新しい Data Workbench サーバーをクラスターに追加する。
* を [!DNL Cluster.cfg] ファイル。
* を [!DNL Log Processing.cfg] ファイルまたは [!DNL Log Processing Dataset Include] ファイルに含まれます（以下に限りません）。

   * 新しいパラメーターの追加
   * 変換の変更
   * Start Time パラメーターまたは End Time パラメーターの変更

* のアップグレード [!DNL Insight Server.exe] ファイル。

これ以外にも、[!DNL Log Processing.cfg] ファイルの Reprocess パラメーターに任意の文字またはその組み合わせを入力し、ファイルを保存することで再処理はいつでも開始できます。

>[!NOTE]
>
>再処理を実行する場合は、 [!DNL Log Processing Mode.cfg] ファイルを false に設定する必要があります。 このパラメーターの値はデフォルトで false になっているので、通常、変更は不要です。詳しくは、 [!DNL Log Processing Mode.cfg]を参照してください。 [追加の設定ファイル](/help/home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md).

## 再変換 {#section-02446744549940ada8eba0573ec5575f}

情報を [!DNL Transformation.cfg] ファイル内または [!DNL Transformation Dataset Include] ファイルの変換は、変換の変更や新しいディメンションの定義など、自動的に行われます。

参照元の参照ファイルを [!DNL Transformation.cfg] ファイル内または [!DNL Transformation Dataset Include] ファイル（参照ファイルを含む） [!DNL Categorize], [!DNL FlatFileLookup]、および [!DNL ODBCLookup] 変換を参照 )、変換を開始するには、 [!DNL Transformation.cfg] ファイルを作成し、ファイルを保存します。
