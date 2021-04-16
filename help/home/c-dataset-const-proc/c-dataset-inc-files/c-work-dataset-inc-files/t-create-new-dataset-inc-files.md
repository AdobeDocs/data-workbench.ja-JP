---
description: 新しいデータセットインクルードファイルを作成するための手順について説明します。
title: 新しいデータセットインクルードファイルの作成
uuid: 707bdd84-b12b-4226-b6aa-43c9fc7ec9fe
exl-id: 8a7b343d-b695-41aa-b465-8c5cd68d6ef7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 42%

---

# 新しいデータセットインクルードファイルの作成{#creating-new-dataset-include-files}

新しいデータセットインクルードファイルを作成するための手順について説明します。

以下のデータセット設定作業では、いずれも新しいデータセットインクルードファイルを作成する必要があります。

* ログ処理から変換に渡すデータに対し新しいフィールドを指定する。
* 次のいずれかの処理を行う変換を定義する。

   * 既存のログフィールドを更新する。
   * ログ処理から変換に渡す新しいフィールドまたは拡張ディメンションの定義に使用する新しいフィールドを作成する。

      利用可能な変換のタイプについて詳しくは、 [データ変換](../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

      >[!NOTE]
      >
      >新しいデータセットインクルードファイルに変換を定義する場合は、入力と出力の順序に注意してください。 変換の順序について詳しくは、[変換を構築する際の規則](../../../../home/c-dataset-const-proc/c-data-trans/c-con-transf.md#concept-01998eebb7e347c58255fb442f2613b6)を参照してください。

* 拡張ディメンションを作成する。利用可能なディメンションのタイプについて詳しくは、 [拡張ディメンション](../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

1. データセットプロファイルー内で[!DNL Profile Manager]を開き、**[!UICONTROL Dataset]**&#x200B;をクリックして既存のデータセットインクルードファイルを表示します。

   * [!DNL Log Processing Dataset Include]ファイルを表示するには、**[!UICONTROL Log Processing]**&#x200B;をクリックします。

   * [!DNL Transformation Dataset Include]ファイルを表示するには、**[!UICONTROL Transformation]**&#x200B;をクリックします。

1. 次のいずれかの手順を実行して、新しい[!DNL Log Processing]ファイルまたは[!DNL Transformation Dataset Include]ファイルを作成します。

   * ログ処理ディレクトリの[!DNL User]列で、**[!UICONTROL Create]** > **[!UICONTROL New Log Processing]**&#x200B;をクリックします。 [!DNL New Log Processing.cfg]という名前のファイルがディレクトリに表示されます。

   * 変換ディレクトリの[!DNL User]列で、**[!UICONTROL Create]** > **[!UICONTROL New Transformation]**&#x200B;をクリックします。 [!DNL New Transformation.cfg]という名前のファイルがディレクトリに表示されます。

1. [!DNL User]列のチェックマークを右クリックし、Fileパラメーターに新しい名前を入力して、新しいファイルの名前を変更します。

   ![ステップ情報](assets/vis_ProfileManager_RenameFile.png)

1. 名前を変更したファイルのチェックマークを右クリックし、**[!UICONTROL Open]**/**[!UICONTROL from the workbench]**&#x200B;をクリックします。 設定ウィンドウが表示されます。
1. 設定ファイルのパラメーターを必要に応じて編集します。使用可能なパラメーターの説明については、[ログ処理データセットインクルードファイル](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab)または[変換データセットインクルードファイル](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace)を参照してください。
1. 変更を保存するには、ウィンドウ上部の&#x200B;**[!UICONTROL (modified)]**&#x200B;を右クリックし、**[!UICONTROL Save]**&#x200B;をクリックします。
1. ローカルに適用した変更を有効にするには、[!DNL Profile Manager]で[!DNL User]列のファイルのチェックマークを右クリックし、**[!UICONTROL Save to]** > ***[!UICONTROL profile name]***&#x200B;をクリックします。プロファイル名は、データセットインクルードファイルが属するデータセットプロファイル名または継承プロファイルです。 データセットプロファイルの同期後、データの再処理または再変換が開始されます。

   >[!NOTE]
   >
   >アドビから提供される内部プロファイルには、変更した設定ファイルを一切保存しないでください。内部プロファイルに対するアップデートをインストールするときに変更内容が上書きされます。

作成したデータセットインクルードファイルを編集する方法については、[Editing Existing Dataset Include Files](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077)を参照してください。
