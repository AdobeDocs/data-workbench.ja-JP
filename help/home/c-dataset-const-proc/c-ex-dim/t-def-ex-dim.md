---
description: 拡張ディメンションを定義するための手順を紹介します。
title: 拡張ディメンションの定義
uuid: 25946998-54ca-4595-a2f9-9c593917643a
exl-id: e1664548-e2b4-47bb-8bec-155c16873e08
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 57%

---

# 拡張ディメンションの定義{#defining-extended-dimensions}

{{eol}}

拡張ディメンションを定義するための手順を紹介します。

1. データセットプロファイル内で、 [!DNL Profile Manager] をクリックし、 **[!UICONTROL Dataset]** 内容を表示する。
1. を開きます。 [!DNL Transformation.cfg] ファイルまたは [!DNL Transformation Dataset Include] 拡張ディメンションを定義するファイル。

   * （推奨）データセットインクルードファイルを開くには、 [データセットインクルードファイル](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

      >[!NOTE]
      >
      >Adobeでは、1 つ以上の新しいディメンションで拡張ディメンションを定義することをお勧めします [!DNL Transformation Dataset Include] ファイル。 詳しくは、 [新しいデータセットインクルードファイルの作成](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e).

   * 次の手順で [!DNL Transformation.cfg] ファイル： [変換設定ファイルの編集](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc).

1. 右クリック **[!UICONTROL Transformations]** をクリックし、 **[!UICONTROL Add new]** > *&lt;**[!UICONTROL Extended dimension type]**>*.
1. 拡張ディメンションに必要な情報を入力します。変換のタイプとそのパラメーターに関する情報については、次の節を参照してください。

   * [可算ディメンション](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-count-dim.md#concept-f28b633419494e7bbc510012dbfcc6f8)
   * [シンプルディメンション](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-simple-dim.md#concept-c1d804dac4094489afe61560d2908181)
   * [多対多ディメンション](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-many-dim.md#concept-5ed3cca8b2194d4f96134f6238040998)
   * [数値ディメンション](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-num-dim.md#concept-8513b9afaff447c8b334410b565b91ed)
   * [非正規ディメンション](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-denormal-dim.md#concept-54a2600b8ee748b7acff405daccf3489)
   * [時間ディメンション](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-time-dim.md#concept-1e4eeb8d33964bb2a8d5768d6439df67)

      独自に定義した拡張ディメンションには、そのディメンションに関する詳しい情報や使用上の注意点をコメント行として Comments パラメーターに追加することができます。コメントを追加するには、 **[!UICONTROL Comments]** ラベルとクリック **[!UICONTROL Add new]** > **[!UICONTROL Comment Line]**.

1. 設定ファイルに拡張ディメンションを定義した後、そのファイルをローカルに保存してから、Data Workbench サーバー上のデータセットプロファイルに保存します。
