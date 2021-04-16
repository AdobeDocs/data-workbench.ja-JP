---
description: Insight サーバー（InsightServer64.exe）を使用すると、イベントデータまたはルックアップデータからカスタムディメンションを定義できます。
title: 拡張ディメンションについて
uuid: ae014a26-5286-4e36-9098-aaa463d9fe05
exl-id: f74aa85e-f880-4ab5-a8fb-128862aa808f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 58%

---

# 拡張ディメンションについて{#about-extended-dimensions}

Insight サーバー（InsightServer64.exe）を使用すると、イベントデータまたはルックアップデータからカスタムディメンションを定義できます。

独自に定義したカスタムディメンションはすべて「拡張ディメンション」と呼ばれます。拡張ディメンションを使用したビジュアライゼーションや拡張指標の作成、分析によって、ビジネスチャンネルに関連した業務や問題を把握することができます。複数のタイプの拡張ディメンションを[!DNL Transformation.cfg]ファイルまたは[!DNL Transformation Dataset Include]ファイルに定義できます。

拡張ディメンションは、ログフィールドの値と親ディメンション間の関係を表します。親ディメンションには、ユーザー定義の任意の可算ディメンションを指定することができます。詳しくは、 [可算ディメンション](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-count-dim.md#concept-f28b633419494e7bbc510012dbfcc6f8). 親は、[!DNL Transformation.cfg]ファイルまたは[!DNL Transformation Dataset Include]ファイルでディメンションを定義するときに指定します。 ディメンションのレベルは、その親と一致します。例えば、Session という親を持つディメンションは、Session レベルのディメンションになります。

>[!NOTE]
>
>ログフィールドの値は、ログ([!DNL .vsl])ファイルに固有の値、その他のイベントデータソース、または変換を使用して作成された拡張ログフィールドから取得できます。

ビジュアライゼーションに拡張ディメンションを追加するには、[!DNL Select Dimension]メニュー内の拡張リストからそのディメンションにアクセスします。 例えば、グラフのビジュアライゼーションに拡張ディメンションを追加するには、ワークスペース内で右クリックし、**[!UICONTROL Add Visualization]**/**[!UICONTROL Graph]**/**[!UICONTROL Extended]**/***[!UICONTROL dimension name]**>*&#x200B;をクリックします。 Data Workbench のインターフェイスに表示される拡張ディメンションのリストを整理したい場合は、サブフォルダーを作成して、そこに拡張ディメンションを移動することができます。『*Data Workbench ユーザーガイド*』の「管理インターフェイス」という章を参照してください。この場合、メニューにサブフォルダーの名前が追加され、ビジュアライゼーションを追加します／グラフ／拡張／&lt;*subfolder name*>／&lt;*dimension name*> のように表示されます。

データセットプロファイルに定義されているすべてのディメンションと各ディメンションのバッファーサイズを確認するには、data workbenchで[!DNL Detailed Status]インターフェイスを開き、**[!UICONTROL Performance]**&#x200B;をクリックしてから&#x200B;**[!UICONTROL Dimensions]**&#x200B;をクリックしてノードを展開します。 バッファーサイズは MB 単位で表示されます。クエリー時間は、バッファーサイズによってコントロールされます。[!DNL Detailed Status]インターフェイスの詳細については、『サーバー管理とインストール』ガイドを参照してください。
