---
description: フィールドビューアは、1 つ以上のデータフィールドの値を格納したテーブルです。
title: フィールドビューア
uuid: 1227b0de-6ae8-4f97-ad3e-5c9ead818ba5
exl-id: 53ede4aa-4865-4e67-b3b1-e3e6287f29d7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 48%

---

# フィールドビューア{#field-viewer}

フィールドビューアは、1 つ以上のデータフィールドの値を格納したテーブルです。

値が表示されるフィールドは、データセットのログソース、変換、拡張ディメンションの入力または出力です。フィールドの名前は列の見出しに表示され、各行にはソースデータの 1 行に対応するフィールドの値が含まれています。フィールドビューアを使用すると、フィールドの値を確認できるので、[正規式](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c)を記述し、テストする場合に役立ちます。

フィールドビューアは、[!DNL Transformation Dependency]マップから引き出し線として、または[!DNL Admin]メニューから単独のビジュアライゼーションとして開くことができます。

* [!DNL Transformation Dependency]マップからフィールドビューアを作成する [!DNL Transformation Dependency]マップからフィールドビューアを開くと、右クリックしたログソース、変換、ディメンションに基づいて、ビューアの内容が自動的に入力されます。 ログソースまたは変換の場合、ビューアのフィールドは、ログソースまたは変換の入力または出力です。ディメンションの場合、フィールドはディメンションの入力です。フィールドは必要に応じて追加および削除できます。

* 独立したビジュアライゼーションとしてフィールドビューアを作成する。単独のビジュアライゼーションとしてフィールドビューアを開く場合は、[!DNL Log Processing Field Viewer]または[!DNL Transformation Field Viewer]を作成できます。 ビューアは空白なので、目的のフィールドをビューアに追加する必要があります。[!DNL Log Processing Field Viewer]の場合は、[!DNL Log Processing.cfg]ファイルまたは任意の[!DNL Log Processing Dataset Include]ファイルからフィールドを追加できます。 [!DNL Transformation Field Viewer]の場合は、[!DNL Transformation.cfg]ファイルまたは任意の[!DNL Transformation Dataset Include]ファイルからフィールドを追加できます。

![](assets/vis_FieldViewer_OneField.png)

>[!NOTE]
>
>フィールドビューアは、テーブルのビジュアライゼーションではありません。したがって、テーブルに関連付けられたプロパティはありません。

フィールドビューア内でのフィールドの追加と削除、およびフィルタリングについて詳しくは、[管理インターフェイス](../../../../../home/c-get-started/c-admin-intrf/c-admin-intrf.md#concept-855c1a91e1a948969fab592adca15f74)を参照してください。
