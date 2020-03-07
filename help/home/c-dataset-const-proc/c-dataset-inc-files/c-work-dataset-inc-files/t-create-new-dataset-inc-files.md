---
description: 新しいデータセットインクルードファイルを作成するための手順について説明します。
solution: Analytics
title: 新しいデータセットインクルードファイルの作成
topic: Data workbench
uuid: 707bdd84-b12b-4226-b6aa-43c9fc7ec9fe
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 新しいデータセットインクルードファイルの作成{#creating-new-dataset-include-files}

新しいデータセットインクルードファイルを作成するための手順について説明します。

以下のデータセット設定作業では、いずれも新しいデータセットインクルードファイルを作成する必要があります。

* ログ処理から変換に渡すデータに対し新しいフィールドを指定する。
* 次のいずれかの処理を行う変換を定義する。

   * 既存のログフィールドを更新する。
   * ログ処理から変換に渡す新しいフィールドまたは拡張ディメンションの定義に使用する新しいフィールドを作成する。

      利用可能な変換のタイプについて詳しくは、[データ変換](../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md)を参照してください。

      >[!NOTE]
      >
      >新しいデータセットインクルードファイルに変換を定義する場合は、入力と出力の順序を考慮してください。 変換の順序について詳しくは、変換を構築する際の表記 [規則を参照してください](../../../../home/c-dataset-const-proc/c-data-trans/c-con-transf.md#concept-01998eebb7e347c58255fb442f2613b6)。

* 拡張ディメンションを作成する。利用可能なディメンションのタイプについて詳しくは、 [拡張ディメンション](../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

1. While working in your dataset profile, open the [!DNL Profile Manager] and click **[!UICONTROL Dataset]** to view the existing dataset include files.

   * ファイルを表示する [!DNL Log Processing Dataset Include] には、をクリックしま **[!UICONTROL Log Processing]**&#x200B;す。

   * ファイルを表示する [!DNL Transformation Dataset Include] には、をクリックしま **[!UICONTROL Transformation]**&#x200B;す。

1. 次のいずれかの手順 [!DNL Log Processing] を実行し [!DNL Transformation Dataset Include] て、新しいファイルまたはファイルを作成します。

   * ログ処理デ [!DNL User] ィレクトリの列で、/をクリ **[!UICONTROL Create]** ックしま **[!UICONTROL New Log Processing]**&#x200B;す。 A file named [!DNL New Log Processing.cfg] appears in the directory.

   * Transformationディレクトリ [!DNL User] の列で、/をクリッ **[!UICONTROL Create]** クしま **[!UICONTROL New Transformation]**&#x200B;す。 A file named [!DNL New Transformation.cfg] appears in the directory.

1. Rename the new file by right-clicking its check mark in the [!DNL User] column and typing the new name in the File parameter.

   ![ステップ情報](assets/vis_ProfileManager_RenameFile.png)

1. Right-click the check mark for the renamed file and click **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. 設定ウィンドウが表示されます。
1. 設定ファイルのパラメーターを必要に応じて編集します。使用可能な [パラメーターの説明については、](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab) Log Processing Dataset Include Files [](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace) （ログ処理データセットインクルードファイル）またはTransformation Dataset Include Files（変換データセットインクルードファイル）を参照してください。
1. To save your changes, right-click **[!UICONTROL (modified)]** at the top of the window and click **[!UICONTROL Save]**.
1. To make the locally made changes take effect, in the [!DNL Profile Manager], right-click the check mark for the file in the [!DNL User] column, then click **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, where profile name is the name of the dataset profile or the inherited profile to which the dataset include file belongs. データセットプロファイルの同期後、データの再処理または再変換が開始されます。

   >[!NOTE]
   >
   >アドビから提供される内部プロファイルには、変更した設定ファイルを一切保存しないでください。内部プロファイルに対するアップデートをインストールするときに変更内容が上書きされます。

作成したデータセットインクルードファイルを編集する方法については、 [Editing Existing Dataset Include Filesを参照してください](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077)。
