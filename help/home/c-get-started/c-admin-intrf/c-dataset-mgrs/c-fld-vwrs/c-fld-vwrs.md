---
description: フィールドビューアは、1 つ以上のデータフィールドの値を格納したテーブルです。
title: フィールドビューア
uuid: 1227b0de-6ae8-4f97-ad3e-5c9ead818ba5
exl-id: 53ede4aa-4865-4e67-b3b1-e3e6287f29d7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 48%

---

# フィールドビューア{#field-viewer}

{{eol}}

フィールドビューアは、1 つ以上のデータフィールドの値を格納したテーブルです。

値が表示されるフィールドは、データセットのログソース、変換、拡張ディメンションの入力または出力です。フィールドの名前は列の見出しに表示され、各行にはソースデータの 1 行に対応するフィールドの値が含まれています。フィールドビューアを使用すると、フィールドの値を確認できるので、記述やテストに役立ちます [正規表現](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).

フィールドビューアを吹き出しとして開くには、 [!DNL Transformation Dependency] からのマッピング、またはスタンドアロンのビジュアライゼーションとして [!DNL Admin] メニュー：

* からのフィールドビューアの作成 [!DNL Transformation Dependency] マップ。 次からフィールドビューアを開くと、 [!DNL Transformation Dependency] マップの場合、ビューアは、右クリックしたログソース、変換、ディメンションに基づいて自動的に入力されます。 ログソースまたは変換の場合、ビューアのフィールドは、ログソースまたは変換の入力または出力です。ディメンションの場合、フィールドはディメンションの入力です。フィールドは必要に応じて追加および削除できます。

* 独立したビジュアライゼーションとしてフィールドビューアを作成する。スタンドアロンのビジュアライゼーションとしてフィールドビューアを開くと、 [!DNL Log Processing Field Viewer] または [!DNL Transformation Field Viewer]. ビューアは空白なので、目的のフィールドをビューアに追加する必要があります。の [!DNL Log Processing Field Viewer]を使用すると、 [!DNL Log Processing.cfg] ファイルまたは任意の [!DNL Log Processing Dataset Include] ファイル。 の [!DNL Transformation Field Viewer]を使用すると、 [!DNL Transformation.cfg] ファイルまたは任意の [!DNL Transformation Dataset Include] ファイル。

![](assets/vis_FieldViewer_OneField.png)

>[!NOTE]
>
>フィールドビューアは、テーブルビジュアライゼーションではありません。したがって、テーブルに関連付けられたプロパティはありません。

フィールドビューア内でのフィールドの追加と削除、およびフィルタリングについて詳しくは、 [管理インターフェイス](../../../../../home/c-get-started/c-admin-intrf/c-admin-intrf.md#concept-855c1a91e1a948969fab592adca15f74).
