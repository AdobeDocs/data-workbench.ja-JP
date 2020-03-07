---
description: データセット構築のログ処理段階または変換段階で適用される変換は独自に定義することができます。
solution: Analytics
title: 変換の定義
topic: Data workbench
uuid: 69dd667b-e465-4c1a-a20e-4384e8988cd0
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 変換の定義{#defining-a-transformation}

データセット構築のログ処理段階または変換段階で適用される変換は独自に定義することができます。

>[!NOTE]
>
>変換は、またはではなく、ま [!DNL Log Processing] たはフ [!DNL Transformation Dataset Include] ァイルで定義することをお勧 [!DNL Log Processing.cfg] めしま [!DNL Transformation.cfg]す。

The following transformations work only when defined in the [!DNL Transformation.cfg] file or in a [!DNL Transformation Dataset Include] file:

* [AppendURI](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-uri-transf/c-appenduri.md#concept-a0df05dd958645bf8219fc7b0b675ee4)
* [CrossRows](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-crossrows.md#concept-fcace08804f54db397ed631cc13ff4f2)
* [LookupRows](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-lookuprows.md#concept-4bd9a1f13ee243e592a6a0008053134f)
* [ODBC データソース](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3)
* [Sessionize](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-sessionize.md#concept-b1af95c8cba34b248f86de883d914bc0)

**変換を定義するには**

1. Use the [!DNL Profile Manager] to open the dataset configuration file in which you want to define the transformation.

   * （推奨）データセットインクルードファイルを開く方法については、「データセットインクルードフ [ァイル」を参照してくださ](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)い。
   * ファイルを開くに [!DNL Log Processing.cfg] は、「ログ処 [理設定ファイルの編集」を参照してください](../../../home/c-dataset-const-proc/c-log-proc-config-file/t-edit-log-proc-config-file.md#task-6a2fa1b735cb4eefad730f0a3a7858e5)。

   * ファイルを開くに [!DNL Transformation.cfg] は、「変換設 [定ファイルの編集」を参照してください](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc)。

1. 右クリックし **[!UICONTROL Transformations]**、「>」を **[!UICONTROL Add new]** クリッ *クし&#x200B;**[!UICONTROL Transformation type]**ます*。
1. 目的とする変換に必要な情報を入力します。変換のタイプとそのパラメーターに関する情報については、次の節を参照してください。

   * [標準変換](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-standard-transf.md#concept-25f4bdbf8fe74c4aaeb2fcd226243886)
   * [URI 変換](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-uri-transf/c-uri-transf.md#concept-2dfa0ffcd83d4fb69c1f42ad50dea125)
   * [ルックアップデータの統合](../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-int-lookup-data.md#concept-08ff70769a464f50ab14299a344f05c7)

1. 設定ファイルに変換を定義した後、そのファイルをローカルに保存してから、Data Workbench サーバー上のデータセットプロファイルに保存します。

       変換を定義したり編集したりするうえでのヒント：
   
   * Data Workbench ウィンドウ内で変換の設定を編集するときは、基本的な編集機能にショートカットキーを使用できます。切り取り（Ctrl + X）、コピー（Ctrl + C）、貼り付け（Ctrl + V）、取り消し（Ctrl + Z）、やり直し（Ctrl + Shift + Z）、セクション選択（クリックしながらドラッグ）、すべて選択（Ctrl + A）などの操作が可能です。In addition, you can use the shortcuts to copy and paste text or entire transformation definitions from one configuration file ( [!DNL .cfg]) to another.
   * 独自に定義した変換には、その変換に関する詳しい情報や使用上の注意点をコメント行として Comments パラメーターに追加することができます。To add a comment using data workbench, right-click the **[!UICONTROL Comments]** label, then click **[!UICONTROL Add new]** > **[!UICONTROL Comment Line]**.

   * You can open the configuration of any transformation from a [!DNL Transformation Dependency Map]. 開いた設定を編集し、変更内容を保存することが可能です。詳しくは、データセッ [!DNL Transformation Dependency Maps]ト設定ツー [ルを参照してください](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5)。

   * 変換によって出力された空の文字列によって、出力フィールド内の、空ではない文字列が上書きされることがあります。

