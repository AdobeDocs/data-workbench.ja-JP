---
description: Insight サーバー（InsightServer64.exe）を使用すると、イベントデータまたはルックアップデータからカスタムディメンションを定義できます。
solution: Analytics
title: 拡張ディメンションについて
topic: Data workbench
uuid: ae014a26-5286-4e36-9098-aaa463d9fe05
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 拡張ディメンションについて{#about-extended-dimensions}

Insight サーバー（InsightServer64.exe）を使用すると、イベントデータまたはルックアップデータからカスタムディメンションを定義できます。

独自に定義したカスタムディメンションはすべて「拡張ディメンション」と呼ばれます。拡張ディメンションを使用したビジュアライゼーションや拡張指標の作成、分析によって、ビジネスチャンネルに関連した業務や問題を把握することができます。You can define several types of extended dimensions in the [!DNL Transformation.cfg] file or in [!DNL Transformation Dataset Include] files.

拡張ディメンションは、ログフィールドの値と親ディメンション間の関係を表します。親ディメンションには、ユーザー定義の任意の可算ディメンションを指定することができます。詳しくは、 [可算ディメンション](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-count-dim.md#concept-f28b633419494e7bbc510012dbfcc6f8). You specify the parent when defining the dimension in the [!DNL Transformation.cfg] file or a [!DNL Transformation Dataset Include] file. ディメンションのレベルは、その親と一致します。例えば、Session という親を持つディメンションは、Session レベルのディメンションになります。

>[!NOTE]
>
>The log field values can come from the inherent values available in the log ( [!DNL .vsl]) files or other event data sources or from extended log fields created through the use of transformations.

To add an extended dimension to a visualization, you access it from the Extended list within the [!DNL Select Dimension] menu. For example, to add an extended dimension to a graph visualization, you would right-click within the workspace and click **[!UICONTROL Add Visualization]** > **[!UICONTROL Graph]** > **[!UICONTROL Extended]** > *&lt;**[!UICONTROL dimension name]**>*. Data Workbench のインターフェイスに表示される拡張ディメンションのリストを整理したい場合は、サブフォルダーを作成して、そこに拡張ディメンションを移動することができます。『*Data Workbench ユーザーガイド*』の「管理インターフェイス」という章を参照してください。この場合、メニューにサブフォルダーの名前が追加され、ビジュアライゼーションを追加します／グラフ／拡張／&lt;*subfolder name*>／&lt;*dimension name*> のように表示されます。

To see all the dimensions that have been defined for your dataset profile and the buffer size for each, open the [!DNL Detailed Status] interface in data workbench and click **[!UICONTROL Performance]**, then **[!UICONTROL Dimensions]** to expand the nodes. バッファーサイズは MB 単位で表示されます。クエリー時間は、バッファーサイズによってコントロールされます。For more information about the [!DNL Detailed Status] interface, see the Server Administration and Installation guide.
