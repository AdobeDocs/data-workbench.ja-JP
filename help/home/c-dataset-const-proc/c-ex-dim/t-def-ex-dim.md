---
description: 拡張ディメンションを定義するための手順を紹介します。
title: 拡張ディメンションの定義
uuid: 25946998-54ca-4595-a2f9-9c593917643a
exl-id: e1664548-e2b4-47bb-8bec-155c16873e08
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 57%

---

# 拡張ディメンションの定義{#defining-extended-dimensions}

拡張ディメンションを定義するための手順を紹介します。

1. データセットプロファイル内で[!DNL Profile Manager]を開き、 **[!UICONTROL Dataset]**&#x200B;をクリックして内容を表示します。
1. 拡張ディメンションを定義する[!DNL Transformation.cfg]ファイルまたは[!DNL Transformation Dataset Include]ファイルを開きます。

   * （推奨）データセットインクルードファイルを開くには、[データセットインクルードファイル](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)を参照してください。

      >[!NOTE]
      >
      >Adobeでは、1つ以上の新しい[!DNL Transformation Dataset Include]ファイルに拡張ディメンションを定義することをお勧めします。 詳しくは、[新しいデータセットインクルードファイルの作成](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e)を参照してください。

   * [!DNL Transformation.cfg]ファイルを開くには、[変換設定ファイルの編集](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc)を参照してください。

1. **[!UICONTROL Transformations]**&#x200B;を右クリックし、**[!UICONTROL Add new]** > *&lt;**[!UICONTROL Extended dimension type]**>*&#x200B;をクリックします。
1. 拡張ディメンションに必要な情報を入力します。変換のタイプとそのパラメーターに関する情報については、次の節を参照してください。

   * [可算ディメンション](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-count-dim.md#concept-f28b633419494e7bbc510012dbfcc6f8)
   * [シンプルディメンション](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-simple-dim.md#concept-c1d804dac4094489afe61560d2908181)
   * [多対多ディメンション](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-many-dim.md#concept-5ed3cca8b2194d4f96134f6238040998)
   * [数値ディメンション](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-num-dim.md#concept-8513b9afaff447c8b334410b565b91ed)
   * [非正規ディメンション](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-denormal-dim.md#concept-54a2600b8ee748b7acff405daccf3489)
   * [時間ディメンション](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-time-dim.md#concept-1e4eeb8d33964bb2a8d5768d6439df67)

      独自に定義した拡張ディメンションには、そのディメンションに関する詳しい情報や使用上の注意点をコメント行として Comments パラメーターに追加することができます。コメントを追加するには、**[!UICONTROL Comments]**&#x200B;ラベルを右クリックし、**[!UICONTROL Add new]** / **[!UICONTROL Comment Line]**&#x200B;をクリックします。

1. 設定ファイルに拡張ディメンションを定義した後、そのファイルをローカルに保存してから、Data Workbench サーバー上のデータセットプロファイルに保存します。
