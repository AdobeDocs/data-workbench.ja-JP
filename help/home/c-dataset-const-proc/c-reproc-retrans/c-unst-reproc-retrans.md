---
description: Data Workbench サーバーは再処理中、ログ処理と変換のデータセット設定ファイルに指定された内容に従ってデータセットを再構築します。
solution: Analytics
title: 再処理と再変換について
topic: Data workbench
uuid: 0253bc8c-8883-41eb-8a9f-e0685613ff5c
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 再処理と再変換について{#understanding-reprocessing-and-retransformation}

Data Workbench サーバーは再処理中、ログ処理と変換のデータセット設定ファイルに指定された内容に従ってデータセットを再構築します。

そのためには、Data Workbench サーバー（InsightServer64.exe）が、データセット構築のログ処理段階と変換段階の両方を完了する必要があります。変換は、ログ処理の完了をきっかけとして自動的に開始されますが、ログ処理とは切り離して実行することもできます。

ログ処理の最中に、Data Workbench のユーザーがデータセット内のデータにアクセスすることはできません。変換段階では最新のデータにアクセスできますが、データはサンプリングされたものであって、完全なものではありません。変換中もデータ分析を続行できますが、進行している変換の範囲でしかクエリーは実行されません。

## 再処理 {#section-92f1e46bf1534b3dba39e9493190b8ab}

次のいずれかの作業を実行するたびに、ログ処理とそれに伴う変換が自動的に実行され、データセット設定ファイル内の指定に従ってデータセットが再構築されます。

* 新しいデータソースを追加する。
* [!DNL Profile.cfg] ファイルで新しい Data Workbench サーバーをクラスターに追加する。
* Change the [!DNL Cluster.cfg] file.
* 次を含むフ [!DNL Log Processing.cfg] ァイルまた [!DNL Log Processing Dataset Include] はファイルを変更します（ただし、これに限りません）。

   * 新しいパラメーターの追加
   * 変換の変更
   * Start Time パラメーターまたは End Time パラメーターの変更

* Upgrade your [!DNL Insight Server.exe] file.

これ以外にも、[!DNL Log Processing.cfg] ファイルの Reprocess パラメーターに任意の文字またはその組み合わせを入力し、ファイルを保存することで再処理はいつでも開始できます。

>[!NOTE]
>
>For reprocessing to occur, the Pause parameter in the [!DNL Log Processing Mode.cfg] file must be set to false. このパラメーターの値はデフォルトで false になっているので、通常、変更は不要です。詳しくは、「追加の設定フ [!DNL Log Processing Mode.cfg]ァイル」 [を参照してください](/help/home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md)。

## 再変換 {#section-02446744549940ada8eba0573ec5575f}

Each time you change any information in the [!DNL Transformation.cfg] file or in a [!DNL Transformation Dataset Include] file, such as change a transformation or define a new dimension, transformation occurs automatically.

Each time you change lookup files that are referenced in the [!DNL Transformation.cfg] file or in a [!DNL Transformation Dataset Include] file (including lookup files for [!DNL Categorize], [!DNL FlatFileLookup], and [!DNL ODBCLookup] transformations), you must initiate transformation by entering any character or combination of characters in the Reprocess parameter of the [!DNL Transformation.cfg] file and saving the file.
