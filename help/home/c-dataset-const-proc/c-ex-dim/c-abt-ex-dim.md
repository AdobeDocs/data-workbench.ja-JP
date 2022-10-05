---
description: Insight サーバー（InsightServer64.exe）を使用すると、イベントデータまたはルックアップデータからカスタムディメンションを定義できます。
title: 拡張ディメンションについて
uuid: ae014a26-5286-4e36-9098-aaa463d9fe05
exl-id: f74aa85e-f880-4ab5-a8fb-128862aa808f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 58%

---

# 拡張ディメンションについて{#about-extended-dimensions}

{{eol}}

Insight サーバー（InsightServer64.exe）を使用すると、イベントデータまたはルックアップデータからカスタムディメンションを定義できます。

独自に定義したカスタムディメンションはすべて「拡張ディメンション」と呼ばれます。拡張ディメンションを使用したビジュアライゼーションや拡張指標の作成、分析によって、ビジネスチャンネルに関連した業務や問題を把握することができます。複数のタイプの拡張ディメンションを [!DNL Transformation.cfg] ファイルまたは [!DNL Transformation Dataset Include] ファイル。

拡張ディメンションは、ログフィールドの値と親ディメンション間の関係を表します。親ディメンションには、ユーザー定義の任意の可算ディメンションを指定することができます。詳しくは、 [可算ディメンション](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-count-dim.md#concept-f28b633419494e7bbc510012dbfcc6f8). 親を指定するには、 [!DNL Transformation.cfg] ファイルまたは [!DNL Transformation Dataset Include] ファイル。 ディメンションのレベルは、その親と一致します。例えば、Session という親を持つディメンションは、Session レベルのディメンションになります。

>[!NOTE]
>
>ログフィールドの値は、ログ ( [!DNL .vsl]) ファイルやその他のイベントデータソース、または変換を使用して作成された拡張ログフィールドから取得します。

ビジュアライゼーションに拡張ディメンションを追加するには、 [!DNL Select Dimension] メニュー 例えば、グラフのビジュアライゼーションに拡張ディメンションを追加するには、ワークスペース内で右クリックし、 **[!UICONTROL Add Visualization]** > **[!UICONTROL Graph]** > **[!UICONTROL Extended]** > *&lt;**[!UICONTROL dimension name]**>*. Data Workbench のインターフェイスに表示される拡張ディメンションのリストを整理したい場合は、サブフォルダーを作成して、そこに拡張ディメンションを移動することができます。『*Data Workbench ユーザーガイド*』の「管理インターフェイス」という章を参照してください。この場合、メニューにサブフォルダーの名前が追加され、ビジュアライゼーションを追加します／グラフ／拡張／&lt;*subfolder name*>／&lt;*dimension name*> のように表示されます。

データセットプロファイルに定義されているすべてのディメンションとそれぞれのバッファーサイズを確認するには、 [!DNL Detailed Status] data workbench のインターフェイスを開き、 **[!UICONTROL Performance]**&#x200B;を、 **[!UICONTROL Dimensions]** ノードを展開します。 バッファーサイズは MB 単位で表示されます。クエリー時間は、バッファーサイズによってコントロールされます。詳しくは、 [!DNL Detailed Status] インターフェイスについては、『サーバー管理およびインストールガイド』を参照してください。
