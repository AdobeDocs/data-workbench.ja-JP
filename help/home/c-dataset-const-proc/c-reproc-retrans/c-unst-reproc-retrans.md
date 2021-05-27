---
description: Data Workbench サーバーは再処理中、ログ処理と変換のデータセット設定ファイルに指定された内容に従ってデータセットを再構築します。
title: 再処理と再変換について
uuid: 0253bc8c-8883-41eb-8a9f-e0685613ff5c
exl-id: 12c69935-a981-492c-9124-71f6f06ff77b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 69%

---

# 再処理と再変換について{#understanding-reprocessing-and-retransformation}

Data Workbench サーバーは再処理中、ログ処理と変換のデータセット設定ファイルに指定された内容に従ってデータセットを再構築します。

そのためには、Data Workbench サーバー（InsightServer64.exe）が、データセット構築のログ処理段階と変換段階の両方を完了する必要があります。変換は、ログ処理の完了をきっかけとして自動的に開始されますが、ログ処理とは切り離して実行することもできます。

ログ処理の最中に、Data Workbench のユーザーがデータセット内のデータにアクセスすることはできません。変換段階では最新のデータにアクセスできますが、データはサンプリングされたものであって、完全なものではありません。変換中もデータ分析を続行できますが、進行している変換の範囲でしかクエリーは実行されません。

## 再処理 {#section-92f1e46bf1534b3dba39e9493190b8ab}

次のいずれかの作業を実行するたびに、ログ処理とそれに伴う変換が自動的に実行され、データセット設定ファイル内の指定に従ってデータセットが再構築されます。

* 新しいデータソースを追加する。
* [!DNL Profile.cfg] ファイルで新しい Data Workbench サーバーをクラスターに追加する。
* [!DNL Cluster.cfg]ファイルを変更します。
* [!DNL Log Processing.cfg]ファイルまたは[!DNL Log Processing Dataset Include]ファイルを変更します（以下を含みますが、これらに限定されません）。

   * 新しいパラメーターの追加
   * 変換の変更
   * Start Time パラメーターまたは End Time パラメーターの変更

* [!DNL Insight Server.exe]ファイルをアップグレードします。

これ以外にも、[!DNL Log Processing.cfg] ファイルの Reprocess パラメーターに任意の文字またはその組み合わせを入力し、ファイルを保存することで再処理はいつでも開始できます。

>[!NOTE]
>
>再処理を行うには、[!DNL Log Processing Mode.cfg]ファイルのPauseパラメーターをfalseに設定する必要があります。 このパラメーターの値はデフォルトで false になっているので、通常、変更は不要です。[!DNL Log Processing Mode.cfg]について詳しくは、[追加の設定ファイル](/help/home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md)を参照してください。

## 再変換 {#section-02446744549940ada8eba0573ec5575f}

[!DNL Transformation.cfg]ファイル内または[!DNL Transformation Dataset Include]ファイル内の情報（変換の変更や新しいディメンションの定義など）を変更するたびに、変換が自動的に実行されます。

[!DNL Transformation.cfg]ファイル内または[!DNL Transformation Dataset Include]ファイル内で参照されているルックアップファイル（[!DNL Categorize]、[!DNL FlatFileLookup]、[!DNL ODBCLookup]変換のルックアップファイルを含む）を変更するたびに、[!DNL Transformation.cfg]ファイルのReprocessパラメーターに任意の文字または組み合わせを入力し、ファイルを保存します。
