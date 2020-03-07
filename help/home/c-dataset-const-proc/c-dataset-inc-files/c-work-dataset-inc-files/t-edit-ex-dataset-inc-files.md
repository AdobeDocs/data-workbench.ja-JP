---
description: 既存のデータセットインクルードファイルを編集するための手順について説明します。
solution: Analytics
title: 既存のデータセットインクルードファイルの編集
topic: Data workbench
uuid: fcce2e46-b4a8-4c53-83bb-32ab410eb89e
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 既存のデータセットインクルードファイルの編集{#editing-existing-dataset-include-files}

既存のデータセットインクルードファイルを編集するための手順について説明します。

You open an existing dataset include file using the [!DNL Profile Manager] in data workbench.

For information about opening and working with the [!DNL Profile Manager], see the *Data Workbench User Guide*.

1. While working in your dataset profile, open the [!DNL Profile Manager] and click **[!UICONTROL Dataset]** to show the contents of the directory.

   * To open a [!DNL Log Processing Dataset Include] file, click **[!UICONTROL Log Processing]** to show the contents of the directory.

   * To open a [!DNL Transformation Dataset Include] file, click **[!UICONTROL Transformation]** to show the contents of the directory.

1. Right-click the check mark next to the desired dataset include file and click **[!UICONTROL Make Local]**. このファイル用のチェックマークが [!DNL User] 列に表示されます。
1. 新しく作成されたチェックマークを右クリックし、/をクリ **[!UICONTROL Open]** ックしま **[!UICONTROL from the workbench]**&#x200B;す。 設定ウィンドウが表示されます。

   You can also open a dataset include file from a [!DNL Transformation Dependency Maps]. 詳しくは、再処理と再 [!DNL Transformation Dependency Maps]変換を [参照してください](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md)。

1. 設定ファイルのパラメーターを必要に応じて編集します。パラメー [ターの説明については、](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab) Log Processing Dataset Include Files [（ログ処理データセットインクルードファイル）または](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace) Transformation Dataset Include Files（変換データセットインクルードファイル）を参照してください。

   Data Workbench ウィンドウ内でデータセットインクルードファイルを編集するときは、基本的な編集機能にショートカットキーを使用できます。切り取り（Ctrl + X）、コピー（Ctrl + C）、貼り付け（Ctrl + V）、取り消し（Ctrl + Z）、やり直し（Ctrl + Shift + Z）、セクション選択（クリックしながらドラッグ）、すべて選択（Ctrl + A）などの操作が可能です。In addition, you can use the shortcuts to copy and paste text from one configuration file ( [!DNL .cfg]) to another.

1. To save your changes, right-click **[!UICONTROL (modified)]** at the top of the window and click **[!UICONTROL Save]**.
1. To make the locally made changes take effect, in the [!DNL Profile Manager], right-click the check mark for the file in the [!DNL User] column, then click **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, where profile name is the name of the dataset profile or the inherited profile to which the dataset include file belongs. データセットプロファイルの同期後、データの再処理または再変換が開始されます。

   >[!NOTE]
   >
   >アドビから提供される内部プロファイルには、変更した設定ファイルを一切保存しないでください。内部プロファイルに対するアップデートをインストールするときに変更内容が上書きされます。

