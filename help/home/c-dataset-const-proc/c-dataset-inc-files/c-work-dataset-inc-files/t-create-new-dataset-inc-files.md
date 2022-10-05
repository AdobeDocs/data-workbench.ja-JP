---
description: 新しいデータセットインクルードファイルを作成するための手順について説明します。
title: 新しいデータセットインクルードファイルの作成
uuid: 707bdd84-b12b-4226-b6aa-43c9fc7ec9fe
exl-id: 8a7b343d-b695-41aa-b465-8c5cd68d6ef7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 42%

---

# 新しいデータセットインクルードファイルの作成{#creating-new-dataset-include-files}

{{eol}}

新しいデータセットインクルードファイルを作成するための手順について説明します。

以下のデータセット設定作業では、いずれも新しいデータセットインクルードファイルを作成する必要があります。

* ログ処理から変換に渡すデータに対し新しいフィールドを指定する。
* 次のいずれかの処理を行う変換を定義する。

   * 既存のログフィールドを更新する。
   * ログ処理から変換に渡す新しいフィールドまたは拡張ディメンションの定義に使用する新しいフィールドを作成する。

      利用可能な変換のタイプについて詳しくは、 [データ変換](../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

      >[!NOTE]
      >
      >新しいデータセットインクルードファイルに変換を定義する場合は、入力と出力の順序を念頭に置いてください。 変換の順序について詳しくは、 [変換を構築する際の規則](../../../../home/c-dataset-const-proc/c-data-trans/c-con-transf.md#concept-01998eebb7e347c58255fb442f2613b6).

* 拡張ディメンションを作成する。利用可能なディメンションのタイプについて詳しくは、 [拡張ディメンション](../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

1. データセットプロファイル内で、 [!DNL Profile Manager] をクリックし、 **[!UICONTROL Dataset]** をクリックして、既存のデータセットインクルードファイルを表示します。

   * 次の手順で [!DNL Log Processing Dataset Include] ファイル、クリック **[!UICONTROL Log Processing]**.

   * 次の手順で [!DNL Transformation Dataset Include] ファイル、クリック **[!UICONTROL Transformation]**.

1. 新しい [!DNL Log Processing] または [!DNL Transformation Dataset Include] ファイルを作成するには、次のいずれかの手順を実行します。

   * 内 [!DNL User] 列をクリックします。 **[!UICONTROL Create]** > **[!UICONTROL New Log Processing]**. という名前のファイル [!DNL New Log Processing.cfg] がディレクトリに表示されます。

   * 内 [!DNL User] 列をクリックします。 **[!UICONTROL Create]** > **[!UICONTROL New Transformation]**. という名前のファイル [!DNL New Transformation.cfg] がディレクトリに表示されます。

1. 新しいファイルの名前を変更するには、 [!DNL User] 列を開き、File パラメータに新しい名前を入力します。

   ![ステップ情報](assets/vis_ProfileManager_RenameFile.png)

1. 名前を変更したファイルのチェックマークを右クリックし、 **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. 設定ウィンドウが表示されます。
1. 設定ファイルのパラメーターを必要に応じて編集します。詳しくは、 [ログ処理データセットインクルードファイル](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab) または [変換データセットインクルードファイル](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace) を参照してください。
1. 変更を保存するには、右クリックします。 **[!UICONTROL (modified)]** ウィンドウの上部にあるをクリックし、 **[!UICONTROL Save]**.
1. ローカルで行った変更を有効にするには、 [!DNL Profile Manager]をクリックし、 [!DNL User] 列、「 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*（ profile name は、データセットインクルードファイルが属するデータセットプロファイルまたは継承プロファイルの名前です）。 データセットプロファイルの同期後、データの再処理または再変換が開始されます。

   >[!NOTE]
   >
   >アドビから提供される内部プロファイルには、変更した設定ファイルを一切保存しないでください。内部プロファイルに対するアップデートをインストールするときに変更内容が上書きされます。

作成したデータセットインクルードファイルを編集するには、 [既存のデータセットインクルードファイルの編集](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077).
