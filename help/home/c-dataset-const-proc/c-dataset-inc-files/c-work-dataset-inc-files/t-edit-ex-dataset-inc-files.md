---
description: 既存のデータセットインクルードファイルを編集するための手順について説明します。
title: 既存のデータセットインクルードファイルの編集
uuid: fcce2e46-b4a8-4c53-83bb-32ab410eb89e
exl-id: f4095871-d004-4e10-af18-bf6c1e47493d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 40%

---

# 既存のデータセットインクルードファイルの編集{#editing-existing-dataset-include-files}

{{eol}}

既存のデータセットインクルードファイルを編集するための手順について説明します。

既存のデータセットインクルードファイルを開くには、 [!DNL Profile Manager] （data workbench の）

を開き、使用する方法については、 [!DNL Profile Manager]を参照し、 *Data Workbenchユーザーガイド*.

1. データセットプロファイル内で、 [!DNL Profile Manager] をクリックし、 **[!UICONTROL Dataset]** ディレクトリの内容を表示します。

   * を開くには [!DNL Log Processing Dataset Include] ファイルを選択し、 **[!UICONTROL Log Processing]** ディレクトリの内容を表示します。

   * を開くには [!DNL Transformation Dataset Include] ファイルを選択し、 **[!UICONTROL Transformation]** ディレクトリの内容を表示します。

1. 目的のデータセットインクルードファイルの横のチェックマークを右クリックし、 **[!UICONTROL Make Local]**. このファイル用のチェックマークが [!DNL User] 列に表示されます。
1. 新しく作成されたチェックマークを右クリックし、 **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. 設定ウィンドウが表示されます。

   また、 [!DNL Transformation Dependency Maps]. 詳しくは、 [!DNL Transformation Dependency Maps]を参照してください。 [再処理と再変換](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

1. 設定ファイルのパラメーターを必要に応じて編集します。詳しくは、 [ログ処理データセットインクルードファイル](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab) または [変換データセットインクルードファイル](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace) を参照してください。

   Data Workbench ウィンドウ内でデータセットインクルードファイルを編集するときは、基本的な編集機能にショートカットキーを使用できます。切り取り（Ctrl + X）、コピー（Ctrl + C）、貼り付け（Ctrl + V）、取り消し（Ctrl + Z）、やり直し（Ctrl + Shift + Z）、セクション選択（クリックしながらドラッグ）、すべて選択（Ctrl + A）などの操作が可能です。また、ショートカットを使用して、1 つの設定ファイル ( [!DNL .cfg]) を別のに置き換えます。

1. 変更を保存するには、右クリックします。 **[!UICONTROL (modified)]** ウィンドウの上部にあるをクリックし、 **[!UICONTROL Save]**.
1. ローカルで行った変更を有効にするには、 [!DNL Profile Manager]をクリックし、 [!DNL User] 列、「 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*（ profile name は、データセットインクルードファイルが属するデータセットプロファイルまたは継承プロファイルの名前です）。 データセットプロファイルの同期後、データの再処理または再変換が開始されます。

   >[!NOTE]
   >
   >アドビから提供される内部プロファイルには、変更した設定ファイルを一切保存しないでください。内部プロファイルに対するアップデートをインストールするときに変更内容が上書きされます。
