---
description: ワークスペースファイルメニューで利用できるメニューオプションに関する情報です。
solution: Analytics
title: ワークスペースファイルメニュー
topic: Data workbench
uuid: abbdb2db-d918-4edf-977c-1daaf8a71721
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Workspace File menu{#workspace-file-menu}

ワークスペースファイルメニューで利用できるメニューオプションに関する情報です。

In the workspace, click **[!UICONTROL File]**.

![](assets/mnu_file.png)

次の表で、各メニュー項目について説明します。

**保存**

ワークスペースを保存します。詳しくは、「 [ワークスペースの保存](../../../home/c-get-started/c-work-worksp/c-save-wksp.md#concept-e0c34e75cc194e57bd02d1f02316a606).

**名前を付けてコピーを保存**

ワークスペースを別の名前で、または別の場所に保存します。詳しくは、「 [ワークスペースの保存](../../../home/c-get-started/c-work-worksp/c-save-wksp.md#concept-e0c34e75cc194e57bd02d1f02316a606).

**元に戻す**

現在のワークスペースを最後に保存したバージョンに戻します。

**ワークスペースを再適合**

使用している表示解像度にビジュアライゼーションのサイズを変更します。この機能は、ディスプレイをプレゼンテーションに合わせてすばやく調整するのに役立ちます。

**ページサイズ**

ワークスペースの作業ページサイズを設定します。「画面にフィット」、「標準」またはコンピューター画面、印刷ページおよびレポート用の特定のサイズを選択できます。「画面にフィット」を選択すると、ご使用の特定の画面にフィットします。「標準」は、お客様の会社の標準的な画面サイズに合わせることのできる設定です。デフォルトの「標準」設定では、1024 x 768 の解像度を使用する画面にフィットします。

Workspaces that are copied, saved as [!DNL .png] files, or printed also use this page size for output. Data Workbenchのビジュアライゼーションより大きいページサイズではスクロールバーを使用しますが、小さいサイズでは画面の中央に配置され、ワークスペースの周囲に薄いグレーの境界線が表示されます。

**説明**

ワークスペースのテキストの説明を作成したり編集したりできます。This text appears on the [!DNL Worktop] below the thumbnail. See [Adding a Description to a Workspace](../../../home/c-get-started/c-work-worksp/t-add-wksp-desc.md#task-163734487e8848dfa0a4d8da6323a963).

**バックグラウンドで計算**

（オンラインで作業している場合のみ表示されます）ユーザーが作業を続行している間、選択したワークスペースのクエリーがバックグラウンドで引き続き実行されます。選択すると、サムネールにクエリーの進行状況を示す次の情報が表示されます。

* 作業中 : *n%* - クエリーが処理中であることと、完了した処理の割合を示します。
* *n* MB クエリーの読み込み - クエリー結果の合計サイズ。クエリーの読み込みは、Data Workbenchサーバーの合計メモリ読み込み量に比例しますが、直接の相関はありません。 ガイドラインとして、10 MB 以上のクエリーの読み込みは、システムに過大な負担をかける場合があります。表示されるクエリーの読み込みでは、クラスタリングが考慮されていません。

>[!NOTE]
>
>「バックグラウンドで計算」を選択したままにすると、選択したワークスペース内のクエリーは常設クエリーとなり、更新が継続され、メモリ読み込みが使用されます。 ワークスペースでの作業を終了するときに、必ず「バックグラウンドで計算」の選択を解除してください。

**閉じる**

ワークスペースを閉じます。Click **[!UICONTROL Close]** > **[!UICONTROL Save]** to save the changes you have made in the workspace, or click **[!UICONTROL Close]** > **[!UICONTROL Don’t Save]** to return to the [!DNL Worktop] without saving the changes you have made in the workspace.

You also can save your changes, close the workspace, and return to the [!DNL Worktop] using any of the following methods:

* ワークスペースの左上隅にあるData Workbenchのロゴをクリックします。
* マウスにナビゲーションボタンがある場合、マウスの「戻る」ボタンをクリックします。

You also can void your changes by closing the workspace without saving by pressing **[!UICONTROL `<Ctrl>`+<Backspace>]**を参照してください。

**テンプレートからエクスポート**

If Microsoft Excel is installed on the Data Workbench machine, automatically starts Microsoft Excel and exports the data from certain visualizations, certain legends, and text annotations to the template Excel file ( [!DNL .xls]or [!DNL .xlsx]) that you select. 詳しくは、「[テンプレート Excel ファイルにエクスポートする](../../../home/c-get-started/c-work-worksp/c-ex-wksp.md#section-814772929ca64cf6b92b89d3fdd02302)」を参照してください。
