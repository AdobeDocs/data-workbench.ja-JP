---
description: フィールドビューアは、1 つ以上のデータフィールドの値を格納したテーブルです。
solution: Analytics
title: フィールドビューア
topic: Data workbench
uuid: 1227b0de-6ae8-4f97-ad3e-5c9ead818ba5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# フィールドビューア{#field-viewer}

フィールドビューアは、1 つ以上のデータフィールドの値を格納したテーブルです。

値が表示されるフィールドは、データセットのログソース、変換、拡張ディメンションの入力または出力です。フィールドの名前は列の見出しに表示され、各行にはソースデータの 1 行に対応するフィールドの値が含まれています。Because field viewers enable you to see a field’s values, they are helpful in writing and testing [regular expressions](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).

You can open a field viewer as a callout from a [!DNL Transformation Dependency] map or as a standalone visualization from the [!DNL Admin] menu:

* Creating a field viewer from a [!DNL Transformation Dependency] map. When you open a field viewer from a [!DNL Transformation Dependency] map, the viewer is populated automatically based on the log source, transformation, or dimension that you right-click. ログソースまたは変換の場合、ビューアのフィールドは、ログソースまたは変換の入力または出力です。ディメンションの場合、フィールドはディメンションの入力です。フィールドは必要に応じて追加および削除できます。

* 独立したビジュアライゼーションとしてフィールドビューアを作成する。フィールドビューアをスタンドアロンのビジュアライゼーションとして開くと、またはを作 [!DNL Log Processing Field Viewer] 成できま [!DNL Transformation Field Viewer]す。 ビューアは空白なので、目的のフィールドをビューアに追加する必要があります。の場合は、フ [!DNL Log Processing Field Viewer]ァイルまたは任意のファイルからフ [!DNL Log Processing.cfg] ィールドを追加で [!DNL Log Processing Dataset Include] きます。 の場合は、フ [!DNL Transformation Field Viewer]ァイルまたは任意のファイルからフ [!DNL Transformation.cfg] ィールドを追加で [!DNL Transformation Dataset Include] きます。

![](assets/vis_FieldViewer_OneField.png)

>[!NOTE]
>
>フィールドビューアはテーブルのビジュアライゼーションではありません。したがって、テーブルに関連付けられたプロパティはありません。

フィールドビューア内でのフィールドの追加と削除、およびフィルタリングについて詳しくは、「管理インターフェイス」を [参照してくださ](../../../../../home/c-get-started/c-admin-intrf/c-admin-intrf.md#concept-855c1a91e1a948969fab592adca15f74)い。
