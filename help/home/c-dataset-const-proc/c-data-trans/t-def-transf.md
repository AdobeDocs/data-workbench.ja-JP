---
description: データセット構築のログ処理段階または変換段階で適用される変換は独自に定義することができます。
title: 変換の定義
uuid: 69dd667b-e465-4c1a-a20e-4384e8988cd0
exl-id: 61ce8093-9e64-419a-bddc-dc2225c0eaab
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 63%

---

# 変換の定義{#defining-a-transformation}

データセット構築のログ処理段階または変換段階で適用される変換は独自に定義することができます。

>[!NOTE]
>
>Adobeでは、変換を[!DNL Log Processing.cfg]または[!DNL Transformation.cfg]ではなく、[!DNL Log Processing]または[!DNL Transformation Dataset Include]ファイルに定義することをお勧めします。

次の変換は、[!DNL Transformation.cfg]ファイルまたは[!DNL Transformation Dataset Include]ファイルで定義されている場合にのみ機能します。

* [AppendURI](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-uri-transf/c-appenduri.md#concept-a0df05dd958645bf8219fc7b0b675ee4)
* [CrossRows](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-crossrows.md#concept-fcace08804f54db397ed631cc13ff4f2)
* [LookupRows](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-lookuprows.md#concept-4bd9a1f13ee243e592a6a0008053134f)
* [ODBC データソース](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3)
* [Sessionize](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-sessionize.md#concept-b1af95c8cba34b248f86de883d914bc0)

**変換を定義するには**

1. [!DNL Profile Manager]を使用して、変換を定義するデータセット設定ファイルを開きます。

   * （推奨）データセットインクルードファイルを開く場合は、[データセットインクルードファイル](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)を参照してください。
   * [!DNL Log Processing.cfg]ファイルを開く方法については、[ログ処理設定ファイルの編集](../../../home/c-dataset-const-proc/c-log-proc-config-file/t-edit-log-proc-config-file.md#task-6a2fa1b735cb4eefad730f0a3a7858e5)を参照してください。

   * [!DNL Transformation.cfg]ファイルを開く方法については、[変換設定ファイルの編集](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc)を参照してください。

1. **[!UICONTROL Transformations]**&#x200B;を右クリックし、**[!UICONTROL Add new]**/*&lt;**[!UICONTROL Transformation type]**>*&#x200B;をクリックします。
1. 目的とする変換に必要な情報を入力します。変換のタイプとそのパラメーターに関する情報については、次の節を参照してください。

   * [標準変換](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-standard-transf.md#concept-25f4bdbf8fe74c4aaeb2fcd226243886)
   * [URI 変換](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-uri-transf/c-uri-transf.md#concept-2dfa0ffcd83d4fb69c1f42ad50dea125)
   * [ルックアップデータの統合](../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-int-lookup-data.md#concept-08ff70769a464f50ab14299a344f05c7)

1. 設定ファイルに変換を定義した後、そのファイルをローカルに保存してから、Data Workbench サーバー上のデータセットプロファイルに保存します。

       変換を定義したり編集したりするうえでのヒント：
   
   * Data Workbench ウィンドウ内で変換の設定を編集するときは、基本的な編集機能にショートカットキーを使用できます。切り取り（Ctrl + X）、コピー（Ctrl + C）、貼り付け（Ctrl + V）、取り消し（Ctrl + Z）、やり直し（Ctrl + Shift + Z）、セクション選択（クリックしながらドラッグ）、すべて選択（Ctrl + A）などの操作が可能です。また、設定ファイル([!DNL .cfg])間でテキストまたは変換定義全体をコピーして貼り付ける際にも、ショートカットキーを使用できます。
   * 独自に定義した変換には、その変換に関する詳しい情報や使用上の注意点をコメント行として Comments パラメーターに追加することができます。data workbenchを使用してコメントを追加するには、**[!UICONTROL Comments]**&#x200B;ラベルを右クリックし、**[!UICONTROL Add new]**/**[!UICONTROL Comment Line]**&#x200B;をクリックします。

   * [!DNL Transformation Dependency Map]から任意の変換の設定を開くことができます。 開いた設定を編集し、変更内容を保存することが可能です。[!DNL Transformation Dependency Maps]について詳しくは、[データセット設定ツール](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5)を参照してください。

   * 変換によって出力された空の文字列によって、出力フィールド内の、空ではない文字列が上書きされることがあります。
