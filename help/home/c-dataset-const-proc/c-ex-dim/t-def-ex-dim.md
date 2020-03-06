---
description: 拡張ディメンションを定義するための手順を紹介します。
solution: Analytics
title: 拡張ディメンションの定義
topic: Data workbench
uuid: 25946998-54ca-4595-a2f9-9c593917643a
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 拡張ディメンションの定義{#defining-extended-dimensions}

拡張ディメンションを定義するための手順を紹介します。

1. While working in your dataset profile, open the [!DNL Profile Manager] and click **[!UICONTROL Dataset]** to show its contents.
1. Open the [!DNL Transformation.cfg] file or the [!DNL Transformation Dataset Include] file in which you want to define the extended dimension.

   * （推奨）データセットインクルードファイルを開く方法については、「データセットインクルードフ [ァイル」を参照してくださ](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)い。

      >[!NOTE]
      >
      >Adobe recommends defining extended dimensions in one or more new [!DNL Transformation Dataset Include] files. 詳しくは、新しいデータセットインクルードフ [ァイルの作成を参照してくださ](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e)い。

   * ファイルを開くに [!DNL Transformation.cfg] は、「変換設 [定ファイルの編集」を参照してください](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc)。

1. 右クリックし、 **[!UICONTROL Transformations]** 「>」を **[!UICONTROL Add new]** クリッ *クし&#x200B;**[!UICONTROL Extended dimension type]**ます*。
1. 拡張ディメンションに必要な情報を入力します。変換のタイプとそのパラメーターに関する情報については、次の節を参照してください。

   * [可算ディメンション](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-count-dim.md#concept-f28b633419494e7bbc510012dbfcc6f8)
   * [シンプルディメンション](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-simple-dim.md#concept-c1d804dac4094489afe61560d2908181)
   * [多対多ディメンション](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-many-dim.md#concept-5ed3cca8b2194d4f96134f6238040998)
   * [数値ディメンション](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-num-dim.md#concept-8513b9afaff447c8b334410b565b91ed)
   * [非正規ディメンション](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-denormal-dim.md#concept-54a2600b8ee748b7acff405daccf3489)
   * [時間ディメンション](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-time-dim.md#concept-1e4eeb8d33964bb2a8d5768d6439df67)

      独自に定義した拡張ディメンションには、そのディメンションに関する詳しい情報や使用上の注意点をコメント行として Comments パラメーターに追加することができます。コメントを追加するには、ラベルを右クリックし、/ **[!UICONTROL Comments]** をクリッ **[!UICONTROL Add new]** クしま **[!UICONTROL Comment Line]**&#x200B;す。

1. 設定ファイルに拡張ディメンションを定義した後、そのファイルをローカルに保存してから、Data Workbench サーバー上のデータセットプロファイルに保存します。
