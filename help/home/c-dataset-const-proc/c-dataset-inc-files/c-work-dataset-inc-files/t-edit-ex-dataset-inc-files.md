---
description: 既存のデータセットインクルードファイルを編集するための手順について説明します。
title: 既存のデータセットインクルードファイルの編集
uuid: fcce2e46-b4a8-4c53-83bb-32ab410eb89e
exl-id: f4095871-d004-4e10-af18-bf6c1e47493d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 40%

---

# 既存のデータセットインクルードファイルの編集{#editing-existing-dataset-include-files}

既存のデータセットインクルードファイルを編集するための手順について説明します。

Data Workbenchの[!DNL Profile Manager]を使用して、既存のデータセットインクルードファイルを開きます。

[!DNL Profile Manager]を開いて使用する方法については、『*Data Workbenchユーザーガイド*』を参照してください。

1. データセットプロファイル内で[!DNL Profile Manager]を開き、**[!UICONTROL Dataset]**&#x200B;をクリックしてディレクトリの内容を表示します。

   * [!DNL Log Processing Dataset Include]ファイルを開くには、**[!UICONTROL Log Processing]**&#x200B;をクリックしてディレクトリの内容を表示します。

   * [!DNL Transformation Dataset Include]ファイルを開くには、**[!UICONTROL Transformation]**&#x200B;をクリックしてディレクトリの内容を表示します。

1. 目的のデータセットインクルードファイルの横のチェックマークを右クリックし、「**[!UICONTROL Make Local]**」をクリックします。 このファイル用のチェックマークが [!DNL User] 列に表示されます。
1. 新しく作成されたチェックマークを右クリックし、**[!UICONTROL Open]** / **[!UICONTROL from the workbench]**&#x200B;をクリックします。 設定ウィンドウが表示されます。

   [!DNL Transformation Dependency Maps]からデータセットインクルードファイルを開くこともできます。 [!DNL Transformation Dependency Maps]について詳しくは、[再処理と再変換](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md)を参照してください。

1. 設定ファイルのパラメーターを必要に応じて編集します。パラメーターの説明については、[ログ処理データセットインクルードファイル](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab)または[変換データセットインクルードファイル](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace)を参照してください。

   Data Workbench ウィンドウ内でデータセットインクルードファイルを編集するときは、基本的な編集機能にショートカットキーを使用できます。切り取り（Ctrl + X）、コピー（Ctrl + C）、貼り付け（Ctrl + V）、取り消し（Ctrl + Z）、やり直し（Ctrl + Shift + Z）、セクション選択（クリックしながらドラッグ）、すべて選択（Ctrl + A）などの操作が可能です。また、設定ファイル([!DNL .cfg])間でテキストをコピーして貼り付ける際にも、ショートカットを使用できます。

1. 変更を保存するには、ウィンドウ上部の&#x200B;**[!UICONTROL (modified)]**&#x200B;を右クリックし、「**[!UICONTROL Save]**」をクリックします。
1. ローカルで作成した変更を反映するには、[!DNL Profile Manager]で[!DNL User]列のファイルのチェックマークを右クリックし、 **[!UICONTROL Save to]** / *&lt;**[!UICONTROL profile name]***&#x200B;をクリックします。profile nameは、データセットインクルードファイルが属するデータセットプロファイルまたは継承プロファイルの名前です。 データセットプロファイルの同期後、データの再処理または再変換が開始されます。

   >[!NOTE]
   >
   >アドビから提供される内部プロファイルには、変更した設定ファイルを一切保存しないでください。内部プロファイルに対するアップデートをインストールするときに変更内容が上書きされます。
